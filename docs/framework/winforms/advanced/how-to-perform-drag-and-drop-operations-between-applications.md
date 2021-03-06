---
title: 'Instrukcje: Wykonywanie operacji przeciągania i upuszczania między aplikacjami'
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
ms.openlocfilehash: 89b1b89c01ba80393e0965858d7767d5c9029003
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718441"
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a>Instrukcje: Wykonywanie operacji przeciągania i upuszczania między aplikacjami
Wykonywanie operacji przeciągania i upuszczania między aplikacjami jest nie różni się od włączania tej akcji w aplikacji, tak długo, jak obie aplikacje, które są zaangażowane zachowują się zgodnie z "Umowy" między <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> i <xref:System.Windows.Forms.DragEventArgs.Effect%2A> właściwości.  
  
 W poniższej procedurze użyje tworzonych aplikacji opartych na Windows i program WordPad edytora tekstów, dostępnej w systemie operacyjnym Windows do wykonywania operacji przeciągania i upuszczania między aplikacjami. Program WordPad ma określone dozwolone efekty, że tekst przeciąganie i upuszczanie; Aplikacja oparta na Windows, który trzeba napisać kod, aby uzyskać będzie działać z tych skutków, dzięki czemu może można pomyślnie ukończyć operacji przeciągania i upuszczania.  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a>Aby wykonać procedurę przeciągania i upuszczania między aplikacjami  
  
1.  Tworzenie nowej aplikacji Windows Forms.  
  
2.  Dodaj <xref:System.Windows.Forms.TextBox> formantu do formularza.  
  
3.  Konfigurowanie <xref:System.Windows.Forms.TextBox> kontroli na odbieranie danych porzucone.  
  
     Aby uzyskać więcej informacji, zobacz [instruktażu: Wykonywanie operacji przeciągania i upuszczania w formularzach Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
4.  Uruchom aplikację z systemem Windows, a aplikacja jest uruchomiona, uruchom program WordPad.  
  
     Program WordPad, jest Edytor tekstu, zainstalowane przez Windows, która umożliwia wykonywanie operacji przeciągania i upuszczania. Nie jest dostępny, naciskając klawisz **Start** przycisku, wybierając **Uruchom**, a następnie wpisując `WordPad` w polu tekstowym z **Uruchom** okna dialogowego pole i klikając **OK**.  
  
5.  Po otwarciu programu WordPad, wpisz ciąg tekstowy do niego.  
  
6.  Za pomocą myszy, zaznacz tekst, a następnie przeciągnij zaznaczony tekst do <xref:System.Windows.Forms.TextBox> kontrolki w aplikacji z systemem Windows.  
  
     Zauważ, że gdy wskaźnik myszy nad <xref:System.Windows.Forms.TextBox> kontroli (i w związku z tym, wywoływanie <xref:System.Windows.Forms.Control.DragEnter> zdarzeń), zmiany kursora, na które mogą porzucić zaznaczonego tekstu do <xref:System.Windows.Forms.TextBox> kontroli.  
  
     Ponadto można skonfigurować usługi <xref:System.Windows.Forms.TextBox> formantu, aby umożliwić ciągów tekstowych można przeciągnąć i upuścić na WordPad. Aby uzyskać więcej informacji, zobacz [instruktażu: Wykonywanie operacji przeciągania i upuszczania w formularzach Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
## <a name="see-also"></a>Zobacz także
- [Instrukcje: Dodawanie danych do Schowka](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
- [Instrukcje: Pobieranie danych ze Schowka](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
- [Operacje przeciągania i upuszczania oraz obsługa schowka](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)
