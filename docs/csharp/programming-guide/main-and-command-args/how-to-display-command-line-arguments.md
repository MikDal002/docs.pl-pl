---
title: 'Instrukcje: Wyświetlanie argumentów wiersza polecenia — C# przewodnik programowania'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#], displaying
ms.assetid: b8479f2d-9e05-4d38-82da-2e61246e5437
ms.openlocfilehash: 948ff6e752b3f5cce870b483340cbbf9f4e78b01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54607718"
---
# <a name="how-to-display-command-line-arguments-c-programming-guide"></a>Instrukcje: Wyświetlanie argumentów wiersza poleceń (C# Programming Guide)
Argumenty dostarczone do pliku wykonywalnego w wierszu polecenia są dostępne za pośrednictwem opcjonalny parametr do `Main`. Argumenty są udostępniane w formie tablicy ciągów. Każdy element tablicy zawiera jeden argument. Odstępy między argumentami zostaną usunięte. Na przykład należy wziąć pod uwagę te wywołania wiersza polecenia fikcyjne pliku wykonywalnego:  
  
|Dane wejściowe w wiersza polecenia|Tablica ciągów przekazywane dla metody Main|  
|----------------------------|-------------------------------------|  
|**executable.exe b c.**|""<br /><br /> "b"<br /><br /> "c"|  
|**executable.exe jeden dwa**|"jeden"<br /><br /> "dwóch"|  
|**executable.exe "jeden dwa" trzy**|„one two”<br /><br /> "trzy"|  
  
> [!NOTE]
>  Po uruchomieniu aplikacji w programie Visual Studio, można określić argumenty wiersza poleceń w [strona debugowania, Projektant projektu](/visualstudio/ide/reference/debug-page-project-designer).  
  
## <a name="example"></a>Przykład  
 Ten przykład wyświetla argumenty wiersza polecenia przekazywane do wiersza polecenia aplikacji. Jest wyświetlone dane wyjściowe do pierwszej pozycji w powyższej tabeli.  
  
 [!code-csharp[csProgGuideMain#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-display-command-line-arguments_1.cs)]  
  
## <a name="see-also"></a>Zobacz także

- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)
- [Kompilacja za pomocą wiersza polecenia przy użyciu csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [Main() i argumenty wiersza polecenia](../../../csharp/programming-guide/main-and-command-args/index.md)
- [Instrukcje: Dostęp do argumentów wiersza polecenia za pomocą foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)
- [Main() — zwracane wartości](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)
