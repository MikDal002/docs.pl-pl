---
title: <add> — Element dla connectionManagement (Ustawienia sieci)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: a7a4cfe952a32c859a113f0903696fec3681f800
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267633"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a>\<Dodaj >, Element dla connectionManagement (ustawienia sieci)
Dodaje adres IP lub nazwę DNS na liście zarządzania połączenia.  
  
 \<Konfiguracja >  
\<system.net>  
\<connectionManagement>  
\<add>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<add   
  address="address expression"   
  maxconnection="integer"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|**Atrybut**|**Opis**|  
|-------------------|---------------------|  
|`address`|Ciąg opisujący adresu IP lub nazwy DNS.|  
|`maxconnection`|Maksymalna liczba dozwolonych połączeń z serwerem. Jeśli nie zostanie podany, wartość domyślna to 2.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|**Element**|**Opis**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Określa maksymalną liczbę połączeń z hostem sieci.|  
  
## <a name="remarks"></a>Uwagi  
 Wartość `address` atrybut powinien być gwiazdki, aby pokazać wszystkie połączenia lub ciąg w postaci `<schema>://<idn_hostname>[:<port>]`.  
  
 Jeśli identyfikator URI przekazywany do żadnych interfejsów API protokołu HTTP zawiera Unicode, zostaną przekonwertowane nazwę wewnętrznie za pomocą <xref:System.Uri.DnsSafeHost%2A> której może zwrócić ciąg punicode (zachowanie zależy od bieżącej konfiguracji IDN).  
  
## <a name="configuration-files"></a>Pliki konfiguracji  
 Ten element może być użyty w pliku konfiguracji aplikacji lub w pliku konfiguracji komputera (Machine.config).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład umożliwia skonfigurowanie aplikacji na używanie cztery połączenia z serwerem `www.contoso.com` i dwóch połączeń na inne serwery.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Schemat ustawień sieci](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
