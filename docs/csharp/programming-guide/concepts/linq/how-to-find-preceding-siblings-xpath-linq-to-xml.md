---
title: "Porady: znajdowanie poprzedzających elementów równorzędnych (XPath-LINQ do XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad6741c265172737b7da0323b653fc3be9df8b1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a><span data-ttu-id="139dd-102">Porady: znajdowanie poprzedzających elementów równorzędnych (XPath-LINQ do XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="139dd-102">How to: Find Preceding Siblings (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="139dd-103">W tym temacie porównuje XPath `preceding-sibling` oś [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] podrzędnych <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> osi.</span><span class="sxs-lookup"><span data-stu-id="139dd-103">This topic compares the XPath `preceding-sibling` axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] child <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> axis.</span></span>  
  
 <span data-ttu-id="139dd-104">Wyrażenie XPath jest:</span><span class="sxs-lookup"><span data-stu-id="139dd-104">The XPath expression is:</span></span>  
  
 `preceding-sibling::*`  
  
 <span data-ttu-id="139dd-105">Należy pamiętać, że wyniki obu <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> i <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> w kolejności dokumentu.</span><span class="sxs-lookup"><span data-stu-id="139dd-105">Note that the results of both <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> and <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> are in document order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="139dd-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="139dd-106">Example</span></span>  
 <span data-ttu-id="139dd-107">Poniższy przykład umożliwia znalezienie `FullAddress` elementu, a następnie pobierze poprzednie elementy, używając `preceding-sibling` osi.</span><span class="sxs-lookup"><span data-stu-id="139dd-107">The following example finds the `FullAddress` element, and then retrieves the previous elements using the `preceding-sibling` axis.</span></span>  
  
 <span data-ttu-id="139dd-108">W tym przykładzie użyto następujących dokumentu XML: [przykładowego pliku XML: Klienci i zamówienia (LINQ do XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="139dd-108">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="139dd-109">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="139dd-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a><span data-ttu-id="139dd-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="139dd-110">See Also</span></span>  
 [<span data-ttu-id="139dd-111">LINQ do XML dla użytkowników XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="139dd-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)