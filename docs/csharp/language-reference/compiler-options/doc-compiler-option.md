---
title: -doc (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- FileProperties.BuildAction
- /doc
helpviewer_keywords:
- comments, C# code
- XML documentation [C#], comments in source files
- doc compiler option [C#]
- Visual C#, XML documentation for
- -doc compiler option [C#]
- /doc compiler option [C#]
ms.assetid: 849eea59-c936-4311-bad8-d07404480f2a
ms.openlocfilehash: baf0084e6caa3fce8ca8c375bdcc2bcd135fa21e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646805"
---
# <a name="-doc-c-compiler-options"></a>-doc (opcje kompilatora C#)
**-Doc** opcja służy do umieszczania komentarzy do dokumentacji w pliku XML.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-doc:file  
```  
  
## <a name="arguments"></a>Argumenty  
 `file`  
 Plik wyjściowy dla formatu XML, który jest wypełniana przy użyciu komentarzy w plikach kodu źródłowego, kompilacji.  
  
## <a name="remarks"></a>Uwagi  
 W plikach kodu źródłowego komentarzy do dokumentacji, które poprzedzają poniżej można przetworzyć i dodawane do pliku XML:  
  
-   Takie typy zdefiniowane przez użytkownika jako [klasy](../../../csharp/language-reference/keywords/class.md), [delegować](../../../csharp/language-reference/keywords/delegate.md), lub [interfejsu](../../../csharp/language-reference/keywords/interface.md)  
  
-   Takich elementów członkowskich jako pole, [zdarzeń](../../../csharp/language-reference/keywords/event.md), [właściwość](../../../csharp/programming-guide/classes-and-structs/using-properties.md), lub metody  
  
 Pliku kodu źródłowego, który zawiera główny najpierw są kierowane do pliku XML.  
  
 Aby użyć pliku XML wygenerowanego do użytku z programem [IntelliSense](/visualstudio/ide/using-intellisense) funkcji, umożliwić nazwę pliku w pliku XML, który być taka sama jak zestaw ma być obsługiwane, a następnie sprawdź, czy plik .xml znajduje się w tym samym katalogu co zestaw. W związku z tym gdy zestaw jest przywoływana w projekcie programu Visual Studio, pliku XML, który znajduje się także. Zobacz [podawania komentarzy do kodu](/visualstudio/ide/supplying-xml-code-comments) i uzyskać więcej informacji.  
  
 Jeśli kompilujesz z [-target: module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), `file` będzie zawierać \<zestawu > \< /Assembly > Znaczniki, określając nazwę pliku zawierającego manifest zestawu dla pliku danych wyjściowych Kompilacja.  
  
> [!NOTE]
>  Doc — opcja ma zastosowanie do wszystkich wejściowych plików; lub, jeśli w ustawieniach projektu, wszystkie pliki w projekcie. Aby wyłączyć ostrzeżenia dotyczące komentarzy dokumentacji dla określonego pliku lub sekcji kodu, należy użyć [ostrzeżenie #pragma](../../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md).  
  
 Zobacz [tagi zalecane dla komentarzy do dokumentacji](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md) sposobów generować dokumentację z komentarzy w kodzie.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1.  Otwórz projekt **właściwości** strony.  
  
2.  Kliknij przycisk **kompilacji** kartę.  
  
3.  Modyfikowanie **pliku dokumentacji XML** właściwości.  
  
 Aby uzyskać informacje na temat sposobu programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DocumentationFile%2A>.  
  
## <a name="see-also"></a>Zobacz także

- [Opcje kompilatora C#](../../../csharp/language-reference/compiler-options/index.md)
- [Zarządzanie właściwościami projektu i rozwiązania](/visualstudio/ide/managing-project-and-solution-properties)
