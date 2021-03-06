---
title: Explicit — słowo kluczowe - C# odwołania
ms.custom: seodec18
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: 4949b88a32dae2a727e623bb6e4db0a4f9d8418c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557997"
---
# <a name="explicit-c-reference"></a>explicit (odwołanie w C#)

`explicit` — Słowo kluczowe deklaruje operator konwersji typu zdefiniowanego przez użytkownika, który musi być wywołana z rzutowania.

W poniższym przykładzie zdefiniowano operator, który konwertuje `Fahrenheit` klasy `Celsius` klasy. Operator musi być zdefiniowana wewnątrz `Fahrenheit` klasy lub `Celsius` klasy:

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

Operator konwersji zdefiniowanej przy użyciu rzutowania, wywołuje się, jak w poniższym przykładzie pokazano:

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

Operator konwersji konwertuje typu źródłowego na typ docelowy. Typ źródłowy zawiera operator konwersji. W odróżnieniu od niejawnej konwersji operatory konwersji jawnej musi wywołać poprzez rzutowanie. Jeśli operacji konwersji może spowodować, że wyjątki lub utratę informacji, należy go oznaczyć `explicit`. Zapobiega to dyskretnie wywoływanie operacji konwersji z prawdopodobnie nieprzewidziane skutki przez kompilator.

Pominięcie rzutowania spowoduje błąd kompilacji CS0266.

Aby uzyskać więcej informacji, zobacz [Używanie operatorów konwersji](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).

## <a name="example"></a>Przykład

W poniższym przykładzie przedstawiono `Fahrenheit` i `Celsius` klasy, z których każdy zawiera operator jawnej konwersji do innej klasy.

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a>Przykład

W poniższym przykładzie zdefiniowano struktury, `Digit`, który reprezentuje pojedynczą cyfrą dziesiętną. Operator jest zdefiniowany dla konwersji z `byte` do `Digit`, ale ponieważ nie wszystkie wartości bajtowe mogą być konwertowane na `Digit`, konwersja jest jawne.

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [implicit](implicit.md)
- [Operator (odwołanie w C#)](operator.md)
- [Instrukcje: Implementowanie zdefiniowanych przez użytkownika konwersji struktur](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
- [Tworzenie łańcucha zdefiniowanych przez użytkownika Konwersje jawne w języku C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
