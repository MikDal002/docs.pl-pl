---
title: 'Instrukcje: Dodawanie możliwości wyszukiwania do formantu ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- lists [Windows Forms], enabling searching
- list views [Windows Forms], enabling searching
- ListView control [Windows Forms], adding search capabilities
- searching [Windows Forms], adding search capabilities to ListView control
ms.assetid: 557782d9-b705-4bab-b496-9938afddac82
ms.openlocfilehash: 0f8b9535539f7f9cd8d0c8ba3a362e9ab7bef03a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716794"
---
# <a name="how-to-add-search-capabilities-to-a-listview-control"></a>Instrukcje: Dodawanie możliwości wyszukiwania do formantu ListView
Często, podczas pracy z dużą listy elementów w <xref:System.Windows.Forms.ListView> kontrolki, mają być oferowane możliwości wyszukiwania do użytkownika. <xref:System.Windows.Forms.ListView> Formant oferuje tej funkcji na dwa sposoby: tekst dopasowywanie i wyszukiwanie w lokalizacji.  
  
 <xref:System.Windows.Forms.ListView.FindItemWithText%2A> Metoda umożliwia wyszukiwanie tekstu w <xref:System.Windows.Forms.ListView> w widoku listy lub szczegółów danego ciągu wyszukiwania i opcjonalne początkowe i końcowe indeksu. Z kolei <xref:System.Windows.Forms.ListView.FindNearestItem%2A> metoda umożliwia znajdowanie element <xref:System.Windows.Forms.ListView> w widoku ikon lub Kafelek, biorąc pod uwagę zestaw współrzędnych x i y i kierunek wyszukiwania.  
  
### <a name="to-find-an-item-using-text"></a>Aby znaleźć element przy użyciu tekstu  
  
1.  Tworzenie <xref:System.Windows.Forms.ListView> za pomocą <xref:System.Windows.Forms.ListView.View%2A> właściwością <xref:System.Windows.Forms.View.Details> lub <xref:System.Windows.Forms.View.List>, a następnie wypełnij <xref:System.Windows.Forms.ListView> z elementami.  
  
2.  Wywołaj <xref:System.Windows.Forms.ListView.FindItemWithText%2A> jest metoda tekstu elementu, które chcesz znaleźć.  
  
3.  Poniższy przykład kodu demonstruje sposób tworzenia prostej <xref:System.Windows.Forms.ListView>go wypełnić przy użyciu elementów i użyj wprowadzanie tekstu przez użytkownika, aby znaleźć element na liście.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#1)]  
  
### <a name="to-find-an-item-using-x--and-y-coordinates"></a>Aby znaleźć element za pomocą współrzędnych x i y  
  
1.  Tworzenie <xref:System.Windows.Forms.ListView> za pomocą <xref:System.Windows.Forms.View> właściwością <xref:System.Windows.Forms.View.SmallIcon> lub <xref:System.Windows.Forms.View.LargeIcon>, a następnie wypełnij <xref:System.Windows.Forms.ListView> z elementami.  
  
2.  Wywołaj <xref:System.Windows.Forms.ListView.FindNearestItem%2A> jest metoda żądaną współrzędne x i y- i kierunku chcesz przeszukać.  
  
3.  Poniższy przykład kodu pokazuje, jak utworzyć podstawowe ikonę <xref:System.Windows.Forms.ListView>, umieścić w nim elementy i przechwytywania <xref:System.Windows.Forms.Control.MouseDown> zdarzeń Aby znaleźć najbliższy element w górę kierunku.  
  
 [!code-cpp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/cpp/form1.cpp#2)]
 [!code-csharp[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/CS/form1.cs#2)]
 [!code-vb[System.Windows.Forms.ListViewFindItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewFindItems/VB/form1.vb#2)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.FindItemWithText%2A>
- <xref:System.Windows.Forms.ListView.FindNearestItem%2A>
- [Kontrolka ListView](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [ListView, kontrolka — omówienie](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [Instrukcje: Dodawanie i usuwanie elementów za pomocą formantu ListView formularzy Windows](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
