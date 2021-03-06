---
title: 'Instrukcje: Dodawanie tabel i kolumn do kontrolki DataGrid formularzy Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: be0bb6d3d7b8d8b362653257139e83900dbb2780
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717873"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a>Instrukcje: Dodawanie tabel i kolumn do kontrolki DataGrid formularzy Windows Forms
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> Kontroli zastępuje i dodaje funkcjonalność do <xref:System.Windows.Forms.DataGrid> kontrolować; jednak <xref:System.Windows.Forms.DataGrid> kontrolki została zachowana na potrzeby zgodności z poprzednimi wersjami i użycia w przyszłości, jeśli wybierzesz. Aby uzyskać więcej informacji, zobacz [różnice między Windows Forms formantami DataGridView i DataGrid](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Można wyświetlić dane w formularzach Windows Forms <xref:System.Windows.Forms.DataGrid> formantu w tabelach i kolumnach, tworząc **Element DataGridTableStyle** obiektów oraz dodać je do **GridTableStylesCollection** obiektu, który jest dostępne za pośrednictwem <xref:System.Windows.Forms.DataGrid> kontrolki **TableStyles** właściwości. Każdy styl tabeli Wyświetla zawartość tabeli niezależnie od danych jest określona w **Element DataGridTableStyle** obiektu **MappingName** właściwości. Domyślnie styl tabeli za pomocą nie style kolumny określone wyświetli wszystkie kolumny w tabeli danych. Można ograniczyć, które kolumny z tabeli są wyświetlane, dodając **DataGridColumnStyle** obiekty do **kolekcji GridColumnStylesCollection** obiektu, który jest dostępny za pośrednictwem  **GridColumnStyles** właściwości każdego **Element DataGridTableStyle** obiektu.  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a>Aby programowo dodać tabel i kolumn z elementem DataGrid  
  
1.  Aby wyświetlić dane w tabeli, najpierw musisz powiązać <xref:System.Windows.Forms.DataGrid> kontrolki do zestawu danych. Aby uzyskać więcej informacji, zobacz [jak: Powiązywanie formantu DataGrid formularzy Windows ze źródłem danych](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
    > [!CAUTION]
    >  Podczas określania programowo Style kolumn, Zawsze twórz **DataGridColumnStyle** obiektów i dodaj je do **kolekcji GridColumnStylesCollection** obiektu przed dodaniem  **Element DataGridTableStyle** obiekty do **GridTableStylesCollection** obiektu. Po dodaniu pustą **Element DataGridTableStyle** obiektu do kolekcji, **DataGridColumnStyle** obiekty są generowane automatycznie. W związku z tym, zostanie zgłoszony wyjątek, Jeśli spróbujesz dodać nowe **DataGridColumnStyle** obiekty ze zduplikowanymi **MappingName** wartości **kolekcji GridColumnStylesCollection**obiektu.  
  
2.  Zadeklaruj nowy styl tabeli i ustaw jego nazwę mapowania.  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  Zadeklaruj nowy styl kolumny i ustaw jego nazwę mapowania i inne właściwości.  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  Wywołaj **Dodaj** metody **kolekcji GridColumnStylesCollection** obiekt, aby dodać kolumnę do styl tabeli  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  Wywołaj **Dodaj** metody **GridTableStylesCollection** obiekt do dodania styl tabeli do siatki danych.  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a>Zobacz także
- [DataGrid, kontrolka](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [Instrukcje: Usuń lub ukrywanie kolumn w kontrolce DataGrid formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
