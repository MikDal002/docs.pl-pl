---
title: ICorDebugProcess5::GetGCHeapInformation — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf3d362902eb338e5d797b66c5fe2af4f3e1ae9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508330"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a>ICorDebugProcess5::GetGCHeapInformation — Metoda
Zawiera ogólne informacje o stercie wyrzucania elementów bezużytecznych, w tym, czy jest ono aktualnie wyliczalny.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pHeapInfo`  
 [out] Wskaźnik do [cor_heapinfo —](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) wartość, która zawiera ogólne informacje o stercie wyrzucania elementów bezużytecznych.  
  
## <a name="remarks"></a>Uwagi  
 `ICorDebugProcess5::GetGCHeapInformation` Metoda musi zostać wywołana przed wyliczanie stosu lub sterty poszczególnych regionów, aby upewnić się, że wyrzucanie elementów bezużytecznych struktury w procesie jest ważny w chwili obecnej. Nie może być dodawanym stercie wyrzucania elementów bezużytecznych, gdy kolekcja jest w toku. W przeciwnym razie wyliczenia mogą przechwytywać struktury kolekcji wyrzucania elementów, które są nieprawidłowe.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebugProcess5, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
