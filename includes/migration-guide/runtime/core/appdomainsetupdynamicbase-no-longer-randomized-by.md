### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase już jest wybierane przez userandomizedstringhashalgorithm —

|   |   |
|---|---|
|Szczegóły|Przed programu .NET Framework 4.6, wartość <xref:System.AppDomainSetup.DynamicBase> mogłoby być wybierane między domenami aplikacji lub procesów, jeśli userandomizedstringhashalgorithm — zostało włączone w pliku konfiguracyjnym aplikacji. Począwszy od programu .NET Framework 4.6 <xref:System.AppDomainSetup.DynamicBase> zwróci on wynik stabilny, między różnymi wystąpieniami uruchamiania aplikacji oraz pomiędzy domenami, innej aplikacji. Dynamiczne podstaw nadal będą się różnić dla różnych aplikacji; Ta zmiana powoduje usunięcie tylko element losowy nazewnictwa, który dotyczy to różnych wystąpień tej samej aplikacji.|
|Sugestia|Należy pamiętać, że włączenie <code>UseRandomizedStringHashAlgorithm</code> nie spowoduje poniesienia <xref:System.AppDomainSetup.DynamicBase> są wybierane. W razie potrzeby losowe podstawowy musi utworzone w kodzie aplikacji, a nie za pośrednictwem tego interfejsu API.|
|Zakres|Krawędź|
|Wersja|4.6|
|Typ|Środowisko uruchomieniowe|
|Dotyczy interfejsów API|<ul><li><xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|

