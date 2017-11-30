---
title: "Wywołania zwrotne serializacji z tolerancją dla wersji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OnDeserializedAttribute [WCF]
- OnDeserializingAttribute [WCF]
- OnSerializingAttribute [WCF]
- serialization [WCF], setting default values
- OnSerializedAttribute [WCF]
ms.assetid: aa4a3a6f-05ec-4efd-bdbf-2181e13e6468
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7c00cadd4b0e643e35f7f56a28760e261c423699
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="version-tolerant-serialization-callbacks"></a><span data-ttu-id="ffb90-102">Wywołania zwrotne serializacji z tolerancją dla wersji</span><span class="sxs-lookup"><span data-stu-id="ffb90-102">Version-Tolerant Serialization Callbacks</span></span>
<span data-ttu-id="ffb90-103">Model programowania kontraktu danych w pełni obsługuje metody wywołania zwrotnego serializacji z tolerancją dla wersji który <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> i <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> klas pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="ffb90-103">The data contract programming model fully supports the version-tolerant serialization callback methods that the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> classes support.</span></span>  
  
## <a name="version-tolerant-attributes"></a><span data-ttu-id="ffb90-104">Atrybuty tolerancją dla wersji</span><span class="sxs-lookup"><span data-stu-id="ffb90-104">Version-Tolerant Attributes</span></span>  
 <span data-ttu-id="ffb90-105">Istnieją cztery atrybuty wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="ffb90-105">There are four callback attributes.</span></span> <span data-ttu-id="ffb90-106">Każdy atrybut można stosować do metody, która wywołuje aparat serializacji/deserializacji w różnym czasie.</span><span class="sxs-lookup"><span data-stu-id="ffb90-106">Each attribute can be applied to a method that the serialization/deserialization engine calls at various times.</span></span> <span data-ttu-id="ffb90-107">W poniższej tabeli opisano, kiedy należy używać każdego atrybutu.</span><span class="sxs-lookup"><span data-stu-id="ffb90-107">The table below explains when to use each attribute.</span></span>  
  
|<span data-ttu-id="ffb90-108">Atrybut</span><span class="sxs-lookup"><span data-stu-id="ffb90-108">Attribute</span></span>|<span data-ttu-id="ffb90-109">Gdy jest wywoływana odpowiedniej metody</span><span class="sxs-lookup"><span data-stu-id="ffb90-109">When the corresponding method is called</span></span>|  
|---------------|---------------------------------------------|  
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="ffb90-110">Wywołuje się przed rozpoczęciem serializacji typu.</span><span class="sxs-lookup"><span data-stu-id="ffb90-110">Called before serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="ffb90-111">Wywoływana po wykonaniu serializacji typu.</span><span class="sxs-lookup"><span data-stu-id="ffb90-111">Called after serializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="ffb90-112">Wywoływana przed deserializacji typu.</span><span class="sxs-lookup"><span data-stu-id="ffb90-112">Called before deserializing the type.</span></span>|  
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="ffb90-113">Wywołuje się po deserializacji typu.</span><span class="sxs-lookup"><span data-stu-id="ffb90-113">Called after deserializing the type.</span></span>|  
  
 <span data-ttu-id="ffb90-114">Musisz zaakceptować metody <xref:System.Runtime.Serialization.StreamingContext> parametru.</span><span class="sxs-lookup"><span data-stu-id="ffb90-114">The methods must accept a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span>  
  
 <span data-ttu-id="ffb90-115">Te metody są przeznaczone głównie do użytku z wersji lub inicjowania.</span><span class="sxs-lookup"><span data-stu-id="ffb90-115">These methods are primarily intended for use with versioning or initialization.</span></span> <span data-ttu-id="ffb90-116">Podczas deserializacji są nazywane ma konstruktorów.</span><span class="sxs-lookup"><span data-stu-id="ffb90-116">During deserialization, no constructors are called.</span></span> <span data-ttu-id="ffb90-117">W związku z tym elementy członkowskie danych nie można prawidłowo zainicjować (do wartości domyślnych zamierzone) Jeśli dla tych elementów członkowskich brakuje danych w strumieniu przychodzącego, na przykład, jeśli dane pochodzą z poprzedniej wersji typu, który nie ma niektórych elementów członkowskich danych.</span><span class="sxs-lookup"><span data-stu-id="ffb90-117">Therefore, data members may not be correctly initialized (to intended default values) if the data for these members is missing in the incoming stream, for example, if the data comes from a previous version of a type that is missing some data members.</span></span> <span data-ttu-id="ffb90-118">Aby rozwiązać ten problem, należy użyć metody wywołania zwrotnego oznaczonej jako <xref:System.Runtime.Serialization.OnDeserializingAttribute>, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="ffb90-118">To correct this, use the callback method marked with the <xref:System.Runtime.Serialization.OnDeserializingAttribute>, as shown in the following example.</span></span>  
  
 <span data-ttu-id="ffb90-119">Można określić tylko jedną metodę według typu z każdą z powyższych atrybuty wywołania zwrotnego.</span><span class="sxs-lookup"><span data-stu-id="ffb90-119">You can mark only one method per type with each of the preceding callback attributes.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ffb90-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="ffb90-120">Example</span></span>  
 [!code-csharp[C_DataContract#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#9)]
 [!code-vb[C_DataContract#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="ffb90-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ffb90-121">See Also</span></span>  
 <xref:System.Runtime.Serialization.OnSerializingAttribute>  
 <xref:System.Runtime.Serialization.OnSerializedAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
 <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
 <xref:System.Runtime.Serialization.StreamingContext>  
 [<span data-ttu-id="ffb90-122">Serializacji z tolerancją dla wersji</span><span class="sxs-lookup"><span data-stu-id="ffb90-122">Version Tolerant Serialization</span></span>](../../../../docs/standard/serialization/version-tolerant-serialization.md)