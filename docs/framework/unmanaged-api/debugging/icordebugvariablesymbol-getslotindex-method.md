---
title: Metoda ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09b50af49f8379539773d2000a6c1f8222fee875
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563837"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a>Metoda ICorDebugVariableSymbol::GetSlotIndex
Pobiera indeks zarządzane miejsce zmiennej lokalnej.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pSlotIndex`  
 [out] Wskaźnik do zmiennej lokalnej miejsca indeksu.  
  
## <a name="return-value"></a>Wartość zwracana  
 `S_OK` Jeśli to się powiedzie. `E_FAIL` Jeśli zmienna jest argumentu funkcji.  
  
## <a name="remarks"></a>Uwagi  
 Indeks gniazda zarządzanych zmienna lokalna może służyć do pobierania informacji o metadanych zmiennej  
  
> [!NOTE]
>  Ta metoda jest tylko dostępne z architekturą .NET Native.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebugVariableSymbol, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
