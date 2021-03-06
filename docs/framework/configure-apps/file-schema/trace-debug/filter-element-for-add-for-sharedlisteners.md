---
title: <filter> — Element do <add> dla <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 739acedcc83cd207a7ef4c10c220d27695dd713d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269305"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<Filtr >, Element dla \<Dodaj > dla \<sharedListeners >
Dodaje filtr do odbiornika w `sharedListeners` kolekcji.  
  
 \<Konfiguracja >  
\<system.diagnostics>  
\<sharedListeners > Element  
\<add>  
\<Filtr >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|**type**|Atrybut wymagany.<br /><br /> Określa typ filtru. Można użyć tylko pełną nazwę tego typu (w formacie <xref:System.Type.FullName%2A?displayProperty=nameWithType> właściwości), lub można użyć w pełni kwalifikowana nazwa typu w tym informacje o zestawie (w formacie <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> właściwości). Aby uzyskać informacje dotyczące tworzenia w pełni kwalifikowaną nazwę typu, zobacz [określanie w pełni kwalifikowanej nazwy typu](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Atrybut opcjonalny.<br /><br /> Ciąg przekazany do konstruktora dla określonej klasy.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`system.diagnostics`|Określa obiektów nasłuchujących śledzenia zbierać, przechowywać i kierowanie komunikatów i poziom, którego ustawiono przełącznikiem śledzenia.|  
|`sharedListeners`|Kolekcja obiektów nasłuchujących dowolnego źródła i elementu śledzenia można odwoływać się do.|  
|`add`|Dodaje odbiornik do **sharedListeners** kolekcji.|  
  
## <a name="remarks"></a>Uwagi  
 Jeśli odbiornik jest zdefiniowany w `<add>` elementu `<sharedListeners>` elementu filtru dla tego odbiornika powinien być zdefiniowany w `<filter>` element, który jest elementem podrzędnym `<add>` elementu.  
  
 Ten element może być użyty w pliku konfiguracji komputera (Machine.config) i pliku konfiguracji aplikacji.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak używać `<filter>` elementu Dodawanie filtru do odbiornika śledzenia `console` w `sharedListeners` kolekcji.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [Schemat ustawień śledzenia i debugowania](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
