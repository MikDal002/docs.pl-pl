---
title: 'Instrukcje: Kontrolowanie prefiksów Namespace (C#) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: 4664be2661e54782598345886029835108934955
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714035"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a>Instrukcje: Kontrolowanie prefiksów Namespace (C#) (LINQ to XML)
W tym temacie opisano, jak kontrolować prefiksy przestrzeni nazw podczas serializacji drzewa XML.  
  
 W wielu sytuacjach nie jest konieczne kontrolowanie prefiksów przestrzeni nazw.  
  
 Jednak niektórych narzędzi do programowania XML Wymagaj sterowania prefiksy przestrzeni nazw. Na przykład użytkownik może być manipulowanie arkusz stylów XSLT lub dokumentu XAML, który zawiera osadzone wyrażenia XPath, które odwołują się do prefiksy przestrzeni nazw określonych; w tym przypadku jest ważne, że dokument można było serializować ją przy tych prefiksów.  
  
 Jest to najbardziej typowe przyczyny kontrolowanie prefiksów przestrzeni nazw.  
  
 Inny typową przyczyną kontrolowanie prefiksów przestrzeni nazw jest, że użytkownicy mają ręcznie edytować dokumentu XML, a chcesz utworzyć prefiksy przestrzeni nazw, które są w dogodnym dla użytkownika o wpisanie. Na przykład użytkownik może generować dokumentu XSD. Konwencje dotyczące schematów sugerują, użyj jednej `xs` lub `xsd` jako prefiksu dla przestrzeni nazw schematu.  
  
 Aby kontrolować prefiksy przestrzeni nazw, należy wstawić atrybuty, które deklarują przestrzeni nazw. W przypadku przestrzeni nazw z specyficzne prefiksy [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] podejmie próbę uznaje prefiksy przestrzeni nazw podczas serializacji.  
  
 Aby utworzyć atrybut, który deklaruje przestrzeni nazw z prefiksem, Utwórz atrybut w przypadku przestrzeni nazw nazwa atrybutu <xref:System.Xml.Linq.XNamespace.Xmlns%2A>, a nazwą atrybutu jest prefiks przestrzeni nazw. Wartość atrybutu jest identyfikatorem URI przestrzeni nazw.  
  
## <a name="example"></a>Przykład  
 Ten przykład deklaruje dwie przestrzeni nazw. Określa, że `http://www.adventure-works.com` przestrzeń nazw ma prefiks `aw`oraz że `www.fourthcoffee.com` przestrzeń nazw ma prefiks `fc`.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Zobacz także

- [Praca z przestrzeniami nazw XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
