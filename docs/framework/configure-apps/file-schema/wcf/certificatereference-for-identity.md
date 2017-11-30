---
title: '&lt;certificateReference&gt; w &lt;identity&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac359c65-c22d-42d2-97de-db53b77cebdb
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 883ae318e32493013f009f3580ef102e4d39b3e0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificatereferencegt-for-ltidentitygt"></a><span data-ttu-id="a02be-102">&lt;certificateReference&gt; w &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="a02be-102">&lt;certificateReference&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="a02be-103">Określa ustawienia dla walidacji certyfikatu X.509.</span><span class="sxs-lookup"><span data-stu-id="a02be-103">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="a02be-104">Bezpieczny [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] klient łączący punkt końcowy o tej tożsamości weryfikuje czy wnioski przedstawione przez serwer zawierają oświadczeń tożsamości użyta do skonstruowania tej tożsamości.</span><span class="sxs-lookup"><span data-stu-id="a02be-104">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity verifies that the claims presented by the server contain the identity claim used to construct this identity.</span></span>  
  
 <span data-ttu-id="a02be-105">\<tożsamość ></span><span class="sxs-lookup"><span data-stu-id="a02be-105">\<identity></span></span>  
<span data-ttu-id="a02be-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="a02be-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a02be-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="a02be-107">Syntax</span></span>  
  
```xml  
<certificateReference   
        findValue="String"   
    isChainIncluded="Boolean"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
  
    storeLocation="LocalMachine/CurrentUser"  
  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
</certificateReference>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a02be-108">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="a02be-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a02be-109">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="a02be-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a02be-110">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="a02be-110">Attributes</span></span>  
  
|<span data-ttu-id="a02be-111">Atrybut</span><span class="sxs-lookup"><span data-stu-id="a02be-111">Attribute</span></span>|<span data-ttu-id="a02be-112">Opis</span><span class="sxs-lookup"><span data-stu-id="a02be-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a02be-113">findValue</span><span class="sxs-lookup"><span data-stu-id="a02be-113">findValue</span></span>|<span data-ttu-id="a02be-114">Określa wartość do wyszukania w magazynie certyfikatów X.509.</span><span class="sxs-lookup"><span data-stu-id="a02be-114">Specifies the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="a02be-115">Typ zawarte w tym atrybucie muszą spełniać wymagania określonego `X509FindType` wartość.</span><span class="sxs-lookup"><span data-stu-id="a02be-115">The type contained in this attribute must satisfy the requirements of the specified `X509FindType` value.</span></span> <span data-ttu-id="a02be-116">Wartość domyślna to ciąg pusty.</span><span class="sxs-lookup"><span data-stu-id="a02be-116">The default is an empty string.</span></span>|  
|<span data-ttu-id="a02be-117">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="a02be-117">isChainIncluded</span></span>|<span data-ttu-id="a02be-118">Wartość logiczna określająca, czy Walidacja jest wykonana przy użyciu łańcucha certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="a02be-118">A Boolean value that specifies if the validation is done using a certificate chain.</span></span>|  
|<span data-ttu-id="a02be-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="a02be-119">storeLocation</span></span>|<span data-ttu-id="a02be-120">Określa lokalizację magazynu certyfikatów, który klient może używać do weryfikacji certyfikatu serwera.</span><span class="sxs-lookup"><span data-stu-id="a02be-120">Specifies the location of the certificate store that the client can use to validate the server’s certificate.</span></span><br /><br /> <span data-ttu-id="a02be-121">Prawidłowe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="a02be-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a02be-122">-LocalMachine: Magazyn certyfikatów przypisany na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="a02be-122">-   LocalMachine: The cert store assigned to the local machine.</span></span><br /><span data-ttu-id="a02be-123">-CurrentUser: Magazyn certyfikatów przypisany do bieżącego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a02be-123">-   CurrentUser: The cert store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="a02be-124">Wartością domyślną jest komputer lokalny.</span><span class="sxs-lookup"><span data-stu-id="a02be-124">The default value is LocalMachine.</span></span><br /><br /> <span data-ttu-id="a02be-125">Ten atrybut jest typu <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span><span class="sxs-lookup"><span data-stu-id="a02be-125">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|<span data-ttu-id="a02be-126">storeName</span><span class="sxs-lookup"><span data-stu-id="a02be-126">storeName</span></span>|<span data-ttu-id="a02be-127">Określa nazwę magazynu certyfikatu X.509 do otwarcia.</span><span class="sxs-lookup"><span data-stu-id="a02be-127">Specifies the name of the X.509 certificate store to open.</span></span><br /><br /> <span data-ttu-id="a02be-128">Prawidłowe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="a02be-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a02be-129">-Książka adresowa: Magazyn certyfikatów dla innych użytkowników.</span><span class="sxs-lookup"><span data-stu-id="a02be-129">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="a02be-130">-AuthRoot: Certyfikatu sklepu dla firm urzędy certyfikacji (CA).</span><span class="sxs-lookup"><span data-stu-id="a02be-130">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="a02be-131">-Urzędów certyfikacji: Magazyn certyfikatów dla pośrednich urzędów certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="a02be-131">-   CertificateAuthority: Certificate store for intermediate CAs.</span></span><br /><span data-ttu-id="a02be-132">— Niedozwolone: Magazyn certyfikatów odwołanych certyfikatów.</span><span class="sxs-lookup"><span data-stu-id="a02be-132">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="a02be-133">-Moje: Magazynu certyfikatów osobistych.</span><span class="sxs-lookup"><span data-stu-id="a02be-133">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="a02be-134">-Główny: Magazyn certyfikatów zaufanych głównych urzędów certyfikacji.</span><span class="sxs-lookup"><span data-stu-id="a02be-134">-   Root: Certificate store for trusted root CAs.</span></span><br /><span data-ttu-id="a02be-135">-TrustedPeople: Magazyn certyfikatów dla bezpośrednio zaufanych osób i zasobów.</span><span class="sxs-lookup"><span data-stu-id="a02be-135">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="a02be-136">-TrustedPublisher: Magazyn certyfikatów dla bezpośrednio zaufanych wydawców.</span><span class="sxs-lookup"><span data-stu-id="a02be-136">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="a02be-137">Wartość domyślna to Moje.</span><span class="sxs-lookup"><span data-stu-id="a02be-137">The default value is My.</span></span><br /><br /> <span data-ttu-id="a02be-138">Ten atrybut jest typu <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span><span class="sxs-lookup"><span data-stu-id="a02be-138">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="a02be-139">X509FindType</span><span class="sxs-lookup"><span data-stu-id="a02be-139">X509FindType</span></span>|<span data-ttu-id="a02be-140">Określa typ wyszukiwania X.509 w celu wykonania.</span><span class="sxs-lookup"><span data-stu-id="a02be-140">Specifies the type of X.509 search to be executed.</span></span> <span data-ttu-id="a02be-141">Typ zawarty w `findValue` atrybutu muszą spełniać wymagania X509FindType określony.</span><span class="sxs-lookup"><span data-stu-id="a02be-141">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="a02be-142">Prawidłowe wartości są następujące:</span><span class="sxs-lookup"><span data-stu-id="a02be-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a02be-143">-Postać FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="a02be-143">-   FindByThumbPrint</span></span><br /><span data-ttu-id="a02be-144">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="a02be-144">-   FindBySubjectName</span></span><br /><span data-ttu-id="a02be-145">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a02be-145">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="a02be-146">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="a02be-146">-   FindByIssuerName</span></span><br /><span data-ttu-id="a02be-147">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="a02be-147">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="a02be-148">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="a02be-148">-   FindBySerialNumber</span></span><br /><span data-ttu-id="a02be-149">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="a02be-149">-   FindByTimeValid</span></span><br /><span data-ttu-id="a02be-150">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="a02be-150">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="a02be-151">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="a02be-151">-   FindByTemplateName</span></span><br /><span data-ttu-id="a02be-152">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="a02be-152">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="a02be-153">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="a02be-153">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="a02be-154">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="a02be-154">-   FindByExtension</span></span><br /><span data-ttu-id="a02be-155">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="a02be-155">-   FindByKeyUsage</span></span><br /><span data-ttu-id="a02be-156">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="a02be-156">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="a02be-157">Wartość domyślna to FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="a02be-157">The default value is FindBySubjectDistinguishedName.</span></span><br /><br /> <span data-ttu-id="a02be-158">Ten atrybut jest typu <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="a02be-158">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a02be-159">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="a02be-159">Child Elements</span></span>  
 <span data-ttu-id="a02be-160">Brak.</span><span class="sxs-lookup"><span data-stu-id="a02be-160">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a02be-161">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="a02be-161">Parent Elements</span></span>  
  
|<span data-ttu-id="a02be-162">Element</span><span class="sxs-lookup"><span data-stu-id="a02be-162">Element</span></span>|<span data-ttu-id="a02be-163">Opis</span><span class="sxs-lookup"><span data-stu-id="a02be-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a02be-164">\<tożsamość ></span><span class="sxs-lookup"><span data-stu-id="a02be-164">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="a02be-165">Określa ustawienia, które umożliwiają uwierzytelnianie punkt końcowy przez inne punkty końcowe, wymiana wiadomości z nim.</span><span class="sxs-lookup"><span data-stu-id="a02be-165">Specifies settings that enable the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a02be-166">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a02be-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>