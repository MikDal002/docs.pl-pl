### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a>Zmiany w znaku separatora ścieżki we właściwości pełną nazwę obiektu klasy ZipArchiveEntry obiektów

|   |   |
|---|---|
|Szczegóły|W przypadku aplikacji przeznaczonych dla platformy .NET Framework 4.6.1 i nowszych wersjach znak separatora ścieżki zmienił się z ukośnik odwrotny (&quot;&quot;) na ukośnik (&quot;/&quot;) w <xref:System.IO.Compression.ZipArchiveEntry.FullName> właściwości <xref:System.IO.Compression.ZipArchiveEntry> obiekty utworzone przez przeciążeń <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> metody. Zmiana powoduje implementacji .NET do zgodności z sekcji 4.4.17.1 [. Specyfikacją formatu pliku ZIP](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) i umożliwia. Archiwa ZIP do można zdekompresować w systemach z systemem innym niż Windows.<br />Podczas dekompresowania pliku zip utworzonego przez aplikację którego element docelowy poprzedniej wersji programu .NET Framework w systemach operacyjnych z systemem innym niż Windows, takich jak Macintosh nie powiedzie się, aby zachować struktura katalogów. Na przykład w przypadku komputerów Macintosh tworzy zestaw plików, których nazwy łączy ścieżki katalogu, wraz z dowolnym ukośnik odwrotny (&quot;&quot;) znaków, a nazwa pliku. W związku z tym struktura katalogów zdekompresowanych plików nie są zachowywane.|
|Sugestia|Wpływ tej zmiany na. Pliki ZIP, które są zdekompresować w systemie operacyjnym Windows przez interfejs API programu .NET Framework <xref:System.IO?displayProperty=nameWithType> przestrzeń nazw powinna mieć minimalny, ponieważ te interfejsy API bezproblemowo może obsłużyć albo ukośnika ("`/`") ani ukośnika odwrotnego ("`\`") jako ścieżka znak separatora.<br />Jeśli ta zmiana jest niepożądane, można zrezygnować z go, dodając ustawienia konfiguracji w celu [ <runtime> ](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sekcji pliku konfiguracji aplikacji. W poniższym przykładzie przedstawiono oba <code>&lt;runtime&gt;</code> sekcji i <code>Switch.System.IO.Compression.ZipFile.UseBackslash</code> przełącznika zrezygnować:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Ponadto aplikacje docelowe poprzednie wersje programu .NET Framework, które są uruchomione w programie .NET Framework 4.6.1 i nowszych wersjach zgodzić się na to zachowanie przez dodanie ustawienia konfiguracji do [ <runtime> ](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sekcji plik konfiguracji aplikacji. Poniżej pokazano zarówno <code>&lt;runtime&gt;</code> sekcji i <code>Switch.System.IO.Compression.ZipFile.UseBackslash</code> opcjonalnych przełącznika.<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Compression.ZipFile.UseBackslash=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Zakres|Krawędź|
|Wersja|4.6.1|
|Typ|Przekierowania|
|Dotyczy interfejsów API|<ul><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType></li><li><xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType></li></ul>|
