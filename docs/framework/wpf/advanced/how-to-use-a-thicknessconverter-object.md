---
title: 'Instrukcje: Użyj obiektu ThicknessConverter'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 22215a155f4a204e3edeebc464413d5718290bb4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577074"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>Instrukcje: Użyj obiektu ThicknessConverter
## <a name="example"></a>Przykład  
 W tym przykładzie przedstawiono sposób tworzenia wystąpienia <xref:System.Windows.ThicknessConverter> i korzystać z niego zmiany grubości obramowania.  
  
 W przykładzie zdefiniowano niestandardową metodę o nazwie `changeThickness`; ta metoda konwertuje najpierw zawartość <xref:System.Windows.Controls.ListBoxItem>, zgodnie z definicją w osobnym [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pliku do wystąpienia <xref:System.Windows.Thickness>i później Konwertuje zawartość <xref:System.String>. Ta metoda przekazuje <xref:System.Windows.Controls.ListBoxItem> do <xref:System.Windows.ThicknessConverter> obiektu, który konwertuje <xref:System.Windows.Controls.ContentControl.Content%2A> z <xref:System.Windows.Controls.ListBoxItem> do wystąpienia <xref:System.Windows.Thickness>. Ta wartość jest następnie przekazywany jako wartość <xref:System.Windows.Controls.Border.BorderThickness%2A> właściwość <xref:System.Windows.Controls.Border>.  
  
 W tym przykładzie nie działa.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Thickness>
- <xref:System.Windows.ThicknessConverter>
- <xref:System.Windows.Controls.Border>
- [Instrukcje: Zmień wartość właściwości marginesów](https://msdn.microsoft.com/library/8a313efd-5f99-4097-b4c1-8fa49d8379a2)
- [Instrukcje: Konwertowanie elementu ListBoxItem na nowy typ danych](https://msdn.microsoft.com/library/7a080b88-184e-4b27-bb61-d42bafba9727)
- [Panele — omówienie](../../../../docs/framework/wpf/controls/panels-overview.md)
