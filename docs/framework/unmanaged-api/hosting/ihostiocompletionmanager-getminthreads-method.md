---
title: "IHostIoCompletionManager::GetMinThreads — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6fb9369b67cd79c6e83dc13e2a1090ae611a5e5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="7aa08-102">IHostIoCompletionManager::GetMinThreads — Metoda</span><span class="sxs-lookup"><span data-stu-id="7aa08-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="7aa08-103">Pobiera minimalną liczbę wątków, które zapewnia hosta do przetwarzania żądań We/Wy.</span><span class="sxs-lookup"><span data-stu-id="7aa08-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa08-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="7aa08-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7aa08-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="7aa08-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="7aa08-106">[out] Wskaźnik do minimalna liczba wątków dostępnych do żądań We/Wy procesu hosta.</span><span class="sxs-lookup"><span data-stu-id="7aa08-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7aa08-107">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="7aa08-107">Return Value</span></span>  
  
|<span data-ttu-id="7aa08-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7aa08-108">HRESULT</span></span>|<span data-ttu-id="7aa08-109">Opis</span><span class="sxs-lookup"><span data-stu-id="7aa08-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7aa08-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7aa08-110">S_OK</span></span>|<span data-ttu-id="7aa08-111">`GetMinThreads`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="7aa08-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="7aa08-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7aa08-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7aa08-113">Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="7aa08-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7aa08-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7aa08-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7aa08-115">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="7aa08-115">The call timed out.</span></span>|  
|<span data-ttu-id="7aa08-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7aa08-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7aa08-117">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="7aa08-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7aa08-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7aa08-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7aa08-119">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="7aa08-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7aa08-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7aa08-120">E_FAIL</span></span>|<span data-ttu-id="7aa08-121">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="7aa08-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7aa08-122">Gdy metoda zwróci wartość E_FAIL, CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="7aa08-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7aa08-123">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7aa08-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7aa08-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="7aa08-124">E_NOTIMPL</span></span>|<span data-ttu-id="7aa08-125">Host nie zapewniać implementację elementu `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="7aa08-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aa08-126">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7aa08-126">Remarks</span></span>  
 <span data-ttu-id="7aa08-127">Host może być wyłączną kontrolę nad to liczba wątków przydzielony obsługę żądań We/Wy, powodów, takich jak wdrożenia, wydajności i skalowalności.</span><span class="sxs-lookup"><span data-stu-id="7aa08-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="7aa08-128">Z tego powodu hosta nie jest wymagane do zaimplementowania `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="7aa08-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="7aa08-129">W takim przypadku hosta powinien zwrócić E_NOTIMPL z tej metody.</span><span class="sxs-lookup"><span data-stu-id="7aa08-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa08-130">Wymagania</span><span class="sxs-lookup"><span data-stu-id="7aa08-130">Requirements</span></span>  
 <span data-ttu-id="7aa08-131">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aa08-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aa08-132">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7aa08-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7aa08-133">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7aa08-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7aa08-134">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aa08-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa08-135">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7aa08-135">See Also</span></span>  
 [<span data-ttu-id="7aa08-136">ICLRIoCompletionManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="7aa08-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="7aa08-137">IHostIoCompletionManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="7aa08-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)