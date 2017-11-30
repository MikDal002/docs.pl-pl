---
title: "Klasy statyczne i statyczni członkowie klas (Przewodnik programowania w języku C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, static members
- static members [C#]
- static classes [C#]
- C# language, static classes
- static class members [C#]
ms.assetid: 235614b5-1371-4dbd-9abd-b406a8b0298b
caps.latest.revision: "49"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cf2517dd5989d36341b840ffcb476cbeb14baf54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="static-classes-and-static-class-members-c-programming-guide"></a><span data-ttu-id="0c1b3-102">Klasy statyczne i statyczni członkowie klas (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="0c1b3-102">Static Classes and Static Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="0c1b3-103">A [statycznej](../../../csharp/language-reference/keywords/static.md) klasy jest zasadniczo taki sam, jak Klasa statyczna, ale ma różnicy jednego: nie można utworzyć wystąpienia klasy statycznej.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-103">A [static](../../../csharp/language-reference/keywords/static.md) class is basically the same as a non-static class, but there is one difference: a static class cannot be instantiated.</span></span> <span data-ttu-id="0c1b3-104">Innymi słowy, nie można użyć [nowe](../../../csharp/language-reference/keywords/new.md) — słowo kluczowe, aby utworzyć zmienną typu klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-104">In other words, you cannot use the [new](../../../csharp/language-reference/keywords/new.md) keyword to create a variable of the class type.</span></span> <span data-ttu-id="0c1b3-105">Ponieważ nie ma żadnych zmienna wystąpienia, możesz uzyskać dostęp z członkami klasy statycznej przy użyciu Nazwa klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-105">Because there is no instance variable, you access the members of a static class by using the class name itself.</span></span> <span data-ttu-id="0c1b3-106">Na przykład, jeśli statycznego klasy, która jest nazywane `UtilityClass` mający publiczną metodę o nazwie `MethodA`, należy wywołać metodę, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="0c1b3-106">For example, if you have a static class that is named `UtilityClass` that has a public method named `MethodA`, you call the method as shown in the following example:</span></span>  
  
```csharp  
UtilityClass.MethodA();  
```  
  
 <span data-ttu-id="0c1b3-107">Klasa statyczna może służyć jako kontener wygodny dla zestawów metody, które właśnie działać na parametry wejściowe i nie mają do pobierania lub ustawiania wszystkie pola wystąpienia wewnętrznego.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-107">A static class can be used as a convenient container for sets of methods that just operate on input parameters and do not have to get or set any internal instance fields.</span></span> <span data-ttu-id="0c1b3-108">Na przykład w bibliotece w klas programu .NET Framework, statycznych <xref:System.Math?displayProperty=nameWithType> klasa zawiera metody, które wykonują operacje matematyczne, bez konieczności przechowywania i pobierania danych, która jest unikatowa dla konkretnego wystąpienia <xref:System.Math> klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-108">For example, in the .NET Framework Class Library, the static <xref:System.Math?displayProperty=nameWithType> class contains methods that perform mathematical operations, without any requirement to store or retrieve data that is unique to a particular instance of the <xref:System.Math> class.</span></span> <span data-ttu-id="0c1b3-109">Oznacza to należy zastosować elementów członkowskich klasy, określając nazwę klasy i nazwę metody, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-109">That is, you apply the members of the class by specifying the class name and the method name, as shown in the following example.</span></span>  
  
```csharp  
double dub = -3.14;  
Console.WriteLine(Math.Abs(dub));  
Console.WriteLine(Math.Floor(dub));  
Console.WriteLine(Math.Round(Math.Abs(dub)));  
  
// Output:  
// 3.14  
// -4  
// 3  
```  
  
 <span data-ttu-id="0c1b3-110">Podobnie jak w przypadku wszystkich typów klasy, informacje o typie dla klasy statycznej jest ładowany przez [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] środowisko uruchomieniowe języka wspólnego (CLR) po załadowaniu program, który odwołuje się do klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-110">As is the case with all class types, the type information for a static class is loaded by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] common language runtime (CLR) when the program that references the class is loaded.</span></span> <span data-ttu-id="0c1b3-111">Program nie można określić dokładnie po załadowaniu klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-111">The program cannot specify exactly when the class is loaded.</span></span> <span data-ttu-id="0c1b3-112">Jednak gwarantowane do załadowania i jego pola zainicjowane i jego Konstruktor statyczny wywoływana przed po raz pierwszy w programie odwołuje się do klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-112">However, it is guaranteed to be loaded and to have its fields initialized and its static constructor called before the class is referenced for the first time in your program.</span></span> <span data-ttu-id="0c1b3-113">Konstruktor statyczny wywołana tylko raz, a Klasa statyczna pozostaje w pamięci przez czas ich istnienia domeny aplikacji, w której znajduje się program.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-113">A static constructor is only called one time, and a static class remains in memory for the lifetime of the application domain in which your program resides.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c1b3-114">Aby utworzyć niestatyczna klasę, która umożliwia tylko jednego wystąpienia samej siebie, należy utworzyć, zobacz [implementacja Singleton w języku C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span><span class="sxs-lookup"><span data-stu-id="0c1b3-114">To create a non-static class that allows only one instance of itself to be created, see [Implementing Singleton in C#](http://go.microsoft.com/fwlink/?LinkID=100567).</span></span>  
  
 <span data-ttu-id="0c1b3-115">Poniżej przedstawiono główne elementy klasy statycznej:</span><span class="sxs-lookup"><span data-stu-id="0c1b3-115">The following list provides the main features of a static class:</span></span>  
  
-   <span data-ttu-id="0c1b3-116">Zawiera tylko statyczne elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-116">Contains only static members.</span></span>  
  
-   <span data-ttu-id="0c1b3-117">Nie można utworzyć wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-117">Cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="0c1b3-118">Jest zapieczętowany.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-118">Is sealed.</span></span>  
  
-   <span data-ttu-id="0c1b3-119">Nie może zawierać [konstruktorów wystąpienia](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0c1b3-119">Cannot contain [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="0c1b3-120">Tworzenie statycznej klasy jest w związku z tym zasadniczo taki sam jak podczas tworzenia klasy, która zawiera tylko statyczne elementy członkowskie i Konstruktor prywatny.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-120">Creating a static class is therefore basically the same as creating a class that contains only static members and a private constructor.</span></span> <span data-ttu-id="0c1b3-121">Konstruktor prywatny uniemożliwia utworzenia wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-121">A private constructor prevents the class from being instantiated.</span></span> <span data-ttu-id="0c1b3-122">Zaletą używania Klasa statyczna jest kompilator można sprawdzić upewnij się, że przypadkowo dodania żadnych członków wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-122">The advantage of using a static class is that the compiler can check to make sure that no instance members are accidentally added.</span></span> <span data-ttu-id="0c1b3-123">Kompilator gwarantuje, że nie można utworzyć wystąpienia tej klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-123">The compiler will guarantee that instances of this class cannot be created.</span></span>  
  
 <span data-ttu-id="0c1b3-124">Klasy statyczne są zapieczętowane i nie może być dziedziczona.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-124">Static classes are sealed and therefore cannot be inherited.</span></span> <span data-ttu-id="0c1b3-125">Nie można dziedziczyć dowolnej klasy, z wyjątkiem <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-125">They cannot inherit from any class except <xref:System.Object>.</span></span> <span data-ttu-id="0c1b3-126">Klasy statyczne nie mogą zawierać konstruktora wystąpienia; może jednak zawierać Konstruktor statyczny.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-126">Static classes cannot contain an instance constructor; however, they can contain a static constructor.</span></span> <span data-ttu-id="0c1b3-127">Niestatyczne klasy powinny również definiować Konstruktor statyczny, jeśli klasa zawiera statycznych elementów członkowskich, które wymagają nieuproszczony inicjowania.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-127">Non-static classes should also define a static constructor if the class contains static members that require non-trivial initialization.</span></span> <span data-ttu-id="0c1b3-128">Aby uzyskać więcej informacji, zobacz [konstruktory statyczne](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span><span class="sxs-lookup"><span data-stu-id="0c1b3-128">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c1b3-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="0c1b3-129">Example</span></span>  
 <span data-ttu-id="0c1b3-130">Oto przykład statycznej klasy, która zawiera dwie metody, których przekonwertować temperatury z c do f i f do c:</span><span class="sxs-lookup"><span data-stu-id="0c1b3-130">Here is an example of a static class that contains two methods that convert temperature from Celsius to Fahrenheit and from Fahrenheit to Celsius:</span></span>  
  
 [!code-csharp[csProgGuideObjects#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_1.cs)]  
  
## <a name="static-members"></a><span data-ttu-id="0c1b3-131">Statyczne elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="0c1b3-131">Static Members</span></span>  
 <span data-ttu-id="0c1b3-132">Klasy statyczne nie może zawierać metod statycznych, pola, właściwości lub zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-132">A non-static class can contain static methods, fields, properties, or events.</span></span> <span data-ttu-id="0c1b3-133">Statyczny element członkowski jest można wywołać w klasie, nawet wtedy, gdy utworzono żadne wystąpienie klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-133">The static member is callable on a class even when no instance of the class has been created.</span></span> <span data-ttu-id="0c1b3-134">Statyczny element członkowski jest zawsze dostęp do nazwy klasy, a nie nazwę wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-134">The static member is always accessed by the class name, not the instance name.</span></span> <span data-ttu-id="0c1b3-135">Istnieje tylko jedna kopia statycznego elementu członkowskiego, niezależnie od tego, jak wiele wystąpień klasy są tworzone.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-135">Only one copy of a static member exists, regardless of how many instances of the class are created.</span></span> <span data-ttu-id="0c1b3-136">Właściwości i metod statycznych nie można uzyskać dostępu niestatycznego pola i zdarzeń w ich typ zawierający, a nie może uzyskać dostępu do zmiennej wystąpienia dowolnego obiektu, chyba że jawnie przekazany parametr metody.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-136">Static methods and properties cannot access non-static fields and events in their containing type, and they cannot access an instance variable of any object unless it is explicitly passed in a method parameter.</span></span>  
  
 <span data-ttu-id="0c1b3-137">Jest bardziej typowego do zadeklarowania klasy niestatycznego z niektórych statycznych elementów członkowskich, niż Aby zadeklarować całej klasy jako statyczny.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-137">It is more typical to declare a non-static class with some static members, than to declare an entire class as static.</span></span> <span data-ttu-id="0c1b3-138">Najczęstsze zastosowania dwóch pól statycznych są zachowanie liczbę liczbę obiektów, które zostały utworzone, lub do przechowywania wartości, które muszą być współużytkowane przez wszystkie wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-138">Two common uses of static fields are to keep a count of the number of objects that have been instantiated, or to store a value that must be shared among all instances.</span></span>  
  
 <span data-ttu-id="0c1b3-139">Metody statyczne mogą być przeciążone, ale nie została zastąpiona, ponieważ należą do klasy, a nie do dowolnego wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-139">Static methods can be overloaded but not overridden, because they belong to the class, and not to any instance of the class.</span></span>  
  
 <span data-ttu-id="0c1b3-140">Mimo że pola nie może być zadeklarowany jako `static const`, [const](../../../csharp/language-reference/keywords/const.md) pole jest zasadniczo statyczne w jego zachowania.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-140">Although a field cannot be declared as `static const`, a [const](../../../csharp/language-reference/keywords/const.md) field is essentially static in its behavior.</span></span> <span data-ttu-id="0c1b3-141">Należy do tego typu, a nie do wystąpień typu.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-141">It belongs to the type, not to instances of the type.</span></span> <span data-ttu-id="0c1b3-142">W związku z tym const pola są dostępne za pomocą takie same `ClassName.MemberName` notation używanym dla pola statyczne.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-142">Therefore, const fields can be accessed by using the same `ClassName.MemberName` notation that is used for static fields.</span></span> <span data-ttu-id="0c1b3-143">Żadne wystąpienie obiektu jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-143">No object instance is required.</span></span>  
  
 <span data-ttu-id="0c1b3-144">C# nie obsługuje statycznych zmiennych lokalnych (zmienne, które są zadeklarowane w zakresie metody).</span><span class="sxs-lookup"><span data-stu-id="0c1b3-144">C# does not support static local variables (variables that are declared in method scope).</span></span>  
  
 <span data-ttu-id="0c1b3-145">Deklarowanie klas statycznych elementów członkowskich za pomocą `static` — słowo kluczowe przed zwracanym typem elementu członkowskiego, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="0c1b3-145">You declare static class members by using the `static` keyword before the return type of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_2.cs)]  
  
 <span data-ttu-id="0c1b3-146">Statyczne elementy członkowskie są inicjowane przed statyczny element członkowski jest dostępny po raz pierwszy, a przed statycznego konstruktora, jeśli istnieje, jest wywoływana.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-146">Static members are initialized before the static member is accessed for the first time and before the static constructor, if there is one, is called.</span></span> <span data-ttu-id="0c1b3-147">Aby uzyskać dostęp do elementu członkowskiego klasy statycznej, użyj nazwy klasy zamiast nazwy zmiennej do określenia lokalizacji elementu członkowskiego, jak pokazano w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="0c1b3-147">To access a static class member, use the name of the class instead of a variable name to specify the location of the member, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/static-classes-and-static-class-members_3.cs)]  
  
 <span data-ttu-id="0c1b3-148">Jeśli klasa zawiera pola statyczne, podaj statycznego konstruktora, który inicjuje je po załadowaniu klasy.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-148">If your class contains static fields, provide a static constructor that initializes them when the class is loaded.</span></span>  
  
 <span data-ttu-id="0c1b3-149">Wywołanie metody statycznej generuje instrukcję wywołanie w języku pośrednim firmy Microsoft (MSIL), natomiast generuje wywołanie do metody wystąpienia `callvirt` instrukcji, która sprawdza również dla obiekt zerowy odwołuje się do.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-149">A call to a static method generates a call instruction in Microsoft intermediate language (MSIL), whereas a call to an instance method generates a `callvirt` instruction, which also checks for a null object references.</span></span> <span data-ttu-id="0c1b3-150">Jednak w większości przypadków różnicy wydajności między tymi dwoma nie ma znaczenia.</span><span class="sxs-lookup"><span data-stu-id="0c1b3-150">However, most of the time the performance difference between the two is not significant.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0c1b3-151">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="0c1b3-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0c1b3-152">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0c1b3-152">See Also</span></span>  
 [<span data-ttu-id="0c1b3-153">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="0c1b3-153">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0c1b3-154">statyczne</span><span class="sxs-lookup"><span data-stu-id="0c1b3-154">static</span></span>](../../../csharp/language-reference/keywords/static.md)  
 [<span data-ttu-id="0c1b3-155">Klasy</span><span class="sxs-lookup"><span data-stu-id="0c1b3-155">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)  
 [<span data-ttu-id="0c1b3-156">klasy</span><span class="sxs-lookup"><span data-stu-id="0c1b3-156">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="0c1b3-157">Konstruktory statyczne</span><span class="sxs-lookup"><span data-stu-id="0c1b3-157">Static Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
 [<span data-ttu-id="0c1b3-158">Konstruktory wystąpień</span><span class="sxs-lookup"><span data-stu-id="0c1b3-158">Instance Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)