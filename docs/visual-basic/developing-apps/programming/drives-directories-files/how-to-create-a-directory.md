---
title: 'Instrukcje: Utwórz katalog w języku Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
ms.openlocfilehash: 878ba0b8f62c067101a73182a377f5cfcb84ebc2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527435"
---
# <a name="how-to-create-a-directory-in-visual-basic"></a>Instrukcje: Utwórz katalog w języku Visual Basic
Użyj `CreateDirectory` metody `My.Computer.FileSystem` obiekt do tworzenia katalogów.  
  
 Jeśli katalog już istnieje, jest zgłaszany żaden wyjątek.  
  
### <a name="to-create-a-directory"></a>Aby utworzyć katalog  
  
-   Użyj `CreateDirectory` metody, podając pełną ścieżkę lokalizacji, w którym można utworzyć katalogu. W tym przykładzie tworzy katalog `NewDirectory` w `C:\Documents and Settings\All Users\Documents`.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Następujące warunki mogą spowodować wyjątek:  
  
-   Nazwa katalogu jest nieprawidłowo sformułowany. Na przykład zawiera niedozwolone znaki lub jest tylko spacją (<xref:System.ArgumentException>).  
  
-   Katalog, który ma zostać utworzony w katalogu nadrzędnym jest tylko do odczytu (<xref:System.IO.IOException>).  
  
-   Nazwa katalogu jest `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Nazwa katalogu jest zbyt długa (<xref:System.IO.PathTooLongException>).  
  
-   Nazwa katalogu jest dwukropek ":" (<xref:System.NotSupportedException>).  
  
-   Użytkownik nie ma uprawnień do tworzenia katalogu (<xref:System.UnauthorizedAccessException>).  
  
-   Użytkownik nie ma uprawnienia w sytuacjach częściowego zaufania (<xref:System.Security.SecurityException>).  
  
## <a name="see-also"></a>Zobacz także
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>
- [Tworzenie, usuwanie i przenoszenie plików i katalogów](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
