---
title: ICorProfilerCallback::ModuleUnloadFinished — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7759b0815946301932ca60edaf731313d04a245
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743468"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>ICorProfilerCallback::ModuleUnloadFinished — Metoda
Powiadamia program profilujący, moduł zakończenie zwolnienie.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
#### <a name="parameters"></a>Parametry  
 `moduleId`  
 [in] Identyfikator modułu, który został usunięty z pamięci.  
  
 `hrStatus`  
 [in] Wartość HRESULT, która wskazuje, czy moduł został zwolniony.  
  
## <a name="remarks"></a>Uwagi  
 Wartość `moduleId` jest nieprawidłowa dla żądania informacji po [icorprofilercallback::moduleunloadstarted —](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) metoda zwraca.  
  
 Niektóre części zwolnienie tej klasy może kontynuować po `ModuleUnloadFinished` wywołania zwrotnego. Błąd HRESULT w `hrStatus` wskazuje błąd. Jednak sukcesów wartość HRESULT w `hrStatus` tylko wskazuje, czy zakończyła się pomyślnie w pierwszej części zwalnianie modułu.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorProfilerCallback, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
