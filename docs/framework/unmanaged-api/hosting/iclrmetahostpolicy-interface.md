---
title: ICLRMetaHostPolicy — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46576552db6e3c9aa06646b260e74cb4b7890d9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559232"
---
# <a name="iclrmetahostpolicy-interface"></a>ICLRMetaHostPolicy — Interfejs
Udostępnia [getrequestedruntime —](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metody, która zwraca wskaźnik do wspólnego interfejsu języka wspólnego (CLR), na podstawie kryteriów zasad, zarządzanego zestawu, wersji i pliku konfiguracji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetRequestedRuntime, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|Udostępnia preferowanym interfejsem CLR na podstawie kryteriów zasad, zarządzane pliku zestawu, wersji i konfiguracji.|  
  
## <a name="remarks"></a>Uwagi  
 Można uzyskać odwołanie do tego interfejsu, wywołując [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) funkcji, jak pokazano w poniższym kodzie:  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  Ten interfejs bez faktycznego obciążenia lub aktywacji środowiska CLR, ale po prostu zwraca, w oparciu o dostępne wersje, które są zainstalowane lub załadować preferowaną wersję środowiska CLR.  
  
 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Hostującego interfejs API konsoliduje zasady, tak, aby hosty z konkretnych potrzeb może używać podstawową funkcjonalność bez ponoszenia kar niezamierzone. Na przykład wielu eksportów MSCorEE.dll powiąże określonego środowiska CLR, mimo iż metoda może być logicznie wymaga. [Metahost_policy_flags —](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) wyliczenia zawiera zasad powiązań, które są wspólne dla większości hostów.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MetaHost.h  
  
 **Biblioteka:** Dołączony jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Interfejsy hostingu środowiska CLR dodane w programie .NET Framework 4 i 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Hosting, interfejsy](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
