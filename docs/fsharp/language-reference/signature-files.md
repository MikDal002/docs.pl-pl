---
title: Pliki podpisów
description: Dowiedz się, jak używać F# plików sygnatur do przechowywania informacji na temat podpisów publicznych zbiór F# program elementy, takie jak typy, przestrzenie nazw i moduły.
ms.date: 06/15/2018
ms.openlocfilehash: 88938309a7c2bd12428f06ba8088141fd5349e80
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613417"
---
# <a name="signatures"></a>Podpisy

Plik podpisu zawiera informacje o podpisów publicznych zestawu F# program elementy, takie jak typy, przestrzenie nazw i moduły. Może służyć do określenia dostępności te elementy programu.

## <a name="remarks"></a>Uwagi

Dla każdego F# plik kodu może mieć *plik podpisu*, czyli pliku, który ma taką samą nazwę jak plik kodu, ale .fsi rozszerzenia zamiast .fs. Pliki podpisów mogą być również dodawane do kompilacji wiersza polecenia, korzystając z wiersza polecenia bezpośrednio. Aby rozróżnić plików kodu i plików sygnatur, pliki kodu są czasami określane jako *pliki wdrożenia*. W projekcie plik podpisu powinien poprzedzać skojarzony plik kodu.

Plik podpisu opisuje przestrzenie nazw, moduły, typy i elementy członkowskie w odpowiedni plik implementacji. Użyj informacji w pliku podpisu do określenia, jakie części kodu w odpowiedniej implementacji plików jest możliwy z kodu poza plikiem wdrożenia i jakie części są wewnętrzne w pliku implementacji. Przestrzenie nazw, moduły i typy, które znajdują się w pliku podpisu musi być podzestawem przestrzenie nazw, moduły i typy, które znajdują się w pliku implementacji. Z pewnymi wyjątkami, podane w dalszej części tego tematu te elementy języka, które nie są wymienione w pliku podpisu są uznawane za prywatne pliku implementacji. Jeśli plik podpisu nie zostanie znaleziony w projekcie lub w wierszu polecenia, jest używana wartość domyślna dostępu.

Aby uzyskać więcej informacji na temat ułatwień dostępu domyślne zobacz [kontroli dostępu](access-control.md).

V souboru signatury nie Powtórz definicji typów i implementacje każdej metody lub funkcji. Zamiast tego należy użyć podpis dla każdej metody i funkcji, która działa jako pełna Specyfikacja funkcji, który jest implementowany przez fragment modułu lub przestrzeni nazw. Składnia dla podpisu typu jest taki sam sposób, który jest używany w deklaracji metody abstrakcyjnej w interfejsach i klasy abstrakcyjne i jest również wyświetlany przez funkcję IntelliSense i przez F# fsi.exe interpreter gdy zostanie wyświetlona poprawnie skompilowany danych wejściowych.

Jeśli nie jest wystarczająco dużo informacji w podpisie typu, aby wskazać, czy typ jest zapieczętowany, lub czy jest ono typu interfejsu, należy dodać atrybut wskazujący rodzaj typu w kompilatorze. W poniższej tabeli opisano atrybuty, które używają do tego celu.

|Atrybut|Opis|
|---------|-----------|
|`[<Sealed>]`|Dla typu, który nie ma żadnych członków abstrakcyjnych lub że nie ma zastosowania.|
|`[<Interface>]`|Dla typu, który jest interfejsem.|

Kompilator generuje błąd, jeśli atrybuty nie są spójne podpisu i deklaracji w pliku implementacji.

Użyj słowa kluczowego `val` do tworzenia podpisu dla wartości lub wartości funkcji. Słowo kluczowe `type` wprowadza sygnatura typu.

Plik podpisu można wygenerować za pomocą `--sig` — opcja kompilatora. Ogólnie rzecz biorąc nie napiszesz .fsi pliki ręcznie. Zamiast tego należy wygenerować .fsi plików za pomocą kompilatora, dodaj je do projektu, jeśli masz i edytować je, usuwając metody i funkcje, które mają być dostępne.

Istnieje kilka reguł dla podpisy typu:

- Skróty typów w pliku z implementacją nie może odpowiadać typu bez skrótu w pliku podpisu.

- Rekordy i sumy rozłączne musi ujawniać wszystkich lub żadnej z ich pól oraz konstruktorów i zamówienia w podpisie musi być zgodna z kolejnością w pliku implementacji. Klasy może ujawnić niektóre, wszystkich lub żadnej z ich pól i metod w podpisie.

- Klasy i struktury, które mają konstruktory musi ujawniać deklaracje ich klasami podstawowymi ( `inherits` deklaracji). Ponadto klas i struktur, które mają konstruktory musi ujawniać wszystkie metody abstrakcyjne i deklaracji interfejsu.

- Typy interfejsu muszą ujawnić, wszystkie metody i interfejsy.

Reguły dla podpisów wartości są następujące:

- Modyfikatory dostępu (`public`, `internal`i tak dalej) i `inline` i `mutable` Modyfikatory w podpisie muszą odpowiadać nazwom w implementacji.

- Liczba parametrów typu ogólnego, (lub wywnioskowane niejawnie zadeklarowany w sposób jawny) muszą być zgodne, a typy i ograniczenia typów w parametrach typu ogólnego muszą być zgodne.

- Jeśli `Literal` atrybut jest używany, musi znajdować się zarówno w przypadku podpis, jak i implementację i taką samą wartość literału musi być używany dla obu.

- Wzorzec parametrów (znany także jako *specifikaci*) podpisów i implementacje muszą być zgodne.

- Jeśli nazwy parametrów w pliku podpisu różnią się od odpowiedniego pliku implementacji, nazwy w pliku podpisu zostanie użyty, co może spowodować problemy podczas debugowania lub profilowania. Jeśli chcesz otrzymywać powiadomienia o takich niezgodności, Włącz ostrzeżenie 3218 w pliku projektu lub podczas wywoływania kompilator (zobacz `--warnon` w obszarze [opcje kompilatora](compiler-options.md)).

Poniższy przykład kodu pokazuje przykład pliku podpisu, który ma przestrzeń nazw, moduł, wartości funkcji i podpisy typu wraz z odpowiednich atrybutów. Zawiera również odpowiedni plik implementacji.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9002.fs)]

Poniższy kod przedstawia plik implementacji.

[!code-fsharp[Main](../../../samples/snippets/fsharp/fssignatures/snippet9001.fs)]

## <a name="see-also"></a>Zobacz także

- [Dokumentacja języka F#](index.md)
- [Kontrola dostępu](access-control.md)
- [Opcje kompilatora](compiler-options.md)
