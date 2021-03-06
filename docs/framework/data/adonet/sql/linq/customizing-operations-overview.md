---
title: 'Dostosowywanie operacji: Omówienie'
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 4f13bed76ad2814d669f487b57ae9acbdc08eb74
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735464"
---
# <a name="customizing-operations-overview"></a>Dostosowywanie operacji: Omówienie
Domyślnie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generuje dynamiczny język SQL insert, update i operacje usuwania na podstawie mapowania. Jednak w praktyce zazwyczaj chcesz dodać własną logiką biznesową w celu zapewnienia bezpieczeństwa, weryfikacji i tak dalej.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] następujące techniki dotyczące dostosowywania tych operacji.  
  
## <a name="loading-options"></a>Opcje ładowania  
 W zapytaniach można kontrolować, jak dużo danych powiązane z głównym docelowej jest pobierana, po nawiązaniu połączenia z bazą danych. Ta funkcja jest zaimplementowana w dużym stopniu przy użyciu <xref:System.Data.Linq.DataLoadOptions>. Aby uzyskać więcej informacji, zobacz [odroczone a ładowania bezpośredniego](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
## <a name="partial-methods"></a>Metody częściowe  
 Domyślnego mapowania, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dostarcza metod częściowych w celu ułatwienia implementacji logiki biznesowej. Aby uzyskać więcej informacji, zobacz [Dodawanie Business Logic przez przy użyciu metod częściowych](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).  
  
## <a name="stored-procedures-and-user-defined-functions"></a>Procedury składowane i funkcje zdefiniowane przez użytkownika  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje korzystanie z procedur składowanych i funkcji zdefiniowanych przez użytkownika. Procedury składowane są często używane do dostosowywania operacji. Aby uzyskać więcej informacji, zobacz [procedur składowanych](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Zobacz także
- [Dostosowywanie operacji wstawiania, aktualizowania i usuwania](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
