---
title: Niezależne od kultury operacje na ciągach
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET Framework], culture-insensitive string operations
- strings [.NET Framework], culture-insensitive string operations
- localization [.NET Framework], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1e1b476a1de1f0c348e264c9dc6b42ceb81eff
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869344"
---
# <a name="culture-insensitive-string-operations"></a>Niezależne od kultury operacje na ciągach
Operacje na ciągach, w których jest uwzględniana kultura, mogą okazać się przydatne w przypadku tworzenia aplikacji, które mają wyświetlać wyniki użytkownikom na podstawie kultury. Domyślnie wrażliwość na ustawienia kulturowe metody uwzględniające kulturę do użycia z <xref:System.Globalization.CultureInfo.CurrentCulture%2A> właściwości dla bieżącego wątku.  
  
 Należy zauważyć, że operacje na ciągach, w których jest uwzględniana kultura, nie zawsze są pożądanym zachowaniem. Używanie operacji, w których jest uwzględniana kultura, gdy wyniki powinny być niezależne od kultury, może spowodować, że kod aplikacji przestanie działać w przypadku kultur z niestandardowymi mapowaniami wielkości liter i regułami sortowania. Aby uzyskać przykład, zobacz sekcję "Ciągów porównań, użyj bieżącej kultury" w [najlepsze rozwiązania dotyczące Using Strings](../../../docs/standard/base-types/best-practices-strings.md) artykułu.  
  
 To, czy w operacjach na ciągach powinna być uwzględniana kultura, zależy od tego, jak aplikacja używa wyników. W operacjach na ciągach, które wyświetlają wyniki użytkownikowi, zazwyczaj powinna być uwzględniana kultura. Na przykład jeśli aplikacja wyświetla posortowaną listę zlokalizowanych ciągów w polu listy, aplikacja powinna wykonać sortowanie z uwzględnieniem kultury.  
  
 W wynikach operacji na ciągach, które są używane wewnętrznie, zazwyczaj nie powinna być uwzględniana kultura. Ogólnie, jeśli aplikacja wykonuje operacje na nazwach plików, formatach trwałości lub informacjach symbolicznych, które nie są wyświetlane użytkownikowi, wyniki operacji na ciągach nie powinny ulegać zmianie w zależności od kultury. Na przykład jeśli aplikacja porównuje ciąg w celu ustalenia, czy jest on rozpoznawanym tagiem XML, w porównaniu nie powinna być uwzględniana kultura. Ponadto jeśli decyzja dot. zabezpieczeń opiera się na wynik ciągu porównania lub operacji zmiany przypadku, operacja nie powinna zależeć od kultury upewnij się, że wynik nie wpływa wartość <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.  
  
 Bez względu na to, czy jest tworzona aplikacja zawierająca kod służący do obsługi problemów lokalizacji i globalizacji, należy pamiętać o metodach programu .NET Framework pobierających domyślnie wyniki, w których jest uwzględniana kultura. Celem tego tematu jest zilustrowanie prawidłowego sposobu używania tych metod w aplikacjach w celu uzyskania wyników, w których nie jest uwzględniana kultura.  
  
## <a name="see-also"></a>Zobacz także

- [Globalizacja i lokalizacja](../../../docs/standard/globalization-localization/index.md)
