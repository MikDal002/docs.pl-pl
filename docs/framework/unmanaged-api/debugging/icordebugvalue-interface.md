---
title: ICorDebugValue, interfejs1
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41afc2e4305034340ad408e52ce08372bf8962dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507450"
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue, interfejs1
Reprezentuje wartość w debugowanym procesie. Wartość może być wartością zapisu lub odczytu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[CreateBreakpoint, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Ta metoda nie jest obecnie zaimplementowana.|  
|[GetAddress, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Pobiera adres to `ICorDebugValue` obiektu, który jest w trakcie debugowania.|  
|[GetSize, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Pobiera rozmiar w bajtach to `ICorDebugValue` obiektu.|  
|[GetType, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Pobiera pierwotny typ `ICorDebugValue` obiektu.|  
  
## <a name="remarks"></a>Uwagi  
 Ogólnie rzecz biorąc własność obiektu wartość jest przekazywana, gdy jest on zwracany. Adresat jest odpowiedzialny za usunięcie odwołanie z obiektu po jego zakończeniu za pomocą obiektu.  
  
 W zależności od tego, gdzie wartość została pobrana z wartość może być pozostają w mocy po wznowieniu procesu. Tak, ogólnie rzecz biorąc, wartość nie powinny być przechowywane przez wywołanie [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) metody.  
  
> [!NOTE]
>  Ten interfejs może być wywoływany zdalnie, między komputerami ani między procesami.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także




- [ICorDebugValue3, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
