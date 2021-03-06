---
title: Dodatkowe biblioteki klas i interfejsów API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: a48a145cd337a18c4ce63b281e1c82032d0532e7
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674415"
---
# <a name="additional-class-libraries-and-apis"></a>Dodatkowe biblioteki klas i interfejsów API

Jest stale rozwijana i .NET Framework. Aby poprawić programowanie dla wielu platform i wprowadzać nowe funkcjonalności wcześnie, nowe funkcje są wydawane poza pasmem (OOB). Ten temat zawiera listę projektów OOB, które firma Microsoft zapewnia dokumentacji.  
  
Ponadto niektóre biblioteki kierować konkretnych platform lub implementacji .NET Framework. Na przykład <xref:System.Text.CodePagesEncodingProvider> klasy sprawia, że stron kodowych są dostępne dla aplikacji platformy uniwersalnej systemu Windows, opracowane przy użyciu programu .NET Framework. Ten temat zawiera również tych bibliotek.  
  
## <a name="oob-projects"></a>Projekty OOB
  
| Projekt | Opis |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Zawiera kolekcje, które są wątkowo bezpieczne i gwarancji nigdy nie zmieni się ich zawartości. |
| <xref:System.Net.Http.WinHttpHandler> | Udostępnia program obsługi komunikatów dla <xref:System.Net.Http.HttpClient> oparte na interfejsie WinHTTP Windows. |
| <xref:System.Numerics> | Zawiera bibliotekę typy wektorowe, które mogą korzystać SIMD przyspieszanie sprzętowe.| 
| <xref:System.Threading.Tasks.Dataflow> | Biblioteka przepływu danych TPL zapewnia składników przepływu danych, aby zwiększyć niezawodność aplikacji obsługujących współbieżności. |  

## <a name="platform-specific-libraries"></a>Biblioteki charakterystyczne dla platformy
  
| Projekt | Opis |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Rozszerza <xref:System.Text.EncodingProvider> klasy w celu udostępnienia aplikacji przeznaczonych dla platformy uniwersalnej Windows stron kodowych. |  
  
## <a name="private-apis"></a>Interfejsy API z prywatnym  

Te interfejsy API obsługuje infrastrukturę produktu i nie/obsługiwanych przeznaczonych do użycia bezpośrednio w kodzie.  
  
| Nazwa interfejsu API |
| -------- |
| [System.Net.Connection Class](../../../docs/framework/additional-apis/connection.md) |
| [System.Net.Connection.m\_WriteList Field](../../../docs/framework/additional-apis/m_writelist.md) |
| [System.Net.ConnectionGroup Class](../../../docs/framework/additional-apis/connectiongroup.md) |
| [System.Net.ConnectionGroup.m\_ConnectionList Field](../../../docs/framework/additional-apis/m_connectionlist.md) |
| [System.Net.CoreResponseData Class](../../../docs/framework/additional-apis/coreresponsedata.md) |
| [System.Net.CoreResponseData.m\_ResponseHeaders Field](../../../docs/framework/additional-apis/coreresponsedata_m_responseheaders.md) |
| [System.Net.CoreResponseData.m\_StatusCode Field](../../../docs/framework/additional-apis/coreresponsedata_m_statuscode.md) |
| [System.Net.HttpWebRequest.\_AutoRedirects Field](../../../docs/framework/additional-apis/_autoredirects.md) |
| [System.Net.HttpWebRequest.\_CoreResponse Field](../../../docs/framework/additional-apis/httpwebrequest__coreresponse.md) |
| [System.Net.HttpWebRequest.\_HttpResponse Field](../../../docs/framework/additional-apis/_httpresponse.md) |
| [System.Net.ServicePoint.m\_ConnectionGroupList Field](../../../docs/framework/additional-apis/m_connectiongrouplist.md) |
| [System.Net.ServicePointManager.s\_ServicePointTable Field](../../../docs/framework/additional-apis/s_servicepointtable.md) |
| [System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes Field](../../../docs/framework/additional-apis/s-isdebuggercheckdisabledfortestpurposes-field.md) |
| [System.Windows.Forms.Design.DataMemberFieldEditor Class](../../../docs/framework/additional-apis/datamemberfieldeditor-class.md) |
| [System.Windows.Forms.Design.DataMemberListEditor Class](../../../docs/framework/additional-apis/datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>Zobacz także

- [Program .NET Framework i wydania poza harmonogramem (OOB)](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)
