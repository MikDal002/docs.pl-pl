---
title: Aplikacje bazujące na proces programistyczny dla platformy Docker
description: Uzyskaj Przegląd wysokiego poziomu opcji do tworzenia aplikacji opartych na platformie Docker. Przy użyciu wybranego programu Visual Studio for Windows, Visual Studio for Mac lub Visual Studio Code obsługi dla wielu platform (Windows, Mac i Linux).
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/27/2018
ms.openlocfilehash: eb87f9a214dbffe71dae1e1739f2563c08fac280
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084930"
---
# <a name="development-process-for-docker-based-applications"></a>Proces programistyczny dotyczący aplikacji opartych na platformie Docker

*Opracowywanie konteneryzowanych aplikacji .NET lubisz, IDE skupia się za pomocą programu Visual Studio i Visual Studio tools for Docker lub interfejsu wiersza polecenia/Edytor skupia się przy użyciu interfejsu wiersza polecenia platformy Docker i Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Środowisko programistyczne dla aplikacji platformy Docker

### <a name="development-tool-choices-ide-or-editor"></a>Wybory dotyczące narzędzi rozwoju: Środowiskiem IDE lub edytorem

Czy wolisz, pełne i zaawansowanego środowiska IDE lub edytora lekkie i elastyczne, firma Microsoft ma narzędzia, które służą do tworzenia aplikacji platformy Docker.

**Program Visual Studio (for Windows).** Podczas opracowywania aplikacji platformy Docker za pomocą programu Visual Studio, zaleca się używać programu Visual Studio 2017 w wersji 15.7 lub nowszej, dostarczanego z tools for Docker wbudowane. Tools for Docker umożliwiają tworzenie, uruchamianie i Weryfikuj aplikacje bezpośrednio w docelowym środowisku platformy Docker. Naciśnij klawisz F5, aby uruchomić i zdebugować aplikację (jeden kontener lub wiele kontenerów) bezpośrednio do hosta platformy Docker lub naciśnij klawisze CTRL + F5, aby edytować i odświeżać aplikację bez konieczności ponownego kompilowania kontenera. Jest to najbardziej wydajnymi procesorami wybór rozwój aplikacji opartych na platformie Docker.

**Program Visual Studio dla komputerów Mac.** Jest środowisko IDE rozwoju programu Xamarin Studio działające w systemach macOS i obsługuje platformę Docker od połowy 2017. Powinna to być preferowanych przez dla deweloperów pracujących w komputerów Mac, również chcą korzystać z zaawansowanego środowiska IDE.

**Visual Studio Code i platformy Docker CLI**. Jeśli wolisz lekkie i Międzyplatformowe edytor, który obsługuje dowolny język programowania, można użyć programu Microsoft Visual Studio Code (VS Code) i interfejsu wiersza polecenia platformy Docker. Jest to podejście wieloplatformowego opracowywania aplikacji dla komputerów Mac, Linux i Windows. Ponadto Visual Studio Code obsługuje rozszerzenia dla platformy Docker, takie jak IntelliSense dla plików Dockerfile i skrót zadania to uruchamianie poleceń Docker z poziomu edytora.

Instalując [Docker Community Edition (CE)](https://www.docker.com/community-edition) narzędzi, można użyć pojedynczego interfejsu wiersza polecenia platformy Docker do tworzenia aplikacji dla systemów Windows i Linux.

### <a name="additional-resources"></a>Dodatkowe zasoby

- **Program Visual Studio**. Oficjalna witryna. \
  [*https://visualstudio.microsoft.com/vs/*](https://visualstudio.microsoft.com/vs/)

- **Program Visual Studio Code** Oficjalna witryna. \
  [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

- **Platformę docker Community Edition (CE) dla systemów Mac i Windows** \
  [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>.NET, języków i struktur dla kontenerów Docker

Jak wspomniano we wcześniejszych sekcjach tego przewodnika, można użyć środowiska .NET Framework, .NET Core lub projekt Mono typu open-source podczas opracowywania Docker kontenerowych nimi aplikacji .NET. Możesz tworzyć w języku C\#, F\#, lub Visual Basic podczas określania wartości docelowej systemu Linux lub Windows kontenery, w zależności od tego, które .NET framework jest w użyciu. Dla większej liczby języków about.NET szczegółowe informacje, zobacz wpis w blogu [strategia językowa platformy .NET](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/).

>[!div class="step-by-step"]
>[Poprzednie](../architect-microservice-container-applications/using-azure-service-fabric.md)
>[dalej](docker-app-development-workflow.md)