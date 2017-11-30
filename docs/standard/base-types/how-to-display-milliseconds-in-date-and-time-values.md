---
title: "Porady: wyświetlanie ilości milisekund wartości daty i godziny"
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
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a><span data-ttu-id="b7bd8-102">Porady: wyświetlanie ilości milisekund wartości daty i godziny</span><span class="sxs-lookup"><span data-stu-id="b7bd8-102">How to: Display Milliseconds in Date and Time Values</span></span>
<span data-ttu-id="b7bd8-103">Domyślne metody formatowania daty i czasu, takie jak <xref:System.DateTime.ToString?displayProperty=nameWithType>, zawierają godziny, minuty i sekundy wartości czasu, ale wykluczają składnik milisekund.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-103">The default date and time formatting methods, such as <xref:System.DateTime.ToString?displayProperty=nameWithType>, include the hours, minutes, and seconds of a time value but exclude its milliseconds component.</span></span> <span data-ttu-id="b7bd8-104">W tym temacie pokazano jak dołączyć datę i składnik czasu w milisekundach w sformatowanym ciągu daty i czasu.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-104">This topic shows how to include a date and time's millisecond component in formatted date and time strings.</span></span>  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a><span data-ttu-id="b7bd8-105">Aby wyświetlić składnik milisekund wartości DateTime</span><span class="sxs-lookup"><span data-stu-id="b7bd8-105">To display the millisecond component of a DateTime value</span></span>  
  
1.  <span data-ttu-id="b7bd8-106">Jeśli pracujesz z ciągiem znaków reprezentującym datę, należy przekonwertować ciąg do wartości <xref:System.DateTime> lub <xref:System.DateTimeOffset> przy użyciu statycznej metody <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-106">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="b7bd8-107">W celu wyodrębnienia ciągu reprezentującego składnik czasu w milisekundach, należy wywołać wartość daty i godziny metody <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> lub <xref:System.DateTimeOffset.ToString%2A> i przekazać wzorzec w niestandardowym formacie `fff` lub `FFF`, oddzielnie lub z innym niestandardowym specyfikatorem formatu, jak parametr `format`.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-107">To extract the string representation of a time's millisecond component, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%2A> method, and pass the `fff` or `FFF` custom format pattern either alone or with other custom format specifiers as the `format` parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7bd8-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="b7bd8-108">Example</span></span>  
 <span data-ttu-id="b7bd8-109">W przykładzie wyświetlono składnik wartości milisekund <xref:System.DateTime> i <xref:System.DateTimeOffset> w konsoli, zarówno samodzielnie, jak i uwzględniając dłuższy ciąg daty i czasu.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-109">The example displays the millisecond component of a <xref:System.DateTime> and a <xref:System.DateTimeOffset> value to the console, both alone and included in a longer date and time string.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 <span data-ttu-id="b7bd8-110">Wzorzec formatu `fff` zawiera dowolne zera końcowe w wartościach milisekund.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-110">The `fff` format pattern includes any trailing zeros in the millisecond value.</span></span> <span data-ttu-id="b7bd8-111">Wzorzec formatu `FFF` pomija je.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-111">The `FFF` format pattern suppresses them.</span></span> <span data-ttu-id="b7bd8-112">Różnice tę ilustruje poniższy przykład.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-112">The difference is illustrated in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 <span data-ttu-id="b7bd8-113">Problemem przy definiowaniu kompletnego niestandardowego specyfikatora formatu, który zawiera składnik milisekund daty i czasu, jest to ze definiuje on format zakodowany, który może nie odpowiadać na rozmieszczenie elementów czasu bieżącej kultury w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-113">A problem with defining a complete custom format specifier that includes the millisecond component of a date and time is that it defines a hard-coded format that may not correspond to the arrangement of time elements in the application's current culture.</span></span> <span data-ttu-id="b7bd8-114">Lepszą alternatywą jest pobranie jednej daty i czasu wyświetlającej wzorzec określony przez obiekt bieżącej kultury <xref:System.Globalization.DateTimeFormatInfo> i zmodyfikować go, aby uwzględniał milisekundy.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-114">A better alternative is to retrieve one of the date and time display patterns defined by the current culture's <xref:System.Globalization.DateTimeFormatInfo> object and modify it to include milliseconds.</span></span> <span data-ttu-id="b7bd8-115">Ten przykład ilustruje takie podejście.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-115">The example also illustrates this approach.</span></span> <span data-ttu-id="b7bd8-116">Pobierany jest wzorzec pełnej daty i czasu dla bieżącej kultury z właściwości <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>, a następnie niestandardowy wzorzec `.ffff` jest wstawiany za wzorcem dla sekund.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-116">It retrieves the current culture's full date and time pattern from the <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> property, and then inserts the custom pattern `.ffff` after its seconds pattern.</span></span> <span data-ttu-id="b7bd8-117">Należy zauważyć, że w przykładzie użyto wyrażenia regularnego do wykonania tej operacji w pojedynczym wywołaniu metody.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-117">Note that the example uses a regular expression to perform this operation in a single method call.</span></span>  
  
 <span data-ttu-id="b7bd8-118">Aby wyświetlić część ułamkową sekund innych niż milisekund można określić specyfikator formatu niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-118">You can also use a custom format specifier to display a fractional part of seconds other than milliseconds.</span></span> <span data-ttu-id="b7bd8-119">Na przykład niestandardowy specyfikator formatu `f` lub `F` wyświetla część dziesiętną sekund, niestandardowy specyfikator formatu `ff` lub `FF` wyświetla setną część sekund, natomiast niestandardowy specyfikator formatu `ffff` lub `FFFF` wyświetla część tysięczną sekund.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-119">For example, the `f` or `F` custom format specifier displays tenths of a second, the `ff` or `FF` custom format specifier displays hundredths of a second, and the `ffff` or `FFFF` custom format specifier displays ten thousandths of a second.</span></span> <span data-ttu-id="b7bd8-120">Części ułamkowe milisekund są obcinane w zwracanym ciągu zamiast zaokrąglane.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-120">Fractional parts of a millisecond are truncated instead of rounded in the returned string.</span></span> <span data-ttu-id="b7bd8-121">W poniższym przykładzie są używane następujące specyfikatory formatu.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-121">These format specifiers are used in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="b7bd8-122">Istnieje możliwość wyświetlania bardzo małych części ułamkowych sekund, takie jak tysięczne sekund lub sto tysięczne sekund.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-122">It is possible to display very small fractional units of a second, such as ten thousandths of a second or hundred-thousandths of a second.</span></span> <span data-ttu-id="b7bd8-123">Jednak te wartości mogą być nieistotne.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-123">However, these values may not be meaningful.</span></span> <span data-ttu-id="b7bd8-124">Dokładność wartości daty i godziny zależy od rozdzielczości zegara systemu.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-124">The precision of date and time values depends on the resolution of the system clock.</span></span> <span data-ttu-id="b7bd8-125">W systemach operacyjnych Windows NT 3.5 (i późniejszych) oraz [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], rozdzielczość zegara wynosi około 10-15 milisekund.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-125">On Windows NT 3.5 and later, and [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] operating systems, the clock's resolution is approximately 10-15 milliseconds.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b7bd8-126">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="b7bd8-126">Compiling the Code</span></span>  
 <span data-ttu-id="b7bd8-127">Skompiluj kod w wierszu polecenia za pomocą csc.exe lub vb.exe.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-127">Compile the code at the command line using csc.exe or vb.exe.</span></span> <span data-ttu-id="b7bd8-128">Aby skompilować kod w [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], należy umieścić go w szablonie projektu aplikacji konsolowej.</span><span class="sxs-lookup"><span data-stu-id="b7bd8-128">To compile the code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], put it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bd8-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b7bd8-129">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="b7bd8-130">Niestandardowa data i godzina ciągi formatujące</span><span class="sxs-lookup"><span data-stu-id="b7bd8-130">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)