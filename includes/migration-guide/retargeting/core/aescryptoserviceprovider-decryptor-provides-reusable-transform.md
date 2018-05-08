### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>AesCryptoServiceProvider odszyfrowujący zawiera transformacji wielokrotnego użytku

|   |   |
|---|---|
|Szczegóły|Począwszy od aplikacji przeznaczonych dla platformy .NET Framework 4.6.2, <xref:System.Security.Cryptography.AesCryptoServiceProvider> odszyfrowujący zawiera transformacji wielokrotnego użytku. Po wywołaniu <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=name>, transformacja są ponownie inicjowane i mogą być ponownie używane. Dla aplikacji przeznaczonych dla wcześniejszych wersji programu .NET Framework, próba ponownego użycia odszyfrowujący, wywołując <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=name> po wywołaniu <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=name> zgłasza <xref:System.Security.Cryptography.CryptographicException> lub uszkodzone dane.|
|Sugestia|Wpływ tej zmiany należy minimalny, ponieważ jest to oczekiwane zachowanie. Aplikacje zależne od poprzedniego zachowanie można zrezygnować z za pomocą go, dodając następujące ustawienia konfiguracji do <code>&lt;runtime&gt;</code> sekcji pliku konfiguracji aplikacji:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Ponadto aplikacje docelowe poprzedniej wersji programu .NET Framework, które działają w ramach wersji platformy .NET w programie .NET Framework 4.6.2 zgodzić się na on, dodając następujące ustawienia konfiguracji do <code>&lt;runtime&gt;</code> sekcji plik konfiguracji aplikacji:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Zakres|Pomocnicza|
|Wersja|4.6.2|
|Typ|Przekierowania|
|Dotyczy interfejsów API|<ul><li><xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType></li></ul>|
