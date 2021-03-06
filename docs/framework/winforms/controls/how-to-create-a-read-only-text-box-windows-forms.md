---
title: 'Instrukcje: Tworzenie pola tekstowego tylko do odczytu (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 89d331f6c7fad5880aff031eb808199292e493a6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670345"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>Instrukcje: Tworzenie pola tekstowego tylko do odczytu (Windows Forms)
Można edytować pole tekstowe Windows Forms można przekształcić do kontrolki tylko do odczytu. Na przykład pola tekstowego może wyświetlić wartość, która zwykle jest edytowany, ale nie może być aktualnie, ze względu na stan aplikacji.  
  
### <a name="to-create-a-read-only-text-box"></a>Aby utworzyć pole tekstowe tylko do odczytu  
  
1.  Ustaw <xref:System.Windows.Forms.TextBox> kontrolki <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> właściwość `true`. Z właściwością ustawioną na `true`, użytkownicy nadal mogą przewijać i wyróżnianie tekstu w polu tekstowym bez możliwości zmiany. A **kopiowania** polecenie działa w polu tekstowym, ale **Wytnij** i **Wklej** polecenia nie są.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Właściwość ma wpływ tylko na interakcji z użytkownikiem w czasie wykonywania. Nadal można zmienić zawartości pola tekstowego programowo w czasie wykonywania, zmieniając <xref:System.Windows.Forms.TextBox.Text%2A> właściwości pola tekstowego.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.TextBox>
- [TextBox, kontrolka — omówienie](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [Instrukcje: Kontrolowanie punktu wstawiania w formancie TextBox formularzy Windows](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [Instrukcje: Tworzenie pola tekstowego hasła za pomocą kontrolki TextBox formularzy Windows](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [Instrukcje: Umieszczanie cudzysłowu w ciągu](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [Instrukcje: Zaznaczanie tekstu w formancie TextBox formularzy Windows](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [Instrukcje: Wyświetlanie wielu wierszy w formancie TextBox formularzy Windows](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox, kontrolka](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
