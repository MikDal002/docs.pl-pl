---
title: WAITORTIMERCALLBACK — Wskaźnik funkcji
ms.date: 03/30/2017
api_name:
- WAITORTIMERCALLBACK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAITORTIMERCALLBACK
helpviewer_keywords:
- WAITORTIMERCALLBACK function pointer [.NET Framework hosting]
ms.assetid: 1fec4aef-0a06-4df0-bae7-d31a9ef9603d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d36ae3ef63c1324f77786ad55674bbdc257d984
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607137"
---
# <a name="waitortimercallback-function-pointer"></a>WAITORTIMERCALLBACK — Wskaźnik funkcji
Wskazuje funkcję, która powiadamia hosta, którego obsługa oczekiwania (<xref:System.Threading.WaitHandle>) zostały zasygnalizowane lub przekroczyło limit czasu.  
  
 Ten wskaźnik funkcji jest przestarzała w [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
## <a name="syntax"></a>Składnia  
  
```  
typedef VOID (__stdcall *WAITORTIMERCALLBACK) (  
    [in] PVOID lpParameter,  
    [in] BOOL  TimerOrWaitFired  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `lpParameter`  
 [in] Wskaźnik do obiektu, który zawiera informacje o zdefiniowanym przez hosta.  
  
 `TimerOrWaitFired`  
 [in] `true` Jeśli dojście oczekiwania upłynął limit czasu, lub `false` Jeśli został on zasygnalizowane.  
  
## <a name="remarks"></a>Uwagi  
 Funkcja, do którego `WAITORTIMERCALLBACK` punktów jest funkcją wywołania zwrotnego i musi być implementowana przez moduł zapisujący aplikacji macierzystej.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** MSCorWks.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Przestarzałe funkcje hostingu środowiska CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
