---
title: 'Instrukcje: Sortuj dane w widoku'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 50e1426f2a220c7d947f7feb9c3ec7e1c4de7643
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522677"
---
# <a name="how-to-sort-data-in-a-view"></a>Instrukcje: Sortuj dane w widoku
W tym przykładzie opisano sposób sortowania danych w widoku.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład tworzy prostą <xref:System.Windows.Controls.ListBox> i <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Programu obsługi zdarzeń przycisku zawiera logikę, aby posortować elementy na <xref:System.Windows.Controls.ListBox> w kolejności malejącej. Można to zrobić, ponieważ dodawanie elementów do <xref:System.Windows.Controls.ListBox> w ten sposób doda je do <xref:System.Windows.Controls.ItemCollection> z <xref:System.Windows.Controls.ListBox>, i <xref:System.Windows.Controls.ItemCollection> pochodzi od klasy <xref:System.Windows.Data.CollectionView> klasy. Są wiązane z <xref:System.Windows.Controls.ListBox> do kolekcji za pomocą <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> właściwości, można użyć tej samej techniki do sortowania.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Tak długo, jak masz odwołanie do obiektu widoku, można użyć tej samej techniki Aby posortować zawartość innych widoków kolekcji. Na przykład sposób uzyskać widok zobacz [widok domyślny zbiór danych](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Inny przykład, zobacz [sortowania GridView kolumny po kliknięciu nagłówka](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Aby uzyskać więcej informacji o widokach, zobacz powiązania do kolekcji w [Przegląd wiązanie danych](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Aby uzyskać przykład sposobu stosowania logiki sortowania [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], zobacz [sortowania i grupy danych przy użyciu widoku w XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Sortowanie kolumny GridView po kliknięciu nagłówka](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Powiązanie danych — omówienie](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Filtrowanie danych w widoku](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
