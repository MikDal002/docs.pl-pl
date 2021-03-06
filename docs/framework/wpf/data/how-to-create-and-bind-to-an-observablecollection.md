---
title: 'Instrukcje: Utwórz i powiąż z ObservableCollection'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: cf9f714878cd1b0b179dc1ced44e3dcfe7c2f9bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517594"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>Instrukcje: Utwórz i powiąż z ObservableCollection
W tym przykładzie pokazano, jak utworzyć i powiązać z kolekcji, która pochodzi od klasy <xref:System.Collections.ObjectModel.ObservableCollection%601> klasy, która jest klasą kolekcji, która zapewnia powiadomienia, gdy elementy Pobierz dodane lub usunięte.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano implementację `NameList` kolekcji:  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 Można udostępnić w kolekcji ten sam sposób, w jaki z innymi powiązania [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] obiekty, zgodnie z opisem w [wprowadzić dostępne dane do powiązania w XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md). Na przykład można utworzyć wystąpienie kolekcji w [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] i określ kolekcję zasobów, jak pokazano poniżej:  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 Następnie możesz powiązać do kolekcji:  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 Definicja `NameItemTemplate` nie został tutaj pokazany.  
  
> [!NOTE]
>  Obiekty w kolekcji musi spełniać wymagania opisane w [Przegląd wiązanie źródeł](../../../../docs/framework/wpf/data/binding-sources-overview.md). W szczególności jeśli używasz <xref:System.Windows.Data.BindingMode.OneWay> lub <xref:System.Windows.Data.BindingMode.TwoWay> (na przykład, chcesz, aby Twoje [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aktualizacji podczas dynamicznie zmieniać właściwości źródła), musisz zaimplementować mechanizm powiadamiania odpowiednie zmiany właściwości, takie jak <xref:System.ComponentModel.INotifyPropertyChanged>interfejsu.  
  
 Aby uzyskać więcej informacji, zobacz powiązania w sekcji kolekcje [Przegląd wiązanie danych](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
## <a name="see-also"></a>Zobacz także
- [Sortowanie danych w widoku](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [Filtrowanie danych w widoku](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [Sortowanie i grupowanie danych przy użyciu widoku w XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Powiązanie danych — omówienie](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Tematy z instrukcjami](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
