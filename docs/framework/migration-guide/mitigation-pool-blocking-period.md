---
title: 'Środki zaradcze: Pula czasu blokowania'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1021cf66c7091e699efac72fc9e614f30910398b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645109"
---
# <a name="mitigation-pool-blocking-period"></a>Środki zaradcze: Pula czasu blokowania
Blokuje czasu puli połączeń została usunięta dla połączeń z bazami danych Azure SQL.  
  
## <a name="additional-description"></a>Dodatkowy opis  
 W [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] i wcześniejszych wersjach, wtedy, gdy aplikacja napotka błąd przejściowy połączenia podczas nawiązywania połączenia z bazą danych, próba połączenia nie mogą zostać powtórzone szybko, ponieważ pula połączeń buforuje błędu i ponownie zgłasza 5 sekund do 1 min. Aby uzyskać więcej informacji, zobacz [programu SQL Server połączenia puli (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md). To zachowanie jest problematyczne dla połączeń z bazami danych Azure SQL, które często zakończona niepowodzeniem z błędami przejściowymi, które są zwykle odzyskała sprawność w ciągu kilku sekund. Funkcji blokowania w puli połączeń oznacza, że aplikacji nie można połączyć z bazą danych na okres rozbudowane nawet, jeśli baza danych jest dostępna. To zachowanie jest szczególnie problematyczny dla aplikacji sieci web, które łączą się z bazy danych Azure SQL, które muszą renderowania w ciągu kilku sekund.  
  
 Począwszy od [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], w przypadku połączenie jest otwarte żądania do znanych baz danych Azure SQL (*. database.windows.net, \*. database.chinacloudapi.cn, \*. database.usgovcloudapi.net, \*. database.cloudapi.de), Otwórz błędy połączenia nie są buforowane. Dla wszystkich innych próby nawiązania połączenia połączenia puli czasu blokowania w dalszym ciągu wymuszane.  
  
## <a name="impact"></a>Wpływ  
 Próba otwarcia połączenia należy natychmiast ponowić baz danych Azure SQL, a więc poprawa wydajności aplikacji z obsługą chmury dzięki tej zmianie.  
  
## <a name="mitigation"></a>Ograniczenie  
 Połączenia czasu blokowania puli aplikacji, które niekorzystny wpływ na tę zmianę, można skonfigurować, ustawiając nową <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> właściwości.  Wartość właściwości jest elementem członkowskim <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> wyliczenia, która może przyjąć jedną z trzech wartości:  
  
-   `PoolBlockingPeriod.AlwaysBlock` 
  
-   `PoolBlockingPeriod.Auto`  
  
-   `PoolBlockingPeriod.NeverBlock` 
  
 Można przywrócić poprzednie zachowanie przez ustawienie <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> właściwość `PoolBlockingPeriod.AlwaysBlock`.  
  
## <a name="see-also"></a>Zobacz także
- [Zmiany środowiska uruchomieniowego](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
