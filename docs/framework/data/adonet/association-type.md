---
title: Typ skojarzenia
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 3b01e053a1d61e2ce413ae6683d350b77c402fb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714597"
---
# <a name="association-type"></a>Typ skojarzenia
*Typ skojarzenia* (nazywane również skojarzenie) jest elementem składowym podstawowych do opisywania relacji w Entity Data Model (EDM). W modelu koncepcyjnym, skojarzenia reprezentuje relację między dwiema [typów jednostek](../../../../docs/framework/data/adonet/entity-type.md) (takie jak `Customer` i `Order`). W aplikacji, wystąpienia skojarzenia reprezentuje określone skojarzenia (takie jak skojarzenie między wystąpieniem `Customer` i wystąpienie `Order`). Skojarzenie wystąpienia są logicznie pogrupowane w [zestaw skojarzeń](../../../../docs/framework/data/adonet/association-set.md).  
  
 Definicja skojarzenie zawiera następujące informacje:  
  
-   Unikatowa nazwa. (Wymagane)  
  
-   Dwa [skojarzenia](../../../../docs/framework/data/adonet/association-end.md), jeden dla każdego typu jednostki w relacji. (Wymagane)  
  
    > [!NOTE]
    >  Skojarzenie nie reprezentują relację między więcej niż dwóch typów jednostek. Skojarzenie można jednak zdefiniować relację self, określając ten sam typ jednostki dla każdego z jego skojarzenie.  
  
-   A [ograniczenia integralności referencyjnej](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (opcjonalnie)  
  
 Każdy punkt końcowy skojarzenia należy określić [skojarzenie i liczebność](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , wskazuje liczbę wystąpień typów jednostek, które mogą być na jednym końcu skojarzenia. Skojarzenie i liczebność może mieć wartość równą jeden (1), zero lub jeden (od 0 do 1), lub wielu (*). Wystąpienia typu jednostki na jednym końcu asocjacji jest możliwy za pośrednictwem [właściwości nawigacji](../../../../docs/framework/data/adonet/navigation-property.md) lub kluczy obcych, jeśli są one widoczne na typ jednostki. Aby uzyskać więcej informacji, zobacz [modelu danych jednostki: Klucze obce](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Przykład  
 Poniższy diagram przedstawia modelu koncepcyjnego z dwóch skojarzeń: `PublishedBy` i `WrittenBy`. Punkty końcowe dla skojarzenia `PublishedBy` to skojarzenie `Book` i `Publisher` typów jednostek. Liczebność `Publisher` end jest jeden (1), a liczebność `Book` end jest wielu (*), informujący, że wydawca publikuje wiele książek i książki opublikowana przez jedną wydawcą.  
  
 ![Przykładowy Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) używa języka specyficznego dla domeny (DSL), o nazwie język definicji schematu koncepcyjnego ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) do definiowania modeli koncepcyjnych. Definiuje następujące CSDL `PublishedBy` skojarzenia pokazano na powyższym diagramie:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Zobacz także
- [Kluczowe założenia modelu danych jednostki](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model danych jednostki](../../../../docs/framework/data/adonet/entity-data-model.md)
