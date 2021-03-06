---
title: gcManagedToUnmanaged MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: add5ba59f8f59fc013f8c04a186b34e711c1490c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537936"
---
# <a name="gcmanagedtounmanaged-mda"></a>gcManagedToUnmanaged MDA
`gcManagedToUnmanaged` Zarządzanego Asystenta debugowania (MDA) powoduje wyrzucania elementów bezużytecznych, zawsze wtedy, gdy wątku przechodzi z kodu zarządzanego do kodu niezarządzanego.  
  
## <a name="symptoms"></a>Symptomy  
 Składnik użytkownika niezarządzanego zgłasza naruszenie zasad dostępu podczas próby użycia obiektu zarządzanego, który ma być narażone na model COM. Obiekt COM, prawdopodobnie zostały zwolnione. Naruszenie zasad dostępu jest niedeterministyczny.  
  
## <a name="cause"></a>Przyczyna  
 Jeśli niezarządzane składnika nie jest zliczanie zarządzanego obiektu COM poprawnie, środowisko uruchomieniowe można zebrać uwidaczniany w modelu COM, gdy składnik niezarządzanych nadal zawiera odwołanie do obiektu zarządzanego obiektu. Środowisko uruchomieniowe wywołuje <xref:System.Runtime.InteropServices.Marshal.Release%2A> podczas wyrzucania elementów bezużytecznych, więc jeśli użytkownik składnik używa obiektu, zanim wystąpi wyrzucania elementów bezużytecznych, następnie go będzie nie jeszcze zostać zebrane. To źródło nondeterminism.  
  
## <a name="resolution"></a>Rozwiązanie  
 Włączenie tego Asystenta skraca czas między po obiekcie kwalifikuje się do kolekcji i <xref:System.Runtime.InteropServices.Marshal.Release%2A> jest wywoływana, pomaga śledzić określają składnik niezarządzanych po raz pierwszy próbuje uzyskać dostępu do obiektu zebrane.  
  
## <a name="effect-on-the-runtime"></a>Wpływ na środowisko uruchomieniowe  
 Powoduje, że wyrzucania elementów bezużytecznych zawsze wtedy, gdy przejścia wątków, z kodu zarządzanego do kodu niezarządzanego.  
  
## <a name="output"></a>Dane wyjściowe  
 To zdarzenie MDA nie daje żadnych danych wyjściowych.  
  
## <a name="configuration"></a>Konfiguracja  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnozowanie błędów przy użyciu asystentów zarządzanego debugowania](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Marshaling międzyoperacyjny](../../../docs/framework/interop/interop-marshaling.md)
- [gcUnmanagedToManaged](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
