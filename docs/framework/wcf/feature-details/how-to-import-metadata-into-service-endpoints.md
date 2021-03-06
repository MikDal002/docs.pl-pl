---
title: 'Instrukcje: Importowanie metadanych do punktów końcowych usługi'
ms.date: 03/30/2017
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
ms.openlocfilehash: 5a6375f0a0b0f657401a1ac2254be942d4e618aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548680"
---
# <a name="how-to-import-metadata-into-service-endpoints"></a>Instrukcje: Importowanie metadanych do punktów końcowych usługi
W tym temacie wyjaśniono, jak zaimportować metadane do kolekcji punktów końcowych usługi i korzystać z niej zdefiniowane w [wprowadzenie](../../../../docs/framework/wcf/samples/getting-started-sample.md). W tym temacie pokazano, jak utworzyć aplikację kliencką, która importuje metadane z usługi, a następnie wywołania `Add` metody dla usługi.  
  
### <a name="to-import-metadata-into-service-endpoints"></a>Aby zaimportować metadane do punktów końcowych usług  
  
1.  Zadeklaruj <xref:System.ServiceModel.EndpointAddress> obiektu i go zainicjować za pomocą identyfikatora URI (Uniform Resource) dla adresu programu exchange (MEX) metadanych usługi.  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  Tworzenie <xref:System.ServiceModel.Description.MetadataExchangeClient>, przekazując MEX adresa i Wywołaj <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>. To pobiera metadane z usługi.  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  Tworzenie <xref:System.ServiceModel.Description.WsdlImporter>, przekazując metadanych wcześniej pobrane i Wywołaj <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>. Spowoduje to wygenerowanie zbiór <xref:System.ServiceModel.Description.ContractDescription> obiektów. Można również wywołać <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> lub <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, w zależności od potrzeb.  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  Po zaimportowaniu metadanych nie można utworzyć kanału klienta lub wyeksportować metadane. Jest to spowodowane typu są dostępne żadne informacje w tym momencie. Informacje o typie jest wymagany do faktycznie wchodzić w interakcje z usługą lub eksportowanie metadanych. Aby wygenerować informacje o typie, należy wygenerować kod, przedstawiono w ramach kroków 4 i 5. Alternatywnie można użyć <xref:System.ServiceModel.Description.MetadataResolver> Klasa pomocy. Aby uzyskać więcej informacji, zobacz [jak: Uzyskiwanie metadanych powiązania przy użyciu klasy MetadataResolver](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).  
  
4.  Generuj informacje o typie dla każdej umowy.  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  Teraz można użyć tych informacji. Poniższy przykład spowoduje wygenerowanie C# kodu źródłowego.  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a>Zobacz także
- [Metadane](../../../../docs/framework/wcf/feature-details/metadata.md)
- [Wprowadzenie](../../../../docs/framework/wcf/samples/getting-started-sample.md)
