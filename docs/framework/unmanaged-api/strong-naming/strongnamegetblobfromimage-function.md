---
title: StrongNameGetBlobFromImage — Funkcja
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d058c1ad070e2ffacdf2129c6d9657d0fc1d01e9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737286"
---
# <a name="strongnamegetblobfromimage-function"></a>StrongNameGetBlobFromImage — Funkcja
Pobiera reprezentacja binarna obrazu zestawu pod adresem określonym pamięci.  
  
 Ta funkcja jest przestarzała. Użyj [iclrstrongname::strongnamegetblobfromimage —](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) metody zamiast tego.  
  
## <a name="syntax"></a>Składnia  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbBase`  
 [in] Adres pamięci manifestu zestawu zamapowany.  
  
 `dwLength`  
 [in] Rozmiar w bajtach, obraz u `pbBase`.  
  
 `pbBlob`  
 [in] Bufor do przechowywania reprezentacja binarna obrazu.  
  
 `pcbBlob`  
 [out w] Maksymalny rozmiar w bajtach, żądane `pbBlob`. Po powrocie, rzeczywisty rozmiar w bajtach, z `pbBlob`.  
  
## <a name="return-value"></a>Wartość zwracana  
 `true` Po pomyślnym zakończeniu; w przeciwnym razie `false`.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli `StrongNameGetBlobFromImage` funkcja nie jest ukończone pomyślnie, wywołaj [strongnameerrorinfo —](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funkcję, aby pobrać ostatni błąd wygenerowany.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** StrongName.h  
  
 **Biblioteka:** Dołączony jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [StrongNameGetBlobFromImage, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [StrongNameGetBlob, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [ICLRStrongName, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
