---
title: Interfejsy API, które działają na podstawie odbicia
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26a198db13e5855d9473cf7780dade9ce95e9298
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610850"
---
# <a name="apis-that-rely-on-reflection"></a>Interfejsy API, które działają na podstawie odbicia
W niektórych przypadkach użycie odbicia w kodzie nie jest oczywisty, a więc [!INCLUDE[net_native](../../../includes/net-native-md.md)] łańcucha narzędzi nie przechowują metadane, które są potrzebne w czasie wykonywania. W tym temacie omówiono niektóre typowe interfejsów API lub typowe wzorce programowania, które nie są traktowane jako część interfejs API odbicia, ale opierają się na podstawie odbicia, aby zostać pomyślnie uruchomiony. Jeśli będziesz ich używać w kodzie źródłowym, można dodać informacji o nich dyrektyw środowiska uruchomieniowego (. rd.xml) plików nie zgłaszają wywołań do tych interfejsów API [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) wyjątku lub innych wyjątków w czasie wykonywania.  
  
## <a name="typemakegenerictype-method"></a>Metoda Type.MakeGenericType  
 Dynamicznie utworzyć wystąpienia typu ogólnego `AppClass<T>` przez wywołanie metody <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> metody przy użyciu kodu w następujący sposób:  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 Dla tego kodu zakończyło się sukcesem w czasie wykonywania wymagane są kilka elementów metadanych. Pierwsza to `Browse` metadanych dla typ ogólny bez wystąpień `AppClass<T>`:  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 Dzięki temu <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> wywołanie metody powiodło się i zwraca prawidłową <xref:System.Type> obiektu.  
  
 Ale nawet wtedy, gdy dodasz metadanych dla typ ogólny bez wystąpień, wywołanie <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> metoda zgłasza wyjątek [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) wyjątek:  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.AppClass`1<System.Int32>.  
```  
  
 Następująca dyrektywa czasu wykonywania można dodać do pliku dyrektywy środowiska uruchomieniowego, aby dodać `Activate` metadanych dla określonego wystąpienia ciągu `AppClass<T>` z <xref:System.Int32?displayProperty=nameWithType>:  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"   
                   Activate="Required Public" />  
```  
  
 Każdy różne wystąpienia ciągu `AppClass<T>` wymaga oddzielnej dyrektywy, jeśli jest tworzona przy użyciu <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> metody i nie używać statycznie.  
  
## <a name="methodinfomakegenericmethod-method"></a>Metoda MethodInfo.MakeGenericMethod  
 Podana klasa `Class1` przy użyciu metody ogólnej `GetMethod<T>(T t)`, `GetMethod` może być wywoływany przez odbicie, przy użyciu kodu w następujący sposób:  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 Pomyślnie uruchomić ten kod wymaga kilku elementów metadanych:  
  
-   `Browse` metadane dla typu do wywołania metody.  
  
-   `Browse` metadane dla metody, którą chcesz się połączyć.  Jeśli jest to metoda publiczna, dodając publicznych `Browse` metadane dla typu zawierającego zawierają metody, zbyt.  
  
-   Dynamiczne metadane dla metody ma zostać wywołana, tak aby delegat wywołania odbicia nie są usuwane przez [!INCLUDE[net_native](../../../includes/net-native-md.md)] łańcucha narzędzi. W przypadku brakujących metody dynamiczne metadane następujący wyjątek jest generowany, gdy <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> metoda jest wywoływana:  
  
    ```  
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 Następujące dyrektywy środowiska uruchomieniowego upewnij się, że wszystkie wymagane metadane są dostępne:  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 A `MethodInstantiation` dyrektywa jest wymagana dla każdego wystąpienia różne metody, która jest wywołana dynamicznie, a `Arguments` element zostanie zaktualizowany w celu odzwierciedlenia każdy argument różne wystąpienia.  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a>Metody Array.CreateInstance i Type.MakeTypeArray  
 Poniższy przykład wywołuje <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> i <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> metod w danym typie `Class1`.  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 Jeśli ma metadanych tablicy nie powoduje następujący błąd:  
  
```  
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 `Browse` metadane dla typu tablicy jest wymagany do dynamicznego utworzenia wystąpienia.  Następujące dyrektyw środowiska uruchomieniowego umożliwia dynamiczne wystąpienia `Class1[]`.  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a>Zobacz także
- [Wprowadzenie](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [Dokumentacja pliku konfiguracji dyrektyw środowiska uruchomieniowego (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
