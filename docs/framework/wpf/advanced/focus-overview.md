---
title: "Przegląd Fokus"
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
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4e10f7136b636829f99da34388db7676810cd06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="focus-overview"></a><span data-ttu-id="8cf8a-102">Przegląd Fokus</span><span class="sxs-lookup"><span data-stu-id="8cf8a-102">Focus Overview</span></span>
<span data-ttu-id="8cf8a-103">W [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] istnieją dwa główne pojęcia, które odnoszą się do fokus: Klawiatura fokus i logiczny fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-103">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] there are two main concepts that pertain to focus: keyboard focus and logical focus.</span></span>  <span data-ttu-id="8cf8a-104">Fokus klawiatury odwołuje się do elementu, który odbiera klawiatury i logiczny fokus odwołuje się do elementu w zakresie fokus, który ma fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-104">Keyboard focus refers to the element that receives keyboard input and logical focus refers to the element in a focus scope that has focus.</span></span>  <span data-ttu-id="8cf8a-105">Pojęcia te omówiono szczegółowo w tym omówieniu.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-105">These concepts are discussed in detail in this overview.</span></span>  <span data-ttu-id="8cf8a-106">Opis różnicy w tych pojęć jest ważne w przypadku tworzenia złożonych aplikacji z wielu regionach, gdzie można uzyskać fokusu.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-106">Understanding the difference in these concepts is important for creating complex applications that have multiple regions where focus can be obtained.</span></span>  
  
 <span data-ttu-id="8cf8a-107">Główne kategorie, które uczestniczą w funkcje zarządzania są <xref:System.Windows.Input.Keyboard> klasy <xref:System.Windows.Input.FocusManager> klasy, a base element klas, takich jak <xref:System.Windows.UIElement> i <xref:System.Windows.ContentElement>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-107">The major classes that participate in focus management are the <xref:System.Windows.Input.Keyboard> class, the <xref:System.Windows.Input.FocusManager> class, and the base element classes, such as <xref:System.Windows.UIElement> and <xref:System.Windows.ContentElement>.</span></span>  <span data-ttu-id="8cf8a-108">Aby uzyskać więcej informacji na temat podstawowych elementów, zobacz [podstawowej Omówienie elementów](../../../../docs/framework/wpf/advanced/base-elements-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8cf8a-108">For more information about the base elements, see the [Base Elements Overview](../../../../docs/framework/wpf/advanced/base-elements-overview.md).</span></span>  
  
 <span data-ttu-id="8cf8a-109"><xref:System.Windows.Input.Keyboard> Klasy dotyczy głównie fokus klawiatury i <xref:System.Windows.Input.FocusManager> dotyczy przede wszystkim z logiczny fokus, ale nie jest bezwzględna różnicy.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-109">The <xref:System.Windows.Input.Keyboard> class is concerned primarily with keyboard focus and the <xref:System.Windows.Input.FocusManager> is concerned primarily with logical focus, but this is not an absolute distinction.</span></span>  <span data-ttu-id="8cf8a-110">Element, który ma fokus klawiatury będą także mieć logiczny fokus, ale element, który ma logiczny fokus nie ma fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-110">An element that has keyboard focus will also have logical focus, but an element that has logical focus does not necessarily have keyboard focus.</span></span>  <span data-ttu-id="8cf8a-111">To jest widoczny, gdy używasz <xref:System.Windows.Input.Keyboard> klasy można ustawić elementu, który ma fokus klawiatury dla niego ustawia również logiczny fokus w elemencie.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-111">This is apparent when you use the <xref:System.Windows.Input.Keyboard> class to set the element that has keyboard focus, for it also sets logical focus on the element.</span></span>  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a><span data-ttu-id="8cf8a-112">Fokus klawiatury</span><span class="sxs-lookup"><span data-stu-id="8cf8a-112">Keyboard Focus</span></span>  
 <span data-ttu-id="8cf8a-113">Fokus klawiatury odwołuje się do elementu, który jest obecnie odbieranie danych wprowadzonych z klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-113">Keyboard focus refers to the element that is currently receiving keyboard input.</span></span>  <span data-ttu-id="8cf8a-114">Może istnieć tylko jeden element na całej pulpitu, który ma fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-114">There can be only one element on the whole desktop that has keyboard focus.</span></span>  <span data-ttu-id="8cf8a-115">W [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ma element, który ma fokus klawiatury <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> ustawioną `true`.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-115">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], the element that has keyboard focus will have <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> set to `true`.</span></span>  <span data-ttu-id="8cf8a-116">Właściwość statyczna <xref:System.Windows.Input.Keyboard.FocusedElement%2A> na <xref:System.Windows.Input.Keyboard> klasy pobiera element, który aktualnie ma fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-116">The static property <xref:System.Windows.Input.Keyboard.FocusedElement%2A> on the <xref:System.Windows.Input.Keyboard> class gets the element that currently has keyboard focus.</span></span>  
  
 <span data-ttu-id="8cf8a-117">Aby element, aby uzyskać fokus klawiatury <xref:System.Windows.UIElement.Focusable%2A> i <xref:System.Windows.UIElement.IsVisible%2A> musi mieć wartość właściwości podstawowych elementów `true`.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-117">In order for an element to obtain keyboard focus, the <xref:System.Windows.UIElement.Focusable%2A> and the <xref:System.Windows.UIElement.IsVisible%2A> properties on the base elements must be set to `true`.</span></span>  <span data-ttu-id="8cf8a-118">Niektóre klasy, takich jak <xref:System.Windows.Controls.Panel> klasy podstawowej, mieć <xref:System.Windows.UIElement.Focusable%2A> ustawioną `false` domyślnie; w związku z tym należy ustawić <xref:System.Windows.UIElement.Focusable%2A> do `true` Jeśli chcesz, aby element, aby można było uzyskać fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-118">Some classes, such as the <xref:System.Windows.Controls.Panel> base class, have <xref:System.Windows.UIElement.Focusable%2A> set to `false` by default; therefore, you must set <xref:System.Windows.UIElement.Focusable%2A> to `true` if you want such an element to be able to obtain keyboard focus.</span></span>  
  
 <span data-ttu-id="8cf8a-119">Fokus klawiatury można uzyskać za pośrednictwem interakcji użytkowników z [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], na przykład klawisza TAB do elementu lub kliknięcie przycisku myszy w przypadku niektórych elementów.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-119">Keyboard focus can be obtained through user interaction with the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], such as tabbing to an element or clicking the mouse on certain elements.</span></span>  <span data-ttu-id="8cf8a-120">Fokus klawiatury również można uzyskać programistycznie przy użyciu <xref:System.Windows.Input.Keyboard.Focus%2A> metoda <xref:System.Windows.Input.Keyboard> klasy.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-120">Keyboard focus can also be obtained programmatically by using the <xref:System.Windows.Input.Keyboard.Focus%2A> method on the <xref:System.Windows.Input.Keyboard> class.</span></span>  <span data-ttu-id="8cf8a-121"><xref:System.Windows.Input.Keyboard.Focus%2A> Metody podejmuje próbę przekazania fokus klawiatury określonego elementu.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-121">The <xref:System.Windows.Input.Keyboard.Focus%2A> method attempts to give the specified element keyboard focus.</span></span>  <span data-ttu-id="8cf8a-122">Zwrócony element to element, który ma fokus klawiatury, która może być elementu innego niż wymagane, jeśli albo starego lub nowego skupić się Blok obiektu żądania.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-122">The returned element is the element that has keyboard focus, which might be a different element than requested if either the old or new focus object block the request.</span></span>  
  
 <span data-ttu-id="8cf8a-123">W poniższym przykładzie użyto <xref:System.Windows.Input.Keyboard.Focus%2A> metodę, aby ustawić fokus klawiatury na <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-123">The following example uses the <xref:System.Windows.Input.Keyboard.Focus%2A> method to set keyboard focus on a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 <span data-ttu-id="8cf8a-124"><xref:System.Windows.UIElement.IsKeyboardFocused%2A> Właściwości klasy podstawowej elementu pobiera wartość wskazującą, czy element ma fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-124">The <xref:System.Windows.UIElement.IsKeyboardFocused%2A> property on the base element classes gets a value indicating whether the element has keyboard focus.</span></span>  <span data-ttu-id="8cf8a-125"><xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> Właściwości klasy podstawowej elementu pobiera wartość wskazującą, czy element lub jeden z jego elementów podrzędnych visual ma fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-125">The <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> property on the base element classes gets a value indicating whether the element or any one of its visual child elements has keyboard focus.</span></span>  
  
 <span data-ttu-id="8cf8a-126">Podczas ustawiania początkowy fokus przy uruchamianiu aplikacji, element, aby ustawić fokusu musi być w drzewie wizualnym okna początkowego załadowanych przez aplikację, i musi mieć element <xref:System.Windows.UIElement.Focusable%2A> i <xref:System.Windows.UIElement.IsVisible%2A> ustawioną `true`.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-126">When setting initial focus at application startup, the element to receive focus must be in the visual tree of the initial window loaded by the application, and the element must have <xref:System.Windows.UIElement.Focusable%2A> and <xref:System.Windows.UIElement.IsVisible%2A> set to `true`.</span></span>  <span data-ttu-id="8cf8a-127">Zalecane miejsce, aby ustawić początkowy fokus znajduje się <xref:System.Windows.FrameworkElement.Loaded> obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-127">The recommended place to set initial focus is in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  <span data-ttu-id="8cf8a-128">A <xref:System.Windows.Threading.Dispatcher> wywołania zwrotnego może być również wykorzystywane przez wywołanie <xref:System.Windows.Threading.Dispatcher.Invoke%2A> lub <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-128">A <xref:System.Windows.Threading.Dispatcher> callback can also be used by calling <xref:System.Windows.Threading.Dispatcher.Invoke%2A> or <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.</span></span>  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a><span data-ttu-id="8cf8a-129">Logiczny fokus</span><span class="sxs-lookup"><span data-stu-id="8cf8a-129">Logical Focus</span></span>  
 <span data-ttu-id="8cf8a-130">Logiczny fokus odwołuje się do <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> w zakresie fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-130">Logical focus refers to the <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> in a focus scope.</span></span>  <span data-ttu-id="8cf8a-131">Zakres fokus jest element, który śledzi <xref:System.Windows.Input.FocusManager.FocusedElement%2A> w jego zakresie.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-131">A focus scope is an element that keeps track of the <xref:System.Windows.Input.FocusManager.FocusedElement%2A> within its scope.</span></span>  <span data-ttu-id="8cf8a-132">Gdy zakres fokus utraci fokus klawiatury, ukierunkowanych elementu utraci fokus klawiatury, ale zachowa logiczny fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-132">When keyboard focus leaves a focus scope, the focused element will lose keyboard focus but will retain logical focus.</span></span>  <span data-ttu-id="8cf8a-133">Po powrocie do zakresu fokus klawiatury ukierunkowanych element uzyska fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-133">When keyboard focus returns to the focus scope, the focused element will obtain keyboard focus.</span></span>  <span data-ttu-id="8cf8a-134">Dzięki temu dla fokus klawiatury zostanie zmieniony między wiele zakresów fokus, ale gwarantuje, że element skupiają się w zakresie fokus odzyskał fokus klawiatury, gdy nastąpi powrót do zakresu fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-134">This allows for keyboard focus to be changed between multiple focus scopes but ensures that the focused element in the focus scope regains keyboard focus when focus returns to the focus scope.</span></span>  
  
 <span data-ttu-id="8cf8a-135">Może istnieć wiele elementów, które ma logiczny fokus w aplikacji, ale może istnieć tylko jeden element, który ma logiczny fokus w zakresie określonego zespołu.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-135">There can be multiple elements that have logical focus in an application, but there may only be one element that has logical focus in a particular focus scope.</span></span>  
  
 <span data-ttu-id="8cf8a-136">Element, który ma fokus klawiatury ma logiczny fokus, dla której należy zakres fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-136">An element that has keyboard focus has logical focus for the focus scope it belongs to.</span></span>  
  
 <span data-ttu-id="8cf8a-137">Element można zmienić zakresu fokusu w [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] przez ustawienie <xref:System.Windows.Input.FocusManager> dołączona właściwość <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> do `true`.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-137">An element can be turned into a focus scope in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] by setting the <xref:System.Windows.Input.FocusManager> attached property <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> to `true`.</span></span>  <span data-ttu-id="8cf8a-138">W kodzie, element można włączyć w zakresie fokus przez wywołanie metody <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-138">In code, an element can be turned into a focus scope by calling <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.</span></span>  
  
 <span data-ttu-id="8cf8a-139">Poniższy przykład powoduje, że <xref:System.Windows.Controls.StackPanel> w zakresie fokus, ustawiając <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> dołączona właściwość.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-139">The following example makes a <xref:System.Windows.Controls.StackPanel> into a focus scope by setting the <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> attached property.</span></span>  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <span data-ttu-id="8cf8a-140"><xref:System.Windows.Input.FocusManager.GetFocusScope%2A>zwraca zakres fokus dla określonego elementu.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-140"><xref:System.Windows.Input.FocusManager.GetFocusScope%2A> returns the focus scope for the specified element.</span></span>  
  
 <span data-ttu-id="8cf8a-141">Klasy w [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , które są zakresów fokus domyślnie są <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, i <xref:System.Windows.Controls.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-141">Classes in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] which are focus scopes by default are <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, and <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
 <span data-ttu-id="8cf8a-142"><xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>pobiera element ukierunkowanych fokus określonego zakresu.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-142"><xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> gets the focused element for the specified focus scope.</span></span>  <span data-ttu-id="8cf8a-143"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>Ustawia element skupiają się w zakresie określonym fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-143"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> sets the focused element in the specified focus scope.</span></span>  <span data-ttu-id="8cf8a-144"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>zwykle służy do ustawiania początkowej elementem mającym fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-144"><xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> is typically used to set the initial focused element.</span></span>  
  
 <span data-ttu-id="8cf8a-145">Ustawia element skupiają się na zakres fokus, pobiera ukierunkowanych element zakresu fokusu w następującym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-145">The following example sets the focused element on a focus scope and gets the focused element of a focus scope.</span></span>  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a><span data-ttu-id="8cf8a-146">Nawigacji klawiatury</span><span class="sxs-lookup"><span data-stu-id="8cf8a-146">Keyboard Navigation</span></span>  
 <span data-ttu-id="8cf8a-147"><xref:System.Windows.Input.KeyboardNavigation> Klasy jest odpowiedzialny za Implementowanie nawigacji fokus klawiatury domyślne, gdy jeden z kluczy nawigacji zostanie naciśnięty.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-147">The <xref:System.Windows.Input.KeyboardNavigation> class is responsible for implementing default keyboard focus navigation when one of the navigation keys is pressed.</span></span>  <span data-ttu-id="8cf8a-148">Klawisze nawigacji są: klucze kartę, SHIFT + TAB klawiszy CTRL + TAB, CTRL + SHIFT + TAB, UPARROW, DOWNARROW, Strzałka w lewo i Strzałka w prawo.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-148">The navigation keys are: TAB, SHIFT+TAB, CTRL+TAB, CTRL+SHIFT+TAB, UPARROW, DOWNARROW, LEFTARROW, and RIGHTARROW keys.</span></span>  
  
 <span data-ttu-id="8cf8a-149">Zachowanie nawigacji kontenera nawigacji można zmienić ustawienie dołączonego <xref:System.Windows.Input.KeyboardNavigation> właściwości <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, i <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-149">The navigation behavior of a navigation container can be changed by setting the attached <xref:System.Windows.Input.KeyboardNavigation> properties <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, and <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.</span></span>  <span data-ttu-id="8cf8a-150">Te właściwości są typu <xref:System.Windows.Input.KeyboardNavigationMode> i możliwe wartości to <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, i <xref:System.Windows.Input.KeyboardNavigationMode.None>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-150">These properties are of type <xref:System.Windows.Input.KeyboardNavigationMode> and the possible values are <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, and <xref:System.Windows.Input.KeyboardNavigationMode.None>.</span></span>  <span data-ttu-id="8cf8a-151">Wartość domyślna to <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, co oznacza, że element nie jest kontenerem nawigacji.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-151">The default value is <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, which means the element is not a navigation container.</span></span>  
  
 <span data-ttu-id="8cf8a-152">Poniższy przykład tworzy <xref:System.Windows.Controls.Menu> o liczbie <xref:System.Windows.Controls.MenuItem> obiektów.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-152">The following example creates a <xref:System.Windows.Controls.Menu> with a number of <xref:System.Windows.Controls.MenuItem> objects.</span></span>  <span data-ttu-id="8cf8a-153"><xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> Ustawiono dołączona właściwość <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> na <xref:System.Windows.Controls.Menu>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-153">The <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> attached property is set to <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> on the <xref:System.Windows.Controls.Menu>.</span></span>  <span data-ttu-id="8cf8a-154">Gdy fokus zostanie zmieniona, za pomocą klawisza tab w <xref:System.Windows.Controls.Menu>, fokus zostanie przeniesiony z każdego elementu i po ostatnim elemencie osiągnięciu fokus zwraca pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-154">When focus is changed using the tab key within the <xref:System.Windows.Controls.Menu>, focus will move from each element and when the last element is reached focus will return to the first element.</span></span>  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a><span data-ttu-id="8cf8a-155">Nawigowanie po fokus programowo</span><span class="sxs-lookup"><span data-stu-id="8cf8a-155">Navigating Focus Programmatically</span></span>  
 <span data-ttu-id="8cf8a-156">Dodatkowe [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] do pracy z fokusem są <xref:System.Windows.UIElement.MoveFocus%2A> i <xref:System.Windows.UIElement.PredictFocus%2A>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-156">Additional [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to work with focus are <xref:System.Windows.UIElement.MoveFocus%2A> and <xref:System.Windows.UIElement.PredictFocus%2A>.</span></span>  
  
 <span data-ttu-id="8cf8a-157"><xref:System.Windows.FrameworkElement.MoveFocus%2A>zmiany fokus do następnego elementu w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-157"><xref:System.Windows.FrameworkElement.MoveFocus%2A> changes focus to the next element in the application.</span></span>  <span data-ttu-id="8cf8a-158">A <xref:System.Windows.Input.TraversalRequest> służy do określania kierunku.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-158">A <xref:System.Windows.Input.TraversalRequest> is used to specify the direction.</span></span>   <span data-ttu-id="8cf8a-159"><xref:System.Windows.Input.FocusNavigationDirection> Przekazany do <xref:System.Windows.UIElement.MoveFocus%2A> określa fokus różnych kierunkach można przenosić, takich jak <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> i <xref:System.Windows.Input.FocusNavigationDirection.Down>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-159">The <xref:System.Windows.Input.FocusNavigationDirection> passed to <xref:System.Windows.UIElement.MoveFocus%2A> specifies the different directions focus can be moved, such as <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> and <xref:System.Windows.Input.FocusNavigationDirection.Down>.</span></span>  
  
 <span data-ttu-id="8cf8a-160">W poniższym przykładzie użyto <xref:System.Windows.FrameworkElement.MoveFocus%2A> zmienić elementem mającym fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-160">The following example uses <xref:System.Windows.FrameworkElement.MoveFocus%2A> to change the focused element.</span></span>  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <span data-ttu-id="8cf8a-161"><xref:System.Windows.FrameworkElement.PredictFocus%2A>Zwraca obiekt, który będzie fokusu gdyby można zmienić fokus.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-161"><xref:System.Windows.FrameworkElement.PredictFocus%2A> returns the object which would receive focus if focus were to be changed.</span></span>  <span data-ttu-id="8cf8a-162">Obecnie tylko <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, i <xref:System.Windows.Input.FocusNavigationDirection.Right> są obsługiwane przez <xref:System.Windows.FrameworkElement.PredictFocus%2A>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-162">Currently, only <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, and <xref:System.Windows.Input.FocusNavigationDirection.Right> are supported by <xref:System.Windows.FrameworkElement.PredictFocus%2A>.</span></span>  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a><span data-ttu-id="8cf8a-163">Zdarzeń fokusu</span><span class="sxs-lookup"><span data-stu-id="8cf8a-163">Focus Events</span></span>  
 <span data-ttu-id="8cf8a-164">Zdarzenia związane z fokus klawiatury są <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> i <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-164">The events related to keyboard focus are <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> and <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.</span></span>  <span data-ttu-id="8cf8a-165">Zdarzenia są zdefiniowane jako dołączone zdarzenia na <xref:System.Windows.Input.Keyboard> klasy, ale są bardziej łatwo dostępne jako równoważne kierowane zdarzenia na base element klasy.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-165">The events are defined as attached events on the <xref:System.Windows.Input.Keyboard> class, but are more readily accessible as equivalent routed events on the base element classes.</span></span>  <span data-ttu-id="8cf8a-166">Aby uzyskać więcej informacji o zdarzeniach, zobacz [kierowane Przegląd zdarzeń](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8cf8a-166">For more information about events, see the [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).</span></span>  
  
 <span data-ttu-id="8cf8a-167"><xref:System.Windows.Input.Keyboard.GotKeyboardFocus>jest wywoływane, gdy element uzyskuje fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-167"><xref:System.Windows.Input.Keyboard.GotKeyboardFocus> is raised when the element obtains keyboard focus.</span></span>  <span data-ttu-id="8cf8a-168"><xref:System.Windows.Input.Keyboard.LostKeyboardFocus>jest wywoływane, gdy element traci fokus klawiatury.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-168"><xref:System.Windows.Input.Keyboard.LostKeyboardFocus> is raised when the element loses keyboard focus.</span></span>  <span data-ttu-id="8cf8a-169">Jeśli <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> zdarzenia lub <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> zdarzenie jest obsługiwane i <xref:System.Windows.RoutedEventArgs.Handled%2A> ma ustawioną wartość `true`, a następnie fokus nie spowoduje zmiany.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-169">If the <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> event or the <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> event is handled and <xref:System.Windows.RoutedEventArgs.Handled%2A> is set to `true`, then focus will not change.</span></span>  
  
 <span data-ttu-id="8cf8a-170">Poniższy przykład dołącza <xref:System.Windows.UIElement.GotKeyboardFocus> i <xref:System.Windows.UIElement.LostKeyboardFocus> procedury obsługi zdarzeń do <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-170">The following example attaches <xref:System.Windows.UIElement.GotKeyboardFocus> and <xref:System.Windows.UIElement.LostKeyboardFocus> event handlers to a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 <span data-ttu-id="8cf8a-171">Gdy <xref:System.Windows.Controls.TextBox> uzyskuje fokus klawiatury <xref:System.Windows.Controls.Control.Background%2A> właściwość <xref:System.Windows.Controls.TextBox> jest zmieniana na <xref:System.Windows.Media.Brushes.LightBlue%2A>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-171">When the <xref:System.Windows.Controls.TextBox> obtains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> property of the <xref:System.Windows.Controls.TextBox> is changed to <xref:System.Windows.Media.Brushes.LightBlue%2A>.</span></span>  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 <span data-ttu-id="8cf8a-172">Gdy <xref:System.Windows.Controls.TextBox> utraci fokus klawiatury <xref:System.Windows.Controls.Control.Background%2A> właściwość <xref:System.Windows.Controls.TextBox> zmieniony na biały.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-172">When the <xref:System.Windows.Controls.TextBox> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> property of the <xref:System.Windows.Controls.TextBox> is changed back to white.</span></span>  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 <span data-ttu-id="8cf8a-173">Zdarzenia związane z logiczny fokus są <xref:System.Windows.UIElement.GotFocus> i <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-173">The events related to logical focus are <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus>.</span></span>  <span data-ttu-id="8cf8a-174">Te zdarzenia są zdefiniowane w <xref:System.Windows.Input.FocusManager> jako dołączone zdarzenia, ale <xref:System.Windows.Input.FocusManager> nie ujawnia otoki zdarzenia CLR.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-174">These events are defined on the <xref:System.Windows.Input.FocusManager> as attached events, but the <xref:System.Windows.Input.FocusManager> does not expose CLR event wrappers.</span></span>  <span data-ttu-id="8cf8a-175"><xref:System.Windows.UIElement>i <xref:System.Windows.ContentElement> ułatwia udostępnianie tych zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="8cf8a-175"><xref:System.Windows.UIElement> and <xref:System.Windows.ContentElement> expose these events more conveniently.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf8a-176">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8cf8a-176">See Also</span></span>  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [<span data-ttu-id="8cf8a-177">Dane wejściowe — omówienie</span><span class="sxs-lookup"><span data-stu-id="8cf8a-177">Input Overview</span></span>](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [<span data-ttu-id="8cf8a-178">Przegląd podstawowych elementów</span><span class="sxs-lookup"><span data-stu-id="8cf8a-178">Base Elements Overview</span></span>](../../../../docs/framework/wpf/advanced/base-elements-overview.md)