---
title: "Jak animować kolor z wykorzystaniem klatek kluczowych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d117d57e5cc761aa2f31fd6531bff8d96ea30dc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="8fab2-102">Jak animować kolor z wykorzystaniem klatek kluczowych</span><span class="sxs-lookup"><span data-stu-id="8fab2-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="8fab2-103">W tym przykładzie pokazano, jak animować <xref:System.Windows.Media.SolidColorBrush.Color%2A> z <xref:System.Windows.Media.SolidColorBrush> przy użyciu klucza ramki.</span><span class="sxs-lookup"><span data-stu-id="8fab2-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fab2-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="8fab2-104">Example</span></span>  
 <span data-ttu-id="8fab2-105">W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> klasy do animowania <xref:System.Windows.Media.SolidColorBrush.Color%2A> właściwość <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="8fab2-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="8fab2-106">Ta animacja używa trzech klatek kluczowych w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="8fab2-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="8fab2-107">Podczas pierwszego dwusekundowe używa wystąpienia <xref:System.Windows.Media.Animation.LinearColorKeyFrame> klasy stopniowo zmiana koloru z zielonego na czerwony.</span><span class="sxs-lookup"><span data-stu-id="8fab2-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="8fab2-108">Liniowy klatek kluczowych, takich jak <xref:System.Windows.Media.Animation.LinearColorKeyFrame> utworzyć liniowej przejścia między wartościami.</span><span class="sxs-lookup"><span data-stu-id="8fab2-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="8fab2-109">W końcu następnej pół sekundy używa wystąpienia <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> klasę, aby szybko zmienić kolor czerwony żółty.</span><span class="sxs-lookup"><span data-stu-id="8fab2-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="8fab2-110">Odrębny klatek kluczowych, takich jak <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> utworzyć nagłym zmiany między wartościami, oznacza to, zmiana koloru w tej części animacji występuje szybko i nie jest niewielkie.</span><span class="sxs-lookup"><span data-stu-id="8fab2-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="8fab2-111">Podczas końcowego dwusekundowe używa wystąpienia <xref:System.Windows.Media.Animation.SplineColorKeyFrame> klasy ponownie zmienić kolor — teraz z powrotem żółty zielony.</span><span class="sxs-lookup"><span data-stu-id="8fab2-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="8fab2-112">Ramek kluczowych krzywej składanej, takich jak <xref:System.Windows.Media.Animation.SplineColorKeyFrame> utworzyć zmiennej przejścia między wartościami zgodnie z wartościami <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="8fab2-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="8fab2-113">W tym przykładzie zmianę koloru rozpoczyna się powoli i przyspiesza wykładniczo do końca segmentu czasu.</span><span class="sxs-lookup"><span data-stu-id="8fab2-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="8fab2-114">Pełny przykład, zobacz [klatek kluczowych animacji próbki](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="8fab2-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fab2-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8fab2-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="8fab2-116">Omówienie klucza poklatkowych</span><span class="sxs-lookup"><span data-stu-id="8fab2-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="8fab2-117">Klucz ramki — tematy porad</span><span class="sxs-lookup"><span data-stu-id="8fab2-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)