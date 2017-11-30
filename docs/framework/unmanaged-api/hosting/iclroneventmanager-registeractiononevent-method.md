---
title: "ICLROnEventManager::RegisterActionOnEvent — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager.RegisterActionOnEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ef99527abc7ca33e1176958a590483f34556a1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="844e6-102">ICLROnEventManager::RegisterActionOnEvent — Metoda</span><span class="sxs-lookup"><span data-stu-id="844e6-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="844e6-103">Rejestruje wywołanie zwrotne wskaźnik określonego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="844e6-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="844e6-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="844e6-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="844e6-105">Parametry</span><span class="sxs-lookup"><span data-stu-id="844e6-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="844e6-106">[in] Jeden z [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) wartości i wskazujący zdarzeń, dla którego ma zostać zarejestrowany opisanego przez wskaźnik wywołania zwrotnego `pAction`.</span><span class="sxs-lookup"><span data-stu-id="844e6-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="844e6-107">[in] Wskaźnik do [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) obiekt, który jest wywoływany, gdy generowane zarejestrowane zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="844e6-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="844e6-108">Wartość zwracana</span><span class="sxs-lookup"><span data-stu-id="844e6-108">Return Value</span></span>  
  
|<span data-ttu-id="844e6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="844e6-109">HRESULT</span></span>|<span data-ttu-id="844e6-110">Opis</span><span class="sxs-lookup"><span data-stu-id="844e6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="844e6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="844e6-111">S_OK</span></span>|<span data-ttu-id="844e6-112">`RegisterActionOnEvent`zwrócona pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="844e6-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="844e6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="844e6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="844e6-114">Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.</span><span class="sxs-lookup"><span data-stu-id="844e6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="844e6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="844e6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="844e6-116">Upłynął limit czasu wywołania.</span><span class="sxs-lookup"><span data-stu-id="844e6-116">The call timed out.</span></span>|  
|<span data-ttu-id="844e6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="844e6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="844e6-118">Obiekt wywołujący nie jest właścicielem blokady.</span><span class="sxs-lookup"><span data-stu-id="844e6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="844e6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="844e6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="844e6-120">Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.</span><span class="sxs-lookup"><span data-stu-id="844e6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="844e6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="844e6-121">E_FAIL</span></span>|<span data-ttu-id="844e6-122">Wystąpił nieznany błąd krytyczny.</span><span class="sxs-lookup"><span data-stu-id="844e6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="844e6-123">Po powrocie z metody E_FAIL CLR nie jest już możliwe w ramach procesu.</span><span class="sxs-lookup"><span data-stu-id="844e6-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="844e6-124">Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="844e6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="844e6-125">Uwagi</span><span class="sxs-lookup"><span data-stu-id="844e6-125">Remarks</span></span>  
 <span data-ttu-id="844e6-126">Hosta można zarejestrować wywołań zwrotnych dla jednego lub obu typów dwóch zdarzeń opisanego przez `EClrEvent`.</span><span class="sxs-lookup"><span data-stu-id="844e6-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="844e6-127">Pobiera hosta `ICLROnEventManager` interfejsu, wywołując [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) metody.</span><span class="sxs-lookup"><span data-stu-id="844e6-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="844e6-128">Zdarzenia który `RegisterActionOnEvent` rejestrów może być uruchamiane więcej niż jeden raz i inne wątki sygnalizują zwolnienie lub wyłączenie środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="844e6-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="844e6-129">Wymagania</span><span class="sxs-lookup"><span data-stu-id="844e6-129">Requirements</span></span>  
 <span data-ttu-id="844e6-130">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="844e6-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="844e6-131">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="844e6-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="844e6-132">**Biblioteka:** uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="844e6-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="844e6-133">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="844e6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844e6-134">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="844e6-134">See Also</span></span>  
 [<span data-ttu-id="844e6-135">EClrEvent — wyliczenie</span><span class="sxs-lookup"><span data-stu-id="844e6-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="844e6-136">IActionOnCLREvent — interfejs</span><span class="sxs-lookup"><span data-stu-id="844e6-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="844e6-137">ICLRControl — interfejs</span><span class="sxs-lookup"><span data-stu-id="844e6-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="844e6-138">ICLROnEventManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="844e6-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)