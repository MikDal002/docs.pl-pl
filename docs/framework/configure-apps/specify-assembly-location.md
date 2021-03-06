---
title: Określanie lokalizacji zestawu
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: 328fe08872a2b57d0bdf87ea9be9224795ca9ad9
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825410"
---
# <a name="specifying-an-assemblys-location"></a>Określanie lokalizacji zestawu
Istnieją dwa sposoby, aby określić lokalizację zestawu:  
  
-   Za pomocą [ \<codeBase >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) elementu.  
  
-   Za pomocą [ \<sondowanie >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elementu.  
  
 Można również użyć [narzędzia .NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) Aby określić inną lokalizację zestawu lub określić inną lokalizację dla środowiska uruchomieniowego języka wspólnego sondowania dla zestawów.  
  
## <a name="using-the-codebase-element"></a>Za pomocą \<codeBase > Element  
 Możesz użyć  **\<codeBase >** elementu tylko w konfiguracji lub wydawcy zasad plików maszyny, które również przekierowanie wersji zestawu. Środowisko wykonawcze określa, jakiego zestawu należy użyć, stosuje się ustawienie baza kodu z pliku, który określa wersję. Jeśli nie baza kodu jest zaznaczone, środowisko uruchomieniowe sondy dla zestawu w normalny sposób. Aby uzyskać więcej informacji, zobacz [jak środowisko uruchomieniowe lokalizuje zestawy](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Poniższy przykład pokazuje sposób określania lokalizacji zestawu.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **Wersji** atrybut jest wymagany dla wszystkich zestawów o silnej nazwie, ale należy pominąć dla zestawów, które są nie o silnej nazwie.  **\<CodeBase >** element wymaga **href** atrybutu. Nie można określić wersji zakresów w  **\<codeBase >** elementu.  
  
> [!NOTE]
>  Jeśli są podawania wskazówką podstawowego kodu dla zestawu, który nie jest, o silnych nazwach, wskazówka musi wskazywać podstawy aplikacji lub podkatalogiem katalogu podstawowego aplikacji.  
  
## <a name="using-the-probing-element"></a>Za pomocą \<sondowanie > Element  
 Środowisko uruchomieniowe lokalizuje zestawy, które nie mają kodu bazowego sondowanie. Aby uzyskać więcej informacji na temat badania, zobacz [jak środowisko uruchomieniowe lokalizuje zestawy](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).  
  
 Możesz użyć [ \<sondowanie >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) elementu w pliku konfiguracyjnym aplikacji, aby określić środowisko uruchomieniowe ma poszukiwać podczas lokalizowania zestawu podkatalogów. Poniższy przykład pokazuje, jak można określić katalogi, których środowisko uruchomieniowe ma wyszukiwać.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 **PrivatePath** atrybut zawiera katalogi, które środowisko wykonawcze powinno poszukać zestawów. Jeśli aplikacja znajduje się w lokalizacji C:\Program Files\MyApp, środowisko uruchomieniowe będzie szukać zestawów, które nie określisz bazy kodu w C:\Program Files\MyApp\Bin C:\Program Files\MyApp\Bin2\Subbin i C:\Program Files\MyApp\Bin3. Katalogi określone w **privatePath** musi być podkatalogi katalogu podstawowego aplikacji.  
  
## <a name="see-also"></a>Zobacz także
- [Zestawy w środowisku uruchomieniowym CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [Programowanie za pomocą zestawów](../../../docs/framework/app-domains/programming-with-assemblies.md)
- [Sposoby lokalizowania zestawów przez środowisko uruchomieniowe](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Konfigurowanie aplikacji za pomocą plików konfiguracji](index.md)
