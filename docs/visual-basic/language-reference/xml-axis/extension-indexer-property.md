---
title: Właściwość indeksatora rozszerzenia (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 25a868afded83f28f5f56a9f19e050bbd32b24c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490833"
---
# <a name="extension-indexer-property-visual-basic"></a>Właściwość indeksatora rozszerzenia (Visual Basic)
Zapewnia dostęp do poszczególnych elementów w kolekcji.  
  
## <a name="syntax"></a>Składnia  
  
```  
object(index)  
```  
  
## <a name="parts"></a>Części  
  
|Termin|Definicja|  
|---|---|  
|`object`|Wymagana. Kolekcja z obsługą zapytań. Oznacza to, kolekcję, która implementuje <xref:System.Collections.Generic.IEnumerable%601> lub <xref:System.Linq.IQueryable%601>.|  
|(|Wymagana. Oznacza początek właściwość indeksatora.|  
|`index`|Wymagana. Wyrażenie liczba całkowita, określająca liczona od zera pozycja elementu kolekcji.|  
|)|Wymagana. Oznacza koniec właściwości indeksatora.|  
  
## <a name="return-value"></a>Wartość zwracana  
 Obiekt z określonej lokalizacji w kolekcji lub `Nothing` Jeśli indeks jest poza zakresem.  
  
## <a name="remarks"></a>Uwagi  
 Właściwość indeksatora rozszerzenia umożliwia dostęp do poszczególnych elementów w kolekcji. Ta właściwość indeksatora zwykle jest używana dla danych wyjściowych właściwości osi XML. Elementu podrzędnego XML i właściwości osi descendant XML zwracają kolekcje <xref:System.Xml.Linq.XElement> obiektów lub wartość atrybutu.  
  
 Kompilator Visual Basic konwertuje właściwości indeksatora rozszerzenia wywołania `ElementAtOrDefault` metody. W przeciwieństwie do indeksatora tablicy `ElementAtOrDefault` metoda zwraca `Nothing` Jeśli indeks jest poza zakresem. To zachowanie jest przydatne, gdy nie można określić, że liczba elementów w kolekcji.  
  
 Ta właściwość indeksatora przypomina właściwości rozszerzenia dla kolekcji, które implementują <xref:System.Collections.Generic.IEnumerable%601> lub <xref:System.Linq.IQueryable%601>: jest używany tylko wtedy, gdy kolekcja nie ma indeksatora lub domyślnej właściwości.  
  
 Aby uzyskać dostęp do wartości pierwszego elementu w kolekcji <xref:System.Xml.Linq.XElement> lub <xref:System.Xml.Linq.XAttribute> obiektów, można użyć pliku XML `Value` właściwości. Aby uzyskać więcej informacji, zobacz [właściwość wartości XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak używać indeksator rozszerzeń dostępu do drugiego węzła podrzędnego w zbiorze <xref:System.Xml.Linq.XElement> obiektów. Kolekcja jest dostępne przy użyciu właściwości osi elementu podrzędnego, który pobiera wszystkie elementy podrzędne, o nazwie `phone` w `contact` obiektu.  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 Ten kod wyświetla następujący tekst:  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Xml.Linq.XElement>
- [Właściwości osi XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Literały XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Tworzenie XML w Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [Właściwość wartości XML](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
