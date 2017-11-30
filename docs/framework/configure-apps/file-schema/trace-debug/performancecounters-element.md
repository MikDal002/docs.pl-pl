---
title: "&lt;liczniki wydajności&gt; — Element"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f7fdbb244663e5114880437a5a508270c80a9c79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltperformancecountersgt-element"></a><span data-ttu-id="98f11-102">&lt;liczniki wydajności&gt; — Element</span><span class="sxs-lookup"><span data-stu-id="98f11-102">&lt;performanceCounters&gt; Element</span></span>
<span data-ttu-id="98f11-103">Określa rozmiar pamięci globalnej współużytkowane przez liczniki wydajności.</span><span class="sxs-lookup"><span data-stu-id="98f11-103">Specifies the size of the global memory shared by performance counters.</span></span>  
  
 <span data-ttu-id="98f11-104">\<Konfiguracja ></span><span class="sxs-lookup"><span data-stu-id="98f11-104">\<configuration></span></span>  
<span data-ttu-id="98f11-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="98f11-105">\<system.diagnostics></span></span>  
<span data-ttu-id="98f11-106">\<liczniki wydajności ></span><span class="sxs-lookup"><span data-stu-id="98f11-106">\<performanceCounters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f11-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="98f11-107">Syntax</span></span>  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98f11-108">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="98f11-108">Attributes and Elements</span></span>  
 <span data-ttu-id="98f11-109">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="98f11-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98f11-110">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="98f11-110">Attributes</span></span>  
  
|<span data-ttu-id="98f11-111">Atrybut</span><span class="sxs-lookup"><span data-stu-id="98f11-111">Attribute</span></span>|<span data-ttu-id="98f11-112">Opis</span><span class="sxs-lookup"><span data-stu-id="98f11-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98f11-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="98f11-113">filemappingsize</span></span>|<span data-ttu-id="98f11-114">Atrybut wymagany.</span><span class="sxs-lookup"><span data-stu-id="98f11-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="98f11-115">Określa rozmiar w bajtach pamięci globalnej współużytkowane przez liczniki wydajności.</span><span class="sxs-lookup"><span data-stu-id="98f11-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="98f11-116">Wartość domyślna to 524288.</span><span class="sxs-lookup"><span data-stu-id="98f11-116">The default is 524288.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98f11-117">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="98f11-117">Child Elements</span></span>  
 <span data-ttu-id="98f11-118">Brak.</span><span class="sxs-lookup"><span data-stu-id="98f11-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98f11-119">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="98f11-119">Parent Elements</span></span>  
  
|<span data-ttu-id="98f11-120">Element</span><span class="sxs-lookup"><span data-stu-id="98f11-120">Element</span></span>|<span data-ttu-id="98f11-121">Opis</span><span class="sxs-lookup"><span data-stu-id="98f11-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="98f11-122">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="98f11-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="98f11-123">Określa element root dla sekcji konfiguracji ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="98f11-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98f11-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="98f11-124">Remarks</span></span>  
 <span data-ttu-id="98f11-125">Liczniki wydajności za pomocą plików mapowanych na pamięć lub pamięci współużytkowanej do publikowania danych wydajności.</span><span class="sxs-lookup"><span data-stu-id="98f11-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="98f11-126">Rozmiar pamięci współużytkowanej Określa, jak wiele wystąpień, które mogą być używane jednocześnie.</span><span class="sxs-lookup"><span data-stu-id="98f11-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="98f11-127">Istnieją dwa typy pamięci współużytkowanej: globalne udostępnionych pamięci i oddzielne pamięci współużytkowanej.</span><span class="sxs-lookup"><span data-stu-id="98f11-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="98f11-128">Globalnej pamięci współdzielonej jest używany przez wszystkie kategorii licznika wydajności zainstalowane wersje .NET Framework w wersji 1.0 lub 1.1.</span><span class="sxs-lookup"><span data-stu-id="98f11-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="98f11-129">Zainstalowane z .NET Framework w wersji 2.0 kategorii licznika wydajności za pomocą osobnych pamięci współużytkowanej, każdej kategorii licznika wydajności posiadanie własnej pamięci.</span><span class="sxs-lookup"><span data-stu-id="98f11-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>  
  
 <span data-ttu-id="98f11-130">Rozmiar globalnej pamięci współdzielonej można ustawić tylko w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="98f11-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="98f11-131">Rozmiar domyślny to 524,288 bTak, maksymalny rozmiar to 33,554,432 bajtów, a minimalny rozmiar to 32 768 bajtów.</span><span class="sxs-lookup"><span data-stu-id="98f11-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="98f11-132">Ponieważ globalnej pamięci współdzielonej jest współużytkowana przez wszystkie procesy i kategorie, twórca pierwszy Określa rozmiar.</span><span class="sxs-lookup"><span data-stu-id="98f11-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="98f11-133">Jeśli rozmiar jest zdefiniowana w pliku konfiguracyjnym aplikacji, ten rozmiar jest używane, jeśli aplikacja jest pierwszym aplikacji, która powoduje, że liczniki wydajności do wykonania.</span><span class="sxs-lookup"><span data-stu-id="98f11-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="98f11-134">W związku z tym właściwym miejscu, aby określić `filemappingsize` wartość jest plik Machine.config.</span><span class="sxs-lookup"><span data-stu-id="98f11-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="98f11-135">Nie można zwolnić pamięć w globalnej pamięci współdzielonej przez liczniki wydajności poszczególnych, więc po pewnym czasie wyczerpania globalnej pamięci współdzielonej jeśli są tworzone dużą liczbę wystąpień liczników wydajności o różnych nazwach.</span><span class="sxs-lookup"><span data-stu-id="98f11-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>  
  
 <span data-ttu-id="98f11-136">Rozmiaru oddzielne pamięci współużytkowanej w rejestrze wartość DWORD FileMappingSize klucza HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<nazwa kategorii >*\Performance odwołuje się do najpierw a następnie wartość określona dla globalnej pamięci współdzielonej w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="98f11-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>*\Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="98f11-137">Jeśli wartość FileMappingSize nie istnieje, a następnie czwarty co ma ustawianą wielkość pamięci współużytkowanej oddzielne (1/4) ustawienie globalne w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="98f11-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f11-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="98f11-138">See Also</span></span>  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>