---
title: 'Przewodnik: Sprawdzanie poprawności danych w kontrolce DataGridView formularzy Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: f9bea4ef90a455f228fd095ad6a5c022b95493d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681836"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Przewodnik: Sprawdzanie poprawności danych w kontrolce DataGridView formularzy Windows Forms
Po wyświetleniu funkcji zapisu danych do użytkowników, często trzeba sprawdzanie poprawności danych wprowadzonych do formularza. <xref:System.Windows.Forms.DataGridView> Klasa oferuje wygodny sposób wykonanie sprawdzenia poprawności przed danych jest zaangażowana w magazynie danych. Sprawdzanie poprawności danych obsługi <xref:System.Windows.Forms.DataGridView.CellValidating> zdarzenie, które jest wywoływane przez <xref:System.Windows.Forms.DataGridView> podczas zmiany bieżącej komórki.  
  
 W tym instruktażu będą pobierać wiersze z `Customers` tabeli w bazie danych Northwind i wyświetlaj je w <xref:System.Windows.Forms.DataGridView> kontroli. Po użytkownik edytuje komórkę w `CompanyName` kolumny i próbuje komórka, <xref:System.Windows.Forms.DataGridView.CellValidating> programu obsługi zdarzeń zbada nowy ciąg nazwy firmy, aby upewnić się, to nie jest pusta, jeśli nowa wartość jest ciągiem pustym <xref:System.Windows.Forms.DataGridView> uniemożliwi użytkownika kursora opuszczanie komórki, dopóki nie podano niepustym ciągiem.  
  
 Aby skopiować kod, w tym temacie na jednej liście, zobacz [jak: Sprawdzanie poprawności danych w formancie DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 Aby ukończyć ten przewodnik, potrzebne są:  
  
-   Dostęp do serwera z przykładowej bazy danych Northwind programu SQL Server.  
  
## <a name="creating-the-form"></a>Tworzenie formularza  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>Aby sprawdzić poprawność danych w formancie DataGridView  
  
1.  Utwórz klasę, która pochodzi od klasy <xref:System.Windows.Forms.Form> i zawiera <xref:System.Windows.Forms.DataGridView> kontroli i <xref:System.Windows.Forms.BindingSource> składnika.  
  
     Poniższy przykład kodu zawiera inicjowanie podstawowych oraz `Main` metody.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  W definicji klasy formularza do obsługi szczegółowe informacje o połączenie z bazą danych, należy zaimplementować metodę.  
  
     W tym przykładzie kodu użyto `GetData` metodę, która zwraca wypełnione <xref:System.Data.DataTable> obiektu. Upewnij się, że możesz `connectionString` zmiennej na wartość, która jest odpowiednia dla bazy danych.  
  
    > [!IMPORTANT]
    >  Przechowywanie poufnych informacji, takich jak hasła, w ciągu połączenia mogą wpływać na bezpieczeństwo aplikacji. Przy użyciu uwierzytelniania Windows, nazywane również zintegrowane zabezpieczenia, jest Bezpieczniejszym sposobem na kontrolowanie dostępu do bazy danych. Aby uzyskać więcej informacji, zobacz [ochrony informacji o połączeniu](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Implementowanie obsługi dla formularza użytkownika <xref:System.Windows.Forms.Form.Load> zdarzeń, która inicjuje <xref:System.Windows.Forms.DataGridView> i <xref:System.Windows.Forms.BindingSource> i konfiguruje powiązanie danych.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Implementowanie obsługi <xref:System.Windows.Forms.DataGridView> kontrolki <xref:System.Windows.Forms.DataGridView.CellValidating> i <xref:System.Windows.Forms.DataGridView.CellEndEdit> zdarzenia.  
  
     <xref:System.Windows.Forms.DataGridView.CellValidating> Procedura obsługi zdarzeń jest, gdzie możesz określić czy wartość komórki w `CompanyName` kolumna jest pusta. W przypadku niepowodzenia weryfikacji wartość komórki zestawu <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> właściwość <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> klasy `true`. Powoduje to, że <xref:System.Windows.Forms.DataGridView> formantu, aby zapobiec opuszczania komórki kursora. Ustaw <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> właściwość wiersz, aby ciągiem objaśnienia. Spowoduje to wyświetlenie ikona błędu z etykietka narzędzia zawierająca tekst błędu. W <xref:System.Windows.Forms.DataGridView.CellEndEdit> ustawić programu obsługi zdarzeń <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> właściwości w wierszu do pustego ciągu. <xref:System.Windows.Forms.DataGridView.CellEndEdit> Wystąpi zdarzenie, tylko gdy komórki kończy działanie trybu edycji, który go nie może w razie niepowodzenia weryfikacji.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>Testowanie aplikacji  
 Teraz można przetestować formularz, aby upewnić się, że działa zgodnie z oczekiwaniami.  
  
#### <a name="to-test-the-form"></a>Aby przetestować formularz  
  
-   Skompilować i uruchomić aplikację.  
  
     Zostanie wyświetlony <xref:System.Windows.Forms.DataGridView> wypełnione danymi z `Customers` tabeli. Gdy klikniesz dwukrotnie komórkę w `CompanyName` kolumny, można edytować wartość. Jeśli usunięcie wszystkich znaków i naciśnij klawisz TAB, aby zakończyć działanie komórce <xref:System.Windows.Forms.DataGridView> zapobiega zakończone. Podczas wpisywania tekstu niepustym ciągiem w komórce, <xref:System.Windows.Forms.DataGridView> kontroli umożliwia wyjście komórki.  
  
## <a name="next-steps"></a>Następne kroki  
 Ta aplikacja zapewnia podstawową wiedzę na temat <xref:System.Windows.Forms.DataGridView> funkcje formantu. Można dostosować wygląd i zachowanie <xref:System.Windows.Forms.DataGridView> kontroli na kilka sposobów:  
  
-   Zmienianie stylów obramowania i nagłówek. Aby uzyskać więcej informacji, zobacz [jak: Zmiana obramowania i formantu DataGridView formularzy style linii siatki w Windows](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Włączać lub ograniczać danych wprowadzonych przez użytkownika <xref:System.Windows.Forms.DataGridView> kontroli. Aby uzyskać więcej informacji, zobacz [jak: Zapobieganie dodawaniu i usuwaniu w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), i [jak: Określanie kolumn jako tylko do odczytu w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Sprawdź dane wejściowe użytkownika błędy związane z bazy danych. Aby uzyskać więcej informacji, zobacz [instruktażu: Obsługa błędów występujących podczas wprowadzania danych w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Obsłużyć bardzo dużych zestawów danych przy użyciu trybu wirtualnego. Aby uzyskać więcej informacji, zobacz [instruktażu: Implementowanie trybu wirtualnego w Windows formantu DataGridView formularzy](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Dostosowywanie wyglądu komórek. Aby uzyskać więcej informacji, zobacz [jak: Dostosowywanie wyglądu komórek w formancie DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) i [jak: Ustawianie stylów czcionek i koloru w formancie DataGridView formularzy Windows](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Wprowadzanie danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
- [Instrukcje: Sprawdzanie poprawności danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Przewodnik: Obsługa błędów występujących podczas wprowadzania danych w kontrolce DataGridView formularzy Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Ochrona informacji o połączeniu](../../../../docs/framework/data/adonet/protecting-connection-information.md)
