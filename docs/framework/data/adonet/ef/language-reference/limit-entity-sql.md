---
title: LIMIT (jednostka SQL)
ms.date: 03/30/2017
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
ms.openlocfilehash: 945aec734f7e71c2a2f24c9bb3632030cede15ec
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826304"
---
# <a name="limit-entity-sql"></a>LIMIT (jednostka SQL)
Stronicowanie fizycznych można wykonać przy użyciu Podklauzula LIMIT w klauzuli ORDER BY. OGRANICZENIE nie może służyć oddzielnie od klauzuli ORDER BY.  
  
## <a name="syntax"></a>Składnia  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a>Argumenty  
 `n`  
 Liczba elementów, które zostaną wybrane.  
  
 Jeśli LIMIT wyrażenia Podklauzula znajduje się w klauzuli ORDER BY, zapytania będą sortowane według specyfikacji sortowania i wynikowa liczba wierszy, zostanie nałożone przez wyrażenie LIMIT. Na przykład LIMIT 5 ograniczyć zestaw wyników do 5 wystąpień lub wiersze. LIMIT jest funkcjonalnym odpowiednikiem GÓRNEJ z wyjątkiem, że LIMIT wymaga klauzuli ORDER BY być obecne. POMIŃ i LIMIT może służyć niezależnie wraz z klauzuli ORDER BY.  
  
> [!NOTE]
>  Zapytanie Sql jednostki będą uznawane za nieprawidłowe w przypadku najważniejszych modyfikator i POMIŃ Podklauzula znajduje się w jednym wyrażeniu zapytania. Powinien zostać przepisany zapytania, zmieniając wyrażenia TOP i LIMIT wyrażenia.  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa operatora klauzuli ORDER BY limit, aby określić kolejność sortowania na obiekty zwrócone w instrukcji SELECT. Zapytanie jest oparty na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [jak: Wykonywanie zapytania, które zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż poniższe zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a>Zobacz także
- [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)
- [Instrukcje: Przejrzyj wyniki zapytania](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))
- [Stronicowanie](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)
- [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
