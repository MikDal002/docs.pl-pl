---
title: skojarzenie i liczebność
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 6d1b31c5b5ead701fbe808b91d7191fb84dc86c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502640"
---
# <a name="association-end-multiplicity"></a>skojarzenie i liczebność
*Skojarzenie i liczebność* definiuje liczbę [typu jednostki](../../../../docs/framework/data/adonet/entity-type.md) wystąpień, które mogą być na jednym końcu [skojarzenie](../../../../docs/framework/data/adonet/association-type.md).  
  
 Skojarzenie i liczebność może mieć jedną z następujących wartości:  
  
-   jeden (1): Wskazuje, że to wystąpienie typu dokładnie jednej jednostki znajduje się na końcu skojarzenia.  
  
-   zero lub jeden (od 0 do 1): Oznacza, że na końcu skojarzenia zera lub jednego wystąpienia typu jednostki.  
  
-   wiele (*): oznacza, że wartość zero, jeden lub więcej wystąpień typu jednostki na końcu skojarzenia.  
  
 Skojarzenie często jest określony przez jego liczebność punktów końcowych skojarzenia. Na przykład jeśli kończy się skojarzenia ma liczebność punktów jeden (1) i jest wielu (*), skojarzenia nosi nazwę skojarzenia typu jeden do wielu. W poniższym przykładzie `PublishedBy` skojarzenie jest skojarzenia typu jeden do wielu (wydawca publikuje wiele książek i książki opublikowana przez jedną wydawcą). `WrittenBy` Skojarzenie jest skojarzenie wiele do wielu (książki może mieć wielu autorów i Autor może zapisywać wiele książek).  
  
## <a name="example"></a>Przykład  
 Poniższy diagram przedstawia modelu koncepcyjnego z dwóch skojarzeń: `PublishedBy` i `WrittenBy`. Punkty końcowe dla skojarzenia `PublishedBy` to skojarzenie `Book` i `Publisher` typów jednostek. Liczebność `Publisher` end jest jeden (1), a liczebność `Book` end jest wielu (*).  
  
 ![Przykładowy Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 ADO.NET Entity Framework używa języka specyficznego dla domeny (DSL), o nazwie język definicji schematu koncepcyjnego ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) do definiowania modeli koncepcyjnych. Definiuje następujące CSDL `PublishedBy` skojarzenia pokazano na powyższym diagramie:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Zobacz także
- [Kluczowe założenia modelu danych jednostki](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model danych jednostki](../../../../docs/framework/data/adonet/entity-data-model.md)
