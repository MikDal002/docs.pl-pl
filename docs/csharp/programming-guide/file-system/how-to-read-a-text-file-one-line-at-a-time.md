---
title: 'Instrukcje: Odczyt pliku jednego wiersza tekstu w czasie (Visual C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- ReadLine method [C#]
- reading text files, line by line
- text files [C#]
ms.assetid: d62e22c5-a13c-48db-af9b-f10c801b0cb1
ms.openlocfilehash: 831f306a19d926b70170c1a6ebc4ab670f1b9851
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718653"
---
# <a name="how-to-read-a-text-file-one-line-at-a-time-visual-c"></a>Instrukcje: Odczyt pliku jednego wiersza tekstu w czasie (Visual C#)
Ten przykład odczytuje zawartość pliku tekstowego, jeden wiersz w czasie, na ciąg za pośrednictwem `ReadLine` metody `StreamReader` klasy. Każdy wiersz tekstu jest przechowywany w ciągu `line` i wyświetlane na ekranie.  
  
## <a name="example"></a>Przykład  
  
```csharp
int counter = 0;  
string line;  
  
// Read the file and display it line by line.  
System.IO.StreamReader file =   
    new System.IO.StreamReader(@"c:\test.txt");  
while((line = file.ReadLine()) != null)  
{  
    System.Console.WriteLine(line);  
    counter++;  
}  
  
file.Close();  
System.Console.WriteLine("There were {0} lines.", counter);  
// Suspend the screen.  
System.Console.ReadLine();  
```  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Skopiuj kod i wklej go w `Main` metoda aplikacji konsoli.  
  
 Zastąp `"c:\test.txt"` nazwą rzeczywistego pliku.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Następujące warunki mogą spowodować wyjątek:  
  
-   Plik nie istnieje.  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Nie należy podejmować decyzji dotyczących zawartości pliku na podstawie rozszerzenia nazwy pliku. Na przykład plik `myFile.cs` może nie być plik źródłowy C#.  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO?displayProperty=nameWithType>
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)
- [System plików i rejestr (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md)
