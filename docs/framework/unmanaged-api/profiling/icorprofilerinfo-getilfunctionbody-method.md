---
title: ICorProfilerInfo::GetILFunctionBody — Metoda
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e1ef61271e5b413972b8ba40a8fe8bac60ceeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566222"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>ICorProfilerInfo::GetILFunctionBody — Metoda
Pobiera wskaźnik do treści metody w kodzie języka intermediate language (MSIL) firmy Microsoft, zaczynając od jej nagłówek.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>Parametry  
 `moduleId`  
 [in] Identyfikator modułu, w której znajduje się funkcja.  
  
 `methodId`  
 [in] Token metadanych dla metody.  
  
 `ppMethodHeader`  
 [out] Wskaźnik do nagłówka metody.  
  
 `pcbMethodSize`  
 [out] Liczba całkowita określająca rozmiar metody.  
  
## <a name="remarks"></a>Uwagi  
 Metoda obejmuje przez moduł, w którym się znajdują. Ponieważ `GetILFunctionBody` metoda kwotę ustalono, aby udzielić dostępu narzędzie do kodu MSIL, zanim został załadowany przez środowisko uruchomieniowe języka wspólnego (CLR), używa tokenu metadanych, metody można znaleźć żądanego wystąpienia.  
  
 `GetILFunctionBody` może zwracać CORPROF_E_FUNCTION_NOT_IL HRESULT, jeśli `methodId` wskazuje metodę bez żadnych MSIL kod (takie jak metody abstrakcyjnej lub platformę invoke, metoda (funkcja PInvoke)).  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf.idl, CorProf.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorProfilerInfo, interfejs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
