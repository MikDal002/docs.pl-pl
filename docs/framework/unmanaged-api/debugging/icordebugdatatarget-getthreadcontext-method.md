---
title: ICorDebugDataTarget::GetThreadContext — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71d267eedf621a11f8ad21cc7148e1810955521c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713434"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>ICorDebugDataTarget::GetThreadContext — Metoda
Zwraca bieżący kontekst wątku określonego wątku.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwThreadID`  
 [in] Identyfikator wątku, którego kontekst ma być pobrana. Identyfikator jest definiowany przez system operacyjny.  
  
 `contextFlags`  
 [in] Bitowa kombinacja flag zależny od platformy, które wskazują, które części kontekstu powinny być odczytywane.  
  
 `contextSize`  
 [in] Rozmiar `pContext`.  
  
 `pContext`  
 [out] Bufor, w którym będzie przechowywany kontekst wątku.  
  
## <a name="remarks"></a>Uwagi  
 Na platformach Windows `pContext` musi być `CONTEXT` struktury (zdefiniowane w pliku WinNT.h), który jest odpowiedni dla typu maszyny, określonego przez [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) metody. `contextFlags` musi mieć takie same wartości jak `ContextFlags` pole `CONTEXT` struktury. `CONTEXT` Struktury jest specyficznych dla procesora; odwoływać się do pliku opis pliku WinNT.h, aby uzyskać szczegółowe informacje.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebugDataTarget, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debugowanie](../../../../docs/framework/unmanaged-api/debugging/index.md)
