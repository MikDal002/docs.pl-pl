---
title: ICorDebugClass Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d12d952fe540b2ec36d058ae2100f0cf5c8e6bcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710230"
---
# <a name="icordebugclass-interface1"></a>ICorDebugClass Interface1
Reprezentuje typ, który może być podstawowy lub złożony (to jest zdefiniowany przez użytkownika). Jeśli typ ogólny, `ICorDebugClass` reprezentuje typ ogólny bez wystąpień.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[GetModule, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|Pobiera moduł, który definiuje tę klasę.|  
|[GetStaticFieldValue, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|Pobiera wartość określonego pola statyczne.|  
|[GetToken, metoda](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|Pobiera `TypeDef` token metadanych dla tej klasy.|  
  
## <a name="remarks"></a>Uwagi  
 `ICorDebugClass` Interfejs reprezentuje typ ogólny bez wystąpień. Icordebugtype — interfejs reprezentuje typ ogólny. Na przykład `Hashtable<K, V>` jest przedstawiany przez `ICorDebugClass`, podczas gdy `Hashtable<Int32, String>` jest przedstawiany przez `ICorDebugType`.  
  
 Typy nieuniwersalne są reprezentowane przez oba `ICorDebugClass` i `ICorDebugType`. Ostatnie interfejsu została wprowadzona w .NET Framework w wersji 2.0 radzenia sobie z podczas tworzenia wystąpienia typu.  
  
> [!NOTE]
>  Ten interfejs może być wywoływany zdalnie, między komputerami ani między procesami.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
