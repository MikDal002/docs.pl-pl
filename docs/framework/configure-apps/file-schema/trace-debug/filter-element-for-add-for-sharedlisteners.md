---
title: "&lt;Filtr&gt; elementu &lt;dodać&gt; dla &lt;sharedListeners&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ce4134d9059d1f1d5bd2e435a3cc87d3fbccd422
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a><span data-ttu-id="70835-102">&lt;Filtr&gt; elementu &lt;dodać&gt; dla &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="70835-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="70835-103">Dodaje filtr do odbiornika w `sharedListeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="70835-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="70835-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="70835-104">\<configuration></span></span>  
<span data-ttu-id="70835-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="70835-105">\<system.diagnostics></span></span>  
<span data-ttu-id="70835-106">\<sharedListeners > — Element</span><span class="sxs-lookup"><span data-stu-id="70835-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="70835-107">\<Dodaj ></span><span class="sxs-lookup"><span data-stu-id="70835-107">\<add></span></span>  
<span data-ttu-id="70835-108">\<Filtr ></span><span class="sxs-lookup"><span data-stu-id="70835-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70835-109">Składnia</span><span class="sxs-lookup"><span data-stu-id="70835-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="70835-110">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="70835-110">Attributes and Elements</span></span>  
 <span data-ttu-id="70835-111">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="70835-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70835-112">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="70835-112">Attributes</span></span>  
  
|<span data-ttu-id="70835-113">Atrybut</span><span class="sxs-lookup"><span data-stu-id="70835-113">Attribute</span></span>|<span data-ttu-id="70835-114">Opis</span><span class="sxs-lookup"><span data-stu-id="70835-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="70835-115">**Typ**</span><span class="sxs-lookup"><span data-stu-id="70835-115">**type**</span></span>|<span data-ttu-id="70835-116">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="70835-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="70835-117">Określa typ filtru.</span><span class="sxs-lookup"><span data-stu-id="70835-117">Specifies the type of the filter.</span></span> <span data-ttu-id="70835-118">Można użyć tylko pełną nazwę typu (w formacie <xref:System.Type.FullName%2A?displayProperty=nameWithType> właściwości), lub w pełni kwalifikowana nazwa typu w tym informacje o zestawie można użyć (w formacie <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> właściwości).</span><span class="sxs-lookup"><span data-stu-id="70835-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="70835-119">Aby uzyskać informacje na temat tworzenia w pełni kwalifikowana nazwa typu, zobacz [określenie pełni kwalifikowane nazwy typów](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="70835-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="70835-120">**initializeData —**</span><span class="sxs-lookup"><span data-stu-id="70835-120">**initializeData**</span></span>|<span data-ttu-id="70835-121">Atrybut opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="70835-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="70835-122">Ciąg przekazany do konstruktora dla określonej klasy.</span><span class="sxs-lookup"><span data-stu-id="70835-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="70835-123">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="70835-123">Child Elements</span></span>  
 <span data-ttu-id="70835-124">Brak.</span><span class="sxs-lookup"><span data-stu-id="70835-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="70835-125">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="70835-125">Parent Elements</span></span>  
  
|<span data-ttu-id="70835-126">Element</span><span class="sxs-lookup"><span data-stu-id="70835-126">Element</span></span>|<span data-ttu-id="70835-127">Opis</span><span class="sxs-lookup"><span data-stu-id="70835-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="70835-128">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="70835-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="70835-129">Określa obiektów nasłuchujących śledzenia zbierania, przechowywania i kierowania wiadomości i poziom, gdy jest ustawiona przełącznik śledzenia.</span><span class="sxs-lookup"><span data-stu-id="70835-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="70835-130">Kolekcja obiektów nasłuchujących może odwoływać się wszystkie źródła lub element śledzenia.</span><span class="sxs-lookup"><span data-stu-id="70835-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="70835-131">Dodaje odbiornika do **sharedListeners** kolekcji.</span><span class="sxs-lookup"><span data-stu-id="70835-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70835-132">Uwagi</span><span class="sxs-lookup"><span data-stu-id="70835-132">Remarks</span></span>  
 <span data-ttu-id="70835-133">Jeśli odbiornik jest zdefiniowany w `<add>` elementu `<sharedListeners>` element powinien być zdefiniowany filtr dla tego odbiornika w `<filter>` element, który jest elementem podrzędnym `<add>` elementu.</span><span class="sxs-lookup"><span data-stu-id="70835-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="70835-134">Ten element może być użyty w pliku konfiguracji komputera (Machine.config) i pliku konfiguracji aplikacji.</span><span class="sxs-lookup"><span data-stu-id="70835-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70835-135">Przykład</span><span class="sxs-lookup"><span data-stu-id="70835-135">Example</span></span>  
 <span data-ttu-id="70835-136">Poniższy przykład przedstawia użycie `<filter>` element, aby dodać filtr do obiektu nasłuchującego śledzenia `console` w `sharedListeners` kolekcji.</span><span class="sxs-lookup"><span data-stu-id="70835-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="70835-137">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="70835-137">See Also</span></span>  
 <xref:System.Diagnostics.TraceFilter>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="70835-138">Schemat ustawień debugowania i śledzenia</span><span class="sxs-lookup"><span data-stu-id="70835-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)