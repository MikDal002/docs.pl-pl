---
title: ICLRPolicyManager — Interfejs
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfce4276c651e5cb6ed20bd2616b68294e49da8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629154"
---
# <a name="iclrpolicymanager-interface"></a>ICLRPolicyManager — Interfejs
Udostępnia metody, które umożliwiają hosta określić zasady działań podejmowanych w przypadku awarii lub przekroczenia limitu czasu.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[SetActionOnFailure, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|Określa akcję zasad, których środowisko uruchomieniowe języka wspólnego (CLR) powinna wykonać, gdy wystąpi awaria określonej.|  
|[SetActionOnTimeout, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|Określa akcję zasady, którą środowisko CLR powinna wykonać, gdy upłynie limit czasu określonej operacji.|  
|[SetDefaultAction, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|Określa akcję zasady, którą środowisko CLR powinna wykonać, gdy występuje określonej operacji.|  
|[SetTimeout, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|Ustawia wartość limitu czasu dla określonej operacji.|  
|[SetTimeoutAndAction, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|Ustawia wartość limitu czasu dla określonej operacji i określa akcję zasady, którą środowisko CLR powinna wykonać, gdy operacja jest wykonywana.|  
|[SetUnhandledExceptionPolicy, metoda](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Określa zachowanie środowiska CLR, po wystąpieniu nieobsługiwanego wyjątku.|  
  
## <a name="requirements"></a>Wymagania  
 **Platformy:** Zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Nagłówek:** MSCorEE.h  
  
 **Biblioteka:** Dołączony jako zasób w MSCorEE.dll  
  
 **Wersje programu .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także
- [EClrFailure, wyliczenie](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [EClrOperation, wyliczenie](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [EPolicyAction, wyliczenie](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [ICLRControl, interfejs](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
