---
title: 'Porady: włączanie śledzenia wątków w strukturze SpinLock'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3b9671c10889287bc22d64df1fb5c3a2984bd55
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2018
ms.locfileid: "44195283"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Porady: włączanie śledzenia wątków w strukturze SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType> jest blokadę niskiego poziomu wzajemne wykluczenie, która służy do scenariuszy, które mają bardzo krótkim czasie oczekiwania, czas. <xref:System.Threading.SpinLock> nie jest wielobieżnej. Po wątku przechodzi blokady, jego musi się zakończyć blokady poprawnie przed można wprowadzić ponownie. Zwykle wszelkie próby ponownego wprowadzania blokady spowodowałoby zakleszczenia i zakleszczenia mogą być bardzo trudne do debugowania. Jako pomoc do tworzenia <xref:System.Threading.SpinLock?displayProperty=nameWithType> obsługuje tryb śledzenia wątków, który powoduje wyjątek zgłaszany, gdy wątek próbuje ponownie wprowadź blokadę, który już posiada. Dzięki temu można więcej łatwy dostęp do punktu, jaką blokady nie został zakończony poprawnie. Tryb śledzenia wątków można włączyć za pomocą <xref:System.Threading.SpinLock> konstruktora, który przyjmuje wartość logiczną wprowadź parametr i przekazywanie w argumencie `true`. Po zakończeniu tworzenia i testowania fazy wyłączyć tryb śledzenia wątków w celu zapewnienia lepszej wydajności.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano śledzenia wątków. Wiersze, które poprawnie zamknąć blokady są ujęte w komentarz do symulacji błędu w kodzie, który powoduje, że jeden z następujących wyników:  
  
-   Wyjątek jest generowany, jeśli <xref:System.Threading.SpinLock> został utworzony przy użyciu argumentu `true` (`True` w języku Visual Basic).  
  
-   Zakleszczenie Jeśli <xref:System.Threading.SpinLock> został utworzony przy użyciu argumentu `false` (`False` w języku Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>Zobacz także

- [SpinLock](../../../docs/standard/threading/spinlock.md)
