---
title: 'Środki zaradcze: PNG ramki w obiektach ikony'
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d67b2fac0c1d55bfa5594e90998d9613de4ad271
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659790"
---
# <a name="mitigation-png-frames-in-icon-objects"></a>Środki zaradcze: PNG ramki w obiektach ikony
Począwszy od programu .NET Framework 4.6 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> metoda konwertuje pomyślnie ikon PNG ramek do <xref:System.Drawing.Bitmap> obiektów.  
  
 W aplikacjach przeznaczonych dla platformy .NET Framework 4.5.2 i wcześniejszymi wersjami <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> metoda zgłasza wyjątek <xref:System.ArgumentOutOfRangeException> wyjątek Jeśli <xref:System.Drawing.Icon> obiekt ma ramek PNG.  
  
## <a name="impact"></a>Wpływ  
 Ta zmiana ma wpływ na aplikacje, które są ponownie kompilowane pod kątem programu .NET Framework 4.6 i implementują specjalna obsługa <xref:System.ArgumentOutOfRangeException> , jest generowany, gdy <xref:System.Drawing.Icon> obiekt ma ramek PNG. Podczas uruchamiania w .NET Framework 4.6, konwersja zakończy się pomyślnie, <xref:System.ArgumentOutOfRangeException> nie jest już zgłaszany, i w związku z tym program obsługi wyjątku nie jest już jest wywoływana.  
  
### <a name="mitigation"></a>Ograniczenie  
 Jeśli to zachowanie jest niepożądany, można zachować poprzednie zachowanie, dodając następujący element do [ \<runtime >](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) sekcji w pliku app.config:  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 Jeśli już zawiera plik app.config `AppContextSwitchOverrides` elementu, nowa wartość ma zostać scalona z `value` atrybutu w następujący sposób:  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a>Zobacz także
- [Zmiany retargetingu](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
