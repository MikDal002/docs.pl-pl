---
title: LINQ do XML osi (C#)
ms.date: 07/20/2015
ms.assetid: 3f7d54ff-b608-43a1-9e2d-e70668b72df8
ms.openlocfilehash: 8755355692b45fa04b960a6b07b53bdc3054a653
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583434"
---
# <a name="linq-to-xml-axes-c"></a>LINQ do XML osi (C#)
Po drzewa XML utworzone lub ładowany dokument XML do drzewa XML można tworzyć zapytania, do znajdowania elementów i atrybutów i pobierania ich wartości.  
  
 Aby można było tworzyć żadnych zapytań, należy zrozumieć [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] osi. Istnieją dwa rodzaje metod osi: Po pierwsze, istnieją metody, które wywołują na pojedynczym <xref:System.Xml.Linq.XElement> obiektu, <xref:System.Xml.Linq.XDocument> obiektu lub <xref:System.Xml.Linq.XNode> obiektu. Te metody działają na pojedynczy obiekt i zwracają zbiór <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute>, lub <xref:System.Xml.Linq.XNode> obiektów. Po drugie są metody rozszerzenia, które działają na kolekcji i zwracają kolekcje. Metody rozszerzenia wyliczania kolekcji źródłowej, wywołać metodę odpowiednich osi dla każdego elementu w kolekcji, a następnie łączenie wyników.  
  
## <a name="in-this-section"></a>W tej sekcji  
  
|Temat|Opis|  
|-----------|-----------------|  
|[LINQ to XML — Przegląd osi (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Definiuje osi i wyjaśniono, jak są używane w kontekście [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] zapytania.|  
|[Instrukcje: Pobieranie kolekcji elementów (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Wprowadza <xref:System.Xml.Linq.XContainer.Elements%2A> metody. Ta metoda pobiera kolekcję elementów podrzędnych elementu.|  
|[Instrukcje: Pobieranie wartości elementu (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Pokazuje, jak można pobrać wartości elementów.|  
|[Instrukcje: Filtrowanie nazw elementów (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Pokazuje, jak filtrowanie nazw elementów, gdy za pomocą osi.|  
|[Instrukcje: Połączyć w łańcuch wywołań metody osi (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Pokazuje, jak połączyć w łańcuch wywołań metody osi.|  
|[Instrukcje: Pobierz jeden typ elementów podrzędnych (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Pokazuje, jak pobrać jeden typ elementów podrzędnych elementu, otrzymuje nazwę tagu elementu podrzędnego.|  
|[Instrukcje: Pobieranie kolekcji atrybutów (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Wprowadza <xref:System.Xml.Linq.XElement.Attributes%2A> metody. Ta metoda pobiera atrybuty elementu.|  
|[Instrukcje: Pobieranie pojedynczego atrybutu (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Pokazuje, jak pobieranie pojedynczego atrybutu elementu, otrzymuje nazwę atrybutu.|  
|[Instrukcje: Pobieranie wartości atrybutu (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Pokazuje, jak można pobrać wartości atrybutów.|  
|[Instrukcje: Pobieranie płytkiej wartości elementu (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Pokazuje, jak pobieranie płytkiej wartości elementu.|  
  
## <a name="see-also"></a>Zobacz także

- [Metody rozszerzeń](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [Przewodnik programowania (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
