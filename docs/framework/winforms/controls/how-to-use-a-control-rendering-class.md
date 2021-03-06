---
title: 'Instrukcje: Używanie klasy renderowania formantu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: 4453e04f6fe36ad2b0de7696da68d55264cd47b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534673"
---
# <a name="how-to-use-a-control-rendering-class"></a>Instrukcje: Używanie klasy renderowania formantu
W tym przykładzie przedstawiono sposób użycia <xref:System.Windows.Forms.ComboBoxRenderer> klasy do renderowania kontrolki pola kombi strzałkę listy rozwijanej. Przykład zawiera <xref:System.Windows.Forms.Control.OnPaint%2A> metoda prostego formantu niestandardowego. <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> Właściwość jest używana do określenia, czy style wizualne są włączone w obszarze klienta w aplikacji systemu windows. Jeśli style wizualne są aktywne, a następnie <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> metody będą renderowane strzałki listy rozwijanej przy użyciu stylów wizualnych; w przeciwnym razie <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> metody będą renderowane strzałki listy rozwijanej w stylu klasycznym Windows.  
  
## <a name="example"></a>Przykład  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Niestandardowy formant pochodzące z <xref:System.Windows.Forms.Control> klasy.  
  
-   A <xref:System.Windows.Forms.Form> obsługujący kontrolki niestandardowej.  
  
-   Odwołuje się do <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, i <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> przestrzeni nazw.  
  
## <a name="see-also"></a>Zobacz także
- [Renderowanie kontrolek przy użyciu stylów wizualnych](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)
