---
title: 'Instrukcje: Pisanie zapytań z zaawansowanym filtrowaniem (C#)'
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 847e50cf0c1cf91f8b731457d351bb0d01d725c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700588"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a>Instrukcje: Pisanie zapytań z zaawansowanym filtrowaniem (C#)
Czasami chcesz zapisywać LINQ do XML zapytań za pomocą złożonych filtrów. Na przykład trzeba znaleźć wszystkie elementy, które ma element podrzędny o określonej nazwie i wartości. Ten temat zawiera przykładowy Pisanie zapytań z zaawansowanym filtrowaniem.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie pokazano, jak znaleźć wszystkie `PurchaseOrder` elementy podrzędne `Address` element, który ma `Type` atrybutu jest równa "Wysyłania" i elementem podrzędnym `State` element równy "NY". Używa ona zapytanie zagnieżdżone w `Where` klauzuli i `Any` operator zwraca `true` Jeśli kolekcja zawiera żadnych elementów. Aby dowiedzieć się, jak za pomocą składni zapytania oparte na metodzie, zobacz [składnia zapytania a składnia metody w technologii LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
 W tym przykładzie użyto następujący dokument XML: [Przykładowy plik XML: Wiele zamówień zakupu (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
 Aby uzyskać więcej informacji na temat `Any` operatora, zobacz [Operacje kwantyfikatora (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md).  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where   
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
99505  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje tego samego zapytania w formacie XML, który znajduje się w przestrzeni nazw. Aby uzyskać więcej informacji, zobacz [Praca z przestrzeniami nazw XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 W tym przykładzie użyto następujący dokument XML: [Przykładowy plik XML: Wiele zamówień zakupu w Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 Ten kod generuje następujące dane wyjściowe:  
  
```  
99505  
```  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [Podstawowe zapytania (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [Operacje rzutowania (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
- [Operacje kwantyfikatora (C#)](../../../../csharp/programming-guide/concepts/linq/quantifier-operations.md)
