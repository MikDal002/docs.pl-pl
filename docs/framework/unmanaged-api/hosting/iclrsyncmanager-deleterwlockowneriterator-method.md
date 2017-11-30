---
title: "ICLRSyncManager::DeleteRWLockOwnerIterator — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.DeleteRWLockOwnerIterator
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::DeleteRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::DeleteRWLockOwnerIterator method [.NET Framework hosting]
- DeleteRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: fcfd340a-b7d6-44e4-8167-2c05b789d483
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3df37a9572c47ce4b4a5080f6aed3f307adba360
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagerdeleterwlockowneriterator-method"></a><span data-ttu-id="c342e-102">ICLRSyncManager::DeleteRWLockOwnerIterator — Metoda</span><span class="sxs-lookup"><span data-stu-id="c342e-102">ICLRSyncManager::DeleteRWLockOwnerIterator Method</span></span>
<span data-ttu-id="c342e-103">Żąda, że środowisko uruchomieniowe języka wspólnego (CLR) zniszczyć iterację, która została utworzona przez wywołanie do [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="c342e-103">Requests that the common language runtime (CLR) destroy an iterator that was created by a call to [ICLRSyncManager::CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c342e-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="c342e-104">Syntax</span></span>  
  
```  
HRESULT DeleteRWLockOwnerIterator (  
    [in] SIZE_T  Iterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c342e-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="c342e-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="c342e-106">[in] Iterator, który został utworzony za pomocą wywołania `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="c342e-106">[in] The iterator that was created by using a call to `CreateRWLockOwnerIterator`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c342e-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="c342e-107">Return Value</span></span>  
  
|<span data-ttu-id="c342e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c342e-108">HRESULT</span></span>|<span data-ttu-id="c342e-109">Opis</span><span class="sxs-lookup"><span data-stu-id="c342e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c342e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c342e-110">S_OK</span></span>|<span data-ttu-id="c342e-111">`DeleteRWLockOwnerIterator`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="c342e-111">`DeleteRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="c342e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c342e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c342e-113">Środowisko CLR nie został załadowany do procesu lub jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="c342e-113">The CLR has not been loaded into a process, or is in a state in which it cannot run managed code or successfully process the call.</span></span>|  
|<span data-ttu-id="c342e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c342e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c342e-115">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="c342e-115">The call timed out.</span></span>|  
|<span data-ttu-id="c342e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c342e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c342e-117">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="c342e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c342e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c342e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c342e-119">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="c342e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c342e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c342e-120">E_FAIL</span></span>|<span data-ttu-id="c342e-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="c342e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c342e-122">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="c342e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c342e-123">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c342e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c342e-124">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c342e-124">Remarks</span></span>  
 <span data-ttu-id="c342e-125">Tę metodę można wywołać hosta i `CreateRWLockOwnerIterator` aby upewnić się, że jej implementacja wątków pozostaje zsynchronizowany.</span><span class="sxs-lookup"><span data-stu-id="c342e-125">The host can call this method and `CreateRWLockOwnerIterator` to ensure that its threading implementation remains synchronized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c342e-126">Wymagania</span><span class="sxs-lookup"><span data-stu-id="c342e-126">Requirements</span></span>  
 <span data-ttu-id="c342e-127">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c342e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c342e-128">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c342e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c342e-129">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c342e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c342e-130">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c342e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c342e-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c342e-131">See Also</span></span>  
 [<span data-ttu-id="c342e-132">ICLRSyncManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="c342e-132">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="c342e-133">IHostSyncManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="c342e-133">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)