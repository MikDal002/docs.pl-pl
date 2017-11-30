---
title: "Peverify.exe (narzędzie PEVerify)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 855a1122eb4507912adca80878f78258b37d202d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="8a418-102">Peverify.exe (narzędzie PEVerify)</span><span class="sxs-lookup"><span data-stu-id="8a418-102">Peverify.exe (PEVerify Tool)</span></span>
<span data-ttu-id="8a418-103">Narzędzie PEVerify pomaga deweloperom, którzy generują język Microsoft intermediate language (MSIL) (na przykład twórcom kompilatorów, deweloperom aparatów skryptów itd.), w ustalaniu, czy ich kod MSIL i związane z nim metadane spełniają wymogi bezpieczeństwa typu.</span><span class="sxs-lookup"><span data-stu-id="8a418-103">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers, script engine developers, and so on) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="8a418-104">Niektóre kompilatory generują weryfikowalny kod bezpieczny ze względu na typy tylko wtedy, gdy unika się używania pewnych konstrukcji języka.</span><span class="sxs-lookup"><span data-stu-id="8a418-104">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="8a418-105">Jeśli jako programista używasz takiego kompilatora, możesz chcieć sprawdzić, czy nie występują zagrożenia bezpieczeństwa typów kodu.</span><span class="sxs-lookup"><span data-stu-id="8a418-105">If, as a developer, you are using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="8a418-106">W tej sytuacji możesz uruchomić narzędzie PEVerify, aby sprawdzić MSIL i metadane plików.</span><span class="sxs-lookup"><span data-stu-id="8a418-106">In this situation, you can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="8a418-107">To narzędzie jest instalowane automatycznie z programem Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8a418-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="8a418-108">Aby uruchomić narzędzie, należy użyć wiersza polecenia dewelopera (lub wiersza polecenia programu Visual Studio w systemie Windows 7).</span><span class="sxs-lookup"><span data-stu-id="8a418-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="8a418-109">Aby uzyskać więcej informacji, zobacz [wiersze polecenia](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8a418-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="8a418-110">W wierszu polecenia wpisz następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="8a418-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a418-111">Składnia</span><span class="sxs-lookup"><span data-stu-id="8a418-111">Syntax</span></span>  
  
```  
peverify filename [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a418-112">Parametry</span><span class="sxs-lookup"><span data-stu-id="8a418-112">Parameters</span></span>  
  
|<span data-ttu-id="8a418-113">Argument</span><span class="sxs-lookup"><span data-stu-id="8a418-113">Argument</span></span>|<span data-ttu-id="8a418-114">Opis</span><span class="sxs-lookup"><span data-stu-id="8a418-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8a418-115">*Nazwa pliku*</span><span class="sxs-lookup"><span data-stu-id="8a418-115">*filename*</span></span>|<span data-ttu-id="8a418-116">Przenośny plik wykonywalny (PE), który ma zostać sprawdzony pod kątem języka MSIL i metadanych.</span><span class="sxs-lookup"><span data-stu-id="8a418-116">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="8a418-117">Opcja</span><span class="sxs-lookup"><span data-stu-id="8a418-117">Option</span></span>|<span data-ttu-id="8a418-118">Opis</span><span class="sxs-lookup"><span data-stu-id="8a418-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8a418-119">**/ Podziel =** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="8a418-119">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="8a418-120">Przerywa weryfikacji po *maxErrorCount* błędy.</span><span class="sxs-lookup"><span data-stu-id="8a418-120">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="8a418-121">Ten parametr nie jest obsługiwany w .NET Framework w wersji 2.0 lub wyższej.</span><span class="sxs-lookup"><span data-stu-id="8a418-121">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="8a418-122">**/Clock**</span><span class="sxs-lookup"><span data-stu-id="8a418-122">**/clock**</span></span>|<span data-ttu-id="8a418-123">Mierzy i raportuje następujące czasy weryfikacji w milisekundach:</span><span class="sxs-lookup"><span data-stu-id="8a418-123">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="8a418-124">**Cykl MD Val.**</span><span class="sxs-lookup"><span data-stu-id="8a418-124">**MD Val. cycle**</span></span><br /> <span data-ttu-id="8a418-125">Cykl sprawdzania poprawności metadanych</span><span class="sxs-lookup"><span data-stu-id="8a418-125">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="8a418-126">**MD Val. czysty**</span><span class="sxs-lookup"><span data-stu-id="8a418-126">**MD Val. pure**</span></span><br /> <span data-ttu-id="8a418-127">Czysty czas sprawdzania poprawności metadanych</span><span class="sxs-lookup"><span data-stu-id="8a418-127">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="8a418-128">**Cykl wersja IL**</span><span class="sxs-lookup"><span data-stu-id="8a418-128">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="8a418-129">Cykli weryfikacji języka pośredniego firmy Microsoft (MSIL)</span><span class="sxs-lookup"><span data-stu-id="8a418-129">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="8a418-130">**Czysty Ver IL**</span><span class="sxs-lookup"><span data-stu-id="8a418-130">**IL Ver pure**</span></span><br /> <span data-ttu-id="8a418-131">Czysty czas weryfikacji języka MSIL</span><span class="sxs-lookup"><span data-stu-id="8a418-131">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="8a418-132">**Cyklu MD Val.** i **cyklu wersja IL** razy obejmuje czasu wymaganego do wykonania niezbędnych procedur uruchamiania i wyłączania.</span><span class="sxs-lookup"><span data-stu-id="8a418-132">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="8a418-133">**Val. MD czysty** i **Ver IL czysty** razy uwzględnienia czasu wymagane do przeprowadzenia weryfikacji lub tylko weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="8a418-133">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="8a418-134">**/ Help**</span><span class="sxs-lookup"><span data-stu-id="8a418-134">**/help**</span></span>|<span data-ttu-id="8a418-135">Wyświetla składnię polecenia i opcje narzędzia.</span><span class="sxs-lookup"><span data-stu-id="8a418-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="8a418-136">**/HRESULT**</span><span class="sxs-lookup"><span data-stu-id="8a418-136">**/hresult**</span></span>|<span data-ttu-id="8a418-137">Wyświetla kody błędów w formacie szesnastkowym.</span><span class="sxs-lookup"><span data-stu-id="8a418-137">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="8a418-138">**/ Ignoruj =** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="8a418-138">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="8a418-139">Ignoruje wymienione kody błędów.</span><span class="sxs-lookup"><span data-stu-id="8a418-139">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="8a418-140">**/ Ignoruj = @** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="8a418-140">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="8a418-141">Ignoruje kody błędów wymienione w określonym pliku odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="8a418-141">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="8a418-142">**/Il**</span><span class="sxs-lookup"><span data-stu-id="8a418-142">**/il**</span></span>|<span data-ttu-id="8a418-143">Sprawdza MSIL typu bezpieczeństwa weryfikacji dla metod zaimplementowanych w zestawie określony przez *filename*.</span><span class="sxs-lookup"><span data-stu-id="8a418-143">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="8a418-144">Narzędzie zwraca szczegółowy opis każdego problemu znaleziono, chyba że zostanie **/quiet** opcji.</span><span class="sxs-lookup"><span data-stu-id="8a418-144">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="8a418-145">**/ / MD**</span><span class="sxs-lookup"><span data-stu-id="8a418-145">**/md**</span></span>|<span data-ttu-id="8a418-146">Przeprowadza weryfikację metadanych dla zestawu określony przez *filename*.</span><span class="sxs-lookup"><span data-stu-id="8a418-146">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="8a418-147">Oznacza to przejrzenie pełnej struktury metadanych w pliku i raportowanie wszystkich napotkanych problemów.</span><span class="sxs-lookup"><span data-stu-id="8a418-147">This walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="8a418-148">**/ nologo**</span><span class="sxs-lookup"><span data-stu-id="8a418-148">**/nologo**</span></span>|<span data-ttu-id="8a418-149">Pomija wyświetlanie informacji o wersji i prawach autorskich produktu.</span><span class="sxs-lookup"><span data-stu-id="8a418-149">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="8a418-150">**/nosymbols**</span><span class="sxs-lookup"><span data-stu-id="8a418-150">**/nosymbols**</span></span>|<span data-ttu-id="8a418-151">W wersji 2.0 .NET Framework wyłącza numery wierszy w celu zapewnienia zgodności z poprzednimi wersjami.</span><span class="sxs-lookup"><span data-stu-id="8a418-151">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="8a418-152">**/ quiet**</span><span class="sxs-lookup"><span data-stu-id="8a418-152">**/quiet**</span></span>|<span data-ttu-id="8a418-153">Określa tryb cichy. Wyłącza raportowanie problemów weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="8a418-153">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="8a418-154">Peverify.exe w dalszym ciągu raportuje, czy plik jest bezpiecznych pod względem typów, ale nie raportuje problemów uniemożliwiających weryfikację bezpieczeństwa typów.</span><span class="sxs-lookup"><span data-stu-id="8a418-154">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="8a418-155">Weryfikuje tylko metody przezroczyste.</span><span class="sxs-lookup"><span data-stu-id="8a418-155">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="8a418-156">**/ unique**</span><span class="sxs-lookup"><span data-stu-id="8a418-156">**/unique**</span></span>|<span data-ttu-id="8a418-157">Ignoruje powtarzające się kody błędów.</span><span class="sxs-lookup"><span data-stu-id="8a418-157">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="8a418-158">**/ verbose**</span><span class="sxs-lookup"><span data-stu-id="8a418-158">**/verbose**</span></span>|<span data-ttu-id="8a418-159">W .NET Framework w wersji 2.0 wyświetla dodatkowe informacje w komunikatach weryfikacji MSIL.</span><span class="sxs-lookup"><span data-stu-id="8a418-159">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="8a418-160">**/?**</span><span class="sxs-lookup"><span data-stu-id="8a418-160">**/?**</span></span>|<span data-ttu-id="8a418-161">Wyświetla składnię polecenia i opcje narzędzia.</span><span class="sxs-lookup"><span data-stu-id="8a418-161">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a418-162">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8a418-162">Remarks</span></span>  
 <span data-ttu-id="8a418-163">Środowisko uruchomieniowe języka wspólnego opiera się na wykonywaniu kodu aplikacji bezpiecznego pod kątem typów, aby ułatwić wymuszanie stosowania mechanizmów zabezpieczeń i izolacji.</span><span class="sxs-lookup"><span data-stu-id="8a418-163">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="8a418-164">Zazwyczaj kod, który nie jest [sprawdzalnie bezpieczny typ](http://msdn.microsoft.com/en-us/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc) nie można uruchomić, chociaż można ustawić zasady zabezpieczeń, aby umożliwić wykonywanie kodu zaufane, ale niemożliwy.</span><span class="sxs-lookup"><span data-stu-id="8a418-164">Normally, code that is not [verifiably type safe](http://msdn.microsoft.com/en-us/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="8a418-165">Jeśli żadna **/ / MD** ani **/il** opcje są określone, Peverify.exe wykonuje obu typów kontroli.</span><span class="sxs-lookup"><span data-stu-id="8a418-165">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="8a418-166">Wykonuje Peverify.exe **/ / MD** najpierw sprawdza.</span><span class="sxs-lookup"><span data-stu-id="8a418-166">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="8a418-167">Jeśli nie ma żadnych błędów **/il** kontroli.</span><span class="sxs-lookup"><span data-stu-id="8a418-167">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="8a418-168">Jeśli możesz określić ich obu **/ / MD** i **/il**, **/il** sprawdzane jest nawet, jeśli występują błędy w metadanych.</span><span class="sxs-lookup"><span data-stu-id="8a418-168">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="8a418-169">W związku z tym, jeśli nie ma żadnych błędów metadanych **peverify** *filename* jest odpowiednikiem **peverify** *filename* **/ / MD** **/il**.</span><span class="sxs-lookup"><span data-stu-id="8a418-169">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="8a418-170">Peverify.exe wykonuje kompleksową weryfikację MSIL na podstawie analizy przepływu danych oraz listy kilkuset reguł poprawności metadanych.</span><span class="sxs-lookup"><span data-stu-id="8a418-170">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="8a418-171">Aby uzyskać szczegółowe informacje na temat testów wykonuje Peverify.exe, zobacz specyfikację"Weryfikacja metadanych" i "MSIL instrukcji ustawić specyfikację" w folderze Narzędzia przewodnik dla deweloperów w [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a418-171">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="8a418-172">Zauważ, że .NET Framework w wersji 2.0 lub nowszej obsługuje weryfikowalny `byref` zwraca określone z poniższymi instrukcjami MSIL: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` i `unbox`.</span><span class="sxs-lookup"><span data-stu-id="8a418-172">Note that the .NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8a418-173">Przykłady</span><span class="sxs-lookup"><span data-stu-id="8a418-173">Examples</span></span>  
 <span data-ttu-id="8a418-174">Polecenie wykonuje sprawdzanie poprawności metadanych i MSIL typu bezpieczeństwa weryfikację dla metod zaimplementowanych w zestawie `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="8a418-174">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="8a418-175">Po pomyślnym zrealizowaniu powyższego żądania Peverify.exe wyświetla następujący komunikat.</span><span class="sxs-lookup"><span data-stu-id="8a418-175">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="8a418-176">Polecenie wykonuje sprawdzanie poprawności metadanych i MSIL typu bezpieczeństwa weryfikację dla metod zaimplementowanych w zestawie `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="8a418-176">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="8a418-177">Narzędzie wyświetla czas potrzebny do wykonywania tych sprawdzeń.</span><span class="sxs-lookup"><span data-stu-id="8a418-177">The tool displays the time required to perform these checks.</span></span>  
  
```  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="8a418-178">Po pomyślnym zrealizowaniu powyższego żądania Peverify.exe wyświetla następujący komunikat.</span><span class="sxs-lookup"><span data-stu-id="8a418-178">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="8a418-179">Polecenie wykonuje sprawdzanie poprawności metadanych i MSIL typu bezpieczeństwa weryfikację dla metod zaimplementowanych w zestawie `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="8a418-179">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="8a418-180">Peverify.exe zatrzymuje się jednak, gdy liczba błędów przekroczy 100.</span><span class="sxs-lookup"><span data-stu-id="8a418-180">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="8a418-181">Narzędzie ignoruje także wymienione kody błędów.</span><span class="sxs-lookup"><span data-stu-id="8a418-181">The tool also ignores the specified error codes.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="8a418-182">Poniższe polecenie tworzy taki sam efekt co w poprzednim przykładzie powyżej, ale Określa kody błędów, aby zignorować w pliku odpowiedzi `ignoreErrors.rsp`.</span><span class="sxs-lookup"><span data-stu-id="8a418-182">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="8a418-183">Plik odpowiedzi może zawierać rozdzielaną przecinkami listę kodów błędów.</span><span class="sxs-lookup"><span data-stu-id="8a418-183">The response file can contain a comma-separated list of error codes.</span></span>  
  
```  
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="8a418-184">Można też sformatować plik odpowiedzi, podając każdy kod błędu w osobnym wierszu.</span><span class="sxs-lookup"><span data-stu-id="8a418-184">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```  
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a418-185">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8a418-185">See Also</span></span>  
 [<span data-ttu-id="8a418-186">Narzędzia</span><span class="sxs-lookup"><span data-stu-id="8a418-186">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="8a418-187">NIB: Sprawdzalnie bezpieczny kod zapisywania</span><span class="sxs-lookup"><span data-stu-id="8a418-187">NIB: Writing Verifiably Type-Safe Code</span></span>](http://msdn.microsoft.com/en-us/d18f10ef-3b48-4f47-8726-96714021547b)  
 [<span data-ttu-id="8a418-188">Typ bezpieczeństwa i zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="8a418-188">Type Safety and Security</span></span>](http://msdn.microsoft.com/en-us/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc)  
 [<span data-ttu-id="8a418-189">Wiersz polecenia</span><span class="sxs-lookup"><span data-stu-id="8a418-189">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)