---
title: 'Instrukcje: Aranżowanie formularzy podrzędnych MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: 6e1e4f22aa70d8ee4d4122f9e77427c101b6713f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540744"
---
# <a name="how-to-arrange-mdi-child-forms"></a>Instrukcje: Aranżowanie formularzy podrzędnych MDI
Aplikacje mają często poleceń menu Akcje, takie jak kafelków, Cascade i rozmieszczanie, które sterowania układem Otwórz formularzy podrzędnych MDI. Możesz użyć <xref:System.Windows.Forms.Form.LayoutMdi%2A> metody przy użyciu jednego z <xref:System.Windows.Forms.MdiLayout> wartości wyliczenia, aby zmienić kolejność formularze podrzędne MDI nadrzędnego formularza.  
  
 <xref:System.Windows.Forms.MdiLayout> Wartości wyliczenia wyświetlanie formularzy podrzędnych jako kaskadowych jako sąsiadująco w poziomie lub pionie, lub ikony formularza podrzędnego rozmieszczone wzdłuż dolnej części formularza MDI. Te wartości mogą być taki sam skutek jak poleceń programu Windows **kaskadowo windows**, **Pokaż okna sąsiadująco**, **Pokaż okna skumulowany**, i **wyświetlanie pulpitu** , odpowiednio.  
  
 Metody te są często używane jako procedury obsługi zdarzeń, wywoływany przez element menu <xref:System.Windows.Forms.Control.Click> zdarzeń. W ten sposób element menu z tekstem "Windows Cascade" może mieć odpowiednią wpływu na oknami podrzędnymi MDI.  
  
### <a name="to-arrange-child-forms"></a>Aby aranżowanie formularzy podrzędnych  
  
1.  W metodzie, użyj <xref:System.Windows.Forms.Form.LayoutMdi%2A> metodę, aby ustawić <xref:System.Windows.Forms.MdiLayout> wyliczenia do formularza nadrzędnego MDI. W poniższym przykładzie użyto <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> wartość wyliczenia okien podrzędnych formularza nadrzędnego MDI (`Form1`). Wyliczenia jest używana w kodzie podczas obsługi zdarzeń dla <xref:System.Windows.Forms.Control.Click> zdarzenia **Windows Cascade** elementu menu.  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    >  Można również podzielić windows i windows rozmieszczenie jako ikony, zmieniając <xref:System.Windows.Forms.MdiLayout> wartość wyliczenia używane.  
  
2.  Jeśli używasz Visual C#, umieść następujący kod w Konstruktorze formularza, aby zarejestrować program obsługi zdarzeń.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a>Zobacz także
- [Aplikacje interfejsu wielu dokumentów (MDI)](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)
- [Instrukcje: Tworzenie formularzy nadrzędnych MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)
- [Instrukcje: Tworzenie formularzy podrzędnych MDI](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)
- [Instrukcje: Określanie elementu podrzędnego Active MDI](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)
- [Instrukcje: Wysyłanie danych do Active MDI Child](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)
