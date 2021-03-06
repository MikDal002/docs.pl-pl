---
title: 'Instrukcje: Zmień kolor elementu przy użyciu elementów Fokus'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: ad5ba8490f4b98512d539f5ae9c72b03333aca69
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547017"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Instrukcje: Zmień kolor elementu przy użyciu elementów Fokus
W tym przykładzie pokazano, jak zmienić kolor elementu uzyskuje i traci fokus przy użyciu <xref:System.Windows.UIElement.GotFocus> i <xref:System.Windows.UIElement.LostFocus> zdarzenia.  
  
 W tym przykładzie składa się z [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] oraz plik CodeBehind.  
  
## <a name="example"></a>Przykład  
 Następujące [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] tworzy interfejs użytkownika, który składa się z dwóch <xref:System.Windows.Controls.Button> obiektów i dołącza obsługę zdarzeń dla <xref:System.Windows.UIElement.GotFocus> i <xref:System.Windows.UIElement.LostFocus> zdarzenia <xref:System.Windows.Controls.Button> obiektów.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 Poniższy kod tworzy <xref:System.Windows.UIElement.GotFocus> i <xref:System.Windows.UIElement.LostFocus> procedury obsługi zdarzeń.  Gdy <xref:System.Windows.Controls.Button> za pomocą klawiatury uzyskuje fokus, <xref:System.Windows.Controls.Control.Background%2A> z <xref:System.Windows.Controls.Button> jest zmieniana na czerwono.  Gdy <xref:System.Windows.Controls.Button> straci fokus klawiatury <xref:System.Windows.Controls.Control.Background%2A> z <xref:System.Windows.Controls.Button> zmieniony na biały.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Zobacz także
- [Przegląd danych wejściowych](../../../../docs/framework/wpf/advanced/input-overview.md)
