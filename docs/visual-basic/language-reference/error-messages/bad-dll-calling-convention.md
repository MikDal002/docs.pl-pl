---
title: Nieprawidłowa konwencja wywoływania biblioteki DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
ms.openlocfilehash: 70200b38ea3d1497daa091fa407accabaf3c4eda
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715780"
---
# <a name="bad-dll-calling-convention"></a>Nieprawidłowa konwencja wywoływania biblioteki DLL
Argumenty przekazane do biblioteki dołączanej (dynamicznie DLL) musi dokładnie odpowiadać ich z oczekiwanymi przez procedura. Konwencje wywoływania zajmuje się numer, typ i kolejność argumentów. Program może wywołania procedury w bibliotekę DLL, która jest przekazywana nieprawidłowego typu lub liczbę argumentów.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1.  Upewnij się, że wszystkie typy argumentów zgadzają się z tymi określonym w deklaracji procedury, którą wywołujesz.  
  
2.  Upewnij się, że przekazujesz taką samą liczbę argumentów wskazane w deklaracji procedury, którą wywołujesz.  
  
3.  Jeśli procedura DLL oczekuje argumentów według wartości, upewnij się, `ByVal` dla tych argumentów w deklaracji dla procedury określono.  
  
## <a name="see-also"></a>Zobacz także
- [Typy błędów](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Call, instrukcja](../../../visual-basic/language-reference/statements/call-statement.md)
- [Declare, instrukcja](../../../visual-basic/language-reference/statements/declare-statement.md)
