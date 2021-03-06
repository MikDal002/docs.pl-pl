---
title: ICorDebugController Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0651f8cd63f2ebdc6b81e92c0b55d94fe51316b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645304"
---
# <a name="icordebugcontroller-interface1"></a>ICorDebugController Interface1
Reprezentuje zakres, albo <xref:System.Diagnostics.Process> lub <xref:System.AppDomain>, wykonanie kodu, które mogą być kontrolowane kontekstu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Ta metoda jest przestarzała.|  
|`ICorDebugController::CommitChanges`|Ta metoda jest przestarzała.|  
|[Continue, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Wznawia wykonywanie wątków zarządzanych po wywołaniu [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).|  
|[Detach, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Odłącza debuger z domeny aplikacji lub procesu.|  
|[EnumerateThreads, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Pobiera moduł wyliczający dla aktywnego zarządzane wątki w procesie.|  
|[HasQueuedCallbacks, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Pobiera wartość wskazującą, czy wszystkie zarządzane wywołania zwrotne aktualnie czekają w kolejce dla określonego wątku.|  
|[IsRunning, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Pobiera wartość wskazującą, czy wątki w procesie są aktualnie uruchomione za darmo.|  
|[SetAllThreadsDebugState, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Ustawia stan debugowania wszystkie zarządzane wątki w procesie.|  
|[Stop, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Wykonuje wspólne stop we wszystkich wątkach, na których uruchomiono kod zarządzany w procesie.|  
|[Terminate, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Kończy proces o określony kod zakończenia.|  
  
## <a name="remarks"></a>Uwagi  
 Jeśli `ICorDebugController` jest kontrolowanie procesu, zakres obejmuje wszystkie wątki tego procesu. Jeśli `ICorDebugController` jest kontrolowanie domenę aplikacji, zakres obejmuje tylko wątki tej domeny określonej aplikacji.  
  
> [!NOTE]
>  Ten interfejs może być wywoływany zdalnie, między komputerami ani między procesami.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
