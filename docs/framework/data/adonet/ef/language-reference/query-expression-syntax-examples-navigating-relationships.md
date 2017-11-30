---
title: "Przykłady składni wyrażeń zapytania: Nawigowanie po relacjach"
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
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d86fa3aab55daff9c7a3724c93ad68be27a6908b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a><span data-ttu-id="922fa-102">Przykłady składni wyrażeń zapytania: Nawigowanie po relacjach</span><span class="sxs-lookup"><span data-stu-id="922fa-102">Query Expression Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="922fa-103">Właściwości nawigacji w [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] są używane do lokalizowania jednostek na końcu skojarzenia właściwości skrótu.</span><span class="sxs-lookup"><span data-stu-id="922fa-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="922fa-104">Właściwości nawigacji zezwolić użytkownikowi na przechodzenie z jednego obiektu do innego, albo z jednego obiektu do powiązanych jednostek przez skojarzenie ustawiona.</span><span class="sxs-lookup"><span data-stu-id="922fa-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="922fa-105">W tym temacie przedstawiono przykłady w składni wyrażeń zapytania nawigowanie po relacjach za pośrednictwem właściwości nawigacji w [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] zapytania.</span><span class="sxs-lookup"><span data-stu-id="922fa-105">This topic provides examples in query expression syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="922fa-106">Model sprzedaży AdventureWorks używany w tym przykładzie jest tworzony z kontaktu, adres produktu, SalesOrderHeader i szczegóły zamówienia sprzedaży tabele w przykładowej bazie danych AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="922fa-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="922fa-107">Przykłady w tym temacie należy użyć następującego `using` / `Imports` instrukcji:</span><span class="sxs-lookup"><span data-stu-id="922fa-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="922fa-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="922fa-108">Example</span></span>  
 <span data-ttu-id="922fa-109">W poniższym przykładzie użyto <xref:System.Linq.Queryable.Select%2A> metody do pobrania wszystkich kontaktów identyfikatorów i sumy całkowitej ukończenia każdego skontaktuj się z których nazwisko jest "Zhou".</span><span class="sxs-lookup"><span data-stu-id="922fa-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="922fa-110">`Contact.SalesOrderHeader` Właściwość nawigacji jest używany do pobierania kolekcję `SalesOrderHeader` obiektów dla każdego kontakt.</span><span class="sxs-lookup"><span data-stu-id="922fa-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="922fa-111">`Sum` Używa metody `Contact.SalesOrderHeader` właściwości nawigacji do zsumowania łączną liczbę wszystkich zleceń dla każdego kontakt z powodu.</span><span class="sxs-lookup"><span data-stu-id="922fa-111">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a><span data-ttu-id="922fa-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="922fa-112">Example</span></span>  
 <span data-ttu-id="922fa-113">Poniższy przykład pobiera wszystkie zamówienia kontaktów, których nazwisko jest "Zhou".</span><span class="sxs-lookup"><span data-stu-id="922fa-113">The following example gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="922fa-114">`Contact.SalesOrderHeader` Właściwość nawigacji jest używany do pobierania kolekcję `SalesOrderHeader` obiektów dla każdego kontakt.</span><span class="sxs-lookup"><span data-stu-id="922fa-114">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="922fa-115">Nazwa kontaktu i zamówienia są zwracane w obrębie typu anonimowego.</span><span class="sxs-lookup"><span data-stu-id="922fa-115">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a><span data-ttu-id="922fa-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="922fa-116">Example</span></span>  
 <span data-ttu-id="922fa-117">W poniższym przykładzie użyto `SalesOrderHeader.Address` i `SalesOrderHeader.Contact` pobieranie właściwości nawigacji kolekcji z `Address` i `Contact` obiekty skojarzone z każdym kolejności.</span><span class="sxs-lookup"><span data-stu-id="922fa-117">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="922fa-118">Nazwisko osoby kontaktowej ulicę, zamówienia sprzedaży, liczby i całkowitej termin dla każdego celu Miasto Seattle są zwracane w obrębie typu anonimowego.</span><span class="sxs-lookup"><span data-stu-id="922fa-118">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a><span data-ttu-id="922fa-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="922fa-119">Example</span></span>  
 <span data-ttu-id="922fa-120">W poniższym przykładzie użyto `Where` metody do znalezienia zlecenia, które zostały dokonane po 1 grudnia 2003, a następnie używa `order.SalesOrderDetail` właściwość nawigacji, aby uzyskać szczegółowe informacje dla każdego zlecenia.</span><span class="sxs-lookup"><span data-stu-id="922fa-120">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="922fa-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="922fa-121">See Also</span></span>  
 [<span data-ttu-id="922fa-122">Zapytania w składniku LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="922fa-122">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)