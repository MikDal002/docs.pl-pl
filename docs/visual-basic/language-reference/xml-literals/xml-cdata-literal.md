---
title: Literał CDATA XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 71769c023ba77d40099ba0ba29ef363091e96831
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521559"
---
# <a name="xml-cdata-literal-visual-basic"></a>Literał CDATA XML (Visual Basic)
Literał reprezentujący <xref:System.Xml.Linq.XCData> obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>Części  
 `<![CDATA[`  
 Wymagana. Oznacza początek sekcja XML CDATA.  
  
 `content`  
 Wymagana. Zawartość tekstowa pojawią się w sekcji XML CDATA.  
  
 `]]>`  
 Wymagana. Oznacza koniec sekcji.  
  
## <a name="return-value"></a>Wartość zwracana  
 <xref:System.Xml.Linq.XCData> Obiektu.  
  
## <a name="remarks"></a>Uwagi  
 Sekcje XML CDATA zawierają nieprzetworzony tekst, które powinny być włączone, lecz nie analizować za pomocą XML, który go zawiera. Sekcja XML CDATA może zawierać dowolny tekst. Obejmuje to zarezerwowanych znaków XML. Sekcja XML CDATA kończy się wraz z sekwencji "]] >". Oznacza to następujące kwestie:  
  
-   Nie można użyć wyrażenia osadzone w literał CDATA XML, ponieważ ograniczniki osadzone wyrażenia są prawidłowa zawartość XML CDATA.  
  
-   Nie można zagnieżdżać sekcji XML CDATA, ponieważ `content` nie może zawierać wartość "]] >".  
  
 Możesz przypisać literał CDATA XML do zmiennej lub ją dołączyć literał elementu XML.  
  
> [!NOTE]
>  Literał XML może obejmować wiele wierszy, ale nie mogą używać znaków kontynuacji wiersza. Dzięki temu można skopiować zawartość z dokumentu XML i wklej go bezpośrednio w programie Visual Basic.  
  
 Kompilator Visual Basic konwertuje literał CDATA XML do wywołania <xref:System.Xml.Linq.XCData.%23ctor%2A> konstruktora.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład obejmuje tworzenie sekcji CDATA, która zawiera tekst "może zawierać literału \<XML > tagi".  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Xml.Linq.XCData>
- [Literał elementu XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Literały XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Tworzenie XML w Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
