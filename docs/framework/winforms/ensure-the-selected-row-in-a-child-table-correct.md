---
title: 'Instrukcje: Upewnij się, że zaznaczony wiersz w tabeli podrzędnej pozostaje w prawidłowym położeniu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
ms.openlocfilehash: ef2c72fb941aa40eff85af4a83f6c76843dc2d6e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547634"
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a>Instrukcje: Upewnij się, że zaznaczony wiersz w tabeli podrzędnej pozostaje w prawidłowym położeniu
Często w przypadku, gdy pracujesz z powiązanie danych w formularzach Windows Forms, będą wyświetlane dane, co jest nazywany nadrzędne/podrzędne lub wzorzec/szczegół widoku. Odnosi się do scenariusza wiązania danych, których dane z tego samego źródła są wyświetlane w dwóch kontrolek. Zmienianie zaznaczenia w jednym formancie powoduje, że dane wyświetlane w drugiej kontrolce. Na przykład pierwszy formant może zawierać listę klientów i druga lista zamówień powiązanych z wybranym klientem w pierwszej kontrolce.  
  
 Uruchamianie przy użyciu platformy .NET Framework w wersji 2.0, podczas wyświetlania danych w widoku nadrzędne/podrzędne, które można wykonać dodatkowe czynności, aby upewnić się, ponieważ obecnie wybrany wiersz w tabeli podrzędnej nie jest resetowana do pierwszego wiersza tabeli. Aby to zrobić, trzeba będzie położenie elementów podrzędnych w tabeli w pamięci podręcznej i zresetowanie jej po zmianie tabeli nadrzędnej. Resetowanie podrzędnych występuje zwykle po raz pierwszy pól w wierszu zmian w tabeli nadrzędnej.  
  
### <a name="to-cache-the-current-child-position"></a>Buforowanie bieżące położenie elementów podrzędnych  
  
1.  Zadeklaruj zmienną całkowitoliczbową do przechowywania położenie listy elementów podrzędnych i zmiennej typu Boolean do przechowywania, czy w pamięci podręcznej położenie elementów podrzędnych.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2.  Obsługa <xref:System.Windows.Forms.CurrencyManager.ListChanged> zdarzenia dla wiązania <xref:System.Windows.Forms.CurrencyManager> i sprawdź, czy <xref:System.ComponentModel.ListChangedType> z <xref:System.ComponentModel.ListChangedType.Reset>.  
  
3.  Sprawdź bieżące położenie <xref:System.Windows.Forms.CurrencyManager>. Czy jest on większy niż pierwszy wpis na liście (zazwyczaj 0), zapisz go do zmiennej.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4.  Obsługiwać listy nadrzędnej <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> zdarzenia nadrzędnego menedżera waluty. W procedurze obsługi należy ustawić wartość logiczna wskazująca, że nie jest scenariusz buforowania. Jeśli <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> problem wystąpi, zmiany do elementu nadrzędnego jest zmiana położenia listy i nie zmieniać wartość elementu.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a>Aby zresetować położenie elementów podrzędnych  
  
1.  Obsługa <xref:System.Windows.Forms.BindingManagerBase.PositionChanged> zdarzenia podrzędnego wiązania <xref:System.Windows.Forms.CurrencyManager>.  
  
2.  Resetuj położenie elementów podrzędnych w tabeli do pamięci podręcznej pozycji zapisany w poprzedniej procedurze.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak zapisać bieżącą pozycję w <xref:System.Windows.Forms.CurrencyManager>tego tabeli podrzędnej i resetowanie położenia po zakończeniu edycji w tabeli nadrzędnej. Ten przykład zawiera dwa <xref:System.Windows.Forms.DataGridView> formanty powiązane z dwiema tabelami w <xref:System.Data.DataSet> przy użyciu <xref:System.Windows.Forms.BindingSource> składnika. Ustanowieniu relacji między dwiema tabelami, a relacja jest dodawany do <xref:System.Data.DataSet>. Pozycja w tabeli podrzędnej jest początkowo ustawiona trzeciego wiersza w celach demonstracyjnych.  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 Aby przetestować przykładowy kod, wykonaj następujące czynności:  
  
1.  Uruchom przykład.  
  
2.  Upewnij się, że **pamięci podręcznej i Resetuj położenie** pole wyboru jest zaznaczone.  
  
3.  Kliknij przycisk **pole nadrzędne wyczyść** przycisk, aby spowodować, że zmiany w tabeli nadrzędnej. Należy zauważyć, że zaznaczony wiersz w tabeli podrzędnej nie zmienia się.  
  
4.  Zamknij i ponownie uruchom przykład. Należy to zrobić, ponieważ spowoduje zachowanie resetowania tylko na pierwszej zmianie wiersza nadrzędnego.  
  
5.  Wyczyść **pamięci podręcznej i Resetuj położenie** pole wyboru.  
  
6.  Kliknij przycisk **pole nadrzędne wyczyść** przycisku. Należy zauważyć, że zaznaczony wiersz w tabeli podrzędnej zmienia się do pierwszego wiersza.  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Odwołania do zestawów systemu, dane systemowe, System.Drawing, przestrzeń nazw System.Windows.Forms i System.XML.  
  
 Aby uzyskać informacje dotyczące sposobu tworzenia tego przykładu z wiersza polecenia dla programu Visual Basic lub Visual C#, zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [wiersza polecenia tworzenia przy użyciu csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Można także utworzyć tego przykładu w programie Visual Studio, wklejając kod do nowego projektu.  Zobacz też [jak: Skompilować i uruchomić przykładowy kod pełną Windows Forms przy użyciu programu Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Zobacz także
- [Instrukcje: Upewnij się, wiele formantów powiązanych z tym samym źródłem danych pozostają zsynchronizowane](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)
- [BindingSource, składnik](../../../docs/framework/winforms/controls/bindingsource-component.md)
- [Wiązanie danych i formularzy Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
