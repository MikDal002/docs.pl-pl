---
title: 'Instrukcje: Używanie procedur składowanych zmapowanych do wielu kształtów wyników'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 6ea318e89cf91dcbf16747117b8000dfa3f9571d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573676"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Instrukcje: Używanie procedur składowanych zmapowanych do wielu kształtów wyników
Podczas procedury składowanej może zwrócić wielu kształtów wyników, zwracany typ nie silnie typizowane do projekcji pojedynczego kształtu. Mimo że [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wygenerować wszystkich typów projekcji możliwe, nie wiedzieć, kolejność, w której zostanie zwrócony.  
  
 Natomiast tego scenariusza za pomocą procedur składowanych, które tworzą wielu kształtów wyników po kolei. Aby uzyskać więcej informacji, zobacz [jak: Używanie procedur składowanych zmapowanych do sekwencyjnych kształtów wyników](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).  
  
 <xref:System.Data.Linq.Mapping.ResultTypeAttribute> Atrybut jest stosowany do procedur przechowywanych, które zwraca wiele typów wyników do określenia zestawu typów, które może zwracać procedury.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie kodu SQL kształtu wynik zależy od danych wejściowych (`shape =1` lub `shape = 2`). Nie wiesz, projekcji, które zostaną zwrócone najpierw.  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a>Przykład  
 Aby wykonać tę procedurę składowaną należy użyć kodu podobnego do następującego.  
  
> [!NOTE]
>  Należy użyć <xref:System.Data.Linq.IMultipleResults.GetResult%2A> wzorca, aby uzyskać moduł wyliczający odpowiedniego typu, w oparciu o swojej wiedzy na temat procedury składowanej.  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Zobacz także
- [Procedury składowane](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
