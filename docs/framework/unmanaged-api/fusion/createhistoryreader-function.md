---
title: CreateHistoryReader — Funkcja
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8beb5e64b05f50ba61ced72fcdb7700d4b9f30e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505045"
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader — Funkcja
Tworzy czytnik historii dla określonego pliku.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a>Parametry  
 `wzFilePath`  
 [in] Ścieżka do pliku.  
  
 `ppHistoryReader`  
 [out] Po pomyślnym zakończeniu zawiera wskaźnik do czytnika historii.  
  
## <a name="return-value"></a>Wartość zwracana  
 Ta metoda zwraca standardowych kodów błędu modelu COM, zgodnie z definicją w pliku WinError.h, oprócz wartości opisanych w poniższej tabeli.  
  
|Kod powrotu|Opis|  
|-----------------|-----------------|  
|S_OK|Wskazuje, czy metoda zakończyła się pomyślnie.|  
|E_INVALIDARG|Oznacza to, że `wzFilePath` lub `ppHistoryReader` są ustawione na odwołanie o wartości null.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Biblioteka:** Fusion.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Łączenie statycznych funkcji globalnych](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
