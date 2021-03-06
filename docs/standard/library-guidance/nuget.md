---
title: Biblioteki NuGet i platformy .NET
description: Zalecane najlepsze dla pakietu nuget biblioteki .NET.
author: jamesnk
ms.author: mairaw
ms.date: 01/15/2019
ms.openlocfilehash: a721c642dd92eb299eef3b62fc845afa99f81ddc
ms.sourcegitcommit: e39d93d358974b9ed4541cedf4e25c0101015c3c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "55204616"
---
# <a name="nuget"></a>NuGet

NuGet to Menedżer pakietów dla ekosystemu .NET i deweloperów podstawowym sposobem odnajdywanie i nabyć bibliotek typu open source platformy .NET. [NuGet.org](https://www.nuget.org/), bezpłatna usługa udostępniana przez firmę Microsoft do obsługi pakietów NuGet jest hostem głównym publicznych pakietów NuGet, ale możesz opublikować niestandardowych usług NuGet, takich jak [MyGet](https://www.myget.org/) i [artefaktów platformy Azure ](https://azure.microsoft.com/services/devops/artifacts/).

![NuGet](./media/nuget/nuget-logo.png "NuGet")

## <a name="create-a-nuget-package"></a>Utwórz pakiet NuGet

Pakiet NuGet (`*.nupkg`) jest plikiem zip, zawierający zestawy .NET oraz skojarzone metadane.

Istnieją dwa główne sposoby, aby utworzyć pakiet NuGet. Sposobem nowszej i zalecane jest utworzenie pakietu z projektu zestawu SDK stylu (plik projektu, którego zawartość rozpoczyna się od `<Project Sdk="Microsoft.NET.Sdk">`). Zespoły i elementy docelowe są automatycznie dodawane do pakietu, a pozostałe metadanych jest dodawany do pliku programu MSBuild, takich jak numer nazwą i wersją pakietu. Kompilowanie przy użyciu [ `dotnet pack` ](../../core/tools/dotnet-pack.md) dane wyjściowe polecenia `*.nupkg` pliku zamiast zestawów.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

Starszy sposób tworzenia pakietu NuGet jest `*.nuspec` pliku i `nuget.exe` narzędzie wiersza polecenia. Soubor nuspec zapewnia dużą kontrolę, ale należy określić dokładnie do końcowego pakietu NuGet, jakie zestawy i elementy docelowe. Łatwo popełnienia błędu lub niepowołanym zapomnij zaktualizować nuspec podczas wprowadzania zmian. Ma tę zaletę nuspec umożliwia tworzenie pakietów NuGet, struktur, które nie obsługują pliku projektu zestawu SDK stylu.

**ROZWAŻ ✔️** przy użyciu zestawu SDK stylu pliku projektu do utworzenia pakietu NuGet.

## <a name="package-dependencies"></a>Zależności pakietów

Zależności pakietów NuGet są tu szczegółowo [zależności](./dependencies.md) artykułu.

## <a name="important-nuget-package-metadata"></a>Ważne metadane pakietu NuGet

Pakiet NuGet obsługuje wiele [właściwości metadanych](/nuget/reference/nuspec). Poniższa tabela zawiera metadane podstawowe, zapewniające każdego pakietu w witrynie NuGet.org:

| Nazwa właściwości programu MSBuild              | Nazwa Nuspec              | Opis  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | Identyfikator pakietu. Jeśli dana jednostka spełnia można zarezerwować prefiksu z identyfikatorem [kryteria](/nuget/reference/id-prefix-reservation). |
| `PackageVersion`                   | `version`                  | Wersja pakietu NuGet. Aby uzyskać więcej informacji, zobacz [pakietu NuGet w wersji](./versioning.md#nuget-package-version).             |
| `Title`                            | `title`                    | Przyjazne dla człowieka tytuł pakietu. Jego wartość domyślna to `PackageId`.             |
| `Description`                      | `description`              | Długi opis pakietu, wyświetlana w interfejsie użytkownika.             |
| `Authors`                          | `authors`                  | Rozdzielana przecinkami lista autorów pakietów, pasujące nazwy profilu w witrynie nuget.org.             |
| `PackageTags`                      | `tags`                     | Rozdzielany spacjami lista tagów i słów kluczowych, które opisują pakietu. Znaczniki są używane podczas wyszukiwania dla pakietów.             |
| `PackageIconUrl`                   | `iconUrl`                  | Adres URL obrazu do użycia jako ikona dla pakietu. Adres URL powinien być schemat HTTPS i obraz, który powinien być 64 x 64 i mieć przezroczyste tło.             |
| `PackageProjectUrl`                | `projectUrl`               | Adres URL strony głównej lub źródło repozytorium projektu.             |
| `PackageLicenseExpression`         | `license`                  | Licencja projektu [identyfikator SPDX](https://spdx.org/licenses/). Tylko do OSI i FSF zatwierdzone licencji można użyć identyfikatora. Należy używać innych licencji `PackageLicenseFile`. Przeczytaj więcej na temat [ `license` metadanych](/nuget/reference/nuspec#license). |

> [!IMPORTANT]
> Projekt bez licencji, wartość domyślna to [wyłącznych praw autorskich](https://choosealicense.com/no-permission/), uniemożliwiając prawnie przez inne osoby do użycia.

**ROZWAŻ ✔️** Wybieranie nazwy pakietów NuGet z prefiksem, który spełnia rezerwowanie prefiksów identyfikatorów NuGet [kryteria](/nuget/reference/id-prefix-reservation).

**CZY ✔️** Użyj href HTTPS, aby ikona pakietu.

> Witryn, takich jak NuGet.org Uruchom przy użyciu protokołu HTTPS jest włączone, a następnie wyświetlanie obrazu innych niż HTTPS utworzy ostrzeżenie zawartości mieszanej.

**CZY ✔️** za pomocą pakietu obrazu ikony, 64 x 64 z przezroczystym tłem, aby uzyskać najlepszy wygląd.

**ROZWAŻ ✔️** Konfigurowanie [Linku źródłowego](./sourcelink.md) do dodawania metadanych do kontroli źródła do zestawów i pakietów NuGet.

> Link źródłowy automatycznie dodaje `RepositoryUrl` i `RepositoryType` metadanych do pakietu NuGet. Link źródłowy dodaje także informacje o kodzie źródłowym dokładnie pakiet został zbudowany z. Na przykład pakiet utworzony na podstawie repozytorium Git będzie mieć skrót zatwierdzenia dodać jako metadane.

## <a name="pre-release-packages"></a>Pakiety w wersji wstępnej

Pakiety NuGet za pomocą sufiksu wersji są traktowane jako [wersji wstępnej](/nuget/create-packages/prerelease-packages). Domyślnie interfejs użytkownika Menedżera pakietów NuGet zawiera stabilnej wersji, chyba że użytkownik zdecyduje się na do wersji wstępnej pakietów, dzięki czemu pakiety w wersji wstępnej niezwykle przydatna przy testowaniu użytkownika z ograniczonymi.

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> Stabilny pakiet nie mogą być zależne od pakietu wersji wstępnej. Możesz utworzyć własny pakiet wersji wstępnej lub są zależne od starsze stabilnej wersji.

![Zależność wersji wstępnej pakietu NuGet](./media/nuget/nuget-prerelease-package.png "zależność wersji wstępnej pakietu NuGet")

**CZY ✔️** publikowanie pakietu wersji wstępnej podczas testowania, Podgląd lub eksperymentowania.

**CZY ✔️** publikowania stabilny pakiet, gdy jego gotowe więc inne stabilne pakiety można odwoływać się do niego.

## <a name="symbol-packages"></a>Pakiety symboli

Pliki symboli (`*.pdb`) są produkowane przez kompilator platformy .NET, wraz z zestawów. Lokalizacje wykonywania mapy plików symboli do oryginalnego kodu źródłowego, dzięki czemu możesz przejrzeć kod źródłowy w postaci, w jakiej jest uruchomiona, przy użyciu debugera. Obsługuje NuGet [generowania pakietu oddzielne symbol (`*.snupkg`)](/nuget/create-packages/symbol-packages-snupkg) zawierający pliki symboli, wraz z pakietu głównego zawierającego zestawy .NET. Koncepcja pakiety symboli jest one hostowane na serwerze symboli i są pobierane tylko wtedy, narzędzia, takiego jak Visual Studio na żądanie.

NuGet.org znajduje się własną [repozytorium serwera symboli](/nuget/create-packages/symbol-packages-snupkg#nugetorg-symbol-server). Deweloperzy mogą używać symbole opublikowane na serwerze symboli NuGet.org, dodając `https://symbols.nuget.org/download/symbols` do ich [symboli źródła w programie Visual Studio](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).

> [!IMPORTANT]
> Serwer symboli NuGet.org obsługuje tylko nowe [pliki symboli przenośne](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) utworzone przez projektów w stylu zestawu SDK.
>
> Aby użyć serwera symboli NuGet.org, podczas debugowania biblioteki .NET, deweloperzy musi mieć program Visual Studio 2017 15.9 lub nowszej.

Alternatywą dla tworzenia pakietu symboli jest osadzanie plików symboli w głównym pakietu NuGet. Głównym pakietu NuGet jest większy, ale osadzone symboli plików oznacza, że deweloperzy nie muszą skonfigurować serwer symboli NuGet.org. Jeśli tworzysz pakiet NuGet za pomocą zestawu SDK stylu projektu, a następnie umożliwia osadzanie plików symboli, ustawiając `AllowedOutputExtensionsInPackageBuildOutputFolder` właściwości:

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

Wadą osadzanie plików symboli jest, mogą zwiększyć rozmiar pakietu o około 30% do bibliotek .NET skompilowanych przy użyciu zestawu SDK stylu projektów. Jeśli rozmiar pakietu jest istotna, należy zamiast tego opublikować symbole w pakietach symboli.

**ROZWAŻ ✔️** publikowania symboli jako pakiet symboli (`*.snupkg`) na stronie NuGet.org

> Pakiety symboli (`*.snupkg`) zapewnia deweloperom dobre środowisko debugowania na żądanie pozwoli uniknąć przeładowania rozmiar pakietu głównego i wpływu na przywracania wydajność dla tych, którzy nie zamierzasz debugowanie pakietu NuGet.
>
> Zastrzeżenie: to ich potrzebować do znalezienia i skonfigurować serwer symboli NuGet w ich środowisku IDE (jako to jednorazowa Konfiguracja), można pobrać pliki symboli. Visual Studio 2019 r planuje dostarcza do serwera symboli NuGet.org jako jedną z opcji gotowe. 


>[!div class="step-by-step"]
>[Poprzednie](strong-naming.md)
>[dalej](dependencies.md)
