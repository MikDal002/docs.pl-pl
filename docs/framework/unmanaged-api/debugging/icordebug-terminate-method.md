---
title: ICorDebug::Terminate — Metoda
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 057ee7a323a8a725ebf82ee9dbaea61a43c061ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674612"
---
# <a name="icordebugterminate-method"></a>ICorDebug::Terminate — Metoda
Kończy `ICorDebug` obiektu.  
  
> [!NOTE]
>  `Terminate` nie powinien być wywoływany do momentu [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) otrzymał wywołania zwrotnego dla wszystkich procesów debugowania.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a>Uwagi  
 `Terminate` musi być wywoływana, gdy `ICorDebug` obiektu nie jest już potrzebny.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebug, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
