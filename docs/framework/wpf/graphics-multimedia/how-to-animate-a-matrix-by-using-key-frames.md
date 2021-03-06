---
title: 'Instrukcje: Animuj Matrix z wykorzystaniem klatek kluczowych'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: fff550a5a3a85575fe86c5290aa604ab00f1437f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518517"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>Instrukcje: Animuj Matrix z wykorzystaniem klatek kluczowych
W tym przykładzie pokazano, jak animować <xref:System.Windows.Media.MatrixTransform.Matrix%2A> właściwość <xref:System.Windows.Media.MatrixTransform> przy użyciu klatek kluczowych.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames> klasy, aby animować <xref:System.Windows.Media.MatrixTransform.Matrix%2A> właściwość <xref:System.Windows.Media.MatrixTransform>. W przykładzie użyto <xref:System.Windows.Media.MatrixTransform> obiekt, aby przekształcić wyglądu i położenia <xref:System.Windows.Controls.Button>.  
  
 Korzysta z tą animację <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> klasy do utworzenia dwóch ramek kluczowych i wykonuje następujące czynności, które z nich:  
  
1.  Animuje pierwszy <xref:System.Windows.Media.Matrix> podczas pierwszego 0,2 sekundy. Przykład zmienia <xref:System.Windows.Media.Matrix.M11%2A> i <xref:System.Windows.Media.Matrix.M12%2A> właściwości <xref:System.Windows.Media.Matrix>. Ta zmiana powoduje, że przycisk, aby zwiększyć i stają się nierówne. Przykład zmienia także <xref:System.Windows.Media.Matrix.OffsetX%2A> i <xref:System.Windows.Media.Matrix.OffsetY%2A> właściwości, aby przycisk zmienia pozycję.  
  
2.  Animuje drugi <xref:System.Windows.Media.Matrix> w wersji 1.0 w ciągu kilku sekund. Przycisk przemieszczeniu na inne stanowisko, gdy nie jest już nierówne czy rozciągnięte przycisku.  
  
3.  Powtarza animacji w nieskończoność.  
  
> [!NOTE]
>  Klucz klatek, które wynikają z <xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame> obiektu tworzenie nagłe skoki między wartościami, oznacza to, że ruch animacji jest jerky.  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 Aby uzyskać pełny przykład, zobacz [przykład animacji ramki kluczowej](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [Animacje kluczowych klatek — przegląd](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Klatki kluczowe — tematy z instrukcjami](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
