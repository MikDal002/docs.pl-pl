---
title: 'Instrukcje: Ustawianie przemiennych wierszy dla kontrolki DataGridView formularzy Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], row styles
- data grids [Windows Forms], row styles
- rows [Windows Forms], data grids
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
ms.openlocfilehash: ba5aaec9e66f1d3c66bb50709f6fbd4afde893ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562729"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control"></a>Instrukcje: Ustawianie przemiennych wierszy dla kontrolki DataGridView formularzy Windows Forms
Dane tabelaryczne często jest przesyłany do użytkowników w postaci księgi, gdzie przemienne wiersze mają różnych kolorów tła. Ten format ułatwia użytkownikom Poinformuj komórki, które są w każdym wierszu, szczególnie w przypadku szerokich tabel, które mają wiele kolumn.  
  
 Za pomocą <xref:System.Windows.Forms.DataGridView> kontrolę, można określić dotycząca pełną styl naprzemiennych wierszach. Dzięki temu możesz użyć właściwości stylu, takich jak kolor pierwszego planu i czcionki, oprócz kolor tła do odróżnienia przemienne wiersze.  
  
 Są obsługiwane dla tego zadania w programie Visual Studio.  Zobacz też [jak: Ustawianie przemiennych wierszy dla formantu DataGridView, które przy użyciu narzędzia Projektant formularzy Windows](https://msdn.microsoft.com/library/3z9sk148\(v=vs.110\)).  
  
### <a name="to-set-alternating-row-styles-programmatically"></a>Aby ustawić programowo alternatywnych stylów wierszy  
  
-   Ustawianie właściwości <xref:System.Windows.Forms.DataGridViewCellStyle> obiektów zwróconych przez <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> i <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> właściwości <xref:System.Windows.Forms.DataGridView>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  Style określony za pomocą <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> i <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> właściwości przesłaniają style określone na podstawie kolumny i <xref:System.Windows.Forms.DataGridView> poziomu, ale są zastępowane przez style ustawić na poziomie wierszy i komórek. Aby uzyskać więcej informacji, zobacz [style komórki w formancie DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   A <xref:System.Windows.Forms.DataGridView> formantu o nazwie `dataGridView1`.  
  
-   Odwołuje się do <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, i <xref:System.Windows.Forms?displayProperty=nameWithType> zestawów.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 W przypadku maksymalnej skalowalności powinny współużytkować <xref:System.Windows.Forms.DataGridViewCellStyle> obiektów między wiele wierszy, kolumny lub komórki, które używają tego samego style, zamiast oddzielnie ustawienie ponownego obliczenia właściwości stylu dla każdego elementu. Aby uzyskać więcej informacji, zobacz [najlepsze praktyki dotyczące skalowania formantu DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Podstawowe formatowanie i style w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Style komórki w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Najlepsze praktyki dotyczące skalowania kontrolki DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [Instrukcje: Ustawianie stylów czcionek i koloru w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)
