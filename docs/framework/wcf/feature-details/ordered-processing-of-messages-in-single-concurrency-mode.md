---
title: "Uporządkowane przetwarzanie komunikatów w trybie pojedynczej współbieżności"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a90f5662-a796-46cd-ae33-30a4072838af
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a1acf4c3edb51500c2ead2e4ba33c6d3cc9c953f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ordered-processing-of-messages-in-single-concurrency-mode"></a>Uporządkowane przetwarzanie komunikatów w trybie pojedynczej współbieżności
Usługi WCF sprawia, że żadnych gwarancji dotyczących kolejności, w jakiej są przetwarzane wiadomości, chyba że zamykania kanału źródłowego.  Dla wystąpienia usługi WCF, który używa MsmqInputChannel, który nie jest podczas zamykania kanału sesji, nie będzie można przetwarzać komunikatów w kolejności. Istnieją pewne okoliczności, w których deweloper może mają w kolejności przetwarzania zachowanie, ale nie mają być używane sesje. W tym temacie opisano sposób skonfigurowania tego zachowania, gdy usługa jest uruchomiona w trybie równoległym pojedynczego.  
  
## <a name="in-order-message-processing"></a>Przetwarzanie komunikatów w kolejności  
 Nowy atrybut o nazwie <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> został dodany do <xref:System.ServiceModel.ServiceBehaviorAttribute>. Gdy <xref:System.ServiceModel.ServiceBehaviorAttribute.EnsureOrderedDispatch%2A> jest ustawiona na wartość true i <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> ustawiono <xref:System.ServiceModel.ConcurrencyMode.Single> komunikaty wysyłane do usługi będą przetwarzane w kolejności. Poniższy fragment kodu przedstawia sposób ustawiania tych atrybutów.  
  
```  
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, EnsureOrderedDispatch = true )]  
    class Service : IService  
    {  
         // ...  
    }  
```  
  
 Jeśli <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> ma ustawioną wartość inną wartość <xref:System.InvalidOperationException> jest generowany.  
  
## <a name="see-also"></a>Zobacz też  
 [Sesje, tworzenie wystąpień i współbieżność](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
 [Współbieżność](../../../../docs/framework/wcf/samples/concurrency.md)