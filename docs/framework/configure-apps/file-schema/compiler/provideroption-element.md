---
title: <providerOption>, element
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: bb29ba8721c3aa13fad4410208b1276bdfa761c1
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675273"
---
# <a name="provideroption-element"></a>\<providerOption> Element
Określa atrybuty wersji kompilatora dla dostawcy języka.  
  
 \<Konfiguracja elementu >  
\<system.codedom Element>  
\<kompilatory Element >  
\<compiler> Element  
\<providerOption> Element  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`name`|Atrybut wymagany.<br /><br /> Określa nazwę opcji; na przykład "CompilerVersion".|  
|`value`|Atrybut wymagany.<br /><br /> Określa wartość dla opcji; na przykład "3.5".|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Konfiguracja > Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Element główny w każdym pliku konfiguracji, który jest używany przez środowisko uruchomieniowe języka wspólnego i aplikacji programu .NET Framework.|  
|[\<system.codedom> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Określa ustawienia konfiguracyjne kompilatora dla dostępnych dostawców języka.|  
|[\<compilers> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Kontener dla elementów konfiguracji, kompilator; zawiera zero lub więcej `<compiler>` elementów.|  
|[\<compiler> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Określa atrybuty kompilatora konfiguracji dostawcy języka.|  
  
## <a name="remarks"></a>Uwagi  
 W .NET Framework w wersji 3.5, dostawców kodu kodu Document Object Model (CodeDOM) może obsługiwać opcji specyficznych dla dostawcy przy użyciu `<providerOption>` elementu.  
  
 .NET Framework 3.5 zawiera zaktualizowane zestawy .NET Framework 2.0, a także nowych zestawów w wersji 3.5, które zawierają nowe typy. Dostawców kodu w języku Microsoft C# i Visual Basic są zawarte w zestawach .NET Framework 2.0, ale został zaktualizowany do obsługi kompilatory w wersji 3.5. Domyślnie dostawców zaktualizowany kod wygenerować kod dla kompilatory w wersji 2.0. Możesz użyć `<providerOption>` element, aby zmienić docelową wersję kompilatora 3.5. Aby to zrobić, należy określić "CompilerVersion" `name` atrybut i "3.5" na `value` atrybutu. Należy poprzedzić liczbę wersji, stosując małe "v".  
  
 Możesz wprowadzić Specyfikacja wersji globalnej, dodawanie `<providerOption>` elementu do .NET Framework w wersji 2.0 w pliku Machine.config lub głównego pliku Web.config. Jeśli zaktualizujesz domyślną wersję kompilatora 3.5 w pliku Machine.config można zmienić go do wersji 2.0, na podstawie poszczególnych aplikacji za pomocą `<providerOption>` elementu w pliku konfiguracyjnym aplikacji.  
  
 Implementacje dostawcy kodu codeDOM może przetworzyć niestandardowych opcji, zapewniając konstruktora przyjmującego `providerOptions` parametr typu <xref:System.Collections.Generic.IDictionary%602>.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak określić, należy używać tej wersji 3.5 dostawcy kodu C#.  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
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
