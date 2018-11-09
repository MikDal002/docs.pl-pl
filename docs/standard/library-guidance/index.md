---
title: Wskazówki dotyczące biblioteki typu open-source
description: Zalecenia dotyczące najlepszych rozwiązań dla deweloperów do tworzenia bibliotek platformy .NET o wysokiej jakości.
author: jamesnk
ms.author: mairaw
ms.date: 10/17/2018
ms.openlocfilehash: ca95cb5ba1ebf27464397b7850ac02aabded1a5b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188628"
---
# <a name="open-source-library-guidance"></a><span data-ttu-id="7d6f2-103">Wskazówki dotyczące biblioteki typu open-source</span><span class="sxs-lookup"><span data-stu-id="7d6f2-103">Open-source library guidance</span></span>

<span data-ttu-id="7d6f2-104">Niniejsze wskazówki zawiera zalecenia dla deweloperów do tworzenia bibliotek .NET wysokiej jakości.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-104">This guidance provides recommendations for developers to create high-quality .NET libraries.</span></span> <span data-ttu-id="7d6f2-105">Ta dokumentacja koncentruje się na *co* i *Dlaczego* podczas kompilowania biblioteki .NET nie *jak*.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-105">This documentation focuses on the *what* and the *why* when building a .NET library, not the *how*.</span></span>

<span data-ttu-id="7d6f2-106">Aspekty bibliotek .NET typu open-source wysokiej jakości:</span><span class="sxs-lookup"><span data-stu-id="7d6f2-106">Aspects of high-quality open-source .NET libraries:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="7d6f2-107">**Włączne** -bibliotek .NET dobre Dokładamy wszelkich starań do obsługi wielu platform, programowania języków i aplikacji.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-107">**Inclusive** - Good .NET libraries strive to support many platforms, programming languages, and applications.</span></span>
> * <span data-ttu-id="7d6f2-108">**Stabilna** -bibliotek .NET dobre współistnieć w ekosystemie platformy .NET w aplikacji utworzonych za pomocą wielu bibliotek.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-108">**Stable** - Good .NET libraries coexist in the .NET ecosystem, running in applications built with many libraries.</span></span>
> * <span data-ttu-id="7d6f2-109">**Zaprojektowana rozwój** -bibliotek .NET należy poprawić i ewoluować wraz z upływem czasu obsługując istniejących użytkowników.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-109">**Designed to evolve** - .NET libraries should improve and evolve over time, while supporting existing users.</span></span>
> * <span data-ttu-id="7d6f2-110">**Debugowalny** -bibliotek .NET Użyj najnowszych narzędzi do tworzenia doskonałe środowisko debugowania dla użytkowników.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-110">**Debuggable** - .NET libraries should use the latest tools to create a great debugging experience for users.</span></span>
> * <span data-ttu-id="7d6f2-111">**Zaufane** -bibliotek .NET mają zaufania deweloperów za publikowanie w usłudze NuGet za pomocą najlepszych rozwiązań dotyczących zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-111">**Trusted** - .NET libraries have developers' trust by publishing to NuGet using security best practices.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7d6f2-112">Wprowadzenie</span><span class="sxs-lookup"><span data-stu-id="7d6f2-112">Get Started</span></span>](./get-started.md)

## <a name="types-of-recommendations"></a><span data-ttu-id="7d6f2-113">Rodzajów zaleceń</span><span class="sxs-lookup"><span data-stu-id="7d6f2-113">Types of recommendations</span></span>

<span data-ttu-id="7d6f2-114">Każdy artykuł przedstawia cztery rodzaje zalecenia: **czy**, **rozważ**, **należy unikać**, i **nie**.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-114">Each article presents four types of recommendations: **Do**, **Consider**, **Avoid**, and **Do not**.</span></span> <span data-ttu-id="7d6f2-115">Typu zalecenie ma do nich wskazuje, jak silnie powinna występować.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-115">The type of recommendation indicates how strongly it should be followed.</span></span>

<span data-ttu-id="7d6f2-116">Należy wykonać prawie zawsze **czy** zalecenia.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-116">You should almost always follow a **Do** recommendation.</span></span> <span data-ttu-id="7d6f2-117">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="7d6f2-117">For example:</span></span>

<span data-ttu-id="7d6f2-118">**CZY ✔️** dystrybucji przy użyciu pakietu NuGet biblioteki.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-118">**✔️ DO** distribute your library using a NuGet package.</span></span>

<span data-ttu-id="7d6f2-119">Z drugiej strony **rozważ** ogólnie należy przestrzegać zaleceń, ale istnieje uzasadnione wyjątki od reguły i nie powinien uważasz, że nieprawidłowe o nie postępując zgodnie ze wskazówkami:</span><span class="sxs-lookup"><span data-stu-id="7d6f2-119">On the other hand, **Consider** recommendations should generally be followed, but there are legitimate exceptions to the rule and you shouldn't feel bad about not following the guidance:</span></span>

<span data-ttu-id="7d6f2-120">**ROZWAŻ ✔️** przy użyciu [SemVer 2.0.0](https://semver.org/) do wersji pakietu NuGet.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-120">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="7d6f2-121">**Należy unikać** zalecenia wspomina o identyfikatorach rzeczy, które nie są zwykle dobry pomysł, ale czasami istotne reguła ma sens:</span><span class="sxs-lookup"><span data-stu-id="7d6f2-121">**Avoid** recommendations mention things that are generally not a good idea, but breaking the rule sometimes makes sense:</span></span>

<span data-ttu-id="7d6f2-122">**Należy UNIKAĆ ❌** odwołania do pakietu NuGet, wymagających dokładna wersja.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-122">**❌ AVOID** NuGet package references that demand an exact version.</span></span>

<span data-ttu-id="7d6f2-123">I wreszcie **nie** zalecenia wskazuje coś prawie nigdy nie należy wykonać:</span><span class="sxs-lookup"><span data-stu-id="7d6f2-123">And finally, **Do not** recommendations indicate something you should almost never do:</span></span>

<span data-ttu-id="7d6f2-124">**❌ NIE** publikowanie o silnych nazwach i innych niż-o silnej nazwie wersji biblioteki.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-124">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="7d6f2-125">Na przykład `Contoso.Api` i `Contoso.Api.StrongNamed`.</span><span class="sxs-lookup"><span data-stu-id="7d6f2-125">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="7d6f2-126">Next</span><span class="sxs-lookup"><span data-stu-id="7d6f2-126">Next</span></span>](./get-started.md)