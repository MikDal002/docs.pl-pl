---
title: 'Instrukcje: Etykieta instrukcji (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 00a08bd3bd1f866cec883b6591b03ebd9d858b90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552267"
---
# <a name="how-to-label-statements-visual-basic"></a>Instrukcje: Etykieta instrukcji (Visual Basic)
Bloki instrukcji składają się z wierszy kodu, rozdzielone średnikami. Wiersze kodu poprzedzone identyfikujący ciąg lub liczba całkowita, są określane jako *etykietą*. Etykiety instrukcji są używane w sposób znaczyć linię kodu w celu identyfikowania go do użycia przy użyciu instrukcji takich jak `On Error Goto`.  
  
 Etykiety mogą być albo prawidłowych identyfikatorów języka Visual Basic — takich jak te, które identyfikują programistyczny — lub literały całkowite. Etykieta musi znajdować się na początku wiersza kodu źródłowego i musi być następuje dwukropek, niezależnie od tego, czy następuje instrukcji w tym samym wierszu.  
  
 Kompilator identyfikuje etykiety, sprawdzając, czy początek wiersza pasuje do żadnego identyfikatora już zdefiniowane. Jeśli nie, kompilator zakłada, że jest etykietę.  
  
 Etykiety mają własnej przestrzeni deklaracji i nie kolidują z innymi identyfikatorami. Zakres etykiety jest treści metody. Deklaracja etykieta ma pierwszeństwo przed w każdej sytuacji niejednoznaczne.  
  
> [!NOTE]
>  Etykiety mogą służyć tylko w instrukcji wykonywalnych wewnątrz metody.  
  
### <a name="to-label-a-line-of-code"></a>Aby dodać etykietę wiersza kodu  
  
-   Umieść identyfikator, następuje dwukropek, na początku wiersza kodu źródłowego.  
  
     Na przykład następujące wiersze kodu są oznaczone za pomocą `Jump` i `120`odpowiednio:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- [Instrukcje](../../../visual-basic/programming-guide/language-features/statements.md)
- [Nazwy zadeklarowanych elementów](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Konwencje dotyczące struktury programów i kodu](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
