---
title: Niestandardowe poświadczenia i walidacja poświadczeń
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 731131d4bc967aa3ae95eca1f9e9cbb2770f8f7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746573"
---
# <a name="custom-credential-and-credential-validation"></a>Niestandardowe poświadczenia i walidacja poświadczeń
Zabezpieczenia w Windows Communication Foundation (WCF) opiera się na wymianie poświadczeń między usług i klientów. Większość scenariuszy zabezpieczeń mogą zostać zrealizowane przy użyciu popularnych typów poświadczeń, takich jak Windows (Kerberos), nazwę użytkownika i hasła oraz certyfikatów. Jednak jeśli wymagany jest nowy typ poświadczeń, tematy w tej sekcji wyjaśniono, jak obsługiwać i Zweryfikuj nowe typy.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Instrukcje: Tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Opis sposobu dostosowywania WCF weryfikacji przez dziedziczenie z <xref:System.IdentityModel.Selectors.X509CertificateValidator> klasy.  
  
 [Przewodnik: Tworzenie niestandardowego klienta i poświadczeń usługi](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Pokazuje, jak rozszerzyć <xref:System.ServiceModel.Description.ClientCredentials> i <xref:System.ServiceModel.Description.ServiceCredentials> klasy w celu uwzględnienia nowych poświadczeń typów. To jest pierwszy w szeregu tematów, które umożliwiają tworzenie typów niestandardowych poświadczeń.  
  
 [Instrukcje: Tworzenie niestandardowego dostawcy tokenów zabezpieczeń](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Wyjaśnia, jak utworzyć dostawcę tokenu zabezpieczającego, aby obsługiwać nowe typy poświadczeń i wrócić nowych tokenów dla poświadczenia. Jest to drugi tematu w serii.  
  
 [Instrukcje: Tworzenie wystawcy uwierzytelniania tokenu zabezpieczeń niestandardowych](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 Omówiono tworzenie niestandardowego wystawcy uwierzytelniania na nowy typ poświadczeń uwierzytelniania. Jest to trzeci tematu w serii.  
  
## <a name="reference"></a>Tematy pomocy  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Uwierzytelnianie](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Federacja i wystawione tokeny](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Autoryzacja](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>Zobacz także
- [Zabezpieczenia](../../../../docs/framework/wcf/feature-details/security.md)
