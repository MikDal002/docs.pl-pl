---
title: ICorProfilerInfo2::GetStaticFieldInfo — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6711d0e0423534744de1ee4b8a734ed2f8eab24d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514286"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>ICorProfilerInfo2::GetStaticFieldInfo — Metoda
Pobiera wartość wskazującą rodzaj statyczną, która ma zastosowanie do określonego pola.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a>Parametry  
 `classId`  
 [in] Identyfikator klasy, w którym zdefiniowano pole statyczne.  
  
 `fieldToken`  
 [in] Token metadanych dla pola statyczne.  
  
 `pFieldInfo`  
 [out] Wskaźnik do wartości [cor_prf_static_type —](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) wyliczenia oznacza to, czy określone pole jest statyczna, a jeśli tak, rodzaj statyczne która odnosi się do pola.  
  
## <a name="remarks"></a>Uwagi  
 Te informacje, można określić, której funkcji należy wywołać, aby uzyskać adres pole statyczne.  
  
 Kod programu profilującego nadal należy sprawdzić metadanych dla pola statycznego upewnić się, że faktycznie ma adres. Literały statyczne (czyli stałych) istnieje tylko w metadanych i nie ma adresu.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorProfilerInfo, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
