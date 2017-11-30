---
title: "Optymalizacja wydajności: zasoby aplikacji"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ac462f3b49788fd909f9d9f4fc785db74704ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="optimizing-performance-application-resources"></a><span data-ttu-id="b8afe-102">Optymalizacja wydajności: zasoby aplikacji</span><span class="sxs-lookup"><span data-stu-id="b8afe-102">Optimizing Performance: Application Resources</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="b8afe-103">pozwala na udostępnianie zasobów aplikacji tak, aby między wpisane podobne elementy można obsługiwać spójny wygląd i zachowanie.</span><span class="sxs-lookup"><span data-stu-id="b8afe-103"> allows you to share application resources so that you can support a consistent look or behavior across similar-typed elements.</span></span> <span data-ttu-id="b8afe-104">Ten temat zawiera kilka zaleceń w tym obszarze, to może pomóc zwiększyć wydajność aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b8afe-104">This topic provides a few recommendations in this area that can help you improve the performance of your applications.</span></span>  
  
 <span data-ttu-id="b8afe-105">Aby uzyskać więcej informacji dotyczących zasobów, zobacz [zasobów XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="b8afe-105">For more information on resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
## <a name="sharing-resources"></a><span data-ttu-id="b8afe-106">Udostępnianie zasobów</span><span class="sxs-lookup"><span data-stu-id="b8afe-106">Sharing resources</span></span>  
 <span data-ttu-id="b8afe-107">Jeśli aplikacja korzysta z Kontrolki niestandardowe i definiuje zasobów w <xref:System.Windows.ResourceDictionary> (lub węzeł zasoby XAML), zaleca się albo zdefiniowania zasobów w <xref:System.Windows.Application> lub <xref:System.Windows.Window> obiekt poziom lub je zdefiniować w motyw domyślny dla Formanty niestandardowe.</span><span class="sxs-lookup"><span data-stu-id="b8afe-107">If your application uses custom controls and defines resources in a <xref:System.Windows.ResourceDictionary> (or XAML Resources node), it is recommended that you either define the resources at the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or define them in the default theme for the custom controls.</span></span> <span data-ttu-id="b8afe-108">Definiowanie zasobów w kontrolkę niestandardową <xref:System.Windows.ResourceDictionary> nakłada negatywny wpływ na wydajność dla każdego wystąpienia tego formantu.</span><span class="sxs-lookup"><span data-stu-id="b8afe-108">Defining resources in a custom control's <xref:System.Windows.ResourceDictionary> imposes a performance impact for every instance of that control.</span></span> <span data-ttu-id="b8afe-109">Na przykład jeśli masz pędzla intensywnie wydajności operacji zdefiniowane jako część definicji zasobu kontrolkę niestandardową oraz wiele wystąpień formantu niestandardowego zestawu roboczego aplikacji znacznie wzrośnie.</span><span class="sxs-lookup"><span data-stu-id="b8afe-109">For example, if you have performance-intensive brush operations defined as part of the resource definition of a custom control and many instances of the custom control, the application's working set will increase significantly.</span></span>  
  
 <span data-ttu-id="b8afe-110">Aby zilustrować ten punkt, należy rozważyć następujące kwestie.</span><span class="sxs-lookup"><span data-stu-id="b8afe-110">To illustrate this point, consider the following.</span></span> <span data-ttu-id="b8afe-111">Załóżmy, że tworzysz karty gier using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8afe-111">Let's say you are developing a card game using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="b8afe-112">Dla większości gier trzeba 52 kart o różnych powierzchni 52.</span><span class="sxs-lookup"><span data-stu-id="b8afe-112">For most card games, you need 52 cards with 52 different faces.</span></span> <span data-ttu-id="b8afe-113">Decyzję o implementacji niestandardowego formantu karty i zdefiniuj 52 pędzle (każdy reprezentuje krój karty) w zasobach formantu niestandardowego karty.</span><span class="sxs-lookup"><span data-stu-id="b8afe-113">You decide to implement a card custom control and you define 52 brushes (each representing a card face) in the resources of your card custom control.</span></span> <span data-ttu-id="b8afe-114">W głównej aplikacji początkowo utworzyć 52 wystąpień tej kontrolki niestandardowej karty.</span><span class="sxs-lookup"><span data-stu-id="b8afe-114">In your main application, you initially create 52 instances of this card custom control.</span></span> <span data-ttu-id="b8afe-115">Każde wystąpienie kontrolki niestandardowej karty generuje 52 wystąpienia <xref:System.Windows.Media.Brush> obiektów, które daje łączną liczbę 52 * 52 <xref:System.Windows.Media.Brush> obiektów w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="b8afe-115">Each instance of the card custom control generates 52 instances of <xref:System.Windows.Media.Brush> objects, which gives you a total of 52 * 52 <xref:System.Windows.Media.Brush> objects in your application.</span></span> <span data-ttu-id="b8afe-116">Przenosząc pędzle poza karty zasobów formantu niestandardowego do <xref:System.Windows.Application> lub <xref:System.Windows.Window> poziomie obiektu lub Definiowanie motyw domyślny dla kontrolki niestandardowej, można zmniejszyć zestaw roboczy aplikacji, ponieważ są teraz udostępnianie 52 pędzle wśród 52 wystąpienia formantu karty.</span><span class="sxs-lookup"><span data-stu-id="b8afe-116">By moving the brushes out of the card custom control resources to the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or defining them in the default theme for the custom control, you reduce the working set of the application, since you are now sharing the 52 brushes among 52 instances of the card control.</span></span>  
  
## <a name="sharing-a-brush-without-copying"></a><span data-ttu-id="b8afe-117">Udostępnianie pędzla bez kopiowania</span><span class="sxs-lookup"><span data-stu-id="b8afe-117">Sharing a Brush without Copying</span></span>  
 <span data-ttu-id="b8afe-118">Jeśli masz wiele elementów korzystającej z tego samego <xref:System.Windows.Media.Brush> obiektu, Zdefiniuj pędzel jako zasób i odwołać, a nie definiowanie w tekście pędzla w [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b8afe-118">If you have multiple elements using the same <xref:System.Windows.Media.Brush> object, define the brush as a resource and reference it, rather than defining the brush inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span> <span data-ttu-id="b8afe-119">Ta metoda będzie utworzyć jedno wystąpienie i ponownego wykorzystania, natomiast definiowanie w tekście pędzle w [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] tworzy nowe wystąpienie dla każdego elementu.</span><span class="sxs-lookup"><span data-stu-id="b8afe-119">This method will create one instance and reuse it, whereas defining brushes inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] creates a new instance for each element.</span></span>  
  
 <span data-ttu-id="b8afe-120">Poniższy przykładowy kod znaczników ilustruje tę sytuację:</span><span class="sxs-lookup"><span data-stu-id="b8afe-120">The following markup sample illustrates this point:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a><span data-ttu-id="b8afe-121">Korzystanie z zasobów statycznych, gdy jest to możliwe</span><span class="sxs-lookup"><span data-stu-id="b8afe-121">Use Static Resources when Possible</span></span>  
 <span data-ttu-id="b8afe-122">Zasób statycznej zapewnia wartość dla każdego atrybutu właściwości XAML wyszukując odwołanie do zasobu już zdefiniowane.</span><span class="sxs-lookup"><span data-stu-id="b8afe-122">A static resource provides a value for any XAML property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="b8afe-123">Zachowanie wyszukiwania dla tego zasobu jest odpowiednikiem wyszukiwania kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b8afe-123">Lookup behavior for that resource is analogous to compile-time lookup.</span></span>  
  
 <span data-ttu-id="b8afe-124">Zasób dynamicznej z drugiej strony, utworzy wyrażenia tymczasowego podczas początkowej kompilacji i w związku z tym odroczenie wyszukiwania zasobów, dopóki wartość żądany zasób nie zostanie faktycznie wymagane do utworzenia obiektu.</span><span class="sxs-lookup"><span data-stu-id="b8afe-124">A dynamic resource, on the other hand, will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="b8afe-125">Zachowanie wyszukiwania dla tego zasobu jest odpowiednikiem odnośników czasu wykonywania, która nakłada negatywny wpływ na wydajność.</span><span class="sxs-lookup"><span data-stu-id="b8afe-125">Lookup behavior for that resource is analogous to run-time lookup, which imposes a performance impact.</span></span> <span data-ttu-id="b8afe-126">Użyj zasoby statyczne, jeśli to możliwe w aplikacji, korzystając z zasobów dynamicznej tylko wtedy, gdy jest to konieczne.</span><span class="sxs-lookup"><span data-stu-id="b8afe-126">Use static resources whenever possible in your application, using dynamic resources only when necessary.</span></span>  
  
 <span data-ttu-id="b8afe-127">Poniższy przykładowy kod znaczników pokazano sposób użycia obu typów zasobów:</span><span class="sxs-lookup"><span data-stu-id="b8afe-127">The following markup sample shows the use of both types of resources:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a><span data-ttu-id="b8afe-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b8afe-128">See Also</span></span>  
 [<span data-ttu-id="b8afe-129">Optymalizacja wydajności aplikacji WPF</span><span class="sxs-lookup"><span data-stu-id="b8afe-129">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="b8afe-130">Planowanie wydajności aplikacji</span><span class="sxs-lookup"><span data-stu-id="b8afe-130">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [<span data-ttu-id="b8afe-131">Dzięki funkcji sprzętu</span><span class="sxs-lookup"><span data-stu-id="b8afe-131">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [<span data-ttu-id="b8afe-132">Układ i projekt</span><span class="sxs-lookup"><span data-stu-id="b8afe-132">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [<span data-ttu-id="b8afe-133">Grafika 2W i utworzenia obrazu</span><span class="sxs-lookup"><span data-stu-id="b8afe-133">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="b8afe-134">Zachowanie obiektu</span><span class="sxs-lookup"><span data-stu-id="b8afe-134">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [<span data-ttu-id="b8afe-135">Tekst</span><span class="sxs-lookup"><span data-stu-id="b8afe-135">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [<span data-ttu-id="b8afe-136">Powiązanie danych</span><span class="sxs-lookup"><span data-stu-id="b8afe-136">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [<span data-ttu-id="b8afe-137">Inne zalecenia dotyczące wydajności</span><span class="sxs-lookup"><span data-stu-id="b8afe-137">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)