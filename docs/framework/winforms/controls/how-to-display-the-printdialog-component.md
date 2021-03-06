---
title: Wyświetlanie składnika PrintDialog
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 198ae75d407bd1837033a1cc186d84ff972fdc2f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285158"
---
# <a name="how-to-display-the-printdialog-component"></a>Wyświetlanie składnika PrintDialog

<xref:System.Windows.Forms.PrintDialog> Składnik to standardowe okno dialogowe drukowania Windows wielu użytkowników należy zapoznać się z. Ponieważ użytkownicy będą natychmiast doświadczenia z nią, korzystne byłoby do użycia <xref:System.Windows.Forms.PrintDialog> składnika.

## <a name="to-display-the-printdialog-component"></a>Aby Wyświetlanie składnika PrintDialog

- Wywołaj <xref:System.Windows.Forms.Form.ShowDialog%2A> metody z kodem aplikacji.

     Gdy składnik zostanie wyświetlone, użytkownicy będą korzystać z niego, ustawienie właściwości zadania drukowania. Są one zapisywane w <xref:System.Drawing.Printing.PrinterSettings> klasy (i <xref:System.Drawing.Printing.PageSettings> klasy, jeśli użytkownik uzyskuje dostęp do [PageSetupDialog, składnik](pagesetupdialog-component-windows-forms.md) za pośrednictwem <xref:System.Windows.Forms.PrintDialog> składnika) skojarzonego z tym zadaniem drukowania. Następnie można prowadzić rozmowy właściwości zestawu określić szczegóły zadania drukowania.

## <a name="see-also"></a>Zobacz także

- [Instrukcje: Tworzenie zadań drukowania formularzy Windows Standard](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [Instrukcje: Przechwytywanie danych wejściowych użytkownika ze składnika PrintDialog w czasie wykonywania](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [PrintPreviewDialog, kontrolka](printpreviewdialog-control-windows-forms.md)
- [PrintDialog, składnik](printdialog-component-windows-forms.md)
- [Obsługa drukowania w formularzach Windows Forms](../advanced/windows-forms-print-support.md)
- [Kontrolki formularzy Windows Forms](index.md)