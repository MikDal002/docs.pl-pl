---
title: Tworzenie elementu DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: d3c20fa4394b09e9ceec332d430ed638166bed8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491666"
---
# <a name="creating-a-datareader"></a>Tworzenie elementu DataReader
<xref:System.Data.DataTable> i <xref:System.Data.DataSet> klasy mają <xref:System.Data.DataTable.CreateDataReader%2A> metodę, która zwraca zawartość <xref:System.Data.DataTable> lub zawartości <xref:System.Data.DataSet> obiektu <xref:System.Data.DataSet.Tables%2A> kolekcji jako jeden lub więcej zestawów wyników tylko do odczytu, tylko do przodu.  
  
## <a name="example"></a>Przykład  
 Tworzy następujące aplikację konsolową <xref:System.Data.DataTable> wystąpienia. Następnie przykład przekazuje wypełniony <xref:System.Data.DataTable> do procedury, która wywołuje <xref:System.Data.DataTable.CreateDataReader%2A> metody, która wykonuje iterację przez wyniki zawartych w <xref:System.Data.DataTableReader>.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 W przykładzie są wyświetlane następujące dane wyjściowe w oknie konsoli:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [Elementy DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [ADO.NET zarządzanego dostawcy i Centrum deweloperów zestawu danych](https://go.microsoft.com/fwlink/?LinkId=217917)
