---
title: Funkcje anonimowe - C# przewodnik programowania
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
ms.openlocfilehash: 05098d1f26526c60656cca2255a2f93922c025da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613730"
---
# <a name="anonymous-functions-c-programming-guide"></a>Funkcje anonimowe (Przewodnik programowania w języku C#)
Funkcja anonimowa jest "inline" instrukcję lub wyrażenie, który może służyć wszędzie tam, gdzie oczekiwany jest typ delegatu. Służy on do zainicjowania delegat nazwany lub przekazać je zamiast typu delegat nazwany, jako parametr metody.  
  
 Istnieją dwa rodzaje funkcje anonimowe, które są omawiane w następujących tematach:  
  
-   [Wyrażenia lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
-   [Metody anonimowe](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Wyrażenia lambda może być powiązana, drzew wyrażeń, a także delegatów.  
  
## <a name="the-evolution-of-delegates-in-c"></a>Rozwój delegatów w języku C#  
 W języku C# w wersji 1.0 utworzono wystąpienie delegata przez jawne inicjowanie przy użyciu metody, która została zdefiniowana w innym miejscu w kodzie. C# w wersji 2.0 wprowadzono koncepcję metod anonimowych, jako sposób pisania bloków instrukcji nienazwane wbudowanych, które mogą być wykonywane w wywołaniu delegata. C# 3.0 wprowadzono wyrażenia lambda, które są podobne do metod anonimowych, ale bardziej ekspresyjnego i zwięzłe. Te dwie funkcje są określane zbiorczo jako *funkcjami anonimowymi*. Ogólnie rzecz biorąc, aplikacje przeznaczone na platformę w wersji 3.5 lub nowszy z [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] należy używać wyrażeń lambda.  
  
 W poniższym przykładzie pokazano ewolucji tworzenia delegata z C# w wersji 1.0 do języka C# 3.0:  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Instrukcje, wyrażenia i operatory](../../../csharp/programming-guide/statements-expressions-operators/index.md)
- [Wyrażenia lambda](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)
- [Delegaty](../../../csharp/programming-guide/delegates/index.md)
- [Drzewa wyrażeń (C#)](../concepts/expression-trees/index.md)
