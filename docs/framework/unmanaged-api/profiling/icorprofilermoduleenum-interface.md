---
title: ICorProfilerModuleEnum — Interfejs
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8966a2fc9e38594e8b2727077b7e1e85c3e52b16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705485"
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum — Interfejs
Udostępnia metody umożliwiające sekwencyjnie iterowania po kolekcji moduły załadowane przez program profilujący lub aplikacji.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Clone, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|Pobiera wskaźnik interfejsu do kopii tego `ICorProfilerModuleEnum` interfejsu.|  
|[GetCount, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|Pobiera liczbę modułów zarządzanych, które zostały załadowane do aplikacji.|  
|[Next, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|Pobiera określoną liczbę modułów sąsiadujących z sekwencyjną kolekcją obiektów, zaczynając od modułu wyliczającego bieżąca pozycja w sekwencji.|  
|[Reset, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|Przenosi kursor modułu wyliczającego do pozycji początkowej sekwencji.|  
|[Skip, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|Przesuwa do przodu pozycję kursora moduł wyliczający tak, aby określoną liczbę elementów są pomijane.|  
  
## <a name="remarks"></a>Uwagi  
 `ICorProfilerModuleEnum` Interfejs jest moduł wyliczający. Umożliwia odbiorcy tablicy do ściągnięcia elementów od nadawcy szybkością, która jest odpowiednia dla odbiorcy. Innymi słowy odbiornik jest w stanie jawnie sterowania przepływem elementów tablicy, tym samym unikając problemów związanych z przekazywania dużych tablic jako parametrów metody.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorProfilerInfo, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfejsy profilowania](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [EnumModules, metoda](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
