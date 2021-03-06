---
title: uzyskanie kontekstowego słowa kluczowego - C# odwołania
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: cfeef1d84a443163f4bbeda863682335d9cd1fcd
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222627"
---
# <a name="yield-c-reference"></a>yield (odwołanie w C#)

Kiedy używasz `yield` [kontekstowego słowa kluczowego](index.md#contextual-keywords) w instrukcji powoduje wskazanie metody, operatora lub `get` dostępu, w której występuje jest iteratorem. Za pomocą `yield` do zdefiniowania iteratora eliminuje konieczność jawnego użycia dodatkowej klasy (klasy przechowującej stan wyliczenia, zobacz <xref:System.Collections.Generic.IEnumerator%601> przykład) podczas implementacji <xref:System.Collections.IEnumerable> i <xref:System.Collections.IEnumerator> wzorca dla kolekcji niestandardowej Typ.

W poniższym przykładzie pokazano dwa rodzaje `yield` instrukcji.

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a>Uwagi

Możesz użyć `yield return` instrukcja zwraca każdy element w danym momencie.

Korzystanie z metody iteratora przy użyciu [foreach](foreach-in.md) instrukcji lub zapytania LINQ. Każda iteracja `foreach` pętli wywołuje metodę iteratora. Gdy `yield return` osiągnięciu instrukcji w metodzie iteratora `expression` jest zwracany, a bieżąca lokalizacja w kodzie jest zachowywana. Wykonanie jest uruchamiane ponownie z tej lokalizacji przy następnym wywołaniu funkcji iteratora.

Możesz użyć `yield break` instrukcję, aby zakończyć iterację.

Aby uzyskać więcej informacji dotyczących iteratorów, zobacz [Iteratory](../../iterators.md).

## <a name="iterator-methods-and-get-accessors"></a>Metody iteratorów i metody dostępu get

Deklaracja iteratora musi spełniać następujące wymagania:

- Zwracany typ musi być <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, lub <xref:System.Collections.Generic.IEnumerator%601>.

- Deklaracja nie może zawierać żadnych [w](in-parameter-modifier.md) [ref](ref.md) lub [się](out-parameter-modifier.md) parametrów.

`yield` Typ iteratora zwracającego <xref:System.Collections.IEnumerable> lub <xref:System.Collections.IEnumerator> jest `object`.  Jeśli iterator zwraca <xref:System.Collections.Generic.IEnumerable%601> lub <xref:System.Collections.Generic.IEnumerator%601>, musi istnieć niejawna konwersja z typu wyrażenia w `yield return` instrukcję, aby parametr typu ogólnego.

Nie można uwzględnić `yield return` lub `yield break` instrukcji w metodach mających następujące cechy:

- Metody anonimowe. Aby uzyskać więcej informacji, zobacz [anonimowymi](../../programming-guide/statements-expressions-operators/anonymous-methods.md).

- Metody, które zawierają bloki ze słowem kluczowym unsafe. Aby uzyskać więcej informacji, zobacz [niebezpieczne](unsafe.md).

## <a name="exception-handling"></a>Obsługa wyjątków

A `yield return` instrukcja nie może znajdować się w bloku try-catch. A `yield return` instrukcji może znajdować się w bloku try instrukcji try-finally.

A `yield break` instrukcji może znajdować się w bloku try lub bloku catch, ale nie bloku finally.

Jeśli `foreach` treści (poza metodą iteratora) zgłasza wyjątek, `finally` blokowanie w metodzie iteratora jest wykonywany.

## <a name="technical-implementation"></a>Implementacja techniczna

Poniższy kod zwraca `IEnumerable<string>` z metody iteratora i następnie iterację przez jego elementów.

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

Wywołanie `MyIteratorMethod` treści metody nie jest wykonywany. Zamiast tego to wywołanie zwraca `IEnumerable<string>` do `elements` zmiennej.

Podczas iteracji `foreach` pętli, <xref:System.Collections.IEnumerator.MoveNext%2A> metoda jest wywoływana dla `elements`. To wywołanie wykonuje treść `MyIteratorMethod` aż do następnej `yield return` osiągnięta zostanie instrukcja. Wyrażenie zwracane przez `yield return` Instrukcja określa nie tylko wartość `element` do użycia w treści pętli, ale także <xref:System.Collections.Generic.IEnumerator%601.Current%2A> właściwość `elements`, czyli `IEnumerable<string>`.

Na poszczególnych kolejnych iteracjach `foreach` pętli, wykonywanie treści iteratora jest kontynuowane od miejsca zostało przerwane, zatrzymywane ponownie po osiągnięciu `yield return` instrukcji. `foreach` Pętli jest ukończone Kiedy koniec metody iteratora lub `yield break` osiągnięta zostanie instrukcja.

## <a name="example"></a>Przykład

W poniższym przykładzie przedstawiono `yield return` instrukcji, która znajduje się wewnątrz `for` pętli. Każda iteracja `foreach` treść instrukcji w `Main` metoda tworzy wywołanie `Power` funkcji iteratora. Każde wywołanie funkcji iteratora przechodzi do następnego wykonania `yield return` instrukcję, która występuje w ciągu następnej iteracji `for` pętli.

Zwracany typ metody iteratora jest <xref:System.Collections.IEnumerable>, który jest typem interfejsu iteratora. Kiedy metoda iteratora jest wywoływana, zwraca obiekt wyliczeniowy, który zawiera potęgi liczb.

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano `get` metodę dostępu, która jest iteratorem. W tym przykładzie każdy `yield return` instrukcja zwraca wystąpienie klasy zdefiniowanej przez użytkownika.

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../../language-reference/index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [foreach, in](foreach-in.md)
- [Iteratory](../../iterators.md)