---
title: BindingSource — Informacje o składniku
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- controls [Windows Forms], binding to data
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: be838caf-fcb0-4b68-827f-58b2c04b747f
ms.openlocfilehash: 6fbd089cef6f014979cf8bbdf376b2f76ac9bcf9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686950"
---
# <a name="bindingsource-component-overview"></a>BindingSource — Informacje o składniku
<xref:System.Windows.Forms.BindingSource> Składnik jest tak zaprojektowany, aby uprościć proces powiązywanie kontrolek z bazowego źródła danych. <xref:System.Windows.Forms.BindingSource> Składnika działa jako kanał i źródła danych dla innych kontrolek, które można powiązać. Udostępnia abstrakcję połączenie danych formularza podczas przekazywania za pomocą poleceń do bazowego wykaz danych. Ponadto można dodać danych bezpośrednio do niego, tak aby sam składnik działa jako źródło danych.  
  
## <a name="bindingsource-component-as-an-intermediary"></a>BindingSource, składnik jako pośrednik  
 <xref:System.Windows.Forms.BindingSource> Składnika działa jako źródło danych dla niektórych lub wszystkich kontrolek w formularzu. W programie Visual Studio <xref:System.Windows.Forms.BindingSource> może być powiązana z kontrolką poprzez `DataBindings` właściwość, która jest dostępna z **właściwości** okna. Zobacz też [jak: Powiązywanie kontrolek formularzy Windows ze składnikiem BindingSource przy użyciu narzędzia Projektant](../../../../docs/framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md).  
  
 Możesz powiązać <xref:System.Windows.Forms.BindingSource> składnik do obu źródeł danych proste, jak w pojedynczej właściwości obiektu lub kolekcji podstawowych, takich jak <xref:System.Collections.ArrayList>i źródeł danych złożonych, takich jak tabela bazy danych. <xref:System.Windows.Forms.BindingSource> Składnika działa jako pośrednik, który zapewnia usługi zarządzania wiązanie i waluty. W czasie projektowania lub w czasie wykonywania można powiązać <xref:System.Windows.Forms.BindingSource> składnika ze źródłem danych złożonych, ustawiając jego <xref:System.Windows.Forms.BindingSource.DataSource%2A> i <xref:System.Windows.Forms.BindingSource.DataMember%2A> właściwości do bazy danych i tabeli, odpowiednio. Poniższa ilustracja przedstawia gdzie <xref:System.Windows.Forms.BindingSource> składnika dopasowuje się do istniejącej architektury powiązanie danych.  
  
 ![Powiązanie źródła i architektura powiązań danych](../../../../docs/framework/winforms/controls/media/net-bindsrcdatabindarch.gif "NET_BindSrcDataBindArch")  
  
> [!NOTE]
>  W czasie projektowania, utworzy pewne akcje, takie jak przeciągnięcie tabeli bazy danych z okna dane na pusty formularz <xref:System.Windows.Forms.BindingSource> składnika powiązać bazowego źródła danych i dodawanie kontrolek obsługujących dane łącznie w jednej operacji. Zobacz też [formanty powiązania formularzy Windows do danych w programie Visual Studio](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio).  
  
## <a name="bindingsource-component-as-a-data-source"></a>BindingSource, składnik jako źródło danych  
 Jeśli rozpoczniesz Dodawanie elementów do <xref:System.Windows.Forms.BindingSource> składnika bez określenia listy może być powiązane z składnik będzie zachowywać się jak źródło danych styl listy i zaakceptować te dodane elementy.  
  
 Ponadto, można napisać kod do dostarczają niestandardowych funkcjonalności "Działają funkcje AddNew" poprzez <xref:System.Windows.Forms.BindingSource.AddingNew> zdarzenie, które jest wywołane, gdy <xref:System.Windows.Forms.BindingSource.AddNew%2A> metoda jest wywoływana przed element dodawany do listy. Aby uzyskać więcej informacji, zobacz [architektura składnika BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-architecture.md).  
  
## <a name="navigation"></a>Nawigacja  
 Dla użytkowników, którzy muszą nawigowanie po danych w formularzu <xref:System.Windows.Forms.BindingNavigator> składnika umożliwia nawigowanie i manipulowanie danymi w połączeniu z <xref:System.Windows.Forms.BindingSource> składnika. Aby uzyskać więcej informacji, zobacz [BindingNavigator — kontrolka](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md).  
  
## <a name="data-manipulation"></a>Manipulowanie danymi  
 : <xref:System.Windows.Forms.BindingSource> Działa jako <xref:System.Windows.Forms.CurrencyManager> wszystkie jej powiązań i może, w związku z tym, zapewniają dostęp do waluty i pozycji informacji o źródle danych. W poniższej tabeli przedstawiono elementy członkowskie <xref:System.Windows.Forms.BindingSource> składnik udostępnia do uzyskiwania dostępu i manipulowania danych bazowych.  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Current%2A> Właściwość|Pobiera bieżący element źródła danych.|  
|<xref:System.Windows.Forms.BindingSource.Position%2A> Właściwość|Pobiera lub ustawia bieżącą pozycję na liście podstawowej.|  
|<xref:System.Windows.Forms.BindingSource.List%2A> Właściwość|Pobiera listę, która jest ocena <xref:System.Windows.Forms.BindingSource.DataSource%2A> i <xref:System.Windows.Forms.BindingSource.DataMember%2A> oceny. Jeśli <xref:System.Windows.Forms.BindingSource.DataMember%2A> nie jest ustawiona, zwraca listę, określony przez <xref:System.Windows.Forms.BindingSource.DataSource%2A>.|  
|<xref:System.Windows.Forms.BindingSource.Insert%2A> — Metoda|Wstawia element na liście pod określonym indeksem.|  
|<xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> — Metoda|Usuwa bieżący element z listy.|  
|<xref:System.Windows.Forms.BindingSource.EndEdit%2A> — Metoda|Ma zastosowanie oczekujących zmian do bazowego źródła danych.|  
|<xref:System.Windows.Forms.BindingSource.CancelEdit%2A> — Metoda|Anuluje bieżącą operację edycji.|  
|<xref:System.Windows.Forms.BindingSource.AddNew%2A> — Metoda|Dodaje nowy element do listy źródłowej. Jeśli źródło danych implementuje <xref:System.ComponentModel.IBindingList> i zwraca element <xref:System.Windows.Forms.BindingSource.AddingNew> zdarzenie dodaje ten element. W przeciwnym razie żądanie jest przekazywane do listy <xref:System.ComponentModel.IBindingList.AddNew%2A> metody. Jeśli nie jest podstawowa lista <xref:System.ComponentModel.IBindingList>, element jest tworzone automatycznie za pomocą jego publicznego konstruktora domyślnego.|  
  
## <a name="sorting-and-filtering"></a>sortowanie i filtrowanie  
 Zazwyczaj powinien współpracować z uporządkowane lub filtrowane widok źródła danych. W poniższej tabeli przedstawiono elementy członkowskie <xref:System.Windows.Forms.BindingSource> zawiera składnik źródła danych.  
  
|Element członkowski|Opis|  
|------------|-----------------|  
|<xref:System.Windows.Forms.BindingSource.Sort%2A> Właściwość|Jeśli źródło danych jest <xref:System.ComponentModel.IBindingList>, pobiera lub ustawia nazwę kolumny, używane do sortowania i informacje o kolejności sortowania. Jeśli źródło danych jest <xref:System.ComponentModel.IBindingListView> i obsługuje zaawansowane, sortowanie, pobiera wiele nazw kolumn, używane do sortowania i informacje o kolejności sortowania|  
|<xref:System.Windows.Forms.BindingSource.Filter%2A> Właściwość|Jeśli źródło danych jest <xref:System.ComponentModel.IBindingListView>, pobiera lub ustawia wyrażenie używane do filtrowania, które wiersze są wyświetlane.|  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [BindingSource, składnik — architektura](../../../../docs/framework/winforms/controls/bindingsource-component-architecture.md)
- [BindingSource, składnik](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [BindingNavigator, kontrolka](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)
- [Wiązanie danych formularzy Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [Kontrolki do użycia w formularzach Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
