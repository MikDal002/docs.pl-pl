---
title: Stosowanie antyaliasingu do linii i krzywych
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d69d635fbdd8720937cd189826c1496b8126ddef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="10c9b-102">Stosowanie antyaliasingu do linii i krzywych</span><span class="sxs-lookup"><span data-stu-id="10c9b-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="10c9b-103">Jeśli używasz [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] do rysowania linii, podaj punkt początkowy i końcowy punkt wiersza, ale nie musisz podać wszystkie informacje o poszczególnych pikseli w wierszu.</span><span class="sxs-lookup"><span data-stu-id="10c9b-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="10c9b-104">działa w połączeniu z oprogramowaniem sterownik ekranu do określenia, które piksele zostanie włączona do wyświetlenia na urządzeniu określonego wiersza.</span><span class="sxs-lookup"><span data-stu-id="10c9b-104"> works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="10c9b-105">Aliasów</span><span class="sxs-lookup"><span data-stu-id="10c9b-105">Aliasing</span></span>  
 <span data-ttu-id="10c9b-106">Należy wziąć pod uwagę wprost red wiersza, który jest przesyłany z punktu (4, 2) w punkcie (16, 10).</span><span class="sxs-lookup"><span data-stu-id="10c9b-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="10c9b-107">Przykładowa współrzędnych ma swoją witryną źródłową w lewym górnym rogu i że jednostka miary piksela.</span><span class="sxs-lookup"><span data-stu-id="10c9b-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="10c9b-108">Założono także osi x punktów w dół w prawo i w punktach osi y.</span><span class="sxs-lookup"><span data-stu-id="10c9b-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="10c9b-109">Na poniższej ilustracji przedstawiono powiększania widoku czerwona linia rysowana na tle różnych kolorach.</span><span class="sxs-lookup"><span data-stu-id="10c9b-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="10c9b-110">![Wiersz, bez antialiasingu](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="10c9b-110">![Line, no antialiasing](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="10c9b-111">Czerwony pikseli, używany do renderowania wiersza są nieprzezroczyste.</span><span class="sxs-lookup"><span data-stu-id="10c9b-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="10c9b-112">W wierszu nie ma żadnych częściowo przezroczyste pikseli.</span><span class="sxs-lookup"><span data-stu-id="10c9b-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="10c9b-113">Tego typu linii renderowania daje wiersza nieregularne wygląd i wiersz wygląda nieco jak klatka schodowa.</span><span class="sxs-lookup"><span data-stu-id="10c9b-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="10c9b-114">Ta technika reprezentujących linię o klatka schodowa nosi nazwę aliasów; klatka schodowa jest aliasem teoretycznego wiersza.</span><span class="sxs-lookup"><span data-stu-id="10c9b-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="10c9b-115">Antialiasingu</span><span class="sxs-lookup"><span data-stu-id="10c9b-115">Antialiasing</span></span>  
 <span data-ttu-id="10c9b-116">Bardziej zaawansowane techniki renderowania linii polega na użyciu częściowo przezroczyste piksele wraz z nieprzezroczyste pikseli.</span><span class="sxs-lookup"><span data-stu-id="10c9b-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="10c9b-117">Pikseli są ustawione na czysty czerwony, lub do niektórych blend czerwony i kolor tła, w zależności od sposobu Zamknij znajdują się w wierszu.</span><span class="sxs-lookup"><span data-stu-id="10c9b-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="10c9b-118">Ten typ renderowania nosi antialiasingu i powoduje linii ludzkiego oka przewiduje jako bardziej smooth.</span><span class="sxs-lookup"><span data-stu-id="10c9b-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="10c9b-119">Na poniższej ilustracji przedstawiono, jak niektórych pikseli są mieszane do wyprodukowania linii antyaliasowany w tle.</span><span class="sxs-lookup"><span data-stu-id="10c9b-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="10c9b-120">![Antialiasing linii](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="10c9b-120">![Antialiasing a Line](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="10c9b-121">Antialiasing, nazywany również wygładzanie, dotyczą również krzywych.</span><span class="sxs-lookup"><span data-stu-id="10c9b-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="10c9b-122">Na poniższej ilustracji przedstawiono powiększania widoku wygładzonymi elipsy.</span><span class="sxs-lookup"><span data-stu-id="10c9b-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="10c9b-123">![Krzywe antialiasingu](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="10c9b-123">![Antialiasing Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="10c9b-124">Na poniższej ilustracji przedstawiono tego samego elipsy w rozmiarze rzeczywistym bez antialiasingu i drugi raz z antialiasingu.</span><span class="sxs-lookup"><span data-stu-id="10c9b-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="10c9b-125">![Przykład antialiasingu](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="10c9b-125">![Antialiasing example](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="10c9b-126">Rysowanie linii i krzywych, które używają antialiasingu, Utwórz wystąpienie <xref:System.Drawing.Graphics> klasy i ustawić jej <xref:System.Drawing.Graphics.SmoothingMode%2A> właściwości <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> lub <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span><span class="sxs-lookup"><span data-stu-id="10c9b-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="10c9b-127">Następnie wywołaj jednej z metod rysowania tego samego <xref:System.Drawing.Graphics> klasy.</span><span class="sxs-lookup"><span data-stu-id="10c9b-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="10c9b-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="10c9b-128">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>  
 [<span data-ttu-id="10c9b-129">Linie, krzywe i kształty</span><span class="sxs-lookup"><span data-stu-id="10c9b-129">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="10c9b-130">Porady: stosowanie antyaliasingu do tekstu</span><span class="sxs-lookup"><span data-stu-id="10c9b-130">How to: Use Antialiasing with Text</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)