---
title: Architektura logiczna a architektura fizyczna
description: Opis różnic między architektury fizycznych i logicznych.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/20/2018
ms.openlocfilehash: e8ed375899637d06db8eb9b12a0e1cb0c05591f9
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129925"
---
# <a name="logical-architecture-versus-physical-architecture"></a>Architektura logiczna a architektura fizyczna

Jest to przydatne w tym momencie zatrzymać, a omówić rozróżnienia między Architektura logiczna a architektura fizyczna i jak to ma zastosowanie do projektowania aplikacji opartych na mikrousługach.

Aby rozpocząć, tworzenia mikrousług nie wymaga użycia każdej określonej technologii. Na przykład kontenery platformy Docker nie są wymagane do tworzenia opartych na mikrousługach architektury. Te mikrousług może także uruchomić jako zwykły procesy. Mikrousługi to architektura logiczna.

Ponadto, nawet wtedy, gdy mikrousługi można fizycznie zaimplementować jako pojedynczą usługę, procesu lub kontenera (sake firmy prostotę, to podejście w pierwotnej wersji [ramach aplikacji eShopOnContainers](https://aka.ms/MicroservicesArchitecture)), to parzystość mikrousługi biznesowych i fizycznych usługi lub kontenera niekoniecznie nie jest wymagane we wszystkich przypadkach, podczas kompilowania dużych i złożonych aplikacji, składające się z wielu dziesiątek, jak i nawet setki usług.

To jest, gdy istnieje różnica między Architektura logiczna a architektura fizyczna aplikacji. Architektura logiczna a logiczne granice systemu nie są zawsze mapowane jeden do jednego z architekturą fizycznej lub wdrożenia. Może się zdarzyć, ale często nie.

Chociaż może być zidentyfikowano niektórych mikrousług firmy lub ograniczonych kontekstów, nie znaczy, zawsze jest najlepszym sposobem ich wdrażania, tworząc pojedynczą usługę (np. interfejsu API sieci Web platformy ASP.NET) lub pojedynczym kontenerem platformy Docker dla poszczególnych mikrousług biznesowych. Reguła informujący o tym, każda mikrousługa firm ma być implementowane przy użyciu jednej usługi lub kontener jest zbyt sztywne.

Dlatego mikrousług biznesowych lub ograniczony kontekst jest logiczną architekturę, która może być pokrywają się (lub nie) przy użyciu architektury fizycznych. Istotną kwestią jest to, że mikrousług biznesowych lub ograniczony kontekst musi być autonomiczne, umożliwiając kodu i stanie się oddzielnie wersjonowanych, wdrażanie i skalowanie.

Jak pokazano na rysunku 4 – 8, mikrousługi firm katalogu może składać się z kilku usług lub procesów. Mogą to być wiele usług interfejsu API sieci Web platformy ASP.NET lub dowolny inny rodzaj usługi przy użyciu protokołu HTTP lub innych protokołów. Co ważniejsze usług można udostępnić te same dane, tak długo, jak te usługi są spójne w odniesieniu do tej samej domeny biznesowej.

![Diagram mikrousług firm katalogu, który zawiera usługi interfejsu API usługi wyszukiwania i bazy danych programu SQL Server.](./media/image8.png)

**Rysunek 4 – 8**. Mikrousługi biznesowych za pomocą kilku usług fizycznych

Usługi w przykładzie udostępnić ten sam model danych, ponieważ te same dane co usługa wyszukiwania jest przeznaczony dla usługi interfejsu API sieci Web. Dlatego w fizycznych implementacji mikrousług firmy one dzielenie tę funkcję, dzięki czemu możesz skalować każdą z tych usług wewnętrznej w górę lub w dół odpowiednio do potrzeb. Może być usługa internetowego interfejsu API zazwyczaj wymaga więcej wystąpień niż usługi wyszukiwania lub na odwrót.

Krótko mówiąc logiczną architekturę mikrousług nie zawsze ma pokrywają się z architekturą fizycznej wdrożenie. W tym przewodniku zawsze wtedy, gdy firma Microsoft wspomnieć o mikrousługach, mamy na myśli przez firmę lub mikrousług logiczne, które można zamapować na co najmniej jednej usługi (fizycznej). W większości przypadków będzie to pojedyncza usługa, ale może być więcej.

>[!div class="step-by-step"]
>[Poprzednie](data-sovereignty-per-microservice.md)
>[dalej](distributed-data-management.md)