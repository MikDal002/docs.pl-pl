---
title: 'Instrukcje: Dodawanie tabel i kolumn do formantu DataGrid formularzy Windows przy użyciu narzędzia Projektant'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: c130dac068ee4866f44fd12398202e21d91fcf48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536232"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Instrukcje: Dodawanie tabel i kolumn do formantu DataGrid formularzy Windows przy użyciu narzędzia Projektant

> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> Kontroli zastępuje i dodaje funkcjonalność do <xref:System.Windows.Forms.DataGrid> kontrolować; jednak <xref:System.Windows.Forms.DataGrid> kontrolki została zachowana na potrzeby zgodności z poprzednimi wersjami i użycia w przyszłości, jeśli wybierzesz. Aby uzyskać więcej informacji, zobacz [różnice między Windows Forms formantami DataGridView i DataGrid](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Można wyświetlić dane w formularzach Windows Forms <xref:System.Windows.Forms.DataGrid> formantu w tabelach i kolumnach, tworząc <xref:System.Windows.Forms.DataGridTableStyle> obiektów oraz dodać je do <xref:System.Windows.Forms.GridTableStylesCollection> obiektu, który jest dostępny za pośrednictwem <xref:System.Windows.Forms.DataGrid> kontrolki <xref:System.Windows.Forms.DataGrid.TableStyles%2A> właściwości. Każdy styl tabeli Wyświetla zawartość tabeli niezależnie od danych jest określona w <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> właściwość <xref:System.Windows.Forms.DataGridTableStyle>. Domyślny styl tabeli bez style kolumny określone wyświetli wszystkie kolumny w tabeli danych. Można ograniczyć, które kolumny z tabeli są wyświetlane, dodając <xref:System.Windows.Forms.DataGridColumnStyle> obiekty do <xref:System.Windows.Forms.GridColumnStylesCollection>, który jest dostępny za pośrednictwem <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> właściwości każdego <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Poniższe procedury wymagają **aplikacji Windows** projektu za pomocą formularza, który zawiera <xref:System.Windows.Forms.DataGrid> kontroli. Aby dowiedzieć się, jak skonfigurować taki projekt, zobacz [jak: Utwórz projekt aplikacji Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) i [jak: Dodawanie formantów do formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). Domyślnie w programie Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> formantu nie znajduje się w **przybornika**. Aby uzyskać informacje dotyczące dodawania go, zobacz [jak: Dodaj elementy do przybornika](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Okna dialogowe i polecenia menu mogą się różnić od tych opisanych w Pomocy, w zależności od ustawień aktywnych lub wydania. Aby zmienić swoje ustawienia, wybierz opcję **Import i eksport ustawień** na **narzędzia** menu. Aby uzyskać więcej informacji, zobacz [personalizowanie środowiska IDE programu Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Aby dodać tabelę do formantu DataGrid w Projektancie  
  
1.  Aby wyświetlić dane w tabeli, najpierw musisz powiązać <xref:System.Windows.Forms.DataGrid> kontrolki do zestawu danych. Aby uzyskać więcej informacji, zobacz [jak: Powiązywanie formantu DataGrid formularzy Windows ze źródłem danych przy użyciu narzędzia Projektant](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Wybierz <xref:System.Windows.Forms.DataGrid> kontrolki <xref:System.Windows.Forms.DataGrid.TableStyles%2A> właściwości w oknie dialogowym właściwości, a następnie kliknij przycisk wielokropka (![VisualStudioEllipsesButton — zrzut ekranu](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) obok pozycji Właściwość do wyświetlenia **Edytor kolekcji Element DataGridTableStyle**.  
  
3.  Edytor kolekcji kliknij **Dodaj** do wstawienia styl tabeli.  
  
4.  Kliknij przycisk **OK** aby zamknąć Edytor kolekcji, a następnie otworzyć go ponownie, klikając przycisk wielokropka obok pozycji <xref:System.Windows.Forms.DataGrid.TableStyles%2A> właściwości.  
  
     Po ponownym otwarciu edytora kolekcji wszystkie tabele danych powiązane z formantem pojawi się na liście rozwijanej <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> właściwości stylu tabeli.  
  
5.  W **członków** okno Edytor kolekcji, kliknij przycisk Styl tabeli.  
  
6.  W **właściwości** okno Edytor kolekcji, wybierz opcję <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> wartość tabeli, którą chcesz wyświetlić.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Aby dodać kolumnę do formantu DataGrid w Projektancie  
  
1.  W **członków** pole **Edytor kolekcji Element DataGridTableStyle**, wybierz styl odpowiedniej tabeli. W **właściwości** okno Edytor kolekcji, wybierz opcję <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> kolekcji, a następnie kliknij przycisk wielokropka (![VisualStudioEllipsesButton — zrzut ekranu](../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) obok właściwości, aby wyświetlić **DataGridColumnStyle — Edytor kolekcji**.  
  
2.  Edytor kolekcji kliknij **Dodaj** wstawić styl kolumny lub kliknij strzałkę w dół obok pozycji **Dodaj** do określenia typu kolumny.  
  
     W polu listy rozwijanej można wybrać opcję <xref:System.Windows.Forms.DataGridTextBoxColumn> lub <xref:System.Windows.Forms.DataGridBoolColumn> typu.  
  
3.  Kliknij przycisk OK, aby zamknąć **DataGridColumnStyle — Edytor kolekcji**, a następnie otwórz go ponownie, klikając przycisk wielokropka obok <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> właściwości.  
  
     Po ponownym otwarciu edytora kolekcji żadnych kolumn danych w tabeli powiązane dane będą wyświetlane na liście rozwijanej <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> właściwość style kolumny.  
  
4.  W **członków** okno Edytor kolekcji, kliknij przycisk Styl kolumny.  
  
5.  W **właściwości** okno Edytor kolekcji, wybierz opcję <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> wartości w kolumnie, którą chcesz wyświetlić.  
  
## <a name="see-also"></a>Zobacz także
- [DataGrid, kontrolka](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Instrukcje: Usuń lub ukrywanie kolumn w kontrolce DataGrid formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
