---
title: '- (Odjąć) (Jednostka SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: aa179f65dbbf1f411fd137a759bb37efbdd1fb48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494070"
---
# <a name="--subtract-entity-sql"></a>-(Odejmowanie) (jednostka SQL)
Odejmuje dwie liczby.  
  
## <a name="syntax"></a>Składnia  
  
```  
expression - expression  
```  
  
## <a name="arguments"></a>Argumenty  
 `expression`  
 Dowolne prawidłowe wyrażenie jeden z typów liczbowych.  
  
## <a name="result-types"></a>Typy wyników  
 Typ danych będącą wynikiem promocji niejawnego typu dwa argumenty. Aby uzyskać więcej informacji na temat podwyższania poziomu konwersjom typu niejawnego, zobacz [System typów](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa operatora arytmetycznego na potrzeby odejmowania dwóch liczb. Zapytanie jest oparty na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [jak: Wykonywanie zapytania, które zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż poniższe zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#SUBTRACT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#subtract)]  
  
## <a name="see-also"></a>Zobacz także
- [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
