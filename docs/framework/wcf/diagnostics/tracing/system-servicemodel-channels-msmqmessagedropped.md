---
title: System.ServiceModel.Channels.MsmqMessageDropped
ms.date: 03/30/2017
ms.assetid: 8b6e644d-fa68-4be7-abe9-3659671a37c1
ms.openlocfilehash: 6218948e89288e76034d7c3f032f3c585e286c3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570541"
---
# <a name="systemservicemodelchannelsmsmqmessagedropped"></a>System.ServiceModel.Channels.MsmqMessageDropped
Usługa MSMQ porzucić komunikatu.  
  
## <a name="description"></a>Opis  
 Śledzenia wskazuje, że wiadomości usługi MSMQ został porzucony. Gdy (używany z NetMsmqBinding lub MsmqIntegrationBinding) Windows Communication Foundation (WCF) nie będzie mógł je przetworzyć można porzucić wiadomości usługi MSMQ. Takie wiadomości są określane jako skażone komunikaty.  
  
 Zarządzanie skażonymi komunikatami zostało porzucone, kiedy `ReceiveErrorHandling` NetMsmqBinding lub MsmqIntegrationBinding zostaje ustalona `Drop`. Porzucone komunikat zostanie usunięty z kolejki i nie jest już możliwe do odzyskania.  
  
 Zobacz [obsługi komunikatów Poison](https://go.microsoft.com/fwlink/?LinkID=99546) więcej informacji na temat po wiadomości stają się zanieczyszczone oraz sposób konfigurowania usługi odpowiednio je obsłużyć.  
  
## <a name="see-also"></a>Zobacz także
- [Śledzenie](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Rozwiązywanie problemów z aplikacją za pomocą śledzenia](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Administracja i diagnostyka](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Obsługa komunikatów poison](https://go.microsoft.com/fwlink/?LinkID=99546)
