---
title: Przykład elementu UriTemplate
ms.date: 03/30/2017
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
ms.openlocfilehash: 565e01fd591149e7eefb7e125b917ddb9acccbfe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735480"
---
# <a name="uritemplate-sample"></a>Przykład elementu UriTemplate
<xref:System.UriTemplate> Klasa dostarcza metody do pracy z zestawami identyfikatory URI, które mają wspólną strukturę. Niniejszy przykład pokazuje następujące kluczowe założenia dotyczące `UriTemplate`:  
  
-   Składnia do tworzenia szablonów.  
  
-   Utworzenie wystąpienia identyfikatory URI z `UriTemplate` przy użyciu <xref:System.UriTemplate.BindByName%2A> i <xref:System.UriTemplate.BindByPosition%2A>.  
  
-   <xref:System.UriTemplateTable.Match%2A>, która jest odwróconą operacją `BindByName` i `BindByPosition`.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, tworzenie i uruchamianie aplikacji przykładowej  
  
1.  Aby kompilować rozwiązania w wersji języka C# lub Visual Basic .NET, postępuj zgodnie z instrukcjami [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Do uruchomienia przykładu w konfiguracji o jednym lub wielu maszyny, postępuj zgodnie z instrukcjami [uruchamianie przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Przykłady może już być zainstalowany na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do strony [Windows Communication Foundation (WCF) i przykłady Windows Workflow Foundation (WF) dla platformy .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) do pobierania wszystkich Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykładów. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## <a name="see-also"></a>Zobacz także
- [Tabela UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)
- [Dyspozytor tabeli UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)
