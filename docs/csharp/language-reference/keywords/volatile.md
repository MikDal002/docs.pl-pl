---
title: volatile — C# odwołania
ms.custom: seodec18
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: e523f7b25e28b41030edd4dc86a1fa144e961950
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758303"
---
# <a name="volatile-c-reference"></a>volatile (odwołanie w C#)

`volatile` — Słowo kluczowe wskazuje, że pola mogą zostać zmodyfikowane przez wiele wątków, które są wykonywane w tym samym czasie. Kompilator, system plików środowiska uruchomieniowego i sprzętu może zmienić kolejność operacji odczytu i zapisu do lokalizacji pamięci, ze względu na wydajność. Pola, które są zadeklarowane `volatile` nie podlegają Optymalizacje te. Dodawanie `volatile` modyfikator gwarantuje, że wszystkie wątki będzie przestrzegać volatile zapisów wykonywane przez inny wątek, w kolejności, w którym zostały wykonane. Nie ma żadnej gwarancji, pojedynczy całkowita kolejności volatile zapisów wyświetlanego ze wszystkich wątków wykonania.

`volatile` — Słowo kluczowe mogą być stosowane do pól z następujących typów:

- Typy odwołań.
- Typy wskaźników (w niebezpiecznym kontekście). Należy pamiętać, że chociaż wskaźnika, sama może być nietrwałe, obiekt, który wskazuje nie może. Innymi słowy nie można zadeklarować "wskaźnik volatile."
- Proste typy, takie jak `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float`, i `bool`.
- `enum` Typu z jednym z następujących typów podstawowych: `byte`, `sbyte`, `short`, `ushort`, `int`, lub `uint`.
- Parametry typu ogólnego, znane jako typy odwołań.
- <xref:System.IntPtr> i <xref:System.UIntPtr>.

Inne typy, w tym `double` i `long`, nie można oznaczyć `volatile` ponieważ odczyty i zapisy do pól z tych typów, nie można zagwarantować niepodzielnych. Aby chronić wielowątkowych dostęp do tych typów pól, użyj <xref:System.Threading.Interlocked> elementy członkowskie klasy lub ochrona dostępu przy użyciu [ `lock` ](lock-statement.md) instrukcji.

`volatile` — Słowo kluczowe może być stosowany tylko do pól `class` lub `struct`. Nie można zadeklarować zmienne lokalne `volatile`.

## <a name="example"></a>Przykład

Poniższy przykład pokazuje sposób deklarowania zmiennej pole publiczne `volatile`.

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

Poniższy przykład pokazuje, jak wątek wiadomości pomocniczych lub procesu roboczego można tworzyć i używany do wykonywania przetwarzania równolegle z wątku głównego. Aby uzyskać więcej informacji o wielowątkowości, zobacz [zarządzana wątkowość](../../../standard/threading/index.md).

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

Za pomocą `volatile` modyfikator dodane do deklaracji `_shouldStop` w miejscu, zawsze uzyskasz takie same wyniki (podobnie jak fragment, jak pokazano w poprzednim kodzie). Jednak bez ten modyfikator na `_shouldStop` elementu członkowskiego, zachowanie jest nieprzewidywalne. `DoWork` Metoda może zoptymalizować dostęp do elementu członkowskiego, wynikiem odczytywanie nieaktualnych danych. Ze względu na charakter programowania wielowątkowe liczba odczytów starych jest nieprzewidywalne. Różnych tras program generuje wyniki nieco inny.

## <a name="c-language-specification"></a>specyfikacja języka C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Zobacz także

- [C#Specyfikacja języka: volatile — słowo kluczowe](../../../../_csharplang/spec/classes.md#volatile-fields)
- [Dokumentacja języka C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](index.md)
- [Modyfikatory](modifiers.md)
- [instrukcji "Lock"](lock-statement.md)
- <xref:System.Threading.Interlocked>