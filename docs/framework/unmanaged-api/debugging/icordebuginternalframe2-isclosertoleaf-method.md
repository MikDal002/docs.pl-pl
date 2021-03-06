---
title: ICorDebugInternalFrame2::IsCloserToLeaf — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3a5dca321470b3fda8490ca5ae809045d724150
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552167"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a>ICorDebugInternalFrame2::IsCloserToLeaf — Metoda
Sprawdza, czy `this` ramka wewnętrzna jest bliżej niż określony obiekt ICorDebugFrame typu liść.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFrameToCompare`  
 [in] Wskaźnik do porównania `ICorDebugFrame` obiektu.  
  
 `pIsCloser`  
 [out] `true` Jeśli `this` ramka wewnętrzna jest bliżej liścia niż ramki określonego przez `pFrameToCompare`; w przeciwnym razie `false`.  
  
## <a name="return-value"></a>Wartość zwracana  
 Ta metoda zwraca następujące specyficzne wyniki HRESULT, a także HRESULT błędów wskazujących Niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Porównanie zostało wykonane pomyślnie.|  
|E_FAIL|Nie można wykonać porównania.|  
|E_INVALIDARG|`pFrameToCompare` lub `pIsCloser` ma wartość null.|  
  
## <a name="remarks"></a>Uwagi  
 `IsCloserToLeaf` może służyć do implementowania zasady z przeplotem ramkach wewnętrznych przy użyciu innych ramek na stosie.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebugInternalFrame2, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debugowanie](../../../../docs/framework/unmanaged-api/debugging/index.md)
