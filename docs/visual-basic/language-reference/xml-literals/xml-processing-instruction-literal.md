---
title: Literał instrukcji przetwarzającej kod XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: cb9ad1d687203dff497e4cd451933a8bbbdf4bf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491236"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a>Literał instrukcji przetwarzającej kod XML (Visual Basic)
Literał reprezentujący <xref:System.Xml.Linq.XProcessingInstruction> obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a>Części  
 `<?`  
 Wymagana. Oznacza początek literał instrukcji przetwarzania XML.  
  
 `piName`  
 Wymagana. Nadaj nazwę wskazującą, która aplikacja przetwarzanie instrukcji celów. Nie może zaczynać od "xml" lub "XML".  
  
 `piData`  
 Opcjonalna. Ciąg wskazujący, jak aplikacja objęte `piName` powinien przetworzyć dokumentu XML.  
  
 `?>`  
 Wymagana. Oznacza koniec instrukcji przetwarzania.  
  
## <a name="return-value"></a>Wartość zwracana  
 <xref:System.Xml.Linq.XProcessingInstruction> Obiektu.  
  
## <a name="remarks"></a>Uwagi  
 Literały instrukcji przetwarzania XML wskazują, jak aplikacje należy przetworzyć dokumentu XML. Podczas ładowania dokumentu XML aplikacji Aplikacja może sprawdzać, czy instrukcje przetwarzania XML w celu ustalenia sposobu przetwarzania dokumentu. Aplikacja interpretuje słowa kluczowe znaczenie `piName` i `piData`.  
  
 Literał dokumentu XML używa składni, która jest podobna do instrukcji przetwarzania XML. Aby uzyskać więcej informacji, zobacz [literał dokumentu XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).  
  
> [!NOTE]
>  `piName` Element nie może rozpoczynać się ciągi "xml" lub "XML", ponieważ Specyfikacja XML 1.0 rezerwuje tych identyfikatorów.  
  
 Można przypisać literał instrukcji przetwarzania XML do zmiennej lub ją dołączyć literał dokumentu XML.  
  
> [!NOTE]
>  Literał XML może obejmować wiele wierszy, bez konieczności używania znaków kontynuacji wiersza. Dzięki temu można skopiować zawartość z dokumentu XML i wklej go bezpośrednio w programie Visual Basic.  
  
 Kompilator Visual Basic konwertuje literał instrukcji przetwarzania XML do wywołania <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> konstruktora.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy instrukcja przetwarzania zidentyfikowanie arkusza stylów dla dokumentu XML.  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Xml.Linq.XProcessingInstruction>
- [Literał dokumentu XML](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [Literały XML](../../../visual-basic/language-reference/xml-literals/index.md)
- [Tworzenie XML w Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
