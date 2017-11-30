---
title: "Testowanie biblioteki F # w .NET Core za pomocą testu dotnet i MSTest jednostki"
description: "Informacje pojęcia testów jednostkowych dla F # w .NET Core za pomocą interaktywna tworzenia przykładowe rozwiązanie krok po kroku przy użyciu platformy dotnet testu i MSTest."
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.topic: article
dev_langs: fsharp
ms.prod: .net-core
ms.openlocfilehash: f8ea697596f144fdd6d50c871399388a075ba935
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-mstest"></a><span data-ttu-id="a5b85-103">Testowanie biblioteki F # w .NET Core za pomocą testu dotnet i MSTest jednostki</span><span class="sxs-lookup"><span data-stu-id="a5b85-103">Unit testing F# libraries in .NET Core using dotnet test and MSTest</span></span>

<span data-ttu-id="a5b85-104">Ten samouczek przedstawia interaktywna tworzenia przykładowe rozwiązanie krok po kroku, aby dowiedzieć się pojęcia testowania jednostek.</span><span class="sxs-lookup"><span data-stu-id="a5b85-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="a5b85-105">Jeśli chcesz wykonać czynności opisane w samouczku za pomocą wbudowanych rozwiązania, [wyświetlić lub pobrać przykładowy kod](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-mstest/) przed rozpoczęciem.</span><span class="sxs-lookup"><span data-stu-id="a5b85-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-with-fsharp-mstest/) before you begin.</span></span> <span data-ttu-id="a5b85-106">Instrukcje pobrania, zobacz [przykłady i samouczki](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a5b85-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="a5b85-107">Tworzenie projektu źródłowego</span><span class="sxs-lookup"><span data-stu-id="a5b85-107">Creating the source project</span></span>

<span data-ttu-id="a5b85-108">Umożliwia otwarcie okna powłoki.</span><span class="sxs-lookup"><span data-stu-id="a5b85-108">Open a shell window.</span></span> <span data-ttu-id="a5b85-109">Utwórz katalog o nazwie *jednostki — testowanie z — języka fsharp* do przechowywania rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="a5b85-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="a5b85-110">Wewnątrz tego nowego katalogu Uruchom [ `dotnet new sln` ](../tools/dotnet-new.md) do tworzenia nowego rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="a5b85-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="a5b85-111">Ułatwia to zarządzanie biblioteki klas i jednostkowy projekt testowy.</span><span class="sxs-lookup"><span data-stu-id="a5b85-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="a5b85-112">Utwórz katalog rozwiązania *MathService* katalogu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="a5b85-113">Struktura katalogów i plików dotychczasowych jest pokazany poniżej:</span><span class="sxs-lookup"><span data-stu-id="a5b85-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="a5b85-114">Wprowadź *MathService* bieżącego katalogu i uruchom [ `dotnet new classlib -lang F#` ](../tools/dotnet-new.md) do tworzenia projektu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="a5b85-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="a5b85-115">Aby użyć projektowanie oparte na testach (TDD), należy utworzyć niepowodzenie stosowania usługi matematyczne:</span><span class="sxs-lookup"><span data-stu-id="a5b85-115">To use test-driven development (TDD), you'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let sumOfSquares xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="a5b85-116">Zmień katalog z powrotem do *jednostki — testowanie z — języka fsharp* katalogu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="a5b85-117">Uruchom [ `dotnet sln add .\MathService\MathService.fsproj` ](../tools/dotnet-sln.md) można dodać projektu biblioteki klas do rozwiązania.</span><span class="sxs-lookup"><span data-stu-id="a5b85-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="a5b85-118">Tworzenie projektu testu</span><span class="sxs-lookup"><span data-stu-id="a5b85-118">Creating the test project</span></span>

<span data-ttu-id="a5b85-119">Następnie należy utworzyć *MathService.Tests* katalogu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="a5b85-120">Następujące konspektu przedstawia strukturę katalogów:</span><span class="sxs-lookup"><span data-stu-id="a5b85-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="a5b85-121">Wprowadź *MathService.Tests* katalogu bieżącego katalogu i Utwórz nowy projekt za pomocą [ `dotnet new mstest -lang F#` ](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="a5b85-121">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new mstest -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="a5b85-122">Spowoduje to utworzenie projektu testowego używanego przełącznika MSTest jako struktury testowej.</span><span class="sxs-lookup"><span data-stu-id="a5b85-122">This creates a test project that uses MSTest as the test framework.</span></span> <span data-ttu-id="a5b85-123">Wygenerowanego szablonu konfiguruje uruchamiający w *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="a5b85-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.18" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.18" />
</ItemGroup>
```

<span data-ttu-id="a5b85-124">Projekt testowy wymaga inne pakiety do tworzenia i uruchamiania testów jednostkowych.</span><span class="sxs-lookup"><span data-stu-id="a5b85-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="a5b85-125">`dotnet new`w poprzednim kroku dodane MSTest i MSTest runner.</span><span class="sxs-lookup"><span data-stu-id="a5b85-125">`dotnet new` in the previous step added MSTest and the MSTest runner.</span></span> <span data-ttu-id="a5b85-126">Teraz Dodaj `MathService` biblioteki klas jako zależność od innego projektu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="a5b85-127">Użyj [ `dotnet add reference` ](../tools/dotnet-add-reference.md) polecenia:</span><span class="sxs-lookup"><span data-stu-id="a5b85-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="a5b85-128">Widoczny cały plik w [przykłady repozytorium](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) w witrynie GitHub.</span><span class="sxs-lookup"><span data-stu-id="a5b85-128">You can see the entire file in the [samples repository](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="a5b85-129">Masz następujące układu ostatecznego rozwiązania:</span><span class="sxs-lookup"><span data-stu-id="a5b85-129">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="a5b85-130">Wykonanie [ `dotnet sln add .\MathService.Tests\MathService.Tests.fsproj` ](../tools/dotnet-sln.md) w *jednostki — testowanie z — języka fsharp* katalogu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-130">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span>

## <a name="creating-the-first-test"></a><span data-ttu-id="a5b85-131">Tworzenie pierwszego testu</span><span class="sxs-lookup"><span data-stu-id="a5b85-131">Creating the first test</span></span>

<span data-ttu-id="a5b85-132">Podejście TDD odwołuje się do pisania niepowodzeniu jednego testu, co Przekaż, a następnie powtórzyć proces.</span><span class="sxs-lookup"><span data-stu-id="a5b85-132">The TDD approach calls for writing one failing test, making it pass, then repeating the process.</span></span> <span data-ttu-id="a5b85-133">Otwórz *Tests.fs* i Dodaj następujący kod:</span><span class="sxs-lookup"><span data-stu-id="a5b85-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
namespace MathService.Tests

open System
open Microsoft.VisualStudio.TestTools.UnitTesting
open MathService

[<TestClass>]
type TestClass () =

    [<TestMethod>]
    member this.TestMethodPassing() =
        Assert.IsTrue(true)

    [<TestMethod>]
     member this.FailEveryTime() = Assert.IsTrue(false)
```

<span data-ttu-id="a5b85-134">`[<TestClass>]` Atrybut określa klasę, która zawiera testy.</span><span class="sxs-lookup"><span data-stu-id="a5b85-134">The `[<TestClass>]` attribute denotes a class that contains tests.</span></span> <span data-ttu-id="a5b85-135">`[<TestMethod>]` Atrybut oznacza metodę test jest uruchamiany przez moduł uruchamiający.</span><span class="sxs-lookup"><span data-stu-id="a5b85-135">The `[<TestMethod>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="a5b85-136">Z *jednostki — testowanie z — języka fsharp* katalogu, wykonaj [ `dotnet test` ](../tools/dotnet-test.md) do tworzenia testów i biblioteki klas, a następnie uruchom testy.</span><span class="sxs-lookup"><span data-stu-id="a5b85-136">From the *unit-testing-with-fsharp* directory, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="a5b85-137">Moduł uruchamiający xUnit zawiera punkt wejścia programu do uruchomienia testów.</span><span class="sxs-lookup"><span data-stu-id="a5b85-137">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="a5b85-138">`dotnet test`Uruchamia uruchamiający przy użyciu jednostkowy projekt testowy, który został utworzony.</span><span class="sxs-lookup"><span data-stu-id="a5b85-138">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="a5b85-139">Tych dwóch testów Pokaż najbardziej podstawową, przekazywanie i w przypadku braku testy.</span><span class="sxs-lookup"><span data-stu-id="a5b85-139">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="a5b85-140">`My test`przekazuje, i `Fail every time` nie powiedzie się.</span><span class="sxs-lookup"><span data-stu-id="a5b85-140">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="a5b85-141">Teraz, Utwórz test `sumOfSquares` metody.</span><span class="sxs-lookup"><span data-stu-id="a5b85-141">Now, create a test for the `sumOfSquares` method.</span></span> <span data-ttu-id="a5b85-142">`sumOfSquares` Metoda zwraca sumę kwadratów wszystkie wartości nieparzystą liczbą całkowitą, które są częścią sekwencji wejściowych.</span><span class="sxs-lookup"><span data-stu-id="a5b85-142">The `sumOfSquares` method returns the sum of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="a5b85-143">Zamiast w trakcie zapisanie wszystkich tych funkcji na raz, można utworzyć wielokrotnie powtarzane testy sprawdzania poprawności funkcji.</span><span class="sxs-lookup"><span data-stu-id="a5b85-143">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="a5b85-144">Wprowadzenie każdego z testów przekazać oznacza, że tworzenie funkcji niezbędne dla metody.</span><span class="sxs-lookup"><span data-stu-id="a5b85-144">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="a5b85-145">Jest najprostsza testu, firma Microsoft może zapisywać do wywołania `sumOfSquares` z wszystkie liczby parzyste, w którym wynik powinien być pustą sekwencją liczb całkowitych.</span><span class="sxs-lookup"><span data-stu-id="a5b85-145">The simplest test we can write is to call `sumOfSquares` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="a5b85-146">Oto tego testu:</span><span class="sxs-lookup"><span data-stu-id="a5b85-146">Here's that test:</span></span>

```fsharp
[<TestMethod>]
member this.TestEvenSequence() = 
    let expected = Seq.empty<int> |> Seq.toList
    let actual = MyMath.sumOfSquares [2; 4; 6; 8; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="a5b85-147">Zwróć uwagę, że `expected` sekwencji została przekonwertowana na listę.</span><span class="sxs-lookup"><span data-stu-id="a5b85-147">Notice that the `expected` sequence has been converted to a list.</span></span> <span data-ttu-id="a5b85-148">Biblioteka MSTest zależy od wielu typów .NET standard.</span><span class="sxs-lookup"><span data-stu-id="a5b85-148">The MSTest library relies on many standard .NET types.</span></span> <span data-ttu-id="a5b85-149">Czy zależności oznacza, że Twoje interfejs publiczny i oczekiwano powoduje Obsługa <xref:System.Collections.ICollection> zamiast <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="a5b85-149">That dependency means that your public interface and expected results support <xref:System.Collections.ICollection> rather than <xref:System.Collections.IEnumerable>.</span></span> 

<span data-ttu-id="a5b85-150">Po uruchomieniu testu, zobacz, czy test zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="a5b85-150">When you run the test, you see that your test fails.</span></span> <span data-ttu-id="a5b85-151">Nie utworzono jeszcze implementacji.</span><span class="sxs-lookup"><span data-stu-id="a5b85-151">You haven't created the implementation yet.</span></span> <span data-ttu-id="a5b85-152">Należy ten test przez pisania kodu najprostsza w `Mathservice` klasy, która działa:</span><span class="sxs-lookup"><span data-stu-id="a5b85-152">Make this test by writing the simplest code in the `Mathservice` class that works:</span></span>

```csharp
let sumOfSquares xs =
    Seq.empty<int> |> Seq.toList
```

<span data-ttu-id="a5b85-153">W *jednostki — testowanie z — języka fsharp* katalogu, uruchom `dotnet test` ponownie.</span><span class="sxs-lookup"><span data-stu-id="a5b85-153">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="a5b85-154">`dotnet test` Polecenia uruchamiane kompilacji dla `MathService` projektu i następnie `MathService.Tests` projektu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-154">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="a5b85-155">Po utworzeniu oba projekty, jest uruchamiana ta pojedynczy test.</span><span class="sxs-lookup"><span data-stu-id="a5b85-155">After building both projects, it runs this single test.</span></span> <span data-ttu-id="a5b85-156">Przekazuje ono.</span><span class="sxs-lookup"><span data-stu-id="a5b85-156">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="a5b85-157">Korzystanie z wymaganiami</span><span class="sxs-lookup"><span data-stu-id="a5b85-157">Completing the requirements</span></span>

<span data-ttu-id="a5b85-158">Teraz, kiedy dokonano jeden test przekazać nadszedł czas na zapis więcej.</span><span class="sxs-lookup"><span data-stu-id="a5b85-158">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="a5b85-159">Następny prostym przypadku współpracuje z sekwencji, których tylko nieparzysta liczba jest `1`.</span><span class="sxs-lookup"><span data-stu-id="a5b85-159">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="a5b85-160">Numer 1 jest łatwiejsze, ponieważ kwadrat 1 jest 1.</span><span class="sxs-lookup"><span data-stu-id="a5b85-160">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="a5b85-161">Oto Następny test:</span><span class="sxs-lookup"><span data-stu-id="a5b85-161">Here's that next test:</span></span>

```fsharp
[<TestMethod>]
member public this.SumOnesAndEvens() =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.sumOfSquares [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="a5b85-162">Wykonywanie `dotnet test` nie powiedzie się nowego testu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-162">Executing `dotnet test` fails the new test.</span></span> <span data-ttu-id="a5b85-163">Należy zaktualizować `sumOfSquares` można obsłużyć tego nowego testu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-163">You must update the `sumOfSquares` method to handle this new test.</span></span> <span data-ttu-id="a5b85-164">Należy filtrować wszystkie liczby parzyste poza kolejnością, aby ten test przekazywania.</span><span class="sxs-lookup"><span data-stu-id="a5b85-164">You must filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="a5b85-165">Możesz to zrobić pisanie funkcji małych filtru i używając `Seq.filter`:</span><span class="sxs-lookup"><span data-stu-id="a5b85-165">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let sumOfSquares xs =
    xs
    |> Seq.filter isOdd |> Seq.toList
```

<span data-ttu-id="a5b85-166">Zwróć uwagę, wywołanie `Seq.toList`.</span><span class="sxs-lookup"><span data-stu-id="a5b85-166">Notice the call to `Seq.toList`.</span></span> <span data-ttu-id="a5b85-167">Która tworzy listę, która implementuje <xref:System.Collections.ICollection> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="a5b85-167">That creates a list, which implements the <xref:System.Collections.ICollection> interface.</span></span>

<span data-ttu-id="a5b85-168">Istnieje jeden krok Przejdź: kwadratowe każdego nieparzyste numery.</span><span class="sxs-lookup"><span data-stu-id="a5b85-168">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="a5b85-169">Rozpocznij od zapisywania nowego testu:</span><span class="sxs-lookup"><span data-stu-id="a5b85-169">Start by writing a new test:</span></span>

```fsharp
[<TestMethod>]
member public this.TestSquaresOfOdds() =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.sumOfSquares [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.AreEqual(expected, actual)
```

<span data-ttu-id="a5b85-170">Test można rozwiązać przez przekazanie w potoku filtrowane sekwencji za pomocą operacji mapy do obliczenia wartości kwadratu każdą nieparzystą liczbę:</span><span class="sxs-lookup"><span data-stu-id="a5b85-170">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let sumOfSquares xs = 
    xs 
    |> Seq.filter isOdd 
    |> Seq.map square
    |> Seq.toList
```

<span data-ttu-id="a5b85-171">Został utworzony małych biblioteki i zestaw testów jednostkowych dla tej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="a5b85-171">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="a5b85-172">Zostały strukturę rozwiązania, aby dodać nowe pakiety i testów jest częścią Normalny przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="a5b85-172">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="a5b85-173">Już skoncentrowany większość czasu i uwagi na temat rozwiązywania problemów celów aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a5b85-173">You've concentrated most of your time and effort on solving the goals of the application.</span></span>