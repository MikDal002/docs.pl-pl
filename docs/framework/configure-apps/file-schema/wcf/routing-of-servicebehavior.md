---
title: <routing> z <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 3f23cbb45aa72b1aae18c845e68b426a4214d499
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261779"
---
# <a name="routing-of-servicebehavior"></a>\<Routing > z \<serviceBehavior >
Udostępnia wykonawczej usługa routingu umożliwia dynamiczne modyfikowanie konfiguracji routingu.  
  
 \<system.ServiceModel>  
\<zachowania >  
\<serviceBehaviors>  
\<zachowanie >  
\<Routing >  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|filterTable|Ciąg określający nazwę tabeli routingu, który zawiera filtry, które mogło zostać ocenione przez usługę routingu. Ta wartość musi odpowiadać `name` atrybutu [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) sekcji.|  
|routeOnHeaderOnly|Wartość logiczna określająca, czy filtr zbada zarówno treści komunikatu i nagłówka lub tylko nagłówek. Wartość domyślna to `true`.|  
|soapProcessingEnabled|Wartość logiczna określająca, czy powinny być wykonywane przetwarzanie protokołu SOAP.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<zachowanie >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Określa zachowanie elementu.|  
  
## <a name="remarks"></a>Uwagi  
 Po dodaniu do konfiguracji zachowania usługi, ten element konfiguracji umożliwia routingu dla usługi. Możesz określić rzeczywistego tabeli routingu do użycia przez usługę, w tym elemencie.  
  
 Korzystając z tej sekcji konfiguracji, można zmienić ustawienia routingu na bieżąco po zmianie deseń wdrożenia. W czasie wykonywania można zarejestrować rozszerzenia routingu z nowymi ustawieniami routingu i usługa routingu rozpocznie się za pomocą informacji zaktualizowanej konfiguracji dla nowych komunikatów i sesje, przy równoczesnym zachowaniu aktywne komunikaty/sesji przy użyciu dowolne reguły były w miejsce, w momencie rozpoczęcia pracy.  Daje możliwość robienia bezpiecznej sesji, odtwarzanie bez ponownej konfiguracji usługi routingu podczas wykonywania.  
  
