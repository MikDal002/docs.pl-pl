---
title: -subsystemversion (opcje kompilatora C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: 42d9d81c4cfbf98c1d7a470a5863ac9198f16395
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738082"
---
# <a name="-subsystemversion-c-compiler-options"></a>-subsystemversion (opcje kompilatora C#)
Określa minimalną wersję podsystemu, na którym można uruchomić wygenerowany plik wykonywalny, określając w ten sposób wersje systemu Windows, na którym można uruchomić pliku wykonywalnego. Najczęściej ta opcja zapewnia, że plik wykonywalny mogą korzystać z funkcji zabezpieczeń, które nie są dostępne ze starszymi wersjami systemu Windows.  
  
> [!NOTE]
>  Aby określić samego podsystemu, użyj [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) — opcja kompilatora.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a>Parametry  
 `major.minor`  
 Minimalna wymagana wersja podsystemu, wyrażone w notacji z kropką dla wersji głównych i pomocniczych. Na przykład można określić, że aplikacja nie może działać w system operacyjny starszy niż Windows 7 po ustawieniu wartości tej opcji na 6.01, zgodnie z opisem w tabeli w dalszej części tego tematu. Należy określić wartości dla `major` i `minor` jako liczby całkowite.  
  
 Wiodące wyzerowania `minor` wersji nie zmieniają wersji, ale czy końcowe zera. Na przykład 6.1 i 6.01 odwołują się do tej samej wersji, ale 6.10 odwołuje się do innej wersji. Zaleca się, wyrażanie wersję pomocniczą w postaci dwóch cyfr, aby uniknąć mylenia go.  
  
## <a name="remarks"></a>Uwagi  
 W poniższej tabeli wymieniono typowe wersji podsystemu Windows.  
  
|Wersja Windows|Wersję podsystemu|  
|---------------------|-----------------------|  
|Windows 2000|5.00|  
|Windows XP|5.01|  
|Windows Server 2003|5.02|  
|Windows Vista|6.00|  
|Windows 7|6.01|  
|Windows Server 2008|6.01|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|  
  
## <a name="default-values"></a>Wartości domyślne  
 Wartość domyślna **- subsystemversion** — opcja kompilatora jest zależna od warunki na poniższej liście:  
  
-   Wartość domyślna to 6.02, jeśli jest ustawiona na poniższej liście wszelkie — opcja kompilatora:  
  
    -   [-target:appcontainerexe](../../../csharp/language-reference/compiler-options/target-appcontainerexe-compiler-option.md)  
  
    -   [-target:winmdobj](../../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md)  
  
    -   [-platform:arm](../../../csharp/language-reference/compiler-options/platform-compiler-option.md)  
  
-   Wartość domyślna to 6.00, jeśli używasz programu MSBuild, gdy elementem docelowym [!INCLUDE[net_v45](~/includes/net-v45-md.md)], i nie został ustawiony opcji kompilatora, które zostały określone we wcześniejszej części tej listy.  
  
-   Wartość domyślna to 4.00, jeśli żaden z poprzednich warunków jest spełniony.  
  
## <a name="setting-this-option"></a>Ustawienie tej opcji  
 Aby ustawić **- subsystemversion** — opcja kompilatora w programie Visual Studio, możesz Otwórz plik .csproj i określić wartość dla `SubsystemVersion` właściwość MSBuild XML. Nie można ustawić tę opcję w środowisku IDE programu Visual Studio. Aby uzyskać więcej informacji, zobacz "Wartości domyślnej" wcześniej w tym temacie lub [wspólne właściwości projektów MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).  
  
## <a name="see-also"></a>Zobacz także

- [Opcje kompilatora C#](../../../csharp/language-reference/compiler-options/index.md)
