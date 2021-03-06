---
title: 'Instrukcje: Powiązanie obiektu widoku danych do formantu DataGridView formularzy Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: e2e8cad453311035332e5a397667835f047184b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548368"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>Instrukcje: Powiązanie obiektu widoku danych do formantu DataGridView formularzy Windows
<xref:System.Windows.Forms.DataGridView> Kontrola zapewnia wydajny i elastyczny sposób wyświetlania danych w formacie tabelarycznym. <xref:System.Windows.Forms.DataGridView> Kontrolka obsługuje standardowe model powiązanie danych formularzy Windows, więc tworzy powiązanie <xref:System.Data.DataView> i wielu innych źródeł danych. W większości sytuacji, jednak użytkownik zostanie z nim powiązane <xref:System.Windows.Forms.BindingSource> składnik, który będzie zarządzać szczegółowe informacje o interakcji ze źródłem danych.  
  
 Aby uzyskać więcej informacji na temat <xref:System.Windows.Forms.DataGridView> sterowania, zobacz [— informacje o formancie DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>Aby nawiązać formantu DataGridView elementu DataView  
  
1.  Implementuje metodę do obsługi Szczegóły pobierania danych z bazy danych. Poniższy kod implementuje przykład `GetData` metodę, która inicjuje <xref:System.Data.SqlClient.SqlDataAdapter> składnika i używa ich do wypełnienia <xref:System.Data.DataSet>. Pamiętaj ustawić `connectionString` zmiennej na wartość, która jest odpowiednia dla bazy danych. Dostęp do serwera, należy za pomocą przykładowej bazie AdventureWorks programu SQL Server zainstalowane.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2.  W <xref:System.Windows.Forms.Form.Load> programu obsługi zdarzeń z formularza, należy powiązać <xref:System.Windows.Forms.DataGridView> kontrolę <xref:System.Windows.Forms.BindingSource> składnika i wywołania `GetData` metodę, aby pobrać dane z bazy danych. <xref:System.Data.DataView> Jest tworzona na podstawie [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] zapytanie dotyczące kontaktu <xref:System.Data.DataTable> , a następnie jest powiązany z <xref:System.Windows.Forms.BindingSource> składnika.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>Zobacz także
- [Powiązanie danych i LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
