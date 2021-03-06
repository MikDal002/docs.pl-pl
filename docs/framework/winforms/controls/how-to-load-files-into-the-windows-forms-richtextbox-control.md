---
title: 'Instrukcje: Ładowanie plików do formantu RichTextBox formularzy Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: 99f869cd5fd3ffc35a58d3d4e7f12161cab3a7ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666049"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a>Instrukcje: Ładowanie plików do formantu RichTextBox formularzy Windows
Formularze Windows <xref:System.Windows.Forms.RichTextBox> formant może wyświetlać zwykłego tekstu, tekst zwykły Unicode lub tekst sformatowany (RTF) pliku. Aby to zrobić, należy wywołać <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> metody. Można również użyć <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> metodę, aby załadować dane ze strumienia. Aby uzyskać więcej informacji, zobacz <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.  
  
### <a name="to-load-a-file-into-the-richtextbox-control"></a>Ładowanie pliku w formancie RichTextBox  
  
1.  Określić ścieżkę do pliku, które były otwierane przy użyciu <xref:System.Windows.Forms.OpenFileDialog> składnika. Aby uzyskać przegląd, zobacz [OpenFileDialog, składnik — omówienie](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).  
  
2.  Wywołaj <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> metody <xref:System.Windows.Forms.RichTextBox> kontrolki, określając plik do załadowania i opcjonalnie typu pliku. W poniższym przykładzie plik do załadowania jest pobierana z <xref:System.Windows.Forms.OpenFileDialog> składnika <xref:System.Windows.Forms.FileDialog.FileName%2A> właściwości. Wywołanie metody z nazwą pliku jako argument tylko typu pliku będą uznawane za będące RTF. Aby określić inny typ pliku, należy wywołać metodę z wartością <xref:System.Windows.Forms.RichTextBoxStreamType> wyliczenia jako swój drugi argument.  
  
     W poniższym przykładzie <xref:System.Windows.Forms.OpenFileDialog> składnik jest wyświetlany po kliknięciu przycisku. Wybrany plik jest otwarty i wyświetlana w <xref:System.Windows.Forms.RichTextBox> kontroli. W tym przykładzie przyjęto założenie, formularz znajduje się przycisk`btnOpenFile`.  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) umieść następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  Aby uruchomić ten proces, zestaw może wymagać poziom uprawnień przyznanych przez <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> klasy. Jeśli używasz w kontekście częściowego zaufania, proces może zgłosić wyjątek, ze względu na niewystarczające uprawnienia. Aby uzyskać więcej informacji, zobacz [podstawy zabezpieczeń dostępu kodu](../../../../docs/framework/misc/code-access-security-basics.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox, kontrolka](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)
- [Kontrolki do użycia w formularzach Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
