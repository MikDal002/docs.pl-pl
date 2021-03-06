---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 7a091ecfbc0f4773ece620f93a9f21c219fcccb6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256707"
---
# <a name="serviceactivations"></a>\<serviceActivations>
Element konfiguracji, który pozwala Tobie dodać ustawienia, które definiują ustawienia aktywacji usług wirtualnych mapowane odpowiadają typom usług Windows Communication Foundation (WCF). Dzięki temu można aktywować usługi hostowane w WAS / IIS bez pliku .svc.  
  
 \<system.ServiceModel>  
\<serviceHostingEnvironment>  
\<serviceActivations>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-serviceactivations.md)|Dodaje element konfiguracji, który określa aktywacji aplikacji usługi.|  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Definiuje typ, który usługę hostingu środowiskowego dla danego transportu.|  
  
## <a name="remarks"></a>Uwagi  
 Poniższy przykład pokazuje, jak skonfigurować ustawienia aktywacji w pliku web.config.  
  
```xml  
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```  
  
 Za pomocą tej konfiguracji, możesz aktywować GreetingService bez użycia pliku .svc.  
  
 Należy pamiętać, że `<serviceHostingEnvironment>` jest konfiguracji na poziomie aplikacji. Musisz umieszczać `web.config` zawierający konfigurację w katalogu głównym aplikacji wirtualnej. Ponadto `serviceHostingEnvironment` to sekcja dziedziczne machinetoApplication. Jeśli zarejestrujesz jednej usługi w katalogu głównym maszyny do każdej usługi w aplikacji będą dziedziczyć tę usługę.  
  
 Aktywacja oparta na konfiguracji obsługuje aktywacji za pośrednictwem protokołu http i innych niż http. Wymaga rozszerzenia w relatativeAddress, czyli .svc xoml oraz .xamlx. Własne rozszerzenia można zamapować na buildProviders wie, który następnie umożliwi Aktywuj usługę za pośrednictwem dowolnego rozszerzenia. Po konfliktu `<serviceActivations>` sekcji zastępuje .svc rejestracji.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
