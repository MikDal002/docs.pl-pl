---
title: '&lt;comContract&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b22c8d0b72d4dfc63eb5fa9afa073f993f75418e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltcomcontractgt"></a><span data-ttu-id="8bd64-102">&lt;comContract&gt;</span><span class="sxs-lookup"><span data-stu-id="8bd64-102">&lt;comContract&gt;</span></span>
<span data-ttu-id="8bd64-103">Określa kontrakt usługi integracji COM +.</span><span class="sxs-lookup"><span data-stu-id="8bd64-103">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="8bd64-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8bd64-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8bd64-105">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="8bd64-105">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd64-106">Składnia</span><span class="sxs-lookup"><span data-stu-id="8bd64-106">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="string"  
      namespace="string"  
      name="string"  
      requireSession="Boolean">  
      <exposedMethods>  
         <exposedMethod name="string" />  
      </exposedMethods>  
      <userDefinedTypes>  
         <userDefinedType name="string"  
            typeLibID="string"  
            typeLibVersion="string"  
            typeDefID="string">  
         </userDefinedType>  
      </userDefinedTypes>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bd64-107">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="8bd64-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8bd64-108">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="8bd64-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bd64-109">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="8bd64-109">Attributes</span></span>  
  
|<span data-ttu-id="8bd64-110">Atrybut</span><span class="sxs-lookup"><span data-stu-id="8bd64-110">Attribute</span></span>|<span data-ttu-id="8bd64-111">Opis</span><span class="sxs-lookup"><span data-stu-id="8bd64-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bd64-112">kontrakt</span><span class="sxs-lookup"><span data-stu-id="8bd64-112">contract</span></span>|<span data-ttu-id="8bd64-113">Ciąg, który zawiera typ kontraktu.</span><span class="sxs-lookup"><span data-stu-id="8bd64-113">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="8bd64-114">nazwa</span><span class="sxs-lookup"><span data-stu-id="8bd64-114">name</span></span>|<span data-ttu-id="8bd64-115">Ciąg, który zawiera nazwę kontraktu.</span><span class="sxs-lookup"><span data-stu-id="8bd64-115">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="8bd64-116">— przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="8bd64-116">namespace</span></span>|<span data-ttu-id="8bd64-117">Ciąg zawierający przestrzeń nazw kontraktu.</span><span class="sxs-lookup"><span data-stu-id="8bd64-117">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="8bd64-118">Element requiresSession</span><span class="sxs-lookup"><span data-stu-id="8bd64-118">requiresSession</span></span>|<span data-ttu-id="8bd64-119">Wartość logiczna określająca, czy kontrakt można używać tylko na powiązaniach sesyjnych.</span><span class="sxs-lookup"><span data-stu-id="8bd64-119">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="8bd64-120">Podczas inicjowania usługi środowiska uruchomieniowego integracji zapewnia, że to ustawienie jest zgodne z typ powiązania do użycia.</span><span class="sxs-lookup"><span data-stu-id="8bd64-120">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="8bd64-121">Wyjątek jest generowany, jeśli jeden lub więcej powiązania dla kontraktu będących w konflikcie.</span><span class="sxs-lookup"><span data-stu-id="8bd64-121">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="8bd64-122">Jeśli ta właściwość jest `false`, jednokierunkowe kanał jest w użyciu i istnieją parametry [out], wyjątek zostanie również wygenerowany.</span><span class="sxs-lookup"><span data-stu-id="8bd64-122">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bd64-123">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="8bd64-123">Child Elements</span></span>  
  
|<span data-ttu-id="8bd64-124">Element</span><span class="sxs-lookup"><span data-stu-id="8bd64-124">Element</span></span>|<span data-ttu-id="8bd64-125">Opis</span><span class="sxs-lookup"><span data-stu-id="8bd64-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bd64-126">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="8bd64-126">persistableTypes</span></span>|<span data-ttu-id="8bd64-127">Wszystkie typy możliwy do utrwalenia.</span><span class="sxs-lookup"><span data-stu-id="8bd64-127">All the persistable types.</span></span>|  
|<span data-ttu-id="8bd64-128">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="8bd64-128">userDefinedTypes</span></span>|<span data-ttu-id="8bd64-129">Kolekcja z użytkownika zdefiniowanych typów (UDT), które ma być zawarty w kontrakcie usługi.</span><span class="sxs-lookup"><span data-stu-id="8bd64-129">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="8bd64-130">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="8bd64-130">exposedMethods</span></span>|<span data-ttu-id="8bd64-131">Kolekcja metod modelu COM +, które są dostępne, gdy interfejs składnika COM + jest udostępniany jako usługa sieci Web.</span><span class="sxs-lookup"><span data-stu-id="8bd64-131">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bd64-132">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="8bd64-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8bd64-133">Element</span><span class="sxs-lookup"><span data-stu-id="8bd64-133">Element</span></span>|<span data-ttu-id="8bd64-134">Opis</span><span class="sxs-lookup"><span data-stu-id="8bd64-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8bd64-135">comContracts</span><span class="sxs-lookup"><span data-stu-id="8bd64-135">comContracts</span></span>|<span data-ttu-id="8bd64-136">Zawiera kolekcję `comContract` elementów.</span><span class="sxs-lookup"><span data-stu-id="8bd64-136">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bd64-137">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8bd64-137">Remarks</span></span>  
 <span data-ttu-id="8bd64-138">Kontrakty usług integracji COM + są obecnie ograniczone do przestrzeni nazw "http://tempuri.org", a Nazwa kontraktu pochodzi od obsługi interfejsu COM.</span><span class="sxs-lookup"><span data-stu-id="8bd64-138">COM+ integration service contracts are currently restricted to the "http://tempuri.org" namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="8bd64-139">Można jednak określić alternatywne przy użyciu `comContracts` sekcji, jak również `comContract` w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="8bd64-139">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="8bd64-140">Na przykład można użyć następującej konfiguracji do określania przestrzeni nazw, Nazwa kontraktu i typy zdefiniowane przez użytkownika do uwzględnienia, a także innych ustawień dla kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="8bd64-140">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>  
  <comContract  
      contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"  
      namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"  
      name="_Broker"  
      requireSession="true">  
      <exposedMethods>  
         <exposedMethod name="BuyStock" />  
         <exposedMethod name="SellStock" />  
         <exposedMethod name="ExecuteTransaction" />  
      </exposedMethods>  
  </comContract>  
</comContracts>  
```  
  
 <span data-ttu-id="8bd64-141">Podczas inicjowania usługi określonych przestrzeni nazw i nazwy kontraktów są stosowane do opisów wygenerowanego usługi.</span><span class="sxs-lookup"><span data-stu-id="8bd64-141">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd64-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8bd64-142">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElementCollection>  
 <xref:System.ServiceModel.Configuration.ComContractElement>  
 [<span data-ttu-id="8bd64-143">\<comContracts ></span><span class="sxs-lookup"><span data-stu-id="8bd64-143">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="8bd64-144">Współdziałanie z aplikacjami COM +</span><span class="sxs-lookup"><span data-stu-id="8bd64-144">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="8bd64-145">Porady: Konfigurowanie ustawień usług COM +</span><span class="sxs-lookup"><span data-stu-id="8bd64-145">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)