---
title: 'Instrukcje: Animuj ciąg z wykorzystaniem klatek kluczowych'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 4cadc1e7e4b7ee70e3a71ddaf433327a7561125d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670839"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Instrukcje: Animuj ciąg z wykorzystaniem klatek kluczowych
W tym przykładzie pokazano, jak animować ciąg, który w tym przykładzie jest <xref:System.Windows.Controls.ContentControl.Content%2A> właściwość <xref:System.Windows.Controls.Button> kontroli przy użyciu klatek kluczowych.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie użyto <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> klasy, aby animować <xref:System.Windows.Controls.ContentControl.Content%2A> właściwość <xref:System.Windows.Controls.Button>.  
  
 Klatek kluczowych w tym przykładzie są używane <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> klasy, ponieważ animacji ciąg, który jest tworzony z użyciem klatek kluczowych można używać tylko dyskretnych klatek kluczowych. Dyskretne klatek kluczowych, takich jak <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> tworzenie nagłe skoki między wartości, oznacza to, zmiany w animacji wystąpić szybko i nie są subtelne.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Aby uzyskać pełny przykład, zobacz [przykład animacji ramki kluczowej](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Animacje kluczowych klatek — przegląd](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Klatki kluczowe — tematy z instrukcjami](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
