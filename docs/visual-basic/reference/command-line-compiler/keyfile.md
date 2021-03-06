---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: 8e90535739adb4f7f8a88f91e301c2db121241a7
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759343"
---
# <a name="-keyfile"></a>-keyfile
Określa plik zawierający klucz lub parę kluczy, aby zapewnić zestawu z silną nazwą.  
  
## <a name="syntax"></a>Składnia  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a>Argumenty  
 `file`  
 Wymagana. Plik, który zawiera klucz. Jeśli nazwa pliku zawiera spację, nazwę należy ująć w znaki cudzysłowu ("").  
  
## <a name="remarks"></a>Uwagi  
 Kompilator wstawia klucz publiczny w manifeście zestawu, a następnie podpisuje ostateczny zestaw przy użyciu klucza prywatnego. Aby wygenerować plik klucza, wpisz `sn -k file` w wierszu polecenia. Aby uzyskać więcej informacji, zobacz [Sn.exe (narzędzie silnych nazw)](../../../framework/tools/sn-exe-strong-name-tool.md)).  
  
 Jeśli kompilujesz z opcją `-target:module`, nazwę pliku klucza jest przechowywany w module i włączyć do zestawu, który jest tworzony podczas kompilowania zestawu za pomocą [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).  
  
 Można również przekazać szyfrowania informacji do kompilatora przy użyciu [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md). Użyj [- delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) Jeśli chcesz, aby częściowo podpisany zestawu.  
  
 Można również określić tę opcję jako atrybut niestandardowy (<xref:System.Reflection.AssemblyKeyFileAttribute>) w kodzie źródłowym dla każdego modułu języka pośredniego firmy Microsoft.  
  
 W przypadku obu `-keyfile` i [- keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) podano (przez opcję wiersza polecenia lub przez atrybut niestandardowy) w tej samej kompilacji kompilator po raz pierwszy próbuje kontenera kluczy. Jeśli się to powiedzie, zestaw zostanie podpisany przy użyciu informacji z kontenera kluczy. Jeśli kompilator nie znajdzie kontenera kluczy, spróbuje pliku określonego przez `-keyfile`. Jeśli operacja się powiedzie, zestaw zostanie podpisany przy użyciu informacji z pliku klucza i informacje o kluczu jest zainstalowany w kontenerze kluczy (podobnie jak `sn -i`) tak, aby przy następnej kompilacji będzie obowiązywać kontenera kluczy.  
  
 Należy pamiętać, że plik klucza może zawierać tylko klucz publiczny.  
  
 Zobacz [tworzenie i zestawy Using Strong-Named](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) więcej informacji na temat podpisywania zestawu.  
  
> [!NOTE]
>  `-keyfile` Opcja nie jest dostępne w środowisku programowania Visual Studio; jest dostępna tylko podczas kompilowania kodu w wierszu polecenia.  
  
## <a name="example"></a>Przykład  
 Poniższy kod kompiluje plik źródłowy `Input.vb` i określa plik klucza.  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a>Zobacz także
- [Zestawy i globalna pamięć podręczna zestawów](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)
- [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [— Odwołanie (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
