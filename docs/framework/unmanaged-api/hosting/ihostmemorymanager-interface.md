---
title: "IHostMemoryManager — Interfejs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 415539be0dbed8e0cf3f9d6e5c79bf4cfac09fe2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanager-interface"></a><span data-ttu-id="acf98-102">IHostMemoryManager — Interfejs</span><span class="sxs-lookup"><span data-stu-id="acf98-102">IHostMemoryManager Interface</span></span>
<span data-ttu-id="acf98-103">Udostępnia metody, które umożliwia środowisko uruchomieniowe języka wspólnego (CLR) do żądania pamięci wirtualnej za pośrednictwem hosta, zamiast używać standardowych funkcji Win32 w pamięci wirtualnej.</span><span class="sxs-lookup"><span data-stu-id="acf98-103">Provides methods that allow the common language runtime (CLR) to make virtual memory requests through the host, instead of using the standard Win32 virtual memory functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acf98-104">Metody</span><span class="sxs-lookup"><span data-stu-id="acf98-104">Methods</span></span>  
  
|<span data-ttu-id="acf98-105">Metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-105">Method</span></span>|<span data-ttu-id="acf98-106">Opis</span><span class="sxs-lookup"><span data-stu-id="acf98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acf98-107">AcquiredVirtualAddressSpace — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-107">AcquiredVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|<span data-ttu-id="acf98-108">Powiadamia hosta, że środowisko uruchomieniowe języka wspólnego (CLR) uzyskał określonego pamięci systemu operacyjnego.</span><span class="sxs-lookup"><span data-stu-id="acf98-108">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>|  
|[<span data-ttu-id="acf98-109">CreateMAlloc — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-109">CreateMAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|<span data-ttu-id="acf98-110">Pobiera wskaźnika interfejsu do [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) wystąpienie, które jest używane do żądania alokacji pamięci z sterty utworzone przez hosta.</span><span class="sxs-lookup"><span data-stu-id="acf98-110">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to request memory allocations from a heap created by the host.</span></span>|  
|[<span data-ttu-id="acf98-111">GetMemoryLoad — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-111">GetMemoryLoad Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|<span data-ttu-id="acf98-112">Pobiera ilość pamięci fizycznej, która jest aktualnie używana, zgłoszonej przez hosta.</span><span class="sxs-lookup"><span data-stu-id="acf98-112">Gets the amount of physical memory that is currently being used, as reported by the host.</span></span>|  
|[<span data-ttu-id="acf98-113">NeedsVirtualAddressSpace — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-113">NeedsVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|<span data-ttu-id="acf98-114">Powiadamia host czy CLR będzie próbować używać pamięci określony.</span><span class="sxs-lookup"><span data-stu-id="acf98-114">Notifies the host that the CLR is going to attempt to use the specified memory.</span></span>|  
|[<span data-ttu-id="acf98-115">RegisterMemoryNotificationCallback — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-115">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|<span data-ttu-id="acf98-116">Rejestruje wskaźnika do funkcji wywołania zwrotnego, która wywołuje hosta powiadomiono CLR bieżącego obciążenia pamięci na komputerze.</span><span class="sxs-lookup"><span data-stu-id="acf98-116">Registers a pointer to a callback function that the host invokes to notify the CLR of the current memory load on the computer.</span></span>|  
|[<span data-ttu-id="acf98-117">ReleasedVirtualAddressSpace — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-117">ReleasedVirtualAddressSpace Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|<span data-ttu-id="acf98-118">Powiadamia hosta CLR zostało zakończone, przy użyciu określonego pamięci.</span><span class="sxs-lookup"><span data-stu-id="acf98-118">Notifies the host that the CLR has finished using the specified memory.</span></span>|  
|[<span data-ttu-id="acf98-119">VirtualAlloc — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-119">VirtualAlloc Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|<span data-ttu-id="acf98-120">Służy jako otoka logiczne dla odpowiedniej funkcji Win32, rezerwuje lub zatwierdza region stron w wirtualnej przestrzeni adresowej procesu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="acf98-120">Serves as a logical wrapper for the corresponding Win32 function, which reserves or commits a region of pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="acf98-121">VirtualFree — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-121">VirtualFree Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|<span data-ttu-id="acf98-122">Służy jako otoka logiczne dla odpowiedniej funkcji Win32, co zwalnia, decommits, lub zwalnia i decommits region stron w wirtualnej przestrzeni adresowej procesu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="acf98-122">Serves as a logical wrapper for the corresponding Win32 function, which releases, decommits, or releases and decommits a region of pages within the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="acf98-123">VirtualProtect — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-123">VirtualProtect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|<span data-ttu-id="acf98-124">Służy jako otoka logiczne dla odpowiedniej funkcji Win32 zmienia ochrony obszaru zatwierdzone stron w wirtualnej przestrzeni adresowej procesu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="acf98-124">Serves as a logical wrapper for the corresponding Win32 function, which changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>|  
|[<span data-ttu-id="acf98-125">VirtualQuery — metoda</span><span class="sxs-lookup"><span data-stu-id="acf98-125">VirtualQuery Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|<span data-ttu-id="acf98-126">Służy jako otoka logiczne dla odpowiedniej funkcji Win32 pobiera informacje o zakresie stron w wirtualnej przestrzeni adresowej procesu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="acf98-126">Serves as a logical wrapper for the corresponding Win32 function, which retrieves information about a range of pages in the virtual address space of the calling process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acf98-127">Uwagi</span><span class="sxs-lookup"><span data-stu-id="acf98-127">Remarks</span></span>  
 <span data-ttu-id="acf98-128">`IHostMemoryManager`udostępnia metody dla CLR można uzyskać wskaźnika za pośrednictwem której na wysyłanie żądań pamięci na stosie, a także aby uzyskać poziom wykorzystania pamięci w procesie zgłoszonej przez hosta.</span><span class="sxs-lookup"><span data-stu-id="acf98-128">`IHostMemoryManager` also provides methods for the CLR to obtain a pointer through which to make memory requests on the heap and to get the level of memory pressure in the process, as reported by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf98-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="acf98-129">Requirements</span></span>  
 <span data-ttu-id="acf98-130">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf98-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf98-131">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="acf98-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acf98-132">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acf98-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acf98-133">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf98-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf98-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="acf98-134">See Also</span></span>  
 [<span data-ttu-id="acf98-135">IHostMalloc — interfejs</span><span class="sxs-lookup"><span data-stu-id="acf98-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="acf98-136">Hosting — interfejsy</span><span class="sxs-lookup"><span data-stu-id="acf98-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)