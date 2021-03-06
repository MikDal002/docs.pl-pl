---
title: IDefinitionAppId — Interfejs
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e8bb31967a6ad515761e6cd03657f2c834debe5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545559"
---
# <a name="idefinitionappid-interface"></a>IDefinitionAppId — Interfejs
Reprezentuje unikatowy identyfikator dla kodu, który definiuje aplikacji w bieżącym zakresie.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Pobiera ciąg formatowania, która przedstawia kod w tym `IDefinitionAppId` obiektu.|  
|`IDefinitionAppId::put_Codebase`|Ustawia kod to `IDefinitionAppId` wartość ciągu sformatowaną jak określony obiekt.|  
|`IDefinitionAppId::EnumAppPath`|Pobiera wskaźnik interfejsu do [ienumdefinitionidentity —](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) obiekt, który zawiera zestawów w bieżącej ścieżce aplikacji.|  
|`IDefinitionAppId::SetAppPath`|Ustawia ścieżkę aplikacji dla zestawu w bieżącym zakresie wartości odwołuje się określony [idefinitionidentity —](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) obiektu.|  
|`IDefinitionAppId::get_SubscriptionId`|Pobiera wskaźnik do reprezentację ciągu identyfikatora tokenu dla subskrypcji w tym `IDefinitionAppId` obiektu.|  
|`IDefinitionAppId::put_SubscriptionId`|Ustawia token identyfikator subskrypcji to `IDefinitionAppId` obiektu określona wartość ciągu.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Isolation.h  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Interfejsy łączenia](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
