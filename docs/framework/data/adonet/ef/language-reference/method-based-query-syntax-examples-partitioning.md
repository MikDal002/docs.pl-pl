---
title: 'Przykłady składni zapytania oparte na metodzie: Partycjonowanie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 181564de997e9a799aafa660a16b32a6ceb91d4a
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827157"
---
# <a name="method-based-query-syntax-examples-partitioning"></a>Przykłady składni zapytania oparte na metodzie: Partycjonowanie
Przykłady w tym temacie prezentują sposób użycia <xref:System.Linq.Enumerable.Skip%2A>, i <xref:System.Linq.Enumerable.Take%2A> metod do wykonywania zapytań [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) przy użyciu składni wyrażeń zapytania. Model sprzedaży AdventureWorks, używany w tych przykładach składa się z kontaktu, adres, produktu, SalesOrderHeader i szczegóły zamówienia sprzedaży tabele w przykładowej bazy danych AdventureWorks.  
  
 Przykłady w tym temacie należy użyć następującego `using` / `Imports` instrukcji:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a>Skip  
  
### <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Linq.Enumerable.Skip%2A> metodę, aby uzyskać wszystkie, ale pięciu pierwszych kontakty tabeli Kontakt.  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Linq.Enumerable.Skip%2A> metodę, aby uzyskać wszystkie, ale pierwsze dwa adresy w Seattle.  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a>Take  
  
### <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Linq.Enumerable.Take%2A> metodę, aby uzyskać tylko pięć pierwszych kontakty z tabeli Kontakt.  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Linq.Enumerable.Take%2A> metodę, aby uzyskać pierwszych trzech adresów w Seattle.  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a>Zobacz także
- [Zapytania w składniku LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
