---
title: 'Instrukcje: Wyodrębnij zawartość tekstu z RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 2c4500f4e5dad56b246148577abeef97f1912205
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666669"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Instrukcje: Wyodrębnij zawartość tekstu z RichTextBox
W tym przykładzie pokazano, jak wyodrębnić zawartość <xref:System.Windows.Controls.RichTextBox> jako zwykły tekst.  
  
## <a name="example"></a>Przykład  
 Następujące [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] kodu w tym artykule opisano nazwane <xref:System.Windows.Controls.RichTextBox> formantu o prostej zawartości.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Przykład  
 Poniższy kod implementuje metodę, która przyjmuje <xref:System.Windows.Controls.RichTextBox> jako argument i zwraca ciąg reprezentujący zawartość zwykły tekst <xref:System.Windows.Controls.RichTextBox>.  
  
 Metoda tworzy nowy <xref:System.Windows.Documents.TextRange> z zawartości <xref:System.Windows.Controls.RichTextBox>przy użyciu <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> i <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> do wskazania zakresu zawartości do wyodrębnienia.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> i <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> właściwości każdego zwracają <xref:System.Windows.Documents.TextPointer>i są dostępne na FlowDocument podstawowego, który reprezentuje zawartość <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> Udostępnia właściwości tekst zwykły tekst części zwraca <xref:System.Windows.Documents.TextRange> jako ciąg.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Zobacz także
- [RichTextBox — omówienie](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
- [TextBox — omówienie](../../../../docs/framework/wpf/controls/textbox-overview.md)
