---
title: Łączenie ze źródłem danych w ADO.NET
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 20cf22e1c9b9bf18dd3109cb9589c05a6c27d4d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701745"
---
# <a name="connecting-to-a-data-source-in-adonet"></a>Łączenie ze źródłem danych w ADO.NET
W ADO.NET **połączenia** obiekt, aby połączyć się z określonym źródłem danych, podając niezbędne informacje dotyczące uwierzytelniania w parametrach połączenia. **Połączenia** obiektu użyjesz zależy od typu źródła danych.  
  
 Każdego dostawcy danych .NET Framework, dołączone do programu .NET Framework ma <xref:System.Data.Common.DbConnection> obiektu: .NET Framework Data Provider for OLE DB zawiera <xref:System.Data.OleDb.OleDbConnection> obiektu .NET Framework Data Provider for SQL Server zawiera <xref:System.Data.SqlClient.SqlConnection> obiektu. NET Framework Data Provider for ODBC obejmuje <xref:System.Data.Odbc.OdbcConnection> obiektu i .NET Framework Data Provider for Oracle obejmuje <xref:System.Data.OracleClient.OracleConnection> obiektu.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Nawiązywanie połączenia](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 Opisuje sposób używania **połączenia** obiektów do nawiązania połączenia ze źródłem danych.  
  
 [Zdarzenia połączenia](../../../../docs/framework/data/adonet/connection-events.md)  
 Opisuje sposób używania **InfoMessage** zdarzenie, aby pobrać komunikaty informacyjne ze źródła danych.  
  
## <a name="see-also"></a>Zobacz także
- [Parametry połączeń](../../../../docs/framework/data/adonet/connection-strings.md)
- [Pula połączeń](../../../../docs/framework/data/adonet/connection-pooling.md)
- [Polecenia i parametry](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [Elementy DataAdapter i DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [Transakcje i współbieżność](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [ADO.NET zarządzanego dostawcy i Centrum deweloperów zestawu danych](https://go.microsoft.com/fwlink/?LinkId=217917)
