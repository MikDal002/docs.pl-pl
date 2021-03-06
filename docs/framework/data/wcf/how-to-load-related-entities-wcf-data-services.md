---
title: 'Instrukcje: Ładowanie powiązanych jednostek (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, deferred content
- WCF Data Services, loading data
ms.assetid: 6f143d30-d997-4e6b-bcf0-d5c394ecb108
ms.openlocfilehash: a05d294f80943e771a298b4442a521de86ff2f19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616969"
---
# <a name="how-to-load-related-entities-wcf-data-services"></a>Instrukcje: Ładowanie powiązanych jednostek (WCF Data Services)
Kiedy należy załadować jednostek skojarzonych w [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], możesz użyć <xref:System.Data.Services.Client.DataServiceContext.LoadProperty%2A> metody <xref:System.Data.Services.Client.DataServiceContext> klasy. Można również użyć <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> metody <xref:System.Data.Services.Client.DataServiceQuery%601> wymaganie, że powiązanych jednostek eagerly załadowane w tej samej odpowiedzi na kwerendę.  
  
 W przykładzie w tym temacie użyto Northwind przykładowe dane usługi i automatycznie wygenerowany klas usługi danych klienta. Ta usługa i klas danych klienta, są tworzone po ukończeniu [Szybki Start usług danych WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak by jawnie ładować `Customer` , jest powiązany z każdym zwrócił `Orders` wystąpienia.  
  
 [!code-csharp[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#loadrelatedordercustomer)]
 [!code-vb[Astoria Northwind Client#LoadRelatedOrderCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#loadrelatedordercustomer)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak używać <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> metodę, aby zwrócić `Order Details` należących do `Orders` zwróconych przez zapytanie.  
  
 [!code-csharp[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#expandorderdetails)]
 [!code-vb[Astoria Northwind Client#ExpandOrderDetails](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#expandorderdetails)]  
  
## <a name="see-also"></a>Zobacz także
- [Wykonywanie zapytań do usługi danych](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
