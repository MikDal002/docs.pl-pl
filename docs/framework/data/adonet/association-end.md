---
title: punkt końcowy skojarzenia
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 8c156ca1c05e22e540578adfb2be06cf477b29e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744950"
---
# <a name="association-end"></a>punkt końcowy skojarzenia
*End skojarzenia* identyfikuje [typu jednostki](../../../../docs/framework/data/adonet/entity-type.md) na jednym końcu [skojarzenia](../../../../docs/framework/data/adonet/association-type.md) i liczby jednostek typu wystąpienia, które może znajdować się na końcu tego skojarzenia. Skojarzenia są zdefiniowane jako część skojarzenia; Skojarzenie musi mieć dokładnie dwa punkty końcowe skojarzenia. [Właściwości nawigacji](../../../../docs/framework/data/adonet/navigation-property.md) umożliwiają nawigacji z elementu end skojarzenia jednego do drugiego.  
  
 Definicja end skojarzenia zawiera następujące informacje:  
  
-   Jeden z typów jednostek zaangażowanych w skojarzeniu. (Wymagane)  
  
    > [!NOTE]
    >  Dla danego skojarzenia typu jednostki, określony dla wszystkich punktów końcowych skojarzenia może być taki sam. Spowoduje to utworzenie skojarzenia samooceny.  
  
-   [Skojarzenie i liczebność](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , wskazuje liczbę wystąpień typów jednostek, które mogą być na jednym końcu skojarzenia. Skojarzenie i liczebność może mieć wartość równą jeden (1), zero lub jeden (od 0 do 1), lub wielu (*).  
  
-   Nazwa dla elementu end skojarzenia. (opcjonalnie)  
  
-   Informacje o operacjach wykonywanych na punkt końcowy skojarzenia, np. kaskadowe podczas usuwania. (opcjonalnie)  
  
## <a name="example"></a>Przykład  
 Poniższy diagram przedstawia modelu koncepcyjnego z dwóch skojarzeń: `PublishedBy` i `WrittenBy`. Punkty końcowe dla skojarzenia `PublishedBy` to skojarzenie `Book` i `Publisher` typów jednostek. Liczebność `Publisher` end jest jeden (1), a liczebność `Book` end jest wielu (*), informujący, że wydawca publikuje wiele książek i książki opublikowana przez jedną wydawcą.  
  
 ![Przykładowy Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 ADO.NET Entity Framework używa języka specyficznego dla domeny (DSL), o nazwie język definicji schematu koncepcyjnego ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) do definiowania modeli koncepcyjnych. Definiuje CSDL poniżej `PublishedBy` skojarzenia pokazano na powyższym diagramie. Należy pamiętać, że typ, nazwa i liczebność każdy punkt końcowy skojarzenia są określone przez atrybuty XML ( `Type`, `Role`, i `Multiplicity` , odpowiednio, atrybutów). Opcjonalne informacje o operacji wykonywanych na koniec jest określony w elemencie XML ( `OnDelete` elementu). W tym przypadku Jeśli wydawca zostanie usunięty, dlatego są wszystkie skojarzone książki.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Zobacz także
- [Kluczowe założenia modelu danych jednostki](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model danych jednostki](../../../../docs/framework/data/adonet/entity-data-model.md)
