---
title: BREAK, instrukcja - C# odwołania
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 18be5171329dd43c419e977a1799e2e72c32404d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727576"
---
# <a name="break-c-reference"></a>break (odwołanie w C#)

`break` Kończy się najbliższej otaczającej pętli lub [Przełącz](../../../csharp/language-reference/keywords/switch.md) instrukcji, w której występuje. Kontrola jest przekazywana do instrukcji następującej instrukcji zakończone, jeśli istnieje.

## <a name="example"></a>Przykład

W tym przykładzie instrukcji warunkowej zawiera licznik, który ma zostać liczba z zakresu od 1 do 100; jednak `break` kończy pętli po liczby 4.

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a>Przykład

W tym przykładzie `break` instrukcja jest używane do zerwać pętlę zagnieżdżonych wewnętrzną i zwraca formantu do zewnętrzna pętla.

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a>Przykład

W tym przykładzie pokazano użycie `break` w [Przełącz](../../../csharp/language-reference/keywords/switch.md) instrukcji.

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

Jeśli wprowadzono `4`, dane wyjściowe będą:

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../../../csharp/language-reference/index.md)
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)
- [Słowa kluczowe języka C#](../../../csharp/language-reference/keywords/index.md)
- [switch](../../../csharp/language-reference/keywords/switch.md)
- [Instrukcje skoku](../../../csharp/language-reference/keywords/jump-statements.md)
- [Instrukcje iteracji](../../../csharp/language-reference/keywords/iteration-statements.md)
