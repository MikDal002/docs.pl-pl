---
title: "Porady: Napisz zapytanie, które wyszukuje elementy na podstawie kontekstu (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a9e818c5e0967a6d146cd48b81aebcba4bbdde3f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="db0ac-102">Porady: Napisz zapytanie, które wyszukuje elementy na podstawie kontekstu (C#)</span><span class="sxs-lookup"><span data-stu-id="db0ac-102">How to: Write a Query that Finds Elements Based on Context (C#)</span></span>
<span data-ttu-id="db0ac-103">Czasami może być konieczne Napisz zapytanie, które wybiera elementy na podstawie ich kontekstu.</span><span class="sxs-lookup"><span data-stu-id="db0ac-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="db0ac-104">Można filtrować na podstawie poprzedzające lub następujące elementów równorzędnych.</span><span class="sxs-lookup"><span data-stu-id="db0ac-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="db0ac-105">Można filtrować na podstawie podrzędnej lub elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="db0ac-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="db0ac-106">Aby to zrobić, zapisywanie zapytania i przy użyciu wyników kwerendy w `where` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="db0ac-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="db0ac-107">Jeśli trzeba najpierw przetestować wartości null, a następnie sprawdź wartość jest wygodniejsze w zapytaniu w `let` klauzuli, a następnie użyj wyniki w `where` klauzuli.</span><span class="sxs-lookup"><span data-stu-id="db0ac-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db0ac-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="db0ac-108">Example</span></span>  
 <span data-ttu-id="db0ac-109">Poniższy przykład wybranie wszystkich `p` elementów, które są od razu następuje `ul` elementu.</span><span class="sxs-lookup"><span data-stu-id="db0ac-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="db0ac-110">Ten kod generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="db0ac-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="db0ac-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="db0ac-111">Example</span></span>  
 <span data-ttu-id="db0ac-112">W poniższym przykładzie pokazano tego samego zapytania w formacie XML, który znajduje się w przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="db0ac-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="db0ac-113">Aby uzyskać więcej informacji, zobacz [Praca z przestrzeni nazw XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="db0ac-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="db0ac-114">Ten kod generuje następujące dane wyjściowe:</span><span class="sxs-lookup"><span data-stu-id="db0ac-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="db0ac-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="db0ac-115">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Parse%2A>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
 <xref:System.Linq.Enumerable.FirstOrDefault%2A>  
 [<span data-ttu-id="db0ac-116">Podstawowe zapytania (LINQ do XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="db0ac-116">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)