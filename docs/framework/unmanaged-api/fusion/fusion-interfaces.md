---
title: "Interfejsy łączenia"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f1742025bed977dfd377a78db42df42c1bc43966
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="fusion-interfaces"></a><span data-ttu-id="644b7-102">Interfejsy łączenia</span><span class="sxs-lookup"><span data-stu-id="644b7-102">Fusion Interfaces</span></span>
<span data-ttu-id="644b7-103">W tej sekcji opisano niezarządzane interfejsy, które fusion interfejsu API używane do dostępu do właściwości zasobów aplikacji i lokalizowania poprawne wersje tych zasobów dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="644b7-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="644b7-104">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="644b7-104">In This Section</span></span>  
 [<span data-ttu-id="644b7-105">IAppIdAuthority — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="644b7-106">Udostępnia metody, które Generowanie i klucze dla tożsamości aplikacji i odwołania do porównania.</span><span class="sxs-lookup"><span data-stu-id="644b7-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="644b7-107">IAssemblyCache — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="644b7-108">Udostępnia reprezentację globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="644b7-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="644b7-109">IAssemblyCacheItem — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="644b7-110">Reprezentuje pojedynczy zestawu w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="644b7-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="644b7-111">IAssemblyEnum — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="644b7-112">Reprezentuje moduł wyliczający dla tablicy `IAssemblyName` obiektów.</span><span class="sxs-lookup"><span data-stu-id="644b7-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="644b7-113">IAssemblyName — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="644b7-114">Udostępnia metody opisujące i pracy z unikatowych tożsamości zestawu.</span><span class="sxs-lookup"><span data-stu-id="644b7-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="644b7-115">IDefinitionAppId — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="644b7-116">Reprezentuje unikatowy identyfikator dla kodu, który definiuje aplikacji w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="644b7-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="644b7-117">IDefinitionIdentity — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="644b7-118">Reprezentuje podpis unikatowy kod, który definiuje aplikacji w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="644b7-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="644b7-119">IEnumDefinitionIdentity — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="644b7-120">Pełni rolę modułu wyliczającego dla kolekcji `IDefinitionIdentity` obiektów.</span><span class="sxs-lookup"><span data-stu-id="644b7-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="644b7-121">Ienumidentity_attribute — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="644b7-122">Służy jako moduł wyliczający dla atrybutów obiektu kodu w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="644b7-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="644b7-123">IEnumReferenceIdentity — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="644b7-124">Służy jako moduł wyliczający kolekcji `IReferenceIdentity` obiektów.</span><span class="sxs-lookup"><span data-stu-id="644b7-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="644b7-125">IIdentityAuthority — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="644b7-126">Zarządza tożsamości klucze obiekty kod.</span><span class="sxs-lookup"><span data-stu-id="644b7-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="644b7-127">IInstallReferenceEnum — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="644b7-128">Reprezentuje moduł wyliczający dla zestawów występujących w odwołaniach zainstalowany w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="644b7-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="644b7-129">IInstallReferenceItem — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="644b7-130">Reprezentuje element zainstalowany w globalnej pamięci podręcznej zestawów.</span><span class="sxs-lookup"><span data-stu-id="644b7-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="644b7-131">IReferenceAppId — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="644b7-132">Reprezentuje odwołanie do Unikatowy identyfikator dla aplikacji w bieżącym zakresie.</span><span class="sxs-lookup"><span data-stu-id="644b7-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="644b7-133">IReferenceIdentity — interfejs</span><span class="sxs-lookup"><span data-stu-id="644b7-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="644b7-134">Reprezentuje odwołanie do unikatowego podpisu obiektu kodu.</span><span class="sxs-lookup"><span data-stu-id="644b7-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="644b7-135">Tematy pomocy</span><span class="sxs-lookup"><span data-stu-id="644b7-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="644b7-136">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="644b7-136">Related Sections</span></span>  
 [<span data-ttu-id="644b7-137">Łączenie statycznych funkcji globalnych</span><span class="sxs-lookup"><span data-stu-id="644b7-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="644b7-138">Wyliczenia łączenia</span><span class="sxs-lookup"><span data-stu-id="644b7-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="644b7-139">Łączenie — struktury</span><span class="sxs-lookup"><span data-stu-id="644b7-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)