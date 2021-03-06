---
title: Słowa kluczowe jako nazwy elementów w Code (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 0d52df42b00abfa364762d97c162eb143e511f06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649495"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>Słowa kluczowe jako nazwy elementów w Code (Visual Basic)
Dowolnego elementu programu — takie jak zmienna, klasy ani składowej — może mieć taką samą nazwę jak ograniczony — słowo kluczowe. Na przykład można utworzyć zmiennej o nazwie `Loop`. Jednak do odwoływania się do swoją wersję — która ma taką samą nazwę jak zastrzeżonego `Loop` — słowo kluczowe — należy poprzedzić go ukośnikiem ciągu pełnej kwalifikacji lub należy ją ująć w nawiasy kwadratowe (`[ ]`), jak pokazano w poniższym przykładzie.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 Wykonaj jedną z tych wersji, a następnie języka Visual Basic założono użycie wewnętrznego `Loop` — słowo kluczowe i generuje błąd, jak w poniższym przykładzie:  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 Można użyć nawiasy kwadratowe przy odwoływaniu się do formularzy i kontrolek, a w przypadku deklarowania zmiennej lub definiowanie procedury o takiej samej nazwie jako ograniczeniami — słowo kluczowe. Można łatwo zapomnieć o kwalifikowania nazwy lub zawierać nawiasów kwadratowych, zatem wprowadzenie błędów w kodzie i utrudnić do odczytu. Z tego powodu zaleca się nie używać ograniczeniami słowa kluczowe jako nazwy elementów programu. Jednak jeśli przyszłych wersjach programu Visual Basic definiuje nowe słowo kluczowe powodującą konflikt z istniejącego formularza lub nazwa kontrolki, następnie służy ta technika podczas aktualizowania kodu do pracy z nową wersją.  
  
> [!NOTE]
>  Program może również obejmować nazwy elementów dostarczane przez inne przywoływanych zestawach. Jeśli te nazwy są w konflikcie z ograniczeniami słowami kluczowymi, następnie umieszczenie nawiasami kwadratowymi wokół nich powoduje, że Visual Basic, aby zinterpretować je jako elementów zdefiniowanych.  
  
## <a name="see-also"></a>Zobacz także
- [Visual Basic — konwencje nazewnictwa](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [Konwencje dotyczące struktury programów i kodu](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [Słowa kluczowe](../../../visual-basic/language-reference/keywords/index.md)
