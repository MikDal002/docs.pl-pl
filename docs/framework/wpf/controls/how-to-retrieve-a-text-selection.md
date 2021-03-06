---
title: 'Instrukcje: Pobierz wybór tekstu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: 3e2a4d9938f73cb306e8fd8b0e6b25b5abfa3b4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517776"
---
# <a name="how-to-retrieve-a-text-selection"></a>Instrukcje: Pobierz wybór tekstu
Ten przykład przedstawia sposób użycia <xref:System.Windows.Controls.TextBox.SelectedText%2A> właściwość służąca do pobierania tekstu zaznaczonego na <xref:System.Windows.Controls.TextBox> kontroli.  
  
## <a name="example"></a>Przykład  
 Następujące [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] przykład przedstawia definicję <xref:System.Windows.Controls.TextBox> formant, który zawiera tekst, który zostanie wybrana, i <xref:System.Windows.Controls.Button> kontrolki z określonym <xref:System.Windows.Controls.Button.OnClick%2A> metody.  
  
 W tym przykładzie przycisku ze skojarzoną <xref:System.Windows.Controls.Primitives.ButtonBase.Click> program obsługi zdarzeń służy do pobierania zaznaczonego tekstu. Gdy użytkownik kliknie przycisk, <xref:System.Windows.Controls.Button.OnClick%2A> metoda Kopiuje zaznaczony tekst w polu tekstowym w ciąg. Szczególne okoliczności, przez które zaznaczonego tekstu są pobierane (kliknięcie przycisku), również akcji wykonywanej za pomocą tego zaznaczenia (skopiowanie zaznaczonego tekstu do ciągu), można łatwo zmodyfikowane w celu uwzględnienia wielu różnych scenariuszach.  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a>Przykład  
 Następujące C# pokazano w przykładzie <xref:System.Windows.Controls.Button.OnClick%2A> programu obsługi zdarzeń dla przycisku, zdefiniowane w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] w tym przykładzie.  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a>Zobacz także
- [TextBox — omówienie](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox — omówienie](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
