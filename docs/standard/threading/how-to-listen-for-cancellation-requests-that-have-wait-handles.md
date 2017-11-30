---
title: "Porady: nasłuchiwanie żądań anulowania z dojściami oczekiwania"
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
helpviewer_keywords: cancellation, waiting with wait handles
ms.assetid: 6e2aa49b-fc84-4bcf-962b-17db98b7edcb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1eaa84d924fde63e94c36fab50a809c7c03f075
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-that-have-wait-handles"></a><span data-ttu-id="e2276-102">Porady: nasłuchiwanie żądań anulowania z dojściami oczekiwania</span><span class="sxs-lookup"><span data-stu-id="e2276-102">How to: Listen for Cancellation Requests That Have Wait Handles</span></span>
<span data-ttu-id="e2276-103">Metody zostało zablokowane, gdy oczekuje na zdarzenie, aby zostać zgłoszony, nie można sprawdzić wartość token anulowania ani odpowiadają w odpowiednim czasie.</span><span class="sxs-lookup"><span data-stu-id="e2276-103">If a method is blocked while it is waiting for an event to be signaled, it cannot check the value of the cancellation token and respond in a timely manner.</span></span> <span data-ttu-id="e2276-104">Pierwszym przykładzie pokazano, jak rozwiązać ten problem, podczas pracy ze zdarzeniami takich jak <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> które nie obsługują natywnie framework ujednoliconego anulowania.</span><span class="sxs-lookup"><span data-stu-id="e2276-104">The first example shows how to solve this problem when you are working with events such as <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> that do not natively support the unified cancellation framework.</span></span> <span data-ttu-id="e2276-105">Drugi przykład przedstawia usprawnić podejście, która używa <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, który obsługuje unified anulowania.</span><span class="sxs-lookup"><span data-stu-id="e2276-105">The second example shows a more streamlined approach that uses <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>, which does support unified cancellation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2276-106">Po włączeniu "Tylko mój kod" programu Visual Studio w niektórych przypadkach będzie podział wiersza, która zgłasza wyjątek i wyświetlony komunikat o błędzie stwierdzający "wyjątek nie obsłużony przez kod użytkownika."</span><span class="sxs-lookup"><span data-stu-id="e2276-106">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="e2276-107">Ten błąd jest niegroźne.</span><span class="sxs-lookup"><span data-stu-id="e2276-107">This error is benign.</span></span> <span data-ttu-id="e2276-108">Naciśnij klawisz F5, aby nadal z niego i zachowanie obsługi wyjątków, które przedstawiono w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="e2276-108">You can press F5 to continue from it, and see the exception-handling behavior that is demonstrated in the examples below.</span></span> <span data-ttu-id="e2276-109">Aby zapobiec dzieleniu pierwszego błędu w Visual Studio, wystarczy usunąć zaznaczenie pola wyboru "Tylko mój kod" w obszarze **narzędzia, opcje, debugowanie, ogólne**.</span><span class="sxs-lookup"><span data-stu-id="e2276-109">To prevent Visual Studio from breaking on the first error, just uncheck the "Just My Code" checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2276-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2276-110">Example</span></span>  
 <span data-ttu-id="e2276-111">W poniższym przykładzie użyto <xref:System.Threading.ManualResetEvent> aby zademonstrować sposób odblokowania uchwyty oczekiwania, które nie obsługują ujednoliconego anulowania.</span><span class="sxs-lookup"><span data-stu-id="e2276-111">The following example uses a <xref:System.Threading.ManualResetEvent> to demonstrate how to unblock wait handles that do not support unified cancellation.</span></span>  
  
 [!code-csharp[Cancellation#9](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex9.cs#9)]
 [!code-vb[Cancellation#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex9.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="e2276-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="e2276-112">Example</span></span>  
 <span data-ttu-id="e2276-113">W poniższym przykładzie użyto <xref:System.Threading.ManualResetEventSlim> pokazujący sposób odblokować koordynacji podstawowych, które obsługują unified anulowania.</span><span class="sxs-lookup"><span data-stu-id="e2276-113">The following example uses a <xref:System.Threading.ManualResetEventSlim> to demonstrate how to unblock coordination primitives that do support unified cancellation.</span></span> <span data-ttu-id="e2276-114">Te same podejście może być używany z innych podstawowych koordynacji lekkie, takich jak <xref:System.Threading.Semaphore> `Slim` i <xref:System.Threading.CountdownEvent>.</span><span class="sxs-lookup"><span data-stu-id="e2276-114">The same approach can be used with other lightweight coordination primitives, such as <xref:System.Threading.Semaphore>`Slim` and <xref:System.Threading.CountdownEvent>.</span></span>  
  
 [!code-csharp[Cancellation#10](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex10.cs#10)]
 [!code-vb[Cancellation#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex10.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="e2276-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e2276-115">See Also</span></span>  
 [<span data-ttu-id="e2276-116">Anulowanie w zarządzanych wątkach</span><span class="sxs-lookup"><span data-stu-id="e2276-116">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)