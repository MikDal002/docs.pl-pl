---
title: 'Instrukcje: Tworzenie aplikacji Framework prezentacji asynchronicznej Windows (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 89a4d1c244e69098971e87957f308f9a30ade6d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676643"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Instrukcje: Tworzenie aplikacji Framework prezentacji asynchronicznej Windows (WCF Data Services)
Za pomocą [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], można powiązać dane uzyskane z usługi danych do elementu interfejsu użytkownika aplikacji Windows Presentation Framework (WPF). Aby uzyskać więcej informacji, zobacz [powiązanie danych z kontrolkami](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). Można również wykonać operacje wobec usługi danych w sposób asynchroniczny, który umożliwia aplikacji nadal odpowiadać podczas oczekiwania na odpowiedź na żądanie usługi danych. Aplikacje dla programu Silverlight są wymagane do uzyskania dostępu do usługi danych asynchronicznie. Aby uzyskać więcej informacji, zobacz [operacji asynchronicznych](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 W tym temacie przedstawiono sposób asynchronicznego dostępu do usługi danych i powiąż wyniki do elementów aplikacji WPF. Przykłady w tym temacie usługi Northwind przykładowych danych i dane klienta automatycznie wygenerowany usługi klas. Ta usługa i klas danych klienta, są tworzone po ukończeniu [Szybki Start usług danych WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  
 Następujące XAML definiuje okna aplikacji WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Przykład  
 Następującą stronę związanym z kodem w pliku XAML wykonuje zapytanie asynchroniczne przy użyciu usługi danych i powiązanie wyniki do elementów w okno WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Zobacz także
- [Biblioteka klienta usług danych WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
