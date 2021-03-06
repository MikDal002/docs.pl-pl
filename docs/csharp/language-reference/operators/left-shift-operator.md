---
title: << operator - C# odwołania
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: 0271c97bc624a8946b90508e9ce39d217a128c05
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261753"
---
# <a name="-operator-c-reference"></a>\<\< Operator (odwołanie w C#)

Operator przesunięcia w lewo (`<<`) pierwszy argument operacji lewo o liczbę bitów określoną przez drugim argumentem operacji przesunięcia. Typ drugiego argumentu operacji musi być [int](../keywords/int.md) lub typ, który ma wstępnie zdefiniowanych niejawnej konwersji liczbowych do `int`.

## <a name="remarks"></a>Uwagi

Jeśli pierwszy argument jest [int](../keywords/int.md) lub [uint](../keywords/uint.md) (32-bitowy), licznik przesunięć oblicza niskiego rzędu pięć bitów drugiego operandu. Licznik przesunięć rzeczywistego jest bitów 0 do 31.

Jeśli pierwszy argument jest [długie](../keywords/long.md) lub [ulong](../keywords/ulong.md) (64-bitowy), licznik przesunięć oblicza mniej znaczące bity sześć, drugi operand. Licznik przesunięć rzeczywistego jest 0, 63 bity.

Wszystkie bity wyższego rzędu, które są nie w zakresie typem pierwszego operandu po zmiany zostaną odrzucone i mniej znaczące bity puste są wypełnione przez zera. Operacje przesunięcia nigdy nie powodują przepełnienia.

Typy zdefiniowane przez użytkownika może doprowadzić do przeciążenia `<<` — operator (zobacz [operator](../keywords/operator.md)); typ pierwszy operand musi być typu zdefiniowanego przez użytkownika, a typ drugiego argumentu operacji musi być `int`. Gdy jest przeciążony operator binarny, odpowiedniego operatora przypisania, jest również niejawnie przeciążona.

## <a name="example"></a>Przykład

[!code-csharp[csRefOperators#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#14)]

## <a name="comments"></a>Komentarze

Należy pamiętać, że `i<<1` i `i<<33` dają taki sam efekt, ponieważ 1 i 33 mają ten sam mniej znaczące bity pięć.

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Operatory języka C#](index.md)
