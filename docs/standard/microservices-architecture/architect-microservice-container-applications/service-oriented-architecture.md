---
title: Architektury zorientowanej na usługi
description: Dowiedz się, podstawowe różnice między mikrousług i architektury zorientowanej na usługi (SOA).
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/20/2018
ms.openlocfilehash: d19053d8296dbe75ac1e0ce037d6a713d9f5687c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148616"
---
# <a name="service-oriented-architecture"></a>Architektury zorientowanej na usługi

Dotycząca architektury zorientowanej na usługi (SOA) był nadmiernego obciążenia termin i spowodował, że różne dla różnych osób. Jednak jako uniwersalność, SOA oznacza, że struktury aplikacji przez podzielenie go na wiele usług (najczęściej jako usługi HTTP), które mogą być klasyfikowane jako różnych typów, takich jak podsystemów lub warstwy.

Te usługi można teraz wdrażać jako kontenery platformy Docker, która rozwiązuje problemy z wdrażaniem, ponieważ wszystkie zależności są uwzględnione w obrazie kontenera. Po musisz skalować aplikacje SOA, Niewykluczone, że skalowalności i dostępności wyzwania, Jeżeli wdrażasz oparte na jednym hostów platformy Docker. Jest to gdzie oprogramowania klastra Docker lub orchestrator może pomóc, zgodnie z opisem w kolejnych sekcjach, w której opisano metody wdrażania mikrousług.

Kontenery platformy docker są przydatne (ale nie jest wymagane) dla bardziej zaawansowanych architektur mikrousług i tradycyjnych architekturach zorientowane na usługę.

Mikrousługi dziedziczyć SOA, ale SOA różni się od architektury mikrousług. Funkcje, takie jak duża brokerów centralnej, centralna koordynatorów na poziomie organizacji i [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) jest typowy w SOA. Jednak w większości przypadków są to niezalecane wzorce dotyczące społeczności mikrousług. W rzeczywistości niektórzy dokumentu uważają, że "architekturze mikrousług jest SOA wykonać".

Ten przewodnik koncentruje się na mikrousługach, ponieważ metoda SOA jest mniej normatywne niż wymagania i technik stosowanych w ramach architektury mikrousługi. Jeśli znasz sposób tworzenia aplikacji opartych na mikrousługach, możesz również wie, jak tworzyć prostsze aplikacji usługowych.

>[!div class="step-by-step"]
>[Poprzednie](docker-application-state-data.md)
>[dalej](microservices-architecture.md)