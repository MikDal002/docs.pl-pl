---
title: 'Instrukcje: Tworzenie drzewa na podstawie elementu XmlReader (C#)'
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: fb65c7b74bf3bd006fd4f545e4587efe9a392131
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496190"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>Instrukcje: Tworzenie drzewa na podstawie elementu XmlReader (C#)
W tym temacie przedstawiono sposób tworzenia drzewa XML bezpośrednio z <xref:System.Xml.XmlReader>. Aby utworzyć <xref:System.Xml.Linq.XElement> z <xref:System.Xml.XmlReader>, należy umieścić <xref:System.Xml.XmlReader> węzeł elementu. <xref:System.Xml.XmlReader> Pozwoli na pominięcie komentarze i przetwarzania instrukcji, ale jeśli <xref:System.Xml.XmlReader> znajduje się w węźle tekst, zostanie zgłoszony błąd. Aby uniknąć takich błędów, umieść zawsze <xref:System.Xml.XmlReader> w elemencie przed przystąpieniem do tworzenia drzewa XML z <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie użyto następujący dokument XML: [Przykładowy plik XML: Książki (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 Poniższy kod tworzy `T:System.Xml.XmlReader` obiektu, a następnie odczytuje węzłów do momentu znalezienia pierwszego węzła elementu. Następnie ładuje <xref:System.Xml.Linq.XElement> obiektu.  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 Ten przykład generuje następujące wyniki:  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>Zobacz także

- [Analizowanie kodu XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
