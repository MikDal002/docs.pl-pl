---
title: 'Instrukcje: Definiuj prostokąt przy użyciu RectangleGeometry'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 9c57f1536065af0bca1f3752179547daa502c066
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511649"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>Instrukcje: Definiuj prostokąt przy użyciu RectangleGeometry
W tym przykładzie przedstawiono sposób użycia <xref:System.Windows.Media.RectangleGeometry> klasę do opisania prostokąta.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak utworzyć i renderowania <xref:System.Windows.Media.RectangleGeometry>.  Względne położenie i wymiary prostokąta są definiowane przez <xref:System.Windows.Rect> struktury. Względne położenie jest `50,50` i wysokość i szerokość są `25` tworzenia kwadrat. Wewnętrzne prostokąta jest malowany <xref:System.Windows.Media.Brushes.LemonChiffon%2A> pędzla i jego konspekt jest malowany <xref:System.Windows.Media.Brushes.Black%2A> grubość pociągnięć `1`.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 Mimo że w tym przykładzie użyto <xref:System.Windows.Shapes.Path> element do renderowania <xref:System.Windows.Media.RectangleGeometry>, istnieje wiele sposobów używania <xref:System.Windows.Media.RectangleGeometry> obiektów. Na przykład <xref:System.Windows.Media.RectangleGeometry> może służyć do określania <xref:System.Windows.UIElement.Clip%2A> z <xref:System.Windows.UIElement> lub <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> z <xref:System.Windows.Media.GeometryDrawing>.  
  
 Inne klasy geometrii proste obejmują <xref:System.Windows.Media.LineGeometry> i <xref:System.Windows.Media.EllipseGeometry>. Te geometrii, a także bardziej złożonych te można również utworzyć przy użyciu <xref:System.Windows.Media.PathGeometry> lub <xref:System.Windows.Media.StreamGeometry>.  
  
## <a name="see-also"></a>Zobacz także
- [Geometria — przegląd](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [Tworzenie kształtu złożonego](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [Tworzenie kształtu przy użyciu elementu PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
