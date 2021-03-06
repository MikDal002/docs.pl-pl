---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: e6bb04364c2f92129993e19c746fd7cb9c18dc8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648537"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Kompilator wyświetla dane wyjściowe przy użyciu kodowania UTF-8.  
  
## <a name="syntax"></a>Składnia  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumenty  
 `+` &#124; `-`  
 Opcjonalna. Wartość domyślna tej opcji to `-utf8output-`, co oznacza, że dane wyjściowe kompilatora nie używa kodowania UTF-8. Określanie `-utf8output` jest taka sama jak określanie `-utf8output+`.  
  
## <a name="remarks"></a>Uwagi  
 W niektórych konfiguracjach międzynarodowe dane wyjściowe kompilatora nie można wyświetlić prawidłowo w konsoli. W takich sytuacjach należy użyć `-utf8output` i przekierować dane wyjściowe kompilatora do pliku.  
  
> [!NOTE]
>  `-utf8output` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.  
  
## <a name="example"></a>Przykład  
 Poniższy kod kompiluje `In.vb` i instruuje kompilator, aby wyświetlić dane wyjściowe przy użyciu kodowania UTF-8.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Zobacz także
- [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
