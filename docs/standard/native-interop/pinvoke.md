---
title: Wywołanie platformy (P/Invoke)
description: Dowiedz się, jak wywoływać funkcje natywne za pośrednictwem metody P/Invoke na platformie .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: f243fee2b246afff36732d469c6295d7e4b2fd87
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416238"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="193f6-103">Wywołanie platformy (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="193f6-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="193f6-104">P/Invoke jest to technologia, która umożliwia dostęp do struktury, wywołania zwrotne i funkcji w bibliotekach niezarządzanych w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="193f6-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="193f6-105">Większość interfejsów API P/Invoke jest zawarta w dwie przestrzeni nazw: `System` i `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="193f6-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="193f6-106">Używanie tych dwóch przestrzeni nazw zapewnią Ci narzędzia do opisywania sposobu komunikowania się za pomocą składnika macierzystego.</span><span class="sxs-lookup"><span data-stu-id="193f6-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="193f6-107">Zacznijmy od najbardziej typowym przykładem, a wywołującym niezarządzane funkcje w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="193f6-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="193f6-108">Umożliwia wyświetlanie pola komunikatu z aplikacji wiersza polecenia:</span><span class="sxs-lookup"><span data-stu-id="193f6-108">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="193f6-109">Poprzedni przykład jest proste, ale stażysta co jest potrzebne do wywoływania funkcji niezarządzanych z kodu zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="193f6-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="193f6-110">Rozważmy kroki przykładu:</span><span class="sxs-lookup"><span data-stu-id="193f6-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="193f6-111">#1. wiersz zawiera za pomocą instrukcji for `System.Runtime.InteropServices` przestrzeni nazw, który zawiera wszystkie elementy, które są potrzebne.</span><span class="sxs-lookup"><span data-stu-id="193f6-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="193f6-112">Wprowadza wiersza #7 `DllImport` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="193f6-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="193f6-113">Ten atrybut jest niezwykle istotne, ponieważ informuje, środowisko uruchomieniowe, należy go załadować niezarządzaną biblioteką DLL.</span><span class="sxs-lookup"><span data-stu-id="193f6-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="193f6-114">Przekazany ciąg jest biblioteką DLL, funkcja naszym docelowym znajduje się w.</span><span class="sxs-lookup"><span data-stu-id="193f6-114">The string passed in is the DLL our target function is in.</span></span>
*   <span data-ttu-id="193f6-115">Wiersz #8 jest crux pracy P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="193f6-115">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="193f6-116">Definiuje metody zarządzanej, która ma **dokładnie tym samym podpisie** , niezarządzanych.</span><span class="sxs-lookup"><span data-stu-id="193f6-116">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="193f6-117">Deklaracja ma nowe słowo kluczowe, które można zauważyć, `extern`informuje środowisko uruchomieniowe, to jest metody zewnętrznej oraz że po jej wywołaniu, środowisko wykonawcze powinno znajduje się w biblioteki DLL określonej w `DllImport` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="193f6-117">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="193f6-118">Rest przykładu jest po prostu wywołania metody, tak jak każda inna metoda zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="193f6-118">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="193f6-119">Przykład jest podobny dla systemu macOS.</span><span class="sxs-lookup"><span data-stu-id="193f6-119">The sample is similar for macOS.</span></span> <span data-ttu-id="193f6-120">Nazwa biblioteki w `DllImport` atrybut wymaga wprowadzenia zmian, ponieważ inny schemat nazewnictwa bibliotek dynamicznych z systemem macOS.</span><span class="sxs-lookup"><span data-stu-id="193f6-120">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="193f6-121">Następujące przykładowe używa `getpid(2)` funkcję, aby pobrać Identyfikatora procesu aplikacji i wydrukuj go do konsoli:</span><span class="sxs-lookup"><span data-stu-id="193f6-121">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

<span data-ttu-id="193f6-122">Jest również w podobny sposób na systemie Linux.</span><span class="sxs-lookup"><span data-stu-id="193f6-122">It is also similar on Linux.</span></span> <span data-ttu-id="193f6-123">Nazwa funkcji jest taka sama, ponieważ `getpid(2)` jest standardem [POSIX](https://en.wikipedia.org/wiki/POSIX) wywołanie systemowe.</span><span class="sxs-lookup"><span data-stu-id="193f6-123">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="193f6-124">Wywoływanie kodu zarządzanego z niezarządzanego kodu</span><span class="sxs-lookup"><span data-stu-id="193f6-124">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="193f6-125">Środowisko uruchomieniowe umożliwia komunikację do przepływu w obu kierunkach, co umożliwia wywołanie zwrotne wywołanie kodu zarządzanego z natywnych funkcji za pomocą wskaźnika funkcji.</span><span class="sxs-lookup"><span data-stu-id="193f6-125">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="193f6-126">W najbliższej kolejności ze wskaźnikiem funkcji w kodzie zarządzanym **delegować**, więc jest to, co umożliwia wywołania zwrotne z kodu natywnego do zarządzanego kodu.</span><span class="sxs-lookup"><span data-stu-id="193f6-126">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="193f6-127">Sposób, aby użyć tej funkcji jest podobny do procesu zarządzanego do natywnego opisany wcześniej.</span><span class="sxs-lookup"><span data-stu-id="193f6-127">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="193f6-128">Dla danego wywołania zwrotnego zdefiniowanie pełnomocnika, który pasuje do podpisu i przekazać go do metody zewnętrznej.</span><span class="sxs-lookup"><span data-stu-id="193f6-128">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="193f6-129">Środowisko uruchomieniowe będzie zajmujemy się całą resztą.</span><span class="sxs-lookup"><span data-stu-id="193f6-129">The runtime will take care of everything else.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

<span data-ttu-id="193f6-130">Przed zalet w przykładzie, dobrze jest przejrzeć sygnatur funkcji niezarządzanych, które są potrzebne do pracy z.</span><span class="sxs-lookup"><span data-stu-id="193f6-130">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="193f6-131">Funkcja wywoływana, aby wyliczyć wszystkie okna ma następujący podpis: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="193f6-131">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="193f6-132">Pierwszy parametr jest wywołanie zwrotne.</span><span class="sxs-lookup"><span data-stu-id="193f6-132">The first parameter is a callback.</span></span> <span data-ttu-id="193f6-133">Wspomniane wywołanie zwrotne ma następujący podpis: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="193f6-133">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="193f6-134">Teraz przejdźmy przykładu:</span><span class="sxs-lookup"><span data-stu-id="193f6-134">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="193f6-135">Wiersz #9, w tym przykładzie definiuje delegata, która pasuje do oznaczenia wywołania zwrotnego z niezarządzanego kodu.</span><span class="sxs-lookup"><span data-stu-id="193f6-135">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="193f6-136">Zwróć uwagę, jak typy LPARAM i HWND są reprezentowane za pomocą `IntPtr` w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="193f6-136">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="193f6-137">Wprowadzenie wiersze #13 i #14 `EnumWindows` funkcji z biblioteki user32.dll.</span><span class="sxs-lookup"><span data-stu-id="193f6-137">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="193f6-138">Wiersze #17-20 zaimplementować delegata.</span><span class="sxs-lookup"><span data-stu-id="193f6-138">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="193f6-139">Na tym prostym przykładzie chcemy tylko się dane wyjściowe dojścia do konsoli.</span><span class="sxs-lookup"><span data-stu-id="193f6-139">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="193f6-140">W wierszu #24 metody zewnętrznej jest na końcu, nazywana i przekazywana w delegacie.</span><span class="sxs-lookup"><span data-stu-id="193f6-140">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="193f6-141">Poniżej przedstawiono przykłady systemów Linux i macOS.</span><span class="sxs-lookup"><span data-stu-id="193f6-141">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="193f6-142">Dla nich używamy `ftw` funkcja, która znajduje się w `libc`, biblioteki C.</span><span class="sxs-lookup"><span data-stu-id="193f6-142">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="193f6-143">Ta funkcja jest używana na przechodzenie przez hierarchie katalogu i pobiera wskaźnik do funkcji jako jeden z jego parametrów.</span><span class="sxs-lookup"><span data-stu-id="193f6-143">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="193f6-144">Funkcja wspomniane ma następujący podpis: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="193f6-144">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

<span data-ttu-id="193f6-145">przykład z systemem macOS używa tej samej funkcji, a jedyną różnicą jest argumentem `DllImport` atrybutu, ponieważ utrzymuje systemu macOS `libc` w innym miejscu.</span><span class="sxs-lookup"><span data-stu-id="193f6-145">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

<span data-ttu-id="193f6-146">Zarówno poprzednich przykładach są zależne od parametrów, a w obu przypadkach parametry są podane jako typami zarządzanymi.</span><span class="sxs-lookup"><span data-stu-id="193f6-146">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="193f6-147">Środowisko uruchomieniowe wykonuje "dobre" i przetwarza je na ich odpowiedniki po drugiej stronie.</span><span class="sxs-lookup"><span data-stu-id="193f6-147">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="193f6-148">Dowiedz się więcej o jak typy są skierowany do kodu natywnego w naszej strony na [kierowania typu](type-marshalling.md).</span><span class="sxs-lookup"><span data-stu-id="193f6-148">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>


## <a name="more-resources"></a><span data-ttu-id="193f6-149">Inne zasoby</span><span class="sxs-lookup"><span data-stu-id="193f6-149">More resources</span></span>

*   <span data-ttu-id="193f6-150">[PInvoke.net wiki](https://www.pinvoke.net/) doskonałe witryny typu Wiki przy użyciu informacji o typowych interfejsów API systemu Win32 i sposobie ich wywoływania.</span><span class="sxs-lookup"><span data-stu-id="193f6-150">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="193f6-151">P/Invoke w witrynie MSDN</span><span class="sxs-lookup"><span data-stu-id="193f6-151">P/Invoke on MSDN</span></span>](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [<span data-ttu-id="193f6-152">Dokumentacja narzędzia mono w P/Invoke</span><span class="sxs-lookup"><span data-stu-id="193f6-152">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)