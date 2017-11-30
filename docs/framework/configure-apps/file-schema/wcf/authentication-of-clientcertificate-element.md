---
title: '&lt;authentication&gt; w &lt;clientCertificate&gt;, element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4eb125727d68d1618b32d21612ecfac28eaa5b6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltauthenticationgt-of-ltclientcertificategt-element"></a><span data-ttu-id="acccf-102">&lt;authentication&gt; w &lt;clientCertificate&gt;, element</span><span class="sxs-lookup"><span data-stu-id="acccf-102">&lt;authentication&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="acccf-103">Określa zachowania uwierzytelnienia dla certyfikatów klienta używanych przez usługę.</span><span class="sxs-lookup"><span data-stu-id="acccf-103">Specifies authentication behaviors for client certificates used by a service.</span></span>  
  
 <span data-ttu-id="acccf-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="acccf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="acccf-105">\<zachowania ></span><span class="sxs-lookup"><span data-stu-id="acccf-105">\<behaviors></span></span>  
<span data-ttu-id="acccf-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="acccf-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="acccf-107">\<zachowanie ></span><span class="sxs-lookup"><span data-stu-id="acccf-107">\<behavior></span></span>  
<span data-ttu-id="acccf-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="acccf-108">\<serviceCredentials></span></span>  
<span data-ttu-id="acccf-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="acccf-109">\<clientCertificate></span></span>  
<span data-ttu-id="acccf-110">\<Uwierzytelnianie ></span><span class="sxs-lookup"><span data-stu-id="acccf-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acccf-111">Składnia</span><span class="sxs-lookup"><span data-stu-id="acccf-111">Syntax</span></span>  
  
```xml  
<authentication  
customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
includeWindowsGroups="Boolean"  
mapClientCertificateToWindowsAccount="Boolean"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acccf-112">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="acccf-112">Attributes and Elements</span></span>  
 <span data-ttu-id="acccf-113">W poniższych sekcjach opisano atrybuty i elementy podrzędne, elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="acccf-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acccf-114">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="acccf-114">Attributes</span></span>  
  
|<span data-ttu-id="acccf-115">Atrybut</span><span class="sxs-lookup"><span data-stu-id="acccf-115">Attribute</span></span>|<span data-ttu-id="acccf-116">Opis</span><span class="sxs-lookup"><span data-stu-id="acccf-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="acccf-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="acccf-117">customCertificateValidatorType</span></span>|<span data-ttu-id="acccf-118">Opcjonalny ciąg.</span><span class="sxs-lookup"><span data-stu-id="acccf-118">Optional string.</span></span> <span data-ttu-id="acccf-119">Typ i zestaw używany do walidacji typu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="acccf-119">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="acccf-120">Ten atrybut musi być ustawiane podczas `certificateValidationMode` ma ustawioną wartość `Custom`.</span><span class="sxs-lookup"><span data-stu-id="acccf-120">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|<span data-ttu-id="acccf-121">tryb certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="acccf-121">certificateValidationMode</span></span>|<span data-ttu-id="acccf-122">Opcjonalne wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="acccf-122">Optional enumeration.</span></span> <span data-ttu-id="acccf-123">Określa jeden z trybów używanych do walidacji poświadczenia.</span><span class="sxs-lookup"><span data-stu-id="acccf-123">Specifies one of the modes used to validate credentials.</span></span> <span data-ttu-id="acccf-124">Ten atrybut jest <xref:System.ServiceModel.Security.X509CertificateValidationMode> typu.</span><span class="sxs-lookup"><span data-stu-id="acccf-124">This attribute is of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> type.</span></span> <span data-ttu-id="acccf-125">Jeśli ustawiono <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, a następnie `customCertificateValidator` należy dostarczyć także.</span><span class="sxs-lookup"><span data-stu-id="acccf-125">If set to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom?displayProperty=nameWithType>, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="acccf-126">Wartość domyślna to <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="acccf-126">The default is <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust?displayProperty=nameWithType>.</span></span>|  
|<span data-ttu-id="acccf-127">właściwości includeWindowsGroups</span><span class="sxs-lookup"><span data-stu-id="acccf-127">includeWindowsGroups</span></span>|<span data-ttu-id="acccf-128">Opcjonalna wartość logiczna.</span><span class="sxs-lookup"><span data-stu-id="acccf-128">Optional Boolean.</span></span> <span data-ttu-id="acccf-129">Określa, czy grupy systemu Windows znajdują się w kontekście zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="acccf-129">Specifies if Windows groups are included in the security context.</span></span> <span data-ttu-id="acccf-130">Ustawienie tego atrybutu na `true` ma wpływ na wydajność, ponieważ jej wynikiem rozszerzenia całej grupy.</span><span class="sxs-lookup"><span data-stu-id="acccf-130">Setting this attribute to `true` has a performance impact, as it results in a full group expansion.</span></span> <span data-ttu-id="acccf-131">Ten atrybut na `false` Jeśli nie musisz ustanowić listę grup należy użytkownik.</span><span class="sxs-lookup"><span data-stu-id="acccf-131">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|<span data-ttu-id="acccf-132">mapClientCertificateToWindowsAcccount</span><span class="sxs-lookup"><span data-stu-id="acccf-132">mapClientCertificateToWindowsAcccount</span></span>|<span data-ttu-id="acccf-133">Wartość logiczna.</span><span class="sxs-lookup"><span data-stu-id="acccf-133">Boolean.</span></span> <span data-ttu-id="acccf-134">Określa, czy klient może być mapowany na tożsamość systemu Windows przy użyciu certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="acccf-134">Specifies whether the client can be mapped to a Windows identity using the certificate.</span></span> <span data-ttu-id="acccf-135">W tym celu należy włączyć usługi Active Directory.</span><span class="sxs-lookup"><span data-stu-id="acccf-135">Active Directory must be enabled to do this.</span></span>|  
|<span data-ttu-id="acccf-136">revocationMode</span><span class="sxs-lookup"><span data-stu-id="acccf-136">revocationMode</span></span>|<span data-ttu-id="acccf-137">Opcjonalne wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="acccf-137">Optional enumeration.</span></span> <span data-ttu-id="acccf-138">Jeden z trybów użytych do sprawdzenia odwołanych list certyfikatów (RCL).</span><span class="sxs-lookup"><span data-stu-id="acccf-138">One of the modes used to check for a revoked certificate lists (RCL).</span></span> <span data-ttu-id="acccf-139">Wartość domyślna to `Online`.</span><span class="sxs-lookup"><span data-stu-id="acccf-139">The default is `Online`.</span></span> <span data-ttu-id="acccf-140">Ta wartość jest ignorowana w przypadku korzystania z zabezpieczeń transportu HTTP.</span><span class="sxs-lookup"><span data-stu-id="acccf-140">This value is ignored when using HTTP transport security.</span></span>|  
|<span data-ttu-id="acccf-141">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="acccf-141">trustedStoreLocation</span></span>|<span data-ttu-id="acccf-142">Opcjonalne wyliczenie.</span><span class="sxs-lookup"><span data-stu-id="acccf-142">Optional enumeration.</span></span> <span data-ttu-id="acccf-143">Jeden z dwóch lokalizacji magazynu systemu: `LocalMachine` lub `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="acccf-143">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="acccf-144">Ta wartość jest używana, gdy negocjowane jest certyfikat usługi do klienta.</span><span class="sxs-lookup"><span data-stu-id="acccf-144">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="acccf-145">Sprawdzanie poprawności jest wykonywane przed **zaufane osoby** są przechowywane w lokalizacji określonej magazynu.</span><span class="sxs-lookup"><span data-stu-id="acccf-145">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="acccf-146">Wartość domyślna to `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="acccf-146">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidatortype-attribute"></a><span data-ttu-id="acccf-147">customCertificateValidatorType atrybutu</span><span class="sxs-lookup"><span data-stu-id="acccf-147">customCertificateValidatorType Attribute</span></span>  
  
|<span data-ttu-id="acccf-148">Wartość</span><span class="sxs-lookup"><span data-stu-id="acccf-148">Value</span></span>|<span data-ttu-id="acccf-149">Opis</span><span class="sxs-lookup"><span data-stu-id="acccf-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acccf-150">String</span><span class="sxs-lookup"><span data-stu-id="acccf-150">String</span></span>|<span data-ttu-id="acccf-151">Określa nazwę typu i zestawu i innych danych można znaleźć typu.</span><span class="sxs-lookup"><span data-stu-id="acccf-151">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="acccf-152">tryb certificateValidationMode atrybutu</span><span class="sxs-lookup"><span data-stu-id="acccf-152">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="acccf-153">Wartość</span><span class="sxs-lookup"><span data-stu-id="acccf-153">Value</span></span>|<span data-ttu-id="acccf-154">Opis</span><span class="sxs-lookup"><span data-stu-id="acccf-154">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acccf-155">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="acccf-155">Enumeration</span></span>|<span data-ttu-id="acccf-156">Jedną z następujących wartości: None, uległ awarii, ChainTrust, PeerOrChainTrust, niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="acccf-156">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="acccf-157">Aby uzyskać więcej informacji, zobacz [Praca z certyfikatami](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="acccf-157">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="acccf-158">revocationMode atrybutu</span><span class="sxs-lookup"><span data-stu-id="acccf-158">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="acccf-159">Wartość</span><span class="sxs-lookup"><span data-stu-id="acccf-159">Value</span></span>|<span data-ttu-id="acccf-160">Opis</span><span class="sxs-lookup"><span data-stu-id="acccf-160">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acccf-161">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="acccf-161">Enumeration</span></span>|<span data-ttu-id="acccf-162">Jedną z następujących wartości: NoCheck, Online, w trybie Offline.</span><span class="sxs-lookup"><span data-stu-id="acccf-162">One of the following values: NoCheck, Online, Offline.</span></span> <span data-ttu-id="acccf-163">Aby uzyskać więcej informacji, zobacz [Praca z certyfikatami](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="acccf-163">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="acccf-164">trustedStoreLocation atrybutu</span><span class="sxs-lookup"><span data-stu-id="acccf-164">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="acccf-165">Wartość</span><span class="sxs-lookup"><span data-stu-id="acccf-165">Value</span></span>|<span data-ttu-id="acccf-166">Opis</span><span class="sxs-lookup"><span data-stu-id="acccf-166">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="acccf-167">Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="acccf-167">Enumeration</span></span>|<span data-ttu-id="acccf-168">Jedną z następujących wartości: `LocalMachine` lub `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="acccf-168">One of the following values: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="acccf-169">Wartość domyślna to `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="acccf-169">The default is `CurrentUser`.</span></span> <span data-ttu-id="acccf-170">Jeśli aplikacja kliencka jest uruchomiona na koncie systemu, a następnie certyfikat jest zwykle w obszarze `LocalMachine`.</span><span class="sxs-lookup"><span data-stu-id="acccf-170">If the client application is running under a system account then the certificate is typically under `LocalMachine`.</span></span> <span data-ttu-id="acccf-171">Jeśli aplikacja kliencka jest uruchomiona na koncie użytkownika, a następnie certyfikat jest zwykle w `CurrentUser`.</span><span class="sxs-lookup"><span data-stu-id="acccf-171">If the client application is running under a user account then the certificate is typically in `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acccf-172">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="acccf-172">Child Elements</span></span>  
 <span data-ttu-id="acccf-173">Brak.</span><span class="sxs-lookup"><span data-stu-id="acccf-173">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acccf-174">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="acccf-174">Parent Elements</span></span>  
  
|<span data-ttu-id="acccf-175">Element</span><span class="sxs-lookup"><span data-stu-id="acccf-175">Element</span></span>|<span data-ttu-id="acccf-176">Opis</span><span class="sxs-lookup"><span data-stu-id="acccf-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acccf-177">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="acccf-177">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|<span data-ttu-id="acccf-178">Definiuje certyfikat X.509 używany do uwierzytelniania klienta do usługi.</span><span class="sxs-lookup"><span data-stu-id="acccf-178">Defines an X.509 certificate used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acccf-179">Uwagi</span><span class="sxs-lookup"><span data-stu-id="acccf-179">Remarks</span></span>  
 <span data-ttu-id="acccf-180">`<authentication>` Element odpowiada <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> klasy.</span><span class="sxs-lookup"><span data-stu-id="acccf-180">The `<authentication>` element corresponds to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="acccf-181">Umożliwia dostosowanie sposobu uwierzytelniania klientów.</span><span class="sxs-lookup"><span data-stu-id="acccf-181">It enables you to customize how clients are authenticated.</span></span> <span data-ttu-id="acccf-182">Można ustawić `certificateValidationMode` atrybutu `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, lub `Custom`.</span><span class="sxs-lookup"><span data-stu-id="acccf-182">You can set the `certificateValidationMode` attribute to `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust`, or `Custom`.</span></span> <span data-ttu-id="acccf-183">Domyślnie po ustawieniu poziomu `ChainTrust`, który określa, że każdy certyfikat musi zostać znaleziony w hierarchii certyfikatów w *główny urząd* w górnej części łańcucha.</span><span class="sxs-lookup"><span data-stu-id="acccf-183">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a *root authority* at the top of the chain.</span></span> <span data-ttu-id="acccf-184">Jest to najbardziej bezpieczny tryb.</span><span class="sxs-lookup"><span data-stu-id="acccf-184">This is the most secure mode.</span></span> <span data-ttu-id="acccf-185">Można również ustawić wartość `PeerOrChainTrust`, która określa, że certyfikaty wystawionej samodzielnie (relacja zaufania elementów równorzędnych) są akceptowane oraz certyfikaty, które znajdują się w łańcuchu zaufanego.</span><span class="sxs-lookup"><span data-stu-id="acccf-185">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="acccf-186">Ta wartość jest używana podczas opracowywania i debugowania klientów i usług, ponieważ własnym wystawione certyfikaty nie muszą można zakupić z zaufanego urzędu.</span><span class="sxs-lookup"><span data-stu-id="acccf-186">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="acccf-187">Podczas wdrażania klienta, użyj `ChainTrust` wartość zmiennej.</span><span class="sxs-lookup"><span data-stu-id="acccf-187">When deploying a client, use the `ChainTrust` value instead.</span></span>  
  
 <span data-ttu-id="acccf-188">Można również ustawić wartość `Custom`.</span><span class="sxs-lookup"><span data-stu-id="acccf-188">You can also set the value to `Custom`.</span></span> <span data-ttu-id="acccf-189">Jeśli wartość `Custom` wartości, należy także ustawić `customCertificateValidatorType` atrybutu zestawu i typ używany do weryfikacji certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="acccf-189">When set to the `Custom` value, you must also set the `customCertificateValidatorType` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="acccf-190">Aby utworzyć własnego niestandardowego modułu weryfikacji, musi dziedziczyć z klasy abstrakcyjnej <xref:System.IdentityModel.Selectors.X509CertificateValidator> klasy.</span><span class="sxs-lookup"><span data-stu-id="acccf-190">To create your own custom validator, you must inherit from the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="acccf-191">Aby uzyskać więcej informacji, zobacz [porady: Tworzenie usługi korzystającej z niestandardowego moduł weryfikacji certyfikatów](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span><span class="sxs-lookup"><span data-stu-id="acccf-191">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acccf-192">Przykład</span><span class="sxs-lookup"><span data-stu-id="acccf-192">Example</span></span>  
 <span data-ttu-id="acccf-193">Poniższy kod określa certyfikat X.509 i niestandardowy typ walidacji w `<authentication>` elementu.</span><span class="sxs-lookup"><span data-stu-id="acccf-193">The following code specifies an X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="acccf-194">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="acccf-194">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>  
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>  
 [<span data-ttu-id="acccf-195">Zachowania zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="acccf-195">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="acccf-196">Porady: Tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów</span><span class="sxs-lookup"><span data-stu-id="acccf-196">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="acccf-197">Praca z certyfikatami</span><span class="sxs-lookup"><span data-stu-id="acccf-197">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)