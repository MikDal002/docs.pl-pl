---
title: Atrybut „Extension” można stosować tylko w deklaracjach „Module”, „Sub” lub „Function”
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: e2e2c41d713b0b04b8bc7208a83d059f0d16bf06
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278723"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Atrybut „Extension” można stosować tylko w deklaracjach „Module”, „Sub” lub „Function”
Jedynym sposobem, aby rozszerzyć typu danych w języku Visual Basic jest zdefiniować metodę rozszerzenia w ramach standardowego modułu. Metoda rozszerzenia może być `Sub` procedury lub `Function` procedury. Wszystkie metody rozszerzenia muszą być oznaczone atrybutem rozszerzenia, `<Extension()>`, z <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> przestrzeni nazw. Opcjonalnie moduł, który zawiera metodę rozszerzającą może być oznaczony w taki sam sposób. Zakaz używania atrybutu rozszerzenia jest nieprawidłowy.  
  
 **Identyfikator błędu:** BC36550  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Usuń atrybut rozszerzenia.  
  
-   Zmodyfikowanie Twojego rozszerzenia jako metoda, zdefiniowana w module otaczającej.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie zdefiniowano `Print` metodę `String` typu danych.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a>Zobacz także
- [Omówienie atrybuty](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Metody rozszerzeń](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Instrukcja Module](../../../visual-basic/language-reference/statements/module-statement.md)
