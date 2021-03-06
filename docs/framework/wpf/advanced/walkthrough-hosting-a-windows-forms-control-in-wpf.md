---
title: 'Przewodnik: Hosting kontrolki Windows Forms w WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
ms.assetid: 9cb88415-39b0-4c46-80c4-ff325b674286
ms.openlocfilehash: 2bbc3d249504bf8bb80dd29de3110002f0fd87e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548823"
---
# <a name="walkthrough-hosting-a-windows-forms-control-in-wpf"></a>Przewodnik: Hosting kontrolki Windows Forms w WPF

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] udostępnia wiele kontrolek z rozbudowanym zestawie funkcji. Jednak czasami warto użyć [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] formantów na Twoje [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stron. Na przykład może mieć znaczne inwestycje w istniejących [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] formantów, lub może być [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] formant, który oferuje unikatową funkcję.

W tym instruktażu dowiesz się, jak hostować [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.MaskedTextBox?displayProperty=nameWithType> kontrolować na [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] strony przy użyciu kodu.

Aby uzyskać kompletny kod listę zadań przedstawione w niniejszym instruktażu, zobacz [Hosting kontrolki formularzy Windows w przykładzie WPF](https://go.microsoft.com/fwlink/?LinkID=160057).

## <a name="prerequisites"></a>Wymagania wstępne

Potrzebujesz programu Visual Studio w celu przeprowadzenia tego instruktażu.

## <a name="hosting-the-windows-forms-control"></a>Hostowanie kontrolki formularza Windows

### <a name="to-host-the-maskedtextbox-control"></a>Do hostowania maskedtextbox — formant

1.  Utwórz projekt aplikacji WPF, o nazwie `HostingWfInWpf`.

2.  Dodaj odwołania do następujących zestawów.

    -   WindowsFormsIntegration

    -   System.Windows.Forms

3.  Otwieranie pliku MainWindow.xaml w [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].

4.  Nazwa <xref:System.Windows.Controls.Grid> elementu `grid1`.

     [!code-xaml[HostingWfInWPF#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml#1)]

5.  W widoku projektu lub XAML, wybierz <xref:System.Windows.Window> elementu.

6.  W oknie dialogowym właściwości kliknij **zdarzenia** kartę.

7.  Kliknij dwukrotnie <xref:System.Windows.FrameworkElement.Loaded> zdarzeń.

8.  Wstaw następujący kod do obsługi <xref:System.Windows.FrameworkElement.Loaded> zdarzeń.

     [!code-csharp[HostingWfInWPF#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#10)]
     [!code-vb[HostingWfInWPF#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#10)]

9. W górnej części pliku Dodaj następujący kod `Imports` lub `using` instrukcji.

     [!code-csharp[HostingWfInWPF#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfInWPF/CSharp/HostingWfInWPF/Window1.xaml.cs#11)]
     [!code-vb[HostingWfInWPF#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfInWPF/VisualBasic/HostingWfInWpf/Window1.xaml.vb#11)]

10. Naciśnij klawisz **F5** Aby skompilować i uruchomić aplikację.

## <a name="see-also"></a>Zobacz także

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Projektowanie XAML w programie Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Przewodnik: Hosting kontrolki Windows Forms w WPF przy użyciu XAML](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf-by-using-xaml.md)
- [Przewodnik: Hostowanie kontrolki złożonej Windows Forms w WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Przewodnik: Hosting złożonego formantu WPF w formularzach Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Kontrolki formularzy Windows Forms i równoważne kontrolki WPF](../../../../docs/framework/wpf/advanced/windows-forms-controls-and-equivalent-wpf-controls.md)
- [Hostowanie kontrolki formularzy Windows w przykładzie WPF](https://go.microsoft.com/fwlink/?LinkID=160057)