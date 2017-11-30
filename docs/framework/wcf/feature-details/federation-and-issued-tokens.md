---
title: Federacja i wystawione tokeny
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: aa3ed1b68cab19b0464067a2dc8f52be03279f5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="868c6-102">Federacja i wystawione tokeny</span><span class="sxs-lookup"><span data-stu-id="868c6-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="868c6-103">Z [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], Utwórz klientów komunikujących się bezpiecznie z usługami, które implementują specyfikacji WS-Federation i WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="868c6-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="868c6-104">Specyfikacje umożliwia XML, SOAP i Web Services Description Language (WSDL) zapewniają mechanizmy, które włączyć uwierzytelnianie i autoryzację w obszarach różnych zaufania.</span><span class="sxs-lookup"><span data-stu-id="868c6-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="868c6-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="868c6-105">In This Section</span></span>  
 [<span data-ttu-id="868c6-106">Federacyjna</span><span class="sxs-lookup"><span data-stu-id="868c6-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="868c6-107">Zawiera omówienie federacji.</span><span class="sxs-lookup"><span data-stu-id="868c6-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="868c6-108">Federacja i zaufanie</span><span class="sxs-lookup"><span data-stu-id="868c6-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="868c6-109">Wyświetla listę problemów projektu pod uwagę podczas tworzenia federacyjnych, usług lub klientów.</span><span class="sxs-lookup"><span data-stu-id="868c6-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="868c6-110">Porady: Tworzenie klienta federacyjnego</span><span class="sxs-lookup"><span data-stu-id="868c6-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="868c6-111">W tym artykule opisano tworzenie klienta federacyjnego z [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="868c6-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="868c6-112">Porady: Konfigurowanie poświadczeń usługi federacyjnej</span><span class="sxs-lookup"><span data-stu-id="868c6-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="868c6-113">W tym artykule opisano kroki tworzenia usługi federacyjnej.</span><span class="sxs-lookup"><span data-stu-id="868c6-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="868c6-114">Porady: tworzenie WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="868c6-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="868c6-115">Opisuje sposób skonfigurować klientów i usługi używające `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="868c6-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="868c6-116">Porady: Tworzenie usługi tokenów zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="868c6-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="868c6-117">W tym artykule opisano kroki tworzenia usługi tokenu zabezpieczającego.</span><span class="sxs-lookup"><span data-stu-id="868c6-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="868c6-118">Zabezpieczenia potwierdzenia Markup Language (SAML) tokenów i oświadczeń</span><span class="sxs-lookup"><span data-stu-id="868c6-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="868c6-119">Opisuje tokenów zabezpieczeń potwierdzenia Markup Language (SAML), które można rozszerzać i włączyć funkcję do tworzenia zaawansowanych typów oświadczeń.</span><span class="sxs-lookup"><span data-stu-id="868c6-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="868c6-120">Porady: Konfigurowanie lokalnego wystawcy</span><span class="sxs-lookup"><span data-stu-id="868c6-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="868c6-121">Opisuje sposób tworzenia lokalnego wystawcy tokenów zabezpieczających.</span><span class="sxs-lookup"><span data-stu-id="868c6-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="868c6-122">Porady: wyłączanie bezpiecznej sesji przy użyciu klasy WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="868c6-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="868c6-123">Opisuje sposób wyłączania bezpiecznej sesji na `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="868c6-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="868c6-124">Wyłączanie bezpiecznej sesji jest niezbędne, podczas tworzenia kolektywu serwerów sieci Web, która wymaga sesji dla każdego klienta.</span><span class="sxs-lookup"><span data-stu-id="868c6-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="868c6-125">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="868c6-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="868c6-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="868c6-126">See Also</span></span>  
 [<span data-ttu-id="868c6-127">Autoryzacji</span><span class="sxs-lookup"><span data-stu-id="868c6-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="868c6-128">Tokeny niestandardowe</span><span class="sxs-lookup"><span data-stu-id="868c6-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="868c6-129">Model zabezpieczeń systemu Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="868c6-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)