---
title: Delegaty ogólne — C# przewodnik programowania
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 43163e0402166c8b1b604b1b80d71763bf82bcea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546059"
---
# <a name="generic-delegates-c-programming-guide"></a>Delegaty ogólne (Przewodnik programowania w języku C#)
A [delegować](../../../csharp/language-reference/keywords/delegate.md) można zdefiniować własne parametry typu. Kod, że odwołania Delegat ogólny można określić argument typu w celu utworzenia zamknięte skonstruowanego typu, podobnie jak podczas tworzenia wystąpienia klasy ogólnej lub wywoływania metody rodzajowej, jak pokazano w poniższym przykładzie:  
  
 [!code-csharp[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 C# w wersji 2.0 zawiera nową funkcję o nazwie metody konwersji grupy dotyczy typów konkretnych, jak również ogólne delegata, która umożliwia pisanie poprzedniego wiersza składnią uproszczoną:  
  
 [!code-csharp[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 Delegaty zdefiniowany w ramach klasy ogólnej można użyć parametrów typu rodzajowego klasy w taki sam sposób, który do metody klasy.  
  
 [!code-csharp[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 Kod, który odwołuje się do obiektu delegowanego należy określić argument typu zawierającego klasy, w następujący sposób:  
  
 [!code-csharp[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 Delegaty ogólne są szczególnie użyteczne w definiując zdarzenia, oparta na wzorcu projektów, ponieważ argument nadawca może być silnie typizowane i nie ma już można rzutować do i z <xref:System.Object>.  
  
 [!code-csharp[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Collections.Generic>
- [Przewodnik programowania w języku C#](../../../csharp/programming-guide/index.md)
- [Wprowadzenie do typów ogólnych](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [Metody ogólne](../../../csharp/programming-guide/generics/generic-methods.md)
- [Klasy ogólne](../../../csharp/programming-guide/generics/generic-classes.md)
- [Interfejsy ogólne](../../../csharp/programming-guide/generics/generic-interfaces.md)
- [Delegaty](../../../csharp/programming-guide/delegates/index.md)
- [Typy ogólne](~/docs/standard/generics/index.md)
