---
title: "Kwalifikowanie typów .NET do międzyoperacyjności"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b6487c151f49f6084977deb600e7f93e5eb7acee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="qualifying-net-types-for-interoperation"></a>Kwalifikowanie typów .NET do międzyoperacyjności
Jeśli zamierzasz ujawniać typów w zestawie do aplikacji modelu COM, należy uwzględnić wymagania Usługa międzyoperacyjna modelu COM w czasie projektowania. Typy zarządzane (klasy, interfejsu struktury i wyliczenia) są bezproblemowo integrowane z typów COM podczas stosować się do następujących wytycznych:  
  
-   Klasy powinny jawnie implementować interfejsów.  
  
     Współdziałanie z COM zapewnia mechanizm do automatycznego generowania interfejs zawierający wszystkie elementy członkowskie klasy i elementów członkowskich klasy podstawowej, jednak dotychczas lepiej jest zapewnienie jawne interfejsy. Interfejs automatycznie generowanych nosi nazwę interfejsu klasy. Aby uzyskać wskazówki, zobacz [wprowadzenie interfejsu klasy](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024).  
  
     Można użyć [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# i C++ włączenie definicji interfejsów w kodzie, zamiast używać języka definicji interfejsu (IDL) lub jego odpowiednik. Szczegółowe informacje składni zobacz dokumentację języka.  
  
-   Typy zarządzane muszą być publiczne.  
  
     Tylko typy publiczne w zestawie są rejestrowane i wyeksportowane do biblioteki typów. W związku z tym tylko typy publiczne są widoczne dla modelu COM.  
  
     Zarządzane typy Uwidacznianie funkcji do innych kod zarządzany, które nie mogą zostać udostępnione modelowi COM. Na przykład stałej pola, metody statyczne i konstruktory sparametryzowane nie są widoczne dla klientów modelu COM. Co więcej ponieważ środowisko uruchomieniowe marshals danych do i z typem, danych może skopiowane lub przekształcenia.  
  
-   Metody, właściwości, pól i zdarzenia muszą być publiczne.  
  
     Elementy członkowskie typów publicznych również muszą być publiczne, jeśli mają być widoczne dla modelu COM. Można ograniczyć widoczność zestawu, typu publicznego lub publiczne elementy członkowskie typu publicznego, stosując <xref:System.Runtime.InteropServices.ComVisibleAttribute>. Domyślnie wszystkie typy publiczne i elementy członkowskie są widoczne.  
  
-   Typy muszą mieć publicznego konstruktora domyślnego do aktywacji z modelu COM.  
  
     Typy zarządzane, public są widoczne dla modelu COM. Jednak bez publicznego konstruktora domyślnego (konstruktora bez argumentów), klienci COM nie można utworzyć typu. Klienci COM można nadal używać typu, jeśli jest aktywowany przy użyciu innych metod.  
  
-   Typy nie mogą być abstrakcyjne.  
  
     Klienci COM ani klientów platformy .NET nie można utworzyć typy abstrakcyjne.  
  
 Podczas eksportowania dla modelu COM, właściwości jest spłaszczona hierarchii dziedziczenia typu zarządzanego. Przechowywanie wersji różni się między środowiskami zarządzane i niezarządzane. Typy widoczne dla modelu COM nie mają takie same charakterystyki przechowywania wersji, jak inne typy zarządzane.  
  
## <a name="see-also"></a>Zobacz też  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>  
 [Udostępnianie składników .NET Framework modelowi COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Wprowadzenie do interfejsu klasy](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)  
 [Stosowanie atrybutów międzyoperacyjności](../../../docs/framework/interop/applying-interop-attributes.md)  
 [Pakowanie zestawu dla modelu COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)