---
title: "Porady: testowanie równości odwołań (tożsamości) (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2dbbd7c0e5ebb507ca3dda0f248d9f1c8f9595fe
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="99169-102">Porady: testowanie równości odwołań (tożsamości) (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="99169-102">How to: Test for Reference Equality (Identity) (C# Programming Guide)</span></span>
<span data-ttu-id="99169-103">Nie masz wdrożenia dowolnej niestandardowej logiki do obsługi odwołania porównywanie równości w typach sieci.</span><span class="sxs-lookup"><span data-stu-id="99169-103">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="99169-104">Ta funkcja jest udostępniane na potrzeby wszystkich typów statycznych <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="99169-104">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="99169-105">Poniższy przykład przedstawia sposób sprawdzić, czy dwie zmienne *odwołania równości*, co oznacza, że odnoszą się do tego samego obiektu w pamięci.</span><span class="sxs-lookup"><span data-stu-id="99169-105">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="99169-106">W przykładzie przedstawiono również Dlaczego <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> zawsze zwraca `false` dla typów wartości i dlaczego nie należy używać <xref:System.Object.ReferenceEquals%2A> do określenia ciągu równości.</span><span class="sxs-lookup"><span data-stu-id="99169-106">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99169-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="99169-107">Example</span></span>  
 [!code-csharp[csProgGuideObjects#90](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-test-for-reference-equality-identity_1.cs)]  
  
 <span data-ttu-id="99169-108">Implementacja `Equals` w <xref:System.Object?displayProperty=nameWithType> uniwersalnych klasy podstawowej również przeprowadza sprawdzanie równość odwołania, ale najlepiej nie można użyć, ponieważ w przypadku klasy Aby przesłonić metodę, wyniki mogą być oczekiwań.</span><span class="sxs-lookup"><span data-stu-id="99169-108">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="99169-109">Dotyczy to także `==` i `!=` operatorów.</span><span class="sxs-lookup"><span data-stu-id="99169-109">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="99169-110">Gdy działają w odwołaniu do typów domyślne zachowanie == i `!=` ma wykonywać sprawdzania równości odwołania.</span><span class="sxs-lookup"><span data-stu-id="99169-110">When they are operating on reference types, the default behavior of == and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="99169-111">Klasy pochodne mogą jednak przeciążenia operatora równości wartości sprawdzania.</span><span class="sxs-lookup"><span data-stu-id="99169-111">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="99169-112">Aby zminimalizować potencjalnych błędów, jest zawsze używać <xref:System.Object.ReferenceEquals%2A> gdy trzeba sprawdzić, czy dwa obiekty równości odwołań.</span><span class="sxs-lookup"><span data-stu-id="99169-112">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="99169-113">Stałe ciągów wewnątrz tego samego zestawu są zawsze interned w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="99169-113">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="99169-114">Oznacza to obsługiwane jest tylko jedno wystąpienie każdego unikatowy ciąg literału.</span><span class="sxs-lookup"><span data-stu-id="99169-114">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="99169-115">Jednak środowiska uruchomieniowego nie gwarantuje, że są interned ciągów utworzone w czasie wykonywania, ani gwarantuje to, że interned są takie same dwa ciągi stałej w różnych zestawach.</span><span class="sxs-lookup"><span data-stu-id="99169-115">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99169-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="99169-116">See Also</span></span>  
 [<span data-ttu-id="99169-117">Porównywanie równości</span><span class="sxs-lookup"><span data-stu-id="99169-117">Equality Comparisons</span></span>](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)