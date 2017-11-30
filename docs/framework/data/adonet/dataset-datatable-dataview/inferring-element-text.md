---
title: Wnioskowanie tekstu elementu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 66dcc6a98d365f20da6c7f4c075c2fdd8ab936e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-element-text"></a><span data-ttu-id="d4446-102">Wnioskowanie tekstu elementu</span><span class="sxs-lookup"><span data-stu-id="d4446-102">Inferring Element Text</span></span>
<span data-ttu-id="d4446-103">Jeśli element zawiera tekst i nie ma żadnych elementów podrzędnych, można go wywnioskować, ponieważ tabele takie jak (elementy z atrybutami) lub powtarzane elementy nową kolumnę o nazwie **TableName_Text** zostaną dodane do tabeli, która jest wywnioskowany dla elementu.</span><span class="sxs-lookup"><span data-stu-id="d4446-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="d4446-104">Tekst zawarte w elemencie zostanie dodany do wiersza w tabeli i przechowywane w nowej kolumnie.</span><span class="sxs-lookup"><span data-stu-id="d4446-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="d4446-105">**ColumnMapping** właściwości nowej kolumny, która zostanie ustawiona do **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="d4446-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="d4446-106">Rozważmy na przykład następujący kod XML.</span><span class="sxs-lookup"><span data-stu-id="d4446-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d4446-107">Proces wnioskowania spowoduje utworzenie tabeli o nazwie **Element1** z dwiema kolumnami: **attr1** i **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="d4446-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="d4446-108">**ColumnMapping** właściwość **attr1** kolumny zostanie ustawiona do **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="d4446-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="d4446-109">**ColumnMapping** właściwość **Element1_Text** kolumny zostanie ustawiona do **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="d4446-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="d4446-110">**Zestaw danych:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d4446-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d4446-111">**Tabela:** Element1</span><span class="sxs-lookup"><span data-stu-id="d4446-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d4446-112">attr1</span><span class="sxs-lookup"><span data-stu-id="d4446-112">attr1</span></span>|<span data-ttu-id="d4446-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="d4446-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="d4446-114">Wartość1</span><span class="sxs-lookup"><span data-stu-id="d4446-114">value1</span></span>|<span data-ttu-id="d4446-115">Tekst1</span><span class="sxs-lookup"><span data-stu-id="d4446-115">Text1</span></span>|  
  
 <span data-ttu-id="d4446-116">Jeśli element zawiera tekst, ale ma także elementy podrzędne, które zawierają tekst, nie można dodać kolumny do tabeli do przechowywania tekstu zawarte w elemencie.</span><span class="sxs-lookup"><span data-stu-id="d4446-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="d4446-117">Tekst zawarte w elemencie zostanie zignorowany, gdy tekst w elementach podrzędnych jest uwzględniany w wiersza w tabeli.</span><span class="sxs-lookup"><span data-stu-id="d4446-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="d4446-118">Rozważmy na przykład następujący kod XML.</span><span class="sxs-lookup"><span data-stu-id="d4446-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="d4446-119">Proces wnioskowania spowoduje utworzenie tabeli o nazwie **Element1** z jedną kolumną o nazwie **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="d4446-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="d4446-120">Tekst dla **ChildElement1** element mają być uwzględnieni w wiersza w tabeli.</span><span class="sxs-lookup"><span data-stu-id="d4446-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="d4446-121">Inny tekst zostanie zignorowany.</span><span class="sxs-lookup"><span data-stu-id="d4446-121">The other text will be ignored.</span></span> <span data-ttu-id="d4446-122">**ColumnMapping** właściwość **ChildElement1** kolumny zostanie ustawiona do **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="d4446-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="d4446-123">**Zestaw danych:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d4446-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d4446-124">**Tabela:** Element1</span><span class="sxs-lookup"><span data-stu-id="d4446-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d4446-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d4446-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="d4446-126">Tekst2</span><span class="sxs-lookup"><span data-stu-id="d4446-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4446-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d4446-127">See Also</span></span>  
 [<span data-ttu-id="d4446-128">Wnioskowanie struktury zestawu danych relacyjnych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="d4446-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="d4446-129">Podczas ładowania zestawu danych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="d4446-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="d4446-130">Ładowanie informacji o schemacie zestawu danych z pliku XML</span><span class="sxs-lookup"><span data-stu-id="d4446-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="d4446-131">Za pomocą języka XML w zestawie danych</span><span class="sxs-lookup"><span data-stu-id="d4446-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="d4446-132">Zbiory danych, DataTables i DataViews</span><span class="sxs-lookup"><span data-stu-id="d4446-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="d4446-133">ADO.NET zarządzanego dostawcy i zestawu danych w Centrum deweloperów</span><span class="sxs-lookup"><span data-stu-id="d4446-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)