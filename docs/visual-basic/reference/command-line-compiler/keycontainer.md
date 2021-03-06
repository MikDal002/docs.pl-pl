---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: d9ceb7b4351d2278835014235bc1f3b5f15b65c0
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2019
ms.locfileid: "55758290"
---
# <a name="-keycontainer"></a>-keycontainer
Określa nazwę kontenera kluczy parę kluczy zapewnić zestawu z silną nazwą.  
  
## <a name="syntax"></a>Składnia  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a>Argumenty  
  
|Termin|Definicja|  
|---|---|  
|`container`|Wymagana. Plik kontenera, który zawiera klucz. Nazwę pliku należy ująć w znaki cudzysłowu (""), jeśli nazwa zawiera spację.|  
  
## <a name="remarks"></a>Uwagi  
 Kompilator tworzy składnik, które można udostępnić przez wstawienie klucza publicznego do manifestu zestawu i rejestrując ostateczny zestaw przy użyciu klucza prywatnego. Aby wygenerować plik klucza, wpisz `sn -k file` w wierszu polecenia. `-i` Opcja instaluje parę kluczy w kontenerze. Aby uzyskać więcej informacji, zobacz [Sn.exe (narzędzie silnych nazw)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Jeśli kompilujesz z opcją `-target:module`, nazwę pliku klucza jest przechowywany w module i włączyć do zestawu, który jest tworzony podczas kompilowania zestawu za pomocą [- addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Można również określić tę opcję jako atrybut niestandardowy (<xref:System.Reflection.AssemblyKeyNameAttribute>) w kodzie źródłowym dla każdego modułu języka intermediate language (MSIL) firmy Microsoft.  
  
 Można również przekazać szyfrowania informacji do kompilatora przy użyciu [- keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md). Użyj [- delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) Jeśli chcesz, aby częściowo podpisany zestawu.  
  
 Zobacz [tworzenie i zestawy Using Strong-Named](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) więcej informacji na temat podpisywania zestawu.  
  
> [!NOTE]
>  `-keycontainer` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.  
  
## <a name="example"></a>Przykład  
 Poniższy kod kompiluje plik źródłowy `Input.vb` i Określa kontener klucza.  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a>Zobacz także
- [Zestawy i globalna pamięć podręczna zestawów](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
