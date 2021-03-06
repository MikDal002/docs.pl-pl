---
title: 'Instrukcje: Określanie sprawdzania konfliktów współbieżności'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: 033a547b25e7280eb39be2698963391543437083
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573728"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a>Instrukcje: Określanie sprawdzania konfliktów współbieżności
Można określić kolumny bazy danych, które mają być sprawdzane pod kątem konfliktów współbieżności, gdy wywołujesz <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Aby uzyskać więcej informacji, zobacz [jak: Określ, które elementy członkowskie są sprawdzane pod kątem konfliktów współbieżności](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
## <a name="example"></a>Przykład  
 Poniższy kod określa, że `HomePage` elementu członkowskiego nigdy nie powinny być badane podczas sprawdzania aktualizacji. Aby uzyskać więcej informacji, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Zobacz także
- [Model obiektu LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
