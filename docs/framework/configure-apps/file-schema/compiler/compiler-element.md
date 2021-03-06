---
title: <compiler>, element
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 34753d538ff37ac4ae621f653d47ac92ac6749a0
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674467"
---
# <a name="compiler-element"></a>\<compiler> Element

Określa atrybuty kompilatora konfiguracji dostawcy języka.

\<Konfiguracja elementu > \<system.CodeDom — Element > \<kompilatory Element > \<kompilatora > Element

## <a name="syntax"></a>Składnia

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a>Atrybuty i elementy

W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.

### <a name="attributes"></a>Atrybuty

|Atrybut|Opis|
|---------------|-----------------|
|`compilerOptions`|Atrybut opcjonalny.<br /><br /> Określa dodatkowe argumenty kompilatora specyficzne dla kompilacji. Wartości `compilerOptions` atrybut zwykle są wymienione w temacie opcje kompilatora dla kompilatora.|
|`extension`|Atrybut wymagany.<br /><br /> Zawiera rozdzieloną średnikami listę rozszerzeń nazw plików używane przez pliki źródłowe dla dostawcy języka. Na przykład ".cs".|
|`language`|Atrybut wymagany.<br /><br /> Zawiera rozdzieloną średnikami listę nazw języków obsługiwanych przez dostawcę języka. Na przykład "c#; cs; csharp".|
|`type`|Atrybut wymagany.<br /><br /> Określa nazwę typu dostawcy języka, łącznie z nazwą zestawu zawierającego implementację dostawcy. Nazwa typu musi spełniać wymagania zdefiniowane w [określanie w pełni kwalifikowanej nazwy typu](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Atrybut opcjonalny.<br /><br /> Określa domyślny poziom ostrzeżeń kompilatora; Określa poziom, który dostawca języka traktuje jako błędy ostrzeżenia kompilacji.|

### <a name="child-elements"></a>Elementy podrzędne

|Element|Opis|
|-------------|-----------------|
|[\<providerOption> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Określa atrybuty wersji kompilatora dla dostawcy języka.|

### <a name="parent-elements"></a>Elementy nadrzędne

|Element|Opis|
|-------------|-----------------|
|[\<Konfiguracja > Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|
|[\<system.codedom> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Określa ustawienia konfiguracyjne kompilatora dla dostępnych dostawców języka.|
|[\<compilers> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Kontener dla elementów konfiguracji, kompilator; zawiera zero lub więcej `<compiler>` elementów.|

## <a name="remarks"></a>Uwagi

Każdy `<compiler>` element określa atrybuty kompilatora konfiguracji dla dostawcy określonego języka. Dostawca rozszerza <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> klasy dla określonego języka; `<compiler>` element definiuje kompilatora i ustawienia generator kodu dla dostawcy języka.

.NET Framework definiuje ustawienia kompilatora początkowe w pliku konfiguracji komputera (Machine.config). Deweloperom i dostawcom kompilatora umożliwia dodanie ustawienia konfiguracji dla nowego <xref:System.CodeDom.Compiler.CodeDomProvider> implementacji. Użyj <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> metody, można programowo wyliczyć języka ustawienia konfiguracji dostawcy i kompilator na komputerze.

Elementy kompilatora w pliku konfiguracji sieci Web lub aplikacji można uzupełnić lub przesłonić ustawienia w pliku konfiguracji komputera. Jeśli więcej niż jedna implementacja dostawcy jest skonfigurowany dla tej samej nazwy języka lub to samo rozszerzenie pliku, ostatniej pasującej konfiguracji zastępuje wszystkie poprzednie dostawców skonfigurowanych dla tego rozszerzenia nazwy lub plik języka.

## <a name="configuration-file"></a>Plik konfiguracji

Ten element może być użyty w pliku konfiguracji komputera i pliku konfiguracji aplikacji.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano element kompilatora typowej konfiguracji:

```xml
<configuration>
  <system.codedom>
    <compilers>
      <!-- zero or more compiler elements -->
      <compiler
        language="c#;cs;csharp"
        extension=".cs"
        type="Microsoft.CSharp.CSharpCodeProvider, System,
          Version=2.0.3600.0, Culture=neutral,
          PublicKeyToken=b77a5c561934e089"
        compilerOptions="/optimize"
        warningLevel="1" />
    </compilers>
  </system.codedom>
</configuration>
```

## <a name="see-also"></a>Zobacz także

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Schemat pliku konfiguracji](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [\<compilers> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [Określanie w pełni kwalifikowanych nazw typów](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Kompilator Element kompilatorów dla kompilacji (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
