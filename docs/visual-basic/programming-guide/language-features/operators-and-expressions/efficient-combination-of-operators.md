---
title: "Skuteczna kombinacja operatorów (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b0f1d637bc1757515cf271a8c70d62effab0843
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="efficient-combination-of-operators-visual-basic"></a><span data-ttu-id="0468d-102">Skuteczna kombinacja operatorów (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0468d-102">Efficient Combination of Operators (Visual Basic)</span></span>
<span data-ttu-id="0468d-103">Wyrażenia złożone może zawierać wielu różnych operatorów.</span><span class="sxs-lookup"><span data-stu-id="0468d-103">Complex expressions can contain many different operators.</span></span> <span data-ttu-id="0468d-104">Ilustruje to poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="0468d-104">The following example illustrates this.</span></span>  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 <span data-ttu-id="0468d-105">Tworzenie złożonych wyrażeń, takie jak w poprzednim przykładzie wymaga dogłębnej wiedzy reguły pierwszeństwo operatorów.</span><span class="sxs-lookup"><span data-stu-id="0468d-105">Creating complex expressions such as the one in the preceding example requires a thorough understanding of the rules of operator precedence.</span></span> <span data-ttu-id="0468d-106">Aby uzyskać więcej informacji, zobacz [kolejność wykonywania w języku Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span><span class="sxs-lookup"><span data-stu-id="0468d-106">For more information, see [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md).</span></span>  
  
## <a name="parenthetical-expressions"></a><span data-ttu-id="0468d-107">Wyrażenia w nawiasach</span><span class="sxs-lookup"><span data-stu-id="0468d-107">Parenthetical Expressions</span></span>  
 <span data-ttu-id="0468d-108">Często ma odbywać się w innym porządku niż określana przez kolejność wykonywania działań.</span><span class="sxs-lookup"><span data-stu-id="0468d-108">Often you want operations to proceed in a different order from that determined by operator precedence.</span></span> <span data-ttu-id="0468d-109">Rozważmy następujący przykład.</span><span class="sxs-lookup"><span data-stu-id="0468d-109">Consider the following example.</span></span>  
  
 `x = z * y + 4`  
  
 <span data-ttu-id="0468d-110">Mnoży w poprzednim przykładzie `z` przez `y`, następnie dodaje wynik do `4`.</span><span class="sxs-lookup"><span data-stu-id="0468d-110">The preceding example multiplies `z` by `y`, then adds the result to `4`.</span></span> <span data-ttu-id="0468d-111">Ale jeśli chcesz dodać `y` i `4` przed pomnożenia wyniku przez `z`, można zastąpić normalne kolejność za pomocą nawiasów.</span><span class="sxs-lookup"><span data-stu-id="0468d-111">But if you want to add `y` and `4` before multiplying the result by `z`, you can override normal operator precedence by using parentheses.</span></span> <span data-ttu-id="0468d-112">Umieszczając wyrażenia w nawiasach, możesz wymusić tego wyrażenia do obliczenia, niezależnie od tego, kolejność wykonywania działań.</span><span class="sxs-lookup"><span data-stu-id="0468d-112">By enclosing an expression in parentheses, you force that expression to be evaluated first, regardless of operator precedence.</span></span> <span data-ttu-id="0468d-113">Aby wymusić w poprzednim przykładzie w celu dodawania, można napisać ponownie jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0468d-113">To force the preceding example to do the addition first, you could rewrite it as in the following example.</span></span>  
  
 `x = z * (y + 4)`  
  
 <span data-ttu-id="0468d-114">W poprzednim przykładzie dodano `y` i `4`, następnie mnoży tej sumy przez `z`.</span><span class="sxs-lookup"><span data-stu-id="0468d-114">The preceding example adds `y` and `4`, then multiplies that sum by `z`.</span></span>  
  
### <a name="nested-parenthetical-expressions"></a><span data-ttu-id="0468d-115">Zagnieżdżone wyrażenia w nawiasach</span><span class="sxs-lookup"><span data-stu-id="0468d-115">Nested Parenthetical Expressions</span></span>  
 <span data-ttu-id="0468d-116">Można zagnieżdżać wyrażenia w nawiasy, aby zastąpić priorytet jeszcze bardziej wiele poziomów.</span><span class="sxs-lookup"><span data-stu-id="0468d-116">You can nest expressions in multiple levels of parentheses to override precedence even further.</span></span> <span data-ttu-id="0468d-117">Wyrażenia najbardziej głęboko zagnieżdżone w nawiasach są oceniane najpierw następuje dalej najbardziej głęboko zagnieżdżone, i tak dalej do najmniej głęboko zagnieżdżone, a na końcu wyrażeń poza nawiasów.</span><span class="sxs-lookup"><span data-stu-id="0468d-117">The expressions most deeply nested in parentheses are evaluated first, followed by the next most deeply nested, and so on to the least deeply nested, and finally the expressions outside parentheses.</span></span> <span data-ttu-id="0468d-118">Ilustruje to poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="0468d-118">The following example illustrates this.</span></span>  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 <span data-ttu-id="0468d-119">W powyższym przykładzie `z + 2` jest pierwszy ocenione, a następnie inne wyrażenia w nawiasach.</span><span class="sxs-lookup"><span data-stu-id="0468d-119">In the preceding example, `z + 2` is evaluated first, then the other parenthetical expressions.</span></span> <span data-ttu-id="0468d-120">Zapis wykładniczy, które zwykle mają wyższy priorytet niż dodawanie lub mnożenie, jest obliczane w ostatnio w tym przykładzie, ponieważ inne wyrażenia są ujęte w nawiasy.</span><span class="sxs-lookup"><span data-stu-id="0468d-120">Exponentiation, which normally has higher precedence than addition or multiplication, is evaluated last in this example because the other expressions are enclosed in parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0468d-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0468d-121">See Also</span></span>  
 [<span data-ttu-id="0468d-122">Operatory arytmetyczne w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0468d-122">Arithmetic Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [<span data-ttu-id="0468d-123">Operatory porównania w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0468d-123">Comparison Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [<span data-ttu-id="0468d-124">Operatory logiczne i bitowe w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0468d-124">Logical and Bitwise Operators in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [<span data-ttu-id="0468d-125">Operatory logiczne/bitowe (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0468d-125">Logical/Bitwise Operators (Visual Basic)</span></span>](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [<span data-ttu-id="0468d-126">Wyrażenia logiczne</span><span class="sxs-lookup"><span data-stu-id="0468d-126">Boolean Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="0468d-127">Porównania wartości</span><span class="sxs-lookup"><span data-stu-id="0468d-127">Value Comparisons</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="0468d-128">Porady: obliczanie wartości liczbowych</span><span class="sxs-lookup"><span data-stu-id="0468d-128">How to: Calculate Numeric Values</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)  
 [<span data-ttu-id="0468d-129">Kolejność wykonywania w języku Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0468d-129">Operator Precedence in Visual Basic</span></span>](../../../../visual-basic/language-reference/operators/operator-precedence.md)