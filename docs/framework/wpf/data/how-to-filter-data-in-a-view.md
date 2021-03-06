---
title: 'Instrukcje: Filtruj dane w widoku'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: 33af517c086f8f89cc06a1de7a2979c5b1624109
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689328"
---
# <a name="how-to-filter-data-in-a-view"></a>Instrukcje: Filtruj dane w widoku
Ten przykład przedstawia sposób filtrowania danych w widoku.  
  
## <a name="example"></a>Przykład  
 Aby utworzyć filtr, należy zdefiniować metodę, która udostępnia logikę filtrowania. Metoda jest używana jako wywołanie zwrotne i akceptuje parametr typu `object`. Poniższa metoda zwraca wszystkie `Order` obiekty z `filled` właściwość ustawioną na "No" filtrowanie pozostałymi obiektami.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 Można użyć filtru, jak pokazano w poniższym przykładzie. W tym przykładzie `myCollectionView` jest <xref:System.Windows.Data.ListCollectionView> obiektu.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Aby cofnąć filtrowanie, możesz ustawić <xref:System.Windows.Data.CollectionView.Filter%2A> właściwości `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Aby uzyskać informacje o tym, jak utworzyć lub uzyskać widok, zobacz [widok domyślny zbiór danych](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Aby uzyskać kompletny przykład, zobacz [sortowanie i filtrowanie elementów w przykładzie widok](https://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Jeśli obiekt widoku pochodzi z <xref:System.Windows.Data.CollectionViewSource> obiekt i zastosować logikę filtrowania przez ustawienie programu obsługi zdarzeń dla <xref:System.Windows.Data.CollectionViewSource.Filter> zdarzeń. W poniższym przykładzie `listingDataView` jest wystąpieniem <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 Poniżej pokazano implementacja przykładu `ShowOnlyBargainsFilter` procedury obsługi zdarzeń filtra. Ta procedura obsługi zdarzeń używa <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> właściwości, aby odfiltrować `AuctionItem` obiektów, które mają `CurrentPrice` 25 USD lub nowszej.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [Powiązanie danych — omówienie](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Sortowanie danych w widoku](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
