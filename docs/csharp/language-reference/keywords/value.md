---
title: kontekstowe słowo kluczowe wartości - C# odwołania
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: ee80888a57e999fa44e891dd6e0d64caa698009c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612065"
---
# <a name="value-c-reference"></a>value (odwołanie w C#)

Kontekstowe słowo kluczowe `value` jest używany w metodzie dostępu set w deklaracji właściwości zwykłych. Jest on podobny do parametru wejściowego metody. Wyraz `value` odwołuje się do wartości, które podejmuje próbę przypisania do właściwości kodu klienta. W poniższym przykładzie `MyDerivedClass` ma właściwość o nazwie `Name` , który używa `value` parametru, aby przypisać nowy ciąg do pola pomocniczego `name`. Z punktu widzenia kodu klienta operacji jest zapisywany jako przypisanie proste.

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

Aby uzyskać więcej informacji na temat użytkowania `value`, zobacz [właściwości](../../programming-guide/classes-and-structs/properties.md).

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)