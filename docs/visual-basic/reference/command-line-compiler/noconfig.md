---
title: -noconfig —
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: a5663fff6f7351272a78947d364458c83e5b8af1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687599"
---
# <a name="-noconfig"></a>-noconfig —
Określa, czy kompilator powinien automatycznie odwołuje się powszechnie używane [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] zestawy lub importowania `System` i `Microsoft.VisualBasic` przestrzeni nazw.  
  
## <a name="syntax"></a>Składnia  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Uwagi  
 `-noconfig` Opcja informuje kompilator, aby nie kompilacji z soubor Vbc.rsp, który znajduje się w tym samym katalogu co plik Vbc.exe. Soubor Vbc.rsp odwołuje się do często używanych [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] zestawów i Importy `System` i `Microsoft.VisualBasic` przestrzeni nazw. Kompilator niejawnie odwołuje się do zestawu System.dll chyba że `-nostdlib` określono opcję. `-nostdlib` Opcja informuje kompilator, aby nie kompilować z Vbc.rsp lub automatycznie odwołuje się do zestawu System.dll.  
  
> [!NOTE]
>  Zestawy Mscorlib.dll i Microsoft.VisualBasic.dll zawsze są wywoływane.  
  
 Można zmodyfikować soubor Vbc.rsp, aby określić opcje dodatkowe kompilatora, które powinny być uwzględnione w każdej kompilacji Vbc.exe (z wyjątkiem sytuacji, określając `-noconfig` opcji). Aby uzyskać więcej informacji, zobacz [@ (Określ plik odpowiedzi)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Kompilator przetwarza opcje przekazywane do `vbc` ostatnie polecenie. W związku z tym dowolnej opcji w wierszu polecenia zastępuje ustawienie tych samych opcji w soubor Vbc.rsp.  
  
> [!NOTE]
>  `-noconfig` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.  
  
## <a name="see-also"></a>Zobacz także
- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (określenie pliku odpowiedzi)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [— Odwołanie (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
