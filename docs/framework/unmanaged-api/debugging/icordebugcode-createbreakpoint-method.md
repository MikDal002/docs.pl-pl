---
title: ICorDebugCode::CreateBreakpoint — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20e718d425d0300aed8cc7ccf064126ee8384704
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608300"
---
# <a name="icordebugcodecreatebreakpoint-method"></a>ICorDebugCode::CreateBreakpoint — Metoda
Tworzy punkt przerwania w tym segmencie kodu od określonego przesunięcia.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `offset`  
 [in] Przesunięcie, przy którym chcesz utworzyć punkt przerwania.  
  
 `ppBreakpoint`  
 [out] Wskaźnik na adres obiektu "icordebugfunctionbreakpoint —", który reprezentuje punkt przerwania.  
  
## <a name="remarks"></a>Uwagi  
 Zanim punkt przerwania jest aktywna, należy dodać do obiektu procesu.  
  
 Jeśli ten kod jest kod intermediate language (MSIL) firmy Microsoft, a istnieje just-in-time (JIT)-skompilowanego, natywne wersję kodu, punkt przerwania zostaną zastosowane również kod kompilowany dokładnie na czas. (Taka sama jest wartość true, jeśli kod jest kompilowany dokładnie na czas później).  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

