---
title: Parametry ogólne używane jako typy parametrów opcjonalnych muszą być ograniczone przez klasę
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7a1411daf446cbf06cd57b4e002c2c3cd77166af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507164"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a>Parametry ogólne używane jako typy parametrów opcjonalnych muszą być ograniczone przez klasę
Procedura jest zadeklarowana z opcjonalnym parametrem, który korzysta z parametrem typu, który nie jest ograniczony do być typem referencyjnym.  
  
 Zawsze należy podać wartość domyślną dla każdego opcjonalnego parametru. Jeśli parametr jest typem referencyjnym, opcjonalna wartość musi być `Nothing`, która jest prawidłową wartością dla dowolnego typu odwołania. Jednakże jeśli parametr jest typem wartości, tego typu musi być typu danych podstawowych wstępnie zdefiniowane przez program Visual Basic. Jest to spowodowane typu złożonych wartości, takie jak struktury zdefiniowany przez użytkownika, nie ma prawidłowe wartości domyślnej.  
  
 Gdy używasz parametru typu dla opcjonalnego parametru musi zagwarantować, jest typu odwołania, aby uniknąć możliwości typu wartości bez wartości prawidłowy domyślny. Oznacza to, że parametr typu należy ograniczyć przy użyciu `Class` — słowo kluczowe lub o nazwie określonej klasy.  
  
 **Identyfikator błędu:** BC32124  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Ograniczenia parametru typu do akceptowania tylko typem referencyjnym lub nie jest używana dla parametru opcjonalnego.  
  
## <a name="see-also"></a>Zobacz także
- [Typy ogólne w Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Lista typów](../../../visual-basic/language-reference/statements/type-list.md)
- [Class, instrukcja](../../../visual-basic/language-reference/statements/class-statement.md)
- [Parametry opcjonalne](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Struktury](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Nothing](../../../visual-basic/language-reference/nothing.md)
