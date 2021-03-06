---
title: Formatowanie danych w formancie DataGridView formularzy systemu Windows
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- data [Windows Forms], formatting in grids
- data grids [Windows Forms], formatting data
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
ms.openlocfilehash: 0016b87add6f20223bdeda72f10ac94b74ec9fcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737861"
---
# <a name="data-formatting-in-the-windows-forms-datagridview-control"></a>Formatowanie danych w formancie DataGridView formularzy systemu Windows
<xref:System.Windows.Forms.DataGridView> Control oferuje automatyczna konwersja między wartości komórek i typy danych, które są wyświetlane kolumny nadrzędnej. Tekst pola kolumny, na przykład wyświetlanie ciągów reprezentujących daty, godziny, liczby i wartości wyliczenia i konwertowanie wartości ciągu wprowadzonych przez użytkownika typy wymagane przez Magazyn danych.  
  
## <a name="formatting-with-the-datagridviewcellstyle-class"></a>Formatowanie przy użyciu klasy DataGridViewCellStyle  
 <xref:System.Windows.Forms.DataGridView> Kontrola zapewnia podstawowe dane formatowanie wartości komórki za pomocą <xref:System.Windows.Forms.DataGridViewCellStyle> klasy. Możesz użyć <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> właściwości formatowania daty, godziny, numer i wyliczenia wartości dla bieżącej kultury domyślnej przy użyciu specyfikatorów formatu opisanego w [typy formatowania](../../../../docs/standard/base-types/formatting-types.md). Możesz również sformatować te wartości dla określonych kultur przy użyciu <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> właściwości. Podany format jest używany do wyświetlania danych i analizowanie danych wprowadzonych przez użytkownika w określonym formacie.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle> Klasa udostępnia dodatkowe właściwości formatowania wordwrap, wyrównanie tekstu i wyświetlanie niestandardowej wartości bazy danych o wartości null. Aby uzyskać więcej informacji, zobacz [jak: Formatowanie danych w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="formatting-with-the-cellformatting-event"></a>Formatowanie ze zdarzeniem CellFormatting  
 Podstawowe formatowanie nie odpowiada Twoim potrzebom, możesz podać dane niestandardowe formatowanie w obsłudze dla <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> zdarzeń. <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> Przekazane do narzędzia obsługi ma <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> właściwość, która początkowo zawiera wartość komórki. Zazwyczaj ta wartość jest automatycznie konwertowane na typ wyświetlania. Aby przekonwertować wartość samodzielnie, należy ustawić <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> właściwość z wartością typ wyświetlania.  
  
> [!NOTE]
>  Jeśli ciąg formatu jest włączone dla tej komórki, zastępuje ona zmiana <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> wartość właściwości, chyba że <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> właściwość `true`.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting> Zdarzenie jest również przydatne, gdy użytkownik chce ustawić <xref:System.Windows.Forms.DataGridViewCellStyle> właściwości dla poszczególnych komórek na podstawie ich wartości. Aby uzyskać więcej informacji, zobacz [jak: Dostosowywanie formatowania danych w formancie DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Jeśli domyślne podczas analizowania wartości określonych przez użytkownika nie odpowiada Twoim potrzebom, które ułatwią Ci obsługę <xref:System.Windows.Forms.DataGridView.CellParsing> zdarzenia <xref:System.Windows.Forms.DataGridView> formantu, aby podać niestandardowy analizy.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Wyświetlanie danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
- [Style komórki w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
- [Instrukcje: Formatowanie danych w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [Instrukcje: Dostosowywanie formatowania danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
