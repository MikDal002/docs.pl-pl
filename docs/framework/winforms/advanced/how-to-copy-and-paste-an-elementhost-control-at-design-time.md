---
title: 'Instrukcje: Kopiowanie i wklejanie formantu ElementHost w czasie projektowania'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 6ff1ccc5e8f188bdec2e09048974fdc20a785920
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572634"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a>Instrukcje: Kopiowanie i wklejanie formantu ElementHost w czasie projektowania
Ta procedura pokazuje, jak kopiowanie kontrolki Windows Presentation Foundation (WPF) w formularzu Windows.  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a>Kopiowanie i wklejanie formantu ElementHost w czasie projektowania  
  
1.  Dodaj nowe WPF <xref:System.Windows.Controls.UserControl> do projektu Windows Forms. Użyj domyślnej nazwy dla kontrolek typu `UserControl1.xaml`. Aby uzyskać więcej informacji, zobacz [instruktażu: Tworzenie nowej zawartości WPF na formularzach Windows Forms w czasie projektowania](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).  
  
2.  W **właściwości** okna, ustaw wartość <xref:System.Windows.FrameworkElement.Width%2A> i <xref:System.Windows.FrameworkElement.Height%2A> właściwości `UserControl1` do `200`.  
  
3.  Ustaw wartość <xref:System.Windows.Controls.Control.Background%2A> właściwość `Blue`.  
  
4.  Skompiluj projekt.  
  
5.  Otwórz `Form1` w programie Windows Forms Designer.  
  
6.  Z **przybornika**, przeciągnij wystąpienie `UserControl1` na formularz.  
  
     Wystąpienie `UserControl1` znajduje się w nowym <xref:System.Windows.Forms.Integration.ElementHost> formantu o nazwie `elementHost1`.  
  
7.  Za pomocą `elementHost1` zaznaczone, naciśnij klawisze CTRL + C, aby skopiować go do Schowka.  
  
8.  Naciśnij klawisze CTRL + V, aby wkleić skopiowanych formantu do formularza.  
  
     Nowy <xref:System.Windows.Forms.Integration.ElementHost> formantu o nazwie `elementHost2` jest tworzony w formularzu.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migracja i współdziałanie](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
- [Korzystanie z kontrolek WPF](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)
- [Projektowanie XAML w programie Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
