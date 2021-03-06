---
title: IEnumReferenceIdentity — Interfejs
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f2ea9d0e20cb67cc36d0b5883e483ce98941b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743221"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity — Interfejs
Służy jako moduł wyliczający dla kolekcji `IReferenceIdentity` obiektów.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|Pobiera wskaźnik interfejsu do nowego `IEnumReferenceIdentity` zawiera te same elementy członkowskie, ponieważ `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Next`|Pobiera określoną liczbę `IReferenceIdentity` obiektów, począwszy od bieżącej pozycji.|  
|`IEnumReferenceIdentity::Reset`|Przesuwa wskaźnik instrukcji na początku `IEnumReferenceIdentity`.|  
|`IEnumReferenceIdentity::Skip`|Przesuwa wskaźnik instrukcji do przodu o określoną liczbę elementów, zaczynając od bieżącej pozycji.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Isolation.h  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Interfejsy łączenia](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IReferenceIdentity, interfejs](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
