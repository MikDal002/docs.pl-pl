---
title: Nazwę zmiennej zakresu można wywnioskować tylko na podstawie prostej lub kwalifikowanej nazwy bez argumentów
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 8b95bb3c53210cc11966466d32924c13aee8234b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581952"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Nazwę zmiennej zakresu można wywnioskować tylko na podstawie prostej lub kwalifikowanej nazwy bez argumentów
Element programowania, który przyjmuje jeden lub więcej argumentów znajduje się w zapytaniu programu LINQ. Kompilator nie może wywnioskować zmienną zakresu, z tym elementem programowania.  
  
 **Identyfikator błędu:** BC36599  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1.  Jawna nazwa zmiennej elementu programistycznego, należy podać, jak pokazano w poniższym kodzie:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>Zobacz także
- [Wprowadzenie do LINQ w Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Select, klauzula](../../../visual-basic/language-reference/queries/select-clause.md)
