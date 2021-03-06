---
title: ECustomDumpFlavor — Wyliczenie
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2be9f112d5997ec8a6b126229eb8608eb8dd8520
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627645"
---
# <a name="ecustomdumpflavor-enumeration"></a>ECustomDumpFlavor — Wyliczenie
Zawiera wartości wskazujące, które elementów do uwzględnienia w niestandardowych podzbiór sterty zrzutu podczas zgłaszania błędów.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Określa, że zrzutu sterty niestandardowych należy uruchomić jako minizrzutu i obejmują dodatkowe dane określone przez dowolne [customdumpitem —](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) wystąpienia przekazane do tej samej metody.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Określa, że zrzut sterty niestandardowego należy zebrać wszystkie dane w stanie w czasie wykonywania, które nie został przydzielony dynamicznie.|  
  
## <a name="remarks"></a>Uwagi  
 Parametr typu `ECustomDumpFlavor` jest przekazywany do [iclrerrorreportingmanager::begincustomdump —](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) metody.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ECustomDumpItemKind, wyliczenie](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [ICLRErrorReportingManager, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Hosting — wyliczenia](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
