---
title: Interfejs ICorDebugDebugEvent
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e9a7efadea7960eadccfa1637489ed14bbeb26f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576320"
---
# <a name="icordebugdebugevent-interface"></a>Interfejs ICorDebugDebugEvent
Definiuje interfejs podstawowy, z którym wszystkie `ICorDebug` pochodzić zdarzeń debugowania.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetEventKind, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|Wskazuje rodzaj zdarzeń, to `ICorDebugDebugEvent` obiekt reprezentuje.|  
|[GetThread, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|Pobiera wątku, w którym wystąpiło zdarzenie.|  
  
## <a name="remarks"></a>Uwagi  
 Następujące interfejsy są pochodną `ICorDebugDebugEvent` interfejsu:  
  
-   [ICorDebugExceptionDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
-   [ICorDebugModuleDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  Interfejs jest tylko dostępne z architekturą .NET Native. Próba wywołania `QueryInterface` do pobrania wskaźnika interfejsu zwraca `E_NOINTERFACE` scenariuszach ICorDebug poza .NET Native.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debugowanie](../../../../docs/framework/unmanaged-api/debugging/index.md)
