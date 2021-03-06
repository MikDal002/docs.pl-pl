---
title: Thread.Suspend, odzyskiwanie pamięci i punkty bezpieczeństwa
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f3e44b81b519bcae42c2e69eff46e73b1ae631a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490807"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, odzyskiwanie pamięci i punkty bezpieczeństwa
Gdy wywołujesz <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> w wątku, system — informacje o że zawieszenia wątku zażądano i zezwala na wykonanie, dopóki osiągnie bezpieczny punkt rzeczywiście wstrzymania wątku wątku. Punkt bezpieczne dla wątków jest punktem w jej wykonanie w pamięci, które mogą być wykonywane kolekcji.  
  
 Po osiągnięciu punktu bezpiecznego środowiska wykonawczego gwarantuje, że wstrzymania wątku nie spowoduje żadnych dalszych postępów w kodzie zarządzanym. Wątek wykonywania poza zarządzanego kodu zawsze jest bezpieczny dla wyrzucania elementów bezużytecznych, a jego wykonywanie jest kontynuowane do czasu jej podejmie próbę wznowienia wykonywanie kodu zarządzanego.  
  
> [!NOTE]
>  Aby można było przeprowadzić wyrzucanie elementów bezużytecznych, środowisko wykonawcze musi zawiesić wszystkie wątki z wyjątkiem wątku wykonującego kolekcji. Każdy wątek można przełączyć do bezpiecznego punktu, zanim może zostać zawieszone.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Threading.Thread>
- <xref:System.GC>
- [Wątkowość](../../../docs/standard/threading/index.md)
- [Automatyczne zarządzanie pamięcią](../../../docs/standard/automatic-memory-management.md)
