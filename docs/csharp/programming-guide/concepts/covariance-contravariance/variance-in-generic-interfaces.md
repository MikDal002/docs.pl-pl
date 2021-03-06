---
title: Wariancje w interfejsach (C#)
ms.date: 07/20/2015
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
ms.openlocfilehash: b713cb4f2b13c54a4a60c522bbef492a5962cdc3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601796"
---
# <a name="variance-in-generic-interfaces-c"></a>Wariancje w interfejsach (C#)
.NET framework 4 wprowadzono wariancji obsługę kilka istniejących interfejsów ogólnych. Obsługa wariancja umożliwia niejawną konwersję klas, które implementują te interfejsy. Następujące interfejsy są teraz wariant:  
  
-   <xref:System.Collections.Generic.IEnumerable%601> (T jest kowariantny)  
  
-   <xref:System.Collections.Generic.IEnumerator%601> (T jest kowariantny)  
  
-   <xref:System.Linq.IQueryable%601> (T jest kowariantny)  
  
-   <xref:System.Linq.IGrouping%602> (`TKey` i `TElement` są kowariantne)  
  
-   <xref:System.Collections.Generic.IComparer%601> (T jest kontrawariantny)  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601> (T jest kontrawariantny)  
  
-   <xref:System.IComparable%601> (T jest kontrawariantny)  
  
 Kowariancja zezwala na metodę, aby mieć zwracanego typu bardziej pochodnego niż określone przez parametr typu ogólnego interfejsu. Aby zilustrować funkcji KOWARIANCJA, należy wziąć pod uwagę te ogólne interfejsy: `IEnumerable<Object>` i `IEnumerable<String>`. `IEnumerable<String>` Interfejsu nie dziedziczy `IEnumerable<Object>` interfejsu. Jednak `String` typ dziedziczyć `Object` typu, a w niektórych przypadkach możesz chcieć przypisać obiekty te interfejsy do siebie nawzajem. Jest to pokazane w poniższym przykładzie kodu.  
  
```csharp  
IEnumerable<String> strings = new List<String>();  
IEnumerable<Object> objects = strings;  
```  
  
 We wcześniejszych wersjach programu .NET Framework, ten kod powoduje błąd kompilacji w języku C# za pomocą `Option Strict On`. Teraz możesz używać, ale `strings` zamiast `objects`, jak pokazano w poprzednim przykładzie, ponieważ <xref:System.Collections.Generic.IEnumerable%601> interfejsu jest kowariantny.  
  
 Kontrawariancja umożliwia metodę, aby mieć typy argumentów, które są mniej pochodnego niż określona przez parametr ogólny interfejsu. Aby zilustrować kontrawariancja, załóżmy, że utworzono `BaseComparer` klasy do porównywania wystąpień `BaseClass` klasy. `BaseComparer` Klasy implementuje `IEqualityComparer<BaseClass>` interfejsu. Ponieważ <xref:System.Collections.Generic.IEqualityComparer%601> interfejs jest obecnie kontrawariantny, możesz użyć `BaseComparer` do porównywania wystąpień klas, które dziedziczą `BaseClass` klasy. Jest to pokazane w poniższym przykładzie kodu.  
  
```csharp  
// Simple hierarchy of classes.  
class BaseClass { }  
class DerivedClass : BaseClass { }  
  
// Comparer class.  
class BaseComparer : IEqualityComparer<BaseClass>   
{  
    public int GetHashCode(BaseClass baseInstance)  
    {  
        return baseInstance.GetHashCode();  
    }  
    public bool Equals(BaseClass x, BaseClass y)  
    {  
        return x == y;  
    }  
}  
class Program  
{  
    static void Test()  
    {  
        IEqualityComparer<BaseClass> baseComparer = new BaseComparer();  
  
        // Implicit conversion of IEqualityComparer<BaseClass> to   
        // IEqualityComparer<DerivedClass>.  
        IEqualityComparer<DerivedClass> childComparer = baseComparer;  
    }  
}  
```  
  
 Aby uzyskać więcej przykładów, zobacz [przy użyciu wariancji w interfejsach dla kolekcji ogólnych (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 Wariancje w interfejsach jest obsługiwana tylko dla typów odwołania. Typy wartości nie obsługują wariancji. Na przykład `IEnumerable<int>` nie może być niejawnie konwertowane na `IEnumerable<object>`, ponieważ liczby całkowite są reprezentowane przez typ wartości.  
  
```csharp  
IEnumerable<int> integers = new List<int>();  
// The following statement generates a compiler errror,  
// because int is a value type.  
// IEnumerable<Object> objects = integers;  
```  
  
 Jest również pamiętać, że klasy, które implementują interfejsów typu variant, są nadal niezmienne. Na przykład mimo że <xref:System.Collections.Generic.List%601> implementuje interfejs kowariantne <xref:System.Collections.Generic.IEnumerable%601>, nie można niejawnie przekonwertować `List<Object>` do `List<String>`. Jest to zilustrowane w poniższym przykładzie kodu.  
  
```csharp  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a>Zobacz także

- [Korzystanie z wariancji w interfejsach dla kolekcji ogólnych (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)
- [Tworzenie interfejsów typu Variant (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)
- [Interfejsy ogólne](../../../../standard/generics/interfaces.md)
- [Wariancje w Delegatach (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
