---
title: 'Instrukcje: Pobierz lub ustaw wartość dokowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: 847f8732e1807ab2541d42fe720aacbecb034154
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738511"
---
# <a name="how-to-get-or-set-a-dock-value"></a>Instrukcje: Pobierz lub ustaw wartość dokowania
Poniższy przykład pokazuje, jak przypisać <xref:System.Windows.Controls.Dock> wartość obiektu. W przykładzie użyto <xref:System.Windows.Controls.DockPanel.GetDock%2A> i <xref:System.Windows.Controls.DockPanel.SetDock%2A> metody <xref:System.Windows.Controls.DockPanel>.  
  
## <a name="example"></a>Przykład  
 Przykład tworzy wystąpienie <xref:System.Windows.Controls.TextBlock> elementu, `txt1`, a następnie przypisuje <xref:System.Windows.Controls.Dock> wartość `Top` przy użyciu <xref:System.Windows.Controls.DockPanel.SetDock%2A> metody <xref:System.Windows.Controls.DockPanel>. Następnie dołącza wartości <xref:System.Windows.Controls.Dock> właściwości <xref:System.Windows.Controls.TextBlock.Text%2A> z <xref:System.Windows.Controls.TextBlock> elementu za pomocą <xref:System.Windows.Controls.DockPanel.GetDock%2A> metody. Ponadto w przykładzie dodano <xref:System.Windows.Controls.TextBlock> elementu nadrzędnego <xref:System.Windows.Controls.DockPanel>, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [Panele — omówienie](../../../../docs/framework/wpf/controls/panels-overview.md)
