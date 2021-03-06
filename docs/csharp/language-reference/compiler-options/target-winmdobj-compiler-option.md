---
title: '-target: winmdobj (opcje kompilatora C#)'
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: 4000394a35c8990d3c5793c1313fc768a61c3271
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608969"
---
# <a name="-targetwinmdobj-c-compiler-options"></a>-target: winmdobj (opcje kompilatora C#)
Jeśli używasz **-target: winmdobj** — opcja kompilatora, kompilator tworzy plik pośredni .winmdobj, który można przekonwertować na plik binarny (.winmd) środowiska wykonawczego Windows. Plik .winmd może następnie być używany przez programy JavaScript i C++, oprócz programów zarządzanych języka.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a>Uwagi  
 **Winmdobj** ustawienie sygnalizuje kompilatorowi, że wymagany jest pośredni moduł. W odpowiedzi skrypt Visual Studio kompiluje bibliotekę klas języka C# jako plik .winmdobj. Plik .winmdobj następnie może być zasilany przez <xref:Microsoft.Build.Tasks.WinMDExp> wyeksportować narzędzie w celu utworzenia pliku metadanych (.winmd) Windows. Plik .winmd zawiera kod z oryginalnej biblioteki i metadane WinMD, które jest używane przez programy JavaScript lub C++ i przez środowisko wykonawcze Windows.  
  
 Dane wyjściowe pliku, który jest kompilowany przy użyciu **-target: winmdobj** — opcja kompilatora jest przeznaczona do użycia tylko jako dane wejściowe dla narzędzia do eksportu WimMDExp; do pliku .winmdobj nie jest przywoływany bezpośrednio.  
  
 Jeśli nie używasz [-się](../../../csharp/language-reference/compiler-options/out-compiler-option.md) opcji Nazwa pliku wyjściowego przyjmuje nazwę pierwszego pliku wejściowego. A [Main](../../../csharp/programming-guide/main-and-command-args/index.md) metoda nie jest wymagane.  
  
 W przypadku określenia opcji target: winmdobj w wierszu polecenia wszystkie pliki, aż do następnej **-się** lub [-target: module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) opcji są używane do tworzenia programów Windows.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>Aby ustawić tę opcję kompilatora w programie Visual Studio IDE dla aplikacji magazynu systemu Windows  
  
1.  W **Eksploratora rozwiązań**, otwórz menu skrótów dla projektu, a następnie wybierz **właściwości**.  
  
2.  Wybierz **aplikacji** kartę.  
  
3.  W **typ danych wyjściowych** wybierz **plik WinMD**.  
  
     **Plik WinMD** opcja jest dostępna tylko w przypadku [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)] szablonów aplikacji.  
  
 Aby dowiedzieć się, jak programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Przykład  
 Następujące polecenie kompiluje `filename.cs` do pliku .winmdobj.  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>Zobacz także

- [-target (opcje kompilatora C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [Opcje kompilatora C#](../../../csharp/language-reference/compiler-options/index.md)
