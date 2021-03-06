---
title: '&amp; — Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: eac99ba38841f6972b5bdc8a01f816519af06288
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684674"
---
# <a name="amp-operator-visual-basic"></a>&amp; — Operator (Visual Basic)
Tworzy połączenie ciągów dwóch wyrażeń.  
  
## <a name="syntax"></a>Składnia  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Części  
 `result`  
 Wymagana. Wszelkie `String` lub `Object` zmiennej.  
  
 `expression1`  
 Wymagana. Dowolne wyrażenie z typem danych, która rozszerza się na `String`.  
  
 `expression2`  
 Wymagana. Dowolne wyrażenie z typem danych, która rozszerza się na `String`.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli typ danych `expression1` lub `expression2` nie `String` , ale rozszerza się na `String`, jest konwertowany na `String`. Jeśli jeden z typów danych nie mogą zostać poszerzone do `String`, kompilator generuje błąd.  
  
 Typ danych `result` jest `String`. Jeśli jeden lub oba wyrażenia mają [nic](../../../visual-basic/language-reference/nothing.md) lub mieć wartość <xref:System.DBNull.Value?displayProperty=nameWithType>, będą one traktowane jako ciąg znaków o wartości "".  
  
> [!NOTE]
>  `&` Operator może być *przeciążone*, co oznacza, że klasy lub struktury można ponownie zdefiniować jej zachowanie, gdy argument operacji ma typ tej klasy lub struktury. Jeśli kod używa tego operatora dla klasy lub struktury, upewnij się, że rozumiesz jej zachowanie zmieniony. Aby uzyskać więcej informacji, zobacz [procedury operatorów](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  Handlowe "i" (&) znak może również służyć do identyfikowania zmienne jako typ `Long`. Aby uzyskać więcej informacji, zobacz [znaki typu](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Przykład  
 W tym przykładzie użyto `&` operatora, aby wymusić ciągów. Wynik jest wartością ciągu reprezentujący łączenie ciąg dwóch argumentów.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- [&=, operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operatory łączenia](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Pierwszeństwo operatorów w języku Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operatory według funkcji](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatory łączenia w języku Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
