---
title: <appDomainResourceMonitoring>, element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainResourceMonitoring element
- <appDomainResourceMonitoring> element
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d085fe8b9cf11e2f195468a93b3fa9b3f0817503
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286562"
---
# <a name="appdomainresourcemonitoring-element"></a>\<appDomainResourceMonitoring> Element
Powoduje, że środowisko uruchomieniowe w celu zbierania statystyk na wszystkie domeny aplikacji, w trakcie trwania procesu.  
  
 \<Konfiguracja >  
\<runtime>  
\<appDomainResourceMonitoring>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`enabled`|Atrybut wymagany.<br /><br /> Określa, czy środowisko uruchomieniowe zbiera statystyki dotyczące monitorowania zasobów domen aplikacji.|  
  
## <a name="enabled-attribute"></a>Atrybut włączony  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`true`|Monitorowanie zasobów domeny aplikacji statystyki są zbierane.|  
|`false`|Statystyki dotyczące monitorowanie zasobów domeny aplikacji nie są zbierane.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|`configuration`|Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.|  
|`runtime`|Zawiera informacje dotyczące powiązania zestawu oraz wyrzucania elementów bezużytecznych.|  
  
## <a name="remarks"></a>Uwagi  
 Monitorowanie zasobów domeny aplikacji jest dostępna za pośrednictwem klasy domeny zarządzanej aplikacji, hostingu [ICLRAppDomainResourceMonitor](../../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) interfejsu i śledzenie zdarzeń dla Windows (ETW). Gdy jest włączone monitorowanie, statystyki są zbierane dla wszystkich domen aplikacji w trakcie trwania procesu.  
  
 Aby włączyć monitorowanie z kodu zarządzanego, należy użyć <xref:System.AppDomain.MonitoringIsEnabled%2A> właściwości.  
  
 Ten element konfiguracji jest dostępny tylko w [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] i nowszych.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak umożliwić monitorowanie zasobów domeny aplikacji.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>
- [Schemat ustawień środowiska uruchomieniowego](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Schemat pliku konfiguracji](../../../../../docs/framework/configure-apps/file-schema/index.md)
