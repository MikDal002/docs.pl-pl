---
title: "ICLRHostBindingPolicyManager::ModifyApplicationPolicy — Metoda"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.ModifyApplicationPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::ModifyApplicationPolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::ModifyApplicationPolicy method [.NET Framework hosting]
- ModifyApplicationPolicy method [.NET Framework hosting]
ms.assetid: d82d633e-cce6-427c-8b02-8227e34e12ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 51775f52e34f35d8ef9f3a8533363be73e9bd7c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="iclrhostbindingpolicymanagermodifyapplicationpolicy-method"></a>ICLRHostBindingPolicyManager::ModifyApplicationPolicy — Metoda
Modyfikuje zasady powiązanie dla określonego zestawu i tworzy nową wersję zasad.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT  ModifyApplicationPolicy (  
    [in] LPCWSTR     pwzSourceAssemblyIdentity,   
    [in] LPCWSTR     pwzTargetAssemblyIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [in] DWORD       dwPolicyModifyFlags,  
    [out, size_is(*pcbNewAppPolicySize)] BYTE *pbNewApplicationPolicy,   
    [in, out] DWORD *pcbNewAppPolicySize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pwzSourceAssemblyIdentity`  
 [in] Tożsamość zestawu do zmodyfikowania.  
  
 `pwzTargetAssemblyIdentity`  
 [in] Nową tożsamość zestawu zmodyfikowane.  
  
 `pbApplicationPolicy`  
 [in] Wskaźnik do buforu, który zawiera dane zasad powiązania dla zestawu do zmodyfikowania.  
  
 `cbAppPolicySize`  
 [in] Rozmiar powiązania zasady mają zostać zastąpione.  
  
 `dwPolicyModifyFlags`  
 [in] Logiczne połączenie lub [EHostBindingPolicyModifyFlags](../../../../docs/framework/unmanaged-api/hosting/ehostbindingpolicymodifyflags-enumeration.md) wartości, wskazując kontroli przekierowania.  
  
 `pbNewApplicationPolicy`  
 [out] Wskaźnik do buforu, który zawiera nowe powiązanie danych zasad.  
  
 `pcbNewAppPolicySize`  
 [w, out] Wskaźnik do rozmiaru buforu nowych zasad powiązania.  
  
## <a name="return-value"></a>Wartość zwracana  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Zasada została pomyślnie zmodyfikowana.|  
|E_INVALIDARG|`pwzSourceAssemblyIdentity`lub `pwzTargetAssemblyIdentity` miał odwołanie o wartości null.|  
|ERROR_INSUFFICIENT_BUFFER|`pbNewApplicationPolicy`jest za mały.|  
|HOST_E_CLRNOTAVAILABLE|Środowisko uruchomieniowe języka wspólnego (CLR) nie został załadowany do procesu lub CLR jest w stanie, w którym nie można uruchamiać kodu zarządzanego lub pomyślnie przetworzyć wywołania.|  
|HOST_E_TIMEOUT|Upłynął limit czasu wywołania.|  
|HOST_E_NOT_OWNER|Obiekt wywołujący nie jest właścicielem blokady.|  
|HOST_E_ABANDONED|Zdarzenie zostało anulowane podczas zablokowanych wątku lub włókna oczekiwał na nim.|  
|E_FAIL|Wystąpił nieznany błąd krytyczny. Po powrocie z metody E_FAIL CLR nie jest już możliwe w ramach procesu. Kolejne wywołania metody hosting zwracać HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Uwagi  
 `ModifyApplicationPolicy` Metodę można wywołać dwa razy. Pierwsze wywołanie należy podać wartość null dla `pbNewApplicationPolicy` parametru. To wywołanie, którą będzie zwracać z wartością niezbędne dla `pcbNewAppPolicySize`. Drugie wywołanie należy podać tę wartość dla `pcbNewAppPolicySize`, a następnie wskaż bufor tego rozmiaru dla `pbNewApplicationPolicy`.  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** uwzględnione jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz też  
 [ICLRHostBindingPolicyManager — interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)