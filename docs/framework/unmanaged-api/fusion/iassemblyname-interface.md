---
title: IAssemblyName — Interfejs
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22276e543e8eeb9c6cf9aeee7a9af92c503d3a7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549018"
---
# <a name="iassemblyname-interface"></a>IAssemblyName — Interfejs
Udostępnia metody dla opisania i Praca z unikatową tożsamość zestawu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Clone, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|Tworzy kopię pobieżną to `IAssemblyName` obiektu.|  
|[Finalize, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|Umożliwia to `IAssemblyName` obiekt, aby zwolnić zasoby i wykonywać inne operacje oczyszczania, przed jego destruktor jest wywoływany.|  
|[GetDisplayName, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|Pobiera nazwę zrozumiałą dla użytkownika, zestawu odwołuje się ten `IAssemblyName` obiektu.|  
|[GetName, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|Pobiera nazwę proste, niezaszyfrowane zestawu odwołuje się ten `IAssemblyName` obiektu.|  
|[GetProperty, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|Pobiera wskaźnik do właściwości odwołuje się określony `PropertyId`.|  
|[GetVersion, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|Pobiera informacje o wersji dla zestawu odwołuje się ten `IAssemblyName` obiektu.|  
|[IsEqual, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|Określa, czy określony `IAssemblyName` obiekt jest taki sam tym `IAssemblyName`zgodnie z flagi porównania określony.|  
|[SetProperty, metoda](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|Ustawia wartość właściwości odwołuje się określony `PropertyId`.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion.h  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Interfejsy łączenia](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IAssemblyEnum, interfejs](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
