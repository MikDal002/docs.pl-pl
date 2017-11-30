---
title: "&lt;gcserver —&gt; — Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 54142a75d178eb1c12e4b182df1dab9bff957ec6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltgcservergt-element"></a><span data-ttu-id="5ad8e-102">&lt;gcserver —&gt; — Element</span><span class="sxs-lookup"><span data-stu-id="5ad8e-102">&lt;gcServer&gt; Element</span></span>
<span data-ttu-id="5ad8e-103">Określa, czy środowisko uruchomieniowe języka wspólnego Uruchamia odzyskiwanie pamięci na serwerze.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-103">Specifies whether the common language runtime runs server garbage collection.</span></span>  
  
 <span data-ttu-id="5ad8e-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="5ad8e-104">\<configuration></span></span>  
<span data-ttu-id="5ad8e-105">\<Runtime ></span><span class="sxs-lookup"><span data-stu-id="5ad8e-105">\<runtime></span></span>  
<span data-ttu-id="5ad8e-106">\<gcserver — ></span><span class="sxs-lookup"><span data-stu-id="5ad8e-106">\<gcServer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad8e-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="5ad8e-107">Syntax</span></span>  
  
```xml  
<gcServer    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ad8e-108">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="5ad8e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5ad8e-109">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ad8e-110">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="5ad8e-110">Attributes</span></span>  
  
|<span data-ttu-id="5ad8e-111">Atrybut</span><span class="sxs-lookup"><span data-stu-id="5ad8e-111">Attribute</span></span>|<span data-ttu-id="5ad8e-112">Opis</span><span class="sxs-lookup"><span data-stu-id="5ad8e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5ad8e-113">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5ad8e-114">Określa, czy środowisko uruchomieniowe Uruchamia odzyskiwanie pamięci na serwerze.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-114">Specifies whether the runtime runs server garbage collection.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5ad8e-115">Atrybut włączony</span><span class="sxs-lookup"><span data-stu-id="5ad8e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5ad8e-116">Wartość</span><span class="sxs-lookup"><span data-stu-id="5ad8e-116">Value</span></span>|<span data-ttu-id="5ad8e-117">Opis</span><span class="sxs-lookup"><span data-stu-id="5ad8e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5ad8e-118">Odzyskiwanie pamięci na serwerze nie jest możliwe.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-118">Does not run server garbage collection.</span></span> <span data-ttu-id="5ad8e-119">Domyślnie włączone.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5ad8e-120">Uruchamia odzyskiwanie pamięci na serwerze.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-120">Runs server garbage collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ad8e-121">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="5ad8e-121">Child Elements</span></span>  
 <span data-ttu-id="5ad8e-122">Brak.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ad8e-123">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="5ad8e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5ad8e-124">Element</span><span class="sxs-lookup"><span data-stu-id="5ad8e-124">Element</span></span>|<span data-ttu-id="5ad8e-125">Opis</span><span class="sxs-lookup"><span data-stu-id="5ad8e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5ad8e-126">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5ad8e-127">Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ad8e-128">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5ad8e-128">Remarks</span></span>  
 <span data-ttu-id="5ad8e-129">Środowisko uruchomieniowe języka wspólnego (CLR) obsługuje dwa typy operacji wyrzucania elementów bezużytecznych: wyrzucanie elementów bezużytecznych stacji roboczej, która jest dostępna we wszystkich systemach, i odzyskiwanie pamięci na serwerze, który jest dostępny w systemach wieloprocesorowych.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="5ad8e-130">Możesz użyć `<gcServer>` wykonuje element, aby kontrolować typ operacji wyrzucania elementów bezużytecznych środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-130">You use the `<gcServer>` element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="5ad8e-131">Użyj <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> właściwości w celu określenia, czy jest włączone odzyskiwanie pamięci na serwerze.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>  
  
 <span data-ttu-id="5ad8e-132">W przypadku komputerów z jednym procesorem domyślnej kolekcji elementy bezużyteczne stacji roboczej powinna być najszybszą opcję.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="5ad8e-133">Dla dwóch komputerów można stacji roboczej lub serwera.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="5ad8e-134">Odzyskiwanie pamięci na serwerze powinny być najszybszą opcję dla więcej niż dwa procesory.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-134">Server garbage collection should be the fastest option for more than two processors.</span></span>  
  
 <span data-ttu-id="5ad8e-135">Ten element może być używana tylko w pliku konfiguracji aplikacji; jest ona ignorowana, jeśli znajduje się w pliku konfiguracji komputera.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-135">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ad8e-136">W .NET Framework 4 i starszych wersjach współbieżne odzyskiwanie pamięci nie jest dostępna, gdy jest włączone odzyskiwanie pamięci na serwerze.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-136">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="5ad8e-137">Począwszy od [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], jest współbieżne odzyskiwanie pamięci na serwerze.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-137">Starting with the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], server garbage collection is concurrent.</span></span> <span data-ttu-id="5ad8e-138">Aby użyć serwera z systemem innym niż współbieżne odzyskiwanie pamięci, należy ustawić `<gcServer>` elementu `true` i [ \<gcconcurrent — > element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) do `false`.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-138">To use non-concurrent server garbage collection, set the `<gcServer>` element to `true` and the [\<gcConcurrent> element](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ad8e-139">Przykład</span><span class="sxs-lookup"><span data-stu-id="5ad8e-139">Example</span></span>  
 <span data-ttu-id="5ad8e-140">Poniższy przykład umożliwia odzyskiwanie pamięci na serwerze.</span><span class="sxs-lookup"><span data-stu-id="5ad8e-140">The following example enables server garbage collection.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ad8e-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5ad8e-141">See Also</span></span>  
 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="5ad8e-142">Schemat ustawień środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="5ad8e-142">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="5ad8e-143">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="5ad8e-143">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="5ad8e-144">Porady: wyłączanie współbieżne odzyskiwanie pamięci</span><span class="sxs-lookup"><span data-stu-id="5ad8e-144">How to: Disable Concurrent Garbage Collection</span></span>](http://msdn.microsoft.com/en-us/ba2c6c67-5778-497c-9fac-5f793b5500c7)