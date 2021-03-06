---
title: 'Instrukcje: Utwórz niestandardowe zdarzenie trasowane'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: f6d043dc2975770fe9111c6266096eefb3fe15b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671697"
---
# <a name="how-to-create-a-custom-routed-event"></a>Instrukcje: Utwórz niestandardowe zdarzenie trasowane
Do zdarzenia niestandardowe do obsługi routingu zdarzeń, należy zarejestrować <xref:System.Windows.RoutedEvent> przy użyciu <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> metody. W tym przykładzie pokazano tworzenie niestandardowe zdarzenie trasowane.  
  
## <a name="example"></a>Przykład  
 Jak pokazano w poniższym przykładzie, należy najpierw zarejestrować <xref:System.Windows.RoutedEvent> przy użyciu <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> metody. Zgodnie z Konwencją <xref:System.Windows.RoutedEvent> nazwę pola statyczne powinny kończyć się sufiksem ***zdarzeń***. W tym przykładzie nazwa zdarzenia jest `Tap` i strategii routingu zdarzenia <xref:System.Windows.RoutingStrategy.Bubble>. Po wywołaniu rejestracji umożliwia dodawanie i usuwanie [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] metod dostępu zdarzeń dla zdarzenia.  
  
 Należy pamiętać, że nawet jeśli zdarzenie jest wywoływane za pośrednictwem `OnTap` metodę wirtualną, w tym przykładzie, jak zgłaszać zdarzenia lub sposób reagowania zdarzenia zmiany zależy od Twoich potrzeb.  
  
 Należy zauważyć, że w tym przykładzie po prostu implementuje całą podklasą <xref:System.Windows.Controls.Button>; tej podklasy jest kompilowany jako osobny zestaw, a następnie uruchomiony jako niestandardowej klasy na oddzielnym [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] strony. Ma to na celu zilustrowania koncepcji, że formanty będące podklasami mogą być wstawiane do drzewa zawierający inne formanty, i że w takiej sytuacji zdarzenia niestandardowe tych kontrolek mają bardzo te same możliwości routingu zdarzeń wszelkie native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] jest element.  
  
 [!code-csharp[RoutedEventCustom#CustomClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 Tunelowania powstają zdarzenia taki sam sposób, ale z <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> równa <xref:System.Windows.RoutingStrategy.Tunnel> w wywołaniu rejestracji. Zgodnie z Konwencją, tunelowanie zdarzeń w [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] są poprzedzone wyrazem "Podgląd".  
  
 Aby zobaczyć przykład sposobu propagacji pracy zdarzeń, zobacz [obsłużyć zdarzenie kierowane](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md).  
  
## <a name="see-also"></a>Zobacz także
- [Przegląd zdarzeń trasowanych](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Przegląd danych wejściowych](../../../../docs/framework/wpf/advanced/input-overview.md)
- [Tworzenie kontrolek — omówienie](../../../../docs/framework/wpf/controls/control-authoring-overview.md)
