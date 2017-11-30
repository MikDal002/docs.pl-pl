---
title: "Moduły (F#)"
description: "Dowiedz się, jak to grupa kodzie języka F #, takie jak wartości, typu i wartości funkcji w programie F # w module języka F #."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 46de2d18-da51-40fa-a262-92edecada79d
ms.openlocfilehash: 89401c1f889be6c5585a302e3a7ac62478573b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="modules"></a><span data-ttu-id="a082e-104">Moduły</span><span class="sxs-lookup"><span data-stu-id="a082e-104">Modules</span></span>

<span data-ttu-id="a082e-105">W kontekście języka F # *modułu* to grupa kodzie języka F #, takie jak wartości, typu i wartości funkcji w programie F #.</span><span class="sxs-lookup"><span data-stu-id="a082e-105">In the context of the F# language, a *module* is a grouping of F# code, such as values, types, and function values, in an F# program.</span></span> <span data-ttu-id="a082e-106">Grupowanie kodu w modułach pomaga zachować kodu powiązanego ze sobą oraz uniknąć konfliktów nazw w programie.</span><span class="sxs-lookup"><span data-stu-id="a082e-106">Grouping code in modules helps keep related code together and helps avoid name conflicts in your program.</span></span>

## <a name="syntax"></a><span data-ttu-id="a082e-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="a082e-107">Syntax</span></span>

```fsharp
// Top-level module declaration.
module [accessibility-modifier] [qualified-namespace.]module-name
declarations
// Local module declaration.
module [accessibility-modifier] module-name =
    declarations
```

## <a name="remarks"></a><span data-ttu-id="a082e-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a082e-108">Remarks</span></span>
<span data-ttu-id="a082e-109">Moduł F # to grupa F # konstrukcji kodu typów, wartości, wartości funkcji i kodu w `do` powiązania.</span><span class="sxs-lookup"><span data-stu-id="a082e-109">An F# module is a grouping of F# code constructs such as types, values, function values, and code in `do` bindings.</span></span> <span data-ttu-id="a082e-110">Są one zaimplementowane jako wspólnego języka środowiska uruchomieniowego (języka wspólnego CLR) klasy z tylko statyczne elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="a082e-110">It is implemented as a common language runtime (CLR) class that has only static members.</span></span> <span data-ttu-id="a082e-111">Istnieją dwa typy deklaracji modułu, w zależności od tego, czy cały plik znajduje się w module: deklaracji najwyższego poziomu modułu i deklaracji modułu lokalnego.</span><span class="sxs-lookup"><span data-stu-id="a082e-111">There are two types of module declarations, depending on whether the whole file is included in the module: a top-level module declaration and a local module declaration.</span></span> <span data-ttu-id="a082e-112">Deklaracji najwyższego poziomu modułu obejmuje cały plik w module.</span><span class="sxs-lookup"><span data-stu-id="a082e-112">A top-level module declaration includes the whole file in the module.</span></span> <span data-ttu-id="a082e-113">Deklaracji najwyższego poziomu modułu może występować tylko jako pierwszej deklaracji w pliku.</span><span class="sxs-lookup"><span data-stu-id="a082e-113">A top-level module declaration can appear only as the first declaration in a file.</span></span>

<span data-ttu-id="a082e-114">W składni dla deklaracji najwyższego poziomu modułu opcjonalny *kwalifikowanych nazw* sekwencję nazwy zagnieżdżonych w przestrzeni nazw, które zawiera moduł.</span><span class="sxs-lookup"><span data-stu-id="a082e-114">In the syntax for the top-level module declaration, the optional *qualified-namespace* is the sequence of nested namespace names that contains the module.</span></span> <span data-ttu-id="a082e-115">Kwalifikowana przestrzeni nazw ma zostać poprzednio zadeklarowana.</span><span class="sxs-lookup"><span data-stu-id="a082e-115">The qualified namespace does not have to be previously declared.</span></span>

<span data-ttu-id="a082e-116">Nie masz wcięcie deklaracji najwyższego poziomu modułu.</span><span class="sxs-lookup"><span data-stu-id="a082e-116">You do not have to indent declarations in a top-level module.</span></span> <span data-ttu-id="a082e-117">Masz wcięcie wszystkimi deklaracjami w modułach lokalnych.</span><span class="sxs-lookup"><span data-stu-id="a082e-117">You do have to indent all declarations in local modules.</span></span> <span data-ttu-id="a082e-118">W deklaracji lokalnej modułu deklaracji, które wcięta w tej deklaracji modułu są częścią tego modułu.</span><span class="sxs-lookup"><span data-stu-id="a082e-118">In a local module declaration, only the declarations that are indented under that module declaration are part of the module.</span></span>

<span data-ttu-id="a082e-119">Plik kodu nie zaczyna się od deklaracji najwyższego poziomu modułu lub deklaracja przestrzeni nazw, całą zawartość pliku, w tym wszystkie moduły lokalne staje się częścią modułu najwyższego poziomu niejawnie tworzonych, który ma taką samą nazwę jak pliku bez rozszerzenia, z pierwszej litery przekonwertowany na wielkie litery.</span><span class="sxs-lookup"><span data-stu-id="a082e-119">If a code file does not begin with a top-level module declaration or a namespace declaration, the whole contents of the file, including any local modules, becomes part of an implicitly created top-level module that has the same name as the file, without the extension, with the first letter converted to uppercase.</span></span> <span data-ttu-id="a082e-120">Rozważmy na przykład następujący plik.</span><span class="sxs-lookup"><span data-stu-id="a082e-120">For example, consider the following file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6601.fs)]

<span data-ttu-id="a082e-121">Ten plik będzie można skompilować tak, jakby zostały zapisane w ten sposób:</span><span class="sxs-lookup"><span data-stu-id="a082e-121">This file would be compiled as if it were written in this manner:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6602.fs)]

<span data-ttu-id="a082e-122">Jeśli masz wiele modułów w pliku, należy użyć deklaracji modułu lokalnego dla każdego modułu.</span><span class="sxs-lookup"><span data-stu-id="a082e-122">If you have multiple modules in a file, you must use a local module declaration for each module.</span></span> <span data-ttu-id="a082e-123">Zadeklarowana otaczającej przestrzeni nazw te moduły są częścią otaczającej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="a082e-123">If an enclosing namespace is declared, these modules are part of the enclosing namespace.</span></span> <span data-ttu-id="a082e-124">Jeśli otaczającej przestrzeni nazw nie jest zadeklarowana, moduły stać się częścią tego modułu najwyższego poziomu niejawnie tworzonych.</span><span class="sxs-lookup"><span data-stu-id="a082e-124">If an enclosing namespace is not declared, the modules become part of the implicitly created top-level module.</span></span> <span data-ttu-id="a082e-125">Poniższy przykładowy kod przedstawia plik kodu, który zawiera wiele modułów.</span><span class="sxs-lookup"><span data-stu-id="a082e-125">The following code example shows a code file that contains multiple modules.</span></span> <span data-ttu-id="a082e-126">Kompilator niejawnie tworzy moduł najwyższego poziomu o nazwie `Multiplemodules`, i `MyModule1` i `MyModule2` są zagnieżdżone w module najwyższego poziomu.</span><span class="sxs-lookup"><span data-stu-id="a082e-126">The compiler implicitly creates a top-level module named `Multiplemodules`, and `MyModule1` and `MyModule2` are nested in that top-level module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6603.fs)]

<span data-ttu-id="a082e-127">Jeśli masz wiele plików w projekcie lub w jednej kompilacji lub jeśli tworzysz biblioteki, musi zawierać deklaracji przestrzeni nazw lub modułu deklaracji w górnej części pliku.</span><span class="sxs-lookup"><span data-stu-id="a082e-127">If you have multiple files in a project or in a single compilation, or if you are building a library, you must include a namespace declaration or module declaration at the top of the file.</span></span> <span data-ttu-id="a082e-128">Kompilator języka F # tylko Określa nazwę modułu niejawnie gdy istnieje tylko jeden plik w projekcie lub kompilacji wiersza polecenia, w przypadku tworzenia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a082e-128">The F# compiler only determines a module name implicitly when there is only one file in a project or compilation command line, and you are creating an application.</span></span>

<span data-ttu-id="a082e-129">*Modyfikator dostępności* może być jedną z następujących czynności: `public`, `private`, `internal`.</span><span class="sxs-lookup"><span data-stu-id="a082e-129">The *accessibility-modifier* can be one of the following: `public`, `private`, `internal`.</span></span> <span data-ttu-id="a082e-130">Aby uzyskać więcej informacji, zobacz [kontroli dostępu](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="a082e-130">For more information, see [Access Control](access-control.md).</span></span> <span data-ttu-id="a082e-131">Wartość domyślna jest publiczny.</span><span class="sxs-lookup"><span data-stu-id="a082e-131">The default is public.</span></span>


## <a name="referencing-code-in-modules"></a><span data-ttu-id="a082e-132">Odwołanie do kodu w modułach</span><span class="sxs-lookup"><span data-stu-id="a082e-132">Referencing Code in Modules</span></span>
<span data-ttu-id="a082e-133">Podając odniesienie funkcje, typy i wartości z innego modułu, możesz za pomocą nazwy kwalifikowanej lub otworzyć modułu.</span><span class="sxs-lookup"><span data-stu-id="a082e-133">When you reference functions, types, and values from another module, you must either use a qualified name or open the module.</span></span> <span data-ttu-id="a082e-134">Użycie nazwy kwalifikowanej, należy określić przestrzenie nazw, modułu oraz identyfikatora elementu programu, który ma.</span><span class="sxs-lookup"><span data-stu-id="a082e-134">If you use a qualified name, you must specify the namespaces, the module, and the identifier for the program element you want.</span></span> <span data-ttu-id="a082e-135">W następujący sposób oddzielić każdej części kwalifikowana ścieżka się kropką (.).</span><span class="sxs-lookup"><span data-stu-id="a082e-135">You separate each part of the qualified path with a dot (.), as follows.</span></span>

`Namespace1.Namespace2.ModuleName.Identifier`

<span data-ttu-id="a082e-136">Można otworzyć modułu lub co najmniej jeden z przestrzeni nazw w celu uproszczenia kodu.</span><span class="sxs-lookup"><span data-stu-id="a082e-136">You can open the module or one or more of the namespaces to simplify the code.</span></span> <span data-ttu-id="a082e-137">Aby uzyskać więcej informacji na temat otwierania przestrzeni nazw i modułów, zobacz [deklaracje importowania: `open` — słowo kluczowe](import-declarations-the-open-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="a082e-137">For more information about opening namespaces and modules, see [Import Declarations: The `open` Keyword](import-declarations-the-open-keyword.md).</span></span>

<span data-ttu-id="a082e-138">Poniższy przykład kodu pokazuje najwyższego poziomu modułu zawierającego wszystkie kod do końca pliku.</span><span class="sxs-lookup"><span data-stu-id="a082e-138">The following code example shows a top-level module that contains all the code up to the end of the file.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6604.fs)]

<span data-ttu-id="a082e-139">Aby użyć tego kodu z innego pliku w tym samym projekcie, albo użyć nazwy kwalifikowane lub można otworzyć modułu przed użyciem funkcji, jak pokazano w poniższych przykładach.</span><span class="sxs-lookup"><span data-stu-id="a082e-139">To use this code from another file in the same project, you either use qualified names or you open the module before you use the functions, as shown in the following examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6605.fs)]

## <a name="nested-modules"></a><span data-ttu-id="a082e-140">Zagnieżdżone modułów</span><span class="sxs-lookup"><span data-stu-id="a082e-140">Nested Modules</span></span>
<span data-ttu-id="a082e-141">Moduły mogą być zagnieżdżone.</span><span class="sxs-lookup"><span data-stu-id="a082e-141">Modules can be nested.</span></span> <span data-ttu-id="a082e-142">Wewnętrzne moduły muszą wcięty miarę deklaracje zewnętrzne modułu wskazuje, że są wewnętrzne moduły nie nowych modułów.</span><span class="sxs-lookup"><span data-stu-id="a082e-142">Inner modules must be indented as far as outer module declarations to indicate that they are inner modules, not new modules.</span></span> <span data-ttu-id="a082e-143">Na przykład porównać dwa poniższe przykłady.</span><span class="sxs-lookup"><span data-stu-id="a082e-143">For example, compare the following two examples.</span></span> <span data-ttu-id="a082e-144">Moduł `Z` jest wewnętrzny moduł w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="a082e-144">Module `Z` is an inner module in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6607.fs)]

<span data-ttu-id="a082e-145">Moduł `Z` jest elementem równorzędnym do modułu `Y` w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="a082e-145">But module `Z` is a sibling to module `Y` in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6608.fs)]
<span data-ttu-id="a082e-146">Moduł `Z` jest również moduł równorzędne w poniższym kodzie, ponieważ nie jest wcięty zależnie od innych deklaracji w module `Y`.</span><span class="sxs-lookup"><span data-stu-id="a082e-146">Module `Z` is also a sibling module in the following code, because it is not indented as far as other declarations in module `Y`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6609.fs)]
<span data-ttu-id="a082e-147">Na koniec zewnętrznego modułu ma nie deklaracje i od razu następuje innej deklaracji modułu, nowe oświadczenie modułu zakłada, że moduł wewnętrzny, ale kompilator wyświetli ostrzeżenie, jeśli drugi definicji modułu nie jest wcięty farther niż pierwszy.</span><span class="sxs-lookup"><span data-stu-id="a082e-147">Finally, if the outer module has no declarations and is followed immediately by another module declaration, the new module declaration is assumed to be an inner module, but the compiler will warn you if the second module definition is not indented farther than the first.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6610.fs)]
<span data-ttu-id="a082e-148">Aby usunąć to ostrzeżenie, wcięcie wewnętrzny moduł.</span><span class="sxs-lookup"><span data-stu-id="a082e-148">To eliminate the warning, indent the inner module.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6611.fs)]
<span data-ttu-id="a082e-149">Jeśli mają cały kod w pliku w jednym modułu zewnętrznego, a wewnętrzny modułów, zewnętrznego modułu nie wymaga znaku równości i deklaracje, łącznie z wszelkimi deklaracjami wewnętrzny moduł, które przechodzą w module zewnętrznym bez wcięcia.</span><span class="sxs-lookup"><span data-stu-id="a082e-149">If you want all the code in a file to be in a single outer module and you want inner modules, the outer module does not require the equal sign, and the declarations, including any inner module declarations, that will go in the outer module do not have to be indented.</span></span> <span data-ttu-id="a082e-150">Deklaracje wewnątrz deklaracji wewnętrzny moduł musi być wcięta.</span><span class="sxs-lookup"><span data-stu-id="a082e-150">Declarations inside the inner module declarations do have to be indented.</span></span> <span data-ttu-id="a082e-151">Poniższy kod przedstawia przypadek.</span><span class="sxs-lookup"><span data-stu-id="a082e-151">The following code shows this case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/modules/snippet6612.fs)]

## <a name="module-rec-allowing-mutual-recursive-code-at-the-module-level"></a><span data-ttu-id="a082e-152">Moduł `rec`: stosowanie kodu cykliczne wzajemnego na poziomie modułu</span><span class="sxs-lookup"><span data-stu-id="a082e-152">Module `rec`: allowing mutual recursive code at the module level</span></span>

<span data-ttu-id="a082e-153">F # 4.1 wprowadzono pojęcie modułów, które umożliwia się wzajemnie rekursywne wszystkich zawartych w niej kodu.</span><span class="sxs-lookup"><span data-stu-id="a082e-153">F# 4.1 introduces the notion of modules which allow for all contained code to be mutually recursive.</span></span>  <span data-ttu-id="a082e-154">Odbywa się za pośrednictwem `module rec`.</span><span class="sxs-lookup"><span data-stu-id="a082e-154">This is done via `module rec`.</span></span>  <span data-ttu-id="a082e-155">Użycie `module rec` można zlikwidować niektóre problemy, które nie jest możliwość napisać kod wzajemnie referencyjnej między typami i modułów.</span><span class="sxs-lookup"><span data-stu-id="a082e-155">Use of `module rec` can alleviate some pains in not being able to write mutually referential code between types and modules.</span></span>  <span data-ttu-id="a082e-156">Oto przykład:</span><span class="sxs-lookup"><span data-stu-id="a082e-156">The following is an example of this:</span></span>

```fsharp
module rec RecursiveModule =
    type Orientation = Up | Down
    type PeelState = Peeled | Unpeeled

    // This exception depends on the type below.
    exception DontSqueezeTheBananaException of Banana

    type BananaPeel() = class end

    type Banana(orientation : Orientation) =
        member val IsPeeled = false with get, set
        member val Orientation = orientation with get, set
        member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set
        
        member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
        member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

    module private BananaHelpers =
        let peel (b : Banana) =
            let flip banana =
                match banana.Orientation with
                | Up -> 
                    banana.Orientation <- Down
                    banana
                | Down -> banana

            let peelSides banana =
                for side in banana.Sides do
                    if side = Unpeeled then
                        side <- Peeled

            match b.Orientation with
            | Up ->   b |> flip |> peelSides
            | Down -> b |> peelSides
```

<span data-ttu-id="a082e-157">Należy pamiętać, że wyjątek `DontSqueezeTheBananaException` i klasa `Banana` odnoszą się do siebie.</span><span class="sxs-lookup"><span data-stu-id="a082e-157">Note that the exception `DontSqueezeTheBananaException` and the class `Banana` both refer to each other.</span></span>  <span data-ttu-id="a082e-158">Ponadto moduł `BananaHelpers` i klasa `Banana` także odwoływać się do siebie.</span><span class="sxs-lookup"><span data-stu-id="a082e-158">Additionally, the module `BananaHelpers` and the class `Banana` also refer to each other.</span></span>  <span data-ttu-id="a082e-159">To nie jest możliwe do wyrażenia w języku F #, jeśli usunięto `rec` — słowo kluczowe z `RecursiveModule` modułu.</span><span class="sxs-lookup"><span data-stu-id="a082e-159">This would not be possible to express in F# if you removed the `rec` keyword from the `RecursiveModule` module.</span></span>

<span data-ttu-id="a082e-160">Ta funkcja jest również możliwe w [przestrzeni nazw](namespaces.md) z 4.1 F #.</span><span class="sxs-lookup"><span data-stu-id="a082e-160">This capability is also possible in [Namespaces](namespaces.md) with F# 4.1.</span></span>

## <a name="see-also"></a><span data-ttu-id="a082e-161">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a082e-161">See Also</span></span>

<span data-ttu-id="a082e-162">[Dokumentacja języka F #](index.md)
[przestrzeni nazw](namespaces.md)
[F # 1009 FS RFC — Zezwalaj modułów i typy referencyjne wzajemnie przez szerszego zakresu w plikach](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span><span class="sxs-lookup"><span data-stu-id="a082e-162">[F# Language Reference](index.md)
[Namespaces](namespaces.md)
[F# RFC FS-1009 - Allow mutually referential types and modules over larger scopes within files](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)</span></span>