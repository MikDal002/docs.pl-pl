---
title: 'Instrukcje: Użyj SystemFonts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: bf99d716c5c41b7604244022d2e58423594a9cf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674875"
---
# <a name="how-to-use-systemfonts"></a>Instrukcje: Użyj SystemFonts
W tym przykładzie pokazano, jak korzystać z zasobów statycznych <xref:System.Windows.SystemFonts> klasy do nadawania stylu lub dostosować przycisku.  
  
## <a name="example"></a>Przykład  
 Zasobów systemowych uwidocznić kilka wartości określić systemu jako zarówno z zasobów i właściwości, aby można było pomocne podczas tworzenia wizualizacji, które są zgodne z ustawieniami systemu. <xref:System.Windows.SystemFonts> jest to klasa, która zawiera obie wartości czcionki systemu jako właściwości statycznych i właściwości, które odwołują się klucze zasobów, których można użyć, aby uzyskać dostęp do tych wartości dynamicznie w czasie wykonywania. Na przykład <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> jest <xref:System.Windows.SystemFonts> wartości, a <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> jest odpowiedni klucz zasobu.  
  
 W [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], można użyć elementów członkowskich <xref:System.Windows.SystemFonts> jako właściwości statyczne lub odwołania do zasobów dynamicznej (wartością właściwości statycznej jako klucz). Użyj odwołania zasób dynamiczny, jeśli chcesz, aby metryki czcionki do automatycznego aktualizowania podczas jej uruchomieniu; w przeciwnym razie użyj odwołania wartość statyczną.  
  
> [!NOTE]
>  Klucze zasobu ma sufiks "Key" dołączony do nazwy właściwości.  
  
 Poniższy przykład pokazuje, jak uzyskać dostęp do właściwości <xref:System.Windows.SystemFonts> jako statyczne wartości do nadawania stylu lub dostosować przycisku. W tym przykładzie znaczników przypisuje <xref:System.Windows.SystemFonts> wartości do przycisku.  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 Aby użyć wartości <xref:System.Windows.SystemFonts> w kodzie, nie trzeba użyć wartość statyczną lub odwołanie do zasobu dynamicznego. Zamiast tego należy użyć właściwości klucza <xref:System.Windows.SystemFonts> klasy. Mimo że niekluczowych właściwości najwyraźniej są definiowane jako właściwości statyczne zachowania w czasie wykonywania z [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] jako hostowanej przez system spowoduje to ponowne ocenienie właściwości w czasie rzeczywistym i prawidłowo będzie uwzględniać zmiany wartości systemu oparte na użytkownika. Poniższy przykład pokazuje, jak określić ustawienia czcionki przycisku.  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.SystemFonts>
- [Malowanie obszaru pędzlem systemowym](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Używanie elementu SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
- [Używanie kluczy czcionek systemowych](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
- [x:Static, rozszerzenie znaczników](../../../../docs/framework/xaml-services/x-static-markup-extension.md)
- [Zasoby XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)
- [DynamicResource, rozszerzenie znaczników](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
