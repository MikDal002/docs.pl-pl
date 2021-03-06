---
title: gcUnmanagedToManaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c99ae7d222db2e44de471eb9a41fed614362e300
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614383"
---
# <a name="gcunmanagedtomanaged-mda"></a>gcUnmanagedToManaged MDA
`gcUnmanagedToManaged` Zarządzanego Asystenta debugowania (MDA) powoduje wyrzucania elementów bezużytecznych, zawsze wtedy, gdy wątku przechodzi z niezarządzane do zarządzanego kodu.  
  
## <a name="symptoms"></a>Symptomy  
 Wywoływanie uruchomione składniki niezarządzane użytkownika za pomocą modelu COM i platformy aplikacji powoduje naruszenie zasad dostępu niedeterministyczne w CLR.  
  
## <a name="cause"></a>Przyczyna  
 Jeśli aplikacja jest uruchomiona składniki niezarządzane użytkownika, następnie tych składników może mieć uszkodzony stosu odśmieconej pamięci. Powoduje naruszenie zasad dostępu w CLR, gdy moduł zbierający elementy bezużyteczne próbuje zapoznaj się z wykresu obiektu.  
  
## <a name="resolution"></a>Rozwiązanie  
 Włączenie tego Asystenta skraca czas między po niezarządzanych składnika wykonana spowoduje uszkodzenie stosu odśmieconej pamięci i kiedy naruszenie zasad dostępu ma miejsce wymuszenia wyrzucania elementów bezużytecznych występuje przed każdym Zarządzanie zmianami.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  
 Powoduje, że wyrzucania elementów bezużytecznych zawsze wtedy, gdy przejścia wątków, z niezarządzanych w kodzie zarządzanym.  
  
## <a name="output"></a>Dane wyjściowe  
 To zdarzenie MDA nie daje żadnych danych wyjściowych.  
  
## <a name="configuration"></a>Konfiguracja  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [gcManagedToUnmanaged](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)
- [Marshaling międzyoperacyjny](../../../docs/framework/interop/interop-marshaling.md)
