---
title: Przekazywanie dalej typu w środowisku uruchomieniowym języka wspólnego
ms.date: 03/30/2017
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92b72667101575aebea9b60a41979e374004b541
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499265"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Przekazywanie dalej typu w środowisku uruchomieniowym języka wspólnego
Przekazywanie dalej typu umożliwia przeniesienie typu do innego zestawu bez konieczności ponownego kompilowania aplikacji, które używają oryginalnego zestawu.  
  
 Załóżmy, że aplikacja używa `Example` klasy w zestawie o nazwie `Utility.dll`. Deweloperzy `Utility.dll` może podjąć decyzję o Refaktoryzuj zestawu, a w procesie może przenieść `Example` klasy do innego zestawu. Jeśli poprzednią wersję `Utility.dll` zostaje zastąpiona przez nową wersję `Utility.dll` i jej zestaw pomocnika, aplikacji używającej `Example` klasy nie powiedzie się, ponieważ nie można zlokalizować `Example` klasy w nowej wersji zestawu `Utility.dll`.  
  
 Deweloperzy `Utility.dll` można tego uniknąć, przekazuje żądania do `Example` klasy przy użyciu <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> atrybutu. Jeśli ten atrybut zostały doliczone do nowej wersji `Utility.dll`, żądań dla `Example` klasy są przekazywane do zestawu, który teraz zawiera klasę. Istniejącej aplikacji działa normalnie, bez ponownej kompilacji.  
  
> [!NOTE]
>  .NET Framework w wersji 2.0 nie mogą przesyłać dalej typów w zestawach napisanych w języku Visual Basic. Jednak aplikacji napisanych w języku Visual Basic mogą wykorzystywać typy przekazane. Oznacza to jeśli aplikacja używa zestawu kodowane w języku C# lub C++ i typu z tego zestawu jest przekazywany do innego zestawu, aplikacji Visual Basic można użyć typ przesłany.  
  
## <a name="forwarding-types"></a>Typy przekazywania  
 Istnieją cztery kroki przekazywania typu:  
  
1.  Przenieść kod źródłowy dla typu z oryginalnego zestawu do zestawu docelowego.  
  
2.  W zestawie, w którym typ używany do można znaleźć, Dodaj <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> dla typu, który został przeniesiony. Poniższy kod przedstawia atrybut typu o nazwie `Example` , została przeniesiona.  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  Skompiluj zestaw, który zawiera teraz typu.  
  
4.  Zestaw, gdzie typ używany w zlokalizowanym z odwołania do zestawu, który teraz zawiera typ należy ponownie skompilować. Na przykład, jeśli kompilujesz z pliku C# z wiersza polecenia, użyj [/Reference (opcje kompilatora C#)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) opcję, aby określić zestaw, który zawiera typu. W języku C++, użyj [#using](/cpp/preprocessor/hash-using-directive-cpp) dyrektywy w pliku źródłowym, aby określić zestaw, który zawiera typu.  
  
## <a name="see-also"></a>Zobacz także
- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Przekazywanie dalej typu (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)
- [#using — dyrektywa](/cpp/preprocessor/hash-using-directive-cpp)
