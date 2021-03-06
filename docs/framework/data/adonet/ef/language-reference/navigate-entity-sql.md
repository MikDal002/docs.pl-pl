---
title: Przejdź (jednostka SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: e66a09276f40ab6d9ff7c11bb160385b4c1efb48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542564"
---
# <a name="navigate-entity-sql"></a>Przejdź (jednostka SQL)
Przechodzi przez relację między jednostkami.  
  
## <a name="syntax"></a>Składnia  
  
```  
navigate(instance-expresssion, [relationship-type], [to-end [, from-end] ])  
```  
  
## <a name="arguments"></a>Argumenty  
 `instance-expresssion`  
 Wystąpienie jednostki.  
  
 `relationship-type`  
 Nazwa typu relacji z pliku (CSDL) języka definicji schematu koncepcyjnego. `relationship-type` Jest kwalifikowana jako \<przestrzeni nazw >.\< Nazwa typu relacji >.  
  
 `to`  
 Zakończenie relacji.  
  
 `from`  
 Początek relacji.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli kardynalność do końca wynosi 1, zwracaną wartością będzie `Ref<T>`. Jeśli kardynalność do końca n, zwracaną wartością będzie `Collection<Ref<T>>`.  
  
## <a name="remarks"></a>Uwagi  
 Relacje są konstrukcje najwyższej jakości w [!INCLUDE[adonet_edm](../../../../../../includes/adonet-edm-md.md)] (EDM struktury). Można ustanowić relacji między co najmniej dwóch typów jednostek, a użytkownicy mogą uzyskać dostęp za pośrednictwem relacji z jednej strony (jednostka) do innego. `from` i `to` są warunkowo opcjonalne, jeśli nie ma żadnych niejednoznaczności w rozpoznawanie w relacji.  
  
 Nawigacja jest prawidłowa w przestrzeni O i C.  
  
 Ogólna postać konstrukcję nawigacji jest następująca:  
  
 Przejdź (`instance-expresssion`, `relationship-type`, [ `to-end` [, `from-end` ]])  
  
 Na przykład:  
  
```  
Select o.Id, navigate(o, OrderCustomer, Customer, Order)  
From LOB.Orders as o  
```  
  
 Gdzie jest OrderCustomer `relationship`, i klienta i zamówienia są `to-end` (klienta) i `from-end` (zamówienie) relacji. Jeśli OrderCustomer została relacji n: 1, a typ wyniku wyrażenie navigate jest Ref\<klienta >.  
  
 Prostsze formularza to wyrażenie jest następująca:  
  
```  
Select o.Id, navigate(o, OrderCustomer)  
From LOB.Orders as o  
```  
  
 Podobnie w zapytaniu o następującej postaci wyrażenie navigate dałby w efekcie kolekcji < Ref\<kolejności >>.  
  
```  
Select c.Id, navigate(c, OrderCustomer, Order, Customer)  
From LOB.Customers as c  
```  
  
 Wyrażenia wystąpienia musi być typem jednostki/ref.  
  
## <a name="example"></a>Przykład  
 Następujące zapytanie SQL jednostki używa operatora przejdź do nawigacji w relacji między adres i SalesOrderHeader typów jednostek. Zapytanie jest oparty na modelu sprzedaży AdventureWorks. Aby skompilować i uruchomić to zapytanie, wykonaj następujące kroki:  
  
1.  Postępuj zgodnie z procedurą w [jak: Wykonywanie zapytania, które zwraca wyniki StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Przekaż poniższe zapytanie jako argument do `ExecuteStructuralTypeQuery` metody:  
  
 [!code-csharp[DP EntityServices Concepts 2#NAVIGATE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#navigate)]  
  
## <a name="see-also"></a>Zobacz także
- [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Instrukcje: Przejdź relacjach za pomocą operatora nawigowania](../../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)
