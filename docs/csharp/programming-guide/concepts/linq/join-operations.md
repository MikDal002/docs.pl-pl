---
title: "Dołącz do operacji (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 158d035985dae0d1c1daf0f276a9df7b913f2263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="join-operations-c"></a><span data-ttu-id="1175a-102">Dołącz do operacji (C#)</span><span class="sxs-lookup"><span data-stu-id="1175a-102">Join Operations (C#)</span></span>
<span data-ttu-id="1175a-103">A *sprzężenia* dwóch źródeł danych jest skojarzenie obiektów w jedno źródło danych z obiektami, które mają wspólny atrybut w innym źródłem danych.</span><span class="sxs-lookup"><span data-stu-id="1175a-103">A *join* of two data sources is the association of objects in one data source with objects that share a common attribute in another data source.</span></span>  
  
 <span data-ttu-id="1175a-104">Sprzęganie jest ważne operacji w zapytaniach, które odnoszą się do źródła danych, w której relacje między sobą nie mogą występować bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="1175a-104">Joining is an important operation in queries that target data sources whose relationships to each other cannot be followed directly.</span></span> <span data-ttu-id="1175a-105">W programowanie zorientowane obiektowo, może to oznaczać korelacji między obiektami, które nie w modelu, takie jak Wstecz kierunek relacji jednokierunkowe.</span><span class="sxs-lookup"><span data-stu-id="1175a-105">In object-oriented programming, this could mean a correlation between objects that is not modeled, such as the backwards direction of a one-way relationship.</span></span> <span data-ttu-id="1175a-106">Przykładem jednokierunkowa relacja jest klasy klienta, która ma właściwość typu Miasto, ale klasa miasta nie ma właściwości, która jest kolekcją obiektów klienta.</span><span class="sxs-lookup"><span data-stu-id="1175a-106">An example of a one-way relationship is a Customer class that has a property of type City, but the City class does not have a property that is a collection of Customer objects.</span></span> <span data-ttu-id="1175a-107">Jeśli masz listę obiektów mieście i chcesz wyszukać wszystkich klientów w każdemu miastu, można użyć operacji sprzężenia je znaleźć.</span><span class="sxs-lookup"><span data-stu-id="1175a-107">If you have a list of City objects and you want to find all the customers in each city, you could use a join operation to find them.</span></span>  
  
 <span data-ttu-id="1175a-108">Metody sprzężenia w ramach składnika LINQ to <xref:System.Linq.Enumerable.Join%2A> i <xref:System.Linq.Enumerable.GroupJoin%2A>.</span><span class="sxs-lookup"><span data-stu-id="1175a-108">The join methods provided in the LINQ framework are <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="1175a-109">Te metody wykonywania equijoins lub sprzężenia, które odpowiada równość kluczy dwóch źródeł danych.</span><span class="sxs-lookup"><span data-stu-id="1175a-109">These methods perform equijoins, or joins that match two data sources based on equality of their keys.</span></span> <span data-ttu-id="1175a-110">(Porównanie, języka Transact-SQL obsługuje join operatorów innych niż "równa się", na przykład "poniżej" operator). W warunkach relacyjnej bazy danych <xref:System.Linq.Enumerable.Join%2A> wykonuje sprzężenie wewnętrzne, typ sprzężenia w zwracane są tylko te obiekty, które mają odpowiednika w zestawie danych.</span><span class="sxs-lookup"><span data-stu-id="1175a-110">(For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned.</span></span> <span data-ttu-id="1175a-111"><xref:System.Linq.Enumerable.GroupJoin%2A> — Metoda nie ma bezpośredniego odpowiednika w kategoriach relacyjnej bazy danych, ale implementuje podzbiorem sprzężenia wewnętrzne i lewe sprzężenia zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="1175a-111">The <xref:System.Linq.Enumerable.GroupJoin%2A> method has no direct equivalent in relational database terms, but it implements a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="1175a-112">Lewe sprzężenie zewnętrzne jest sprzężenia, które zwraca każdy element pierwszego źródła danych (po lewej), nawet jeśli go nie ma żadnych skorelowane elementów w źródle danych.</span><span class="sxs-lookup"><span data-stu-id="1175a-112">A left outer join is a join that returns each element of the first (left) data source, even if it has no correlated elements in the other data source.</span></span>  
  
 <span data-ttu-id="1175a-113">Na poniższej ilustracji przedstawiono koncepcję dwóch zestawów i elementów w obrębie tych zestawów, które znajdują się w przypadku sprzężenia wewnętrznego lub lewe sprzężenie zewnętrzne.</span><span class="sxs-lookup"><span data-stu-id="1175a-113">The following illustration shows a conceptual view of two sets and the elements within those sets that are included in either an inner join or a left outer join.</span></span>  
  
 <span data-ttu-id="1175a-114">![Dwie nakładające się okręgi przedstawiający wewnętrzny &#47; zewnętrzne. ] (../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span><span class="sxs-lookup"><span data-stu-id="1175a-114">![Two overlapping circles showing inner&#47;outer.](../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1175a-115">Metody</span><span class="sxs-lookup"><span data-stu-id="1175a-115">Methods</span></span>  
  
|<span data-ttu-id="1175a-116">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="1175a-116">Method Name</span></span>|<span data-ttu-id="1175a-117">Opis</span><span class="sxs-lookup"><span data-stu-id="1175a-117">Description</span></span>|<span data-ttu-id="1175a-118">Składnia wyrażenia zapytania C#</span><span class="sxs-lookup"><span data-stu-id="1175a-118">C# Query Expression Syntax</span></span>|<span data-ttu-id="1175a-119">Więcej informacji</span><span class="sxs-lookup"><span data-stu-id="1175a-119">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="1175a-120">Łączenie</span><span class="sxs-lookup"><span data-stu-id="1175a-120">Join</span></span>|<span data-ttu-id="1175a-121">Łączy dwie sekwencje oparta na funkcjach selektora kluczy i wyodrębnia par wartości.</span><span class="sxs-lookup"><span data-stu-id="1175a-121">Joins two sequences based on key selector functions and extracts pairs of values.</span></span>|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="1175a-122">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="1175a-122">GroupJoin</span></span>|<span data-ttu-id="1175a-123">Tworzy sprzężenie dwóch sekwencji na podstawie funkcji selektora kluczy i grup znalezione wyniki dla każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="1175a-123">Joins two sequences based on key selector functions and groups the resulting matches for each element.</span></span>|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a><span data-ttu-id="1175a-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1175a-124">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="1175a-125">Operatory standardowe zapytań — omówienie (C#)</span><span class="sxs-lookup"><span data-stu-id="1175a-125">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="1175a-126">Typy anonimowe</span><span class="sxs-lookup"><span data-stu-id="1175a-126">Anonymous Types</span></span>](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="1175a-127">Sformułować sprzężenia i iloczyn wektorowy zapytania</span><span class="sxs-lookup"><span data-stu-id="1175a-127">Formulate Joins and Cross-Product Queries</span></span>](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b)  
 [<span data-ttu-id="1175a-128">JOIN — klauzula</span><span class="sxs-lookup"><span data-stu-id="1175a-128">join clause</span></span>](../../../../csharp/language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="1175a-129">Porady: sprzęganie za pomocą kluczy złożonych</span><span class="sxs-lookup"><span data-stu-id="1175a-129">How to: Join by Using Composite Keys</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)  
 [<span data-ttu-id="1175a-130">Porady: łączenie zawartości niepodobnych plików (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1175a-130">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)  
 [<span data-ttu-id="1175a-131">Porady: kolejność wyników klauzuli Join</span><span class="sxs-lookup"><span data-stu-id="1175a-131">How to: Order the Results of a Join Clause</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
 [<span data-ttu-id="1175a-132">Porady: wykonywanie niestandardowych operacji łączenia</span><span class="sxs-lookup"><span data-stu-id="1175a-132">How to: Perform Custom Join Operations</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md)  
 [<span data-ttu-id="1175a-133">Porady: wykonanie sprzężeń grupowanych</span><span class="sxs-lookup"><span data-stu-id="1175a-133">How to: Perform Grouped Joins</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)  
 [<span data-ttu-id="1175a-134">Porady: wykonanie sprzężeń wewnętrznych</span><span class="sxs-lookup"><span data-stu-id="1175a-134">How to: Perform Inner Joins</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)  
 [<span data-ttu-id="1175a-135">Porady: wykonanie lewych sprzężeń zewnętrznych</span><span class="sxs-lookup"><span data-stu-id="1175a-135">How to: Perform Left Outer Joins</span></span>](../../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)  
 [<span data-ttu-id="1175a-136">Porady: wypełnianie kolekcji Object z wielu źródeł (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1175a-136">How to: Populate Object Collections from Multiple Sources (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)