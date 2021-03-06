---
title: 'Instrukcje: Animuj właściwość przy użyciu AnimationClock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], properties [WPF], with AnimationClocks
- AnimationClocks [WPF]
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
ms.openlocfilehash: 7940d65c61d57ec9c6a2a6e02e3b1e3e0bb2795f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610477"
---
# <a name="how-to-animate-a-property-by-using-an-animationclock"></a>Instrukcje: Animuj właściwość przy użyciu AnimationClock
W tym przykładzie pokazano, jak używać <xref:System.Windows.Media.Animation.Clock> obiektów, aby animować właściwości.  
  
 Istnieją trzy sposoby, aby animować właściwości zależności:  
  
-   Tworzenie <xref:System.Windows.Media.Animation.AnimationTimeline> i skojarz go z tej właściwości przy użyciu <xref:System.Windows.Media.Animation.Storyboard>.  
  
-   Użyj obiektu <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metody do stosowania pojedynczej <xref:System.Windows.Media.Animation.AnimationTimeline> do właściwości docelowej.  
  
-   Tworzenie <xref:System.Windows.Media.Animation.AnimationClock> z <xref:System.Windows.Media.Animation.AnimationTimeline> i zastosować je do właściwości.  
  
 <xref:System.Windows.Media.Animation.Storyboard> obiekty i <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> metody umożliwiają animować właściwości bez bezpośrednio tworzenie i rozpowszechnianie zegary (przykłady można znaleźć [animować właściwość przy użyciu scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) i [animować właściwości bez Za pomocą scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)); zegary są tworzone i dystrybucji dla Ciebie automatycznie.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak utworzyć <xref:System.Windows.Media.Animation.AnimationClock> i zastosować je do dwóch podobnych właściwości.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 Aby uzyskać przykład pokazujący sposób interaktywnie kontrolować <xref:System.Windows.Media.Animation.Clock> po jego uruchomieniu, zobacz [interaktywnie kontrolować zegar](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md).  
  
## <a name="see-also"></a>Zobacz także
- [Animowanie właściwości przy użyciu scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [Animowanie właściwości bez użycia scenorysu](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)
- [Techniki animacji właściwości — przegląd](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
