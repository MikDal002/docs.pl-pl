---
title: "Numeric — Typ danych (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- integral types [Visual Basic], Visual Basic
- Short data type [Visual Basic], numeric data types
- Double data type [Visual Basic], numeric data types
- Long data type [Visual Basic], Visual Basic numeric data types
- numbers [Visual Basic], whole
- fractions
- numbers
- whole numbers
- integer numbers
- numbers [Visual Basic], integer
- fractional data types [Visual Basic]
- mantissas, of fractional numbers
- mantissas
- data types [Visual Basic], numeric
- Integer data type [Visual Basic], numeric data types
- exponent, of fractional numbers
- integers [Visual Basic]
- numeric data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], numeric types
- Decimal data type [Visual Basic], numeric data types
ms.assetid: a27bd4d0-7e14-43eb-9cc4-b42eaab323c9
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c185b7c04d589bfe74d1cca0c60df3e81ab80d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="numeric-data-types-visual-basic"></a><span data-ttu-id="bb743-102">Numeric — Typ danych (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb743-102">Numeric Data Types (Visual Basic)</span></span>
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="bb743-103">udostępnia kilka *numeryczne typy danych* do obsługi liczby w różnych reprezentacji.</span><span class="sxs-lookup"><span data-stu-id="bb743-103"> supplies several *numeric data types* for handling numbers in various representations.</span></span> <span data-ttu-id="bb743-104">*Całkowite* typy reprezentują tylko liczby całkowite (dodatnie, ujemne i zero), a *nonintegral* typy reprezentujące liczby z liczbą całkowitą i ułamkowych części.</span><span class="sxs-lookup"><span data-stu-id="bb743-104">*Integral* types represent only whole numbers (positive, negative, and zero), and *nonintegral* types represent numbers with both integer and fractional parts.</span></span>  
  
 <span data-ttu-id="bb743-105">Dla Tabela zawierająca porównanie side-by-side [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] , zobacz [typy danych](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span><span class="sxs-lookup"><span data-stu-id="bb743-105">For a table showing a side-by-side comparison of the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types, see [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).</span></span>  
  
## <a name="integral-numeric-types"></a><span data-ttu-id="bb743-106">Numeryczne typy całkowite</span><span class="sxs-lookup"><span data-stu-id="bb743-106">Integral Numeric Types</span></span>  
 <span data-ttu-id="bb743-107">*Typy całkowite danych* są tymi, które reprezentują tylko cyfry bez części ułamkowej.</span><span class="sxs-lookup"><span data-stu-id="bb743-107">*Integral data types* are those that represent only numbers without fractional parts.</span></span>  
  
 <span data-ttu-id="bb743-108">*Podpisany* są typy całkowite danych [SByte — typ danych](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8 bitów) [krótkich — typ danych](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-bitowy), [Integer — typ danych](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-bitowy) i [ Long — typ danych](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-bitowe).</span><span class="sxs-lookup"><span data-stu-id="bb743-108">The *signed* integral data types are [SByte Data Type](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md) (8-bit), [Short Data Type](../../../../visual-basic/language-reference/data-types/short-data-type.md) (16-bit), [Integer Data Type](../../../../visual-basic/language-reference/data-types/integer-data-type.md) (32-bit), and [Long Data Type](../../../../visual-basic/language-reference/data-types/long-data-type.md) (64-bit).</span></span> <span data-ttu-id="bb743-109">Jeśli zmienna zawsze przechowuje liczb całkowitych, a nie z liczbami ułamkowymi, należy zadeklarować go jako jednego z tych typów.</span><span class="sxs-lookup"><span data-stu-id="bb743-109">If a variable always stores integers rather than fractional numbers, declare it as one of these types.</span></span>  
  
 <span data-ttu-id="bb743-110">*Niepodpisane* są typy całkowite [Byte — typ danych](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8 bitów) [ushort — typ danych](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-bitowy), [uinteger — typ danych](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-bitowy) i [ Ulong — typ danych](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-bitowe).</span><span class="sxs-lookup"><span data-stu-id="bb743-110">The *unsigned* integral types are [Byte Data Type](../../../../visual-basic/language-reference/data-types/byte-data-type.md) (8-bit), [UShort Data Type](../../../../visual-basic/language-reference/data-types/ushort-data-type.md) (16-bit), [UInteger Data Type](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md) (32-bit), and [ULong Data Type](../../../../visual-basic/language-reference/data-types/ulong-data-type.md) (64-bit).</span></span> <span data-ttu-id="bb743-111">Jeśli zmienna zawiera dane binarne lub dane o charakterze nieznany, Zadeklaruj ją jako jeden z tych typów.</span><span class="sxs-lookup"><span data-stu-id="bb743-111">If a variable contains binary data, or data of unknown nature, declare it as one of these types.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="bb743-112">Wydajność</span><span class="sxs-lookup"><span data-stu-id="bb743-112">Performance</span></span>  
 <span data-ttu-id="bb743-113">Operacje arytmetyczne są szybsze z typów całkowitych od innych typów danych.</span><span class="sxs-lookup"><span data-stu-id="bb743-113">Arithmetic operations are faster with integral types than with other data types.</span></span> <span data-ttu-id="bb743-114">Są one najszybszym z `Integer` i `UInteger` typy w [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bb743-114">They are fastest with the `Integer` and `UInteger` types in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="large-integers"></a><span data-ttu-id="bb743-115">Dużej liczby całkowite</span><span class="sxs-lookup"><span data-stu-id="bb743-115">Large Integers</span></span>  
 <span data-ttu-id="bb743-116">Jeśli potrzebujesz do przechowywania liczbą całkowitą większą niż `Integer` może zawierać danych typu, możesz użyć `Long` zamiast tego typu danych.</span><span class="sxs-lookup"><span data-stu-id="bb743-116">If you need to hold an integer larger than the `Integer` data type can hold, you can use the `Long` data type instead.</span></span> <span data-ttu-id="bb743-117">`Long`zmienne może zawierać cyfry od-9,223,372,036,854,775,808 za pośrednictwem 9,223,372,036,854,775,807.</span><span class="sxs-lookup"><span data-stu-id="bb743-117">`Long` variables can hold numbers from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807.</span></span> <span data-ttu-id="bb743-118">Operacje z `Long` są nieco wolniej niż `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bb743-118">Operations with `Long` are slightly slower than with `Integer`.</span></span>  
  
 <span data-ttu-id="bb743-119">Jeśli potrzebujesz jeszcze większym wartości, możesz użyć [typu danych dziesiętnych](../../../../visual-basic/language-reference/data-types/decimal-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="bb743-119">If you need even larger values, you can use the [Decimal Data Type](../../../../visual-basic/language-reference/data-types/decimal-data-type.md).</span></span> <span data-ttu-id="bb743-120">Może zawierać cyfry od-79,228,162,514,264,337,593,543,950,335 za pośrednictwem 79,228,162,514,264,337,593,543,950,335 w `Decimal` zmiennej, jeśli nie używasz żadnych miejsc dziesiętnych.</span><span class="sxs-lookup"><span data-stu-id="bb743-120">You can hold numbers from -79,228,162,514,264,337,593,543,950,335 through 79,228,162,514,264,337,593,543,950,335 in a `Decimal` variable if you do not use any decimal places.</span></span> <span data-ttu-id="bb743-121">Jednak operacje przy użyciu `Decimal` liczby są znacznie wolniejsze niż w przypadku każdego typu danych liczbowych.</span><span class="sxs-lookup"><span data-stu-id="bb743-121">However, operations with `Decimal` numbers are considerably slower than with any other numeric data type.</span></span>  
  
### <a name="small-integers"></a><span data-ttu-id="bb743-122">Małej liczby całkowite</span><span class="sxs-lookup"><span data-stu-id="bb743-122">Small Integers</span></span>  
 <span data-ttu-id="bb743-123">Jeśli nie potrzebujesz pełnego zakresu `Integer` typu danych, można użyć `Short` typ danych, który może zawierać liczby całkowite od-32 768 do 32 767.</span><span class="sxs-lookup"><span data-stu-id="bb743-123">If you do not need the full range of the `Integer` data type, you can use the `Short` data type, which can hold integers from -32,768 through 32,767.</span></span> <span data-ttu-id="bb743-124">Aby uzyskać najmniejszą liczbą całkowitą `SByte` — typ danych przechowuje liczby całkowite od -128 do 127.</span><span class="sxs-lookup"><span data-stu-id="bb743-124">For the smallest integer range, the `SByte` data type holds integers from -128 through 127.</span></span> <span data-ttu-id="bb743-125">Jeśli masz dużą liczbę zmiennych zawierających małej liczby całkowite, czasem może przechowywać środowisko uruchomieniowe języka wspólnego programu `Short` i `SByte` zmienne wydajniej, a następnie zapisz zużycie pamięci.</span><span class="sxs-lookup"><span data-stu-id="bb743-125">If you have a very large number of variables that hold small integers, the common language runtime can sometimes store your `Short` and `SByte` variables more efficiently and save memory consumption.</span></span> <span data-ttu-id="bb743-126">Jednak operacje przy użyciu `Short` i `SByte` są nieco wolniej niż `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bb743-126">However, operations with `Short` and `SByte` are somewhat slower than with `Integer`.</span></span>  
  
### <a name="unsigned-integers"></a><span data-ttu-id="bb743-127">Liczb całkowitych bez znaku</span><span class="sxs-lookup"><span data-stu-id="bb743-127">Unsigned Integers</span></span>  
 <span data-ttu-id="bb743-128">Jeśli wiesz, że do zmiennej nigdy nie należy do przechowywania liczbą ujemną, możesz użyć *niepodpisanych typów*`Byte`, `UShort`, `UInteger`, i `ULong`.</span><span class="sxs-lookup"><span data-stu-id="bb743-128">If you know that your variable never needs to hold a negative number, you can use the *unsigned types*`Byte`, `UShort`, `UInteger`, and `ULong`.</span></span> <span data-ttu-id="bb743-129">Każdy z tych typów danych może zawierać dodatnią liczbą całkowitą dwa razy większy jako odpowiednie podpisany typ (`SByte`, `Short`, `Integer`, i `Long`).</span><span class="sxs-lookup"><span data-stu-id="bb743-129">Each of these data types can hold a positive integer twice as large as its corresponding signed type (`SByte`, `Short`, `Integer`, and `Long`).</span></span> <span data-ttu-id="bb743-130">Pod względem wydajności dokładnie tak wydajna, jak jego odpowiedniego typu ze znakiem jest każdego typu bez znaku.</span><span class="sxs-lookup"><span data-stu-id="bb743-130">In terms of performance, each unsigned type is exactly as efficient as its corresponding signed type.</span></span> <span data-ttu-id="bb743-131">W szczególności `UInteger` udostępnia `Integer` rozróżnienie jest najbardziej wydajnym wszystkie typy podstawowe dane liczbowe.</span><span class="sxs-lookup"><span data-stu-id="bb743-131">In particular, `UInteger` shares with `Integer` the distinction of being the most efficient of all the elementary numeric data types.</span></span>  
  
## <a name="nonintegral-numeric-types"></a><span data-ttu-id="bb743-132">Nonintegral typy liczbowe</span><span class="sxs-lookup"><span data-stu-id="bb743-132">Nonintegral Numeric Types</span></span>  
 <span data-ttu-id="bb743-133">*Typy danych nonintegral* to takie, które reprezentują liczb z liczbą całkowitą i ułamkowych części.</span><span class="sxs-lookup"><span data-stu-id="bb743-133">*Nonintegral data types* are those that represent numbers with both integer and fractional parts.</span></span>  
  
 <span data-ttu-id="bb743-134">Typy danych numerycznych nonintegral są `Decimal` (128-bitowego stałego punktu), [jednego typu danych](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-bitowych zmiennoprzecinkowych), i [Double — typ danych](../../../../visual-basic/language-reference/data-types/double-data-type.md) (punkt przestawne 64-bitowe).</span><span class="sxs-lookup"><span data-stu-id="bb743-134">The nonintegral numeric data types are `Decimal` (128-bit fixed point), [Single Data Type](../../../../visual-basic/language-reference/data-types/single-data-type.md) (32-bit floating point), and [Double Data Type](../../../../visual-basic/language-reference/data-types/double-data-type.md) (64-bit floating point).</span></span> <span data-ttu-id="bb743-135">Są one typy wszystko podpisane.</span><span class="sxs-lookup"><span data-stu-id="bb743-135">They are all signed types.</span></span> <span data-ttu-id="bb743-136">Jeśli zmienna może zawierać ułamek, Zadeklaruj ją jako jeden z tych typów.</span><span class="sxs-lookup"><span data-stu-id="bb743-136">If a variable can contain a fraction, declare it as one of these types.</span></span>  
  
 <span data-ttu-id="bb743-137">`Decimal`nie jest typem danych zmiennoprzecinkowych.</span><span class="sxs-lookup"><span data-stu-id="bb743-137">`Decimal` is not a floating-point data type.</span></span> <span data-ttu-id="bb743-138">`Decimal`liczby mają wartość całkowitą binarne i czynnik skalowania liczba całkowita, która określa, jaka część wartość jest ułamek dziesiętny.</span><span class="sxs-lookup"><span data-stu-id="bb743-138">`Decimal` numbers have a binary integer value and an integer scaling factor that specifies what portion of the value is a decimal fraction.</span></span>  
  
 <span data-ttu-id="bb743-139">Można użyć `Decimal` zmienne dla wartości pieniędzy.</span><span class="sxs-lookup"><span data-stu-id="bb743-139">You can use `Decimal` variables for money values.</span></span> <span data-ttu-id="bb743-140">Zaletą jest dokładność wartości.</span><span class="sxs-lookup"><span data-stu-id="bb743-140">The advantage is the precision of the values.</span></span> <span data-ttu-id="bb743-141">`Double` — Typ danych jest szybsze i wymaga mniej pamięci, ale podlega błędów zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="bb743-141">The `Double` data type is faster and requires less memory, but it is subject to rounding errors.</span></span> <span data-ttu-id="bb743-142">`Decimal` — Typ danych zachowuje pełną dokładność do 28 miejsc po przecinku.</span><span class="sxs-lookup"><span data-stu-id="bb743-142">The `Decimal` data type retains complete accuracy to 28 decimal places.</span></span>  
  
 <span data-ttu-id="bb743-143">Zmiennoprzecinkowe (`Single` i `Double`) liczby mają zakresy większych niż `Decimal` numery, ale mogą podlegać błędów zaokrąglania.</span><span class="sxs-lookup"><span data-stu-id="bb743-143">Floating-point (`Single` and `Double`) numbers have larger ranges than `Decimal` numbers but can be subject to rounding errors.</span></span> <span data-ttu-id="bb743-144">Typy zmiennoprzecinkowe obsługują mniejszą liczbę cyfr znaczących niż `Decimal` , ale może reprezentować wartości większe znaczenie.</span><span class="sxs-lookup"><span data-stu-id="bb743-144">Floating-point types support fewer significant digits than `Decimal` but can represent values of greater magnitude.</span></span>  
  
 <span data-ttu-id="bb743-145">Nonintegral wartości liczbowe może zostać wyrażona jako mmmEeee, w których jest mmm *mantysa* (cyfr znaczących) i jest See *wykładnik* (power 10).</span><span class="sxs-lookup"><span data-stu-id="bb743-145">Nonintegral number values can be expressed as mmmEeee, in which mmm is the *mantissa* (the significant digits) and eee is the *exponent* (a power of 10).</span></span> <span data-ttu-id="bb743-146">Najwyższej wartości dodatnie nonintegral typów są 7.9228162514264337593543950335E + 28 dla `Decimal`, 3.4028235E + 38 dla `Single`i 1.79769313486231570E + 308 do `Double`.</span><span class="sxs-lookup"><span data-stu-id="bb743-146">The highest positive values of the nonintegral types are 7.9228162514264337593543950335E+28 for `Decimal`, 3.4028235E+38 for `Single`, and 1.79769313486231570E+308 for `Double`.</span></span>  
  
### <a name="performance"></a><span data-ttu-id="bb743-147">Wydajność</span><span class="sxs-lookup"><span data-stu-id="bb743-147">Performance</span></span>  
 <span data-ttu-id="bb743-148">`Double`jest najbardziej wydajnym typy danych ułamkowych, ponieważ procesorów na platformach bieżącego wykonywania operacji zmiennoprzecinkowych w podwójnej precyzji.</span><span class="sxs-lookup"><span data-stu-id="bb743-148">`Double` is the most efficient of the fractional data types, because the processors on current platforms perform floating-point operations in double precision.</span></span> <span data-ttu-id="bb743-149">Jednak operacje przy użyciu `Double` nie są tak szybko, jak w przypadku typów całkowitych, takich jak `Integer`.</span><span class="sxs-lookup"><span data-stu-id="bb743-149">However, operations with `Double` are not as fast as with the integral types such as `Integer`.</span></span>  
  
### <a name="small-magnitudes"></a><span data-ttu-id="bb743-150">Małe wielkości</span><span class="sxs-lookup"><span data-stu-id="bb743-150">Small Magnitudes</span></span>  
 <span data-ttu-id="bb743-151">W przypadku numerów o najniższej wartości możliwe (znajdujący się najbliżej 0) `Double` zmienne można, przytrzymaj numery będzie jak - 4.94065645841246544E-324 dla wartości ujemnych i 4.94065645841246544E-324 dla wartości dodatnie.</span><span class="sxs-lookup"><span data-stu-id="bb743-151">For numbers with the smallest possible magnitude (closest to 0), `Double` variables can hold numbers as small as -4.94065645841246544E-324 for negative values and 4.94065645841246544E-324 for positive values.</span></span>  
  
### <a name="small-fractional-numbers"></a><span data-ttu-id="bb743-152">Mała liczb ułamkowych</span><span class="sxs-lookup"><span data-stu-id="bb743-152">Small Fractional Numbers</span></span>  
 <span data-ttu-id="bb743-153">Jeśli nie potrzebujesz pełnego zakresu `Double` typu danych, można użyć `Single` typ danych, który może zawierać liczb zmiennoprzecinkowych od - 3.4028235E + 38 za pośrednictwem 3.4028235E + 38.</span><span class="sxs-lookup"><span data-stu-id="bb743-153">If you do not need the full range of the `Double` data type, you can use the `Single` data type, which can hold floating-point numbers from -3.4028235E+38 through 3.4028235E+38.</span></span> <span data-ttu-id="bb743-154">Najmniejsza wielkości dla `Single` zmienne są - 1, 401298E-45 dla wartości ujemnych i 1, 401298E-45 dla wartości dodatnie.</span><span class="sxs-lookup"><span data-stu-id="bb743-154">The smallest magnitudes for `Single` variables are -1.401298E-45 for negative values and 1.401298E-45 for positive values.</span></span> <span data-ttu-id="bb743-155">Jeśli masz dużą liczbę zmiennych, mające mały liczb zmiennoprzecinkowych, czasem może przechowywać środowisko uruchomieniowe języka wspólnego programu `Single` zmienne wydajniej, a następnie zapisz zużycie pamięci.</span><span class="sxs-lookup"><span data-stu-id="bb743-155">If you have a very large number of variables that hold small floating-point numbers, the common language runtime can sometimes store your `Single` variables more efficiently and save memory consumption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb743-156">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bb743-156">See Also</span></span>  
 [<span data-ttu-id="bb743-157">Podstawowe typy danych</span><span class="sxs-lookup"><span data-stu-id="bb743-157">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [<span data-ttu-id="bb743-158">Znakowe typy danych</span><span class="sxs-lookup"><span data-stu-id="bb743-158">Character Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)  
 [<span data-ttu-id="bb743-159">Różne typy danych</span><span class="sxs-lookup"><span data-stu-id="bb743-159">Miscellaneous Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/miscellaneous-data-types.md)  
 [<span data-ttu-id="bb743-160">Rozwiązywanie problemów z typów danych</span><span class="sxs-lookup"><span data-stu-id="bb743-160">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="bb743-161">Porady: wywoływanie funkcji Windows wykorzystującej typy bez znaku</span><span class="sxs-lookup"><span data-stu-id="bb743-161">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)