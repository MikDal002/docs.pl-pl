---
title: ICLRStrongName::StrongNameKeyGenEx — Metoda
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b02792a0547b9b8ba6215069c3c0abf48726ded
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508668"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a>ICLRStrongName::StrongNameKeyGenEx — Metoda
Generuje nową parę kluczy publiczny/prywatny z określonego rozmiaru klucza do użycia silnej nazwy.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `wszKeyContainer`  
 [in] Nazwa żądany kontener kluczy. `wszKeyContainer` musi być niepustym ciągiem lub wartością null można wygenerować tymczasowej nazwy.  
  
 `dwFlags`  
 [in] Wartość, która określa, czy należy pozostawić klawisz zarejestrowany. Obsługiwane są następujące wartości:  
  
-   0x00000000 — używany podczas `wszKeyContainer` ma wartość null, aby wygenerować nazwę kontenera kluczy tymczasowych.  
  
-   0x00000001 (`SN_LEAVE_KEY`) — określa, że klucz powinien być zarejestrowany po lewej.  
  
 `dwKeySize`  
 [in] Żądany rozmiar klucza w bitach.  
  
 `ppbKeyBlob`  
 [out] Zwrócone pary kluczy publiczny/prywatny.  
  
 `pcbKeyBlob`  
 [out] Rozmiar w bajtach z `ppbKeyBlob`.  
  
## <a name="return-value"></a>Wartość zwracana  
 `S_OK` Jeśli metoda została ukończona pomyślnie; w przeciwnym razie wartość HRESULT, która wskazuje błąd (zobacz [typowe wartości HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) dla listy).  
  
## <a name="remarks"></a>Uwagi  
 Wymaga platformy .NET Framework w wersji 1.0 i 1.1 `dwKeySize` o długości 1024 bitów, aby podpisać zestaw silną nazwą; w wersji 2.0 dodaje obsługiwanych w przypadku 2048-bitowe klucze.  
  
 Po pobraniu klucza, należy wywołać [iclrstrongname::strongnamefreebuffer —](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodę, aby zwolnić alokacji pamięci.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MetaHost.h  
  
 **Biblioteka:** Dołączony jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [StrongNameKeyGen, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [ICLRStrongName, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
