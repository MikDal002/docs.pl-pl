---
title: "Jak animować właściwości materiału w scenie 3-D"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Material properties [WPF], animating in 3-D scenes
- animation [WPF], Material properties in 3-D scenes
- 3-D scenes [WPF], animating Material properties
ms.assetid: 229fd6eb-7401-4992-b0c9-8b28de230c0f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 273c03fcedbd5e5b2f6a38cb718788d5f8d8fda3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-material-properties-in-a-3-d-scene"></a><span data-ttu-id="17440-102">Jak animować właściwości materiału w scenie 3-D</span><span class="sxs-lookup"><span data-stu-id="17440-102">How to: Animate Material Properties in a 3-D Scene</span></span>
<span data-ttu-id="17440-103">W tym przykładzie pokazano, jak animować <xref:System.Windows.Media.Brush.Opacity%2A> właściwość <xref:System.Windows.Media.Media3D.Material> dotyczą [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] modelu.</span><span class="sxs-lookup"><span data-stu-id="17440-103">This example shows how to animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="17440-104">Poniższy przykładowy kod definiuje <xref:System.Windows.Media.LinearGradientBrush> używany jako <xref:System.Windows.Media.Media3D.Material> obiektu 3D.</span><span class="sxs-lookup"><span data-stu-id="17440-104">The following code example defines the <xref:System.Windows.Media.LinearGradientBrush> used as the <xref:System.Windows.Media.Media3D.Material> applied to the 3D object.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline1)]  
  
 <span data-ttu-id="17440-105"><xref:System.Windows.Media.Brush.Opacity%2A> Właściwości tego <xref:System.Windows.Media.LinearGradientBrush> jest animowany przykładu kodu poniżej.</span><span class="sxs-lookup"><span data-stu-id="17440-105">The <xref:System.Windows.Media.Brush.Opacity%2A> property of this <xref:System.Windows.Media.LinearGradientBrush> is animated using the code example below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexampleinline2)]  
  
## <a name="example"></a><span data-ttu-id="17440-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="17440-106">Example</span></span>  
 <span data-ttu-id="17440-107">Poniższy kod przedstawia całej próbki.</span><span class="sxs-lookup"><span data-stu-id="17440-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#AnimateMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/AnimateMaterialExample.xaml#animatematerialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="17440-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="17440-108">See Also</span></span>  
 [<span data-ttu-id="17440-109">Utwórz 3-sceny</span><span class="sxs-lookup"><span data-stu-id="17440-109">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="17440-110">Przegląd grafiki 3-w</span><span class="sxs-lookup"><span data-stu-id="17440-110">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)