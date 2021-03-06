---
title: Dodawanie odwołania usługi w projekcie obsługującym podzestaw przenośny
ms.date: 03/30/2017
ms.assetid: 61ccfe0f-a34b-40ca-8f5e-725fa1b8095e
ms.openlocfilehash: dd07ab5623a66f7ad4b666955027adcaea232db4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681017"
---
# <a name="add-service-reference-in-a-portable-subset-project"></a>Dodawanie odwołania usługi w projekcie obsługującym podzestaw przenośny
Projekty obsługującym podzestaw przenośny umożliwiają deweloperom zestawu .NET do utrzymywania drzewa pojedyncze źródło i systemu kompilacji, nadal obsługując wiele implementacji .NET (pulpitu, Silverlight, Windows Phone i XBOX). Projekty obsługującym podzestaw przenośny tylko odwołania do bibliotek przenośnych platformy .NET, będące zestaw .NET framework, używanym w implementacji .NET.  
  
## <a name="add-service-reference-details"></a>Dodaj szczegóły usługi  
 Podczas dodawania odwołania do usługi w projekcie obsługującym podzestaw przenośny obowiązują następujące ograniczenia:  
  
1.  Aby uzyskać <xref:System.Xml.Serialization.XmlSerializer>, dozwolone są tylko literał kodowania. Kodowania SOAP generuje błąd podczas importowania.  
  
2.  Dla usługi używające <xref:System.Runtime.Serialization.DataContractSerializer> scenariuszy, danych zastępcza Umowa znajduje się w celu zapewnienia, że typy ponownie pochodzić tylko z obsługującym podzestaw przenośny.  
  
3.  Punkty końcowe, które zależą od powiązania nie są obsługiwane w przenośnych bibliotekach (wszystkie powiązania z wyjątkiem <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WSHttpBinding> bez przepływu transakcji, niezawodnej sesji lub kodowanie MTOM i powiązań niestandardowych równoważne) są ignorowane.  
  
4.  Nagłówki wiadomości są usuwane z wszystkie opisy wiadomości we wszystkich operacjach przed zaimportowaniem.  
  
5.  Atrybuty nieprzenośne <xref:System.ComponentModel.DesignerCategoryAttribute>, <xref:System.SerializableAttribute>, i <xref:System.ServiceModel.TransactionFlowAttribute> są usuwane z kodu serwera proxy wygenerowanego klienta.  
  
6.  Nieprzenośne właściwości ProtectionLevel, SessionMode, IsInitiating i IsTerminating są usuwane z <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, i <xref:System.ServiceModel.FaultContractAttribute>.  
  
7.  Wszystkie operacje usługi są generowane jako operacji asynchronicznych na serwerze proxy klienta.  
  
8.  Konstruktor wygenerowanego klienta, który używa typów nieprzenośne są usuwane.  
  
9. A <xref:System.Net.CookieContainer> wystąpienia jest uwidaczniany w wygenerowanego klienta.  
  
10. Komentarz zostanie wstawione w górnej części pliku zestawu i wersję generatora kodu:`// This code was auto-generated by Microsoft.VisualStudio.Portable.AddServiceReference, version 1.0.0.0`  
  
11. <xref:System.Runtime.Serialization.ISerializable> Interfejs nie jest obsługiwany.  
  
12. Powiązania Net.Tcp i PollingDuplex nie są obsługiwane.  
  
13. <xref:System.Runtime.Serialization.DataContractSerializer> Będzie zawsze używana dla błędów.  
  
14. <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> nie jest obsługiwane w projektach obsługującym podzestaw przenośny.  
  
## <a name="see-also"></a>Zobacz także
- [Uzyskiwanie dostępu do usług za pomocą klienta WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)
- [Biblioteka klas przenośnych](../../standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
