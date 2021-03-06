---
title: _CorDllMain — Funkcja
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f62ad2c9ec6e1c9672ac5c78e838e926b02359f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512375"
---
# <a name="cordllmain-function"></a>_CorDllMain — Funkcja
Inicjuje środowisko uruchomieniowe języka wspólnego (CLR), lokalizuje zarządzany punkt wejścia w nagłówku CLR zestawu biblioteki DLL i rozpoczyna wykonywanie.  
  
## <a name="syntax"></a>Składnia  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `hInst`  
 [in] Uchwyt wystąpienia załadowanym module.  
  
 `dwReason`  
 [in] Wskazuje, dlaczego jest wywoływana funkcja punktu wejścia biblioteki DLL. Ten parametr może być jedną z następujących wartości: DLL_PROCESS_ATTACH DLL_THREAD_ATTACH, DLL_THREAD_ATTACH lub komunikat DLL_PROCESS_DETACH. Aby uzyskać opis tych wartości, zobacz `DllMain` dokumentacji w zestawie SDK platformy.  
  
 `lpReserved`  
 [in] Nieużywane.  
  
## <a name="return-value"></a>Wartość zwracana  
 Ta metoda zwraca `true` w celu osiągnięcia sukcesu i `false` w przypadku wystąpienia błędu.  
  
## <a name="remarks"></a>Uwagi  
 Ta funkcja jest wywoływana przez program ładujący systemu operacyjnego dla zestawów DLL. Dla pliku wykonywalnego zestawów wywołuje moduł ładujący [_corexemain —](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) zamiast tego funkcji.  
  
 Program ładujący systemu operacyjnego wywołuje tę metodę, niezależnie od tego punktu wejścia, określone w pliku DLL.  
  
 W Windows 98, Windows ME, Windows NT i Windows 2000 `_CorDllMain` funkcja jest wywoływana, pośrednio za pośrednictwem fixupin program ładujący systemu operacyjnego. We wszystkich innych wersjach systemu Windows jest wywoływana bezpośrednio przez program ładujący systemu operacyjnego.  
  
 Aby uzyskać dodatkowe informacje, zobacz sekcję Uwagi w [_corvalidateimage —](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tematu.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** COR.h  
  
 **Biblioteka:** Dołączony jako zasób w MsCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [Statyczne funkcje globalne metadanych](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
