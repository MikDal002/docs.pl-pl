---
title: 'Instrukcje: Definiowanie wielu wersji procedury (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
ms.openlocfilehash: a3f4657b22fe0a9186e339d00cd9341e55405244
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528878"
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a>Instrukcje: Definiowanie wielu wersji procedury (Visual Basic)
Procedurę można zdefiniować w wielu wersjach, *przeciążenie* go przy użyciu tej samej nazwie, ale inną listą parametrów dla każdej wersji. Przeciążanie ma na celu zdefiniować kilka wersji ściśle powiązanych procedury bez konieczności odróżnić je według nazwy.  
  
 Aby uzyskać więcej informacji, zobacz [przeciążanie procedury](./procedure-overloading.md).  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a>Aby zdefiniować wielu wersji procedury  
  
1.  Zapis `Sub` lub `Function` instrukcji deklaracji dla każdej wersji procedury, aby zdefiniować. Użyj tej samej nazwy procedury w każdej deklaracji.  
  
2.  Należy poprzedzić `Sub` lub `Function` — słowo kluczowe w każdej deklaracji z [przeciążenia](../../../../visual-basic/language-reference/modifiers/overloads.md) — słowo kluczowe. Opcjonalnie można pominąć `Overloads` w deklaracji, ale jeśli należy uwzględnić w deklaracji, należy ją dołączyć w każdej deklaracji.  
  
3.  Po każdej instrukcji deklaracji napisać kod procedury obsługi konkretnego przypadku, gdy kod wywołujący dostarcza argumentów dopasowania na liście parametrów tej wersji. Nie masz do testowania dla parametrów, które udostępnił kodu wywołującego. Visual Basic przekazuje sterowanie do tej samej wersji odpowiedniej procedury.  
  
4.  Zakończenie każdą wersję procedury z `End Sub` lub `End Function` instrukcji zgodnie z potrzebami.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie zdefiniowano `Sub` procedury, aby transakcję przed saldo odbiorcy. Używa ona `Overloads` — słowo kluczowe, aby zdefiniować dwie wersje procedury, taki, który akceptuje klientów według nazwy i innych przez numer konta.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 Kod wywołujący można uzyskać identyfikator klienta jako `String` lub `Integer`, a następnie użyć tej samej instrukcji wywołujące w obu przypadkach.  
  
 Aby uzyskać informacje dotyczące wywołań te wersje programu `post` procedury, zobacz [jak: Wywoływanie procedury przeciążenia](./how-to-call-an-overloaded-procedure.md).  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Upewnij się, że każdy z usługi przeciążone wersje ma taką samą nazwę procedury, ale z inną listą parametrów.  
  
## <a name="see-also"></a>Zobacz także
- [Procedury](./index.md)
- [Parametry i argumenty procedur](./procedure-parameters-and-arguments.md)
- [Rozwiązywanie problemów z procedurami](./troubleshooting-procedures.md)
- [Instrukcje: Przeciążanie procedury wykorzystującej parametry opcjonalne](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Instrukcje: Przeciążanie procedury wykorzystującej nieokreśloną liczbę parametrów](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Zagadnienia dotyczące przeciążania procedur](./considerations-in-overloading-procedures.md)
- [Rozpoznanie przeciążenia](./overload-resolution.md)
