---
title: "Porady: modyfikowanie zawartości ciągu - przewodnik C#"
ms.date: 02/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], modifying
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 830ca207c4cd5bd24dbb667328465cafb2509409
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-modify-string-contents-in-c"></a><span data-ttu-id="29619-102">Porady: modyfikowanie zawartości ciągu w języku C#</span><span class="sxs-lookup"><span data-stu-id="29619-102">How to: Modify string contents in C#</span></span> #

<span data-ttu-id="29619-103">W tym artykule przedstawiono kilka technik w celu utworzenia `string` przez zmodyfikowanie istniejącej `string`.</span><span class="sxs-lookup"><span data-stu-id="29619-103">This article demonstrates several techniques to produce a `string` by modifying an existing `string`.</span></span> <span data-ttu-id="29619-104">Wszystkie techniki przedstawiona zwracają wynik jako nowe zmiany `string` obiektu.</span><span class="sxs-lookup"><span data-stu-id="29619-104">All the techniques demonstrated return the result of the modifications as a new `string` object.</span></span> <span data-ttu-id="29619-105">Aby zademonstrować to wyraźnie, wszystkie przykłady przechowywać wynik w nowej zmiennej.</span><span class="sxs-lookup"><span data-stu-id="29619-105">To clearly demonstrate this, the examples all store the result in a new variable.</span></span> <span data-ttu-id="29619-106">Następnie można sprawdzić zarówno oryginalny `string` i `string` wynikające z modyfikacji podczas uruchamiania każdy przykład.</span><span class="sxs-lookup"><span data-stu-id="29619-106">You can then examine both the original `string` and the `string` resulting from the modification when you run each example.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="29619-107">Istnieje kilka technik przedstawiona w tym artykule.</span><span class="sxs-lookup"><span data-stu-id="29619-107">There are several techniques demonstrated in this article.</span></span> <span data-ttu-id="29619-108">Można zastąpić istniejącego tekstu.</span><span class="sxs-lookup"><span data-stu-id="29619-108">You can replace existing text.</span></span> <span data-ttu-id="29619-109">Można wyszukać wzorców i zamienić szukanego tekstu inny tekst.</span><span class="sxs-lookup"><span data-stu-id="29619-109">You can search for patterns and replace matching text with other text.</span></span> <span data-ttu-id="29619-110">Ciąg można traktować jako sekwencja znaków.</span><span class="sxs-lookup"><span data-stu-id="29619-110">You can treat a string as a sequence of characters.</span></span> <span data-ttu-id="29619-111">Umożliwia także podręczne metody, które Usuń biały znak.</span><span class="sxs-lookup"><span data-stu-id="29619-111">You can also use convenience methods that remove white space.</span></span> <span data-ttu-id="29619-112">Należy wybrać techniki, które najlepiej pasują danego scenariusza.</span><span class="sxs-lookup"><span data-stu-id="29619-112">You should choose the techniques that most closely match your scenario.</span></span>

## <a name="replace-text"></a><span data-ttu-id="29619-113">Zastępowanie tekstu</span><span class="sxs-lookup"><span data-stu-id="29619-113">Replace text</span></span>

<span data-ttu-id="29619-114">Poniższy kod tworzy nowe parametry, zastępując istniejący tekst zastępczy.</span><span class="sxs-lookup"><span data-stu-id="29619-114">The following code creates a new string by replacing existing text with a substitute.</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#1)]

<span data-ttu-id="29619-115">Poprzedni kod pokazuje to *niezmienne* właściwości ciągów.</span><span class="sxs-lookup"><span data-stu-id="29619-115">The preceding code demonstrates this *immutable* property of strings.</span></span> <span data-ttu-id="29619-116">Można zobaczyć w poprzednim przykładzie który oryginalnego ciągu `source`, nie jest modyfikowany.</span><span class="sxs-lookup"><span data-stu-id="29619-116">You can see in the preceding example that the original string, `source`, is not modified.</span></span> <span data-ttu-id="29619-117"><xref:System.String.Replace%2A?displayProperty=nameWithType> Metoda tworzy nowy `string` zawierające te zmiany.</span><span class="sxs-lookup"><span data-stu-id="29619-117">The <xref:System.String.Replace%2A?displayProperty=nameWithType> method creates a new `string` containing the modifications.</span></span>

<span data-ttu-id="29619-118"><xref:System.String.Replace%2A> Metody można zastąpić, ciągi lub pojedynczy znaki.</span><span class="sxs-lookup"><span data-stu-id="29619-118">The <xref:System.String.Replace%2A> method can replace either strings or single characters.</span></span> <span data-ttu-id="29619-119">W obu przypadkach każde wystąpienie poszukiwaną tekst został zastąpiony.</span><span class="sxs-lookup"><span data-stu-id="29619-119">In both cases, every occurrence of the sought text is replaced.</span></span>  <span data-ttu-id="29619-120">Poniższy przykład zastępuje wszystkie ' "znaków i zawierają"\_":</span><span class="sxs-lookup"><span data-stu-id="29619-120">The following example replaces all ' ' characters with '\_':</span></span>

[!code-csharp-interactive[replace characters](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#2)]

<span data-ttu-id="29619-121">Ciąg źródłowy jest bez zmian, a nowy ciąg z zastąpienia.</span><span class="sxs-lookup"><span data-stu-id="29619-121">The source string is unchanged, and a new string is returned with the replacement.</span></span>

## <a name="trim-white-space"></a><span data-ttu-id="29619-122">TRIM biały znak</span><span class="sxs-lookup"><span data-stu-id="29619-122">Trim white space</span></span>

<span data-ttu-id="29619-123">Można użyć <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType>, i <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> metod, aby usunąć wszystkie białe wiodących lub końcowych.</span><span class="sxs-lookup"><span data-stu-id="29619-123">You can use the <xref:System.String.Trim%2A?displayProperty=nameWithType>, <xref:System.String.TrimStart%2A?displayProperty=nameWithType>, and <xref:System.String.TrimEnd%2A?displayProperty=nameWithType> methods to remove any leading or trailing white space.</span></span>  <span data-ttu-id="29619-124">Poniższy kod przedstawia przykład każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="29619-124">The following code shows an example of each.</span></span> <span data-ttu-id="29619-125">Ciąg źródłowy nie ulega zmianie; te metody zwracają nowe parametry z zawartością, zmodyfikowany.</span><span class="sxs-lookup"><span data-stu-id="29619-125">The source string does not change; these methods return a new string with the modified contents.</span></span>

[!code-csharp-interactive[trim white space](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#3)]

## <a name="remove-text"></a><span data-ttu-id="29619-126">Usuń tekst</span><span class="sxs-lookup"><span data-stu-id="29619-126">Remove text</span></span>

<span data-ttu-id="29619-127">Możesz usunąć tekst z ciągu za pomocą <xref:System.String.Remove%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="29619-127">You can remove text from a string using the <xref:System.String.Remove%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="29619-128">Ta metoda usuwa liczba znaków, zaczynając od określonego indeksu.</span><span class="sxs-lookup"><span data-stu-id="29619-128">This method removes a number of characters starting at a specific index.</span></span> <span data-ttu-id="29619-129">Poniższy przykład przedstawia użycie <xref:System.String.IndexOf%2A?displayProperty=nameWithType> następuje <xref:System.String.Remove%2A> do usunięcia z ciągu tekstowego:</span><span class="sxs-lookup"><span data-stu-id="29619-129">The following example shows how to use <xref:System.String.IndexOf%2A?displayProperty=nameWithType> followed by <xref:System.String.Remove%2A> to remove text from a string:</span></span>

[!code-csharp-interactive[remove text](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#4)]

## <a name="replace-matching-patterns"></a><span data-ttu-id="29619-130">Zastąp wzorce dopasowania</span><span class="sxs-lookup"><span data-stu-id="29619-130">Replace matching patterns</span></span>

<span data-ttu-id="29619-131">Można użyć [wyrażeń regularnych](../../standard/base-types/regular-expressions.md) tekst wzorce nowym tekstem, prawdopodobnie wynika z wzorca dopasowania.</span><span class="sxs-lookup"><span data-stu-id="29619-131">You can use [regular expressions](../../standard/base-types/regular-expressions.md) to replace text matching patterns with new text, possibly defined by a pattern.</span></span> <span data-ttu-id="29619-132">W poniższym przykładzie użyto <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> klasy można znaleźć wzorzec ciągu źródła i Zamień odpowiednie wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="29619-132">The following example uses the <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class to find a pattern in a source string and replace it with proper capitalization.</span></span> <span data-ttu-id="29619-133"><xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> Metoda przyjmuje funkcja, która udostępnia logikę zastąpienia jako jeden z jego argumentów.</span><span class="sxs-lookup"><span data-stu-id="29619-133">The <xref:System.Text.RegularExpressions.Regex.Replace(System.String,System.String,System.Text.RegularExpressions.MatchEvaluator,System.Text.RegularExpressions.RegexOptions)?displayProperty=nameWithType> method takes a function that provides the logic of the replacement as one of its arguments.</span></span> <span data-ttu-id="29619-134">W tym przykładzie, że funkcja `LocalReplaceMatchCase` jest **funkcja lokalna** deklarowane w przykładowej metody.</span><span class="sxs-lookup"><span data-stu-id="29619-134">In this example, that function, `LocalReplaceMatchCase` is a **local function** declared inside the sample method.</span></span> <span data-ttu-id="29619-135">`LocalReplaceMatchCase` używa <xref:System.Text.StringBuilder?displayProperty=nameWithType> klasa do tworzenia ciąg zastępczy z właściwego wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="29619-135">`LocalReplaceMatchCase` uses the <xref:System.Text.StringBuilder?displayProperty=nameWithType> class to build the replacement string with proper capitalization.</span></span>

<span data-ttu-id="29619-136">Wyrażenia regularne są najbardziej przydatny w przypadku wyszukiwania i zastępowanie tekstu, która jest zgodna ze wzorcem zamiast tekstu znane.</span><span class="sxs-lookup"><span data-stu-id="29619-136">Regular expressions are most useful for searching and replacing text that follows a pattern, rather than known text.</span></span> <span data-ttu-id="29619-137">Zobacz [porady: wyszukiwanie ciągów](search-strings.md) więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="29619-137">See [How to: search strings](search-strings.md) for more details.</span></span> <span data-ttu-id="29619-138">Wzorzec wyszukiwania "the\s" Wyszukiwanie słowa "" następuje biały znak.</span><span class="sxs-lookup"><span data-stu-id="29619-138">The search pattern, "the\s" searches for the word "the" followed by a white-space character.</span></span> <span data-ttu-id="29619-139">Części wzorca gwarantuje, że nie jest zgodna "Brak" w ciągu źródła.</span><span class="sxs-lookup"><span data-stu-id="29619-139">That part of the pattern ensures that it doesn't match "there" in the source string.</span></span> <span data-ttu-id="29619-140">Aby uzyskać więcej informacji na elementy języka wyrażeń regularnych, zobacz [język wyrażeń regularnych — podręczny wykaz](../../standard/base-types/regular-expression-language-quick-reference.md).</span><span class="sxs-lookup"><span data-stu-id="29619-140">For more information on regular expression language elements, see [Regular Expression Language - Quick Reference](../../standard/base-types/regular-expression-language-quick-reference.md).</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#5)]

<span data-ttu-id="29619-141"><xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> Metoda zwraca niezmienny ciąg z zawartością w <xref:System.Text.StringBuilder> obiektu.</span><span class="sxs-lookup"><span data-stu-id="29619-141">The <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> method returns an immutable string with the contents in the <xref:System.Text.StringBuilder> object.</span></span>

## <a name="modifying-individual-characters"></a><span data-ttu-id="29619-142">Modyfikowanie znaki</span><span class="sxs-lookup"><span data-stu-id="29619-142">Modifying individual characters</span></span>

<span data-ttu-id="29619-143">Można utworzyć tablicy znaków z ciągu, modyfikowania zawartości tablicy, a następnie utwórz nowe parametry z zmodyfikowanej zawartości tablicy.</span><span class="sxs-lookup"><span data-stu-id="29619-143">You can produce a character array from a string, modify the contents of the array, and then create a new string from the modified contents of the array.</span></span>

<span data-ttu-id="29619-144">Poniższy przykład pokazuje, jak zastąpić zestaw znaków w ciągu.</span><span class="sxs-lookup"><span data-stu-id="29619-144">The following example shows how to replace a set of characters in a string.</span></span> <span data-ttu-id="29619-145">Po pierwsze, używa <xref:System.String.ToCharArray?displayProperty=nameWithName> metodę w celu utworzenia tablicy znaków.</span><span class="sxs-lookup"><span data-stu-id="29619-145">First, it uses the <xref:System.String.ToCharArray?displayProperty=nameWithName> method to create an array of characters.</span></span> <span data-ttu-id="29619-146">Używa <xref:System.String.IndexOf%2A> metody do znalezienia indeks początkowy wyrazu "fox."</span><span class="sxs-lookup"><span data-stu-id="29619-146">It uses the <xref:System.String.IndexOf%2A> method to find the starting index of the word "fox."</span></span> <span data-ttu-id="29619-147">Trzech kolejnych znaków są zastępowane innego programu word.</span><span class="sxs-lookup"><span data-stu-id="29619-147">The next three characters are replaced with a different word.</span></span> <span data-ttu-id="29619-148">Ponadto nowy ciąg jest tworzony z tablicy znaków zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="29619-148">Finally, a new string is constructed from the updated character array.</span></span>

[!code-csharp-interactive[replace creates a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#6)]

## <a name="unsafe-modifications-to-string"></a><span data-ttu-id="29619-149">Niebezpieczne modyfikacje na ciąg</span><span class="sxs-lookup"><span data-stu-id="29619-149">Unsafe modifications to string</span></span>

<span data-ttu-id="29619-150">Przy użyciu **niebezpieczne** kodu, ciąg "w miejscu" można modyfikować po został utworzony.</span><span class="sxs-lookup"><span data-stu-id="29619-150">Using **unsafe** code, you can modify a string "in place" after it has been created.</span></span> <span data-ttu-id="29619-151">Niebezpieczny kod pomijany wiele funkcji .NET zaprojektowany w celu zminimalizowania niektórych typów błędów w kodzie.</span><span class="sxs-lookup"><span data-stu-id="29619-151">Unsafe code bypasses many of the features of .NET designed to minimize certain types of bugs in code.</span></span> <span data-ttu-id="29619-152">Należy użyć można zmodyfikować ciąg w miejscu, ponieważ klasa ciąg został zaprojektowany jako niebezpieczny kod **niezmienialnych** typu.</span><span class="sxs-lookup"><span data-stu-id="29619-152">You need to use unsafe code to modify a string in place because the string class is designed as an **immutable** type.</span></span> <span data-ttu-id="29619-153">Po utworzeniu, jego wartość nie ulega zmianie.</span><span class="sxs-lookup"><span data-stu-id="29619-153">Once it has been created, its value does not change.</span></span> <span data-ttu-id="29619-154">Niebezpieczny kod obejścia tej właściwości, uzyskiwanie dostępu i modyfikując pamięci używanej przez `string` bez użycia normalne `string` metody.</span><span class="sxs-lookup"><span data-stu-id="29619-154">Unsafe code circumvents this property by accessing and modifying the memory used by a `string` without using normal `string` methods.</span></span>
<span data-ttu-id="29619-155">Poniższy przykład jest dostępna dla tych rzadkich sytuacji, w której chcesz zmodyfikować ciąg w miejscu przy użyciu niebezpieczny kod.</span><span class="sxs-lookup"><span data-stu-id="29619-155">The following example is provided for those rare situations where you want to modify a string in-place using unsafe code.</span></span> <span data-ttu-id="29619-156">W przykładzie pokazano sposób użycia `fixed` — słowo kluczowe.</span><span class="sxs-lookup"><span data-stu-id="29619-156">The example shows how to use the `fixed` keyword.</span></span> <span data-ttu-id="29619-157">`fixed` — Słowo kluczowe uniemożliwia przenoszenie z obiektem ciągu w pamięci, gdy kod uzyskuje dostęp do pamięci przy użyciu wskaźnika niebezpieczny moduł garbage collector (GC).</span><span class="sxs-lookup"><span data-stu-id="29619-157">The `fixed` keyword prevents the garbage collector (GC) from moving the string object in memory while code accesses the memory using the unsafe pointer.</span></span> <span data-ttu-id="29619-158">Ilustruje też jedną możliwe ubocznym niebezpieczne operacje na ciągach będącą wynikiem sposób kompilatora C# wewnętrznie przechowuje ciągi (stażystów).</span><span class="sxs-lookup"><span data-stu-id="29619-158">It also demonstrates one possible side effect of unsafe operations on strings that results from the way that the C# compiler stores (interns) strings internally.</span></span> <span data-ttu-id="29619-159">Ogólnie rzecz biorąc nie należy użyć tej metody, chyba że jest bezwzględnie konieczne.</span><span class="sxs-lookup"><span data-stu-id="29619-159">In general, you shouldn't use this technique unless it is absolutely necessary.</span></span> <span data-ttu-id="29619-160">Możesz dowiedzieć się więcej informacji, zobacz artykuły na [niebezpieczne](../language-reference/keywords/unsafe.md) i [stałej](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="29619-160">You can learn more in the articles on [unsafe](../language-reference/keywords/unsafe.md) and [fixed](../language-reference/keywords/fixed-statement.md).</span></span> <span data-ttu-id="29619-161">Dokumentacja interfejsu API dla <xref:System.String.Intern%2A> obejmuje inforamtion na interning ciągu.</span><span class="sxs-lookup"><span data-stu-id="29619-161">The API reference for <xref:System.String.Intern%2A> includes inforamtion on string interning.</span></span>

[!code-csharp-interactive[unsafe ways to create a new string](../../../samples/snippets/csharp/how-to/strings/ModifyStrings.cs#7)]

<span data-ttu-id="29619-162">Możesz spróbować te przykłady, sprawdzając kod w naszym [repozytorium GitHub](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span><span class="sxs-lookup"><span data-stu-id="29619-162">You can try these samples by looking at the code in our [GitHub repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings).</span></span> <span data-ttu-id="29619-163">Można również pobrać próbki [jako plik zip](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings.zip).</span><span class="sxs-lookup"><span data-stu-id="29619-163">Or you can download the samples [as a zip file](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/strings.zip).</span></span>

## <a name="see-also"></a><span data-ttu-id="29619-164">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="29619-164">See also</span></span>

[<span data-ttu-id="29619-165">.NET framework — nieprawidłowe wyrażenia</span><span class="sxs-lookup"><span data-stu-id="29619-165">.NET Framework Regular Expressions</span></span>](../../standard/base-types/regular-expressions.md)  
 [<span data-ttu-id="29619-166">Język wyrażeń regularnych — podręczny wykaz</span><span class="sxs-lookup"><span data-stu-id="29619-166">Regular Expression Language - Quick Reference</span></span>](../../standard/base-types/regular-expression-language-quick-reference.md)  