---
title: Typ jednostki
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3955de1873d80e85df713a557750e34e76efeb41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502887"
---
# <a name="entity-type"></a>Typ jednostki
*Typu jednostki* jest elementem składowym podstawowych do opisywania struktury danych z Entity Data Model (EDM). W modelu koncepcyjnym typ jednostki reprezentuje strukturę koncepcje najwyższego poziomu, takich jak klienci i zamówienia. Typ jednostki jest szablonem dla wystąpienia typu jednostki. Każdy szablon zawiera następujące informacje:  
  
-   Unikatowa nazwa. (Wymagane).  
  
-   [Klucz jednostki](../../../../docs/framework/data/adonet/entity-key.md) zdefiniowane przez jedną lub więcej właściwości. (Wymagane).  
  
-   Dane w postaci [właściwości](../../../../docs/framework/data/adonet/property.md). (Opcjonalnie).  
  
-   [Właściwości nawigacji](../../../../docs/framework/data/adonet/navigation-property.md) umożliwiające nawigacji z jednego [zakończenia](../../../../docs/framework/data/adonet/association-end.md) z [skojarzenia](../../../../docs/framework/data/adonet/association-type.md) w innym celu. (opcjonalnie)  
  
 W aplikacji wystąpienia typu jednostki reprezentuje określonego obiektu (na przykład konkretnego klienta lub zamówienia). Każde wystąpienie typu jednostki musi mieć unikatową [klucz jednostki](../../../../docs/framework/data/adonet/entity-key.md) w ramach [zestaw jednostek](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Dwa wystąpienia typu jednostki są traktowane jako równe tylko wtedy, gdy są one tego samego typu i wartości kluczy podmiotu są takie same.  
  
## <a name="example"></a>Przykład  
 Poniższy diagram przedstawia modelu koncepcyjnego z trzech typów jednostek: `Book`, `Publisher`, i `Author`:  
  
 ![Przykładowy Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Należy pamiętać, że właściwości każdego typu jednostki, które tworzą klucz jednostki są oznaczone symbolem "(klucz)".  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) używa języka specyficznego dla domeny (DSL), o nazwie język definicji schematu koncepcyjnego ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) do definiowania modeli koncepcyjnych. Definiuje następujące CSDL `Book` typu jednostki, które pokazano na powyższym diagramie:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Zobacz także
- [Kluczowe założenia modelu danych jednostki](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Model danych jednostki](../../../../docs/framework/data/adonet/entity-data-model.md)
- [aspekt](../../../../docs/framework/data/adonet/facet.md)
