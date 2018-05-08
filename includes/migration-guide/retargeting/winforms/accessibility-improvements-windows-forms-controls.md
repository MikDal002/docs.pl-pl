### <a name="accessibility-improvements-in-windows-forms-controls"></a>Ulepszenia ułatwień dostępu w formantach formularzy systemu Windows

|   |   |
|---|---|
|Szczegóły|Formularze systemu Windows w celu ulepszania jak działa z technologiami ułatwień dostępu w celu skuteczniejszej obsługi klientów formularzy systemu Windows. Obejmują one następujące zmiany w programie .NET Framework 4.7.1:<ul><li>Zmiany w celu polepszenia wyświetlone w trybie dużego kontrastu.</li><li>Zmiany w celu polepszenia przeglądania właściwości. Właściwość przeglądarki ulepszenia obejmują:</li><li>Lepsze nawigacji klawiatury przez różne okna wyboru z listy rozwijanej.</li><li>Zmniejszona niepotrzebnych tabulatorów.</li><li>Lepiej raportowanie typy formantów.</li><li>Ulepszone narrator zachowanie.</li><li>Zmiany do zaimplementowania w formantach Brak wzorce ułatwień dostępu interfejsu użytkownika.</li></ul>|
|Sugestia|<strong>Jak zgłosić do lub z tych zmian do</strong></br>Aby aplikacji do korzystania z tych zmian, należy uruchomić w programie .NET Framework 4.7.1 lub nowszym. Aplikacji mogą korzystać z tych zmian w jednym z następujących sposobów:<ul><li>Jest ponownie kompilowana docelową programu .NET Framework 4.7.1. Te zmiany ułatwień dostępu są domyślnie włączona w aplikacji formularzy systemu Windows, które odnoszą się do programu .NET Framework 4.7.1 lub nowszym.</li><li>Zdecyduje poza zachowania starszych ułatwień dostępu, dodając następujące [przełącznika AppContext](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) do <code>&lt;runtime&gt;</code> sekcji w pliku app.config i ustawieniem dla niego <code>false</code>, jak pokazano na poniższym przykładzie.</li></ul><pre><code class="lang-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;&#13;&#10;&lt;configuration&gt;&#13;&#10;&lt;startup&gt;&#13;&#10;&lt;supportedRuntime version=&quot;v4.0&quot; sku=&quot;.NETFramework,Version=v4.7&quot;/&gt;&#13;&#10;&lt;/startup&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;!-- AppContextSwitchOverrides value attribute is in the form of &#39;key1=true/false;key2=true/false  --&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.UseLegacyAccessibilityFeatures=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre></br>Aplikacji przeznaczonych dla platformy .NET Framework 4.7.1 lub nowszym i chcesz zachować starszego zachowanie dostępności zgodzić się na korzystanie z funkcji ułatwień dostępu w starszej wersji, jawnie ustawiając tego przełącznika AppContext na <code>true</code>.<p/>Przegląd automatyzacji interfejsu użytkownika, zobacz [Przegląd automatyzacji interfejsu użytkownika](~/docs/framework/ui-automation/ui-automation-overview.md).&lt; /p/&gt;<p/><strong>Dodano obsługę dla właściwości i wzorce automatyzacji interfejsu użytkownika</strong><br/>Ułatwień dostępu klientów możliwość korzystania z nowych funkcji ułatwień dostępu WinForms za pomocą wspólnego, publicznie opis wywołania wzorców. Te wzorce nie są specyficzne dla WinForms. Na przykład ułatwień dostępu klientów można wywołać metody QueryInterface interfejsu IAccessible (MAAS) w celu uzyskania interfejsu IServiceProvider. Jeśli ten interfejs jest dostępny, klienci mogą używać własnej metody QueryService żądania interfejsu IAccessibleEx. Aby uzyskać więcej informacji, zobacz [przy użyciu IAccessibleEx w kliencie](https://msdn.microsoft.com/library/windows/desktop/dd561924.aspx). Począwszy od programu .NET Framework 4.7.1, IServiceProvider i [IAccessibleEx](https://msdn.microsoft.com/library/windows/desktop/dd561898.aspx) (jeśli dotyczy) są dostępne dla obiektów dostępności WinForms.<p/>.NET Framework 4.7.1 dodaje obsługę następujących wzorce automatyzacji interfejsu użytkownika i właściwości:<ul><li><xref:System.Windows.Forms.ToolStripSplitButton> i <xref:System.Windows.Forms.ComboBox> formanty obsługi [wzorzec Rozwiń/Zwiń](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</li><li><xref:System.Windows.Forms.ToolStripMenuItem> Formant ma [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) wartość właściwości <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.</li><li><xref:System.Windows.Forms.ToolStripItem> Sterowanie obsługuje <xref:System.Windows.Automation.AutomationElement.NameProperty> właściwości i[wzorzec Rozwiń/Zwiń](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</li><li><xref:System.Windows.Forms.ToolStripDropDownItem> Sterowanie obsługuje <xref:System.Windows.Forms.AccessibleEvents> wskazujący StateChange i NameChange, gdy lista rozwijana jest rozwinięte lub zwinięte.</li><li><xref:System.Windows.Forms.ToolStripDropDownButton> Formant ma [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) wartość właściwości <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.</li><li><xref:System.Windows.Forms.DataGridViewCheckBoxCell> Sterowanie obsługuje <xref:System.Windows.Automation.TogglePattern>.</li><li><xref:System.Windows.Forms.NumericUpDown> i <xref:System.Windows.Forms.DomainUpDown> formanty obsługi <xref:System.Windows.Automation.AutomationElement.NameProperty> właściwości i mieć [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-spinner-control-type.md) z <xref:System.Windows.Automation.ControlType.Spinner?displayProperty=nameWithType>.</p></li></ul><strong>Ulepszenia dotyczące kontroli PropertyGrid</strong></br>.NET Framework 4.7.1 dodano następujące ulepszenia do formantu PropertyBrowser:<ul><li><strong>Szczegóły</strong> przycisk w oknie dialogowym błędu, który jest wyświetlany, gdy użytkownik wprowadzi nieprawidłowe wartości w <xref:System.Windows.Forms.PropertyGrid> sterowanie obsługuje [wzorzec Rozwiń/Zwiń](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md), stan i zmiana nazwy powiadomienia, a [właściwość ControlType]~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) z wartością <xref:System.Windows.Automation.ControlType.MenuItem?displayProperty=nameWithType>.</li><li>Wyświetlane w okienku komunikat <strong>szczegóły</strong> rozwinięciu przycisku okna dialogowego błędu jest obecnie klawiatury dostępny i umożliwia Narrator zawiera informacje o zawartości komunikatu o błędzie.</li><li><xref:System.Windows.Forms.AccessibleRole> Wierszy w <xref:System.Windows.Forms.PropertyGrid> kontroli zostały zmienione od &quot;wiersza&quot; do &quot;komórki&quot;. Mapuje komórki ControlType funkcją UIA &quot;DataItem&quot;, umożliwi obsługuje odpowiednie skróty klawiaturowe i Narrator anonsów.</li><li><xref:System.Windows.Forms.PropertyGrid> Kontroli wiersze nagłówka reprezentuje elementy, jeśli <xref:System.Windows.Forms.PropertyGrid> formant ma <xref:System.Windows.Forms.PropertyGrid.PropertySort> ustawioną właściwość <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> ma [ControlType](~/docs/framework/ui-automation/ui-automation-support-for-the-menubar-control-type.md) wartość właściwości <xref:System.Windows.Automation.ControlType.Button?displayProperty=nameWithType>.</li><li><xref:System.Windows.Forms.PropertyGrid> Kontroli wiersze nagłówka reprezentuje elementy, jeśli <xref:System.Windows.Forms.PropertyGrid> formant ma <xref:System.Windows.Forms.PropertyGrid.PropertySort> ustawioną właściwość <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> obsługuje [wzorzec Rozwiń/Zwiń](~/docs/framework/ui-automation/implementing-the-ui-automation-expandcollapse-control-pattern.md).</li><li>Ulepszone klawiatury nawigacji między siatki i narzędzi nad nim. Naciśnięcie przycisku &quot;Shift — karta&quot; teraz wybiera pierwszy przycisku paska narzędzi, zamiast całego paska narzędzi.</li><li><xref:System.Windows.Forms.PropertyGrid> kontrolką w trybie dużego kontrastu będzie teraz Rysuj prostokąt fokusu wokół przycisku paska narzędzi, co odpowiada bieżącego <xref:System.Windows.Forms.PropertyGrid.PropertySort> wartości właściwości.</li><li><xref:System.Windows.Forms.PropertyGrid> Formanty wyświetlane w trybie dużego kontrastu z <xref:System.Windows.Forms.PropertyGrid.PropertySort> ustawioną właściwość <xref:System.Windows.Forms.PropertySort.Categorized?displayProperty=nameWithType> będą teraz wyświetlane tła nagłówków kategorii w dużej kontrastowy kolor.</li><li><xref:System.Windows.Forms.PropertyGrid> Formanty lepiej oddzieli elementów paska narzędzi z fokusem elementów paska narzędzi, które wskazują bieżącą wartość <xref:System.Windows.Forms.PropertyGrid.PropertySort> właściwości. Ta poprawka składa się z zmiany duży kontrast i zmiany w scenariuszach z systemem innym niż - dużego kontrastu.</li><li><xref:System.Windows.Forms.PropertyGrid> kontrolowanie elementów paska narzędzi, które wskazuje bieżącą wartość <xref:System.Windows.Forms.PropertyGrid.PropertySort> Obsługa właściwości <xref:System.Windows.Automation.TogglePattern>.</li><li>Ulepszona obsługa Narrator rozróżniania wybranego wyrównania w selektorze wyrównania.</li><li>Gdy pustą <xref:System.Windows.Forms.PropertyGrid> formant jest wyświetlany na formularzu, otrzyma teraz fokus, gdy wcześniej w ten sposób nie.</p></li></ul><strong>Użyj kolorów systemu operacyjnego w kompozycji duży kontrast</strong></br><ul><li><xref:System.Windows.Forms.Button> i <xref:System.Windows.Forms.CheckBox> formanty z ich <xref:System.Windows.Forms.ButtonBase.FlatStyle> ustawioną właściwość <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>, który jest domyślnym stylu, teraz Użyj kolorów systemu operacyjnego w kompozycję Duży kontrast, gdy wybrana. Wcześniej kolory tła i tekstu nie zostały kontrastem i był trudny do odczytania.</li><li><xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton>, <xref:System.Windows.Forms.Label>, <xref:System.Windows.Forms.LinkLabel> i <xref:System.Windows.Forms.GroupBox> formanty z ich <xref:System.Windows.Forms.Control.Enabled> ustawioną właściwość <strong>false</strong> używany kolor przyciemnione do renderowania tekstu w duży kontrast kompozycje, co w niskim kontraście na tle. Teraz używać tych kontrolek &quot;wyłączonego tekstu&quot; kolor zdefiniowany przez system operacyjny. Ta poprawka jest przeznaczona do formantów z ich <code>FlatStyle</code> właściwość o wartości innej niż <xref:System.Windows.Forms.FlatStyle.System?displayProperty=nameWithType>. Ostatnie formanty są renderowane przez system operacyjny.</li><li><xref:System.Windows.Forms.DataGridView> renderuje teraz widoczne prostokątem zawartość komórki, który ma aktualnie fokus. Wcześniej to nie było widoczne w niektórych motywów dużego kontrastu.</li><li><xref:System.Windows.Forms.ToolStripMenuItem> Formanty z ich <xref:System.Windows.Forms.ToolStripMenuItem.Enabled> ustawioną właściwość <strong>false</strong> teraz używać &quot;wyłączonego tekstu&quot; kolor zdefiniowany przez system operacyjny.</li><li><xref:System.Windows.Forms.ToolStripMenuItem> Formanty z ich <xref:System.Windows.Forms.ToolStripMenuItem.Checked> ustawioną właściwość <strong>true</strong> teraz renderowania skojarzone znacznik wyboru w kolorze kontrastowym systemu.  Wcześniej kolor znacznika wyboru został nie kontrastem wystarczająco i nie są widoczne w duży kontrast motywów.</li></ul>Uwaga: System Windows 10 zmienił wartości dla niektórych duży kontrast kolorów systemu. Struktura formularzy systemu Windows jest oparta na strukturze Win32. Aby uzyskać najlepsze wyniki należy uruchomić na najnowszej wersji systemu Windows i zdecydować się na najnowsze zmiany systemu operacyjnego przez dodanie pliku app.manifest w aplikacji testu i usunięcie komentarza z następującego kodu:<pre><code class="lang-xml">&lt;!-- Windows 10 --&gt;&#13;&#10;&lt;supportedOS Id=&quot;{8e0f7a12-bfb3-4fe8-b9a5-48fd50a15a9a}&quot; /&gt;&#13;&#10;</code></pre></br><strong>Ulepszone klawiatury nawigacji</strong><ul><li>Gdy <xref:System.Windows.Forms.ComboBox> formant ma jego <xref:System.Windows.Forms.ComboBox.DropDownStyle> ustawioną właściwość <xref:System.Windows.Forms.ComboBoxStyle.DropDownList?displayProperty=nameWithType> i jest pierwszą kontrolkę w karcie kolejność na formularzu, teraz program wyświetla prostokąt fokusu po otwarciu formularza nadrzędnego, za pomocą klawiatury. Przed wprowadzeniem tej zmiany fokus klawiatury dla tego formantu, ale było wskaźnik fokus nie był renderowany.</li></ul><strong>Ulepszona obsługa Narrator</strong><ul><li><xref:System.Windows.Forms.MonthCalendar> Formant został dodany obsługę technologie pomocnicze do kontroli dostępu, łącznie z możliwością Narrator można odczytać wartości formantu, gdy wcześniej może nie.</li><li><xref:System.Windows.Forms.CheckedListBox> Kontroli teraz powiadamia program Narrator przy <xref:System.Windows.Forms.CheckBox.CheckState?displayProperty=nameWithType> zmieniono właściwość. Poprzednio Narrator nie otrzymał powiadomienie i w związku z tym użytkownicy nie będą informowane, który <xref:System.Windows.Forms.CheckBox.CheckState> Zaktualizowano właściwości.</li><li><xref:System.Windows.Forms.LinkLabel> Kontroli zmieniono sposób powiadomi Narrator tekst w formancie. Wcześniej, Narrator ogłosiła dwa razy ten tekst i odczytu &quot; &amp; &quot; symboli jako tekst prawdziwe, nawet jeśli nie są widoczne dla użytkownika. Zduplikowany tekst został usunięty z anonsów Narrator, a także niepotrzebnych &quot; &amp; &quot; symboli.</li><li><xref:System.Windows.Forms.DataGridViewCell> Kontroli teraz typy poprawnie raportu stanu tylko do odczytu do Narrator i innych technologii pomocniczych.</li><li>Narrator może teraz odczytać Menu systemowego okno podrzędne w [Interface]~/docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md wielu dokumentów) aplikacji.</li><li>Narrator może teraz odczytać <xref:System.Windows.Forms.ToolStripMenuItem> formanty z <xref:System.Windows.Forms.ToolStripItem.Enabled?displayProperty=nameWithType> ustawioną właściwość <strong>false</strong>. Wcześniej Narrator nie skoncentrowane na elementach menu wyłączone do odczytu zawartości.</li></ul>|
|Zakres|Główne|
|Wersja|4.7.1|
|Typ|Przekierowania|
|Dotyczy interfejsów API|<ul><li><xref:System.Windows.Forms.ToolStripDropDownButton.CreateAccessibilityInstance?displayProperty=nameWithType></li><li><xref:System.Windows.Forms.DomainUpDown.DomainUpDownAccessibleObject.Name?displayProperty=nameWithType></li><li>[MonthCalendar.AccessibilityObject](xref:System.Windows.Forms.Control.AccessibilityObject)</li></ul>|
