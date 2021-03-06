---
title: -langversion — (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 6fffe264377474bba14f6f086b521ccf9bd04adf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534462"
---
# <a name="-langversion-visual-basic"></a>-langversion — (Visual Basic)
Powoduje, że kompilator akceptuje tylko w przypadku składni, która znajduje się w określonej wersji języka Visual Basic.  
  
## <a name="syntax"></a>Składnia  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumenty  
 `version`  
 Wymagana. Wersja języka, który ma być używany podczas kompilacji. Akceptowane wartości to `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` i `latest`.

 Dowolnej liczby całkowite mogą być również określone przy użyciu `.0` jako wersję pomocniczą, na przykład `11.0`.

 Można wyświetlić listę wszystkich możliwych wartości, określając `-langversion:?` w wierszu polecenia.  
  
## <a name="remarks"></a>Uwagi  
 `-langversion` Opcja określa, jakie składni, kompilator akceptuje. Na przykład jeśli określisz, że wersja językowa jest 9.0, kompilator generuje błędy składni, która jest prawidłowy tylko w wersji 10.0 lub nowszy.  
  
 Można użyć tej opcji, podczas tworzenia aplikacji, że kierują do różnych wersji programu .NET Framework. Na przykład jeśli są przeznaczone dla .NET Framework 3.5, można tę opcję, aby upewnić się, że nie używasz składnię języka w wersji 10.0.  
  
 Możesz ustawić `-langversion` bezpośrednio tylko przy użyciu wiersza polecenia. Aby uzyskać więcej informacji, zobacz [przeznaczonych dla określonej wersji programu .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Przykład  
 Poniższy kod kompiluje `sample.vb` 9.0 Visual Basic.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Zobacz także
- [Kompilator wiersza polecenia programu Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Przykłady kompilacji — wiersze poleceń](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Określanie konkretnej wersji programu .NET Framework jako docelowej](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
