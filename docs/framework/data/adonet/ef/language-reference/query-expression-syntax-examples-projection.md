---
title: "Przykłady składni wyrażeń zapytania: projekcji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 83d4f1e68938d4aa7330fbcacb40c44b3c06e400
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-projection"></a><span data-ttu-id="96743-102">Przykłady składni wyrażeń zapytania: projekcji</span><span class="sxs-lookup"><span data-stu-id="96743-102">Query Expression Syntax Examples: Projection</span></span>
<span data-ttu-id="96743-103">Przykłady w tym temacie przedstawiają sposób użycia `Select` — metoda i `From … From …` słowa kluczowe zapytania [modelu sprzedaży AdventureWorks](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) przy użyciu składni wyrażenia zapytania.</span><span class="sxs-lookup"><span data-stu-id="96743-103">The examples in this topic demonstrate how to use the `Select` method and the `From … From …` keywords to query the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) using query expression syntax.</span></span> <span data-ttu-id="96743-104">`From … From …`jest odpowiednikiem kwerendy na podstawie `SelectMany` metody.</span><span class="sxs-lookup"><span data-stu-id="96743-104">`From … From …` is the query based equivalent of the `SelectMany` method.</span></span> <span data-ttu-id="96743-105">Model sprzedaży AdventureWorks używany w tym przykładzie składa się z kontaktu, adres produktu, SalesOrderHeader i szczegóły zamówienia sprzedaży tabele w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="96743-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="96743-106">Przykłady w tym temacie należy użyć następującego `using` / `Imports` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="96743-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="96743-107">Wybierz</span><span class="sxs-lookup"><span data-stu-id="96743-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="96743-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="96743-108">Example</span></span>  
 <span data-ttu-id="96743-109">W poniższym przykładzie użyto <xref:System.Linq.Enumerable.Select%2A> metodę zwracanie wszystkich wierszy z `Product` tabelę i wyświetlić nazwy produktu.</span><span class="sxs-lookup"><span data-stu-id="96743-109">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="96743-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="96743-110">Example</span></span>  
 <span data-ttu-id="96743-111">W poniższym przykładzie użyto <xref:System.Linq.Enumerable.Select%2A> do zwrócenia sekwencję tylko nazwy produktu.</span><span class="sxs-lookup"><span data-stu-id="96743-111">The following example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a><span data-ttu-id="96743-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="96743-112">Example</span></span>  
 <span data-ttu-id="96743-113">W poniższym przykładzie użyto <xref:System.Linq.Queryable.Select%2A> metody do projektu `Product.Name` i `Product.ProductID` właściwości do sekwencji typy anonimowe.</span><span class="sxs-lookup"><span data-stu-id="96743-113">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a><span data-ttu-id="96743-114">Z...</span><span class="sxs-lookup"><span data-stu-id="96743-114">From …</span></span> <span data-ttu-id="96743-115">Z...</span><span class="sxs-lookup"><span data-stu-id="96743-115">From …</span></span> <span data-ttu-id="96743-116">(Operacja SelectMany)</span><span class="sxs-lookup"><span data-stu-id="96743-116">(SelectMany)</span></span>  
  
### <a name="example"></a><span data-ttu-id="96743-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="96743-117">Example</span></span>  
 <span data-ttu-id="96743-118">W poniższym przykładzie użyto `From … From …` (odpowiednik <xref:System.Linq.Enumerable.SelectMany%2A> metody) aby wybrać wszystkie porządkuje where `TotalDue` jest mniejsza niż 500,00.</span><span class="sxs-lookup"><span data-stu-id="96743-118">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="96743-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="96743-119">Example</span></span>  
 <span data-ttu-id="96743-120">W poniższym przykładzie użyto `From … From …` (odpowiednik <xref:System.Linq.Enumerable.SelectMany%2A> metody) do wybrania wszystkich zleceń, których kolejność została wprowadzona w 1 października 2002 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="96743-120">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="96743-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="96743-121">Example</span></span>  
 <span data-ttu-id="96743-122">W poniższym przykładzie użyto `From … From …` (odpowiednikiem <xref:System.Linq.Enumerable.SelectMany%2A> — metoda) do wszystkich zleceń, których kolejność całkowita liczba jest większa niż 10000.00 i używa wybierz `From` przypisania, aby uniknąć żąda łączną dwa razy.</span><span class="sxs-lookup"><span data-stu-id="96743-122">The following example uses a `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="96743-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96743-123">See Also</span></span>  
 [<span data-ttu-id="96743-124">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="96743-124">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)