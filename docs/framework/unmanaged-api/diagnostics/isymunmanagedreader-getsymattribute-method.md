---
title: ISymUnmanagedReader::GetSymAttribute — Metoda
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d43467a0f3ff94eb7903b808e192230e6c0ff1e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561075"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a>ISymUnmanagedReader::GetSymAttribute — Metoda
Pobiera atrybut niestandardowy na podstawie jego nazwy. W przeciwieństwie do metadanych atrybutów niestandardowych te atrybuty niestandardowe są przechowywane w magazynie symboli.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [in] Token metadanych dla obiektu, dla którego żądana jest atrybut.  
  
 `name`  
 [in] Wskaźnik do zmiennej, która wskazuje atrybut do pobrania.  
  
 `cBuffer`  
 [in] Rozmiar `buffer` tablicy.  
  
 `pcBuffer`  
 [out] Wskaźnik do zmiennej, która odbiera długość danych atrybutu.  
  
 `buffer`  
 [out] Wskaźnik do zmiennej, która odbiera dane atrybutu.  
  
## <a name="return-value"></a>Wartość zwracana  
 S_OK, jeśli metoda się powiedzie; w przeciwnym razie E_FAIL lub innego kodu błędu...  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Zobacz także
- [ISymUnmanagedReader, interfejs](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
