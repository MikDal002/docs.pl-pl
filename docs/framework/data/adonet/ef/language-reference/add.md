---
title: + (Dodaj)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 32c661ff36e3dcdcdadfc892267cc9e5354cbe5b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="-add"></a><span data-ttu-id="9c303-102">+ (Dodaj)</span><span class="sxs-lookup"><span data-stu-id="9c303-102">+ (Add)</span></span>
<span data-ttu-id="9c303-103">Dodaje dwie liczby.</span><span class="sxs-lookup"><span data-stu-id="9c303-103">Adds two numbers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c303-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="9c303-104">Syntax</span></span>  
  
```  
expression + expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="9c303-105">Argumenty</span><span class="sxs-lookup"><span data-stu-id="9c303-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="9c303-106">Dowolne prawidłowe wyrażenie jednego z typów numerycznych.</span><span class="sxs-lookup"><span data-stu-id="9c303-106">Any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="9c303-107">Typy wyników</span><span class="sxs-lookup"><span data-stu-id="9c303-107">Result Types</span></span>  
 <span data-ttu-id="9c303-108">Typ danych, który powoduje z typem niejawnym promocji dwa argumenty.</span><span class="sxs-lookup"><span data-stu-id="9c303-108">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="9c303-109">Aby uzyskać więcej informacji na temat podwyższania poziomu typu niejawnego zobacz [System typów](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="9c303-109">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c303-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9c303-110">Remarks</span></span>  
 <span data-ttu-id="9c303-111">Dla EDM. Parametry typów, dodanie jest łączenia.</span><span class="sxs-lookup"><span data-stu-id="9c303-111">For EDM.String types, addition is concatenation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c303-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="9c303-112">Example</span></span>  
 <span data-ttu-id="9c303-113">Następujące zapytanie SQL jednostki używa + operatora arytmetycznego można dodać dwóch liczb.</span><span class="sxs-lookup"><span data-stu-id="9c303-113">The following Entity SQL query uses the + arithmetic operator to add two numbers.</span></span> <span data-ttu-id="9c303-114">Kwerenda jest oparta na modelu sprzedaży AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="9c303-114">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="9c303-115">Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="9c303-115">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="9c303-116">Postępuj zgodnie z procedurą w [porady: wykonywanie zapytań tego zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="9c303-116">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="9c303-117">Przekaż następujące zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:</span><span class="sxs-lookup"><span data-stu-id="9c303-117">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a><span data-ttu-id="9c303-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9c303-118">See Also</span></span>  
 [<span data-ttu-id="9c303-119">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="9c303-119">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="9c303-120">Typy modelu koncepcyjnego (CSDL)</span><span class="sxs-lookup"><span data-stu-id="9c303-120">Conceptual Model Types (CSDL)</span></span>](http://msdn.microsoft.com/en-us/987b995f-e429-4569-9559-b4146744def4)