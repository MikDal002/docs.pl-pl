---
title: Metoda ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24c3c46a1f347093061983b9185234cc9959b68d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656144"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>Metoda ICorDebugProcess6::GetExportStepInfo
Zawiera informacje na temat funkcji środowiska uruchomieniowego wyeksportowane ułatwiające Przechodź przez kod zarządzany.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a>Parametry  
 pszExportName  
 [in] Nazwa funkcji eksportu środowiska uruchomieniowego podczas zapisywania w tabeli eksportu PE.  
  
 invokeKind  
 [out] Wskaźnik do składowej klasy [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) wyliczenie opisujące jak eksportowanych funkcji spowoduje wywołanie kodu zarządzanego.  
  
 invokePurpose  
 [out] Wskaźnik do składowej klasy [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) wyliczenie, które w tym artykule opisano, dlaczego eksportowanych funkcji będzie wywoływać kod zarządzany.  
  
## <a name="return-value"></a>Wartość zwracana  
 Metoda może zwracać wartości wymienione w poniższej tabeli.  
  
|Wartość zwracana|Opis|  
|------------------|-----------------|  
|`S_OK`|Wywołanie metody powiodło się.|  
|`E_POINTER`|`pInvokeKind` lub `pInvokePurpose` jest **null**.|  
|Inne niepowodzenia `HRESULT` wartości.|Odpowiednio.|  
  
## <a name="remarks"></a>Uwagi  
  
> [!NOTE]
>  Ta metoda jest tylko dostępne z architekturą .NET Native.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorDebugProcess6, interfejs](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [Debugowanie, interfejsy](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
