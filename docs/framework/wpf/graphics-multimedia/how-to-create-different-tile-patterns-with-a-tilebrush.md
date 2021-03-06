---
title: 'Instrukcje: Utwórz różne wzory sąsiadujących kafelek z użyciem TileBrush'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: d6b6d4a20d43478131d3adb7c7d091214b3c5871
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722009"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Instrukcje: Utwórz różne wzory sąsiadujących kafelek z użyciem TileBrush
W tym przykładzie pokazano, jak używać <xref:System.Windows.Media.TileBrush.TileMode%2A> właściwość <xref:System.Windows.Media.TileBrush> utworzyć wzorca.  
  
 <xref:System.Windows.Media.TileBrush.TileMode%2A> Właściwości można określić sposób, w jaki zawartości <xref:System.Windows.Media.TileBrush> jest powtarzany, to znaczy, sąsiadująco w celu wypełnienia obszaru danych wyjściowych. Aby utworzyć wzorzec, należy ustawić <xref:System.Windows.Media.TileBrush.TileMode%2A> do <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, lub <xref:System.Windows.Media.TileMode.FlipXY>. Należy także ustawić <xref:System.Windows.Media.TileBrush.Viewport%2A> z <xref:System.Windows.Media.TileBrush> tak, aby jego rozmiar jest mniejszy niż obszar malowanego; w przeciwnym razie pojedynczego kafelka jest utworzone, niezależnie od tego, co <xref:System.Windows.Media.TileBrush.TileMode%2A> ustawienie używasz.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy pięć <xref:System.Windows.Media.DrawingBrush> obiektów, daje im każdego innego <xref:System.Windows.Media.TileBrush.TileMode%2A> ustawienie i używa ich do malowania pięć prostokąty. Mimo że w tym przykładzie użyto <xref:System.Windows.Media.DrawingBrush> klasę wykazać <xref:System.Windows.Media.TileBrush.TileMode%2A> zachowanie, <xref:System.Windows.Media.TileBrush.TileMode%2A> właściwości działa tak samo dla wszystkich <xref:System.Windows.Media.TileBrush> obiekty, oznacza to, że dla <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, i <xref:System.Windows.Media.DrawingBrush>.  
  
 Poniższa ilustracja przedstawia ten przykład generuje dane wyjściowe.  
  
 ![TileBrush fragmentacji przykładowe dane wyjściowe](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
Utworzone za pomocą właściwości TileMode wzorce kafelkowe  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Zobacz także
- [Ustawianie rozmiaru kafelka dla elementu TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)
- [Malowanie przy użyciu obrazów, rysowania i wizualizacji](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
