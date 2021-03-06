---
title: CorDebugChainReason — Wyliczenie
ms.date: 03/30/2017
api_name:
- CorDebugChainReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugChainReason
helpviewer_keywords:
- CorDebugChainReason enumeration [.NET Framework debugging]
ms.assetid: c915da51-50b2-41df-841a-2b971f4d0975
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 621ae6dae32e79a26d81441841b4c6a274d86f83
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497603"
---
# <a name="cordebugchainreason-enumeration"></a>CorDebugChainReason — Wyliczenie
Wskazuje powód lub powody do rozpoczęcia łańcuch wywołań.  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef enum CorDebugChainReason {  
    CHAIN_NONE              = 0x000,  
    CHAIN_CLASS_INIT        = 0x001,  
    CHAIN_EXCEPTION_FILTER  = 0x002,  
    CHAIN_SECURITY          = 0x004,  
    CHAIN_CONTEXT_POLICY    = 0x008,  
    CHAIN_INTERCEPTION      = 0x010,  
    CHAIN_PROCESS_START     = 0x020,  
    CHAIN_THREAD_START      = 0x040,  
    CHAIN_ENTER_MANAGED     = 0x080,  
    CHAIN_ENTER_UNMANAGED   = 0x100,  
    CHAIN_DEBUGGER_EVAL     = 0x200,  
    CHAIN_CONTEXT_SWITCH    = 0x400,  
    CHAIN_FUNC_EVAL         = 0x800  
} CorDebugChainReason;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|`CHAIN_NONE`|Łańcuch wywołań, nie został zainicjowany.|  
|`CHAIN_CLASS_INIT`|Ciąg został zainicjowany przez Konstruktor.|  
|`CHAIN_EXCEPTION_FILTER`|Łańcuch zostało zainicjowane przez filtra wyjątku.|  
|`CHAIN_SECURITY`|Łańcuch zostało zainicjowane przez kod, który wymusza stosowanie zabezpieczeń.|  
|`CHAIN_CONTEXT_POLICY`|Łańcuch zostało zainicjowane przez zasadę kontekstu.|  
|`CHAIN_INTERCEPTION`|Nie używany.|  
|`CHAIN_PROCESS_START`|Nie używany.|  
|`CHAIN_THREAD_START`|Łańcuch zostało zainicjowane przez rozpoczęciem wykonywaniem wątków.|  
|`CHAIN_ENTER_MANAGED`|Łańcuch zostało zainicjowane przez wejścia w kodzie zarządzanym.|  
|`CHAIN_ENTER_UNMANAGED`|Łańcuch zostało zainicjowane przez wejścia w niezarządzanym kodzie.|  
|`CHAIN_DEBUGGER_EVAL`|Nie używany.|  
|`CHAIN_CONTEXT_SWITCH`|Nie używany.|  
|`CHAIN_FUNC_EVAL`|Łańcuch zostało zainicjowane przez Obliczanie funkcji.|  
  
## <a name="remarks"></a>Uwagi  
 Użyj [ICorDebugChain::GetReason](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md) metodę, aby ustalić przyczyny do rozpoczęcia łańcuch wywołań.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** CorDebug.idl, CorDebug.h  
  
 **Biblioteka:** CorGuids.lib  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Debugowanie, wyliczenia](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
