---
title: System Functions
ms.date: 03/30/2017
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
ms.openlocfilehash: 9ab9298214813e7dd3af31f224d84a00040fbf01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597414"
---
# <a name="system-functions"></a>System Functions
.NET Framework Data Provider for SQL Server (SqlClient) udostępnia następujące funkcje systemu:  
  
|Funkcja|Opis|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Zwraca wartość sumy kontrolnej. `CHECKSUM` jest przeznaczony do użycia podczas tworzenia indeksów skrótu.<br /><br /> **Argumenty**<br /><br /> `value`: A `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `String`, `Binary`, lub `Guid`. Można określić wartości jeden, dwa lub trzy.<br /><br /> **Wartość zwracana**<br /><br /> Wartość bezwzględna z określonego wyrażenia.<br /><br /> **Przykład**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Generuje bieżącą datę i godzinę w formacie wewnętrznych programu SQL Server dla `DateTime` wartości z dokładnością do 7 w programie SQL Server 2008 i dokładność 3 w programie SQL Server 2005.<br /><br /> **Wartość zwracana**<br /><br /> Bieżącej systemowej daty i godziny jako `DateTime`.<br /><br /> **Przykład**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER``()`|Zwraca nazwę bieżącego użytkownika.<br /><br /> **Wartość zwracana**<br /><br /> An ASCII `String`.<br /><br /> **Przykład**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Zwraca liczbę bajtów reprezentujących dowolne wyrażenie.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, lub `Guid`.<br /><br /> **Wartość zwracana**<br /><br /> Rozmiar właściwości `Int32`.<br /><br /> **Przykład**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Zwraca nazwę stacji roboczej.<br /><br /> **Wartość zwracana**<br /><br /> Unicode `String`.<br /><br /> **Przykład**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Określa, czy wyrażenie wejściowe jest prawidłową datą.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, lub `Guid`.<br /><br /> **Wartość zwracana**<br /><br /> `Int32`. Jeden (1) Jeśli wyrażenie danych wejściowych jest prawidłową datą. Zero (0) w przeciwnym razie.<br /><br /> **Przykład**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Określa, czy wyrażenie jest prawidłowy typ liczbowy.<br /><br /> **Argumenty**<br /><br /> `expression`: A `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, lub `Guid`.<br /><br /> **Wartość zwracana**<br /><br /> `Int32`. Jeden (1) Jeśli wyrażenie danych wejściowych jest prawidłową datą. Zero (0) w przeciwnym razie.<br /><br /> **Przykład**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Tworzy wartość Unikatowy identyfikator Guid typu.<br /><br /> **Wartość zwracana**<br /><br /> A `Guid`.<br /><br /> **Przykład**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Zwraca numer identyfikacyjny określony nazwa użytkownika bazy danych.<br /><br /> **Argumenty**<br /><br /> `expression`: `Int32` Numeru identyfikacyjnego skojarzonych z użytkownikiem bazy danych.<br /><br /> **Wartość zwracana**<br /><br /> Unicode `String`.<br /><br /> **Przykład**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Aby uzyskać więcej informacji o funkcjach ciągu, które obsługuje klient SQL zobacz dokumentację dla używanej wersji programu SQL Server określonego w manifeście dostawcy SqlClient:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[System Functions Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115918)|[System Functions Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115917)|[System Functions (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115919)|  
  
## <a name="see-also"></a>Zobacz także
- [Jednostki języka SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [Klient SQL dla funkcji programu Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
