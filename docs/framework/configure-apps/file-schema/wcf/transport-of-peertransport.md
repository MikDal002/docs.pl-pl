---
title: <transport> z <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3dbeda5d418c30f378515fa83979eaca289370f9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284014"
---
# <a name="transport-of-peertransport"></a>\<transport > z \<peerTransport >
Określa typ transportu dla zabezpieczonych wiadomości wysłanych przez elementy równorzędne skonfigurowany tym wiązaniem.  
  
 \<system.serviceModel>  
\<powiązania >  
\<customBinding>  
\<Powiązanie >  
\<peerTransport>  
\<security>  
\<transport>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|credentialType|Opcjonalna. Określa typ poświadczenia używane do weryfikowania komunikaty wysyłane za pomocą transportu elementu równorzędnego. Ten atrybut jest typu <xref:System.ServiceModel.PeerTransportCredentialType>.|  
  
## <a name="credentialtype-attribute"></a>credentialType Attribute  
  
|Wartość|Opis|  
|-----------|-----------------|  
|Certyfikat|Uwierzytelnianie transportu kanał elementu równorzędnego wymaga X509 certyfikatu.|  
|Hasło|Uwierzytelnianie transportu kanał elementu równorzędnego wymaga prawidłowego hasła.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<Zabezpieczenia >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|Definiuje ustawienia zabezpieczeń transport elementu równorzędnego.|  
  
## <a name="remarks"></a>Uwagi  
 Ten element jest ustawiona tylko wtedy, gdy atrybut tryb [ \<zabezpieczeń >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md) ustawiono `Transport` lub `TransportWithMessageCredential`.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Zabezpieczenia transportu](../../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Transporty](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Wybieranie transportu](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Powiązania](../../../../../docs/framework/wcf/bindings.md)
- [Rozszerzanie powiązań](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Powiązania niestandardowe](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
