---
title: ISymUnmanagedMethod::GetScopeFromOffset — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5422e781ab2f494e85f637219aa540bf4ac34cb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629738"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a>ISymUnmanagedMethod::GetScopeFromOffset — Metoda
Pobiera najbardziej otaczającym zakresie leksykalnym w ramach tej metody, która otacza danego przesunięcia. Może to służyć do rozpoczęcia wyszukiwania zmiennych lokalnych.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `offset`  
 [in] Element `ULONG` zawiera przesunięcie.  
  
 `pRetVal`  
 [out] Wskaźnik, który jest ustawiony do zwracanego [isymunmanagedscope —](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfejsu.  
  
## <a name="return-value"></a>Wartość zwracana  
 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub innego kodu błędu.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Zobacz także
- [ISymUnmanagedMethod, interfejs](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
