---
title: 'Instrukcje: Wywoływanie procedury, która nie zwraca wartości (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: f85c7a7edf4d05dc50166ad4f30080c2e595cf65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590646"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Instrukcje: Wywoływanie procedury, która nie zwraca wartości (Visual Basic)
A `Sub` procedury nie zwraca wartości do wywołującego kodu. Możesz wywołać ją jawnie za pomocą autonomicznego instrukcji wywołujące. Nie można jej wywołać przy użyciu jego nazwy w wyrażeniu.  
  
### <a name="to-call-a-sub-procedure"></a>Aby wywołać procedurę Sub  
  
1.  Określ nazwę `Sub` procedury.  
  
2.  Postępuj zgodnie z nazwą procedury należy umieścić na liście argumentów za pomocą nawiasów. Jeśli nie ma żadnych argumentów, opcjonalnie można pominąć nawiasów. Jednak przy użyciu nawiasów sprawia, że Twój kod łatwiejsza do odczytania.  
  
3.  Argumenty należy umieścić na liście argumentów w nawiasie rozdzielone przecinkami. Należy podać argumenty w tej samej kolejności, `Sub` procedura określa odpowiednich parametrów.  
  
     Poniższy przykład wywołuje Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> funkcję, aby aktywować okna aplikacji. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> pobiera tytuł okna jako jedyny argument. Nie zwraca wartości do wywołującego kodu. Jeśli nie jest uruchomiony proces Notatnik, przykład generuje <xref:System.ArgumentException>. `Shell` Procedurze przyjęto założenie, znajdują się w określonej ścieżce.  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Procedury](./index.md)
- [Sub, procedury](./sub-procedures.md)
- [Parametry i argumenty procedur](./procedure-parameters-and-arguments.md)
- [Sub, instrukcja](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Instrukcje: Tworzenie procedury](./how-to-create-a-procedure.md)
- [Instrukcje: Wywoływanie procedury zwracającej wartość](./how-to-call-a-procedure-that-returns-a-value.md)
- [Instrukcje: Wywoływanie programu do obsługi zdarzeń w języku Visual Basic](./how-to-call-an-event-handler.md)
