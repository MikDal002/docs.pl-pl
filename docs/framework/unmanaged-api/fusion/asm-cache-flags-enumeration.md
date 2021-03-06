---
title: ASM_CACHE_FLAGS — Wyliczenie
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29388f7a83182fe3149a9df364a0f4721232012d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585331"
---
# <a name="asmcacheflags-enumeration"></a>ASM_CACHE_FLAGS — Wyliczenie
Wskazuje źródło zestawu, który jest reprezentowany przez [iassemblycacheitem —](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) w globalnej pamięci podręcznej.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Wylicza pamięci podręcznej zestawów, wstępnie skompilowane przy użyciu Ngen.exe.|  
|`ASM_CACHE_GAC`|Wylicza globalnej pamięci podręcznej.|  
|`ASM_CACHE_DOWNLOAD`|Wylicza zestawy, które zostały pobrane na żądanie lub które zostały skopiowane w tle.|  
|`ASM_CACHE_ROOT`|Oznacza to, że [getcachepath —](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funkcja powinna zwrócić ścieżki do globalnej pamięci podręcznej, aby uzyskać środowisko uruchomieniowe języka wspólnego (CLR) w wersji 2.0. Znaczenie tylko w kontekście wywołania [getcachepath —](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Oznacza to, że [getcachepath —](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md) funkcja powinna zwrócić ścieżki do globalnej pamięci podręcznej dla CLR w wersji 4. Znaczenie tylko w kontekście wywołania [getcachepath —](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md).|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion.h  
  
 **Biblioteka:** Dołączony jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [GetCachePath, funkcja](../../../../docs/framework/unmanaged-api/fusion/getcachepath-function.md)
- [IAssemblyCacheItem, interfejs](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
- [Wyliczenia łączenia](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
