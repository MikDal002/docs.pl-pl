---
title: 'Instrukcje: Ładowanie dźwięku asynchronicznie w formularzu Windows'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SoundPlayer class [Windows Forms], loading sounds asynchronously
- sounds [Windows Forms], loading on separate threads
- threading [Windows Forms], sounds
ms.assetid: 3b6a9296-1d5e-4d52-a4ba-94366d6fe302
ms.openlocfilehash: ed1257a942eb990c9b0c6427d264013e3324326b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523678"
---
# <a name="how-to-load-a-sound-asynchronously-within-a-windows-form"></a>Instrukcje: Ładowanie dźwięku asynchronicznie w formularzu Windows
Poniższy przykład kodu asynchronicznego ładuje dźwięku z adresu URL i jest odtwarzany w nowym wątku.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/CS/Form1.cs#1)]
 [!code-vb[System.Media.SoundPlayer.LoadAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Media.SoundPlayer.LoadAsync/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
 Ten przykład wymaga:  
  
-   Odwołania do zestawów System i przestrzeń nazw System.Windows.Forms.  
  
-   Zastąp nazwę pliku `"http://www.tailspintoys.com/sounds/stop.wav"` z prawidłową nazwą pliku.  
  
 Aby dowiedzieć się, jak tworzyć aplikacje w tym przykładzie z wiersza polecenia dla języka Visual Basic lub Visual C#, zobacz [tworzenie z wiersza polecenia](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) lub [wiersza polecenia tworzenia przy użyciu csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Można także utworzyć tego przykładu w programie Visual Studio, wklejając kod do nowego projektu.  Zobacz też [jak: Skompilować i uruchomić przykładowy kod pełną Windows Forms przy użyciu programu Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Operacje na plikach powinna zostać ujęta w odpowiednie bloki obsługi wyjątków.  
  
 Następujące warunki mogą spowodować wyjątek:  
  
-   Nazwa ścieżki jest nieprawidłowo sformułowany. Na przykład zawiera znaki, które są nieprawidłowe lub jest tylko spacją (<xref:System.ArgumentException> klasy).  
  
-   Ścieżka jest tylko do odczytu (<xref:System.IO.IOException> klasy).  
  
-   Nazwa ścieżki jest `Nothing` (<xref:System.ArgumentNullException> klasy).  
  
-   Nazwa ścieżki jest za długa (<xref:System.IO.PathTooLongException> klasy).  
  
-   Ścieżka nie jest prawidłowa (<xref:System.IO.DirectoryNotFoundException> klasy).  
  
-   Ścieżka jest tylko dwukropek ":" (<xref:System.NotSupportedException> klasy).  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  
 Nie należy podejmować decyzji dotyczących zawartości pliku na podstawie rozszerzenia nazwy pliku. Na przykład plik `Form1.vb` może nie być plikiem źródłowym programu Visual Basic. Sprawdź wszystkie dane wejściowe, zanim użyjesz danych w aplikacji.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Media.SoundPlayer.LoadAsync%2A>
- <xref:System.Media.SoundPlayer.LoadCompleted>
- <xref:System.Media.SoundPlayer.Play%2A>
- [Instrukcje: Odtwarzanie dźwięku za pomocą formularza Windows](../../../../docs/framework/winforms/controls/how-to-play-a-sound-from-a-windows-form.md)
