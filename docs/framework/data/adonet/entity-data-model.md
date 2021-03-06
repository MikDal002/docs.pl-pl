---
title: Entity Data Model
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: f6f3d02a27ce9df152753b7aeec9ceb251bca532
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904832"
---
# <a name="entity-data-model"></a>Entity Data Model
Entity Data Model (EDM) to zbiór pojęcia, które opisują struktury danych, niezależnie od tego, w postaci przechowywane. EDM obiektowy Model Relacja jednostki, opisanego przez Peter Chen w 1976, ale również jest oparta na modelu jednostki relacji i rozszerza jego tradycyjnych zastosowań.  
  
 EDM rozwiązuje problemy, które wynikają z konieczności — dane przechowywane w wielu formularzach. Rozważmy na przykład firma, która przechowuje dane w relacyjnych baz danych, pliki tekstowe, pliki XML, arkusze kalkulacyjne i raporty. Przedstawia informacje o istotnym wyzwaniom związanym z modelowania danych, projektowania aplikacji i dostępu do danych. Podczas projektowania aplikacji zorientowanych na dane, wezwanie jest do pisania kodu, wydajnego i łatwego w utrzymaniu bez obniżania oczekiwanego poziomu dostępu do danych wydajne, magazynu i skalowalności. Przypadku relacyjnej struktury danych, dostęp do danych, magazynu i skalowalności jest bardzo wydajny, ale pisania kodu wydajnego i łatwego w utrzymaniu staje się coraz trudniejszy. Gdy dane znajdują się struktury obiektu, zostały cofnięte wad i zalet: Pisanie kodu wydajnego i łatwego w utrzymaniu pochodzi kosztem dostępu do danych wydajne, magazynu i skalowalności. Nawet wtedy, gdy można znaleźć równowagę między te wad, nowe wyzwania wystąpić, gdy dane są przenoszone z jednego formularza do innego. W modelu Entity Data Model uwzględniają te problemy, zawierająca opis struktury danych pod względem jednostek i relacji, które są niezależne od dowolnego schematu magazynu. Dzięki temu formularzu przechowywanych danych nieodpowiednie do projektowania aplikacji i tworzenia. Ponadto ponieważ jednostek i relacji opisać struktury danych, jest używany w aplikacji (nie jego przechowywanej formularz), ich ewolucji miarę rozwoju aplikacji.  
  
 A `conceptual model` to reprezentacja określonej struktury danych jako jednostek i relacji i zwykle jest zdefiniowany w języka specyficznego dla domeny (DSL), który implementuje koncepcji EDM. [Język definicji schematu koncepcyjnego (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) jest przykładem języka specyficznego dla domeny. Jednostek i relacji, które opisano w modelu koncepcyjnym mogą być uważane za abstrakcje obiektów i skojarzenia w aplikacji. Umożliwia deweloperom skoncentrowanie się na modelu koncepcyjnego zapewnieniu schemat magazynu i pozwala na ich wydajność i łatwość konserwacji należy pamiętać, do pisania kodu. W międzyczasie projektantów schematu magazynu skupić się na wydajność dostępu do danych, magazynu i skalowalności.  
  
## <a name="in-this-section"></a>W tej sekcji  
 Tematy w tej sekcji opisano pojęcia związane z modelu Entity Data Model. Wszelkie DSL, który implementuje EDM powinno obejmować pojęcia opisane w tym miejscu. Należy pamiętać, że [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) używa CSDL do definiowania modeli koncepcyjnych. Aby uzyskać więcej informacji, zobacz [Specyfikacja CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).  
  
 [Kluczowe założenia modelu danych jednostki](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [Model danych jednostki: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [Model danych jednostki: Pierwotne typy danych](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [Model danych jednostki: Dziedziczenie](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [punkt końcowy skojarzenia](../../../../docs/framework/data/adonet/association-end.md)  
  
 [skojarzenie i liczebność](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [zestaw skojarzeń](../../../../docs/framework/data/adonet/association-set.md)  
  
 [punkt końcowy zestawu skojarzeń](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [typ skojarzenia](../../../../docs/framework/data/adonet/association-type.md)  
  
 [typ złożony](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [kontener jednostek](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [klucz jednostki](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [zestaw jednostek](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [typ jednostki](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [aspekt](../../../../docs/framework/data/adonet/facet.md)  
  
 [właściwość klucza obcego](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [funkcja zadeklarowana modelu](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [funkcja zdefiniowana przez model](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [właściwość nawigacji](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [właściwość](../../../../docs/framework/data/adonet/property.md)  
  
 [ograniczenie integralności referencyjnej](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a>Zobacz także
- [Narzędzia do modelu danych jednostki ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Omówienie pliku edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [Specyfikacja CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
