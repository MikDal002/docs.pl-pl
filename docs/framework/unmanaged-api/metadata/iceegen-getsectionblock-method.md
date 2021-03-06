---
title: ICeeGen::GetSectionBlock — Metoda
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb1268d9fd892a4400491aca7966d81a3e23f9c6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515355"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock — Metoda
Pobiera blok części bazy kodu.  
  
 Ta metoda jest przestarzała i nie powinna być używana.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
#### <a name="parameters"></a>Parametry  
 `section`  
 [in] Sekcja, z których mają być pobierane blok bazy kodu.  
  
 `len`  
 [in] Długość bloku, które mają zostać pobrane.  
  
 `align`  
 [in] Bajt względem początku sekcji, z którą ma zostać wyrównywanie pierwszego bajtu bloku. Jest to pozycja bloku, w ramach tej sekcji.  
  
 `ppBytes`  
 [out] Wskaźnik do lokalizacji, która otrzymuje adres bloku pobrane.  
  
## <a name="remarks"></a>Uwagi  
 Wywołaj `GetSectionBlock` tylko wtedy, gdy masz sekcją wymagań, które nie są obsługiwane przy użyciu innych metod.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** COR.h  
  
 **Biblioteka:** Używany jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICeeGen, interfejs](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
