---
title: Wzorce aktywne (F#)
description: "Dowiedz się, jak użyć aktywne wzorce, aby zdefiniować nazwany partycji, które należy podzielić danych wejściowych w języku programowania w języku F #."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 11a724ff-f9ff-4056-b5e0-87e9ed986f4a
ms.openlocfilehash: 845184e6150cf0b93393038ca3d39f0e6d898a2e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2017
---
# <a name="active-patterns"></a><span data-ttu-id="d4aa0-104">Wzorce aktywne</span><span class="sxs-lookup"><span data-stu-id="d4aa0-104">Active Patterns</span></span>

<span data-ttu-id="d4aa0-105">*Wzorce aktywne* umożliwiają zdefiniowanie nazwanego partycji, które należy podzielić danych wejściowych, dzięki czemu można używać tych nazw we wzorcu zgodnego z wyrażeniem, tak jak w przypadku Unii rozłącznej.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-105">*Active patterns* enable you to define named partitions that subdivide input data, so that you can use these names in a pattern matching expression just as you would for a discriminated union.</span></span> <span data-ttu-id="d4aa0-106">Wzorce aktywne umożliwia dekompozycji danych w sposób dostosowany dla każdej partycji.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-106">You can use active patterns to decompose data in a customized manner for each partition.</span></span>


## <a name="syntax"></a><span data-ttu-id="d4aa0-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="d4aa0-107">Syntax</span></span>

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a><span data-ttu-id="d4aa0-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d4aa0-108">Remarks</span></span>
<span data-ttu-id="d4aa0-109">W poprzednich składni identyfikatory są nazwy partycji danych wejściowych, która jest reprezentowana przez *argumenty*, lub innymi słowy, nazwy dla podzbiorów zestawu wszystkie wartości argumentów.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-109">In the previous syntax, the identifiers are names for partitions of the input data that is represented by *arguments*, or, in other words, names for subsets of the set of all values of the arguments.</span></span> <span data-ttu-id="d4aa0-110">W definicji — aktywny wzorzec może być do siedmiu partycji.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-110">There can be up to seven partitions in an active pattern definition.</span></span> <span data-ttu-id="d4aa0-111">*Wyrażenie* opisuje formularza, do którego próba dekompozycji danych.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-111">The *expression* describes the form into which to decompose the data.</span></span> <span data-ttu-id="d4aa0-112">Definicja — aktywny wzorzec umożliwia definiowanie zasady określające, który partycji o nazwie wartości podanej jako argumenty należą do.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-112">You can use an active pattern definition to define the rules for determining which of the named partitions the values given as arguments belong to.</span></span> <span data-ttu-id="d4aa0-113">(| A |) symbole są określane jako *klipy bananów* i została wywołana funkcja utworzone przez tego typu powiązania let *aktywny aparat rozpoznawania*.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-113">The (| and |) symbols are referred to as *banana clips* and the function created by this type of let binding is called an *active recognizer*.</span></span>

<span data-ttu-id="d4aa0-114">Na przykład należy wziąć pod uwagę następujące aktywny wzorzec z nieprawidłowym argumentem.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-114">As an example, consider the following active pattern with an argument.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

<span data-ttu-id="d4aa0-115">Aktywny wzorzec można użyć we wzorcu zgodnego wyrażeniem, jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-115">You can use the active pattern in a pattern matching expression, as in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

<span data-ttu-id="d4aa0-116">Dane wyjściowe tego programu jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-116">The output of this program is as follows:</span></span>

```
7 is odd
11 is odd
32 is even
```

<span data-ttu-id="d4aa0-117">Inny użycie aktywne wzorce jest próba dekompozycji typy danych na wiele sposobów, na przykład w przypadku tych samych danych różne reprezentacje możliwe.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-117">Another use of active patterns is to decompose data types in multiple ways, such as when the same underlying data has various possible representations.</span></span> <span data-ttu-id="d4aa0-118">Na przykład `Color` obiektu może być rozłożone na reprezentacja RGB lub reprezentacja HSB.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-118">For example, a `Color` object could be decomposed into an RGB representation or an HSB representation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

<span data-ttu-id="d4aa0-119">Dane wyjściowe programu powyżej jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-119">The output of the above program is as follows:</span></span>

```
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

<span data-ttu-id="d4aa0-120">W połączeniu sposobów przy użyciu aktywne wzorce pozwala na partycji i Rozłóż dane na odpowiednie formularza i wykonaj odpowiednią obliczenia na odpowiednie dane w postaci najbardziej odpowiednim obliczenia.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-120">In combination, these two ways of using active patterns enable you to partition and decompose data into just the appropriate form and perform the appropriate computations on the appropriate data in the form most convenient for the computation.</span></span>

<span data-ttu-id="d4aa0-121">Wyrażenia dopasowania wzorca wynikowe Włącz dane są zapisywane w wygodny sposób, który jest bardzo do odczytu, znacznie uproszczenie rozgałęzianie złożonych i kod analizy danych.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-121">The resulting pattern matching expressions enable data to be written in a convenient way that is very readable, greatly simplifying potentially complex branching and data analysis code.</span></span>


## <a name="partial-active-patterns"></a><span data-ttu-id="d4aa0-122">Częściowe aktywne wzorce</span><span class="sxs-lookup"><span data-stu-id="d4aa0-122">Partial Active Patterns</span></span>
<span data-ttu-id="d4aa0-123">Czasami trzeba tylko część obszaru wejściowego podzielić na partycje.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-123">Sometimes, you need to partition only part of the input space.</span></span> <span data-ttu-id="d4aa0-124">W takim przypadku zestaw z częściowa wzorców zapisu w sytuacji, z których zgodne niektórych danych wejściowych, ale nie pasuje do innych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-124">In that case, you write a set of partial patterns each of which match some inputs but fail to match other inputs.</span></span> <span data-ttu-id="d4aa0-125">Wzorce aktywne, które nie zawsze utworzyć wartość są nazywane *częściowe aktywne wzorce*; mają wartości zwracanej, który jest typem opcji.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-125">Active patterns that do not always produce a value are called *partial active patterns*; they have a return value that is an option type.</span></span> <span data-ttu-id="d4aa0-126">Aby zdefiniować częściowe aktywny wzorzec, należy użyć symbolu wieloznacznego (_) na końcu listy wzorców wewnątrz klipy bananów.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-126">To define a partial active pattern, you use a wildcard character (_) at the end of the list of patterns inside the banana clips.</span></span> <span data-ttu-id="d4aa0-127">Poniższy kod ilustruje korzystanie z częściowa aktywny wzorzec.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-127">The following code illustrates the use of a partial active pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

<span data-ttu-id="d4aa0-128">Dane wyjściowe w poprzednim przykładzie ma następującą składnię:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-128">The output of the previous example is as follows:</span></span>

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

<span data-ttu-id="d4aa0-129">Korzystając z częściowa aktywne wzorce, czasami poszczególnych opcji mogą być rozłączne lub wykluczają się wzajemnie, ale nie muszą być.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-129">When using partial active patterns, sometimes the individual choices can be disjoint or mutually exclusive, but they need not be.</span></span> <span data-ttu-id="d4aa0-130">W poniższym przykładzie kwadratowe wzorzec i wzorzec modułu nie są rozłączne, ponieważ niektóre liczby są kwadratów i modułów, takich jak 64.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-130">In the following example, the pattern Square and the pattern Cube are not disjoint, because some numbers are both squares and cubes, such as 64.</span></span> <span data-ttu-id="d4aa0-131">Następujący program drukowania wszystkich liczb całkowitych do 1000000 zarówno kwadratów i modułów.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-131">The following program prints out all integers up to 1000000 that are both squares and cubes.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

<span data-ttu-id="d4aa0-132">Wynik jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-132">The output is as follows:</span></span>

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a><span data-ttu-id="d4aa0-133">Wzorce aktywne sparametryzowane</span><span class="sxs-lookup"><span data-stu-id="d4aa0-133">Parameterized Active Patterns</span></span>
<span data-ttu-id="d4aa0-134">Wzorce aktywne zawsze wykonać co najmniej jednego argumentu dla elementu filtrowanego, ale potrwać również dodatkowe argumenty w takim przypadku nazwa *sparametryzowane — aktywny wzorzec* ma zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-134">Active patterns always take at least one argument for the item being matched, but they may take additional arguments as well, in which case the name *parameterized active pattern* applies.</span></span> <span data-ttu-id="d4aa0-135">Zezwalaj na dodatkowe argumenty ogólne wzorzec być specjalizowany.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-135">Additional arguments allow a general pattern to be specialized.</span></span> <span data-ttu-id="d4aa0-136">Wzorce aktywne, które często analizowanie ciągów za pomocą wyrażeń regularnych zawierają na przykład wyrażenia regularnego jako dodatkowy parametr, zgodnie z poniższym kodem, który także używa częściowe aktywny wzorzec `Integer` zdefiniowane w poprzednim przykładzie kodu.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-136">For example, active patterns that use regular expressions to parse strings often include the regular expression as an extra parameter, as in the following code, which also uses the partial active pattern `Integer` defined in the previous code example.</span></span> <span data-ttu-id="d4aa0-137">W tym przykładzie Aby dostosować ogólny ParseRegex — aktywny wzorzec podane są ciągów, które używają wyrażeń regularnych dla różnych formatów daty.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-137">In this example, strings that use regular expressions for various date formats are given to customize the general ParseRegex active pattern.</span></span> <span data-ttu-id="d4aa0-138">Liczba całkowita — aktywny wzorzec jest używana do konwertowania podciągów do liczb całkowitych, które mogą zostać przekazane do konstruktora elementu DateTime.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-138">The Integer active pattern is used to convert the matched strings into integers that can be passed to the DateTime constructor.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

<span data-ttu-id="d4aa0-139">Dane wyjściowe poprzedniego kodu jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-139">The output of the previous code is as follows:</span></span>

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

<span data-ttu-id="d4aa0-140">Aktywne wzorce nie są ograniczone tylko do wzorca dopasowania wyrażenia, można również użyć na let — powiązania.</span><span class="sxs-lookup"><span data-stu-id="d4aa0-140">Active patterns are not restricted only to pattern matching expressions, you can also use them on let-bindings.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

<span data-ttu-id="d4aa0-141">Dane wyjściowe poprzedniego kodu jest następujący:</span><span class="sxs-lookup"><span data-stu-id="d4aa0-141">The output of the previous code is as follows:</span></span>

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a><span data-ttu-id="d4aa0-142">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d4aa0-142">See Also</span></span>
[<span data-ttu-id="d4aa0-143">Dokumentacja języka F #</span><span class="sxs-lookup"><span data-stu-id="d4aa0-143">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="d4aa0-144">Wyrażenia dopasowania</span><span class="sxs-lookup"><span data-stu-id="d4aa0-144">Match Expressions</span></span>](match-expressions.md)
