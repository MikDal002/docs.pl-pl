---
title: << = — operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: 4c262da906a6033680b05f6a4099a6a1dc8bfab5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260635"
---
# <a name="-operator-visual-basic"></a>\<\<= — Operator (Visual Basic)
Wykonuje arytmetyczne przesunięcie w lewo na wartość zmiennej lub właściwości, a następnie przypisuje wynik do zmiennej lub właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>Części  
 `variableorproperty`  
 Wymagana. Zmiennej lub właściwości typu całkowitego (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, lub `ULong`).  
  
 `amount`  
 Wymagana. Wyrażenia liczbowego typu danych, która rozszerza się na `Integer`.  
  
## <a name="remarks"></a>Uwagi  
 Element w lewej części `<<=` operator może być prosta zmienna skalarne, właściwości lub elementu w tablicy. Zmiennej lub właściwości nie może być [tylko do odczytu](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 `<<=` Operator najpierw wykonuje arytmetyczne przesunięcie w lewo na wartość zmiennej lub właściwości. Operator następnie przypisuje wynik tej operacji do tej zmiennej lub właściwości.  
  
 Arytmetycznego przesunięcia nie są cykliczne, co oznacza, że bity przesunięte poza jednym końcu wynik nie są ponownie wprowadzone po drugiej stronie. W arytmetyczne przesunięcie w lewo bity przesunięte poza zakresem typu danych wyniku są odrzucane i pozycje bitów zwolnione w wyniku po prawej stronie zostaną ustawione na zero.  
  
## <a name="overloading"></a>Przeciążenie  
 [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) może być *przeciążone*, co oznacza, że klasy lub struktury można ponownie zdefiniować jej zachowanie, gdy argument operacji ma typ tej klasy lub struktury. Przeciążanie `<<` operator ma wpływ na zachowanie `<<=` operatora. Jeśli kod używa `<<=` dla klasy lub struktury, która przeciążenia `<<`, należy zrozumieć zachowanie zmieniony. Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `<<=` operatora przesunięcia wzorca bitowego `Integer` zmiennej pozostawiony przez określony przedział i przypisz wynik do zmiennej.  
  
 [!code-vb[VbVbalrOperators#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-assignment-operator_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- [<<, operator](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [Operatory przypisania](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatory Bit Shift](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Pierwszeństwo operatorów w języku Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operatory według funkcji](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrukcje](../../../visual-basic/programming-guide/language-features/statements.md)
