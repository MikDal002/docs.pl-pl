---
title: Get — instrukcja (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: ade54b2f00c540a1bf4ede311e1631b2c5d7e3ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742396"
---
# <a name="get-statement"></a>Get — Instrukcja
Deklaruje `Get` procedury właściwości używane do pobierania wartości właściwości.  
  
## <a name="syntax"></a>Składnia  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>Części  
  
|Termin|Definicja|  
|---|---|  
|`attributelist`|Opcjonalna. Zobacz temat [Lista atrybutów](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcjonalnie na co najwyżej jeden z `Get` i `Set` instrukcje w tej właściwości. Może to być jeden z następujących elementów:<br /><br /> -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Zobacz temat [Poziomy dostępu w języku Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Opcjonalna. Jedna lub więcej instrukcji, które są uruchamiane podczas `Get` nosi nazwę procedury właściwości.|  
|`End Get`|Wymagana. Kończy definicję `Get` procedury właściwości.|  
  
## <a name="remarks"></a>Uwagi  
 Dla każdej właściwości musi mieć `Get` procedury właściwości, chyba że właściwość jest oznaczona `WriteOnly`. `Get` Procedura służy do zwracania bieżącej wartości właściwości.  
  
 Visual Basic automatycznie wywołuje właściwość `Get` procedury, gdy wyrażenie żąda wartość właściwości.  
  
 Treść deklaracja właściwości może zawierać tylko właściwości `Get` i `Set` procedury między [Property — instrukcja](../../../visual-basic/language-reference/statements/property-statement.md) i `End Property` instrukcji. Nie można zapisać coś innego niż te procedury. W szczególności go nie można zapisać bieżącą wartość właściwości. Ta wartość poza właściwości, muszą być przechowywane, ponieważ jeśli będą przechowywane w jednej z procedur właściwość, inne procedury właściwości nie można uzyskać do niego dostęp. Zwykle rozwiązaniem jest wartość jest przechowywana w [prywatnej](../../../visual-basic/language-reference/modifiers/private.md) Zmienna zadeklarowana na tym samym poziomie jak właściwość. Należy zdefiniować `Get` procedury właściwości, której dotyczy.  
  
 `Get` Procedury wartość domyślna to poziom dostępu do jego zawierającą je właściwość, chyba że używasz `accessmodifier` w `Get` instrukcji.  
  
## <a name="rules"></a>reguły  
  
-   **Mieszanymi poziomami dostępu.** Jeśli zamierzasz zdefiniować właściwości odczytu / zapisu, można opcjonalnie określić poziom dostępu do różnych dla dowolnego `Get` lub `Set` procedury, ale nie oba. Jeśli to zrobisz, procedura poziom dostępu musi być bardziej restrykcyjny niż poziom dostępu do właściwości. Na przykład, jeśli właściwość jest zadeklarowana `Friend`, można zadeklarować `Get` procedury `Private`, ale nie `Public`.  
  
     Jeśli definiujesz `ReadOnly` właściwości `Get` procedury reprezentuje cały właściwość. Nie można zadeklarować dostęp inny poziom `Get`, ponieważ, ustawić dwa poziomy dostępu dla właściwości.  
  
-   **Typ zwracany.** [Property — instrukcja](../../../visual-basic/language-reference/statements/property-statement.md) można zadeklarować typ danych zwracanych wartości. `Get` Procedury automatycznie zwraca typ danych. Można określić dowolny typ danych lub nazwa wyliczenia, struktury, klasy lub interfejsu.  
  
     Jeśli `Property` instrukcji nie określa `returntype`, zwraca procedury `Object`.  
  
## <a name="behavior"></a>Zachowanie  
  
-   **Zwracanie z procedury.** Gdy `Get` procedury zwraca do kodu wywołującego, wykonywanie jest kontynuowane wewnątrz instrukcji, który zażądał wartości właściwości.  
  
     `Get` procedury własności może zwracać wartość za pomocą [instrukcji Return](../../../visual-basic/language-reference/statements/return-statement.md) lub przypisując wartość zwracaną do danej nazwy właściwości. Aby uzyskać więcej informacji, zobacz "Zwraca wartość" w [Function — instrukcja](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     `Exit Property` i `Return` instrukcji powodują natychmiastowego wyjścia z procedury właściwości. Dowolną liczbę `Exit Property` i `Return` instrukcji może występować w dowolnym miejscu w ramach procedury i możesz mieszać `Exit Property` i `Return` instrukcji.  
  
-   **Zwraca wartość.** Aby zwrócić wartość z zakresu od `Get` procedury, można przypisać wartości do danej nazwy właściwości lub uwzględnić go w [instrukcji Return](../../../visual-basic/language-reference/statements/return-statement.md). `Return` Instrukcja jednocześnie przypisuje `Get` procedury zwracać wartości i kończy procedurę.  
  
     Jeśli używasz `Exit Property` bez przypisywania wartości do nazwy właściwości `Get` procedura zwraca wartość domyślna dla typu danych właściwości. Aby uzyskać więcej informacji, zobacz "Zwraca wartość" w [Function — instrukcja](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Poniższy przykład przedstawia dwa sposoby właściwość tylko do odczytu `quoteForTheDay` może zwrócić wartość przechowywaną w zmiennej prywatnej `quoteValue`.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto `Get` instrukcji, aby zwrócić wartości właściwości.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a>Zobacz także
- [Set, instrukcja](../../../visual-basic/language-reference/statements/set-statement.md)
- [Instrukcja Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit, instrukcja](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Obiekty i klasy](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Przewodnik: Definiowanie klas](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
