---
title: EBindPolicyLevels — Wyliczenie
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 635cf7c4e8ff715096728414506b4a7e683727b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704215"
---
# <a name="ebindpolicylevels-enumeration"></a>EBindPolicyLevels — Wyliczenie
Zawiera flagi, aby określić poziom, na którym można zastosować lub zmodyfikować zasady zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Określa, czy zasady mają być stosowane na poziomie administratora.|  
|`ePolicyLevelApp`|Określa, czy zasady mają być stosowane na poziomie aplikacji.|  
|`ePolicyLevelHost`|Określa, czy zasady mają być stosowane na poziomie hosta.|  
|`ePolicyLevelNone`|Określa flagi nie poziomu zasad.|  
|`ePolicyLevelPublisher`|Określa, czy zasady mają być stosowane na poziomie wydawcy.|  
|`ePolicyLevelRetargetable`|Określa, że zasady powinny mieć zastosowanie na poziomach zmiennej.|  
|`ePolicyPortability`|Określa, że zasady powinny obsługiwać przenoszenia między implementacjami zestawu .NET Framework. Zobacz [ \<supportportability — >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) element pliku konfiguracji.|  
|`ePolicyUnifiedToCLR`|Określa, że zasady powinny unified, środowisko uruchomieniowe języka wspólnego (CLR).|  
  
## <a name="remarks"></a>Uwagi  
 To wyliczenie jest przekazywany do metody [iclrhostbindingpolicymanager —](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfejsu, aby określić zmiany w zasadach aplikacji.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICLRAssemblyIdentityManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Hosting — wyliczenia](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
