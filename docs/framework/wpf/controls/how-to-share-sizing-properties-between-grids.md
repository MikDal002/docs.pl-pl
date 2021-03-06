---
title: 'Instrukcje: Udostępniaj właściwości ustalania rozmiaru miedzy siatkami'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: e415cb8bf5d2eb53926ae885ba18685390a61201
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694103"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Instrukcje: Udostępniaj właściwości ustalania rozmiaru miedzy siatkami
W tym przykładzie pokazano, jak udostępnianie danych zmiany rozmiaru kolumn i wierszy między <xref:System.Windows.Controls.Grid> elementów, aby zachować zmiany rozmiaru spójne.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia dwa <xref:System.Windows.Controls.Grid> jako elementy podrzędne elementu nadrzędnego <xref:System.Windows.Controls.DockPanel>. <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> Dołączonych właściwości <xref:System.Windows.Controls.Grid> jest zdefiniowany w nadrzędnej <xref:System.Windows.Controls.DockPanel>.  
  
 Przykład manipuluje wartości właściwości, używając dwóch <xref:System.Windows.Controls.Button> elementów; każdy element reprezentuje jedną z wartości właściwości typu Boolean. Gdy <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> wartość właściwości jest równa `true`, każdego wiersza lub kolumny elementu członkowskiego <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> udostępnia informacje dotyczące zmiany rozmiaru, niezależnie od tego, zawartość wiersza lub kolumny.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 W poniższym przykładzie związanym z kodem obsługuje metody, przycisk <xref:System.Windows.Controls.Primitives.ButtonBase.Click> wywołuje zdarzenia. W przykładzie polecenie zapisuje wyniki tych wywołań metody <xref:System.Windows.Controls.TextBlock> elementy, które są związane z użycia metod get na dane wyjściowe nowe wartości właściwości jako ciągi.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [Panele — omówienie](../../../../docs/framework/wpf/controls/panels-overview.md)
