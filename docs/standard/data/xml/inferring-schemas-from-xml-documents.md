---
title: "Wnioskowanie schematów z dokumentów XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: f3d97d53-614d-4a04-a174-87965b7405f6
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aa4d6d2758392fc48969b08db30b91bdfe0eeaa1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-schemas-from-xml-documents"></a><span data-ttu-id="40dea-102">Wnioskowanie schematów z dokumentów XML</span><span class="sxs-lookup"><span data-stu-id="40dea-102">Inferring Schemas from XML Documents</span></span>
<span data-ttu-id="40dea-103">W tym temacie opisano sposób użycia <xref:System.Xml.Schema.XmlSchemaInference> klasy na potrzeby wnioskowania dotyczącego schematu schematu XML definition language (XSD) ze struktury dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-103">This topic describes how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XML Schema definition language (XSD) schema from the structure of an XML document.</span></span>  
  
## <a name="the-schema-inference-process"></a><span data-ttu-id="40dea-104">Proces wnioskowania schematu</span><span class="sxs-lookup"><span data-stu-id="40dea-104">The Schema Inference Process</span></span>  
 <span data-ttu-id="40dea-105"><xref:System.Xml.Schema.XmlSchemaInference> Klasy <xref:System.Xml.Schema?displayProperty=nameWithType> przestrzeni nazw jest używany do generowania schematów języka (XSD) definicja schematu XML co najmniej jednego ze struktury dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-105">The <xref:System.Xml.Schema.XmlSchemaInference> class of the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace is used to generate one or more XML Schema definition language (XSD) schemas from the structure of an XML document.</span></span> <span data-ttu-id="40dea-106">Wygenerowany schematów może służyć do zweryfikowania oryginalnego dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-106">The generated schemas may be used to validate the original XML document.</span></span>  
  
 <span data-ttu-id="40dea-107">Jako XML dokumentu jest przetwarzany przez <xref:System.Xml.Schema.XmlSchemaInference> klasy <xref:System.Xml.Schema.XmlSchemaInference> klasy sprawia, że założenia dotyczące składników schematu, które opisują elementów i atrybutów w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-107">As an XML document is processed by the <xref:System.Xml.Schema.XmlSchemaInference> class, the <xref:System.Xml.Schema.XmlSchemaInference> class makes assumptions about the schema components that describe the elements and attributes in the XML document.</span></span> <span data-ttu-id="40dea-108"><xref:System.Xml.Schema.XmlSchemaInference> Klasy również wnioskuje składników schematu w sposób ograniczone przez wnioskowanie najbardziej restrykcyjne typu dla określonego elementu lub atrybutu.</span><span class="sxs-lookup"><span data-stu-id="40dea-108">The <xref:System.Xml.Schema.XmlSchemaInference> class also infers schema components in a constrained way by inferring the most restrictive type for a particular element or attribute.</span></span> <span data-ttu-id="40dea-109">Jak zbierane więcej informacji na temat dokumentu XML przez wnioskowanie typów mniej restrykcyjnych są zmniejszyć te ograniczenia.</span><span class="sxs-lookup"><span data-stu-id="40dea-109">As more information about the XML document is gathered, these constraints are loosened by inferring less restrictive types.</span></span> <span data-ttu-id="40dea-110">Jest najmniej restrykcyjny typ, który można wywnioskować `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="40dea-110">The least restrictive type that can be inferred is `xs:string`.</span></span>  
  
 <span data-ttu-id="40dea-111">Podjąć, na przykład następujące części dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-111">Take, for example, the following piece of an XML document.</span></span>  
  
```xml  
<parent attribute1="6">  
    <child>One</child>  
    <child>Two</child>  
</parent>  
<parent attribute1="A">  
```  
  
 <span data-ttu-id="40dea-112">W przykładzie przedstawionym powyżej, gdy `attribute1` napotkano atrybut o wartości `6` przez <xref:System.Xml.Schema.XmlSchemaInference> procesu, zakłada się, być typu `xs:unsignedByte`.</span><span class="sxs-lookup"><span data-stu-id="40dea-112">In the example above, when the `attribute1` attribute is encountered with a value of `6` by the <xref:System.Xml.Schema.XmlSchemaInference> process, it is assumed to be of type `xs:unsignedByte`.</span></span> <span data-ttu-id="40dea-113">Gdy drugi `parent` napotkano element przez <xref:System.Xml.Schema.XmlSchemaInference> procesów, ograniczenie jest zmniejszyć zmieniając typ do `xs:string` ponieważ wartość `attribute1` atrybut jest teraz `A`.</span><span class="sxs-lookup"><span data-stu-id="40dea-113">When the second `parent` element is encountered by the <xref:System.Xml.Schema.XmlSchemaInference> process, the constraint is loosened by modifying the type to `xs:string` because the value of the `attribute1` attribute is now `A`.</span></span> <span data-ttu-id="40dea-114">Podobnie `minOccurs` atrybutu dla wszystkich `child` elementy wywnioskować w schemacie są zmniejszyć do `minOccurs="0"` ponieważ drugi element nadrzędny nie ma elementów podrzędnych.</span><span class="sxs-lookup"><span data-stu-id="40dea-114">Similarly, the `minOccurs` attribute for all the `child` elements inferred in the schema are loosened to `minOccurs="0"` because the second parent element has no child elements.</span></span>  
  
## <a name="inferring-schemas-from-xml-documents"></a><span data-ttu-id="40dea-115">Wnioskowanie schematów z dokumentów XML</span><span class="sxs-lookup"><span data-stu-id="40dea-115">Inferring Schemas from XML Documents</span></span>  
 <span data-ttu-id="40dea-116"><xref:System.Xml.Schema.XmlSchemaInference> Klasa korzysta z dwóch przeciążony <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> metod można pobrać schematu z dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-116">The <xref:System.Xml.Schema.XmlSchemaInference> class uses two overloaded <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> methods to infer a schema from an XML document.</span></span>  
  
 <span data-ttu-id="40dea-117">Pierwszy <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> metoda służy do tworzenia schematu na podstawie dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-117">The first <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method is used to create a schema based on an XML document.</span></span> <span data-ttu-id="40dea-118">Drugi <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> metody jest używany na potrzeby wnioskowania dotyczącego schematu, które opisują wiele dokumentów XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-118">The second <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method is used to infer a schema that describes multiple XML documents.</span></span> <span data-ttu-id="40dea-119">Na przykład może dostarczyć wiele dokumentów XML do <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> metodą w czasie, aby wygenerować schematu, który opisuje cały zestaw dokumentów XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-119">For example, you can feed multiple XML documents to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method one at a time to produce a schema that describes the entire set of XML documents.</span></span>  
  
 <span data-ttu-id="40dea-120">Pierwszy <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> metody wnioskuje schemat z dokumentu XML zawartych w <xref:System.Xml.XmlReader> obiektu i zwraca <xref:System.Xml.Schema.XmlSchemaSet> obiekt zawierający wywnioskowany schemat.</span><span class="sxs-lookup"><span data-stu-id="40dea-120">The first <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method infers a schema from an XML document contained in an <xref:System.Xml.XmlReader> object, and returns an <xref:System.Xml.Schema.XmlSchemaSet> object containing the inferred schema.</span></span> <span data-ttu-id="40dea-121">Drugi <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> wyszukiwania — metoda <xref:System.Xml.Schema.XmlSchemaSet> obiekt do schematu z tego samego obszaru nazw docelowych zawartymi w dokumencie XML <xref:System.Xml.XmlReader> obiektu udoskonalanie istniejącego schematu i zwraca <xref:System.Xml.Schema.XmlSchemaSet> obiekt zawierający wywnioskowane schemat.</span><span class="sxs-lookup"><span data-stu-id="40dea-121">The second <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A?displayProperty=nameWithType> method searches an <xref:System.Xml.Schema.XmlSchemaSet> object for a schema with the same target namespace as the XML document contained in the <xref:System.Xml.XmlReader> object, refines the existing schema, and returns an <xref:System.Xml.Schema.XmlSchemaSet> object containing the inferred schema.</span></span>  
  
 <span data-ttu-id="40dea-122">Zmiany wprowadzone w schemacie precyzyjnych są oparte na nowej struktury odnaleziono w dokumencie XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-122">The changes made to the refined schema are based on new structure found in the XML document.</span></span> <span data-ttu-id="40dea-123">Na przykład jako dokument XML jest przesunięta, zostają założeń dotyczących typów danych znaleziono i schemat jest tworzony na podstawie tych założeń.</span><span class="sxs-lookup"><span data-stu-id="40dea-123">For example, as an XML document is traversed, assumptions are made about the data types found, and the schema is created based on those assumptions.</span></span> <span data-ttu-id="40dea-124">Jednak jeśli dane na drugi wnioskowania przebiegu różni się od oryginalnej założeń, schemat jest precyzyjnych.</span><span class="sxs-lookup"><span data-stu-id="40dea-124">However, if data is encountered on a second inference pass that differs from the original assumption, the schema is refined.</span></span> <span data-ttu-id="40dea-125">Poniższy przykład przedstawia proces uściślenia.</span><span class="sxs-lookup"><span data-stu-id="40dea-125">The following example illustrates the refinement process.</span></span>  
  
 [!code-cpp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaInferenceExamples/CPP/XmlSchemaInferenceExamples.cpp#4)]
 [!code-csharp[XmlSchemaInferenceExamples#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaInferenceExamples/CS/XmlSchemaInferenceExamples.cs#4)]
 [!code-vb[XmlSchemaInferenceExamples#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaInferenceExamples/VB/XmlSchemaInferenceExamples.vb#4)]  
  
 <span data-ttu-id="40dea-126">Przykład przyjmuje następującego pliku `item1.xml`, jako jego pierwszej danej wejściowej.</span><span class="sxs-lookup"><span data-stu-id="40dea-126">The example takes the following file, `item1.xml`, as its first input.</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#13](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item1.xml#13)]  
  
 <span data-ttu-id="40dea-127">Przykład bierze `item2.xml` pliku jako dane wejściowe drugiego:</span><span class="sxs-lookup"><span data-stu-id="40dea-127">The example then takes the `item2.xml` file as its second input:</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#14](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/item2.xml#14)]  
  
 <span data-ttu-id="40dea-128">Gdy `productID` napotkano w pierwszy dokument XML, wartość atrybutu `123456789` zakłada się, że `xs:unsignedInt` typu.</span><span class="sxs-lookup"><span data-stu-id="40dea-128">When the `productID` attribute is encountered in the first XML document, the value of `123456789` is assumed to be an `xs:unsignedInt` type.</span></span> <span data-ttu-id="40dea-129">Podczas drugiego dokumentu XML jest jednak odczytu i wartość `A53-246` zostanie znaleziony, `xs:unsignedInt` nie można przyjąć typu.</span><span class="sxs-lookup"><span data-stu-id="40dea-129">However, when the second XML document is read and the value of `A53-246` is found, the `xs:unsignedInt` type can no longer be assumed.</span></span> <span data-ttu-id="40dea-130">Schemat jest precyzyjnych i typ `productID` jest zmieniana na `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="40dea-130">The schema is refined and the type of `productID` is changed to `xs:string`.</span></span> <span data-ttu-id="40dea-131">Ponadto `minOccurs` atrybutu dla `supplierID` element jest ustawiony na wartość `0`, ponieważ jest drugi dokument XML nie `supplierID` elementu.</span><span class="sxs-lookup"><span data-stu-id="40dea-131">In addition, the `minOccurs` attribute for the `supplierID` element is set to `0`, because the second XML document contains no `supplierID` element.</span></span>  
  
 <span data-ttu-id="40dea-132">Oto schemat wywnioskować na podstawie pierwszego dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-132">The following is the schema inferred from the first XML document.</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#15](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema1.xml#15)]  
  
 <span data-ttu-id="40dea-133">Oto schemat wywnioskować na podstawie pierwszy dokument XML, przez drugiego dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="40dea-133">The following is the schema inferred from the first XML document, refined by the second XML document.</span></span>  
  
 [!code-xml[XmlSchemaInferenceExamples#16](../../../../samples/snippets/xml/VS_Snippets_Data/XmlSchemaInferenceExamples/XML/InferSchema2.xml#16)]  
  
## <a name="inline-schemas"></a><span data-ttu-id="40dea-134">Wbudowane schematy</span><span class="sxs-lookup"><span data-stu-id="40dea-134">Inline Schemas</span></span>  
 <span data-ttu-id="40dea-135">Jeśli schemat wbudowany schemat XML definition language (XSD) napotkano podczas <xref:System.Xml.Schema.XmlSchemaInference> procesu <xref:System.Xml.Schema.XmlSchemaInferenceException> jest generowany.</span><span class="sxs-lookup"><span data-stu-id="40dea-135">If an inline XML Schema definition language (XSD) schema is encountered during the <xref:System.Xml.Schema.XmlSchemaInference> process, an <xref:System.Xml.Schema.XmlSchemaInferenceException> is thrown.</span></span> <span data-ttu-id="40dea-136">Na przykład następujące wbudowanego schematu zgłasza <xref:System.Xml.Schema.XmlSchemaInferenceException>.</span><span class="sxs-lookup"><span data-stu-id="40dea-136">For example, the following inline schema throws an <xref:System.Xml.Schema.XmlSchemaInferenceException>.</span></span>  
  
```xml  
<root xmlns:ex="http://www.contoso.com" xmlns="http://www.tempuri.org">  
    <xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://www.contoso.com">  
        <xs:element name="Contoso" type="xs:normalizedString" />  
    </xs:schema>  
    <ex:Contoso>Test</ex:Contoso>  
</root>  
```  
  
## <a name="schemas-that-cannot-be-refined"></a><span data-ttu-id="40dea-137">Schematów, które nie mogą być Refined</span><span class="sxs-lookup"><span data-stu-id="40dea-137">Schemas that Cannot be Refined</span></span>  
 <span data-ttu-id="40dea-138">Brak konstrukcje schematu W3C XML, który schematu (XSD) języka definicji schematu XML <xref:System.Xml.Schema.XmlSchemaInference> procesu nie może obsłużyć, jeśli określony typ, aby doprecyzować i spowodować wyjątków.</span><span class="sxs-lookup"><span data-stu-id="40dea-138">There are W3C XML Schema constructs that the XML Schema definition language (XSD) schema <xref:System.Xml.Schema.XmlSchemaInference> process cannot handle if given a type to refine and cause an exception to be thrown.</span></span> <span data-ttu-id="40dea-139">Takie jak typ złożony którego compositor najwyższego poziomu jest inna niż sekwencji.</span><span class="sxs-lookup"><span data-stu-id="40dea-139">Such as a complex type whose top-level compositor is anything other than a sequence.</span></span> <span data-ttu-id="40dea-140">W modelu obiektu schematu (SOM) odpowiada <xref:System.Xml.Schema.XmlSchemaComplexType> których <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A> właściwość nie jest wystąpieniem <xref:System.Xml.Schema.XmlSchemaSequence>.</span><span class="sxs-lookup"><span data-stu-id="40dea-140">In the Schema Object Model (SOM), this corresponds to an <xref:System.Xml.Schema.XmlSchemaComplexType> whose <xref:System.Xml.Schema.XmlSchemaComplexType.Particle%2A> property is not an instance of <xref:System.Xml.Schema.XmlSchemaSequence>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40dea-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="40dea-141">See Also</span></span>  
 <xref:System.Xml.Schema.XmlSchemaInference>  
 [<span data-ttu-id="40dea-142">Model obiektu schematu XML (SOM)</span><span class="sxs-lookup"><span data-stu-id="40dea-142">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 [<span data-ttu-id="40dea-143">Wnioskowanie schematu XML</span><span class="sxs-lookup"><span data-stu-id="40dea-143">Inferring an XML Schema</span></span>](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 [<span data-ttu-id="40dea-144">Zasady wnioskowanie schematu węzła typy i struktury</span><span class="sxs-lookup"><span data-stu-id="40dea-144">Rules for Inferring Schema Node Types and Structure</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-schema-node-types-and-structure.md)  
 [<span data-ttu-id="40dea-145">Wnioskowanie typów prostych reguł</span><span class="sxs-lookup"><span data-stu-id="40dea-145">Rules for Inferring Simple Types</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)