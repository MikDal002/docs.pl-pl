---
title: 'Instrukcje: Znajdź elementy wygenerowane DataTemplate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: d271a3d53a0e102f8f969fd0751e15b470a52862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511569"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Instrukcje: Znajdź elementy wygenerowane DataTemplate
W tym przykładzie pokazano, jak znajdowanie elementów generowanych przez <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Przykład  
 W tym przykładzie występuje <xref:System.Windows.Controls.ListBox> , jest powiązany z niektórymi [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] danych:  
  
 [!code-xaml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox> Korzysta z następujących <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Jeśli chcesz pobrać <xref:System.Windows.Controls.TextBlock> elementu generowanych przez <xref:System.Windows.DataTemplate> pewnego <xref:System.Windows.Controls.ListBoxItem>, zajdzie potrzeba przywrócenia <xref:System.Windows.Controls.ListBoxItem>, Znajdź <xref:System.Windows.Controls.ContentPresenter> w tym <xref:System.Windows.Controls.ListBoxItem>, a następnie wywołać <xref:System.Windows.FrameworkTemplate.FindName%2A> na <xref:System.Windows.DataTemplate> na które ustawiono <xref:System.Windows.Controls.ContentPresenter>. Poniższy przykład przedstawia sposób wykonywania tych kroków. Dla celów demonstracyjnych, w tym przykładzie tworzy okno komunikatu, który pokazuje tekst zawartości <xref:System.Windows.DataTemplate>-generowane blok tekstu.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Oto implementacja `FindVisualChild`, który używa <xref:System.Windows.Media.VisualTreeHelper> metody:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Zobacz także
- [Instrukcje: Find ControlTemplate-Generated Elements](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Powiązanie danych — omówienie](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
- [Tworzenie szablonów i stylów](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Zakresy nazw WPF XAML](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)
- [Drzewa w WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
