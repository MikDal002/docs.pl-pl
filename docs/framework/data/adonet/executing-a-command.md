---
title: Wykonywanie polecenia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 40494916-c25a-4cb8-8f7c-fcb8d378464e
ms.openlocfilehash: 4081558f9ea6a1bc258ab4cbebe6c2f72ee2c60c
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/08/2019
ms.locfileid: "55903383"
---
# <a name="executing-a-command"></a>Wykonywanie polecenia
Każdego dostawcy danych .NET Framework, dołączone do programu .NET Framework ma swój własny obiekt polecenia, która dziedziczy <xref:System.Data.Common.DbCommand>. .NET Framework Data Provider for OLE DB zawiera <xref:System.Data.OleDb.OleDbCommand> obiektu .NET Framework Data Provider for SQL Server zawiera <xref:System.Data.SqlClient.SqlCommand> obiektu .NET Framework Data Provider for ODBC obejmuje <xref:System.Data.Odbc.OdbcCommand> obiektu i .NET Framework Data Provider Pro Oracle obejmuje <xref:System.Data.OracleClient.OracleCommand> obiektu. Każda z tych obiektów udostępnia metody wykonywania poleceń na podstawie typu polecenia, a żądane zwracanej wartości, zgodnie z opisem w poniższej tabeli.  
  
|Polecenie|Wartość zwracana|  
|-------------|------------------|  
|`ExecuteReader`|Zwraca `DataReader` obiektu.|  
|`ExecuteScalar`|Zwraca pojedynczą wartość skalarną.|  
|`ExecuteNonQuery`|Wykonuje polecenie, która nie zwraca żadnych wierszy.|  
|`ExecuteXMLReader`|Zwraca <xref:System.Xml.XmlReader>. Dostępne dla `SqlCommand` tylko obiekt.|  
  
 Każdy obiekt polecenia silnie typizowaną obsługuje również <xref:System.Data.CommandType> wyliczenie, które określa, jak ciąg polecenia jest interpretowany, zgodnie z opisem w poniższej tabeli.  
  
|CommandType|Opis|  
|-----------------|-----------------|  
|`Text`|Polecenie SQL definiujący instrukcje mają być wykonane w źródle danych.|  
|`StoredProcedure`|Nazwa procedury składowanej. Możesz użyć `Parameters` właściwości polecenia dostęp do parametrów wejściowych i wyjściowych i wartości zwracane, niezależnie od tego, który `Execute` metoda jest wywoływana. Korzystając z `ExecuteReader`, wartości zwracane i parametry wyjściowe nie będą dostępne do momentu `DataReader` jest zamknięty.|  
|`TableDirect`|Nazwa tabeli.|  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu demonstruje sposób tworzenia <xref:System.Data.SqlClient.SqlCommand> obiekt, aby wykonać procedurę składowaną przez ustawienie jego właściwości. A <xref:System.Data.SqlClient.SqlParameter> obiekt jest używany do określenia parametru wejściowego procedury składowanej. Polecenie jest wykonywane przy użyciu <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> metoda i dane wyjściowe z <xref:System.Data.SqlClient.SqlDataReader> są wyświetlane w oknie konsoli.  
  
 [!code-csharp[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.StoredProcedure#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.StoredProcedure/VB/source.vb#1)]  
  
### <a name="troubleshooting-commands"></a>Rozwiązywanie problemów z poleceń  
 .NET Framework Data Provider for SQL Server dodaje liczniki wydajności, aby umożliwić wykrywanie sporadyczne problemy związane z wykonania polecenia nie powiodło się. Aby uzyskać więcej informacji, zobacz [liczniki wydajności](../../../../docs/framework/data/adonet/performance-counters.md).  
  
## <a name="see-also"></a>Zobacz także
- [Polecenia i parametry](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Elementy DataAdapter i DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Omówienie ADO.NET](ado-net-overview.md)
