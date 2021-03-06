---
title: StrongNameErrorInfo — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameErrorInfo
helpviewer_keywords:
- StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a905840c471a268c6b106c5e25baca9c36f485d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54731065"
---
# <a name="strongnameerrorinfo-function"></a>StrongNameErrorInfo — Funkcja
Pobiera kod ostatniego błędu, który został zgłoszony przez jedną z funkcji silnej nazwy.  
  
 Ta funkcja jest przestarzała.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Ostatni kod błędu modelu COM za pomocą jednej z funkcji silnej nazwy.  
  
## <a name="remarks"></a>Uwagi  
 Większość metod silnej nazwy zwraca prostą `true` lub `false` wskazanie pomyślne zakończenie. Użyj `StrongNameErrorInfo` funkcję, aby pobrać wartość HRESULT określający ostatni błąd generowanych przez funkcje silnej nazwy.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName.h  
  
 **Biblioteka:** Dołączony jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Silnych nazw statycznych funkcji globalnych](https://msdn.microsoft.com/library/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)
