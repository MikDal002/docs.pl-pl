---
title: <exposedMethod>
ms.date: 03/30/2017
ms.assetid: 61c938cd-4ee9-4b06-ab28-922ef491ab11
ms.openlocfilehash: 151929cd99df08b705bee94eb6fd6f10c254a660
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259855"
---
# <a name="exposedmethod"></a>\<exposedMethod>
Reprezentuje metodę COM +, która jest widoczna gdy interfejs składnika COM + jest widoczny jako usługi sieci Web.  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract>  
\<metody >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<comContracts>
  <comContract>
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|nazwa|Ciąg, który zawiera metodę COM +, która jest widoczna gdy interfejs składnika COM + jest widoczny jako usługi sieci Web.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<exposedMethods>](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethods.md)|Kolekcja [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementów.|  
  
## <a name="remarks"></a>Uwagi  
 COM + integracja narzędzie konfiguracji (ComSvcConfig.exe) może służyć do dodawania konkretnych metod z interfejsem COM żeby pojawiły się na kontrakt usługi wygenerowany.  
  
 Na przykład służy następujące polecenie do dodania trzy metody o nazwie z `IFinances` interfejsu COM na `ItemOrders`. Składnik finansowych umową serwisową wygenerowany.  
  
 `ComSvcConfig.exe /i /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{TransferFunds,AddFunds,RemoveFunds} /hosting:complus`  
  
 Po uruchomieniu również ComSvcConfig.exe, następnie generuje następujące kontraktu usługi, wyświetlanie listy opisanych powyżej metod jako [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementów.  
  
```xml  
<comContract contractType="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"
             name="IFinances"
             namespace="http://contoso.com/services/financial">
  <exposedMethod name="TransferFunds"/>
  <exposedMethod name="AddFunds"/>
  <exposedMethod name="RemoveFunds"/>
</comContract>
```  
  
 Podczas inicjowania usługi, środowisko uruchomieniowe spróbuje go wygenerować kontraktu usługi odzwierciedlający za pośrednictwem i dodając tylko te metody, które są uwzględnione na liście [ \<exposedMethod >](../../../../../docs/framework/configure-apps/file-schema/wcf/exposedmethod.md) elementów. Śledzenie jest tworzony dla każdej metody interfejsu, który nie znajduje się na kontrakt usługi.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.ServiceModel.Configuration.ComMethodElementCollection>
- <xref:System.ServiceModel.Configuration.ComMethodElement>
- [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Współdziałanie z aplikacjami COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Instrukcje: Konfigurowanie ustawień usługi COM +](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
