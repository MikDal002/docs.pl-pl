---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 4d0bed2fb000e96e9fd0ceac6ea90e19b8fa7514
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554858"
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
Łączy dwa `Boolean` wyrażenia.  
  
## <a name="syntax"></a>Składnia  
  
```  
boolean_expression OR boolean_expression  
or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>Argumenty  
 `boolean_expression`  
 Dowolne prawidłowe wyrażenie, które zwraca `Boolean`.  
  
## <a name="return-value"></a>Wartość zwracana  
 `true` gdy jeden z warunków jest `true`; w przeciwnym razie `false`.  
  
## <a name="remarks"></a>Uwagi  
 LUB [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatora logicznego. Służy do łączenia dwóch warunków. Gdy więcej niż jeden operator jest używany w instrukcji, lub operatory są obliczane po operatorach i. Można jednak zmienić kolejność obliczania, za pomocą nawiasów.  
  
 Podwójne pionowych słupków (&#124;&#124;) mają taką samą funkcjonalność jak OR operator.  
  
 W poniższej tabeli przedstawiono możliwe wartości wejściowych i zwracanych typów.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|WARTOŚĆ TRUE|WARTOŚĆ TRUE|WARTOŚĆ TRUE|  
|`FALSE`|WARTOŚĆ TRUE|FAŁSZ|NULL|  
|`NULL`|WARTOŚĆ TRUE|NULL|NULL|  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa operatora OR połączyć dwa `Boolean` wyrażenia. Zapytanie jest oparty na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [jak: Wykonywanie zapytania, które zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż poniższe zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#OR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#or)]  
  
## <a name="see-also"></a>Zobacz także
- [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
