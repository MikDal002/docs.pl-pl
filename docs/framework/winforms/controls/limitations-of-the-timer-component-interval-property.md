---
title: Ograniczenia właściwości Interval składnika Timer formularzy systemu Windows
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 2d8e25d9d27c0908f2d794a0c3c9646024984764
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269679"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Ograniczenia właściwości Interval składnika Timer formularzy systemu Windows
Formularze Windows <xref:System.Windows.Forms.Timer> składnik ma <xref:System.Windows.Forms.Timer.Interval%2A> właściwość, która określa liczbę milisekund, które przechodzą między zdarzenie czasomierza jeden, a następnie. Jeśli składnik jest wyłączony, czasomierz w dalszym ciągu otrzymywać <xref:System.Windows.Forms.Timer.Tick> zdarzeń w przybliżeniu jednakowej odstępach czasu.  
  
 Ten składnik jest przeznaczony dla środowiska Windows Forms. Jeśli potrzebujesz czasomierza, która jest odpowiednia w środowisku serwera, zobacz [wprowadzenie do serwerowych czasomierzy](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>Właściwości interwału  
 <xref:System.Windows.Forms.Timer.Interval%2A> Właściwość ma pewne ograniczenia, które należy wziąć pod uwagę podczas programowania <xref:System.Windows.Forms.Timer> składników:  
  
-   Jeśli aplikacja lub innej aplikacji wysokimi wymaganiami w systemie — takiej jak długo pętli, intensywnie korzystających z obliczeń, dysków, sieci lub dostępu do portu — aplikacja nie może pobrać zdarzenia czasomierza, tak często, jak <xref:System.Windows.Forms.Timer.Interval%2A> określa właściwości.  
  
-   Interwał nie musi upłynąć dokładnie na czas. W celu zapewnienia dokładności, czasomierz powinien sprawdzanie zegara systemowego zgodnie z potrzebami, a nie spróbuj śledzić czas skumulowana wewnętrznie.  
  
-   Dokładność <xref:System.Windows.Forms.Timer.Interval%2A> właściwość jest podana w milisekundach. Niektóre komputery udostępniają licznika o wysokiej rozdzielczości o rozdzielczości wyższej niż milisekund. Dostępność tych liczników jest zależna od sprzętu procesora komputera.
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.Timer>
- [Timer, składnik](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)
- [Timer, składnik — omówienie](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
