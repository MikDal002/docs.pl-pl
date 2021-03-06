---
title: PreBindAssemblyEx — Funkcja
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea34c4087014091b92d6227177a2f08209cc2e10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570882"
---
# <a name="prebindassemblyex-function"></a>PreBindAssemblyEx — Funkcja
Pobiera nazwę wyświetlaną po zastosowaniu zasad dla zestawu.  
  
 Ta funkcja obsługuje infrastrukturę .NET Framework i nie jest przeznaczona do użycia bezpośrednio w kodzie.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAppCtx`  
 [in] Identyfikuje kontekst aplikacji.  
  
 `pName`  
 [in] Określa nazwę zestawu.  
  
 `pAsmParent`  
 [in] Identyfikuje zestaw nadrzędnej. Ten parametr jest ignorowany.  
  
 `pwzRuntimeVersion`  
 [in] Określa wersję środowiska uruchomieniowego.  
  
 `ppNamePostPolicy`  
 [out] Zawiera nazwę wyświetlaną po zastosowaniu zasad.  
  
 `pvReserved`  
 [in] Zarezerwowane dla przyszłej rozszerzalności. `pvReserved` musi być odwołanie o wartości null.  
  
## <a name="remarks"></a>Uwagi  
 `ppNamePostPolicy` Parametr wyjściowy jest ustawiona tylko wtedy, gdy funkcja zwraca wartość HRESULT FUSION_E_REF_DEF_MISMATCH. W przeciwnym razie ma wartość null.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion.h  
  
 **Biblioteka:** Dołączony jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Łączenie statycznych funkcji globalnych](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
