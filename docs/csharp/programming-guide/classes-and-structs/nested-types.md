---
title: "Zagnieżdżone typy (Przewodnik programowania w języku C#)"
ms.date: 07/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="9b5b5-102">Zagnieżdżone typy (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="9b5b5-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="9b5b5-103">Typ zdefiniowany w ramach [klasy](../../../csharp/language-reference/keywords/class.md) lub [struktury](../../../csharp/language-reference/keywords/struct.md) nosi nazwę typu zagnieżdżonego.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="9b5b5-104">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="9b5b5-104">For example:</span></span>  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
<span data-ttu-id="9b5b5-105">Niezależnie od tego, czy zewnętrznego typu klasy lub struktury, domyślnie zagnieżdżone typy [prywatnego](../../../csharp/language-reference/keywords/private.md); są one dostępne tylko z ich typu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="9b5b5-106">W poprzednim przykładzie `Nested` klasy jest niedostępna dla typów zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="9b5b5-107">Można również określić [modyfikator dostępu](../../language-reference/keywords/access-modifiers.md) do definiowania ułatwień dostępu typu zagnieżdżonego w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9b5b5-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="9b5b5-108">Zagnieżdżone typy **klasy** może być [publicznego](../../../csharp/language-reference/keywords/public.md), [chronione](../../../csharp/language-reference/keywords/protected.md), [wewnętrzny](../../../csharp/language-reference/keywords/internal.md), [chronionych wewnętrznych](../../../csharp/language-reference/keywords/protected-internal.md), [prywatnej](../../../csharp/language-reference/keywords/private.md) lub [prywatne chronione](../../../csharp/language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="9b5b5-108">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="9b5b5-109">Jednak definiowanie `protected`, `protected internal` lub `private protected` zagnieżdżona klasa wewnątrz [zapieczętowane klasy](../../language-reference/keywords/sealed.md) generuje ostrzeżenie kompilatora [CS0628](../../misc/cs0628.md), "w klasie zapieczętowanej zadeklarowano nowy chroniony element członkowski."</span><span class="sxs-lookup"><span data-stu-id="9b5b5-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="9b5b5-110">Zagnieżdżone typy **struktury** może być [publicznego](../../../csharp/language-reference/keywords/public.md), [wewnętrzny](../../../csharp/language-reference/keywords/internal.md), lub [prywatnej](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="9b5b5-110">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="9b5b5-111">Poniższy przykład powoduje, że `Nested` publicznej klasy:</span><span class="sxs-lookup"><span data-stu-id="9b5b5-111">The following example makes the `Nested` class public:</span></span>
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 <span data-ttu-id="9b5b5-112">Typ zagnieżdżony lub wewnętrznej, ma dostęp do typu zawierającego lub zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="9b5b5-113">Aby uzyskać dostęp do typu zawierającego, przekaż go jako argument do konstruktora typu zagnieżdżonego.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="9b5b5-114">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="9b5b5-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 <span data-ttu-id="9b5b5-115">Zagnieżdżony typ ma dostęp do wszystkich elementów członkowskich, które są dostępne dla jego typu zawierającego.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="9b5b5-116">Dostęp można uzyskać prywatnych i chronionych elementów członkowskich typu zawierającego tym dziedziczone chronionych elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="9b5b5-117">W poprzedniej deklaracji, pełna nazwa klasy `Nested` jest `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="9b5b5-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="9b5b5-118">Jest to nazwa użyty do utworzenia nowego wystąpienia klasy zagnieżdżone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9b5b5-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9b5b5-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9b5b5-119">See Also</span></span>  
 [<span data-ttu-id="9b5b5-120">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="9b5b5-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9b5b5-121">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="9b5b5-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="9b5b5-122">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="9b5b5-122">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="9b5b5-123">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="9b5b5-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)