---
title: IPv6 Routing
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
ms.openlocfilehash: dabf17f85330b884918d5c6e1bc9832a7a0dbd02
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694818"
---
# <a name="ipv6-routing"></a>IPv6 Routing
Elastyczny mechanizm routingu jest to korzyść protokołu IPv6. Ze względu na sposób, w których IPv4 zostały identyfikatory sieci i nie są przydzielone, duże tabele routingu muszą być przechowywane przez routery, które znajdują się na szkieletowymi Internet. Te routery musi znać wszystkie trasy, aby przekazywać pakiety, które są potencjalnie skierowany do dowolnego węzła w Internecie. Zdolność do agregacji adresów IPv6 umożliwia elastyczne adresowania i znacząco zmniejsza rozmiar tabele routingu. W tej nowej architektury adresowania routery pośrednie musi śledzić tylko lokalnej części sieci w celu przekazywania wiadomości odpowiednio.  
  
## <a name="neighbor-discovery"></a>Odnajdywanie sąsiadujących  
 Niektóre z funkcji oferowanych przez funkcję odnajdowania sąsiadów to:  
  
-   Odnajdywanie routera. To pozwala hostom na identyfikację lokalne routery.  
  
-   Adres rozdzielczości. Dzięki temu węzłów do rozpoznania adresu warstwy linku, aby uzyskać odpowiedni adres następnego przeskoku (wymiana Address Resolution Protocol [ARP]).  
  
-   Adres automatycznej konfiguracji. Dzięki temu hosty automatycznie skonfigurować adresów lokalnych i globalnych.  
  
 Odnajdywanie sąsiadujących używa Internet Control Message Protocol dla IPv6 (ICMPv6) wiadomości, które obejmują:  
  
-   Anons routera. Wysyłany przez router pseudolosowego okresowo lub w odpowiedzi na żądanie routera. Routery IPv6 użyć anonse routera, aby anonsować ich dostępności, prefiksów adresów i inne parametry.  
  
-   Żądanie routera. Wysyłany przez hosta, by zażądać, routery łącze natychmiast wysyłać anons routera.  
  
-   Żądanie sąsiadów. Wysyłane przez węzły do rozpoznawania adresów, wykrywanie powtarzających się adresów, lub sprawdź, czy sąsiada jest nadal dostępny.  
  
-   Anons sąsiadów. Wysyłane przez węzły, aby odpowiedzieć na żądanie sąsiadów lub powiadamiania sąsiadów zmianę adresu warstwy linku.  
  
-   Przekierowanie. Wysyłane przez routery, aby wskazać, lepsze adres następnego przeskoku do określonego miejsca docelowego dla wysyłania węzła.  
  
## <a name="see-also"></a>Zobacz także
- [Protokół IPv6](../../../docs/framework/network-programming/internet-protocol-version-6.md)
- [Gniazda](../../../docs/framework/network-programming/sockets.md)
