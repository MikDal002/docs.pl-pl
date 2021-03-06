---
title: 'Środki zaradcze: Usługi WCF i uwierzytelnianie certyfikatu'
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc2e80a050e3b2e14663ba4bb67f650a16a6c619
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738316"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a>Środki zaradcze: Usługi WCF i uwierzytelnianie certyfikatu
.NET Framework 4.6 dodaje protokołu TLS 1.1 i TLS 1.2, do listy domyślnych protokołu SSL usługi WCF. Gdy zarówno klienta, jak i serwera zainstalować program .NET Framework 4.6 lub nowszy, protokołu TLS 1.2 jest używana do negocjacji.  
  
## <a name="impact"></a>Wpływ  
 Protokół TLS 1.2 nie obsługuje uwierzytelnianie certyfikatu MD5. W rezultacie jeśli klient używa certyfikatu SSL, który używa algorytmu wyznaczania wartości skrótu MD5, klient WCF nie uda się nawiązać usługi WCF. Aby uzyskać więcej informacji, zobacz [środki zaradcze: Usługi WCF i uwierzytelnianie certyfikatu](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).  
  
## <a name="mitigation"></a>Ograniczenie  
 Ten problem można obejść, czemu klienta programu WCF można nawiązywać połączenia z serwerem usługi WCF, wykonując następujące czynności:  
  
-   Zaktualizuj certyfikat, aby nie używać algorytmu MD5. Jest to zalecane rozwiązanie.  
  
-   Jeśli dynamicznie powiązanie nie jest skonfigurowany w kodzie źródłowym, należy zaktualizować plik konfiguracji aplikacji do używania protokołu TLS 1.1 lub wcześniejszej wersji protokołu. Dzięki temu można w dalszym ciągu używać certyfikatu przy użyciu algorytmu wyznaczania wartości skrótu MD5.  
  
    > [!CAUTION]
    >  To rozwiązanie nie jest zalecane, ponieważ certyfikat przy użyciu algorytmu wyznaczania wartości skrótu MD5 jest uznawany za niebezpieczne.  
  
     Następujący plik konfiguracji ma następujące efekty:  
  
    ```xml  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding>  
                        <security mode= "None|Transport|Message|TransportWithMessageCredential" >  
                            <transport clientCredentialType="None|Windows|Certificate"  
                                                protectionLevel="None|Sign|EncryptAndSign"  
                                                sslProtocols="Ssl3|Tls1|Tls11">  
                            </transport>  
                        </security>  
                    </binding>  
                </netTcpBinding>  
            </bindings>  
        </system.ServiceModel>  
    </configuration>  
    ```  
  
-   Jeśli wiązanie dynamiczne jest skonfigurowany w kodzie źródłowym, należy zaktualizować <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> właściwości, aby korzystała z protokołu TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) lub starszej wersji protokołu w kodzie źródłowym.  
  
    > [!CAUTION]
    >  To rozwiązanie nie jest zalecane, ponieważ certyfikat przy użyciu algorytmu wyznaczania wartości skrótu MD5 jest uznawany za niebezpieczne.  
  
## <a name="see-also"></a>Zobacz także
- [Zmiany środowiska uruchomieniowego](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
