---
title: Porównanie usług sieci Web platformy ASP.NET i architektury WCF na podstawie przeznaczenia oraz stosowanych standardów
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 74ef2f3f3505125f8720695e218617817fcae82d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548381"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Porównanie usług sieci Web platformy ASP.NET i architektury WCF na podstawie przeznaczenia oraz stosowanych standardów
Usługi sieci Web programu ASP.NET został opracowany do tworzenia aplikacji, których wysyłanie i odbieranie komunikatów za pomocą proste obiektu dostępu protokołu (SOAP) przy użyciu protokołu HTTP. Struktura komunikatów można zdefiniować przy użyciu schematu XML, a narzędzie jest dostarczany w celu ułatwienia serializacji wiadomości do i z obiektów .NET Framework. Ta technologia może automatycznie generować metadane do opisu usługi sieci Web w sieci Web Services Description Language (WSDL), a drugie narzędzie towarzyszy Generowanie klientów dla usług sieci Web na podstawie pliku WSDL.  
  
 Usługi WCF jest dotyczące włączania aplikacji .NET Framework do wymiany wiadomości z innymi jednostkami oprogramowania. Domyślnie używany jest protokół SOAP, ale komunikaty mogą znajdować się w dowolnym formacie i przekazywany przy użyciu dowolnego protokołu transportu. Struktura komunikatów można zdefiniować przy użyciu schematu XML, a istnieją różne opcje dla serializacji wiadomości do i z obiektów .NET Framework. WCF może automatycznie generować metadane do opisania aplikacje utworzone przy użyciu technologii w języku WSDL. Ponadto zapewnia także narzędzie generowania klientów dla tych aplikacji na podstawie pliku WSDL.  
  
 Standardy obsługiwane przez usługi sieci Web platformy ASP.NET są udokumentowane w artykule [XML sieci Web usług utworzone za pomocą programu ASP.NET](https://go.microsoft.com/fwlink/?LinkId=94872). Bardziej rozległe lista normach obsługiwanych przez architekturę WCF znajduje się w [Web Services protokoły obsługiwane przez wiązania współdziałania System-Provided](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Zobacz także
- [Porównywanie usług internetowych platformy ASP.NET z programem WCF na podstawie procesów programistycznych](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
