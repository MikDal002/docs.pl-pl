---
title: Operacje na zestawie (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2b06e822-e030-438f-9db7-ee402bd3a706
ms.openlocfilehash: b1b515c7eee11f7aadc1d34223dbb4ea1367842d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741883"
---
# <a name="set-operations-visual-basic"></a>Operacje na zestawie (Visual Basic)
Operacje na zestawie w składniku LINQ dotyczą operacje zapytań, które tworzą zestaw wyników, który zależy od obecności lub braku równoważne elementów w obrębie tego samego lub oddzielne kolekcje (lub zestawy).  
  
 Metody standardowego operatora zapytań, które wykonują operacje na zestawie są wymienione w poniższej sekcji.  
  
## <a name="methods"></a>Metody  
  
|Nazwa metody|Opis|Składnia wyrażeń języka Visual Basic|Więcej informacji|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Distinct|Usuwa zduplikowane wartości z kolekcji.|`Distinct`|<xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Distinct%2A?displayProperty=nameWithType>|  
|Z wyjątkiem|Zwraca różnicę zestawu, który oznacza, że elementy jednej kolekcji, które nie są wyświetlane w drugiej kolekcji.|Nie dotyczy.|<xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Except%2A?displayProperty=nameWithType>|  
|INTERSECT|Zwraca część wspólną zestawu, co oznacza, elementy, które są wyświetlane w każdym dwie kolekcje.|Nie dotyczy.|<xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Intersect%2A?displayProperty=nameWithType>|  
|Union|Zwraca Unię zestawu, co oznacza unikatowych elementów, które pojawiają się w jednej z dwóch kolekcjach.|Nie dotyczy.|<xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Union%2A?displayProperty=nameWithType>|  
  
## <a name="comparison-of-set-operations"></a>Porównanie operacje na zestawie  
  
### <a name="distinct"></a>Distinct  
 Poniższa ilustracja przedstawia zachowanie <xref:System.Linq.Enumerable.Distinct%2A?displayProperty=nameWithType> metody w sekwencji znaków. Zwracana sekwencja zawiera unikatowych elementów z sekwencji wejściowych.  
  
 ![Grafika przedstawiająca zachowanie słowa kluczowego DISTINCT&#40;&#41;. ](../../../../csharp/programming-guide/concepts/linq/media/distinct.png "Odrębne")  
  
### <a name="except"></a>Z wyjątkiem  
 Poniższa ilustracja przedstawia zachowanie <xref:System.Linq.Enumerable.Except%2A?displayProperty=nameWithType>. Zwracana sekwencja zawiera tylko elementy z pierwszej sekwencji wejściowych, które nie znajdują się w drugiej sekwencji wejściowych.  
  
 ![Grafika przedstawiająca działania z wyjątkiem&#40;&#41;. ](../../../../csharp/programming-guide/concepts/linq/media/except.png "z wyjątkiem")  
  
### <a name="intersect"></a>INTERSECT  
 Poniższa ilustracja przedstawia zachowanie <xref:System.Linq.Enumerable.Intersect%2A?displayProperty=nameWithType>. Zwracana sekwencja zawiera elementy, które są wspólne dla obu sekwencji wejściowych.  
  
 ![Grafika przedstawiająca części wspólnych dwóch sekwencji. ](../../../../csharp/programming-guide/concepts/linq/media/intersect.png "Intersect")  
  
### <a name="union"></a>Union  
 Poniższa ilustracja przedstawia operacji union na dwie sekwencje znaków. Zwracana sekwencja zawiera unikatowych elementów z obu sekwencji wejściowych.  
  
 ![Grafika przedstawiająca sumę dwóch sekwencji. ](../../../../csharp/programming-guide/concepts/linq/media/union.png "Unii")  
  
## <a name="query-expression-syntax-example"></a>Przykład składni wyrażenia zapytania  
 W poniższym przykładzie użyto `Distinct` klauzuli w zapytaniu programu LINQ do zwrócenia unikatowe numery z listy liczb całkowitych.  
  
 [!code-vb[CsLINQSetOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/set-operations_1.vb)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Linq>
- [Omówienie operatorów standardowej kwerendy (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [Distinct, klauzula](../../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Instrukcje: Łączenie i porównywanie kolekcji ciągów (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md)
- [Instrukcje: Wyszukiwanie zestawu różnic między dwoma listami (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md)
