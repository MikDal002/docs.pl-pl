---
title: "Porady: mierzenie wydajności zapytań PLINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03432e70454cb6203e55e340111a6cb7efe62dc4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-measure-plinq-query-performance"></a><span data-ttu-id="ea3dd-102">Porady: mierzenie wydajności zapytań PLINQ</span><span class="sxs-lookup"><span data-stu-id="ea3dd-102">How to: Measure PLINQ Query Performance</span></span>
<span data-ttu-id="ea3dd-103">W tym przykładzie przedstawiono sposób użycia <xref:System.Diagnostics.Stopwatch> klasy do mierzenia czas potrzebny na wykonanie zapytania PLINQ.</span><span class="sxs-lookup"><span data-stu-id="ea3dd-103">This example shows how use the <xref:System.Diagnostics.Stopwatch> class to measure the time it takes for a PLINQ query to execute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea3dd-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="ea3dd-104">Example</span></span>  
 <span data-ttu-id="ea3dd-105">W tym przykładzie użyto pustą `foreach` pętli (`For Each` w języku Visual Basic) do mierzenia na czas potrzebny na wykonanie kwerendy.</span><span class="sxs-lookup"><span data-stu-id="ea3dd-105">This example uses an empty `foreach` loop (`For Each` in Visual Basic) to measure the time it takes for the query to execute.</span></span> <span data-ttu-id="ea3dd-106">W kodzie rzeczywistych pętli zazwyczaj zawiera kroki dodatkowego przetwarzania, które czasu wykonywania kwerendy.</span><span class="sxs-lookup"><span data-stu-id="ea3dd-106">In real-world code, the loop typically contains additional processing steps that add to the total query execution time.</span></span> <span data-ttu-id="ea3dd-107">Należy zauważyć, że stopera nie jest uruchomione, dopóki tylko przed pętli, ponieważ jest to, kiedy rozpoczyna się wykonanie zapytania.</span><span class="sxs-lookup"><span data-stu-id="ea3dd-107">Notice that the stopwatch is not started until just before the loop, because that is when the query execution begins.</span></span> <span data-ttu-id="ea3dd-108">Jeśli potrzebujesz więcej szczegółowych pomiarów, możesz użyć `ElapsedTicks` właściwości zamiast `ElapsedMilliseconds`.</span><span class="sxs-lookup"><span data-stu-id="ea3dd-108">If you require more fine-grained measurement, you can use the `ElapsedTicks` property instead of `ElapsedMilliseconds`.</span></span>  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 <span data-ttu-id="ea3dd-109">Łączny czas wykonywania jest przydatne metryki, gdy są eksperymentowanie z implementacji kwerendy, ale nie zawsze powiadomi cały artykuł.</span><span class="sxs-lookup"><span data-stu-id="ea3dd-109">The total execution time is a useful metric when you are experimenting with query implementations, but it does not always tell the whole story.</span></span> <span data-ttu-id="ea3dd-110">Aby uzyskać bardziej i zaawansowaną widok interakcji wątków zapytania ze sobą oraz z innych procesów uruchomionych, korzystanie z wizualizatora współbieżności.</span><span class="sxs-lookup"><span data-stu-id="ea3dd-110">To get a deeper and richer view of the interaction of the query threads with one another and with other running processes, use the Concurrency Visualizer.</span></span> <span data-ttu-id="ea3dd-111">Aby uzyskać więcej informacji, zobacz [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span><span class="sxs-lookup"><span data-stu-id="ea3dd-111">For more information, see [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea3dd-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ea3dd-112">See Also</span></span>  
 [<span data-ttu-id="ea3dd-113">Równoległe LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="ea3dd-113">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)