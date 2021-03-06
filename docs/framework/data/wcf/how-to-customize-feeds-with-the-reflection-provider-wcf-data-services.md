---
title: 'Instrukcje: Dostosowywanie źródła danych za pomocą dostawcy odbicia (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: fe6e65a0030ca016f280e6b2c1106b4aa302d26e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637706"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Instrukcje: Dostosowywanie źródła danych za pomocą dostawcy odbicia (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Umożliwia dostosowanie Atom serializacji w odpowiedzi usługi danych, dzięki czemu właściwości jednostki mogą być mapowane do nieużywanych elementów, które są zdefiniowane w protokole AtomPub. W tym temacie przedstawiono sposób definiowania atrybutów mapowania dla typów jednostek w modelu danych, która jest zdefiniowana za pomocą dostawcy odbicia. Aby uzyskać więcej informacji, zobacz [kanału informacyjnego dostosowywania](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 Model danych w tym przykładzie jest zdefiniowana w temacie [jak: Tworzenie usługi danych przy użyciu dostawcy odbicia](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie, obie właściwości `Order` typu są mapowane na istniejące elementy Atom. `Product` Właściwość `Item` typu jest mapowany na atrybut niestandardowy kanału informacyjnego w oddzielnych przestrzeni nazw.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Przykład  
 Poprzedni przykład zwraca następujące wyniki dla identyfikatora URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>Zobacz także
- [Dostawca odbicia](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
