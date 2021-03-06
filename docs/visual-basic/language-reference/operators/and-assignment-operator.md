---
title: '&amp;= — Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: dee30096f244adc34b83fdfdc6af0baabd372b4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672412"
---
# <a name="amp-operator-visual-basic"></a>&amp;= — Operator (Visual Basic)
Łączy `String` wyrażenie `String` zmiennej lub właściwości i przypisuje wynik do zmiennej lub właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>Części  
 `variableorproperty`  
 Wymagana. Wszelkie `String` zmiennej lub właściwości.  
  
 `expression`  
 Wymagana. Wszelkie `String` wyrażenia.  
  
## <a name="remarks"></a>Uwagi  
 Element w lewej części `&=` operator może być prosta zmienna skalarne, właściwości lub elementu w tablicy. Zmiennej lub właściwości nie może być [tylko do odczytu](../../../visual-basic/language-reference/modifiers/readonly.md). `&=` Łączy operator `String` wyrażenie po jego prawej stronie, aby `String` zmiennej lub właściwości po lewej stronie, a następnie przypisuje wynik do zmiennej lub właściwość po lewej stronie.  
  
## <a name="overloading"></a>Przeciążenie  
 [& — Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) może być *przeciążone*, co oznacza, że klasy lub struktury można ponownie zdefiniować jej zachowanie, gdy argument operacji ma typ tej klasy lub struktury. Przeciążanie `&` operator ma wpływ na zachowanie `&=` operatora. Jeśli kod używa `&=` dla klasy lub struktury, która przeciążenia `&`, należy zrozumieć zachowanie zmieniony. Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `&=` operatora do łączenia dwóch `String` zmienne i przypisz wynik do pierwszej zmiennej.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/and-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- [&, operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [+=, operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [Operatory przypisania](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatory łączenia](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Pierwszeństwo operatorów w języku Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operatory według funkcji](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrukcje](../../../visual-basic/programming-guide/language-features/statements.md)
