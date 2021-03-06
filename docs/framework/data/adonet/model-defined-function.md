---
title: funkcja zdefiniowana przez model
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 371af3ae090e37cfd425a9e9d5946bb0751dc527
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538885"
---
# <a name="model-defined-function"></a>funkcja zdefiniowana przez model
A *funkcja zdefiniowana przez model* jest funkcją, która jest zdefiniowana w modelu koncepcyjnym. Treść funkcji definiowanych przez model danych jest wyrażona w [jednostki SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), co umożliwia funkcji wyrażane niezależnie od reguł lub języki obsługiwane w źródle danych.  
  
 Definicja dla funkcji definiowanych przez model zawiera następujące informacje:  
  
-   Nazwa funkcji. (Wymagane)  
  
-   Typ wartości zwracanej. (opcjonalnie)  
  
    > [!NOTE]
    >  Jeśli żaden typ zwracany jest określony, wartość zwracana jest nieważne.  
  
-   Informacje o parametrach. (opcjonalnie)  
  
-   [Jednostki SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) wyrażenia, który definiuje treści funkcji.  
  
 Należy pamiętać, że funkcje zdefiniowane w modelu nie obsługują parametrów wyjściowych. To ograniczenie jest w miejscu, dzięki czemu mogą być składane funkcji definiowanych przez model.  
  
## <a name="example"></a>Przykład  
 Poniższy diagram przedstawia modelu koncepcyjnego z trzech typów jednostek: `Book`, `Publisher`, i `Author`.  
  
 ![Model przy użyciu Data opublikowania](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) używa języka specyficznego dla domeny (DSL), o nazwie język definicji schematu koncepcyjnego ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) do definiowania modeli koncepcyjnych. Następujące CSDL definiuje funkcję w modelu koncepcyjnym, zwracające liczbę lat od wystąpienia `Book` (w powyższym diagramie) została opublikowana.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>Zobacz także
- [Kluczowe założenia modelu danych jednostki](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model danych jednostki](../../../../docs/framework/data/adonet/entity-data-model.md)
- [Model danych jednostki: Pierwotne typy danych](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
