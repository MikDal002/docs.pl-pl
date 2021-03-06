---
title: notMarshalable MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cec3fd0c3b20c70b6ddf3e875c481e829dd5eb28
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695494"
---
# <a name="notmarshalable-mda"></a>notMarshalable MDA
`notMarshalable` Zarządzanego Asystenta debugowania (MDA) jest aktywowany, gdy środowisko uruchomieniowe języka wspólnego (CLR) napotka wskaźnika interfejsu COM bez prawidłowe zarejestrowanych proxy/zastępczego lub niepoprawne `IMarshal` implementacji podczas próby interfejsu Kieruj interfejsu w różnych kontekstach.  
  
## <a name="symptoms"></a>Symptomy  
 Wywołania nie są obsługiwane lub występować wywołań w nieprawidłowym kontekście dla wskaźników interfejsu COM.  
  
## <a name="cause"></a>Przyczyna  
 Nie prawidłowe zarejestrowanych proxy/zastępczego lub niepoprawne `IMarshal` podczas próby kierować interfejsu w różnych kontekstach.  
  
## <a name="resolution"></a>Rozwiązanie  
 Upewnij się, pełnomocnika namiastki zarejestrowany oraz że `IMarshal` wdrożenia jest prawidłowy.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  
 To zdarzenie MDA nie ma wpływu na środowiska uruchomieniowego.  
  
## <a name="output"></a>Dane wyjściowe  
 Komunikat opisujący problem.  
  
## <a name="configuration"></a>Konfiguracja  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshaling międzyoperacyjny](../../../docs/framework/interop/interop-marshaling.md)
