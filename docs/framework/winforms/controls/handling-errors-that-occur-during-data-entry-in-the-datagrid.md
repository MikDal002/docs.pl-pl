---
title: 'Przewodnik: Obsługa błędów występujących podczas wprowadzania danych w kontrolce DataGridView formularzy Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: b47185118441b60302ef8c8dc8418f7c6a873e2c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644836"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Przewodnik: Obsługa błędów występujących podczas wprowadzania danych w kontrolce DataGridView formularzy Windows Forms
Obsługa błędów z źródłowy magazyn danych jest wymagana funkcja dla aplikacji wprowadzania danych. Formularze Windows <xref:System.Windows.Forms.DataGridView> kontroli ułatwia to dzięki uwidocznieniu działania <xref:System.Windows.Forms.DataGridView.DataError> zdarzenie, które jest wywoływane, gdy magazyn danych wykryje naruszenie ograniczenia lub reguła biznesowa przerwane.  
  
 W tym instruktażu będą pobierać wiersze z `Customers` tabeli w bazie danych Northwind i wyświetlaj je w <xref:System.Windows.Forms.DataGridView> kontroli. Gdy duplikat `CustomerID` niewykrycia wartości w nowym wierszu lub edytowane istniejącego wiersza, <xref:System.Windows.Forms.DataGridView.DataError> wystąpi zdarzenie, który będzie obsługiwany przez wyświetlenie <xref:System.Windows.Forms.MessageBox> opisujący wyjątek.  
  
 Aby skopiować kod, w tym temacie na jednej liście, zobacz [jak: Obsługa błędów występujących podczas wprowadzania danych w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 Aby ukończyć ten przewodnik, potrzebne są:  
  
-   Dostęp do serwera z przykładowej bazy danych Northwind programu SQL Server.  
  
## <a name="creating-the-form"></a>Tworzenie formularza  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Aby obsługiwać błędy wprowadzania danych w formancie DataGridView  
  
1.  Utwórz klasę, która pochodzi od klasy <xref:System.Windows.Forms.Form> i zawiera <xref:System.Windows.Forms.DataGridView> kontroli i <xref:System.Windows.Forms.BindingSource> składnika.  
  
     Poniższy przykład kodu zawiera inicjowanie podstawowych oraz `Main` metody.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  W definicji klasy formularza do obsługi szczegółowe informacje o połączenie z bazą danych, należy zaimplementować metodę.  
  
     W tym przykładzie kodu użyto `GetData` metodę, która zwraca wypełnione <xref:System.Data.DataTable> obiektu. Upewnij się, że możesz `connectionString` zmiennej na wartość, która jest odpowiednia dla bazy danych.  
  
    > [!IMPORTANT]
    >  Przechowywanie poufnych informacji, takich jak hasła, w ciągu połączenia mogą wpływać na bezpieczeństwo aplikacji. Korzystanie z uwierzytelniania systemu Windows (znanego również jako zabezpieczenia zintegrowane) jest bezpieczniejszym sposobem na kontrolowanie dostępu do bazy danych. Aby uzyskać więcej informacji, zobacz [ochrony informacji o połączeniu](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implementowanie obsługi dla formularza użytkownika <xref:System.Windows.Forms.Form.Load> zdarzeń, która inicjuje <xref:System.Windows.Forms.DataGridView> i <xref:System.Windows.Forms.BindingSource> i konfiguruje powiązanie danych.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Obsługa <xref:System.Windows.Forms.DataGridView.DataError> zdarzenie na <xref:System.Windows.Forms.DataGridView>.  
  
     Kontekst błędu w przypadku operacji zatwierdzania, wyświetla błąd w <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Testowanie aplikacji  
 Teraz można przetestować formularz, aby upewnić się, że działa zgodnie z oczekiwaniami.  
  
#### <a name="to-test-the-form"></a>Aby przetestować formularz  
  
-   Naciśnij klawisz F5, aby uruchomić aplikację.  
  
     Zostanie wyświetlony <xref:System.Windows.Forms.DataGridView> kontroli wypełnione danymi z tabeli Customers. Jeśli wprowadzasz zduplikowane wartości `CustomerID` i zatwierdź edycję, wartość komórki zostaną przywrócone automatycznie i zostanie wyświetlony <xref:System.Windows.Forms.MessageBox> wyświetlającą błąd zapisu danych.  
  
## <a name="next-steps"></a>Następne kroki  
 Ta aplikacja zapewnia podstawową wiedzę na temat <xref:System.Windows.Forms.DataGridView> funkcje formantu. Można dostosować wygląd i zachowanie <xref:System.Windows.Forms.DataGridView> kontroli na kilka sposobów:  
  
-   Zmienianie stylów obramowania i nagłówek. Aby uzyskać więcej informacji, zobacz [jak: Zmiana obramowania i formantu DataGridView formularzy style linii siatki w Windows](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Włączać lub ograniczać danych wprowadzonych przez użytkownika <xref:System.Windows.Forms.DataGridView> kontroli. Aby uzyskać więcej informacji, zobacz [jak: Zapobieganie dodawaniu i usuwaniu w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), i [jak: Określanie kolumn jako tylko do odczytu w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Weryfikowanie danych wejściowych użytkownika do <xref:System.Windows.Forms.DataGridView> kontroli. Aby uzyskać więcej informacji, zobacz [instruktażu: Sprawdzanie poprawności danych w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Obsłużyć bardzo dużych zestawów danych przy użyciu trybu wirtualnego. Aby uzyskać więcej informacji, zobacz [instruktażu: Implementowanie trybu wirtualnego w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Dostosowywanie wyglądu komórek. Aby uzyskać więcej informacji, zobacz [jak: Dostosowywanie wyglądu komórek w formancie DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) i [jak: Ustawianie domyślnych stylów komórki dla formantu DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Wprowadzanie danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [Instrukcje: Obsługa błędów występujących podczas wprowadzania danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Przewodnik: Sprawdzanie poprawności danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Ochrona informacji o połączeniu](../../../../docs/framework/data/adonet/protecting-connection-information.md)
