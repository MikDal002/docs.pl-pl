---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: eb7ff953fcb61232fad16a99ac80cb98dbd83186
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259972"
---
# <a name="msmqtransportsecurity"></a>\<msmqTransportSecurity>
Określa ustawienia zabezpieczenia transportu MSMQ dla niestandardowego powiązania.  
  
 \<system.serviceModel>  
\<powiązania >  
\<customBinding>  
\<Powiązanie >  
\<msmqIntegration>  
\<msmqTransportSecurity>  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
  
|Atrybut|Opis|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|Określa, jak wiadomość musi zostać uwierzytelniony przez usługę transportową MSMQ. Jeśli jest ono ustawione na `None`, wartość `msmqProtectionLevel` atrybut również musi być ustawiona na `None`.<br /><br /> Prawidłowe wartości są następujące:<br /><br /> -Brak: Bez uwierzytelniania.<br />-Windows: Mechanizm uwierzytelniania używa usługi Active Directory, aby uzyskać certyfikat X.509, identyfikator SID skojarzone z wiadomością. Następnie służy do Sprawdź, czy lista ACL kolejki, aby upewnić się, użytkownik ma uprawnienia do zapisu do kolejki.<br />-Certyfikat: Kanał uzyskuje certyfikat z magazynu certyfikatów.<br /><br /> Wartość domyślna to Windows. Ten atrybut jest typu <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Określa algorytm używany do szyfrowania wiadomości na łączu podczas transferu wiadomości między menedżerami kolejki wiadomości. Prawidłowe wartości są następujące:<br /><br /> -RC4Stream<br />-AES<br /><br /> Wartość domyślna to RC4Stream. Ten atrybut jest typu <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Określa, w jaki sposób wiadomość jest zabezpieczona na poziomie usługi transportu MSMQ. Szyfrowanie zapewnia integralność wiadomości, podczas gdy EncryptAndSign zapewnia integralność komunikatów i uznawania; oznacza to w rzeczywistości pochodzą od nadawcy i informacje o nadawcy mają który mówi, że jest on. Prawidłowe wartości są następujące:<br /><br /> -Brak: Brak ochrony.<br />— Logowanie: Komunikaty są podpisane.<br />-EncryptAndSign: Komunikaty są szyfrowane i podpisany.<br /><br /> Wartość domyślna to znak. Ten atrybut jest typu <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Określa algorytm, który ma być używany w obliczeniu skrótu jako części podpisów. Prawidłowe wartości są następujące:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Wartość domyślna to SHA1. Ten atrybut jest typu <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[\<msmqIntegration>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|Określa ustawienia wymagane w celu interakcji z usługi kolejkowania komunikatów (MSMQ) nadawcy i adresata.|  
|[\<msmqTransport>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|Określa kolejkowania właściwości komunikacji usługi Windows Communication Foundation (WCF), który korzysta z natywnego protokołu usługi MSMQ.|  
  
## <a name="remarks"></a>Uwagi  
 Aby uzyskać więcej informacji na temat zabezpieczeń transportu, zobacz [Transport Security](../../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Kolejki programu WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [Transporty](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Wybieranie transportu](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Powiązania](../../../../../docs/framework/wcf/bindings.md)
- [Rozszerzanie powiązań](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Powiązania niestandardowe](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [Zabezpieczenia transportu](../../../../../docs/framework/wcf/feature-details/transport-security.md)
