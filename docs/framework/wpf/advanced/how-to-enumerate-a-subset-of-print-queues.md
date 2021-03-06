---
title: 'Instrukcje: Wykaż podzbiór kolejek drukowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: e1cbd9e7332a5e021e1cf9fba75f6d21ae01582b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558569"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>Instrukcje: Wykaż podzbiór kolejek drukowania
Typowe sytuacji sterowaną przez specjalistów technologii informatycznych (IT), zarządzanie zbiór drukarek w firmie polega na generowaniu listę drukarek mające określoną wspólną charakterystykę. Ta funkcjonalność jest dostarczana przez <xref:System.Printing.PrintServer.GetPrintQueues%2A> metody <xref:System.Printing.PrintServer> obiektu i <xref:System.Printing.EnumeratedPrintQueueTypes> wyliczenia.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie na początku kodu, tworząc tablicę flagi określające właściwości kolejki wydruku, którą chcemy, aby wyświetlić listę. W tym przykładzie firma Microsoft szuka kolejki wydruku, są instalowane lokalnie na serwerze wydruku, które są udostępniane. <xref:System.Printing.EnumeratedPrintQueueTypes> Wyliczenia zawiera wiele innych możliwości.  
  
 Następnie kod tworzy <xref:System.Printing.LocalPrintServer> obiektu z klasą pochodną <xref:System.Printing.PrintServer>. Lokalny serwer wydruku jest komputer, na którym działa aplikacja.  
  
 Ostatnim krokiem znaczące służy do przekazywania macierzy <xref:System.Printing.PrintServer.GetPrintQueues%2A> metody.  
  
 Na koniec wyniki są prezentowane użytkownikowi.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 W tym przykładzie można rozszerzyć przez `foreach` pętli, który przeprowadza użytkownika przez proces każdej kolejki wydruku do dalszego kontroli. Na przykład użytkownik może sprawia, drukarki, które nie obsługują drukowania dwustronnego przez wywołanie pętli każdej kolejki wydruku <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> metody i testowania zwracanej wartości na obecność dupleksu.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [Dokumenty w WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Przegląd drukowania](../../../../docs/framework/wpf/advanced/printing-overview.md)
- [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319)
