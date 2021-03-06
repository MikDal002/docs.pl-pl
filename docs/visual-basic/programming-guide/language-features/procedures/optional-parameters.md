---
title: Parametry opcjonalne (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
ms.openlocfilehash: 0f7f7910b5e19c3e1a22598c1a987aa2b02e256e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552232"
---
# <a name="optional-parameters-visual-basic"></a>Parametry opcjonalne (Visual Basic)
Możesz określić, że parametr procedury jest opcjonalny i nie trzeba do niego przekazywać żadnego argumentu w momencie wywołania procedury. *Następujące parametry opcjonalne* są wskazywane przez `Optional` — słowo kluczowe w definicji procedury. Mają zastosowanie następujące zasady:  
  
-   Każdy parametr opcjonalny w definicji procedury musi określać wartość domyślną.  
  
-   Wartość domyślna dla opcjonalnego parametru musi być wyrażeniem stałym.  
  
-   Każdy parametr występujący w definicji procedury po opcjonalnym parametrze również musi być opcjonalny.  
  
 Deklaracja procedury z opcjonalnym parametrem ma następującą składnię:  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a>Wywoływanie procedur z opcjonalnymi parametrami  
 Gdy wywołujesz procedurę z opcjonalnym parametrem, możesz wybrać, czy podać argument. Jeśli tego nie zrobisz, procedura użyje wartości domyślnej zadeklarowanej dla tego parametru.  
  
 Jeżeli pomijasz jeden lub więcej argumentów opcjonalnych na liście argumentów, użyj kolejnych średników do oznaczania ich położenia. Następujący przykład wywołania dostarcza pierwszy i czwarty argument, a pomija drugi i trzeci:  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 Poniższy przykład wykonuje kilka wywołań do `MsgBox` funkcji. `MsgBox` ma jeden parametr wymagany i dwa parametry opcjonalne.  
  
 Pierwsze wywołanie `MsgBox` dostarcza wszystkie trzy argumenty w kolejności, `MsgBox` definiuje je. Drugie wywołanie dostarcza tylko wymagany argument. Wywołania trzecie i czwarte dostarczają argumenty pierwszy i trzeci. Trzecie wywołanie robi to według pozycji, a czwarte wywołanie — według nazwy.  
  
 [!code-vb[VbVbcnProcedures#47](./codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a>Określenie, czy opcjonalny argument jest obecny  
 Procedura nie może wykryć w czasie wykonywania, czy podany argument został pominięty lub kod wywołujący ma jawnie przekazywaną wartość domyślną. Jeśli potrzebujesz takiego rozróżnienia, możesz ustawić mało prawdopodobną wartość jako domyślną. Poniższa procedura określa opcjonalny parametr `office`i testuje jego wartość domyślną `QJZ`, aby zobaczyć, jeśli została pominięta w wywołaniu:  
  
 [!code-vb[VbVbcnProcedures#46](./codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 Jeśli parametr opcjonalny jest typem referencyjnym `String`, możesz użyć `Nothing` jako wartości domyślnej, pod warunkiem nie jest oczekiwana wartość dla argumentu.  
  
## <a name="optional-parameters-and-overloading"></a>Parametry opcjonalne i przeciążenie  
 Innym sposobem zdefiniowania procedury z opcjonalnymi parametrami jest używanie przeciążenia. Jeśli masz jeden parametr opcjonalny, możesz zdefiniować dwie przeciążone wersje procedury, jedną przyjmującą parametr i jedną bez niego. Takie podejście staje się bardziej skomplikowane w miarę wzrostu liczby parametrów opcjonalnych. Jej zaletą jest jednak, że możesz mieć absolutną pewność, czy program wywołujący dostarcza każdy opcjonalny argument.  
  
## <a name="see-also"></a>Zobacz także
- [Procedury](./index.md)
- [Parametry i argumenty procedur](./procedure-parameters-and-arguments.md)
- [Przekazywanie argumentów według wartości i według odwołania](./passing-arguments-by-value-and-by-reference.md)
- [Przekazywanie argumentów według pozycji i według nazwy](./passing-arguments-by-position-and-by-name.md)
- [Tablice parametrów](./parameter-arrays.md)
- [Przeciążanie procedury](./procedure-overloading.md)
- [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)
- [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
