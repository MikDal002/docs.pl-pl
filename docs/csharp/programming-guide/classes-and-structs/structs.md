---
title: "Struktury (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 475d9b96e078270faf6c841a62e6031556e8e539
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="a6530-102">Struktury (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="a6530-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="a6530-103">Struktury są zdefiniowane przy użyciu [struktury](../../../csharp/language-reference/keywords/struct.md) — słowo kluczowe, na przykład:</span><span class="sxs-lookup"><span data-stu-id="a6530-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="a6530-104">Struktury udziału większość takiej samej składni jak klasy, struktury są bardziej ograniczone niż klasy:</span><span class="sxs-lookup"><span data-stu-id="a6530-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="a6530-105">W deklaracji struktury pól nie można zainicjować, chyba że zostały zgłoszone jako const lub statycznej.</span><span class="sxs-lookup"><span data-stu-id="a6530-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="a6530-106">Struktury nie można zadeklarować konstruktora domyślnego (Konstruktor bez parametrów) lub finalizatora.</span><span class="sxs-lookup"><span data-stu-id="a6530-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="a6530-107">Struktury są kopiowane na przypisanie.</span><span class="sxs-lookup"><span data-stu-id="a6530-107">Structs are copied on assignment.</span></span> <span data-ttu-id="a6530-108">Gdy struktury jest przypisany do nowej zmiennej, wszystkie dane zostaną skopiowane, a wszelkie zmiany nowej kopii nie zmienia dane oryginał.</span><span class="sxs-lookup"><span data-stu-id="a6530-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="a6530-109">Jest to ważne podczas pracy z kolekcjami typów wartości, takich jak słownik\<ciąg, myStruct >.</span><span class="sxs-lookup"><span data-stu-id="a6530-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="a6530-110">Struktury są typy wartości i typy referencyjne występują następujące klasy.</span><span class="sxs-lookup"><span data-stu-id="a6530-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="a6530-111">W przeciwieństwie do klasy, struktury można wdrożyć bez użycia `new` operatora.</span><span class="sxs-lookup"><span data-stu-id="a6530-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="a6530-112">Struktury mogą zadeklarować konstruktorów, które mają parametry.</span><span class="sxs-lookup"><span data-stu-id="a6530-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="a6530-113">Struktury nie może dziedziczyć z innego struktury lub klasy, a nie może być podstawą klasy.</span><span class="sxs-lookup"><span data-stu-id="a6530-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="a6530-114">Strukturami dziedziczyć bezpośrednio po `System.ValueType`, który dziedziczy z `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="a6530-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="a6530-115">Struktury mogą implementować interfejsów.</span><span class="sxs-lookup"><span data-stu-id="a6530-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="a6530-116">Struktury mogą być używane jako typ dopuszczający wartość null i można przypisać wartości null.</span><span class="sxs-lookup"><span data-stu-id="a6530-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a6530-117">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="a6530-117">Related Sections</span></span>  
 <span data-ttu-id="a6530-118">Informacje dodatkowe:</span><span class="sxs-lookup"><span data-stu-id="a6530-118">For more information:</span></span>  
  
-   [<span data-ttu-id="a6530-119">Używanie struktur</span><span class="sxs-lookup"><span data-stu-id="a6530-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="a6530-120">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="a6530-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="a6530-121">Typy dopuszczające wartości zerowe</span><span class="sxs-lookup"><span data-stu-id="a6530-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="a6530-122">Porady: różnica między przekazywaniem struktury a przekazywaniem odwołań do klas do metody</span><span class="sxs-lookup"><span data-stu-id="a6530-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="a6530-123">Porady: Implementowanie zdefiniowanych przez użytkownika konwersji struktur</span><span class="sxs-lookup"><span data-stu-id="a6530-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="a6530-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a6530-124">See Also</span></span>  
 [<span data-ttu-id="a6530-125">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="a6530-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a6530-126">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="a6530-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="a6530-127">Klasy</span><span class="sxs-lookup"><span data-stu-id="a6530-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)