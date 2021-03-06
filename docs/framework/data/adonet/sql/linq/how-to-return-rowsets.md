---
title: 'Instrukcje: Zwracane zestawy wierszy'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b9fcbd8aa74740a66fa6caca18067ac473891f4e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587219"
---
# <a name="how-to-return-rowsets"></a>Instrukcje: Zwracane zestawy wierszy
W tym przykładzie zwraca zestawu wierszy z bazy danych i zawiera parametr wejściowy do filtrowania wyników.  
  
 Podczas wykonywania procedury składowanej, która zwraca zestawu wierszy, możesz użyć *wynik* klasy, która przechowuje zwraca z procedury składowanej. Aby uzyskać więcej informacji, zobacz [analizowanie LINQ to SQL kod źródłowy](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia procedury przechowywanej, która zwraca wiersze klientów i używa parametru wejściowego, aby zwrócić tylko wiersze z tej listy "Londyn", jak miasto klienta. W przykładzie założono wyliczalny `CustomersByCityResult` klasy.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a>Zobacz także
- [Procedury składowane](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [Pobieranie przykładowych baz danych](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
