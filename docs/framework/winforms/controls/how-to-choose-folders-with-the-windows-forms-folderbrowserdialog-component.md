---
title: 'Instrukcje: Wybierz foldery, za pomocą składnika FolderBrowserDialog formularzy Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: 7055875f25aa0f39feb2d944f4b6684c6ae5d9a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614696"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a>Instrukcje: Wybierz foldery, za pomocą składnika FolderBrowserDialog formularzy Windows
Często w aplikacji Windows, które tworzysz, trzeba będzie monitować użytkowników o wybranie folderu, większość często, aby zapisać zestawu plików. Formularze Windows <xref:System.Windows.Forms.FolderBrowserDialog> składnik umożliwia łatwe wykonać to zadanie.  
  
### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a>Aby wybrać foldery, za pomocą składnika FolderBrowserDialog  
  
1.  W procedurze, sprawdź <xref:System.Windows.Forms.FolderBrowserDialog> składnika <xref:System.Windows.Forms.Form.DialogResult%2A> właściwości, aby zobaczyć, jak zostało zamknięte okno dialogowe i uzyskać wartość <xref:System.Windows.Forms.FolderBrowserDialog> składnika <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> właściwości.  
  
2.  Jeśli zachodzi potrzeba folderu zestawu najlepszy, która będzie wyświetlana w widoku drzewa okna dialogowego, ustaw <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> właściwość, która przyjmuje członkiem <xref:System.Environment.SpecialFolder> wyliczenia.  
  
3.  Ponadto można ustawić <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> właściwość, która określa ciąg znaków, który pojawia się w górnej części widoku drzewa przeglądarka folderów.  
  
     W poniższym przykładzie <xref:System.Windows.Forms.FolderBrowserDialog> składnik jest używany do wybierania folderu, podobnie jak podczas tworzenia projektu w programie Visual Studio i monit o wybranie folderu do zapisania go w. W tym przykładzie nazwa folderu jest następnie wyświetlana w <xref:System.Windows.Forms.TextBox> formant w formularzu. To dobry pomysł, aby umieścić lokalizacji w obszarze można edytować, takich jak <xref:System.Windows.Forms.TextBox> kontrolować, dzięki czemu użytkownicy mogą edytować ich zaznaczenia w przypadku błędu lub innych kwestiach. W tym przykładzie przyjęto założenie, formularz z <xref:System.Windows.Forms.FolderBrowserDialog> składnika i <xref:System.Windows.Forms.TextBox> kontroli.  
  
    ```vb  
    Public Sub ChooseFolder()  
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then  
            TextBox1.Text = FolderBrowserDialog1.SelectedPath  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    public void ChooseFolder()  
    {  
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)   
        {  
            textBox1.Text = folderBrowserDialog1.SelectedPath;  
        }  
    }  
    ```  
  
    ```cpp  
    public:  
       void ChooseFolder()  
       {  
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Text = folderBrowserDialog1->SelectedPath;  
          }  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Aby użyć tej klasy, zestaw wymaga poziom uprawnień przyznanych przez <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> właściwość, która jest częścią programu <xref:System.Security.Permissions.FileIOPermissionAccess> wyliczenia. Jeśli używasz w kontekście częściowego zaufania, proces może zgłosić wyjątek, ze względu na niewystarczające uprawnienia. Aby uzyskać więcej informacji, zobacz [podstawy zabezpieczeń dostępu kodu](../../../../docs/framework/misc/code-access-security-basics.md).  
  
 Aby uzyskać informacje na temat sposobu zapisywania plików, zobacz [jak: Zapisywanie plików za pomocą składnika SaveFileDialog](../../../../docs/framework/winforms/controls/how-to-save-files-using-the-savefiledialog-component.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [FolderBrowserDialog, składnik — omówienie (Windows Forms)](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-overview-windows-forms.md)
- [FolderBrowserDialog, składnik](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
