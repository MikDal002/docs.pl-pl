---
title: 'Instrukcje: Użyj załączonych właściwości kanwy, aby ustawić położenie elementów podrzędnych'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: a0d0bc51466ee18e09eeffe80a568d277280248c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682083"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a>Instrukcje: Użyj załączonych właściwości kanwy, aby ustawić położenie elementów podrzędnych
W tym przykładzie pokazano, jak użyć załączonych właściwości <xref:System.Windows.Controls.Canvas> położenie elementów podrzędnych.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie dodano cztery <xref:System.Windows.Controls.Button> jako elementy podrzędne elementu nadrzędnego <xref:System.Windows.Controls.Canvas>. Każdy element jest reprezentowany przez <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, i <xref:System.Windows.Controls.Canvas.Top%2A>.
Każdy <xref:System.Windows.Controls.Button> jest umieszczony względem nadrzędnego <xref:System.Windows.Controls.Canvas> i zgodnie z jej wartością właściwości przypisane.  
  
 [!code-cpp[CanvasAttachedProperties#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [Panele — omówienie](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)
- [Przegląd właściwości dołączonych](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)
