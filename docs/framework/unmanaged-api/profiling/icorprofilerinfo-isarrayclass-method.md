---
title: ICorProfilerInfo::IsArrayClass — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c131c5531d52f5ee81c70bddb67e8bc6071f39e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599672"
---
# <a name="icorprofilerinfoisarrayclass-method"></a>ICorProfilerInfo::IsArrayClass — Metoda
Określa, czy określona klasa jest klasą tablicy.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a>Parametry  
 `classId`  
 [in] Identyfikator klasy do badania.  
  
 `pBaseElemType`  
 [out] Wskaźnik do wartości corelementtype — wyliczenie, który wskazuje na typ elementów tablicy.  
  
 `pBaseClassId`  
 [out] Wskaźnik do Identyfikatora klasy elementów tablicy, jeśli jest dostępna.  
  
 `pcRank`  
 [out] Wskaźnik na liczbę całkowitą, która określa rangę tablicy (oznacza to, że liczba wymiarów).  
  
## <a name="remarks"></a>Uwagi  
 Jeśli określona klasa jest klasą tablicy `IsArrayClass` metoda zwraca wartość HRESULT S_OK i wartości dla parametrów innych niż null w danych wyjściowych. W przeciwnym razie zwraca wartość S_FALSE.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorProfilerInfo, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
