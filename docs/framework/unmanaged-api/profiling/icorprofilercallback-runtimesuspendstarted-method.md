---
title: ICorProfilerCallback::RuntimeSuspendStarted — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 29d57f4ff2584ca6444f09d4e66c4ba36e3fff67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517802"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted — Metoda
Powiadamia program profilujący, że środowisko uruchomieniowe zostanie wstrzymać wszystkie wątki w czasie wykonywania.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a>Parametry  
 `suspendReason`  
 [in] Wartość [cor_prf_suspend_reason —](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) wyliczenia, która wskazuje powodem zawieszenia.  
  
## <a name="remarks"></a>Uwagi  
 Wszystkie wątki środowiska uruchomieniowego, które są w niezarządzanym kodzie są może być kontynuowane, dopóki użytkownik podejmie próbę ponownego wprowadzania w czasie wykonywania. W tym momencie one zostaną również zawieszone, dopóki nie zostanie wznowione środowiska uruchomieniowego. Dotyczy to również nowe wątki, które wprowadzać środowiska uruchomieniowego. Albo zawieszone natychmiast, gdy są one już przerywania kodu lub użytkownicy zostaną poproszeni o wstrzymać, gdy osiągną oni limit kodu są to wszystkie wątki w środowisku uruchomieniowym.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorProfilerCallback, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [RuntimeSuspendAborted, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
- [RuntimeSuspendFinished, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
