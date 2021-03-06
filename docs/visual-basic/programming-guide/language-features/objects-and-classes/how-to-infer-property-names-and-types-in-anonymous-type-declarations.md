---
title: 'Instrukcje: Wnioskowanie nazw właściwości i typów w deklaracjach typu anonimowego (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 67cc9e85d249365a7b4b7636c99766087314622d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54596865"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a>Instrukcje: Wnioskowanie nazw właściwości i typów w deklaracjach typu anonimowego (Visual Basic)
Typy anonimowe zapewniają żaden mechanizm służący bezpośrednio określać typy danych właściwości. Typy wszystkich właściwości są wnioskowane. W poniższym przykładzie typy `Name` i `Price` są dedukowane bezpośrednio z wartości, które są używane do ich inicjowania.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_1.vb)]  
  
 Typy anonimowe można również wnioskowanie nazw właściwości i typów z innych źródeł. Sekcje zawierają listę okoliczności, w którym możliwe jest wnioskowania i przykłady sytuacji, gdy nie jest.  
  
## <a name="successful-inference"></a>Pomyślne wnioskowania  
  
#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a>Typy anonimowe można wnioskowanie nazw właściwości i typów z następujących źródeł:  
  
-   W nazwach zmiennych. Typ anonimowy `anonProduct` będzie mieć dwie właściwości `productName` i `productPrice`. Typy danych będą identyczne ze zmiennych oryginalnego `String` i `Double`, odpowiednio.  
  
     [!code-vb[VbVbalrAnonymousTypes#11](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_2.vb)]  
  
-   Właściwość lub pole nazw innych obiektów. Na przykład, rozważmy `car` obiektu `CarClass` typ, który zawiera `Name` i `ID` właściwości. Aby utworzyć nowe wystąpienie typu anonimowego `car1`, za pomocą `Name` i `ID` właściwości, które są inicjowane z wartościami z `car` obiektu, można napisać następujące czynności:  
  
     [!code-vb[VbVbalrAnonymousTypes#34](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_3.vb)]  
  
     Poprzednie deklaracja jest równoważna dłużej wiersz kodu, który definiuje typ anonimowy `car2`.  
  
     [!code-vb[VbVbalrAnonymousTypes#35](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_4.vb)]  
  
-   Od nazw składowych XML.  
  
     [!code-vb[VbVbalrAnonymousTypes#12](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_5.vb)]  
  
     Wynikowy typ `anon` miałby jedną właściwość `Book`, typu <xref:System.Collections.IEnumerable>(z XElement).  
  
-   Z funkcji, która nie ma parametrów, takich jak `SomeFunction` w poniższym przykładzie.  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     Zmienna `anon2` w poniższym kodzie jest typ anonimowy, który ma jedną właściwość, znakiem o nazwie `First`. Ten kod wyświetli się literą "E", list, który jest zwracany przez funkcję <xref:System.Linq.Enumerable.First%2A>.  
  
     [!code-vb[VbVbalrAnonymousTypes#13](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_6.vb)]  
  
## <a name="inference-failures"></a>Błędy wnioskowania  
  
#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a>Wnioskowanie o nazwie zakończy się niepowodzeniem w wielu sytuacjach, w tym następujące:  
  
-   Wnioskowanie pochodzi z wywołania metody, Konstruktor lub właściwości sparametryzowane, która wymaga argumentów. Poprzednia deklaracja elementu `anon1` zakończy się niepowodzeniem, jeśli `someFunction` ma jeden lub więcej argumentów.  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     Przypisanie do nowej nazwy właściwości rozwiązuje problem.  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   Wnioskowanie pochodzi ze złożonego wyrażenia.  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     Ten błąd można rozwiązać, przypisując wynik wyrażenia do nazwy właściwości.  
  
     [!code-vb[VbVbalrAnonymousTypes#14](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_7.vb)]  
  
-   Wnioskowanie o wiele właściwości tworzy dwa lub więcej właściwości, które mają taką samą nazwę. Przywołujący deklaracji w wcześniejszych przykładów, nie możesz wyświetlać listy zarówno `product.Name` i `car1.Name` jako właściwości tego samego typu anonimowego. Jest to spowodowane wywnioskowane identyfikator dla każdego z nich będzie `Name`.  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     Problem można rozwiązać przez przypisywanie wartości do nazw różne właściwości.  
  
     [!code-vb[VbVbalrAnonymousTypes#36](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_8.vb)]  
  
     Pamiętaj, że zmiany w przypadku, gdy (zmiany między wielkie i małe litery) nie należy wprowadzać nazwy dwóch odrębnych.  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   Początkowa typu i wartości jedną właściwość zależy od innej właściwości, która nie jest jeszcze nawiązane. Na przykład `.IDName = .LastName` nie jest prawidłowy w deklaracji typu anonimowego, chyba że `.LastName` jest już zainicjowany.  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     W tym przykładzie można rozwiązać problem, odwracając kolejność, w którym są zadeklarowane właściwości.  
  
     [!code-vb[VbVbalrAnonymousTypes#15](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_9.vb)]  
  
-   Nazwa właściwości typu anonimowego jest taka sama jak nazwa składowej <xref:System.Object>. Na przykład następująca deklaracja nie powiedzie się, ponieważ `Equals` to metoda <xref:System.Object>.  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     Aby naprawić ten problem, należy zmienić nazwy właściwości:  
  
     [!code-vb[VbVbalrAnonymousTypes#16](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_10.vb)]  
  
## <a name="see-also"></a>Zobacz także
- [Inicjatory obiektów: Typy nazwane i anonimowe](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Wnioskowanie o typie lokalnym](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Typy anonimowe](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
