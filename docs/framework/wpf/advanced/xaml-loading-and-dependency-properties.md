---
title: Właściwości zależności i ładowania XAML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: 3cce6e09cd2dbb02a07487ade781b03406fcad96
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580281"
---
# <a name="xaml-loading-and-dependency-properties"></a>Właściwości zależności i ładowania XAML
Bieżący [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementację jej [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora jest świadomość właściwość zależności. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Procesor używa metody system właściwości dla właściwości zależności podczas ładowania pliku binarnego [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] i podczas przetwarzania atrybutów, które są właściwościami zależności. Pomija to skutecznie otoki właściwości. Podczas implementowania niestandardowe właściwości zależności muszą uwzględniać to zachowanie i unikać umieszczania każdy inny kod w swojej otoki właściwość niż metody system właściwości <xref:System.Windows.DependencyObject.GetValue%2A> i <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Wymagania wstępne  
 W tym temacie założono, że zrozumieć właściwości zależności zarówno jako odbiorców i autor i po ich przeczytaniu [Przegląd właściwości zależności](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) i [niestandardowe właściwości zależności](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md). Należy również przeczytanie [Przegląd XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) i [składnia XAML w szczegółów](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>Implementacja modułu ładującego WPF XAML i wydajności  
 Ze względu na implementację jest mniej obciążającymi do identyfikowania właściwość jako właściwość zależności i uzyskać dostęp do właściwości systemu <xref:System.Windows.DependencyObject.SetValue%2A> metodę, aby ustawić go, a nie przy użyciu otoki właściwości i jej metoda ustawiająca. Jest to spowodowane [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesor musi wywnioskować cały obiekt modelu kodu zapasowy oparte tylko na, wiedząc, typów i elementów członkowskich relacje, które są wskazywane przez strukturę znaczników oraz różne parametry.  
  
 Typ jest wyszukiwana przy użyciu kombinacji xmlns i atrybutów zestawu, ale Identyfikowanie członków, określania, który mógłby wspierać zostanie ustawiony jako atrybutu, i rozpoznawanie, jakie typy wartości właściwości pomocy technicznej będzie w przeciwnym razie wymagają rozbudowane odbicia za pomocą <xref:System.Reflection.PropertyInfo>. Ponieważ właściwości zależności dla danego typu są dostępne jako tabeli magazynu za pośrednictwem systemu właściwość [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementację jej [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora korzysta z tej tabeli i ustala, że wszelkie podane właściwości *ABC* można ustawić bardziej wydajnie, wywołując <xref:System.Windows.DependencyObject.SetValue%2A> na zawierający <xref:System.Windows.DependencyObject> pochodne typu przy użyciu identyfikatora właściwości zależności *ABCProperty*.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>Wpływ na niestandardowe właściwości zależności  
 Ponieważ bieżący [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementacji [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zachowanie procesora ustawienie właściwości całkowicie pomija otoki, nie wolno umieszczać dodatkowej logiki w definicji zestawu otoki dla swojej właściwości zależności niestandardowej. Umieść takich logikę w definicji zestawu, a następnie logika nie zostaną wykonane, gdy właściwość jest ustawiona [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , a nie w kodzie.  
  
 Podobnie, inne aspekty [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesora, który uzyskać wartości właściwości z [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] przetwarzania również użycie <xref:System.Windows.DependencyObject.GetValue%2A> zamiast przy użyciu otoki. W związku z tym, powinien również unikać wszelkich dodatkowych implementacji w `get` definicji poza <xref:System.Windows.DependencyObject.GetValue%2A> wywołania.  
  
 Poniższy przykład przedstawia definicję właściwości zależności zalecane przy użyciu otoki, gdzie identyfikator właściwości jest przechowywana jako `public` `static` `readonly` pola i `get` i `set` definicje zawierać żadnego kodu poza metody systemu wymagana właściwość, które definiują właściwości zależności kopii.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>Zobacz także
- [Przegląd właściwości zależności](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [Przegląd XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [Metadane zależności właściwości](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)
- [Właściwości zależności typu kolekcji](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)
- [Zabezpieczenia właściwości zależności](../../../../docs/framework/wpf/advanced/dependency-property-security.md)
- [Bezpieczne wzorce konstruktora dla obiektów DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)
