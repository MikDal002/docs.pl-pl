---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: 3b9d1ec15c6c2000fb0842abe25848f853cdf986
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703717"
---
# <a name="widening-visual-basic"></a>Widening (Visual Basic)
Oznacza to, że operator konwersji (`CType`) konwertuje klasę lub strukturę do typu, który może pomieścić wszystkie możliwe wartości oryginalnej klasy lub struktury.  
  
## <a name="converting-with-the-widening-keyword"></a>Konwertowanie za pomocą rozszerzającą — słowo kluczowe  
 Należy określić procedury konwersji `Public Shared` oprócz `Widening`.  
  
 Konwersje rozszerzające zawsze kończą się pomyślnie w czasie wykonywania i nigdy nie pociągnąć za sobą utratę danych. Należą do nich `Single` do `Double`, `Char` do `String`, a jego typ podstawowy typ pochodny. Ta ostatnia konwersja jest rozszerzanie, ponieważ typ pochodny zawiera wszystkie elementy członkowskie w typie podstawowym, a więc jest wystąpieniem typu podstawowego.  
  
 Kod konsumencki nie trzeba używać `CType` do poszerzenia konwersje, nawet jeśli `Option Strict` jest `On`.  
  
 Słowa kluczowego `Widening` można użyć w tym kontekście:  
  
 [Operator, instrukcja](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Na przykład definicje rozszerzanie i zwężanie konwersji, operatorów, zobacz [jak: Definiowanie operatora konwersji](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## <a name="see-also"></a>Zobacz także
- [Operator, instrukcja](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Rozszerzanie i zwężanie konwersji](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Instrukcje: Definiowanie operatora](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Funkcja CType](../../../visual-basic/language-reference/functions/ctype-function.md)
- [Option Strict, instrukcja](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Instrukcje: Definiowanie operatora konwersji](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
