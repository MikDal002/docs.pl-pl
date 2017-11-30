---
title: "Deklarowanie i wywoływanie zdarzeń (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bf75cfba5102be5d837af385e2d3578f78a03c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="794f2-102">Wskazówki: deklarowanie i wywoływanie zdarzeń (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="794f2-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="794f2-103">W tym przewodniku pokazano, jak deklarowanie i wywoływanie zdarzeń klasy o nazwie `Widget`.</span><span class="sxs-lookup"><span data-stu-id="794f2-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="794f2-104">Po wykonaniu kroków warto przeczytać temat Pomocnika [wskazówki: Obsługa zdarzeń](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), który wskazuje, jak używać zdarzeń z `Widget` obiektów, aby podać informacje o stanie w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="794f2-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="794f2-105">Klasa widżetu</span><span class="sxs-lookup"><span data-stu-id="794f2-105">The Widget Class</span></span>  
 <span data-ttu-id="794f2-106">Załóżmy na chwilę, że masz `Widget` klasy.</span><span class="sxs-lookup"><span data-stu-id="794f2-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="794f2-107">Twoje `Widget` klasa ma metodę, która może zająć dużo czasu na wykonanie i chcesz mieć możliwość wystawione określonego rodzaju zakończenia wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="794f2-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="794f2-108">Oczywiście można utworzyć `Widget` obiektu Wyświetla okno dialogowe procent wykonania, ale następnie użytkownik będzie zablokowany z tego okna dialogowego w każdym projekcie, w którym jest używana `Widget` klasy.</span><span class="sxs-lookup"><span data-stu-id="794f2-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="794f2-109">Dobrym zasada projektowania obiektu jest umożliwienie aplikacji, która używa dojścia obiektu interfejsu użytkownika — celem obiekt nie ma zarządzać formularza lub okna dialogowego.</span><span class="sxs-lookup"><span data-stu-id="794f2-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="794f2-110">Celem `Widget` jest wykonywanie innych zadań, dlatego zaleca się dodawania `PercentDone` zdarzeń i umożliwiają tej procedury, która wywołuje `Widget`do metod obsługi czy zdarzeń i wyświetlić stan aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="794f2-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="794f2-111">`PercentDone` Zdarzeń można też podać mechanizm anulowanie zadania.</span><span class="sxs-lookup"><span data-stu-id="794f2-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="794f2-112">Tworzenie, przykładów kodu dla tego tematu</span><span class="sxs-lookup"><span data-stu-id="794f2-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="794f2-113">Otwórz nowe [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] aplikacji systemu Windows projektu i tworzenie formularza o nazwie `Form1`.</span><span class="sxs-lookup"><span data-stu-id="794f2-113">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="794f2-114">Dodawanie dwóch przycisków i etykiet do `Form1`.</span><span class="sxs-lookup"><span data-stu-id="794f2-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="794f2-115">Nazwy obiektów, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="794f2-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="794f2-116">Obiekt</span><span class="sxs-lookup"><span data-stu-id="794f2-116">Object</span></span>|<span data-ttu-id="794f2-117">Właściwość</span><span class="sxs-lookup"><span data-stu-id="794f2-117">Property</span></span>|<span data-ttu-id="794f2-118">Ustawienie</span><span class="sxs-lookup"><span data-stu-id="794f2-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="794f2-119">Uruchom zadanie</span><span class="sxs-lookup"><span data-stu-id="794f2-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="794f2-120">Anuluj</span><span class="sxs-lookup"><span data-stu-id="794f2-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="794f2-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="794f2-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="794f2-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="794f2-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="794f2-123">Na **projektu** menu, wybierz **Dodaj klasę** Aby dodać klasę o nazwie `Widget.vb` do projektu.</span><span class="sxs-lookup"><span data-stu-id="794f2-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="794f2-124">Aby zadeklarować zdarzenia dla klasy widżetu</span><span class="sxs-lookup"><span data-stu-id="794f2-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="794f2-125">Użyj `Event` — słowo kluczowe, aby zadeklarować zdarzenia w `Widget` klasy.</span><span class="sxs-lookup"><span data-stu-id="794f2-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="794f2-126">Należy pamiętać, że zdarzenie może mieć `ByVal` i `ByRef` argumenty, jako `Widget`w `PercentDone` przedstawia zdarzenia:</span><span class="sxs-lookup"><span data-stu-id="794f2-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 <span data-ttu-id="794f2-127">Gdy obiekt wywołujący odbiera `PercentDone` zdarzenia `Percent` argument zawiera procent wykonania zadania.</span><span class="sxs-lookup"><span data-stu-id="794f2-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="794f2-128">`Cancel` Argument może być ustawiony `True` anulować metodę, która wywołała zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="794f2-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="794f2-129">Argumenty zdarzenia można zadeklarować tak samo, jak argumenty procedur z następującymi wyjątkami: zdarzenia nie mogą mieć `Optional` lub `ParamArray` argumentów i zdarzeń nie ma wartości zwracanych.</span><span class="sxs-lookup"><span data-stu-id="794f2-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="794f2-130">`PercentDone` Zdarzenie jest wywoływane przez `LongTask` metody `Widget` klasy.</span><span class="sxs-lookup"><span data-stu-id="794f2-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="794f2-131">`LongTask`przyjmuje dwa argumenty: czas metody udaje do realizacji pracy i czas minimalny czas, przed `LongTask` pauzy podnieść `PercentDone` zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="794f2-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="794f2-132">Aby zgłosić zdarzenie PercentDone</span><span class="sxs-lookup"><span data-stu-id="794f2-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="794f2-133">Aby uprościć dostęp do `Timer` Dodaj używane przez tę klasę, właściwości `Imports` instrukcji na początku sekcji deklaracji klasy modułu, powyżej `Class Widget` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="794f2-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  <span data-ttu-id="794f2-134">Dodaj następujący kod do `Widget` klasy:</span><span class="sxs-lookup"><span data-stu-id="794f2-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 <span data-ttu-id="794f2-135">Jeśli aplikacja wymaga `LongTask` metody `Widget` klasy zgłasza `PercentDone` zdarzeń co `MinimumInterval` sekund.</span><span class="sxs-lookup"><span data-stu-id="794f2-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="794f2-136">Po powrocie z zdarzenia `LongTask` sprawdza, czy `Cancel` ustawiono argument `True`.</span><span class="sxs-lookup"><span data-stu-id="794f2-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="794f2-137">W tym miejscu są niezbędne kilka zrzeczenie odpowiedzialności.</span><span class="sxs-lookup"><span data-stu-id="794f2-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="794f2-138">Dla uproszczenia `LongTask` procedurze przyjęto założenie, musisz wiedzieć z wyprzedzeniem, jak długo trwa zadania.</span><span class="sxs-lookup"><span data-stu-id="794f2-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="794f2-139">Prawie nigdy nie jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="794f2-139">This is almost never the case.</span></span> <span data-ttu-id="794f2-140">Dzielenie zadań na fragmentów parzystej rozmiar może być trudne i często przyjazny dla użytkowników jest po prostu ilość czasu, jaki upływa zanim uzyskają wskazanie, że coś jest przeprowadzana.</span><span class="sxs-lookup"><span data-stu-id="794f2-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="794f2-141">Inna wada może mieć wykrył w tym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="794f2-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="794f2-142">`Timer` Właściwość zwraca liczbę sekund, które zostały przekazane od północy; w związku z tym aplikacja zablokowała, jeśli zostanie uruchomiony bezpośrednio przed północy.</span><span class="sxs-lookup"><span data-stu-id="794f2-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="794f2-143">Bardziej dokładne podejście do pomiaru czasu przenoszące warunków ograniczających, takich jak ta pod uwagę lub ich uniknięcie, takich jak przy użyciu właściwości `Now`.</span><span class="sxs-lookup"><span data-stu-id="794f2-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="794f2-144">Teraz, gdy `Widget` klasy może wywoływać zdarzenia, można przenieść do następnego wskazówki.</span><span class="sxs-lookup"><span data-stu-id="794f2-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="794f2-145">[Wskazówki: Obsługa zdarzeń](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) przedstawiono sposób użycia `WithEvents` do skojarzenia z obsługi zdarzeń `PercentDone` zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="794f2-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794f2-146">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="794f2-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [<span data-ttu-id="794f2-147">Wskazówki: Obsługa zdarzeń</span><span class="sxs-lookup"><span data-stu-id="794f2-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [<span data-ttu-id="794f2-148">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="794f2-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)