---
title: IAssemblyEnum::GetNextAssembly — Metoda
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 563784dd2fe3881cbf3278992ca2c75a94df1d3f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727563"
---
# <a name="iassemblyenumgetnextassembly-method"></a>IAssemblyEnum::GetNextAssembly — Metoda
Pobiera wskaźnik do następnego [iassemblyname —](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) zawarte w tym [iassemblyenum —](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pvReserved`  
 [in] Zarezerwowane dla przyszłej rozszerzalności. `pvReserved` musi być odwołanie o wartości null.  
  
 `ppName`  
 [out] Zwrócony `IAssemblyName` wskaźnika.  
  
 `dwFlags`  
 [in] Zarezerwowane dla przyszłej rozszerzalności. `dwFlags` musi być równa 0 (zero).  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion.h  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [IAssemblyName, interfejs](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [IAssemblyEnum, interfejs](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
