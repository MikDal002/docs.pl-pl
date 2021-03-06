---
title: 'Instrukcje: Wyświetlanie wygenerowanego kodu SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 9c293757b642f0a945097c4ea4299d97cadddbcc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725691"
---
# <a name="how-to-display-generated-sql"></a>Instrukcje: Wyświetlanie wygenerowanego kodu SQL
Można wyświetlić kodu SQL, generowany dla zapytań i przetwarzania przy użyciu zmiany <xref:System.Data.Linq.DataContext.Log%2A> właściwości. Takie podejście może być przydatne do zrozumienia [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] funkcjonalność i debugowania konkretnych problemów.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Data.Linq.DataContext.Log%2A> właściwość, aby wyświetlić kod SQL w oknie konsoli, zanim kod zostanie wykonany.  Można używać tej właściwości przy użyciu zapytań, wstawiania, aktualizacji i usuwania poleceń.  
  
 Wiersze z okna konsoli są, zobacz podczas wykonywania Visual Basic lub C# kod następujący po ciągu.  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Zobacz także
- [Obsługa debugowania](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
