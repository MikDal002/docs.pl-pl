---
title: IHostSyncManager::SetCLRSyncManager — Metoda
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cbf6d14ebb82b5e653596c735ed170c5bc7e763
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625227"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a>IHostSyncManager::SetCLRSyncManager — Metoda
Zestawy [iclrsyncmanager —](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) wystąpienia do skojarzenia z bieżącego [ihostsyncmanager —](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) wystąpienia.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pManager`  
 [in] Wskaźnik do `ICLRSyncManager` wystąpienia dostarczane przez środowisko uruchomieniowe języka wspólnego (CLR).  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|`SetCLRSyncManager` pomyślnie zwrócił.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko CLR nie został załadowany do procesu lub środowisko CLR jest w stanie, w której nie można uruchomić kod zarządzany lub przetworzyć wywołania.|  
|HOST_E_TIMEOUT|Upłynął limit czasu wywołania.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie posiada blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas zablokowane wątki lub włókna oczekiwał na nim.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Po powrocie z metody E_FAIL CLR nie jest już można używać w ramach procesu. Kolejne wywołania do hostowania metody zwracają HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  
 W celu ułatwienia komunikacji między hostem a środowisko CLR, interfejsami hostingu są ogólnie dostępne w pary. Jednego członka pary jest implementowany przez hosta i innego członka jest implementowany przez środowisko CLR. Jako wdrażania po stronie hosta `IHostSyncManager` interfejsu odnosi się do `ICLRSyncManager` interfejs implementowany przez środowisko CLR. CLR wywołuje `SetCLRSyncManager` umożliwiają określanie wartości `ICLRSyncManager` wystąpienia hosta do skojarzenia z bieżącego `IHostSyncManager` wystąpienia.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** Dołączony jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICLRSyncManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
