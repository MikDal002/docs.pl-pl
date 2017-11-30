---
title: Metody typu System.String
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3cfddba1bfa7bf7cefba917be0026b1c366f3513
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="systemstring-methods"></a><span data-ttu-id="f1bdb-102">Metody typu System.String</span><span class="sxs-lookup"><span data-stu-id="f1bdb-102">System.String Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="f1bdb-103">nie obsługuje następujących <xref:System.String> metody.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-103"> does not support the following <xref:System.String> methods.</span></span>  
  
## <a name="unsupported-systemstring-methods-in-general"></a><span data-ttu-id="f1bdb-104">Ogólnie rzecz biorąc nieobsługiwany metod typu System.String</span><span class="sxs-lookup"><span data-stu-id="f1bdb-104">Unsupported System.String Methods in General</span></span>  
 <span data-ttu-id="f1bdb-105">Nieobsługiwany <xref:System.String> metody ogólne:</span><span class="sxs-lookup"><span data-stu-id="f1bdb-105">Unsupported <xref:System.String> methods in general:</span></span>  
  
-   <span data-ttu-id="f1bdb-106">Overloads pamiętać kultury (metody, które przyjmują `CultureInfo`  /  `StringComparison`  /  `IFormatProvider`).</span><span class="sxs-lookup"><span data-stu-id="f1bdb-106">Culture-aware overloads (methods that take a `CultureInfo` / `StringComparison` / `IFormatProvider`).</span></span>  
  
-   <span data-ttu-id="f1bdb-107">Metody zająć lub utworzyć `char` tablicy.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-107">Methods that take or produce a `char` array.</span></span>  
  
## <a name="unsupported-systemstring-static-methods"></a><span data-ttu-id="f1bdb-108">Metody nieobsługiwanego typu System.String statyczne</span><span class="sxs-lookup"><span data-stu-id="f1bdb-108">Unsupported System.String Static Methods</span></span>  
  
|<span data-ttu-id="f1bdb-109">Metody nieobsługiwanego typu System.String statyczne</span><span class="sxs-lookup"><span data-stu-id="f1bdb-109">Unsupported System.String Static Methods</span></span>|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a><span data-ttu-id="f1bdb-110">Nieobsługiwany System.String metod niestatycznych</span><span class="sxs-lookup"><span data-stu-id="f1bdb-110">Unsupported System.String Non-static Methods</span></span>  
  
|<span data-ttu-id="f1bdb-111">Nieobsługiwany System.String metod niestatycznych</span><span class="sxs-lookup"><span data-stu-id="f1bdb-111">Unsupported System.String Non-static Methods</span></span>|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="f1bdb-112">Różnice z platformy .NET</span><span class="sxs-lookup"><span data-stu-id="f1bdb-112">Differences from .NET</span></span>  
  
-   <span data-ttu-id="f1bdb-113">Sortowania programu SQL Server, które mogą obowiązywać na serwerze, a zatem będą dostarczać porównania z uwzględnieniem kultury, bez uwzględniania wielkości liter domyślnie nie uwzględniają zapytania.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-113">Queries do not account for SQL Server collations that might be in effect on the server, and therefore will provide culture-sensitive, case-insensitive comparisons by default.</span></span> <span data-ttu-id="f1bdb-114">To zachowanie różni się od domyślnej, z uwzględnieniem wielkości liter semantyki .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-114">This behavior differs from the default, case-sensitive semantics of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="f1bdb-115">Gdy `LastIndexOf` jest zwraca wartość 0, ciągiem `NULL` lub znaleziono pozycji wynosi 0.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-115">When `LastIndexOf` returns 0, either the string is `NULL` or the found position is 0.</span></span>  
  
-   <span data-ttu-id="f1bdb-116">Nieoczekiwane wyniki mogą być zwracane z łączenia lub inne operacje na ciągach o stałej długości (`CHAR`, `NCHAR`), ponieważ te typy mają automatycznie dopełnienie stosowane w bazie danych.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-116">Unexpected results might be returned from concatenation or other operations on fixed-length strings (`CHAR`, `NCHAR`), because these types automatically have padding applied in the database.</span></span>  
  
-   <span data-ttu-id="f1bdb-117">Ponieważ wiele metod, takich jak `Replace`, `ToLower`, `ToUpper`i indeksatora znak, ma nie prawidłowy Translacja `TEXT` lub `NTEXT` kolumn i XML, `SqlExceptions` wystąpić, jeśli translacji normalnie.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-117">Because many methods, such as `Replace`, `ToLower`, `ToUpper`, and the character indexer, have no valid translation for `TEXT` or `NTEXT` columns and XML, `SqlExceptions` occur if translated normally.</span></span> <span data-ttu-id="f1bdb-118">To zachowanie jest uważany za akceptowalne dla tych typów.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-118">This behavior is considered acceptable for these types.</span></span> <span data-ttu-id="f1bdb-119">Jednak wszystkie operacje na ciągach musi być zgodna wspólnego języka środowiska uruchomieniowego (języka wspólnego CLR) semantykę dla `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, i `NVARCHAR(max)`.</span><span class="sxs-lookup"><span data-stu-id="f1bdb-119">However, all string operations must match common language runtime (CLR) semantics for `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, and `NVARCHAR(max)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1bdb-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f1bdb-120">See Also</span></span>  
 [<span data-ttu-id="f1bdb-121">Typy danych i funkcje</span><span class="sxs-lookup"><span data-stu-id="f1bdb-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)