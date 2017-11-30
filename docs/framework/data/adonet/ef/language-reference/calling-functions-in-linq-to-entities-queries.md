---
title: "Wywoływanie funkcji w składniku LINQ to Entities zapytań"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12a525a9-727c-4464-a0c7-71a0ef541792
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6e50147d356ad9e389a87868205bb9b8b6b3e7b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="calling-functions-in-linq-to-entities-queries"></a><span data-ttu-id="12080-102">Wywoływanie funkcji w składniku LINQ to Entities zapytań</span><span class="sxs-lookup"><span data-stu-id="12080-102">Calling Functions in LINQ to Entities Queries</span></span>
<span data-ttu-id="12080-103">Tematy w tej sekcji opisano sposób wywołania funkcji w składniku LINQ do jednostek zapytań.</span><span class="sxs-lookup"><span data-stu-id="12080-103">The topics in this section describe how to call functions in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="12080-104"><xref:System.Data.Objects.EntityFunctions> i <xref:System.Data.Objects.SqlClient.SqlFunctions> klasy zapewniają dostęp do kanonicznej i funkcje bazy danych jako część programu Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="12080-104">The <xref:System.Data.Objects.EntityFunctions> and <xref:System.Data.Objects.SqlClient.SqlFunctions> classes provide access to canonical and database functions as part of the Entity Framework.</span></span> <span data-ttu-id="12080-105">Aby uzyskać więcej informacji, zobacz [jak: wywołanie funkcji kanonicznej](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) i [jak: Wywołaj funkcje bazy danych](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span><span class="sxs-lookup"><span data-stu-id="12080-105">For more information, see [How to: Call Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md) and [How to: Call Database Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md).</span></span>  
  
 <span data-ttu-id="12080-106">Proces wywoływania funkcji niestandardowej wymaga trzy podstawowe czynności:</span><span class="sxs-lookup"><span data-stu-id="12080-106">The process for calling a custom function requires three basic steps:</span></span>  
  
1.  <span data-ttu-id="12080-107">Zdefiniuj funkcję w modelu koncepcyjnym lub zadeklarowania funkcji w modelu magazynu.</span><span class="sxs-lookup"><span data-stu-id="12080-107">Define a function in your conceptual model or declare a function in your storage model.</span></span>  
  
2.  <span data-ttu-id="12080-108">Dodawanie metody do aplikacji i mapowanie go do funkcji w modelu o <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="12080-108">Add a method to your application and map it to the function in the model with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span>  
  
3.  <span data-ttu-id="12080-109">Wywołanie funkcji w zapytaniu składnika LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="12080-109">Call the function in a LINQ to Entities query.</span></span>  
  
 <span data-ttu-id="12080-110">Aby uzyskać więcej informacji zobacz Tematy w tej sekcji.</span><span class="sxs-lookup"><span data-stu-id="12080-110">For more information, see the topics in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12080-111">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="12080-111">In This Section</span></span>  
 [<span data-ttu-id="12080-112">Porady: wywoływać funkcje kanoniczny</span><span class="sxs-lookup"><span data-stu-id="12080-112">How to: Call Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-canonical-functions.md)  
  
 [<span data-ttu-id="12080-113">Porady: Wywołaj funkcje bazy danych</span><span class="sxs-lookup"><span data-stu-id="12080-113">How to: Call Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-database-functions.md)  
  
 [<span data-ttu-id="12080-114">Porady: wywoływać funkcje w niestandardowej bazie danych</span><span class="sxs-lookup"><span data-stu-id="12080-114">How to: Call Custom Database Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-custom-database-functions.md)  
  
 [<span data-ttu-id="12080-115">Porady: Wywołaj funkcje zdefiniowane przez Model w zapytaniach</span><span class="sxs-lookup"><span data-stu-id="12080-115">How to: Call Model-Defined Functions in Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)  
  
 [<span data-ttu-id="12080-116">Porady: Wywołaj funkcje zdefiniowane przez Model, jako metody obiektów</span><span class="sxs-lookup"><span data-stu-id="12080-116">How to: Call Model-Defined Functions as Object Methods</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-as-object-methods.md)  
  
## <a name="see-also"></a><span data-ttu-id="12080-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="12080-117">See Also</span></span>  
 [<span data-ttu-id="12080-118">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="12080-118">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
 [<span data-ttu-id="12080-119">Canonical funkcji</span><span class="sxs-lookup"><span data-stu-id="12080-119">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)  
 [<span data-ttu-id="12080-120">Omówienie plików edmx</span><span class="sxs-lookup"><span data-stu-id="12080-120">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="12080-121">Porady: Definiowanie funkcji niestandardowych w modelu koncepcyjnym</span><span class="sxs-lookup"><span data-stu-id="12080-121">How to: Define Custom Functions in the Conceptual Model</span></span>](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)