---
title: ICorDebugValue::GetType — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4d2ba850ffc6e49cf330174dda9524c7bac4549
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709198"
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType — Metoda
Pobiera typ pierwotny obiekt "ICorDebugValue".  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pType`  
 [out] Wskaźnik do wartości wyliczenia "Corelementtype —", który wskazuje typ tej wartości.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli obiekt jest złożonych typów w czasie wykonywania, tego typu może być sprawdzane w drodze odpowiednie podklasy `ICorDebugValue` interfejsu. Na przykład "ICorDebugObjectValue", która dziedziczy z `ICorDebugValue`, reprezentuje typ złożony.  
  
 `GetType` i [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) każdego zwracają informacje o typie wartości. Zostały one zarówno zastąpione świadomy rodzajowo [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) metody.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

