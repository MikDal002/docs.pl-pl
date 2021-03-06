---
title: 'Instrukcje: Implementuj właściwość zależności'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 90eb15d3cc0d9a6c1d07879b0166da4d45d786be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727329"
---
# <a name="how-to-implement-a-dependency-property"></a>Instrukcje: Implementuj właściwość zależności
W tym przykładzie pokazano, jak utworzyć kopię [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] właściwość o <xref:System.Windows.DependencyProperty> pola, w związku z tym Definiowanie właściwości zależności. Podczas definiowania własnych właściwości i chcesz, aby obsługiwać wiele aspektów [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] funkcje, w tym stylów, powiązań danych, dziedziczenie, animacji i wartości domyślne należy go wdrożyć jako właściwość zależności.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład najpierw rejestruje właściwości zależności, wywołując <xref:System.Windows.DependencyProperty.Register%2A> metody. Nazwa pola identyfikatora, które umożliwiają przechowywanie nazwy i właściwości właściwość zależności musi być <xref:System.Windows.DependencyProperty.Name%2A> został wybrany dla właściwości zależności w ramach <xref:System.Windows.DependencyProperty.Register%2A> wywołanie, uzupełnione przez ciąg literału `Property`. Na przykład jeśli Zarejestruj właściwości zależności za pomocą <xref:System.Windows.DependencyProperty.Name%2A> z `Location`, muszą być nazwane pole identyfikatora, który zdefiniujesz dla właściwości zależności, a następnie `LocationProperty`.  
  
 W tym przykładzie nazwa właściwości zależności i jego [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] akcesor jest `State`; to pole identyfikatora `StateProperty`; typ właściwości to <xref:System.Boolean>; i typ, który rejestruje właściwość zależności jest `MyStateControl`.  
  
 Jeśli nie korzystać z tego wzoru nazewnictwa, projektantów może nie raportować Twoja własność prawidłowo i niektóre aspekty stosowanie stylu systemu właściwości mogą nie zachowywać się zgodnie z oczekiwaniami.  
  
 Można również określić domyślne metadane dla właściwości zależności. W tym przykładzie rejestruje wartość domyślną `State` właściwości zależności `false`.  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 Aby uzyskać więcej informacji o tym, jak i dlaczego implementować właściwość zależności, a nie tylko tworzenie kopii [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] Zobacz właściwość z polem prywatnej [Przegląd właściwości zależności](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
## <a name="see-also"></a>Zobacz także
- [Przegląd właściwości zależności](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
