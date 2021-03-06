---
title: 'Instrukcje: Zapis w plikach binarnych w Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], binary access
- WriteAllBytes method [Visual Basic]
- binary files [Visual Basic], writing in Visual Basic
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
ms.openlocfilehash: 283c1c59d4bfa73f12ee0c9b772bf71c15a3b541
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676708"
---
# <a name="how-to-write-to-binary-files-in-visual-basic"></a>Instrukcje: Zapis w plikach binarnych w Visual Basic
<xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> Metoda zapisuje dane w pliku binarnym. Jeśli `append` parametr jest `True`, dołączy je do pliku; w przeciwnym razie zostanie zastąpiony dane w pliku.  
  
 Jeśli określona ścieżka, z wyjątkiem nazwy pliku nie jest prawidłowy, <xref:System.IO.DirectoryNotFoundException> zostanie zgłoszony wyjątek. Jeśli ścieżka jest prawidłowa, ale plik nie istnieje, zostanie utworzony plik.  
  
### <a name="to-write-to-a-binary-file"></a>Można zapisać do pliku binarnego  
  
-   Użyj `WriteAllBytes` metody, podając ścieżkę i nazwę i bajtów do zapisania. W tym przykładzie dołącza tablicy danych `CustomerData` pliku o nazwie `CollectedData.dat`.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Następujące warunki mogą utworzyć wyjątek:  
  
-   Ścieżka nie jest prawidłowa dla jednego z następujących przyczyn: jest to ciąg o zerowej długości; zawiera tylko znak odstępu; lub zawiera nieprawidłowe znaki. (<xref:System.ArgumentException>).  
  
-   Ścieżka jest nieprawidłowa, ponieważ jest on `Nothing` (<xref:System.ArgumentNullException>).  
  
-   `File` Wskazuje ścieżkę, która nie istnieje (<xref:System.IO.FileNotFoundException> lub <xref:System.IO.DirectoryNotFoundException>).  
  
-   Plik jest używany przez inny proces lub wystąpi błąd We/Wy (<xref:System.IO.IOException>).  
  
-   Ścieżka przekracza maksymalną długość zdefiniowaną przez system (<xref:System.IO.PathTooLongException>).  
  
-   Nazwa pliku lub katalogu w ścieżce zawiera dwukropek (:) lub jest w nieprawidłowym formacie (<xref:System.NotSupportedException>).  
  
-   Użytkownik nie ma wystarczających uprawnień do wyświetlania ścieżki (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Zobacz także
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>
- [Instrukcje: Zapisywanie tekstu do plików](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)
