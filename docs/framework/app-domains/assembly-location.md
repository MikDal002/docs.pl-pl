---
title: Lokalizacja zestawu
ms.date: 03/30/2017
helpviewer_keywords:
- locating assemblies
- assemblies [.NET Framework], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0b065fe488031329815f6ec38da9661fd19700d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54529937"
---
# <a name="assembly-location"></a>Lokalizacja zestawu
Lokalizacja zestawu Określa, czy można wyszukanie w przypadku odwołania do środowiska uruchomieniowego języka wspólnego i można również określić, czy zestaw mogą być współużytkowane z innymi zestawami. Można wdrożyć zestaw w następujących lokalizacjach:  
  
-   Katalog aplikacji lub podkatalogi.  
  
     Jest to najbardziej typowe lokalizacja do wdrażania zestawu. Podkatalogi katalogu głównego aplikacji może bazować na języka lub kultury. Jeśli zestaw ma informacje w atrybucie kultury, należy w podkatalogu w katalogu aplikacji o nazwie tej kultury.  
  
-   Global assembly cache.  
  
     Jest to pamięć podręczna kodu dla całego komputera, zainstalowanym wszędzie tam, gdzie zainstalowano środowisko uruchomieniowe języka wspólnego. W większości przypadków Jeśli zamierzasz dzielenie się zestawem z wielu aplikacji, należy wdrożyć ją w globalnej pamięci podręcznej.  
  
-   Na serwerze HTTP.  
  
     Zestaw wdrożonych na serwerze HTTP musi mieć silną nazwą; wskaż zestawu w części bazy kodu w pliku konfiguracji aplikacji.  
  
## <a name="see-also"></a>Zobacz także
- [Tworzenie zestawów](../../../docs/framework/app-domains/create-assemblies.md)
- [Global Assembly Cache](../../../docs/framework/app-domains/gac.md)
- [Sposoby lokalizowania zestawów przez środowisko uruchomieniowe](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Programowanie za pomocą zestawów](../../../docs/framework/app-domains/programming-with-assemblies.md)
