---
title: 'Instrukcje: Animuj obiekt na ścieżce (animacja double)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: a57b21e3f05f90e756c46c167bb419b5bc9068f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54600417"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>Instrukcje: Animuj obiekt na ścieżce (animacja double)
W tym przykładzie pokazano, jak używać <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> klasy, aby przenieść obiekt na ścieżce definicją <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto dwóch <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> przenieść prostokąt wzdłuż ścieżki geometrycznej obiekty:  
  
-   Pierwszy <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animuje <xref:System.Windows.Media.TranslateTransform.X%2A> z <xref:System.Windows.Media.TranslateTransform> stosowane do prostokąta. To sprawia, że prostokąt przenoszony w poziomie wzdłuż ścieżki.  
  
-   Drugi <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animuje <xref:System.Windows.Media.TranslateTransform.Y%2A> z <xref:System.Windows.Media.TranslateTransform> stosowane do prostokąta. To sprawia, że prostokąt przesunąć pionowo wzdłuż ścieżki.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 Aby uzyskać pełny przykład, zobacz [przykład animacji ścieżki](https://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Innym sposobem, aby przenieść obiekt przy użyciu ścieżki geometrycznej jest użycie <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> obiektu. Aby uzyskać przykład, zobacz [animowanie obiektu na ścieżce (animacja Matrix)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Zobacz także
- [Animacja — przegląd](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Animacja ścieżki — tematy z instrukcjami](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
