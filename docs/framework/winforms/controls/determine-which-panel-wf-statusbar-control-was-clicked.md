---
title: 'Instrukcje: Określanie, które panelu w formancie StatusBar formularzy Windows został kliknięty'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: 2907b6344cd4fcc7c7d84c110dbc638cdc86f23c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708327"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>Instrukcje: Określanie, które panelu w formancie StatusBar formularzy Windows został kliknięty
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> i <xref:System.Windows.Forms.ToolStripStatusLabel> kontrolki Zastąp i dodawania funkcjonalności do <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> kontroluje; jednak <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> kontrolek zostaną zachowane dla zgodności z poprzednimi wersjami i użycia w przyszłości, jeśli możesz Wybierz.  
  
 Do programu [StatusBar, kontrolka](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) kontroli odpowiadanie na kliknięcia użytkownika, należy użyć w instrukcji case <xref:System.Windows.Forms.StatusBar.PanelClick> zdarzeń. Zdarzenie zawiera argument (argument panelu), który zawiera odwołanie do kliknięto <xref:System.Windows.Forms.StatusBarPanel>. Za pomocą tego odwołania, można określić indeksu kliknięto panelu i w związku z tym program.  
  
> [!NOTE]
>  Upewnij się, że <xref:System.Windows.Forms.StatusBar> kontrolki <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> właściwość jest ustawiona na `true`.  
  
### <a name="to-determine-which-panel-was-clicked"></a>Aby ustalić, który panel został kliknięty  
  
1.  W <xref:System.Windows.Forms.StatusBar.PanelClick> programu obsługi zdarzeń, użyj `Select Case` (w języku Visual Basic) lub `switch case` (Visual C# lub [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) instrukcię, aby określić, który panel został kliknięty, sprawdzając indeks kliknięto panelu w argumenty zdarzeń.  
  
     Poniższy przykład kodu wymaga obecności w formularzu, od <xref:System.Windows.Forms.StatusBar> kontroli `StatusBar1`oraz dwóch <xref:System.Windows.Forms.StatusBarPanel> obiektów, `StatusBarPanel1` i `StatusBarPanel2`.  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,   
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     (Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) umieść następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.  
  
    ```csharp  
    this.statusBar1.PanelClick += new   
       System.Windows.Forms.StatusBarPanelClickEventHandler   
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [Instrukcje: Ustawianie rozmiaru paneli paska stanu](../../../../docs/framework/winforms/controls/how-to-set-the-size-of-status-bar-panels.md)
- [Przewodnik: Aktualizowanie informacji na pasku stanu w czasie wykonywania](../../../../docs/framework/winforms/controls/walkthrough-updating-status-bar-information-at-run-time.md)
- [StatusBar, kontrolka — omówienie](../../../../docs/framework/winforms/controls/statusbar-control-overview-windows-forms.md)
