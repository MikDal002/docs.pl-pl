---
title: 'Instrukcje: Utwórz ekspander za pomocą ScrollViewer'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 8d21c7ec0172dca23f218a0d710c3976872f162c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681966"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Instrukcje: Utwórz ekspander za pomocą ScrollViewer
W tym przykładzie przedstawiono sposób tworzenia <xref:System.Windows.Controls.Expander> formant, który zawiera złożone zawartości, takiej jak tekstowych i obrazów. Przykład również umieszcza treść <xref:System.Windows.Controls.Expander> w <xref:System.Windows.Controls.ScrollViewer> kontroli.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak utworzyć <xref:System.Windows.Controls.Expander>. W przykładzie użyto <xref:System.Windows.Controls.Primitives.BulletDecorator> formant, który zawiera obraz i tekst, aby zdefiniować <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>. A <xref:System.Windows.Controls.ScrollViewer> kontroli udostępnia metodę przewijanie zawartości rozwinięty.  
  
 Należy zauważyć, że w przykładzie <xref:System.Windows.FrameworkElement.Height%2A> właściwość <xref:System.Windows.Controls.ScrollViewer> zamiast zawartości. Jeśli <xref:System.Windows.FrameworkElement.Height%2A> jest ustawiony na zawartości, <xref:System.Windows.Controls.ScrollViewer> nie zezwala użytkownikowi na przewijanie zawartości. <xref:System.Windows.FrameworkElement.Width%2A> Właściwość jest ustawiona na <xref:System.Windows.Controls.Expander> kontroli i to ustawienie dotyczy <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> oraz zawartość, rozwinięty.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Controls.Expander>
- [Ekspander — omówienie](../../../../docs/framework/wpf/controls/expander-overview.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
