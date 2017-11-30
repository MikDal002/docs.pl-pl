---
title: "Konfigurowanie projektów (F #)"
description: "Dowiedz się, jak podczas pracy z projektów F # w programie Visual Studio za pomocą projektanta projektu."
keywords: "Visual f #, f #, funkcjonalności programowania"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8b2ed206-34e4-4256-a6ce-0c2499561165
ms.openlocfilehash: d2a92f725c40443c8dc6af593d28deccd3ee88de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-projects-in-visual-studio"></a><span data-ttu-id="5d11b-104">Konfigurowanie projektów programu Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5d11b-104">Configuring Projects in Visual Studio</span></span>

> [!NOTE]
<span data-ttu-id="5d11b-105">W tym artykule nie jest aktualny najnowsze Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5d11b-105">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="5d11b-106">Zostaną zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="5d11b-106">It will be updated.</span></span>

<span data-ttu-id="5d11b-107">Ten temat zawiera informacje o sposobie używania **projektanta projektu** podczas pracy z projektów F #.</span><span class="sxs-lookup"><span data-stu-id="5d11b-107">This topic includes information about how to use the **Project Designer** when you work with F# projects.</span></span> <span data-ttu-id="5d11b-108">Korzystanie z projektów F # nie jest znacznie różni się od Praca z projektami Visual Basic lub C#.</span><span class="sxs-lookup"><span data-stu-id="5d11b-108">Working with F# projects is not significantly different from working with Visual Basic or C# projects.</span></span> <span data-ttu-id="5d11b-109">Dokumentacja ogólna projektu programu Visual Studio można użyć jako odwołanie do podstawowej często, korzystając z języka F #.</span><span class="sxs-lookup"><span data-stu-id="5d11b-109">You can often use the general Visual Studio project documentation as your primary reference when you use F#.</span></span> <span data-ttu-id="5d11b-110">W tym temacie zawiera linki do odpowiednich informacji w dokumentacji programu Visual Studio dla ustawień, które są współużytkowane z innymi językami Visual Studio, a także opisano ustawienia specyficzne dla języka F #.</span><span class="sxs-lookup"><span data-stu-id="5d11b-110">This topic provides links to relevant information in the Visual Studio documentation for settings that are shared with the other Visual Studio languages, and also describes the settings specific to F#.</span></span>

## <a name="project-designer"></a><span data-ttu-id="5d11b-111">Projektant projektu</span><span class="sxs-lookup"><span data-stu-id="5d11b-111">Project Designer</span></span>
<span data-ttu-id="5d11b-112">**Projektanta projektu** użytkowania ogólne są opisane w temacie w pełni [wprowadzenie do projektanta projektu](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7) w dokumentacji programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5d11b-112">The **Project Designer** and its general use are described fully in the topic [Introduction to the Project Designer](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7) in the Visual Studio documentation.</span></span> <span data-ttu-id="5d11b-113">**Projektanta projektu** składa się z wielu stronach w rozbiciu na funkcje.</span><span class="sxs-lookup"><span data-stu-id="5d11b-113">The **Project Designer** consists of several pages grouped by related functionality.</span></span> <span data-ttu-id="5d11b-114">Strony dostępne dla projektów języka F # są przeważnie podzbiór tych, które są dostępne dla innych języków.</span><span class="sxs-lookup"><span data-stu-id="5d11b-114">The pages available for F# projects are mostly a subset of those available for other languages.</span></span> <span data-ttu-id="5d11b-115">W poniższej tabeli opisano stron obsługiwane w F #.</span><span class="sxs-lookup"><span data-stu-id="5d11b-115">The pages supported in F# are described in the following table.</span></span> <span data-ttu-id="5d11b-116">Stron, które nie są dostępne odnoszą się do funkcji, które nie są dostępne w języku F #, lub które są dostępne tylko w wyniku zmiany opcji wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="5d11b-116">The pages that are not available relate to features that are not available in F#, or that are available only by changing a command-line option.</span></span> <span data-ttu-id="5d11b-117">Stron, które są dostępne w języku F # przypominać najlepiej, stron C#, więc zostanie podane łącze do odpowiednich C# **projektanta projektu** strony.</span><span class="sxs-lookup"><span data-stu-id="5d11b-117">The pages that are available in F# resemble the C# pages most closely, so a link is provided to the relevant C# **Project Designer** page.</span></span>

|<span data-ttu-id="5d11b-118">Strony projektanta projektu</span><span class="sxs-lookup"><span data-stu-id="5d11b-118">Project Designer page</span></span>|<span data-ttu-id="5d11b-119">Linki pokrewne</span><span class="sxs-lookup"><span data-stu-id="5d11b-119">Related links</span></span>|<span data-ttu-id="5d11b-120">Opis</span><span class="sxs-lookup"><span data-stu-id="5d11b-120">Description</span></span>|
|---------------------|-------------|-----------|
|`Application`|[<span data-ttu-id="5d11b-121">Strona aplikacji, Projektant projektu &#40; K & 35; &#41;</span><span class="sxs-lookup"><span data-stu-id="5d11b-121">Application Page, Project Designer &#40;C&#35;&#41;</span></span>](https://msdn.microsoft.com/library/ms247046.aspx)|<span data-ttu-id="5d11b-122">Można określić ustawienia na poziomie aplikacji i właściwości, takich jak czy tworzenie biblioteki lub pliku wykonywalnego, jakiej wersji programu .NET Framework jest element docelowy aplikacji i informacje o którym zasobu pliki aplikacji używane są przechowywane.</span><span class="sxs-lookup"><span data-stu-id="5d11b-122">Enables you to specify application-level settings and properties, such as whether you are creating a library or an executable file, what version of the .NET Framework the application is targeting, and information about where the resource files that the application uses are stored.</span></span>|
|`Build`|[<span data-ttu-id="5d11b-123">Tworzenie strony, Projektant projektu &#40; K & 35; &#41;</span><span class="sxs-lookup"><span data-stu-id="5d11b-123">Build Page, Project Designer &#40;C&#35;&#41;</span></span>](https://msdn.microsoft.com/library/kb4wyys2.aspx)|<span data-ttu-id="5d11b-124">Umożliwia kontrolowanie sposobu kompilowania kodu.</span><span class="sxs-lookup"><span data-stu-id="5d11b-124">Enables you to control how the code is compiled.</span></span>|
|`Build Events`|[<span data-ttu-id="5d11b-125">Tworzenie strony zdarzenia, Projektant projektu &#40; K & 35; &#41;</span><span class="sxs-lookup"><span data-stu-id="5d11b-125">Build Events Page, Project Designer &#40;C&#35;&#41;</span></span>](https://msdn.microsoft.com/library/kb4wyys2.aspx)|<span data-ttu-id="5d11b-126">Można określić polecenie do uruchomienia przed lub po kompilacji.</span><span class="sxs-lookup"><span data-stu-id="5d11b-126">Enables you to specify commands to run before or after a compilation.</span></span>|
|`Debug`|[<span data-ttu-id="5d11b-127">Strona debugowania, Projektant projektu</span><span class="sxs-lookup"><span data-stu-id="5d11b-127">Debug Page, Project Designer</span></span>](https://msdn.microsoft.com/library/2wcdezs5.aspx)|<span data-ttu-id="5d11b-128">Umożliwia sterowanie, jak aplikacja zostanie uruchomiona podczas debugowania.</span><span class="sxs-lookup"><span data-stu-id="5d11b-128">Enables you to control how the application runs during debugging.</span></span> <span data-ttu-id="5d11b-129">Obejmuje to co wiersza polecenia oraz katalog początkowy aplikacji jest i specjalne debugowania tryby, które chcesz włączyć, takich jak SQL i kodu natywnego.</span><span class="sxs-lookup"><span data-stu-id="5d11b-129">This includes what command-line to use and what your application's starting directory is, and any special debugging modes you want to enable, such as native code and SQL.</span></span>|
|`Reference Paths`|[<span data-ttu-id="5d11b-130">Zarządzanie odwołaniami w projekcie</span><span class="sxs-lookup"><span data-stu-id="5d11b-130">Managing references in a project</span></span>](https://msdn.microsoft.com/library/ez524kew.aspx)|<span data-ttu-id="5d11b-131">Pozwala określić, gdzie do wyszukiwania zestawów, która zależy od kodu.</span><span class="sxs-lookup"><span data-stu-id="5d11b-131">Enables you to specify where to search for assemblies that the code depends on.</span></span>|

## <a name="f-specific-settings"></a><span data-ttu-id="5d11b-132">F #-określonych ustawień</span><span class="sxs-lookup"><span data-stu-id="5d11b-132">F#-Specific Settings</span></span>
<span data-ttu-id="5d11b-133">Poniższa tabela zawiera podsumowanie ustawień, które są specyficzne dla języka F #:</span><span class="sxs-lookup"><span data-stu-id="5d11b-133">The following table summarizes settings that are specific to F#:</span></span>

|<span data-ttu-id="5d11b-134">Strony projektanta projektu</span><span class="sxs-lookup"><span data-stu-id="5d11b-134">Project Designer page</span></span>|<span data-ttu-id="5d11b-135">Ustawienie</span><span class="sxs-lookup"><span data-stu-id="5d11b-135">Setting</span></span>|<span data-ttu-id="5d11b-136">Opis</span><span class="sxs-lookup"><span data-stu-id="5d11b-136">Description</span></span>|
|---------------------|-------|-----------|
|`Build`|`Generate tail calls`|<span data-ttu-id="5d11b-137">Jeśli zaznaczone, umożliwia użycie tail instrukcji języka pośredniego (MSIL) firmy Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d11b-137">If selected, enables the use of the tail Microsoft intermediate language (MSIL) instruction.</span></span> <span data-ttu-id="5d11b-138">Powoduje to, że ramka stosu zostanie ponownie tail funkcji cyklicznej.</span><span class="sxs-lookup"><span data-stu-id="5d11b-138">This causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="5d11b-139">Odpowiednikiem `--tailcalls` — opcja kompilatora.</span><span class="sxs-lookup"><span data-stu-id="5d11b-139">Equivalent to the `--tailcalls` compiler option.</span></span>|
|`Build`|`Other flags`|<span data-ttu-id="5d11b-140">Umożliwia określenie kompilatora dodatkowe opcje wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="5d11b-140">Allows you to specify additional compiler command-line options.</span></span>|

## <a name="see-also"></a><span data-ttu-id="5d11b-141">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5d11b-141">See Also</span></span>
 [<span data-ttu-id="5d11b-142">Rozpoczynanie pracy z F # w programie Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5d11b-142">Get Started with F# in Visual Studio</span></span>](../get-started/get-started-visual-studio.md)  
 [<span data-ttu-id="5d11b-143">Opcje kompilatora</span><span class="sxs-lookup"><span data-stu-id="5d11b-143">Compiler Options</span></span>](../language-reference/compiler-options.md)  
 <span data-ttu-id="5d11b-144">[Wprowadzenie do projektanta projektu](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5d11b-144">[Introduction to the Project Designer](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7(v=vs.100))</span></span>