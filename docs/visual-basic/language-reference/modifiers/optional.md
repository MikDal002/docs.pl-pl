---
title: Optional (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a><span data-ttu-id="71a54-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71a54-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="71a54-103">Określa, że argument procedury można pominąć, gdy procedura jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="71a54-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71a54-104">Uwagi</span><span class="sxs-lookup"><span data-stu-id="71a54-104">Remarks</span></span>  
 <span data-ttu-id="71a54-105">Dla każdego parametru opcjonalnego wartością domyślną tego parametru należy określić wyrażenie stałe.</span><span class="sxs-lookup"><span data-stu-id="71a54-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="71a54-106">Jeśli wyrażenie ma [nic](../../../visual-basic/language-reference/nothing.md), wartość domyślna typu danych wartość jest używana jako wartość domyślna parametru.</span><span class="sxs-lookup"><span data-stu-id="71a54-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="71a54-107">Jeśli lista parametrów zawiera parametr opcjonalny, każdy parametr następującym musi być opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="71a54-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="71a54-108">`Optional` Modyfikatora można używać w tych sytuacjach:</span><span class="sxs-lookup"><span data-stu-id="71a54-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="71a54-109">DECLARE — instrukcja</span><span class="sxs-lookup"><span data-stu-id="71a54-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="71a54-110">Function — instrukcja</span><span class="sxs-lookup"><span data-stu-id="71a54-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="71a54-111">Property — instrukcja</span><span class="sxs-lookup"><span data-stu-id="71a54-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="71a54-112">Sub — instrukcja</span><span class="sxs-lookup"><span data-stu-id="71a54-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="71a54-113">Podczas wywoływania procedury z lub bez parametrów, można przekazywać argumenty, według położenia lub nazwy.</span><span class="sxs-lookup"><span data-stu-id="71a54-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="71a54-114">Aby uzyskać więcej informacji, zobacz [przekazywanie argumentów według pozycji i według nazwy](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="71a54-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71a54-115">Można również definiować procedury z opcjonalnymi parametrami za pomocą przeciążenia.</span><span class="sxs-lookup"><span data-stu-id="71a54-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="71a54-116">Jeśli masz jeden opcjonalny parametr można zdefiniować dwie wersje przeciążone procedurą, który akceptuje parametr i bez.</span><span class="sxs-lookup"><span data-stu-id="71a54-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="71a54-117">Aby uzyskać więcej informacji, zobacz [przeciążanie procedury](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="71a54-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71a54-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="71a54-118">Example</span></span>  
 <span data-ttu-id="71a54-119">W poniższym przykładzie zdefiniowano procedury, która ma parametr opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="71a54-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="71a54-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="71a54-120">Example</span></span>  
 <span data-ttu-id="71a54-121">W poniższym przykładzie pokazano sposób wywołania procedury z argumentów przekazywanych według pozycji i argumenty przekazane według nazwy.</span><span class="sxs-lookup"><span data-stu-id="71a54-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="71a54-122">Procedura zawiera dwa parametry opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="71a54-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="71a54-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="71a54-123">See Also</span></span>  
 [<span data-ttu-id="71a54-124">Listy parametrów</span><span class="sxs-lookup"><span data-stu-id="71a54-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="71a54-125">Parametry opcjonalne</span><span class="sxs-lookup"><span data-stu-id="71a54-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="71a54-126">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="71a54-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)