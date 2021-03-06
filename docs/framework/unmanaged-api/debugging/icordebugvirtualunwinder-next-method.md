---
title: Metoda ICorDebugVirtualUnwinder::Next
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6b6b7078db058150ec39bcf82e6984a1949e7cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507138"
---
# <a name="icordebugvirtualunwindernext-method"></a>Metoda ICorDebugVirtualUnwinder::Next
Przechodzi do obiektu wywołującego kontekstu.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT Next();  
```  
  
#### <a name="parameters"></a>Parametry  
 Brak.  
  
## <a name="return-value"></a>Wartość zwracana  
 `S_OK` Jeśli rozwinięcie wystąpił pomyślnie, lub `CORDBG_S_AT_END_OF_STACK` Jeśli rozwinięcie nie można zakończyć, ponieważ nie ma żadnych więcej ramek.  
  
 Jeśli niepowodzenie, jest zwracana wartość HRESULT, icordebug — interfejsy API zwracają `CORDBG_E_DATA_TARGET_ERROR`.  
  
## <a name="remarks"></a>Uwagi  
 Walker stosu należy upewnić się, że to sprawia, że postęp, to znaczy po pewnym czasie wywołania `Next` zwróci niepowodzenie HRESULT lub `CORDBG_S_AT_END_OF_STACK`. Zwracanie `S_OK` przez czas nieokreślony może spowodować nieskończoną pętlę.  
  
> [!NOTE]
>  Ta metoda jest tylko dostępne z architekturą .NET Native.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebugMemoryBuffer, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
