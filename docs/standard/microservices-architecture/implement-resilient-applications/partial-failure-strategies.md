---
title: Strategie dotyczące obsługi częściowych niepowodzeń
description: Ustal, jakimi kilka strategii obsługi częściowych niepowodzeń bezpiecznie.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: ad45e357c1656b9346b7bdb5f324bde5fa76eaba
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362772"
---
# <a name="strategies-to-handle-partial-failure"></a>Strategie do obsługi częściowych niepowodzeń

Strategie dotyczące postępowania z błędami częściowe są następujące.

**Użyj asynchronicznej komunikacji (na przykład, oparta na komunikatach) na wewnętrznej mikrousług**. Zaleca się wysoce nie utworzyć długie łańcuchy synchroniczne wywołania HTTP między wewnętrznego mikrousług, ponieważ niepoprawne projektu staną się ostatecznie główną przyczynę awarii zła. Przeciwnie, z wyjątkiem frontonu komunikację między aplikacjami klienta i pierwszy poziom mikrousług lub szczegółowe bramy interfejsu API, zaleca się komunikacji przy użyciu tylko asynchroniczne (oparta na komunikatach) jeden raz w przeszłości początkowego żądania / Cykl odpowiedzi na wewnętrzny mikrousług. Aby zminimalizować wpływ ripple pomoże oparte na zdarzeniach architektury i spójności ostatecznej. Te metody wymuszania wyższego poziomu autonomii mikrousług i w związku z tym zapobiec problem oznaczane w tym miejscu.

**Użyj ponownych prób z wykorzystaniem wykładniczego wycofywania**. Ta technika pozwala uniknąć krótki i sporadycznych błędów, wykonując wywołanie ponawia próbę kilka razy, w przypadku, gdy usługa nie jest dostępna tylko przez krótki czas. Taka sytuacja może wystąpić z powodu problemów z sieciowych okresowymi lub mikrousług/kontenera zostanie przeniesiony do innego węzła w klastrze. Jednak jeśli te ponownych prób nie są zaprojektowane prawidłowo w przypadku wyłączników, jego pogłębić skutki ripple ostatecznie nawet powodujące [przeprowadzenie ataku typu "odmowa usługi" (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).

**Obejście sieci przekroczeń limitu czasu**. Ogólnie rzecz biorąc klientów powinny zaprojektowana, aby nie blokować w sposób ciągły i zawsze używaj przekroczeń limitu czasu podczas oczekiwania na odpowiedź. Korzystanie z limitów czasu zapewnia, że zasoby są nigdy nie blokowana przez czas nieokreślony.

**Użyj wzorca wyłącznika**. W tym podejściu procesu klienta śledzi liczbę żądań zakończonych niepowodzeniem. Jeśli tak, aby dalszych prób od razu zakończyć się niepowodzeniem, współczynnik błędów przekracza skonfigurowany limit wycieczek "wyłącznik". (Jeśli dużą liczbę żądań kończą się niepowodzeniem, umożliwiającej wyświetlanie sugerowanych usługa jest niedostępna i że wysyłania żądań jest sensu.) Po upływie limitu czasu klient powinien ponownie i, jeśli nowe żądania się pomyślnie, zamykając wyłącznik.

**Podaj planów awaryjnych**. W tym podejściu procesu klienta sprawdza logiki rezerwowej, gdy żądanie zakończy się niepowodzeniem, takie jak przekazywania danych z pamięci podręcznej lub wartość domyślną. To podejście jest odpowiednie dla zapytań i jest bardziej złożona dla aktualizacji lub poleceń.

**Ogranicz liczbę żądań w kolejce**. Klienci także powinny nakładać górnej granicy liczby oczekujących żądań, które mikrousług klienta mogą wysyłać do określonej usługi. Jeśli zostanie osiągnięty limit jest prawdopodobnie sensu dodatkowych żądań i tych prób powinna zakończyć się niepowodzeniem natychmiast. Pod względem implementacji Polly [izolacji grodziowym](https://github.com/App-vNext/Polly/wiki/Bulkhead) zasady mogą służyć do spełnienia tego wymagania. To podejście jest zasadniczo ograniczania przetwarzania równoległego przy użyciu <xref:System.Threading.SemaphoreSlim> jako implementacja. Umożliwia on również poza grodzi "kolejki". Możesz proaktywnie zmniejszenia nadmiernego obciążenia, nawet przed wykonaniem, (na przykład, ponieważ za pojemność jest pełna). Dzięki temu swojej odpowiedzi do pewnych scenariuszy awarii szybciej, niż byłoby wyłącznika, ponieważ wyłącznik czeka, aż po awarii. Obiekt BulkheadPolicy [Polly](http://www.thepollyproject.org/) są ujawnia jak Pełna grodziowym i kolejki, a oferty zdarzenia przy przepełnieniu tak może także służyć do kierowania, automatyczne skalowanie w poziomie.

## <a name="additional-resources"></a>Dodatkowe zasoby

- **Wzorce odporności**\
  [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](/azure/architecture/patterns/category/resiliency)

- **Dodawanie odporności i optymalizacji wydajności**\
  [*https://msdn.microsoft.com/library/jj591574.aspx*](https://msdn.microsoft.com/library/jj591574.aspx)

- **Bulkhead.** Repozytorium GitHub. Implementacja za pomocą zasad Polly. \
  [*https://github.com/App-vNext/Polly/wiki/Bulkhead*](https://github.com/App-vNext/Polly/wiki/Bulkhead)

- **Projektowanie aplikacji odpornych na błędy dla platformy Azure**\
  [*https://docs.microsoft.com/azure/architecture/resiliency/*](/azure/architecture/resiliency/)

- **Obsługa błędu przejściowego**\
  [*https://docs.microsoft.com/azure/architecture/best-practices/transient-faults*](/azure/architecture/best-practices/transient-faults)

>[!div class="step-by-step"]
>[Poprzednie](handle-partial-failure.md)
>[dalej](implement-retries-exponential-backoff.md)