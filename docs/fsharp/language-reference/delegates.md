---
title: Delegaty
description: Dowiedz się, jak pracować z delegatów w F#.
ms.date: 05/16/2016
ms.openlocfilehash: 772685488b7caef92123979d817929c631248afb
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612897"
---
# <a name="delegates"></a>Delegaty

Obiekt delegowany reprezentuje wywołanie funkcji jako obiekt. W F#, zazwyczaj należy używać wartości funkcji do reprezentowania funkcje jako wartości pierwszej klasy. Jednak obiekty delegowane są używane w programie .NET Framework i dlatego są wymagane podczas współdziałania z interfejsami API, które ich wymagają. One może również służyć podczas tworzenia bibliotek przeznaczone do użycia z innych językach .NET Framework.

## <a name="syntax"></a>Składnia

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>Uwagi

W poprzedniej składni `type1` reprezentuje argument typu lub typów i `type2` reprezentuje typ zwracany. Typy argumentów, które są reprezentowane przez `type1` są automatycznie przenoszeni. Sugeruje to, że dla tego typu, możesz użyć formularzu krotki, jeśli są przenoszeni argumentów funkcji docelowej i krotki ujęty w nawiasy dla argumentów, które już znajdują się w formularzu krotki. Automatyczne currying usuwa zestaw nawiasów, pozostawiając argument spójnej kolekcji, który pasuje do metody docelowej. Zobacz przykład kodu dla składni, do którego należy używać w każdym przypadku.

Delegaty mogą być dołączane do F# funkcji wartości i statyczne lub wystąpienie metody. F#wartości funkcji mogą być przekazywane bezpośrednio jako argumenty do delegowanie konstruktorów. W przypadku statycznej metody delegata konstruowania przy użyciu nazwy klasy i metody. Dla metody wystąpienia możesz podać wystąpienie obiektu i metody w jeden argument. W obu przypadkach należy uzyskać dostęp — operator (`.`) jest używany.

`Invoke` Metody na typ delegata wywołania zhermetyzowanych funkcji. Ponadto delegatów mogą być przekazywane jako wartości funkcji, odwołując się do nazwy metody Invoke, bez nawiasów.

Poniższy kod przedstawia składnię utworzenie obiektów delegowanych, które reprezentują różne metody w klasie. W zależności od tego, czy metoda jest metodą statyczną lub metodą wystąpienia oraz czy ma argumentów w formularzu krotki lub formularzu rozwinięte składnia do deklarowania i przypisywanie delegata jest nieco inny.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

Poniższy kod przedstawia niektóre różne sposoby korzystania z obiektów delegowanych.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

Dane wyjściowe w poprzednim przykładzie kodu jest w następujący sposób.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka F#](index.md)
- [Parametry i argumenty](parameters-and-arguments.md)
- [Zdarzenia](members/events.md)