---
title: ICorDebug::SetUnmanagedHandler — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.SetUnmanagedHandler
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::SetUnmanagerHandler
helpviewer_keywords:
- SetUnmanagedHandler method [.NET Framework debugging]
- ICorDebug::SetUnmanagedHandler method [.NET Framework debugging]
ms.assetid: 6b546be4-f86d-4536-8cfc-1d08e5066eb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42ee1f0652a6534372a37a630df0e48d289a9a34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724609"
---
# <a name="icordebugsetunmanagedhandler-method"></a>ICorDebug::SetUnmanagedHandler — Metoda
Określa obiekt programu obsługi zdarzeń dla zdarzenia niezarządzane.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT SetUnmanagedHandler (  
    [in] ICorDebugUnmanagedCallback  *pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCallback`  
 [in] Wskaźnik do [icordebugunmanagedcallback —](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md) obiekt, który reprezentuje program obsługi zdarzeń dla zdarzenia niezarządzane.  
  
## <a name="remarks"></a>Uwagi  
 Program obsługi zdarzeń obiekt niezarządzanych zdarzenia musi być ustawiona po wywołaniu [ICorDebug::Initialize](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md) i przed wszelkie wywołania [icordebug::CreateProcess —](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) lub [ICorDebug::DebugActiveProcess ](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md). Jednak do celów starszej wersji, nie należy ustawić obiekt programu obsługi zdarzeń dla zdarzenia niezarządzane do momentu pierwszego zdarzenia debugowania natywnych jest wywoływane. W szczególności jeśli `ICorDebug::CreateProcess` flagę CREATE_SUSPENDED, debugowania natywnych zdarzeń nie może być przekazana, dopóki nie zostanie wznowione w wątku głównym.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebug, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
