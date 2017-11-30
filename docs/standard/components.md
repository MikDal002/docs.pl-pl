---
title: "Składniki architektury .NET"
description: "W tym artykule opisano składniki architektury .NET, takie jak .NET Standard, .NET implementacji środowiska uruchomieniowe .NET i narzędzi."
author: cartermp
ms.author: mairaw
ms.date: 08/23/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.openlocfilehash: ce3368f4c34a8e4b20a7deb2a6c6e4d163927cd4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="net-architectural-components"></a><span data-ttu-id="d28e2-103">Składniki architektury .NET</span><span class="sxs-lookup"><span data-stu-id="d28e2-103">.NET architectural components</span></span>

<span data-ttu-id="d28e2-104">Aplikacji .NET jest opracowany dla i działa w co najmniej jeden *implementacje .NET*.</span><span class="sxs-lookup"><span data-stu-id="d28e2-104">A .NET app is developed for and runs in one or more *implementations of .NET*.</span></span>  <span data-ttu-id="d28e2-105">Implementacje .NET obejmują .NET Framework .NET Core i Mono.</span><span class="sxs-lookup"><span data-stu-id="d28e2-105">Implementations of .NET include the .NET Framework, .NET Core, and Mono.</span></span> <span data-ttu-id="d28e2-106">Wspólne dla wszystkich implementacji programu .NET, który wywołał .NET Standard to specyfikacja interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="d28e2-106">There is an API specification common to all implementations of .NET that's called the .NET Standard.</span></span> <span data-ttu-id="d28e2-107">Ten artykuł zawiera krótkie wprowadzenie do każdego z tych pojęć.</span><span class="sxs-lookup"><span data-stu-id="d28e2-107">This article gives a brief introduction to each of these concepts.</span></span>

## <a name="net-standard"></a><span data-ttu-id="d28e2-108">.NET standard</span><span class="sxs-lookup"><span data-stu-id="d28e2-108">.NET Standard</span></span>

<span data-ttu-id="d28e2-109">.NET Standard to zestaw interfejsów API, które są implementowane przez podstawowej biblioteki klas z implementacji programu .NET.</span><span class="sxs-lookup"><span data-stu-id="d28e2-109">The .NET Standard is a set of APIs that are implemented by the Base Class Library of a .NET implementation.</span></span> <span data-ttu-id="d28e2-110">Więcej formalnie jest specyfikacji interfejsów API platformy .NET, które tworzą jednolity zestaw kontraktów kompilowanych Twój kod.</span><span class="sxs-lookup"><span data-stu-id="d28e2-110">More formally, it's a specification of .NET APIs that make up a uniform set of contracts that you compile your code against.</span></span> <span data-ttu-id="d28e2-111">Umowy te są implementowane w każdej implementacji .NET.</span><span class="sxs-lookup"><span data-stu-id="d28e2-111">These contracts are implemented in each .NET implementation.</span></span> <span data-ttu-id="d28e2-112">Dzięki temu przenośność przez inne implementacje .NET, skuteczne stosowanie wszędzie wykonywania kodu.</span><span class="sxs-lookup"><span data-stu-id="d28e2-112">This enables portability across different .NET implementations, effectively allowing your code to run everywhere.</span></span>

<span data-ttu-id="d28e2-113">.NET Standard jest również [platformy docelowej](glossary.md#target-framework).</span><span class="sxs-lookup"><span data-stu-id="d28e2-113">The .NET Standard is also a [target framework](glossary.md#target-framework).</span></span> <span data-ttu-id="d28e2-114">Jeśli kod jest przeznaczony dla wersji programu .NET Standard, można go uruchomić w implementacji .NET obsługującej danej wersji programu .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d28e2-114">If your code targets a version of the .NET Standard, it can run on any .NET implementation which supports that version of the .NET Standard.</span></span>

<span data-ttu-id="d28e2-115">Aby dowiedzieć się więcej o .NET Standard i stosowanie ich, zobacz [.NET Standard](net-standard.md) tematu.</span><span class="sxs-lookup"><span data-stu-id="d28e2-115">To learn more about the .NET Standard and how to target it, see the [.NET Standard](net-standard.md) topic.</span></span>

## <a name="net-implementations"></a><span data-ttu-id="d28e2-116">Implementacje .NET</span><span class="sxs-lookup"><span data-stu-id="d28e2-116">.NET implementations</span></span>

<span data-ttu-id="d28e2-117">Każda implementacja .NET obejmuje następujące składniki:</span><span class="sxs-lookup"><span data-stu-id="d28e2-117">Each implementation of .NET includes the following components:</span></span>

- <span data-ttu-id="d28e2-118">Jeden lub więcej środowisk uruchomieniowych.</span><span class="sxs-lookup"><span data-stu-id="d28e2-118">One or more runtimes.</span></span> <span data-ttu-id="d28e2-119">Przykłady: CLR programu .NET Framework, środowisko CoreCLR i CoreRT dla platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d28e2-119">Examples: CLR for .NET Framework, CoreCLR and CoreRT for .NET Core.</span></span>
- <span data-ttu-id="d28e2-120">Biblioteka klas, który implementuje standardowe .NET i może wdrożyć dodatkowe interfejsy API.</span><span class="sxs-lookup"><span data-stu-id="d28e2-120">A class library that implements the .NET Standard and may implement additional APIs.</span></span> <span data-ttu-id="d28e2-121">Przykłady: Klasa podstawowa Biblioteka programu .NET Framework, .NET Core klasy podstawowej biblioteki.</span><span class="sxs-lookup"><span data-stu-id="d28e2-121">Examples: .NET Framework Base Class Library, .NET Core Base Class Library.</span></span>
- <span data-ttu-id="d28e2-122">Opcjonalnie co najmniej jeden struktury aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d28e2-122">Optionally, one or more application frameworks.</span></span> <span data-ttu-id="d28e2-123">Przykłady: [ASP.NET](https://www.asp.net/), [formularzy systemu Windows](../framework/winforms/windows-forms-overview.md), i [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) znajdują się w programie .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d28e2-123">Examples: [ASP.NET](https://www.asp.net/), [Windows Forms](../framework/winforms/windows-forms-overview.md), and [Windows Presentation Foundation (WPF)](../framework/wpf/index.md) are included in the .NET Framework.</span></span>
- <span data-ttu-id="d28e2-124">Opcjonalnie narzędzia do programowania.</span><span class="sxs-lookup"><span data-stu-id="d28e2-124">Optionally, development tools.</span></span> <span data-ttu-id="d28e2-125">Niektóre narzędzia do programowania są współużytkowane przez wiele implementacji.</span><span class="sxs-lookup"><span data-stu-id="d28e2-125">Some development tools are shared among multiple implementations.</span></span>

<span data-ttu-id="d28e2-126">Istnieją cztery głównej implementacje .NET, które firma Microsoft aktywnie rozwija i przechowuje: .NET Core, .NET Framework Mono i platformy uniwersalnej systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="d28e2-126">There are four primary .NET implementations that Microsoft actively develops and maintains: .NET Core, .NET Framework, Mono, and UWP.</span></span>

### <a name="net-core"></a><span data-ttu-id="d28e2-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="d28e2-127">.NET Core</span></span>

<span data-ttu-id="d28e2-128">Oprogramowanie .NET core to implementacja i platform .NET i przeznaczone do obsługi obciążeń serwera i w chmurze na dużą skalę.</span><span class="sxs-lookup"><span data-stu-id="d28e2-128">.NET Core is a cross-platform implementation of .NET and designed to handle server and cloud workloads at scale.</span></span> <span data-ttu-id="d28e2-129">Uruchamia go w systemie Windows, system macOS i Linux.</span><span class="sxs-lookup"><span data-stu-id="d28e2-129">It runs on Windows, macOS and Linux.</span></span> <span data-ttu-id="d28e2-130">Implementuje standardowe .NET, więc kod, który jest przeznaczony dla platformy .NET Standard można uruchamiać na .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d28e2-130">It implements the .NET Standard, so code that targets the .NET Standard can run on .NET Core.</span></span> <span data-ttu-id="d28e2-131">Platformy ASP.NET Core działa na .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d28e2-131">ASP.NET Core runs on .NET Core.</span></span> 

<span data-ttu-id="d28e2-132">Aby dowiedzieć się więcej na temat platformy .NET Core, zobacz [.NET Core przewodnik](../core/index.md) i [wybór między .NET Core i .NET Framework dla aplikacji serwera](choosing-core-framework-server.md).</span><span class="sxs-lookup"><span data-stu-id="d28e2-132">To learn more about .NET Core, see the [.NET Core Guide](../core/index.md) and [Choosing between .NET Core and .NET Framework for server apps](choosing-core-framework-server.md).</span></span>

### <a name="net-framework"></a><span data-ttu-id="d28e2-133">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="d28e2-133">.NET Framework</span></span>

<span data-ttu-id="d28e2-134">.NET Framework jest oryginalnym implementację .NET, która była dostępna już 2002.</span><span class="sxs-lookup"><span data-stu-id="d28e2-134">The.NET Framework is the original .NET implementation that has existed since 2002.</span></span> <span data-ttu-id="d28e2-135">Jest tej samej .NET Framework, która zawsze używanych istniejących programistów platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="d28e2-135">It's the same .NET Framework that existing .NET developers have always used.</span></span> <span data-ttu-id="d28e2-136">W wersji 4.5 i wdrożenie nowszej .NET Standard tak kodu, który jest przeznaczony dla platformy .NET Standard można uruchomić w tych wersjach systemu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d28e2-136">Versions 4.5 and later implement the .NET Standard, so code that targets the .NET Standard can run on those versions of the .NET Framework.</span></span> <span data-ttu-id="d28e2-137">Zawiera on dodatkowe interfejsy API właściwe dla systemu Windows, takich jak interfejsy API dla systemu Windows dla deweloperów pulpitu WPF i formularze systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="d28e2-137">It contains additional Windows-specific APIs, such as APIs for Windows desktop development with Windows Forms and WPF.</span></span> <span data-ttu-id="d28e2-138">.NET Framework jest zoptymalizowana pod kątem tworzenia aplikacji klasycznych systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="d28e2-138">The .NET Framework is optimized for building Windows desktop applications.</span></span>

<span data-ttu-id="d28e2-139">Aby dowiedzieć się więcej na temat programu .NET Framework, zobacz [.NET Framework — przewodnik](../framework/index.md).</span><span class="sxs-lookup"><span data-stu-id="d28e2-139">To learn more about the .NET Framework, see the [.NET Framework Guide](../framework/index.md).</span></span>

### <a name="mono"></a><span data-ttu-id="d28e2-140">Mono</span><span class="sxs-lookup"><span data-stu-id="d28e2-140">Mono</span></span>

<span data-ttu-id="d28e2-141">Mono jest implementację .NET, która jest głównie używane, gdy wymagana jest mała środowiska wykonawczego.</span><span class="sxs-lookup"><span data-stu-id="d28e2-141">Mono is a .NET implementation that is mainly used when a small runtime is required.</span></span> <span data-ttu-id="d28e2-142">To środowisko uruchomieniowe, które uprawnienia aplikacji platformy Xamarin Android, Mac, iOS, systemu tvOS i watchOS i koncentruje się przede wszystkim na niewielkie rozmiary.</span><span class="sxs-lookup"><span data-stu-id="d28e2-142">It is the runtime that powers Xamarin applications on Android, Mac, iOS, tvOS and watchOS and is focused primarily on a small footprint.</span></span>

<span data-ttu-id="d28e2-143">Obsługuje wszystkie obecnie opublikowanej wersji platformy .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d28e2-143">It supports all of the currently published .NET Standard versions.</span></span>

<span data-ttu-id="d28e2-144">W przeszłości Mono zaimplementowana większych interfejsu API programu .NET Framework i emulowane niektóre najpopularniejsze funkcje w systemie Unix.</span><span class="sxs-lookup"><span data-stu-id="d28e2-144">Historically, Mono implemented the larger API of the .NET Framework and emulated some of the most popular capabilities on Unix.</span></span> <span data-ttu-id="d28e2-145">Czasami służy do uruchamiania aplikacji .NET, które zależą od tych funkcji w systemie Unix.</span><span class="sxs-lookup"><span data-stu-id="d28e2-145">It is sometimes used to run .NET applications that rely on those capabilities on Unix.</span></span>

<span data-ttu-id="d28e2-146">Mono jest zwykle używana z kompilatora just in time, ale także kompilatora pełnej statyczne (kompilacja z wyprzedzeniem o czasie) używaną na platformach, np. z systemem iOS.</span><span class="sxs-lookup"><span data-stu-id="d28e2-146">Mono is typically used with a just-in-time compiler, but it also features a full static compiler (ahead-of-time compilation) that is used on platforms like iOS.</span></span>

<span data-ttu-id="d28e2-147">Aby dowiedzieć się więcej na temat Mono, zobacz [Mono dokumentacji](http://www.mono-project.com/docs/).</span><span class="sxs-lookup"><span data-stu-id="d28e2-147">To learn more about Mono, see the [Mono documentation](http://www.mono-project.com/docs/).</span></span>

### <a name="universal-windows-platform-uwp"></a><span data-ttu-id="d28e2-148">Platforma uniwersalna systemu Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="d28e2-148">Universal Windows Platform (UWP)</span></span>

<span data-ttu-id="d28e2-149">Platformy uniwersalnej systemu Windows jest implementacja klasy .NET, który jest używany do tworzenia nowoczesnych, obsługą dotyku aplikacji systemu Windows, jak i oprogramowania dla Internetu rzeczy (IoT).</span><span class="sxs-lookup"><span data-stu-id="d28e2-149">UWP is an implementation of .NET that is used for building modern, touch-enabled Windows applications and software for the Internet of Things (IoT).</span></span> <span data-ttu-id="d28e2-150">Zostało zaprojektowane do ujednolicenie różne typy urządzeń, które chcesz docelowych, łącznie z komputerami, tablety, phablets, telefony i nawet Xbox.</span><span class="sxs-lookup"><span data-stu-id="d28e2-150">It's designed to unify the different types of devices that you may want to target, including PCs, tablets, phablets, phones, and even the Xbox.</span></span> <span data-ttu-id="d28e2-151">Platformy uniwersalnej systemu Windows udostępnia wiele usług, takich jak scentralizowane sklepu, środowiska wykonawczego (AppContainer) i zestaw interfejsów API systemu Windows do użycia zamiast Win32 (WinRT).</span><span class="sxs-lookup"><span data-stu-id="d28e2-151">UWP provides many services, such as a centralized app store, an execution environment (AppContainer), and a set of Windows APIs to use instead of Win32 (WinRT).</span></span> <span data-ttu-id="d28e2-152">Aplikacje mogą być napisane w języku C++, C#, VB.NET i JavaScript.</span><span class="sxs-lookup"><span data-stu-id="d28e2-152">Apps can be written in C++, C#, VB.NET, and JavaScript.</span></span> <span data-ttu-id="d28e2-153">Korzystając z języka C# i VB.NET, interfejsów API architektury .NET są udostępniane przez oprogramowanie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d28e2-153">When using C# and VB.NET, the .NET APIs are provided by .NET Core.</span></span>

<span data-ttu-id="d28e2-154">Aby dowiedzieć się więcej na temat platformy uniwersalnej systemu Windows, zobacz [wprowadzenie do platformy uniwersalnej systemu Windows](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide).</span><span class="sxs-lookup"><span data-stu-id="d28e2-154">To learn more about UWP, see [Intro to the Universal Windows Platform](https://docs.microsoft.com/windows/uwp/get-started/universal-application-platform-guide).</span></span>

## <a name="net-runtimes"></a><span data-ttu-id="d28e2-155">Środowiska uruchomieniowe .NET</span><span class="sxs-lookup"><span data-stu-id="d28e2-155">.NET runtimes</span></span>

<span data-ttu-id="d28e2-156">Środowisko wykonawcze jest środowiska wykonania programu zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="d28e2-156">A runtime is the execution environment for a managed program.</span></span> <span data-ttu-id="d28e2-157">System operacyjny jest częścią środowiska uruchomieniowego, ale nie jest częścią środowiska uruchomieniowego .NET.</span><span class="sxs-lookup"><span data-stu-id="d28e2-157">The OS is part of the runtime environment but is not part of the .NET runtime.</span></span> <span data-ttu-id="d28e2-158">Oto kilka przykładów środowisk uruchomieniowych .NET:</span><span class="sxs-lookup"><span data-stu-id="d28e2-158">Here are some examples of .NET runtimes:</span></span>
 
 - <span data-ttu-id="d28e2-159">Środowisko uruchomieniowe języka wspólnego (CLR) dla programu .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d28e2-159">Common Language Runtime (CLR) for the .NET Framework</span></span>
 - <span data-ttu-id="d28e2-160">Podstawowe środowisko uruchomieniowe języka wspólnego (środowisko CoreCLR) dla platformy .NET Core</span><span class="sxs-lookup"><span data-stu-id="d28e2-160">Core Common Language Runtime (CoreCLR) for .NET Core</span></span>
 - <span data-ttu-id="d28e2-161">Architektura .NET native dla platformy uniwersalnej systemu Windows</span><span class="sxs-lookup"><span data-stu-id="d28e2-161">.NET Native for Universal Windows Platform</span></span> 
 - <span data-ttu-id="d28e2-162">Mono środowiska wykonawczego dla platformy Xamarin.iOS, Xamarin.Android Xamarin.Mac i Mono framework pulpitu</span><span class="sxs-lookup"><span data-stu-id="d28e2-162">The Mono runtime for Xamarin.iOS, Xamarin.Android, Xamarin.Mac, and the Mono desktop framework</span></span>

## <a name="net-tooling-and-common-infrastructure"></a><span data-ttu-id="d28e2-163">Narzędzia .NET i wspólnej infrastruktury</span><span class="sxs-lookup"><span data-stu-id="d28e2-163">.NET tooling and common infrastructure</span></span>

<span data-ttu-id="d28e2-164">Masz dostęp do rozbudowany zestaw narzędzi i składników infrastruktury, które współpracują z każdego wdrożenia programu .NET.</span><span class="sxs-lookup"><span data-stu-id="d28e2-164">You have access to an extensive set of tools and infrastructure components that work with every implementation of .NET.</span></span> <span data-ttu-id="d28e2-165">Te obejmują, ale nie są ograniczone do następujących:</span><span class="sxs-lookup"><span data-stu-id="d28e2-165">These include, but are not limited to the following:</span></span>

- <span data-ttu-id="d28e2-166">Języków .NET i ich kompilatory</span><span class="sxs-lookup"><span data-stu-id="d28e2-166">The .NET languages and their compilers</span></span>
- <span data-ttu-id="d28e2-167">System projektu platformy .NET (na podstawie *.csproj*, *vbproj*, i *.fsproj* plików)</span><span class="sxs-lookup"><span data-stu-id="d28e2-167">The .NET project system (based on *.csproj*, *.vbproj*, and *.fsproj* files)</span></span>
- <span data-ttu-id="d28e2-168">[MSBuild](/visualstudio/msbuild/msbuild), aparatu kompilacji używany do tworzenia projektów</span><span class="sxs-lookup"><span data-stu-id="d28e2-168">[MSBuild](/visualstudio/msbuild/msbuild), the build engine used to build projects</span></span>
- <span data-ttu-id="d28e2-169">[NuGet](/nuget/), Menedżer pakietów firmy Microsoft dla programu .NET</span><span class="sxs-lookup"><span data-stu-id="d28e2-169">[NuGet](/nuget/), Microsoft's package manager for .NET</span></span>
- <span data-ttu-id="d28e2-170">Orchestration kompilacji open source narzędzi, takich jak [CIASTO](http://cakebuild.net/) i [FAŁSZYWE](https://fake.build/)</span><span class="sxs-lookup"><span data-stu-id="d28e2-170">Open-source build orchestration tools, such as [CAKE](http://cakebuild.net/) and [FAKE](https://fake.build/)</span></span>

## <a name="see-also"></a><span data-ttu-id="d28e2-171">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d28e2-171">See also</span></span>
<span data-ttu-id="d28e2-172">[Wybór między .NET Core i .NET Framework dla serwera aplikacji](choosing-core-framework-server.md) </span><span class="sxs-lookup"><span data-stu-id="d28e2-172">[Choosing between .NET Core and .NET Framework for server apps](choosing-core-framework-server.md) </span></span>  
[<span data-ttu-id="d28e2-173">.NET standard</span><span class="sxs-lookup"><span data-stu-id="d28e2-173">.NET Standard</span></span>](net-standard.md)  
[<span data-ttu-id="d28e2-174">Przewodnik po podstawowej platformy .NET</span><span class="sxs-lookup"><span data-stu-id="d28e2-174">.NET Core Guide</span></span>](../core/index.md)  
[<span data-ttu-id="d28e2-175">.NET framework — przewodnik</span><span class="sxs-lookup"><span data-stu-id="d28e2-175">.NET Framework Guide</span></span>](../framework/index.md)  
[<span data-ttu-id="d28e2-176">Przewodnik C#</span><span class="sxs-lookup"><span data-stu-id="d28e2-176">C# Guide</span></span>](../csharp/index.md)  
[<span data-ttu-id="d28e2-177">Przewodnik F #</span><span class="sxs-lookup"><span data-stu-id="d28e2-177">F# Guide</span></span>](../fsharp/index.md)  
[<span data-ttu-id="d28e2-178">Przewodnik VB.NET</span><span class="sxs-lookup"><span data-stu-id="d28e2-178">VB.NET Guide</span></span>](../visual-basic/index.md)  
