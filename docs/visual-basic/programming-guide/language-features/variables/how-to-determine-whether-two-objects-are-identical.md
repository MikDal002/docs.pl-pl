---
title: 'Instrukcje: Określanie, czy dwa obiekty są jednakowe (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 62d73b6c3d706d9990be7783f0f3461fc0783d9f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512973"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Instrukcje: Określanie, czy dwa obiekty są jednakowe (Visual Basic)
W języku Visual Basic dwóch odwołań do zmiennych są traktowane jako identyczne, jeśli ich wskaźniki są takie same, oznacza to, jeśli obie zmienne wskazywać tego samego wystąpienia klasy w pamięci. Na przykład w aplikacji Windows Forms, warto wykonania porównania, aby określić, czy bieżące wystąpienie (`Me`) jest taka sama jak konkretnego wystąpienia, takie jak `Form2`.  
  
 Visual Basic oferuje dwa operatory porównanie wskaźników. [Operatora Is](../../../../visual-basic/language-reference/operators/is-operator.md) zwraca `True` Jeśli obiekty są identyczne i [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) zwraca `True` Jeśli nie są.  
  
## <a name="determining-if-two-objects-are-identical"></a>Określanie, jeśli dwa obiekty są jednakowe  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Aby określić, jeśli dwa obiekty są jednakowe  
  
1.  Konfigurowanie `Boolean` wyrażenie do przetestowania dwóch obiektów.  
  
2.  W wyrażeniu testowania za pomocą `Is` dwa obiekty jako argumenty operacji operatora.  
  
     `Is` Zwraca `True` Jeśli obiekty wskazywać tego samego wystąpienia klasy.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Określanie, jeśli dwa obiekty nie są identyczne  
 Czasami trzeba wykonać akcję, jeśli dwa obiekty nie są identyczne i mogą być niewygodna połączyć `Not` i `Is`, na przykład `If Not obj1 Is obj2`. W takim przypadku można użyć `IsNot` operatora.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Aby sprawdzić, czy dwa obiekty nie są identyczne  
  
1.  Konfigurowanie `Boolean` wyrażenie do przetestowania dwóch obiektów.  
  
2.  W wyrażeniu testowania za pomocą `IsNot` dwa obiekty jako argumenty operacji operatora.  
  
     `IsNot` Zwraca `True` Jeśli obiekty nie mogą wskazywać tego samego wystąpienia klasy.  
  
## <a name="example"></a>Przykład  
 Następujący przykład sprawdza pary `Object` zmienne, aby zobaczyć, jeśli wskazują na to samo wystąpienie klasy.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 Poprzedni przykład wyświetla następujące dane wyjściowe.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Zobacz także
- [Object, typ danych](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Zmienne obiektów](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Wartości zmiennej obiektu](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Is, operator](../../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot, operator](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Instrukcje: Określanie, czy dwa obiekty są powiązane](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase i MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
