---
title: "Inne konstrukcje w wyrażeniach regularnych"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- constructs, miscellaneous
- .NET Framework regular expressions, miscellaneous constructs
- regular expressions, miscellaneous constructs
ms.assetid: 7d10d11f-680f-4721-b047-fb136316b4cd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b33d196a7af9bc5a1f81c1624bbd98fea074319
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="miscellaneous-constructs-in-regular-expressions"></a><span data-ttu-id="91177-102">Inne konstrukcje w wyrażeniach regularnych</span><span class="sxs-lookup"><span data-stu-id="91177-102">Miscellaneous Constructs in Regular Expressions</span></span>
<span data-ttu-id="91177-103">Wyrażeń regularnych programu .NET obejmują trzy różne języka konstrukcje.</span><span class="sxs-lookup"><span data-stu-id="91177-103">Regular expressions in .NET include three miscellaneous language constructs.</span></span> <span data-ttu-id="91177-104">Co pozwala włączyć lub wyłączyć opcjami pasującego środku wzorzec wyrażenia regularnego.</span><span class="sxs-lookup"><span data-stu-id="91177-104">One lets you enable or disable particular matching options in the middle of a regular expression pattern.</span></span> <span data-ttu-id="91177-105">Dwóch pozostałych pozwala na uwzględnianie komentarzy w wyrażeniu regularnym.</span><span class="sxs-lookup"><span data-stu-id="91177-105">The remaining two let you include comments in a regular expression.</span></span>  
  
## <a name="inline-options"></a><span data-ttu-id="91177-106">Wbudowane opcje</span><span class="sxs-lookup"><span data-stu-id="91177-106">Inline Options</span></span>  
 <span data-ttu-id="91177-107">Możesz ustawić lub wyłącz określonego wzorca dopasowania opcje część wyrażenia regularnego przy użyciu składni</span><span class="sxs-lookup"><span data-stu-id="91177-107">You can set or disable specific pattern matching options for part of a regular expression by using the syntax</span></span>  
  
```  
(?imnsx-imnsx)  
```  
  
 <span data-ttu-id="91177-108">Możesz wyświetlić listę opcje, które chcesz włączyć po znaku zapytania i opcje, które mają zostać wyłączone po znaku minus.</span><span class="sxs-lookup"><span data-stu-id="91177-108">You list the options you want to enable after the question mark, and the options you want to disable after the minus sign.</span></span> <span data-ttu-id="91177-109">W tabeli poniżej opisano wszystkie opcje.</span><span class="sxs-lookup"><span data-stu-id="91177-109">The following table describes each option.</span></span> <span data-ttu-id="91177-110">Aby uzyskać więcej informacji na temat poszczególnych opcji, zobacz [opcje wyrażeń regularnych](../../../docs/standard/base-types/regular-expression-options.md).</span><span class="sxs-lookup"><span data-stu-id="91177-110">For more information about each option, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
|<span data-ttu-id="91177-111">Opcja</span><span class="sxs-lookup"><span data-stu-id="91177-111">Option</span></span>|<span data-ttu-id="91177-112">Opis</span><span class="sxs-lookup"><span data-stu-id="91177-112">Description</span></span>|  
|------------|-----------------|  
|`i`|<span data-ttu-id="91177-113">Dopasowywanie bez uwzględniania wielkości liter.</span><span class="sxs-lookup"><span data-stu-id="91177-113">Case-insensitive matching.</span></span>|  
|`m`|<span data-ttu-id="91177-114">Wielowierszowy tryb.</span><span class="sxs-lookup"><span data-stu-id="91177-114">Multiline mode.</span></span>|  
|`n`|<span data-ttu-id="91177-115">Jawne przechwytywanie tylko.</span><span class="sxs-lookup"><span data-stu-id="91177-115">Explicit captures only.</span></span> <span data-ttu-id="91177-116">(Nawiasy mają nie zachowywać się jak przechwytywanie grup.)</span><span class="sxs-lookup"><span data-stu-id="91177-116">(Parentheses do not act as capturing groups.)</span></span>|  
|`s`|<span data-ttu-id="91177-117">Jednowierszowy tryb.</span><span class="sxs-lookup"><span data-stu-id="91177-117">Single-line mode.</span></span>|  
|`x`|<span data-ttu-id="91177-118">Ignoruj niezmienionym znaczeniu biały znak, a następnie poczekanie komentarze w trybie x.</span><span class="sxs-lookup"><span data-stu-id="91177-118">Ignore unescaped white space, and allow x-mode comments.</span></span>|  
  
 <span data-ttu-id="91177-119">Zmiany w opcjach wyrażenia regularnego zdefiniowane przez `(?imnsx-imnsx)` w celu utworzenia pozostaje aż do zakończenia otaczające grupy.</span><span class="sxs-lookup"><span data-stu-id="91177-119">Any change in regular expression options defined by the `(?imnsx-imnsx)` construct remains in effect until the end of the enclosing group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91177-120">`(?imnsx-imnsx:` *Podwyrażenie* `)` konstrukcji grupowania udostępnia funkcję identyczne dla podwyrażenia.</span><span class="sxs-lookup"><span data-stu-id="91177-120">The `(?imnsx-imnsx:`*subexpression*`)` grouping construct provides identical functionality for a subexpression.</span></span> <span data-ttu-id="91177-121">Aby uzyskać więcej informacji, zobacz [konstrukcji grupowania](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="91177-121">For more information, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="91177-122">W poniższym przykładzie użyto `i`, `n`, i `x` opcje umożliwiające liter i jawne przechwytywanie i Ignoruj biały znak w wzorzec wyrażenia regularnego w trakcie wykonywania wyrażenia regularnego.</span><span class="sxs-lookup"><span data-stu-id="91177-122">The following example uses the `i`, `n`, and `x` options to enable case insensitivity and explicit captures, and to ignore white space in the regular expression pattern in the middle of a regular expression.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous1.cs#1)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous1.vb#1)]  
  
 <span data-ttu-id="91177-123">W przykładzie zdefiniowano dwóch wyrażeń regularnych.</span><span class="sxs-lookup"><span data-stu-id="91177-123">The example defines two regular expressions.</span></span> <span data-ttu-id="91177-124">Pierwsza strona, `\b(D\w+)\s(d\w+)\b`, odpowiada dwa kolejne słowa zaczynające się wielkie litery "D" i "d" jedną małą literę.</span><span class="sxs-lookup"><span data-stu-id="91177-124">The first, `\b(D\w+)\s(d\w+)\b`, matches two consecutive words that begin with an uppercase "D" and a lowercase "d".</span></span> <span data-ttu-id="91177-125">Drugie wyrażenie regularne, `\b(D\w+)(?ixn) \s (d\w+) \b`, używa wbudowanego opcji do modyfikowania tego wzorca, zgodnie z opisem w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="91177-125">The second regular expression, `\b(D\w+)(?ixn) \s (d\w+) \b`, uses inline options to modify this pattern, as described in the following table.</span></span> <span data-ttu-id="91177-126">Porównanie wyników potwierdza efekt `(?ixn)` utworzenia.</span><span class="sxs-lookup"><span data-stu-id="91177-126">A comparison of the results confirms the effect of the `(?ixn)` construct.</span></span>  
  
|<span data-ttu-id="91177-127">Wzorzec</span><span class="sxs-lookup"><span data-stu-id="91177-127">Pattern</span></span>|<span data-ttu-id="91177-128">Opis</span><span class="sxs-lookup"><span data-stu-id="91177-128">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="91177-129">Rozpoczyna na granicy wyrazu.</span><span class="sxs-lookup"><span data-stu-id="91177-129">Start at a word boundary.</span></span>|  
|`(D\w+)`|<span data-ttu-id="91177-130">Zgodne kapitału "D", po którym następuje co najmniej jeden znak programu word.</span><span class="sxs-lookup"><span data-stu-id="91177-130">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="91177-131">Jest to pierwsza grupa przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="91177-131">This is the first capture group.</span></span>|  
|`(?ixn)`|<span data-ttu-id="91177-132">Z tego punktu na marka porównania bez uwzględniania wielkości liter markę tylko jawne przechwytuje i Ignoruj biały znak w wzorzec wyrażenia regularnego.</span><span class="sxs-lookup"><span data-stu-id="91177-132">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`\s`|<span data-ttu-id="91177-133">Dopasowuje znak odstępu.</span><span class="sxs-lookup"><span data-stu-id="91177-133">Match a white-space character.</span></span>|  
|`(d\w+)`|<span data-ttu-id="91177-134">Zgodne wielkie i małe litery "d" następuje co najmniej jeden znak programu word.</span><span class="sxs-lookup"><span data-stu-id="91177-134">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="91177-135">Ta grupa nie jest przechwycona, ponieważ `n` została włączona opcja (jawne przechwytywanie).</span><span class="sxs-lookup"><span data-stu-id="91177-135">This group is not captured because the `n` (explicit capture) option was enabled..</span></span>|  
|`\b`|<span data-ttu-id="91177-136">Dopasowuje granicę wyrazu.</span><span class="sxs-lookup"><span data-stu-id="91177-136">Match a word boundary.</span></span>|  
  
## <a name="inline-comment"></a><span data-ttu-id="91177-137">Komentarz w tekście</span><span class="sxs-lookup"><span data-stu-id="91177-137">Inline Comment</span></span>  
 <span data-ttu-id="91177-138">`(?#` *Komentarz* `)` konstrukcja pozwala umieścić komentarz w tekście w wyrażeniu regularnym.</span><span class="sxs-lookup"><span data-stu-id="91177-138">The `(?#` *comment*`)` construct lets you include an inline comment in a regular expression.</span></span> <span data-ttu-id="91177-139">Pomimo że komentarz zawiera ciąg, który jest zwracany przez aparat wyrażeń regularnych nie używa dowolną część komentarz w dopasowywania do wzorca <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> metody.</span><span class="sxs-lookup"><span data-stu-id="91177-139">The regular expression engine does not use any part of the comment in pattern matching, although the comment is included in the string that is returned by the <xref:System.Text.RegularExpressions.Regex.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="91177-140">Komentarz kończy się przy pierwszym nawiasie zamykającym.</span><span class="sxs-lookup"><span data-stu-id="91177-140">The comment ends at the first closing parenthesis.</span></span>  
  
 <span data-ttu-id="91177-141">Poniższy przykład powtarza pierwszy wzorzec wyrażenia regularnego z przykładu w poprzedniej sekcji.</span><span class="sxs-lookup"><span data-stu-id="91177-141">The following example repeats the first regular expression pattern from the example in the previous section.</span></span> <span data-ttu-id="91177-142">Dodaje dwa komentarzy wewnętrznych do wyrażenia regularnego, aby wskazać, czy wynik porównania jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="91177-142">It adds two inline comments to the regular expression to indicate whether the comparison is case-sensitive.</span></span> <span data-ttu-id="91177-143">Wzorzec wyrażenia regularnego `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, jest zdefiniowany w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="91177-143">The regular expression pattern, `\b((?# case-sensitive comparison)D\w+)\s((?#case-insensitive comparison)d\w+)\b`, is defined as follows.</span></span>  
  
|<span data-ttu-id="91177-144">Wzorzec</span><span class="sxs-lookup"><span data-stu-id="91177-144">Pattern</span></span>|<span data-ttu-id="91177-145">Opis</span><span class="sxs-lookup"><span data-stu-id="91177-145">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="91177-146">Rozpoczyna na granicy wyrazu.</span><span class="sxs-lookup"><span data-stu-id="91177-146">Start at a word boundary.</span></span>|  
|`(?# case-sensitive comparison)`|<span data-ttu-id="91177-147">Komentarz.</span><span class="sxs-lookup"><span data-stu-id="91177-147">A comment.</span></span> <span data-ttu-id="91177-148">Nie ma ona wpływu na zachowanie dopasowywanie do wzorca.</span><span class="sxs-lookup"><span data-stu-id="91177-148">It does not affect pattern-matching behavior.</span></span>|  
|`(D\w+)`|<span data-ttu-id="91177-149">Zgodne kapitału "D", po którym następuje co najmniej jeden znak programu word.</span><span class="sxs-lookup"><span data-stu-id="91177-149">Match a capital "D" followed by one or more word characters.</span></span> <span data-ttu-id="91177-150">Jest to pierwsza grupa przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="91177-150">This is the first capturing group.</span></span>|  
|`\s`|<span data-ttu-id="91177-151">Dopasowuje znak odstępu.</span><span class="sxs-lookup"><span data-stu-id="91177-151">Match a white-space character.</span></span>|  
|`(?ixn)`|<span data-ttu-id="91177-152">Z tego punktu na marka porównania bez uwzględniania wielkości liter markę tylko jawne przechwytuje i Ignoruj biały znak w wzorzec wyrażenia regularnego.</span><span class="sxs-lookup"><span data-stu-id="91177-152">From this point on, make comparisons case-insensitive, make only explicit captures, and ignore white space in the regular expression pattern.</span></span>|  
|`(?#case-insensitive comparison)`|<span data-ttu-id="91177-153">Komentarz.</span><span class="sxs-lookup"><span data-stu-id="91177-153">A comment.</span></span> <span data-ttu-id="91177-154">Nie ma ona wpływu na zachowanie dopasowywanie do wzorca.</span><span class="sxs-lookup"><span data-stu-id="91177-154">It does not affect pattern-matching behavior.</span></span>|  
|`(d\w+)`|<span data-ttu-id="91177-155">Zgodne wielkie i małe litery "d" następuje co najmniej jeden znak programu word.</span><span class="sxs-lookup"><span data-stu-id="91177-155">Match an uppercase or lowercase "d" followed by one or more word characters.</span></span> <span data-ttu-id="91177-156">Jest to drugi grupa przechwytywania.</span><span class="sxs-lookup"><span data-stu-id="91177-156">This is the second capture group.</span></span>|  
|`\b`|<span data-ttu-id="91177-157">Dopasowuje granicę wyrazu.</span><span class="sxs-lookup"><span data-stu-id="91177-157">Match a word boundary.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous2.cs#2)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous2.vb#2)]  
  
## <a name="end-of-line-comment"></a><span data-ttu-id="91177-158">Komentarz do końca wiersza</span><span class="sxs-lookup"><span data-stu-id="91177-158">End-of-Line Comment</span></span>  
 <span data-ttu-id="91177-159">Znak liczby (`#`) oznacza komentarz w trybie x, który rozpoczyna się od znaku # niezmienionym znaczeniu na końcu wzorzec wyrażenia regularnego i jest kontynuowane do końca wiersza.</span><span class="sxs-lookup"><span data-stu-id="91177-159">A number sign (`#`)marks an x-mode comment, which starts at the unescaped # character at the end of the regular expression pattern and continues until the end of the line.</span></span> <span data-ttu-id="91177-160">Aby użyć tej konstrukcji, należy albo Włącz `x` opcja (przy użyciu opcji wbudowany) lub podać <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> do wartości `option` parametru podczas tworzenia wystąpienia <xref:System.Text.RegularExpressions.Regex> obiektu lub wywoływania statycznych <xref:System.Text.RegularExpressions.Regex> — metoda.</span><span class="sxs-lookup"><span data-stu-id="91177-160">To use this construct, you must either enable the `x` option (through inline options) or supply the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> value to the `option` parameter when instantiating the <xref:System.Text.RegularExpressions.Regex> object or calling a static <xref:System.Text.RegularExpressions.Regex> method.</span></span>  
  
 <span data-ttu-id="91177-161">Poniższy przykład przedstawia konstrukcja komentarz końca wiersza.</span><span class="sxs-lookup"><span data-stu-id="91177-161">The following example illustrates the end-of-line comment construct.</span></span> <span data-ttu-id="91177-162">Określają one, czy ciąg formatu złożony, który zawiera co najmniej jeden element formatu ciągu.</span><span class="sxs-lookup"><span data-stu-id="91177-162">It determines whether a string is a composite format string that includes at least one format item.</span></span> <span data-ttu-id="91177-163">W poniższej tabeli opisano konstrukcje w wzorzec wyrażenia regularnego:</span><span class="sxs-lookup"><span data-stu-id="91177-163">The following table describes the constructs in the regular expression pattern:</span></span>  
  
 `\{\d+(,-*\d+)*(\:\w{1,4}?)*\}(?x) # Looks for a composite format item.`  
  
|<span data-ttu-id="91177-164">Wzorzec</span><span class="sxs-lookup"><span data-stu-id="91177-164">Pattern</span></span>|<span data-ttu-id="91177-165">Opis</span><span class="sxs-lookup"><span data-stu-id="91177-165">Description</span></span>|  
|-------------|-----------------|  
|`\{`|<span data-ttu-id="91177-166">Zgodny z nawiasem otwierającym.</span><span class="sxs-lookup"><span data-stu-id="91177-166">Match an opening brace.</span></span>|  
|`\d+`|<span data-ttu-id="91177-167">Dopasowanie do co najmniej jednej cyfry dziesiętnej.</span><span class="sxs-lookup"><span data-stu-id="91177-167">Match one or more decimal digits.</span></span>|  
|`(,-*\d+)*`|<span data-ttu-id="91177-168">Zgodne wystąpienie zero lub jeden przecinkami, i opcjonalnie znak minus następuje co najmniej jeden cyfr dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="91177-168">Match zero or one occurrence of a comma, followed by an optional minus sign, followed by one or more decimal digits.</span></span>|  
|`(\:\w{1,4}?)*`|<span data-ttu-id="91177-169">Zgodne wystąpienie zero lub jeden dwukropek, następuje 1 do 4, ale jak najmniejszej liczby znaków, jak to możliwe, biały znak.</span><span class="sxs-lookup"><span data-stu-id="91177-169">Match zero or one occurrence of a colon, followed by one to four, but as few as possible, white-space characters.</span></span>|  
|`(?#case insensitive comparison)`|<span data-ttu-id="91177-170">Komentarz w tekście.</span><span class="sxs-lookup"><span data-stu-id="91177-170">An inline comment.</span></span> <span data-ttu-id="91177-171">Go nie ma wpływu na zachowanie dopasowywanie do wzorca.</span><span class="sxs-lookup"><span data-stu-id="91177-171">It has no effect on pattern-matching behavior.</span></span>|  
|`\}`|<span data-ttu-id="91177-172">Zgodny nawiasem zamykającym.</span><span class="sxs-lookup"><span data-stu-id="91177-172">Match a closing brace.</span></span>|  
|`(?x)`|<span data-ttu-id="91177-173">Tak, aby komentarz końca wiersza zostanie rozpoznany, należy włączyć opcję białe wzorzec ignorowania.</span><span class="sxs-lookup"><span data-stu-id="91177-173">Enable the ignore pattern white-space option so that the end-of-line comment will be recognized.</span></span>|  
|`# Looks for a composite format item.`|<span data-ttu-id="91177-174">Komentarz do końca wiersza.</span><span class="sxs-lookup"><span data-stu-id="91177-174">An end-of-line comment.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.miscellaneous/cs/miscellaneous3.cs#3)]
 [!code-vb[RegularExpressions.Language.Miscellaneous#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.miscellaneous/vb/miscellaneous3.vb#3)]  
  
 <span data-ttu-id="91177-175">Należy zauważyć, że zamiast dostarczanie `(?x)` skonstruować w wyrażeniu regularnym komentarz można również zostały uznane przez wywołanie metody <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> — metoda i przekazanie jej <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> wartość wyliczenia.</span><span class="sxs-lookup"><span data-stu-id="91177-175">Note that, instead of providing the `(?x)` construct in the regular expression, the comment could also have been recognized by calling the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> method and passing it the <xref:System.Text.RegularExpressions.RegexOptions.IgnorePatternWhitespace?displayProperty=nameWithType> enumeration value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91177-176">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="91177-176">See Also</span></span>  
 [<span data-ttu-id="91177-177">Język wyrażeń regularnych — podręczny wykaz</span><span class="sxs-lookup"><span data-stu-id="91177-177">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)