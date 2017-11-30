---
title: "Oficjalna obrazy usługi .NET Docker"
description: "Architektura Mikrousług .NET dla aplikacji .NET konteneryzowanych | Oficjalna obrazy usługi .NET Docker"
keywords: "Docker, Mikrousług, ASP.NET, kontenera"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a><span data-ttu-id="898c2-104">Oficjalna obrazy usługi .NET Docker</span><span class="sxs-lookup"><span data-stu-id="898c2-104">Official .NET Docker images</span></span>

<span data-ttu-id="898c2-105">Obrazy oficjalnego Docker .NET są obrazy usługi Docker utworzone i zoptymalizowane przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="898c2-105">The Official .NET Docker images are Docker images created and optimized by Microsoft.</span></span> <span data-ttu-id="898c2-106">Są one dostępne publicznie w repozytoriach Microsoft [Centrum Docker](https://hub.docker.com/u/microsoft/).</span><span class="sxs-lookup"><span data-stu-id="898c2-106">They are publicly available in the Microsoft repositories on [Docker Hub](https://hub.docker.com/u/microsoft/).</span></span> <span data-ttu-id="898c2-107">Każdego repozytorium może zawierać wiele obrazów, w zależności od wersji platformy .NET, a także w zależności od systemu operacyjnego i wersji (Linux Debian, Alpine systemu Linux, Windows Nano Server, Windows Server Core, itp.).</span><span class="sxs-lookup"><span data-stu-id="898c2-107">Each repository can contain multiple images, depending on .NET versions, and depending on the OS and versions (Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core, etc.).</span></span>

<span data-ttu-id="898c2-108">Wizji firmy Microsoft dla repozytoriów .NET jest szczegółowym i skupiają się repozytoriów, gdzie repozytorium reprezentuje konkretnych sytuacji lub obciążenia.</span><span class="sxs-lookup"><span data-stu-id="898c2-108">Microsoft’s vision for .NET repositories is to have granular and focused repos, where a repo represents a specific scenario or workload.</span></span> <span data-ttu-id="898c2-109">Na przykład [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) obrazów powinna być używana, jeśli przy użyciu platformy ASP.NET Core na Docker, ponieważ te obrazy platformy ASP.NET Core udostępniają dodatkowe optymalizacje tak kontenery można uruchomić szybciej.</span><span class="sxs-lookup"><span data-stu-id="898c2-109">For instance, the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) images should be used when using ASP.NET Core on Docker, because those ASP.NET Core images provide additional optimizations so containers can start faster.</span></span>

<span data-ttu-id="898c2-110">Z drugiej strony obrazy .NET Core (microsoft/dotnet) są przeznaczone dla aplikacji konsoli .NET Core w oparciu.</span><span class="sxs-lookup"><span data-stu-id="898c2-110">On the other hand, the .NET Core images (microsoft/dotnet) are intended for console apps based on .NET Core.</span></span> <span data-ttu-id="898c2-111">Na przykład procesy partii zadań Webjob Azure i inne scenariusze konsoli, należy użyć .NET Core.</span><span class="sxs-lookup"><span data-stu-id="898c2-111">For example, batch processes, Azure WebJobs, and other console scenarios should use .NET Core.</span></span> <span data-ttu-id="898c2-112">Tych obrazów nie dołączaj stosu platformy ASP.NET Core, co powoduje mniejsze obrazu kontenera.</span><span class="sxs-lookup"><span data-stu-id="898c2-112">Those images do not include the ASP.NET Core stack, resulting in a smaller container image.</span></span>

<span data-ttu-id="898c2-113">Większość repozytoriów obrazu zapewniają szeroką gamę znakowanie ułatwiające wybranie nie tylko wersji określonej platformy, ale wybierz system operacyjny (Linux distro lub wersji systemu Windows).</span><span class="sxs-lookup"><span data-stu-id="898c2-113">Most image repos provide extensive tagging to help you select not just a specific framework version, but also to choose an OS (Linux distro or Windows version).</span></span>

<span data-ttu-id="898c2-114">Aby uzyskać więcej informacji o obrazach .NET Docker oficjalnego obsługiwane przez firmę Microsoft, zobacz [podsumowanie obrazy usługi Docker .NET](https://aka.ms/dotnetdockerimages).</span><span class="sxs-lookup"><span data-stu-id="898c2-114">For further information about the official .NET Docker images provided by Microsoft, see the [.NET Docker Images summary](https://aka.ms/dotnetdockerimages).</span></span>

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a><span data-ttu-id="898c2-115">Oprogramowanie .NET core i Docker optymalizacji obrazu dla rozwoju i produkcji</span><span class="sxs-lookup"><span data-stu-id="898c2-115">.NET Core and Docker image optimizations for development versus production</span></span>

<span data-ttu-id="898c2-116">Tworząc obrazy usługi Docker dla deweloperów, Microsoft skupia się na następujących głównych scenariuszy:</span><span class="sxs-lookup"><span data-stu-id="898c2-116">When building Docker images for developers, Microsoft focused on the following main scenarios:</span></span>

-   <span data-ttu-id="898c2-117">Obrazy używane do *opracowanie* i tworzenie aplikacji platformy .NET Core.</span><span class="sxs-lookup"><span data-stu-id="898c2-117">Images used to *develop* and build .NET Core apps.</span></span>

-   <span data-ttu-id="898c2-118">Obrazy używane do *Uruchom* aplikacje .NET Core.</span><span class="sxs-lookup"><span data-stu-id="898c2-118">Images used to *run* .NET Core apps.</span></span>

<span data-ttu-id="898c2-119">Dlaczego wiele obrazów?</span><span class="sxs-lookup"><span data-stu-id="898c2-119">Why multiple images?</span></span> <span data-ttu-id="898c2-120">Podczas tworzenia, tworzenie i uruchamianie aplikacji konteneryzowanych, zwykle mają różnych priorytetów.</span><span class="sxs-lookup"><span data-stu-id="898c2-120">When developing, building, and running containerized applications, you usually have different priorities.</span></span> <span data-ttu-id="898c2-121">Podając inną obrazy te poszczególnych zadań, Microsoft pomaga zoptymalizować oddzielne procesy tworzenia, kompilowania i wdrażania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="898c2-121">By providing different images for these separate tasks, Microsoft helps optimize the separate processes of developing, building, and deploying apps.</span></span>

### <a name="during-development-and-build"></a><span data-ttu-id="898c2-122">Podczas projektowania i kompilacji</span><span class="sxs-lookup"><span data-stu-id="898c2-122">During development and build</span></span>

<span data-ttu-id="898c2-123">Podczas tworzenia ważne jest tempa można wykonać iterację zmiany i możliwość zmiany debugowania.</span><span class="sxs-lookup"><span data-stu-id="898c2-123">During development, what is important is how fast you can iterate changes, and the ability to debug the changes.</span></span> <span data-ttu-id="898c2-124">Rozmiar obrazu nie jest ważniejsza niż możliwość wprowadzić zmiany w kodzie i szybko zobaczyć zmiany.</span><span class="sxs-lookup"><span data-stu-id="898c2-124">The size of the image is not as important as the ability to make changes to your code and see the changes quickly.</span></span> <span data-ttu-id="898c2-125">Niektóre narzędzia i "kontenery agenta kompilacji", użyj programowanie obrazu platformy ASP.NET Core (microsoft aspnetcore kompilacji) podczas tworzenia i proces kompilacji.</span><span class="sxs-lookup"><span data-stu-id="898c2-125">Some tools and "build-agent containers", use the development ASP.NET Core image (microsoft/aspnetcore-build) during development and build proces.</span></span> <span data-ttu-id="898c2-126">Podczas kompilowania w kontenerze Docker, ważne kwestie związane są elementy, które są wymagane, aby skompilować aplikację.</span><span class="sxs-lookup"><span data-stu-id="898c2-126">When building inside a Docker container, the important aspects are the elements that are needed in order to compile your app.</span></span> <span data-ttu-id="898c2-127">Obejmuje to kompilator i wszelkich innych zależności .NET, a także zależności programowanie sieci web, takich jak npm, system Gulp i Bower.</span><span class="sxs-lookup"><span data-stu-id="898c2-127">This includes the compiler and any other .NET dependencies, plus web development dependencies like npm, Gulp, and Bower.</span></span>

<span data-ttu-id="898c2-128">Ten typ obrazu kompilacji jest ważna</span><span class="sxs-lookup"><span data-stu-id="898c2-128">Why is this type of build image important?</span></span> <span data-ttu-id="898c2-129">Ten obraz nie są wdrażane w środowisku produkcyjnym.</span><span class="sxs-lookup"><span data-stu-id="898c2-129">You do not deploy this image to production.</span></span> <span data-ttu-id="898c2-130">Zamiast tego jest obraz, który umożliwia tworzenie zawartości, który można umieścić w środowisku produkcyjnym obraz.</span><span class="sxs-lookup"><span data-stu-id="898c2-130">Instead, it is an image you use to build the content you place into a production image.</span></span> <span data-ttu-id="898c2-131">Ten obraz będzie używany w danym środowisku ciągłej integracji (CI) lub środowisko kompilacji.</span><span class="sxs-lookup"><span data-stu-id="898c2-131">This image would be used in your continuous integration (CI) environment or build environment.</span></span> <span data-ttu-id="898c2-132">Na przykład zamiast ręcznego instalowania zależności aplikacji bezpośrednio na agenta kompilacji hosta (maszyn wirtualnych, na przykład), agent kompilacji będzie wystąpienia obrazu kompilacji platformy .NET Core wszystkie zależności wymagane do tworzenia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="898c2-132">For instance, rather than manually installing all your application dependencies directly on a build agent host (a VM, for example), the build agent would instantiate a .NET Core build image with all the dependencies required to build the application.</span></span> <span data-ttu-id="898c2-133">Agenta kompilacji musi znać tylko sposób uruchamiania tego obrazu Docker.</span><span class="sxs-lookup"><span data-stu-id="898c2-133">Your build agent only needs to know how to run this Docker image.</span></span> <span data-ttu-id="898c2-134">Upraszcza środowiska CI to i ułatwia znacznie bardziej przewidywalne.</span><span class="sxs-lookup"><span data-stu-id="898c2-134">This simplifies your CI environment and makes it much more predictable.</span></span>

### <a name="in-production"></a><span data-ttu-id="898c2-135">W środowisku produkcyjnym</span><span class="sxs-lookup"><span data-stu-id="898c2-135">In production</span></span>

<span data-ttu-id="898c2-136">Co to jest ważne w środowisku produkcyjnym jest tempa można wdrożyć i uruchomić kontenerów na podstawie obrazu platformy .NET Core produkcji.</span><span class="sxs-lookup"><span data-stu-id="898c2-136">What is important in production is how fast you can deploy and start your containers based on a production .NET Core image.</span></span> <span data-ttu-id="898c2-137">W związku z tym, na podstawie obrazu tylko do środowiska wykonawczego [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) jest mały, dzięki czemu rozprzestrzenia się szybko w sieci z rejestru Docker na hostach Docker.</span><span class="sxs-lookup"><span data-stu-id="898c2-137">Therefore, the runtime-only image based on [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) is small so that it can travel quickly across the network from your Docker registry to your Docker hosts.</span></span> <span data-ttu-id="898c2-138">Zawartość jest gotowy do uruchomienia, włączanie o najszybszym czasie uruchamianiu kontenera do przetwarzania wyników.</span><span class="sxs-lookup"><span data-stu-id="898c2-138">The contents are ready to run, enabling the fastest time from starting the container to processing results.</span></span> <span data-ttu-id="898c2-139">W modelu Docker nie jest wymagane do kompilacji z C\# kodu, ponieważ wystąpiły po uruchomieniu dotnet kompilacji lub dotnet publikowania, gdy używa kontenera kompilacji.</span><span class="sxs-lookup"><span data-stu-id="898c2-139">In the Docker model, there is no need for compilation from C\# code, as there is when you run dotnet build or dotnet publish when using the build container.</span></span>

<span data-ttu-id="898c2-140">W tym zoptymalizowanego obrazu możesz umieścić tylko pliki binarne i innej zawartości, wymaganego do uruchomienia aplikacji.</span><span class="sxs-lookup"><span data-stu-id="898c2-140">In this optimized image you put only the binaries and other content needed to run the application.</span></span> <span data-ttu-id="898c2-141">Na przykład zawartość utworzona przez dotnet opublikować zawiera tylko skompilowanych .NET pliki binarne, obrazy, js i pliki CSS.</span><span class="sxs-lookup"><span data-stu-id="898c2-141">For example, the content created by dotnet publish contains only the compiled .NET binaries, images, .js, and .css files.</span></span> <span data-ttu-id="898c2-142">W czasie zostanie wyświetlony obrazów zawierających pakiety poprzedzającego utworzenie kopii zapasowej przy użyciu kompilatora JIT.</span><span class="sxs-lookup"><span data-stu-id="898c2-142">Over time, you will see images that contain pre-jitted packages.</span></span>

<span data-ttu-id="898c2-143">Mimo że istnieje wiele wersji .NET Core i ASP.NET Core obrazów, wszystkie mają jednej lub kilku warstw, łącznie z warstwy podstawowej.</span><span class="sxs-lookup"><span data-stu-id="898c2-143">Although there are multiple versions of the .NET Core and ASP.NET Core images, they all share one or more layers, including the base layer.</span></span> <span data-ttu-id="898c2-144">W związku z tym ilość miejsca na dysku wymagane do przechowywania obrazu jest mała; składa się tylko z różnica między niestandardowego obrazu i jego obrazu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="898c2-144">Therefore, the amount of disk space needed to store an image is small; it consists only of the delta between your custom image and its base image.</span></span> <span data-ttu-id="898c2-145">Wynik jest szybkie do pobierania obrazu z rejestru.</span><span class="sxs-lookup"><span data-stu-id="898c2-145">The result is that it is quick to pull the image from your registry.</span></span>

<span data-ttu-id="898c2-146">Podczas eksplorowania repozytoria obrazu platformy .NET w Centrum Docker można znaleźć wiele wersji obrazu sklasyfikowane lub oznaczone tagami.</span><span class="sxs-lookup"><span data-stu-id="898c2-146">When you explore the .NET image repositories at Docker Hub, you will find multiple image versions classified or marked with tags.</span></span> <span data-ttu-id="898c2-147">Tagi te pomogą zdecydować, który z nich do używania w zależności od wersji, które są potrzebne, podobnie jak w poniższej tabeli:</span><span class="sxs-lookup"><span data-stu-id="898c2-147">These tags help to decide which one to use, depending on the version you need, like those in the following table:</span></span>

-   <span data-ttu-id="898c2-148">Microsoft /**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="898c2-148">microsoft/**aspnetcore:2.0**</span></span>

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   <span data-ttu-id="898c2-149">Microsoft /**aspnetcore-kompilacji: 2.0**</span><span class="sxs-lookup"><span data-stu-id="898c2-149">microsoft/**aspnetcore-build:2.0**</span></span>

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
<span data-ttu-id="898c2-150">[Poprzednie] (net kontenera os-targets.md) [dalej] (.. /Architect-microservice-container-Applications/index.MD)</span><span class="sxs-lookup"><span data-stu-id="898c2-150">[Previous] (net-container-os-targets.md) [Next] (../architect-microservice-container-applications/index.md)</span></span>