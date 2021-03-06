---
title: ICLRControl — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61f9448735f5d26d122ed44c4f41c4fd2a9f7478
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614305"
---
# <a name="iclrcontrol-interface"></a>ICLRControl — Interfejs
Udostępnia metody, które umożliwia pobieranie odwołań do hosta i Konfiguruj aspekty, środowisko uruchomieniowe języka wspólnego (CLR).  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetCLRManager, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)|Pobiera wskaźnik interfejsu do wystąpienia dowolnego typu menedżera, która hosta można użyć do konfigurowania środowiska CLR.|  
|[SetAppDomainManagerType, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)|Ustawia typ pochodzący od <xref:System.AppDomainManager> jako typ dla menedżerów domeny aplikacji.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** Dołączony jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICLRAssemblyIdentityManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRDebugManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [ICLRGCManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [ICLRHostBindingPolicyManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [ICLRHostProtectionManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [ICLROnEventManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [ICLRPolicyManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [IHostControl, interfejs](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [Hosting, interfejsy](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
