---
title: "Jak zastosować animacje do tekstu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0298462db5897e955bf0a2551cca7fc81bb27d89
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-apply-animations-to-text"></a><span data-ttu-id="a4e7c-102">Jak zastosować animacje do tekstu</span><span class="sxs-lookup"><span data-stu-id="a4e7c-102">How to: Apply Animations to Text</span></span>
<span data-ttu-id="a4e7c-103">Animacji można zmienić wyświetlanie i wyglądu tekstu w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-103">Animations can alter the display and appearance of text in your application.</span></span> <span data-ttu-id="a4e7c-104">W poniższych przykładach użyto różnych typów animacji wpływ na wyświetlanie tekstu w <xref:System.Windows.Controls.TextBlock> formantu.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-104">The following examples use different types of animations to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4e7c-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="a4e7c-105">Example</span></span>  
 <span data-ttu-id="a4e7c-106">W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.DoubleAnimation> do animowania szerokość bloku tekstu.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-106">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the width of the text block.</span></span> <span data-ttu-id="a4e7c-107">Wartość szerokości zmienia szerokość bloku tekstu na 0 przez dany okres 10 sekund, a następnie odwraca wartości szerokości i będzie kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-107">The width value changes from the width of the text block to 0 over a duration of 10 seconds, and then reverses the width values and continues.</span></span> <span data-ttu-id="a4e7c-108">Ten typ animacji tworzy efekt czyszczenia.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-108">This type of animation creates a wipe effect.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 <span data-ttu-id="a4e7c-109">W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.DoubleAnimation> do Animuj przezroczystość bloku tekstu.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-109">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the opacity of the text block.</span></span> <span data-ttu-id="a4e7c-110">Wartość nieprzezroczystości zmieni się z 1.0 0 przez dany okres 5 sekund, a następnie odwraca wartości nieprzezroczystość i będzie kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-110">The opacity value changes from 1.0 to 0 over a duration of 5 seconds, and then reverses the opacity values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 <span data-ttu-id="a4e7c-111">Na poniższym diagramie przedstawiono efekt <xref:System.Windows.Controls.TextBlock> kontroli zmiana jego nieprzezroczystość z `1.00` do `0.00` interwale 5 sekund zdefiniowane przez <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-111">The following diagram shows the effect of the <xref:System.Windows.Controls.TextBlock> control changing its opacity from `1.00` to `0.00` during the 5-second interval defined by the <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.</span></span>  
  
 <span data-ttu-id="a4e7c-112">![Tekst zmieniający nieprzezroczystość z 1,00 0,00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span><span class="sxs-lookup"><span data-stu-id="a4e7c-112">![Text changing opacity from 1.00 to 0.00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")</span></span>  
<span data-ttu-id="a4e7c-113">Nieprzezroczystość tekstu zmiana z 1,00 na 0,00</span><span class="sxs-lookup"><span data-stu-id="a4e7c-113">Text Opacity changing from 1.00 to 0.00</span></span>  
  
 <span data-ttu-id="a4e7c-114">W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.ColorAnimation> do animowania kolor pierwszego planu bloku tekstu.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-114">The following example uses a <xref:System.Windows.Media.Animation.ColorAnimation> to animate the foreground color of the text block.</span></span> <span data-ttu-id="a4e7c-115">Wartość koloru pierwszego planu zmienia kolor na drugi kolor przez dany okres 5 sekund, a następnie odwraca wartości kolorów i będzie kontynuowane.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-115">The foreground color value changes from one color to a second color over a duration of 5 seconds, and then reverses the color values and continues.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 <span data-ttu-id="a4e7c-116">W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.DoubleAnimation> Obracanie bloku tekstu.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-116">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to rotate the text block.</span></span> <span data-ttu-id="a4e7c-117">Bloku tekstu wykonuje pełne obrotu w czasie trwania 20 sekund, a następnie kontynuuje Powtórz obrót.</span><span class="sxs-lookup"><span data-stu-id="a4e7c-117">The text block performs a full rotation over a duration of 20 seconds, and then continues to repeat the rotation.</span></span>  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a><span data-ttu-id="a4e7c-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a4e7c-118">See Also</span></span>  
 [<span data-ttu-id="a4e7c-119">Animacja — omówienie</span><span class="sxs-lookup"><span data-stu-id="a4e7c-119">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)