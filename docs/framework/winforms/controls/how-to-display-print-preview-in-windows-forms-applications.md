---
title: 'Instrukcje: Wyświetlanie podglądu wydruku w Windows Forms aplikacji'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: d348c89e3334543cf935e5faec29e546d848a984
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526733"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>Instrukcje: Wyświetlanie podglądu wydruku w Windows Forms aplikacji
Możesz użyć <xref:System.Windows.Forms.PrintPreviewDialog> sterowania, aby użytkownicy mogli wyświetlić dokument, często, zanim zostanie do wydrukowania.  
  
 Aby to zrobić, należy określić wystąpienie <xref:System.Drawing.Printing.PrintDocument> klasy; jest to dokument do wydrukowania. Aby uzyskać więcej informacji na temat przy użyciu podglądu wydruku z <xref:System.Drawing.Printing.PrintDocument> składników, zobacz [jak: Drukowanie w formularzach Windows Forms przy użyciu podglądu wydruku](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md).  
  
> [!NOTE]
>  Aby użyć <xref:System.Windows.Forms.PrintPreviewDialog> kontroli w czasie wykonywania, użytkownicy muszą mieć zainstalowany na komputerze, lokalnie lub za pośrednictwem sieci, drukarki, jest częściowo sposób, w jaki <xref:System.Windows.Forms.PrintPreviewDialog> składnika określa wygląd dokumentu po wydrukowaniu.  
  
 <xref:System.Windows.Forms.PrintPreviewDialog> Kontrolować używa <xref:System.Drawing.Printing.PrinterSettings> klasy. Ponadto <xref:System.Windows.Forms.PrintPreviewDialog> kontrolować używa <xref:System.Drawing.Printing.PageSettings> klasy, podobnie jak <xref:System.Windows.Forms.PrintPreviewDialog> składników. Drukuj dokument określone w <xref:System.Windows.Forms.PrintPreviewDialog> kontrolki <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> właściwość odwołuje się do obu wystąpień <xref:System.Drawing.Printing.PrinterSettings> i <xref:System.Drawing.Printing.PageSettings> klasy i te, które są używane do renderowania dokumentu w oknie podglądu.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>Aby wyświetlić strony za pomocą printpreviewdialog — formant  
  
-   Użyj <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> metodę, aby wyświetlić okno dialogowe, określając <xref:System.Drawing.Printing.PrintDocument> do użycia.  
  
     W poniższym przykładzie kodu <xref:System.Windows.Forms.Button> kontrolki <xref:System.Windows.Forms.Control.Click> programu obsługi zdarzeń otwaiera wystąpienia programu <xref:System.Windows.Forms.PrintPreviewDialog> kontroli. Drukuj dokument jest określona w <xref:System.Windows.Forms.PrintDialog.Document%2A> właściwości. W poniższym przykładzie jest określony żaden dokument drukowania.  
  
     Przykład wymaga, że formularz ma <xref:System.Windows.Forms.Button> kontroli <xref:System.Drawing.Printing.PrintDocument> składnika o nazwie `myDocument`, a <xref:System.Windows.Forms.PrintPreviewDialog> kontroli.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) umieść następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Zobacz także
- [PrintDocument, składnik](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
- [PrintPreviewDialog, kontrolka](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)
- [Obsługa drukowania w formularzach Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
- [Windows Forms](../../../../docs/framework/winforms/index.md)
