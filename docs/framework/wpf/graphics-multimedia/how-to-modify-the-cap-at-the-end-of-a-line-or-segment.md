---
title: 'Instrukcje: Modyfikuj zakończenie na końcu linii lub segmentu'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 9476fad503cf761672ae8460fcffb860ff683310
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645018"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Instrukcje: Modyfikuj zakończenie na końcu linii lub segmentu
W tym przykładzie przedstawiono sposób modyfikowania kształt na początku lub końcu otwartą <xref:System.Windows.Shapes.Shape> elementu. Aby zmienić limit na początku otwartą <xref:System.Windows.Shapes.Shape>, użyj jej <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> właściwości. Aby zmienić limit na końcu otwartą <xref:System.Windows.Shapes.Shape>, użyj jej <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> właściwości. Aby wyświetlić caps dostępnego wiersza, zobacz <xref:System.Windows.Media.PenLineCap> wyliczenia.  
  
> [!NOTE]
>  Ta właściwość ma wpływ tylko na otwarty kształt, takich jak <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, lub Otwórz <xref:System.Windows.Shapes.Path> elementu.  
  
 Poniższy przykład pobiera cztery <xref:System.Windows.Shapes.Polyline> elementów oraz korzysta z innego zestawu, kształtów na końcach każdego z nich.  
  
## <a name="example"></a>Przykład  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 W tym przykładzie jest częścią większego przykładu; Aby uzyskać pełny przykład, zobacz [przykładowe elementy kształtu](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
