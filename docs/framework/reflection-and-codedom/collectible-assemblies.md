---
title: "Zestawów kolekcjonowanych generacji typu dynamicznego"
description: 
ms.date: 08/29/2017
ms.prod: .net
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c9a613f4cc13c3e4189a59ace2e05d01d1bcb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a><span data-ttu-id="88b54-102">Zestawów kolekcjonowanych generacji typu dynamicznego</span><span class="sxs-lookup"><span data-stu-id="88b54-102">Collectible assemblies for dynamic type generation</span></span>

<span data-ttu-id="88b54-103">*Zestawów kolekcjonowanych* są dynamiczne zestawy, które może być zwolniony bez zwalniania domeny aplikacji, w którym zostały utworzone.</span><span class="sxs-lookup"><span data-stu-id="88b54-103">*Collectible assemblies* are dynamic assemblies that can be unloaded without unloading the application domain in which they were created.</span></span> <span data-ttu-id="88b54-104">Można odzyskać wszystkie zarządzane i niezarządzane pamięci używanej przez zestawu kolekcjonowanego i typy, które zawiera.</span><span class="sxs-lookup"><span data-stu-id="88b54-104">All managed and unmanaged memory used by a collectible assembly and the types it contains can be reclaimed.</span></span> <span data-ttu-id="88b54-105">Informacje takie jak nazwa zestawu jest usuwany z wewnętrznego tabel.</span><span class="sxs-lookup"><span data-stu-id="88b54-105">Information such as the assembly name is removed from internal tables.</span></span>

<span data-ttu-id="88b54-106">Aby włączyć zwalnianie, należy użyć <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> Flaga podczas tworzenia zestawu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="88b54-106">To enable unloading, use the <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> flag when you create a dynamic assembly.</span></span> <span data-ttu-id="88b54-107">Zestaw jest przejściowy (to znaczy, że nie można jej zapisać) i ograniczenia opisane w tym podlega [ograniczenia dotyczące zestawów kolekcjonowanych](#restrictions-on-collectible-assemblies) sekcji.</span><span class="sxs-lookup"><span data-stu-id="88b54-107">The assembly is transient (that is, it cannot be saved) and is subject to limitations described in the [Restrictions on Collectible Assemblies](#restrictions-on-collectible-assemblies) section.</span></span> <span data-ttu-id="88b54-108">Środowisko uruchomieniowe języka wspólnego (CLR) zwalnia zestawu kolekcjonowanego automatycznie po zwolnieniu wszystkie obiekty skojarzone z zestawu.</span><span class="sxs-lookup"><span data-stu-id="88b54-108">The common language runtime (CLR) unloads a collectible assembly automatically when you release all objects associated with the assembly.</span></span> <span data-ttu-id="88b54-109">We wszystkich innych aspektach zestawów kolekcjonowanych są tworzone i używane w taki sam sposób jak inne zestawów dynamicznych.</span><span class="sxs-lookup"><span data-stu-id="88b54-109">In all other respects, collectible assemblies are created and used in the same way as other dynamic assemblies.</span></span>

## <a name="lifetime-of-collectible-assemblies"></a><span data-ttu-id="88b54-110">Okres istnienia zestawów kolekcjonowanych</span><span class="sxs-lookup"><span data-stu-id="88b54-110">Lifetime of collectible assemblies</span></span>

<span data-ttu-id="88b54-111">Okres istnienia zestawu kolekcjonowanego jest kontrolowana przez istnienie odwołania do typów, które zawiera i obiekty, które są tworzone na podstawie tych typów.</span><span class="sxs-lookup"><span data-stu-id="88b54-111">The lifetime of a collectible assembly is controlled by the existence of references to the types it contains and the objects that are created from those types.</span></span> <span data-ttu-id="88b54-112">Środowisko uruchomieniowe języka wspólnego nie spowoduje usunięcia zestawu tak długo, jak istnieje co najmniej jeden z następujących (`T` jest dowolnego typu, który jest zdefiniowany w zestawie):</span><span class="sxs-lookup"><span data-stu-id="88b54-112">The common language runtime does not unload an assembly as long as one or more of the following exist (`T` is any type that is defined in the assembly):</span></span> 

- <span data-ttu-id="88b54-113">Wystąpienie `T`.</span><span class="sxs-lookup"><span data-stu-id="88b54-113">An instance of `T`.</span></span>

- <span data-ttu-id="88b54-114">Wystąpienia tablicy `T`.</span><span class="sxs-lookup"><span data-stu-id="88b54-114">An instance of an array of `T`.</span></span>
 
- <span data-ttu-id="88b54-115">Wystąpienie typu ogólnego, który ma `T` jako jeden z jego argumentów typu.</span><span class="sxs-lookup"><span data-stu-id="88b54-115">An instance of a generic type that has `T` as one of its type arguments.</span></span> <span data-ttu-id="88b54-116">Dotyczy to również ogólne kolekcje `T`nawet w przypadku tej kolekcji jest pusty.</span><span class="sxs-lookup"><span data-stu-id="88b54-116">This includes generic collections of `T`, even if that collection is empty.</span></span>

- <span data-ttu-id="88b54-117">Wystąpienie <xref:System.Type> lub <xref:System.Reflection.Emit.TypeBuilder> reprezentujący `T`.</span><span class="sxs-lookup"><span data-stu-id="88b54-117">An instance of <xref:System.Type> or <xref:System.Reflection.Emit.TypeBuilder> that represents `T`.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="88b54-118">Konieczne jest zwolnienie wszystkich obiektów, które reprezentują części zestawu.</span><span class="sxs-lookup"><span data-stu-id="88b54-118">You must release all objects that represent parts of the assembly.</span></span> <span data-ttu-id="88b54-119"><xref:System.Reflection.Emit.ModuleBuilder> Definiuje `T` przechowuje odwołanie do <xref:System.Reflection.Emit.TypeBuilder>i <xref:System.Reflection.Emit.AssemblyBuilder> obiekt przechowuje odwołanie do <xref:System.Reflection.Emit.ModuleBuilder>, więc musi zostać zwolniona odwołania do tych obiektów.</span><span class="sxs-lookup"><span data-stu-id="88b54-119">The <xref:System.Reflection.Emit.ModuleBuilder> that defines `T` keeps a reference to the <xref:System.Reflection.Emit.TypeBuilder>, and the <xref:System.Reflection.Emit.AssemblyBuilder> object keeps a reference to the <xref:System.Reflection.Emit.ModuleBuilder>, so references to these objects must be released.</span></span> <span data-ttu-id="88b54-120">Nawet istnienie <xref:System.Reflection.Emit.LocalBuilder> lub <xref:System.Reflection.Emit.ILGenerator> używany do budowy `T` uniemożliwia zwalnianie.</span><span class="sxs-lookup"><span data-stu-id="88b54-120">Even the existence of a <xref:System.Reflection.Emit.LocalBuilder> or an <xref:System.Reflection.Emit.ILGenerator> used in the construction of `T` prevents unloading.</span></span>

- <span data-ttu-id="88b54-121">Statyczne odwołanie do `T` za pomocą innego typu dynamicznie zdefiniowanych `T1` jest nadal dostępny przez wykonywanie kodu.</span><span class="sxs-lookup"><span data-stu-id="88b54-121">A static reference to `T` by another dynamically defined type `T1` that is still reachable by executing code.</span></span> <span data-ttu-id="88b54-122">Na przykład `T1` może pochodzić od `T`, lub `T` może być typem parametru w metodzie `T1`.</span><span class="sxs-lookup"><span data-stu-id="88b54-122">For example, `T1` might derive from `T`, or `T` might be the type of a parameter in a method of `T1`.</span></span>
 
- <span data-ttu-id="88b54-123">A **ByRef** w polu statycznym, który należy do `T`.</span><span class="sxs-lookup"><span data-stu-id="88b54-123">A **ByRef** to a static field that belongs to `T`.</span></span>

- <span data-ttu-id="88b54-124">A <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, lub <xref:System.RuntimeMethodHandle> odwołujący się do `T` lub składnik `T`.</span><span class="sxs-lookup"><span data-stu-id="88b54-124">A <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, or <xref:System.RuntimeMethodHandle> that refers to `T` or to a component of `T`.</span></span>

- <span data-ttu-id="88b54-125">Wystąpienia dowolnego obiektu odbicia, które mogą zostać użyte pośrednio lub bezpośrednio do dostępu <xref:System.Type> obiekt, który reprezentuje `T`.</span><span class="sxs-lookup"><span data-stu-id="88b54-125">An instance of any reflection object that could be used indirectly or directly to access the <xref:System.Type> object that represents `T`.</span></span> <span data-ttu-id="88b54-126">Na przykład <xref:System.Type> obiekt do `T` można uzyskać z typem tablicy o typie elementu `T`, lub z typu ogólnego, który ma `T` jako argument typu.</span><span class="sxs-lookup"><span data-stu-id="88b54-126">For example, the <xref:System.Type> object for `T` can be obtained from an array type whose element type is `T`, or from a generic type that has `T` as a type argument.</span></span> 

- <span data-ttu-id="88b54-127">Metody `M` w stosie wywołań z dowolnego wątku, gdzie `M` jest metodą `T` lub metody poziom modułu, który jest zdefiniowany w zestawie.</span><span class="sxs-lookup"><span data-stu-id="88b54-127">A method `M` on the call stack of any thread, where `M` is a method of `T` or a module-level method that is defined in the assembly.</span></span>

- <span data-ttu-id="88b54-128">Delegat metody statycznej, który jest zdefiniowany w module tego zestawu.</span><span class="sxs-lookup"><span data-stu-id="88b54-128">A delegate to a static method that is defined in a module of the assembly.</span></span>

<span data-ttu-id="88b54-129">Jeśli tylko jeden element z tej listy istnieje tylko jeden typ lub jednej metody w zestawie, środowisko uruchomieniowe nie może zwolnić zestawu.</span><span class="sxs-lookup"><span data-stu-id="88b54-129">If only one item from this list exists for only one type or one method in the assembly, the runtime cannot unload the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="88b54-130">Środowisko uruchomieniowe nie powoduje faktycznie zwolnienia zestawu, do momentu finalizatory zostały przeprowadzone dla wszystkich elementów na liście.</span><span class="sxs-lookup"><span data-stu-id="88b54-130">The runtime does not actually unload the assembly until finalizers have run for all items in the list.</span></span>

<span data-ttu-id="88b54-131">W celu śledzenia okres istnienia, skonstruowane ogólny wpisz na przykład `List<int>` (w języku C#) lub `List(Of Integer)` (w języku Visual Basic) który są tworzone i używane w Generowanie zestawu kolekcjonowanego jest uznawany za zostały zdefiniowane w zestawie który zawiera ogólnych definicji typu lub w zestawie, który zawiera definicję jednego z jego argumentów typu.</span><span class="sxs-lookup"><span data-stu-id="88b54-131">For purposes of tracking lifetime, a constructed generic type such as `List<int>` (in C#) or `List(Of Integer)` (in Visual Basic) that is created and used in the generation of a collectible assembly is considered to have been defined either in the assembly that contains the generic type definition or in an assembly that contains the definition of one of its type arguments.</span></span> <span data-ttu-id="88b54-132">Dokładne zestawu, który jest używany jest szczegóły implementacji i ulegną zmianie.</span><span class="sxs-lookup"><span data-stu-id="88b54-132">The exact assembly that is used is an implementation detail and subject to change.</span></span>
 
## <a name="restrictions-on-collectible-assemblies"></a><span data-ttu-id="88b54-133">Ograniczenia dotyczące zestawów kolekcjonowanych</span><span class="sxs-lookup"><span data-stu-id="88b54-133">Restrictions on collectible assemblies</span></span>

<span data-ttu-id="88b54-134">Do zestawów kolekcjonowanych, obowiązują następujące ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="88b54-134">The following restrictions apply to collectible assemblies:</span></span> 

- <span data-ttu-id="88b54-135">**Statyczne odwołań** </span><span class="sxs-lookup"><span data-stu-id="88b54-135">**Static references** </span></span>  
  <span data-ttu-id="88b54-136">Typy w zestawie dynamicznym zwykłej nie mogą mieć statycznych odwołania do typów, które są zdefiniowane w zestawu kolekcjonowanego.</span><span class="sxs-lookup"><span data-stu-id="88b54-136">Types in an ordinary dynamic assembly cannot have static references to types that are defined in a collectible assembly.</span></span> <span data-ttu-id="88b54-137">Na przykład w przypadku definiowania zwykłej typu, który dziedziczy z typu w zestawie kolekcjonowanych <xref:System.NotSupportedException> wyjątku.</span><span class="sxs-lookup"><span data-stu-id="88b54-137">For example, if you define an ordinary type that inherits from a type in a collectible assembly, a <xref:System.NotSupportedException> exception is thrown.</span></span> <span data-ttu-id="88b54-138">Typ w zestawu kolekcjonowanego może mieć statyczne odwołania do typu w innym zestawie kolekcjonowanych, ale powoduje rozszerzenie okres istnienia przywoływanego zestawu do istnienia odwołaniem do zestawu.</span><span class="sxs-lookup"><span data-stu-id="88b54-138">A type in a collectible assembly can have static references to a type in another collectible assembly, but this extends the lifetime of the referenced assembly to the lifetime of the referencing assembly.</span></span>

- <span data-ttu-id="88b54-139">**Współdziałanie z COM** </span><span class="sxs-lookup"><span data-stu-id="88b54-139">**COM interop** </span></span>  
   <span data-ttu-id="88b54-140">Interfejsy modelu COM, nie może zostać zdefiniowany w ramach zestawu kolekcjonowanego, a nie wystąpień typów wewnątrz zestawów kolekcjonowanych można przekonwertować na obiekty COM.</span><span class="sxs-lookup"><span data-stu-id="88b54-140">No COM interfaces can be defined within a collectible assembly, and no instances of types within a collectible assembly can be converted into COM objects.</span></span> <span data-ttu-id="88b54-141">Typ w zestawu kolekcjonowanego nie może służyć jako wywoływana otoka COM (CCW) lub wywoływana otoka środowiska uruchomieniowego (otoki RCW).</span><span class="sxs-lookup"><span data-stu-id="88b54-141">A type in a collectible assembly cannot serve as a COM callable wrapper (CCW) or runtime callable wrapper (RCW).</span></span> <span data-ttu-id="88b54-142">Jednak typów w zestawach kolekcjonowanych można użyć obiektów implementujących interfejsy modelu COM.</span><span class="sxs-lookup"><span data-stu-id="88b54-142">However, types in collectible assemblies can use objects that implement COM interfaces.</span></span>

- <span data-ttu-id="88b54-143">**Wywołanie platformy** </span><span class="sxs-lookup"><span data-stu-id="88b54-143">**Platform invoke** </span></span>  
   <span data-ttu-id="88b54-144">Metody, które mają <xref:System.Runtime.InteropServices.DllImportAttribute> atrybut nie zostanie skompilowany, gdy są one zgłoszone w zestawu kolekcjonowanego.</span><span class="sxs-lookup"><span data-stu-id="88b54-144">Methods that have the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute will not compile when they are declared in a collectible assembly.</span></span> <span data-ttu-id="88b54-145"><xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> Nie może być używana w implementacji typu w zestawu kolekcjonowanego i takich typów nie mogą być przekazywane do kodu niezarządzanego.</span><span class="sxs-lookup"><span data-stu-id="88b54-145">The <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> instruction cannot be used in the implementation of a type in a collectible assembly, and such types cannot be marshaled to unmanaged code.</span></span> <span data-ttu-id="88b54-146">Można jednak wywoływać kodu natywnego, przy użyciu punktu wejścia, które są zadeklarowane w zestaw niekolekcjonowany.</span><span class="sxs-lookup"><span data-stu-id="88b54-146">However, you can call into native code by using an entry point that is declared in a non-collectible assembly.</span></span>
 
- <span data-ttu-id="88b54-147">**Organizowanie** </span><span class="sxs-lookup"><span data-stu-id="88b54-147">**Marshaling** </span></span>  
   <span data-ttu-id="88b54-148">Obiekty (w szczególności, delegatów), które są zdefiniowane w zestawów kolekcjonowanych nie mogą być przekazywane.</span><span class="sxs-lookup"><span data-stu-id="88b54-148">Objects (in particular, delegates) that are defined in collectible assemblies cannot be marshaled.</span></span> <span data-ttu-id="88b54-149">To ograniczenie na wszystkich typach emitowany przejściowej.</span><span class="sxs-lookup"><span data-stu-id="88b54-149">This is a restriction on all transient emitted types.</span></span>

- <span data-ttu-id="88b54-150">**Podczas ładowania zestawu** </span><span class="sxs-lookup"><span data-stu-id="88b54-150">**Assembly loading** </span></span>  
   <span data-ttu-id="88b54-151">Emisja odbicia jest tylko mechanizm, który jest obsługiwany w przypadku ładowania zestawów kolekcjonowanych.</span><span class="sxs-lookup"><span data-stu-id="88b54-151">Reflection emit is the only mechanism that is supported for loading collectible assemblies.</span></span> <span data-ttu-id="88b54-152">Zestawy, które są ładowane przy użyciu jakąkolwiek inną formę ładowania zestawu nie może być usunięty z pamięci.</span><span class="sxs-lookup"><span data-stu-id="88b54-152">Assemblies that are loaded by using any other form of assembly loading cannot be unloaded.</span></span>
 
- <span data-ttu-id="88b54-153">**Obiekty związane z kontekstem**  </span><span class="sxs-lookup"><span data-stu-id="88b54-153">**Context-bound objects**  </span></span>  
   <span data-ttu-id="88b54-154">Zmienne statyczne kontekstu nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="88b54-154">Context-static variables are not supported.</span></span> <span data-ttu-id="88b54-155">Typy w zestawu kolekcjonowanego nie może rozszerzać <xref:System.ContextBoundObject>.</span><span class="sxs-lookup"><span data-stu-id="88b54-155">Types in a collectible assembly cannot extend <xref:System.ContextBoundObject>.</span></span> <span data-ttu-id="88b54-156">Jednak kod w zestawów kolekcjonowanych użyć obiekty związane z kontekstem, które są zdefiniowane w innym miejscu.</span><span class="sxs-lookup"><span data-stu-id="88b54-156">However, code in collectible assemblies can use context-bound objects that are defined elsewhere.</span></span>

- <span data-ttu-id="88b54-157">**Dane statyczne dla wątku**     </span><span class="sxs-lookup"><span data-stu-id="88b54-157">**Thread-static data**     </span></span>  
   <span data-ttu-id="88b54-158">Zmienne statyczne dla wątku nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="88b54-158">Thread-static variables are not supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="88b54-159">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="88b54-159">See also</span></span>

[<span data-ttu-id="88b54-160">Emitowanie dynamicznych metod i zestawów</span><span class="sxs-lookup"><span data-stu-id="88b54-160">Emitting Dynamic Methods and Assemblies</span></span>](emitting-dynamic-methods-and-assemblies.md)