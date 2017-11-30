---
title: Zasoby i kod
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
- keys [WPF], using objects as
- resources [WPF], accessing from procedural code
- procedural code [WPF], creating resources with
- procedural code [WPF], accessing resources from
- resources [WPF], creating with procedural code
ms.assetid: c1cfcddb-e39c-41c8-a7f3-60984914dfae
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1177f7eeb2b6184ea6ae0a021730658913a4794b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="resources-and-code"></a><span data-ttu-id="d36db-102">Zasoby i kod</span><span class="sxs-lookup"><span data-stu-id="d36db-102">Resources and Code</span></span>
<span data-ttu-id="d36db-103">To omówienie koncentruje się na temat [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] zasobów można uzyskać dostępu do lub utworzone za pomocą kodu zamiast [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] składni.</span><span class="sxs-lookup"><span data-stu-id="d36db-103">This overview concentrates on how [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] resources can be accessed or created using  code rather than [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] syntax.</span></span> <span data-ttu-id="d36db-104">Aby uzyskać więcej informacji na temat użycia zasobów ogólne i zasoby z [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] perspektywy składni, zobacz [zasobów XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="d36db-104">For more information on general resource usage and resources from a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] syntax perspective, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
  
  
<a name="accessing"></a>   
## <a name="accessing-resources-from-code"></a><span data-ttu-id="d36db-105">Uzyskiwanie dostępu do zasobów z kodu</span><span class="sxs-lookup"><span data-stu-id="d36db-105">Accessing Resources from Code</span></span>  
 <span data-ttu-id="d36db-106">Zidentyfikuj zasoby, jeśli są one zdefiniowane za pomocą kluczy [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] są również używane do pobierania określonych zasobów, jeśli żądanie zasobu w kodzie.</span><span class="sxs-lookup"><span data-stu-id="d36db-106">The keys that identify resources if they are defined through [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] are also used to retrieve specific resources if you request the resource in code.</span></span> <span data-ttu-id="d36db-107">Najprostszym sposobem, aby pobrać zasobu z kodu jest wywołać albo <xref:System.Windows.FrameworkElement.FindResource%2A> lub <xref:System.Windows.FrameworkElement.TryFindResource%2A> metody z obiektów o poziomie struktury w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d36db-107">The simplest way to retrieve a resource from code is to call either the <xref:System.Windows.FrameworkElement.FindResource%2A> or the <xref:System.Windows.FrameworkElement.TryFindResource%2A> method from framework-level objects in your application.</span></span> <span data-ttu-id="d36db-108">Behawioralnej różnią te metody się, co się stanie, jeśli nie odnaleziono żądanego klucza.</span><span class="sxs-lookup"><span data-stu-id="d36db-108">The behavioral difference between these methods is what happens if the requested key is not found.</span></span> <span data-ttu-id="d36db-109"><xref:System.Windows.FrameworkElement.FindResource%2A>zgłasza wyjątek; <xref:System.Windows.FrameworkElement.TryFindResource%2A> nie generuje wyjątku lecz zwraca `null`.</span><span class="sxs-lookup"><span data-stu-id="d36db-109"><xref:System.Windows.FrameworkElement.FindResource%2A> raises an exception; <xref:System.Windows.FrameworkElement.TryFindResource%2A> will not raise an exception but returns `null`.</span></span> <span data-ttu-id="d36db-110">Każda metoda przyjmuje jako parametr wejściowy klucz zasobu i zwraca obiekt słabo typizowana.</span><span class="sxs-lookup"><span data-stu-id="d36db-110">Each method takes the resource key as an input parameter, and returns a loosely typed object.</span></span> <span data-ttu-id="d36db-111">Zazwyczaj klucz zasobu jest ciągiem, ale ma typu okazjonalne użycia; zobacz [przy użyciu obiektów jako klucze](#objectaskey) sekcji, aby uzyskać szczegółowe informacje.</span><span class="sxs-lookup"><span data-stu-id="d36db-111">Typically, a resource key is a string, but there are occasional nonstring usages; see the [Using Objects as Keys](#objectaskey) section for details.</span></span> <span data-ttu-id="d36db-112">Zwykle będzie rzutować zwróconego obiektu na typ wymagany przez właściwość ustawieniu podczas żądania do zasobu.</span><span class="sxs-lookup"><span data-stu-id="d36db-112">Typically you would cast the returned object to the type required by the property that you are setting when requesting the resource.</span></span> <span data-ttu-id="d36db-113">Logika wyszukiwania do rozpoznania zasobu kodu jest taka sama jak odwołanie do zasobu dynamicznego [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] case.</span><span class="sxs-lookup"><span data-stu-id="d36db-113">The lookup logic for code resource resolution is the same as the dynamic resource reference [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] case.</span></span> <span data-ttu-id="d36db-114">Wyszukaj zasoby rozpoczyna się od elementu wywołującego, a następnie w dalszym ciągu elementy nadrzędne kolejnych w drzewie logicznym.</span><span class="sxs-lookup"><span data-stu-id="d36db-114">The search for resources starts from the calling element, then continues to successive parent elements in the logical tree.</span></span> <span data-ttu-id="d36db-115">Wyszukiwanie i jego nowszych wersjach nadal do zasobów aplikacji, kompozycje i zasobów systemowych, jeśli to konieczne.</span><span class="sxs-lookup"><span data-stu-id="d36db-115">The lookup continues onwards into application resources, themes, and system resources if necessary.</span></span> <span data-ttu-id="d36db-116">Żądanie kodu dla zasobu zostaną prawidłowo konto do zmiany środowiska uruchomieniowego w słownikach zasobów, które może zostały wprowadzone po tym słownik zasobów ładowana z [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], a także do zmiany zasobów systemu w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="d36db-116">A code request for a resource will properly account for runtime changes in resource dictionaries that might have been made subsequent to that resource dictionary being loaded from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], and also for realtime system resource changes.</span></span>  
  
 <span data-ttu-id="d36db-117">Przykład kodu krótki, wyszukuje zasób według klucza, który używa zwrócona wartość można ustawić właściwości, zaimplementowane jako <xref:System.Windows.Controls.Primitives.ButtonBase.Click> obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="d36db-117">The following is a brief code example that finds a resource by key and uses the returned value to set a property, implemented as a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler.</span></span>  
  
 [!code-csharp[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page3.xaml.cs#resourceproceduralget)]
 [!code-vb[PropertiesOvwSupport#ResourceProceduralGet](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page3.xaml.vb#resourceproceduralget)]  
  
 <span data-ttu-id="d36db-118">Alternatywną metodą przypisywania odwołania zasobu jest <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.</span><span class="sxs-lookup"><span data-stu-id="d36db-118">An alternative method for assigning a resource reference is <xref:System.Windows.FrameworkElement.SetResourceReference%2A>.</span></span> <span data-ttu-id="d36db-119">Ta metoda przyjmuje dwa parametry: klucz zasobu oraz identyfikatora właściwości zależności w szczególności w wystąpieniu elementu, do której można przypisać wartości zasobów.</span><span class="sxs-lookup"><span data-stu-id="d36db-119">This method takes two parameters: the key of the resource, and the identifier for a particular dependency property that is present on the element instance to which the resource value should be assigned.</span></span> <span data-ttu-id="d36db-120">Funkcjonalnym ta metoda jest taka sama i daje możliwość nie wymaga żadnych Rzutowanie wartości zwracanych.</span><span class="sxs-lookup"><span data-stu-id="d36db-120">Functionally, this method is the same and has the advantage of not requiring any casting of return values.</span></span>  
  
 <span data-ttu-id="d36db-121">Inny sposób programowy dostęp do zasobów ma dostępu do zawartości <xref:System.Windows.FrameworkElement.Resources%2A> właściwości w formie słownika.</span><span class="sxs-lookup"><span data-stu-id="d36db-121">Still another way to access resources programmatically is to access the contents of the <xref:System.Windows.FrameworkElement.Resources%2A> property as a dictionary.</span></span> <span data-ttu-id="d36db-122">Uzyskiwanie dostępu do słownika zawarty w tej właściwości jest również, jak dodać nowych zasobów do istniejącej kolekcji, sprawdź, czy podana nazwa klucza jest już zajęty w kolekcji i innych operacji słownika/kolekcji.</span><span class="sxs-lookup"><span data-stu-id="d36db-122">Accessing the dictionary contained by this property is also how you can add new resources to existing collections, check to see if a given key name is already taken in the collection, and other dictionary/collection operations.</span></span> <span data-ttu-id="d36db-123">Jeśli piszesz [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikacji całkowicie w kodzie, możesz można również utworzyć całą kolekcję w kodzie, przypisać kluczy, a następnie przypisz kolekcję gotowych do <xref:System.Windows.FrameworkElement.Resources%2A> właściwość elementu ustalonych.</span><span class="sxs-lookup"><span data-stu-id="d36db-123">If you are writing a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application entirely in code, you can also create the entire collection in code, assign keys to it, and then assign the finished collection to the <xref:System.Windows.FrameworkElement.Resources%2A> property of an established element.</span></span> <span data-ttu-id="d36db-124">Będzie to opisana w następnej sekcji.</span><span class="sxs-lookup"><span data-stu-id="d36db-124">This will be described in the next section.</span></span>  
  
 <span data-ttu-id="d36db-125">Może indeksować w żadnej podanej <xref:System.Windows.FrameworkElement.Resources%2A> kolekcji, przy użyciu określonego klucza jako indeks, ale należy zwrócić uwagę, że dostęp do zasobu w ten sposób nie zgodne z regułami normalne środowiska uruchomieniowego rozpoznawania zasobów.</span><span class="sxs-lookup"><span data-stu-id="d36db-125">You can index within any given <xref:System.Windows.FrameworkElement.Resources%2A> collection, using a specific key as the index, but you should be aware that accessing the resource in this way does not follow the normal runtime rules of resource resolution.</span></span> <span data-ttu-id="d36db-126">Tylko uzyskujesz dostęp do tej określonej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="d36db-126">You are only accessing that particular collection.</span></span> <span data-ttu-id="d36db-127">Wyszukiwania zasobów zostanie nie można przechodzących przez zakres do katalogu głównego lub aplikacji Jeśli znaleziono nie prawidłowego obiektu żądanego klucza.</span><span class="sxs-lookup"><span data-stu-id="d36db-127">Resource lookup will not be traversing the scope to the root or the application if no valid object was found at the requested key.</span></span> <span data-ttu-id="d36db-128">Takie podejście może jednak zawierać zalety wydajności w niektórych przypadkach mówiąc, ponieważ zakres wyszukiwania dla klucza jest bardziej ograniczone.</span><span class="sxs-lookup"><span data-stu-id="d36db-128">However, this approach may have performance advantages in some cases precisely because the scope of the search for the key is more constrained.</span></span> <span data-ttu-id="d36db-129">Zobacz <xref:System.Windows.ResourceDictionary> klasy, aby uzyskać więcej informacji na temat pracy z słownika zasobów bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="d36db-129">See the <xref:System.Windows.ResourceDictionary> class for more details on how to work with the resource dictionary directly.</span></span>  
  
<a name="creating"></a>   
## <a name="creating-resources-with-code"></a><span data-ttu-id="d36db-130">Tworzenie zasobów z kodem</span><span class="sxs-lookup"><span data-stu-id="d36db-130">Creating Resources with Code</span></span>  
 <span data-ttu-id="d36db-131">Jeśli chcesz utworzyć cały [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplikacji w kodzie, można także utworzyć wszystkie zasoby w tej aplikacji w kodzie.</span><span class="sxs-lookup"><span data-stu-id="d36db-131">If you want to create an entire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application in code, you might also want to create any resources in that application in code.</span></span> <span data-ttu-id="d36db-132">Aby to osiągnąć, Utwórz nową <xref:System.Windows.ResourceDictionary> wystąpienia, a następnie dodaj wszystkie zasoby do słownika przy użyciu kolejnych wywołań <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d36db-132">To achieve this, create a new <xref:System.Windows.ResourceDictionary> instance, and then add all the resources to the dictionary using successive calls to <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d36db-133">Następnie należy użyć <xref:System.Windows.ResourceDictionary> utworzony w ten sposób, aby ustawić <xref:System.Windows.FrameworkElement.Resources%2A> właściwości w elemencie, który znajduje się w zakresie strony lub <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d36db-133">Then, use the <xref:System.Windows.ResourceDictionary> thus created to set the <xref:System.Windows.FrameworkElement.Resources%2A> property on an element that is present in a page scope, or the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d36db-134">Można również obsługa <xref:System.Windows.ResourceDictionary> jako obiektu autonomicznego bez dodawania go do elementu.</span><span class="sxs-lookup"><span data-stu-id="d36db-134">You could also maintain the <xref:System.Windows.ResourceDictionary> as a standalone object without adding it to an element.</span></span> <span data-ttu-id="d36db-135">Jednak jeśli to zrobisz, można musi uzyskać dostęp do zasobów w niej według klucza elementu, tak jakby był on słownika ogólnego.</span><span class="sxs-lookup"><span data-stu-id="d36db-135">However, if you do this, you must access the resources within it by item key, as if it were a generic dictionary.</span></span> <span data-ttu-id="d36db-136">A <xref:System.Windows.ResourceDictionary> nie jest dołączony do elementu `Resources` właściwość czy istnieje jako część elementu drzewa i ma żaden zakres w sekwencji wyszukiwania, które mogą być używane przez <xref:System.Windows.FrameworkElement.FindResource%2A> i związanych z metod.</span><span class="sxs-lookup"><span data-stu-id="d36db-136">A <xref:System.Windows.ResourceDictionary> that is not attached to an element `Resources` property would not  exist as part of the element tree and has no scope in a lookup sequence that can be used by <xref:System.Windows.FrameworkElement.FindResource%2A> and related methods.</span></span>  
  
<a name="objectaskey"></a>   
## <a name="using-objects-as-keys"></a><span data-ttu-id="d36db-137">Jako klucze przy użyciu obiektów</span><span class="sxs-lookup"><span data-stu-id="d36db-137">Using Objects as Keys</span></span>  
 <span data-ttu-id="d36db-138">Większość użycia zasobów ustawi klucz zasób powinien być ciągiem.</span><span class="sxs-lookup"><span data-stu-id="d36db-138">Most resource usages will set the key of the resource to be a string.</span></span> <span data-ttu-id="d36db-139">Jednak różnych [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funkcje celowo nie należy używać typu ciąg do określenia klucze, zamiast tego parametru jest obiektem.</span><span class="sxs-lookup"><span data-stu-id="d36db-139">However, various [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features deliberately do not use a string type to specify keys, instead this parameter is an object.</span></span> <span data-ttu-id="d36db-140">Możliwość wystąpienia zasobu trzeba wprowadzić przez obiekt jest używany przez [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Obsługa stylów i motywów.</span><span class="sxs-lookup"><span data-stu-id="d36db-140">The capability of having the resource be keyed by an object is used by the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] style and theming support.</span></span> <span data-ttu-id="d36db-141">Style w kompozycje, które stają się domyślny styl formantu w przeciwnym razie nie stylem każdego określonemu przez <xref:System.Type> którego ma być stosowana do formantu.</span><span class="sxs-lookup"><span data-stu-id="d36db-141">The styles in themes which become the default style for an otherwise non-styled control are each keyed by the <xref:System.Type> of the control that they should apply to.</span></span> <span data-ttu-id="d36db-142">Trwa wyznaczaną przez typ zapewnia mechanizm niezawodnej wyszukiwania, który działa na wystąpień poszczególnych typów kontroli i typu może być wykrywane przez odbicie i używane do zdefiniowania stylów klas pochodnych, nawet jeśli typ pochodny, w przeciwnym razie ma żaden styl domyślny.</span><span class="sxs-lookup"><span data-stu-id="d36db-142">Being keyed by type provides a reliable lookup mechanism that works on default instances of each control type, and type can be detected by reflection and used for styling derived classes even though the derived type otherwise has no default style.</span></span> <span data-ttu-id="d36db-143">Można określić <xref:System.Type> klucza zdefiniowane w zasobu [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] za pomocą [x: Type — rozszerzenie znaczników](../../../../docs/framework/xaml-services/x-type-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d36db-143">You can specify a <xref:System.Type> key for a resource defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] by using the [x:Type Markup Extension](../../../../docs/framework/xaml-services/x-type-markup-extension.md).</span></span> <span data-ttu-id="d36db-144">Podobne rozszerzenia istnieją inne użycia klucza typu, które obsługują [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] funkcje, takie jak [ComponentResourceKey — rozszerzenie znaczników](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="d36db-144">Similar extensions exist for other nonstring key usages that support [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features, such as [ComponentResourceKey Markup Extension](../../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36db-145">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d36db-145">See Also</span></span>  
 [<span data-ttu-id="d36db-146">Zasoby dla języka XAML</span><span class="sxs-lookup"><span data-stu-id="d36db-146">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="d36db-147">Style i tworzenia szablonów</span><span class="sxs-lookup"><span data-stu-id="d36db-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)