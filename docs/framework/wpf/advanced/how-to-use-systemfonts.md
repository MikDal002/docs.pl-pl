---
title: 'Porady: korzystanie z SystemFonts'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce82724a4e9a547b8441628f43621f29eab6307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="bca1b-102">Porady: korzystanie z SystemFonts</span><span class="sxs-lookup"><span data-stu-id="bca1b-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="bca1b-103">W tym przykładzie pokazano, jak korzystać z zasobów statycznej <xref:System.Windows.SystemFonts> klasy do nadawania stylu lub dostosowywanie przycisku.</span><span class="sxs-lookup"><span data-stu-id="bca1b-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bca1b-104">Przykład</span><span class="sxs-lookup"><span data-stu-id="bca1b-104">Example</span></span>  
 <span data-ttu-id="bca1b-105">Zasoby systemowe ujawnia kilka określić systemu wartości jako właściwości i zasoby w celu ułatwienia tworzenia elementów wizualnych, które są zgodne z ustawieniami systemu.</span><span class="sxs-lookup"><span data-stu-id="bca1b-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="bca1b-106"><xref:System.Windows.SystemFonts>to klasa, która zawiera zarówno system czcionki wartości jako właściwości statycznych i właściwości, które odwołują się klucze zasobów, które mogą być używane do dostępu tych wartości dynamicznie w czasie wykonywania.</span><span class="sxs-lookup"><span data-stu-id="bca1b-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="bca1b-107">Na przykład <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> jest <xref:System.Windows.SystemFonts> wartości, i <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> jest odpowiedni klucz zasobów.</span><span class="sxs-lookup"><span data-stu-id="bca1b-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="bca1b-108">W [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], można użyć elementów członkowskich <xref:System.Windows.SystemFonts> jako statycznej właściwości lub odwołania do zasobów dynamicznych (o wartości właściwości statycznej jako klucz).</span><span class="sxs-lookup"><span data-stu-id="bca1b-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="bca1b-109">Odwołanie do zasobu dynamicznego należy użyć, jeśli Metryka czcionki mają być automatycznie aktualizowane podczas aplikacji działa; w przeciwnym razie użyj wartości statycznej odwołania.</span><span class="sxs-lookup"><span data-stu-id="bca1b-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bca1b-110">Klucze zasobów mieć sufiks "Klucz" dołączony do nazwy właściwości.</span><span class="sxs-lookup"><span data-stu-id="bca1b-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="bca1b-111">Poniższy przykład przedstawia sposób dostępu i użycia właściwości <xref:System.Windows.SystemFonts> jako wartości statyczne do nadawania stylu lub dostosowywanie przycisku.</span><span class="sxs-lookup"><span data-stu-id="bca1b-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="bca1b-112">W tym przykładzie znaczników przypisuje <xref:System.Windows.SystemFonts> wartości do przycisku.</span><span class="sxs-lookup"><span data-stu-id="bca1b-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="bca1b-113">Aby użyć wartości <xref:System.Windows.SystemFonts> w kodzie, nie trzeba używać wartość statyczną lub odwołaniem zasobu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="bca1b-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="bca1b-114">Zamiast tego użyj właściwości niekluczowe <xref:System.Windows.SystemFonts> klasy.</span><span class="sxs-lookup"><span data-stu-id="bca1b-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="bca1b-115">Mimo że właściwości niekluczowe pozornie są zdefiniowane jako właściwości statyczne, zachowanie środowiska wykonawczego [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] obsługiwanych przez system będzie obliczyć ponownie właściwości w czasie rzeczywistym i zostanie prawidłowo konta użytkownika driven zmiany wartości systemu.</span><span class="sxs-lookup"><span data-stu-id="bca1b-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="bca1b-116">Poniższy przykład przedstawia sposób określ ustawienia czcionki przycisku.</span><span class="sxs-lookup"><span data-stu-id="bca1b-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="bca1b-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bca1b-117">See Also</span></span>  
 <xref:System.Windows.SystemFonts>  
 [<span data-ttu-id="bca1b-118">Malowanie obszar o pędzla systemu</span><span class="sxs-lookup"><span data-stu-id="bca1b-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="bca1b-119">Użyj SystemParameters</span><span class="sxs-lookup"><span data-stu-id="bca1b-119">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="bca1b-120">Użyj klawiszy systemowych czcionek</span><span class="sxs-lookup"><span data-stu-id="bca1b-120">Use System Fonts Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [<span data-ttu-id="bca1b-121">Tematy porad</span><span class="sxs-lookup"><span data-stu-id="bca1b-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [<span data-ttu-id="bca1b-122">x: Static — rozszerzenie znaczników</span><span class="sxs-lookup"><span data-stu-id="bca1b-122">x:Static Markup Extension</span></span>](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [<span data-ttu-id="bca1b-123">Zasoby dla języka XAML</span><span class="sxs-lookup"><span data-stu-id="bca1b-123">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="bca1b-124">Rozszerzenie znaczników DynamicResource</span><span class="sxs-lookup"><span data-stu-id="bca1b-124">DynamicResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)