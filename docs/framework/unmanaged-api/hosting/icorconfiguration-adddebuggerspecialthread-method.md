---
title: ICorConfiguration::AddDebuggerSpecialThread — Metoda
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca33c8eb5e214cdaaa49905c311fd62042285d4f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569296"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a>ICorConfiguration::AddDebuggerSpecialThread — Metoda
Do debugowania usług wskazuje, że określonego wątku powinny mieć możliwość kontynuowania wykonywania, gdy debuger został zatrzymany w zarządzanych lub niezarządzanych scenariusze debugowania aplikacji.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwSpecialThreadId`  
 [in] Identyfikator wątku, który powinien być dozwolony kontynuowania wykonywania.  
  
## <a name="remarks"></a>Uwagi  
 Do uruchomienia kodu zarządzanego, lub wprowadź środowiska uruchomieniowego w żaden sposób nie będzie można określonego wątku. Przykładem takiego wątku może być wątek w trakcie obsługi debugery starszej wersji skryptu.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** Dołączony jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [ICorConfiguration, interfejs](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
