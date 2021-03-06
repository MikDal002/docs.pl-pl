---
title: Konstruowanie typów (jednostka SQL)
ms.date: 03/30/2017
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
ms.openlocfilehash: 917c59a6602ce0313b91ba78fd59d11596f86e9f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718588"
---
# <a name="constructing-types-entity-sql"></a>Konstruowanie typów (jednostka SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] zawiera trzy rodzaje konstruktorów: wiersz konstruktorów, typu nazwanego konstruktorów i konstruktorów kolekcji.  
  
## <a name="row-constructors"></a>Konstruktory wiersza  
 Użyj wiersza konstruktorów w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] do konstruowania anonimowe, strukturalnie wpisane rekordy z co najmniej jedną wartość. Typ wyniku w Konstruktorze wierszy jest typu wiersza, w których typy pól odpowiadają typy wartości używane do konstruowania wiersza. Na przykład poniższe wyrażenie tworzy wartość typu `Record(a int, b string, c int)`:  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 Jeśli nie podasz alias wyrażenia w Konstruktorze wierszy, platformy Entity Framework podejmie próbę go wygeneruje. Aby uzyskać więcej informacji, zobacz sekcję "Zasady aliasowania" w [identyfikatory](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md).  
  
 Następujące reguły stosuje się do wyrażenia aliasów w Konstruktorze wierszy:  
  
-   Wyrażenia w Konstruktorze row nie może odwoływać się do innych aliasów w tej samej konstruktora.  
  
-   Dwóch wyrażeń w tym samym Konstruktor row nie może mieć takiego samego aliasu.  
  
 Aby uzyskać więcej informacji na temat konstruktory wiersz zobacz [wiersza](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## <a name="collection-constructors"></a>Konstruktory kolekcji  
 Możesz użyć kolekcji konstruktorów w [!INCLUDE[esql](../../../../../../includes/esql-md.md)] do utworzenia wystąpienia zestawu wielokrotnego z listy wartości. Wszystkie wartości w Konstruktorze musi być typu wzajemnie zgodne `T`, i Konstruktor tworzy kolekcję typu `Multiset<T>`. Na przykład poniższe wyrażenie tworzy kolekcję liczb całkowitych:  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 Pusty zestaw wielokrotny konstruktory nie są dozwolone, ponieważ nie można określić typ elementów. Poniżej jest nieprawidłowa:  
  
 `multiset() {}`  
  
 Aby uzyskać więcej informacji, zobacz [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md).  
  
## <a name="named-type-constructors-namedtype-initializers"></a>Typ nazwany, konstruktory (NamedType inicjatory)  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Umożliwia konstruktorów typu (inicjatory), aby tworzyć wystąpienia nazwane typy złożone i typy jednostek. Na przykład poniższe wyrażenie tworzy wystąpienie `Person` typu.  
  
 `Person("abc", 12)`  
  
 Poniższe wyrażenie tworzy wystąpienie typu złożonego.  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 Poniższe wyrażenie tworzy wystąpienie zagnieżdżonego typu złożonego.  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 Poniższe wyrażenie tworzy wystąpienie jednostki przy użyciu zagnieżdżonych typu złożonego.  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 Poniższy przykład pokazuje, jak zainicjować właściwość typu złożonego do wartości null. `MyModel.ZipCode(‘98118’, null)`  
  
 Argumenty konstruktora są rozpatrywane w tej samej kolejności, jak deklaracja atrybuty typu.  
  
 Aby uzyskać więcej informacji, zobacz [konstruktora typu o nazwie](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md).  
  
## <a name="see-also"></a>Zobacz także
- [Odwołanie do jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Omówienie jednostki SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [System typów](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)
