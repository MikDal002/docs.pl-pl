---
title: IGCHost::GetStats — Metoda
ms.date: 03/30/2017
api_name:
- IGCHost.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetStats
helpviewer_keywords:
- GetStats method, IGCHost interface [.NET Framework hosting]
- IGCHost::GetStats method [.NET Framework hosting]
ms.assetid: c4ae022c-46ac-4f19-9ddd-09b955f19412
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d9a3775f453cb432ce6b92d067f93ca54c329c06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674183"
---
# <a name="igchostgetstats-method"></a>IGCHost::GetStats — Metoda
Pobiera statystyki dla bieżącego stanu systemu czyszczenia pamięci.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStats`  
 [out w] Wskaźnik do [cor_gc_stats —](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) strukturę, która zawiera dane statystyczne dla bieżącego stanu systemu kolekcji wyrzucania elementów.  
  
## <a name="remarks"></a>Uwagi  
 Statystyki można przez system inteligentne alokacji systemu kolekcji wyrzucania elementów działania pomocy. Na przykład system alokacji może określić, po zapoznaniu się z statystyki, którą chce dodać większej ilości pamięci lub wymusić kolekcji.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** GCHost.idl, GCHost.h  
  
 **Biblioteka:** Dołączony jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [IGCHost, interfejs](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
