---
title: "Mapowanie identyfikatorów obiektów na algorytmy kryptografii"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: dbfe394193925e38dad774d39d79ac813abef22a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="8a9dc-102">Mapowanie identyfikatorów obiektów na algorytmy kryptografii</span><span class="sxs-lookup"><span data-stu-id="8a9dc-102">Mapping Object Identifiers to Cryptography Algorithms</span></span>
<span data-ttu-id="8a9dc-103">Podpisy cyfrowe upewnij się, że dane nie jest modyfikowany podczas wysyłania pomiędzy programami do innego.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-103">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="8a9dc-104">Zwykle podpis cyfrowy jest obliczana przez zastosowanie funkcji matematycznych do wyznaczania wartości skrótu danych do podpisania.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-104">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="8a9dc-105">Podczas formatowania wartości skrótu, aby były podpisane niektóre algorytmy podpisu cyfrowego Dołącz ASN.1 identyfikatora obiektu (OID) w ramach operacji formatowania.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-105">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="8a9dc-106">OID Określa algorytm używany do obliczania skrótu.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-106">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="8a9dc-107">Algorytmy można mapować do identyfikatorów obiektów rozszerzenie mechanizmu kryptografii użycia niestandardowego algorytmów.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-107">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="8a9dc-108">Poniższy przykład przedstawia sposób odwzorowywania identyfikator obiektu nowego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-108">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="8a9dc-109">[ \<Oidentry — > element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) zawiera dwa atrybuty.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-109">The [\<oidEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="8a9dc-110">**OID** atrybut jest numer identyfikatora obiektu.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-110">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="8a9dc-111">**Nazwa** atrybutu jest wartością **nazwa** atrybutu z [ \<nameentry — > elementu](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="8a9dc-111">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="8a9dc-112">Mapowanie nazw algorytmu do klasy musi istnieć, przed identyfikatorem obiektu mogą być mapowane na prostą nazwą.</span><span class="sxs-lookup"><span data-stu-id="8a9dc-112">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a9dc-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8a9dc-113">See Also</span></span>  
 [<span data-ttu-id="8a9dc-114">Konfigurowanie klasy kryptografii</span><span class="sxs-lookup"><span data-stu-id="8a9dc-114">Configuring Cryptography Classes</span></span>](../../../docs/framework/configure-apps/configure-cryptography-classes.md)  
 [<span data-ttu-id="8a9dc-115">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="8a9dc-115">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)