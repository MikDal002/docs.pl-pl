---
title: ICLRMetadataLocator::GetMetadata — Metoda
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7758e61635bf6611cf83d2d66d0b62a28fac97d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647689"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>ICLRMetadataLocator::GetMetadata — Metoda
Metoda wywoływana przez wspólnego języka wspólnego (CLR) usługi dostępu do danych do pobierania metadanych obrazu.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `imagePath`  
 [in] Ciąg, który określa ścieżkę do pliku obrazu.  
  
 `imageTimestamp`  
 [in] Sygnatura czasowa pliku obrazu.  
  
 `imageSize`  
 [in] Rozmiar pliku obrazu.  
  
 `mvid`  
 [in] Unikatowy identyfikator globalny obrazu.  
  
 `mdRva`  
 [in] Wirtualny adres względny (RVA) metadanych. Adres jest określany względem adresu podstawowego obrazu.  
  
 `flags`  
 [in] Zarezerwowane do użytku w przyszłości.  
  
 `bufferSize`  
 [in] Rozmiar buforu, w której chcesz umieścić metadanych.  
  
 `buffer`  
 [out] Bufor, w której chcesz umieścić metadanych.  
  
 `dataSize`  
 [out] Rozmiar metadanych, który jest zwracany.  
  
## <a name="remarks"></a>Uwagi  
 Ta metoda jest implementowana przez moduł zapisujący debugowania aplikacji.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** ClrData.idl, ClrData.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICLRMetadataLocator, interfejs](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
