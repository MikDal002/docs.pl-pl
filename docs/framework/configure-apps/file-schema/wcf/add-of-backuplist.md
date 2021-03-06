---
title: <add> z <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: e61ee275a7e98f13370504f5f15fdbe62a8221bd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285795"
---
# <a name="add-of-backuplist"></a>\<Dodaj > z \<backupList >
Reprezentuje element konfiguracji, który definiuje element kopii zapasowej punktu końcowego.  
  
 \<system.serviceModel>  
\<Routing >  
\<backupLists>  
\<backupList>  
\<add>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|nazwa|Ciąg, który określa nazwę punktu końcowego, tworzenia kopii zapasowej.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Zawiera listę punktów końcowych, które chcesz, aby usługa routingu do użycia w przypadku, gdy nie można nawiązać połączenia z podstawowego punktu końcowego.|  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
