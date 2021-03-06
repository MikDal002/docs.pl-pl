---
title: 'Optymalizacja wydajności: Zasoby aplikacji'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: fa412a4f900179c22868b2ef3e7429e7dc2acc9c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507554"
---
# <a name="optimizing-performance-application-resources"></a>Optymalizacja wydajności: Zasoby aplikacji
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pozwala na udostępnianie zasobów aplikacji, aby może obsługiwać spójnego wyglądu i zachowania, które znajdują się w podobnych elementów. Ten temat zawiera kilka zaleceń, w tym obszarze, które mogą pomóc poprawić wydajność aplikacji.  
  
 Aby uzyskać więcej informacji na temat zasobów, zobacz [zasoby XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
## <a name="sharing-resources"></a>Udostępnianie zasobów  
 Jeśli aplikacja używa niestandardowych formantów i definiuje zasoby w <xref:System.Windows.ResourceDictionary> (lub węzeł zasoby XAML), zalecane jest, albo zdefiniowania zasoby na <xref:System.Windows.Application> lub <xref:System.Windows.Window> obiekt poziom lub zdefiniuj je w motyw domyślny dla Kontrolki niestandardowe. Definiowanie zasobów w niestandardowej kontrolce <xref:System.Windows.ResourceDictionary> nakłada wpływ na wydajność dla każdego wystąpienia tej kontrolki. Na przykład w przypadku operacji intensywnie pędzla, które zdefiniowano jako część definicji zasobu formantu niestandardowego i wiele wystąpień formantu niestandardowego zestaw roboczy aplikacji znacznie wzrośnie.  
  
 Aby zilustrować ten punkt, należy rozważyć następujące kwestie. Załóżmy, że tworzysz, karta gier przy użyciu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. W większości gier należy 52 kart z 52 różnych powierzchni. Użytkownik chce zaimplementować formant niestandardowy karty, a następnie zdefiniować pędzle 52 (każdy reprezentuje twarzy karty) w zasobach niestandardową kontrolkę karty. W głównym aplikacji wstępnie tworzyć 52 wystąpienia tej kontrolki niestandardowej karty. Każde wystąpienie kontrolki niestandardowej karty generuje 52 wystąpień <xref:System.Windows.Media.Brush> obiektów, które daje w sumie 52 * 52 <xref:System.Windows.Media.Brush> obiektów w aplikacji. Przenosząc pędzle wykorzystać zasoby kontrolki niestandardowej karty do <xref:System.Windows.Application> lub <xref:System.Windows.Window> poziomie obiektu lub Definiowanie motyw domyślny dla formantu niestandardowego, zmniejszyć zestaw roboczy aplikacji, ponieważ są teraz udostępnianie pędzli 52 między 52 wystąpień kontrolce karty.  
  
## <a name="sharing-a-brush-without-copying"></a>Udostępnianie pędzli bez kopiowania  
 Jeśli masz wiele elementów, korzystając z tych samych <xref:System.Windows.Media.Brush> obiektów, Zdefiniuj pędzel jako zasób i odwołania, a nie definiowanie w tekście pędzla w [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Ta metoda spowoduje to utworzenie jednego wystąpienia i ponownego wykorzystania, natomiast definiowanie w tekście pędzli w [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] tworzy nowe wystąpienie dla każdego elementu.  
  
 W poniższym przykładzie znaczników ilustruje tę sytuację:  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Użyj zasobów statycznych, gdy jest to możliwe  
 Zasób statyczny zawiera wartość dla każdego atrybutu właściwość XAML, sprawdzając odwołanie do zasobu już zdefiniowane. Zachowanie wyszukiwania dla tego zasobu jest analogiczne do wyszukiwania w czasie kompilacji.  
  
 Zasób dynamiczny, z drugiej strony, utworzysz wyrażenie tymczasowego podczas początkowej kompilacji i związku z tym Odrocz wyszukiwania dla zasobów, dopóki wartość faktycznie wymagane w celu utworzenia obiektu żądanego zasobu. Zachowanie wyszukiwania dla tego zasobu jest analogiczne do wyszukiwania środowiska wykonawczego, która nakłada negatywny wpływ na wydajność. Użyj zasobów statycznych w miarę możliwości w aplikacji, korzystając z dynamicznych zasobów tylko wtedy, gdy jest to konieczne.  
  
 W poniższym przykładzie znaczników pokazano sposób użycia obu typów zasobów:  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Zobacz także
- [Optymalizacja wydajności aplikacji WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [Planowanie wydajności aplikacji](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)
- [Wykorzystanie możliwości sprzętu](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)
- [Układ i projekt](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)
- [Grafika 2D i obrazowanie](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Zachowanie obiektu](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)
- [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)
- [Powiązanie danych](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)
- [Inne zalecenia dotyczące wydajności](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
