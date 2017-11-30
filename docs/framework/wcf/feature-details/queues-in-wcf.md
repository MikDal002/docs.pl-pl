---
title: Kolejki programu Windows Communication Foundation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 279f6094b7e41549a285ac0175c3f949f9d8e7e1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="queues-in-windows-communication-foundation"></a><span data-ttu-id="d4fed-102">Kolejki programu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d4fed-102">Queues in Windows Communication Foundation</span></span>
<span data-ttu-id="d4fed-103">Tematy w tej sekcji omówiono w nim [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] obsługę kolejki.</span><span class="sxs-lookup"><span data-stu-id="d4fed-103">The topics in this section discuss [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for queues.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d4fed-104">zapewnia obsługę dla usługi kolejkowania wiadomości dzięki wykorzystaniu kolejkowania wiadomości Microsoft (wcześniej znane jako MSMQ) jako transportu i umożliwia realizację następujących scenariuszy:</span><span class="sxs-lookup"><span data-stu-id="d4fed-104"> provides support for queuing by leveraging Microsoft Message Queuing (previously known as MSMQ) as a transport and enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="d4fed-105">Luźno powiązanych aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d4fed-105">Loosely coupled applications.</span></span> <span data-ttu-id="d4fed-106">Wysyłanie aplikacje mogą wysyłać wiadomości do kolejki, bez dokładnej znajomości, czy aplikacja jest dostępna do przetworzenia komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d4fed-106">Sending applications can send messages to queues without needing to know whether the receiving application is available to process the message.</span></span> <span data-ttu-id="d4fed-107">Kolejka zapewnia niezależność przetwarzania, umożliwiający wysyłanie aplikacji do wysyłania wiadomości do kolejki z szybkością nie zależy od tempa aplikacje odbierające może przetwarzać komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d4fed-107">The queue provides processing independence that allows a sending application to send messages to the queue at a rate that does not depend on how fast the receiving applications can process the messages.</span></span> <span data-ttu-id="d4fed-108">Ogólnej dostępności systemu zwiększa podczas wysyłania wiadomości do kolejki jest nie ściśle powiązane do przetwarzania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d4fed-108">Overall system availability increases when sending messages to a queue is not tightly coupled to message processing.</span></span>  
  
-   <span data-ttu-id="d4fed-109">Izolacja awarii.</span><span class="sxs-lookup"><span data-stu-id="d4fed-109">Failure isolation.</span></span> <span data-ttu-id="d4fed-110">Aplikacje wysyłaniu lub odbieraniu wiadomości do kolejki może zakończyć się niepowodzeniem bez wpływu na siebie.</span><span class="sxs-lookup"><span data-stu-id="d4fed-110">Applications sending or receiving messages to a queue can fail without affecting each other.</span></span> <span data-ttu-id="d4fed-111">Jeśli na przykład, aplikacja ulegnie awarii, aplikacja wysyłająca można nadal wysyłać wiadomości do kolejki.</span><span class="sxs-lookup"><span data-stu-id="d4fed-111">If, for example, the receiving application fails, the sending application can continue to send messages to the queue.</span></span> <span data-ttu-id="d4fed-112">Jeśli odbiornik jest się ponownie, go przetworzyć wiadomości z kolejki.</span><span class="sxs-lookup"><span data-stu-id="d4fed-112">When the receiver is up again, it can process the messages from the queue.</span></span> <span data-ttu-id="d4fed-113">Błąd izolacji zwiększa ogólną niezawodności i dostępności.</span><span class="sxs-lookup"><span data-stu-id="d4fed-113">Failure isolation increases the overall system reliability and availability.</span></span>  
  
-   <span data-ttu-id="d4fed-114">Wyrównywanie obciążenia.</span><span class="sxs-lookup"><span data-stu-id="d4fed-114">Load leveling.</span></span> <span data-ttu-id="d4fed-115">Aplikacje wysyłające można przeciąży aplikacje odbierające komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d4fed-115">Sending applications can overwhelm receiving applications with messages.</span></span> <span data-ttu-id="d4fed-116">Kolejki można zarządzać szybkości przetwarzania produkcji i zużycia niedopasowanych komunikatów, aby odbiornik nie zalewowi.</span><span class="sxs-lookup"><span data-stu-id="d4fed-116">Queues can manage mismatched message production and consumption rates so that a receiver is not overwhelmed.</span></span>  
  
-   <span data-ttu-id="d4fed-117">Operacje odłączone.</span><span class="sxs-lookup"><span data-stu-id="d4fed-117">Disconnected operations.</span></span> <span data-ttu-id="d4fed-118">Wysyłania, odbierania i operacji przetwarzania może stać się rozłączona podczas komunikacji za pośrednictwem sieci dużymi opóźnieniami lub ograniczoną dostępność sieci, takich jak w przypadku urządzeń przenośnych.</span><span class="sxs-lookup"><span data-stu-id="d4fed-118">Sending, receiving, and processing operations can become disconnected when communicating over high-latency networks or limited-availability networks, such as in the case of mobile devices.</span></span> <span data-ttu-id="d4fed-119">Kolejki umożliwiają te operacje kontynuować, nawet wtedy, gdy punkty końcowe zostały odłączone.</span><span class="sxs-lookup"><span data-stu-id="d4fed-119">Queues allow these operations to continue, even when the endpoints are disconnected.</span></span> <span data-ttu-id="d4fed-120">Po ponownym ustanowieniu połączenia, kolejki przesyła dalej wiadomości do aplikacji odbierającej.</span><span class="sxs-lookup"><span data-stu-id="d4fed-120">When the connection is reestablished, the queue forwards messages to the receiving application.</span></span>  
  
 <span data-ttu-id="d4fed-121">Aby korzystać z funkcji kolejek w [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aplikacji, można użyć jednej z powiązań standardowych, lub można utworzyć powiązania niestandardowego, jeśli jedno z powiązań standardowych nie spełnia wymagań.</span><span class="sxs-lookup"><span data-stu-id="d4fed-121">To use the queues feature in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, you can use one of the standard bindings, or you can create a custom binding if one of the standard bindings does not satisfy your requirements.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d4fed-122">odpowiednich powiązań standardowych i wybierz jedną, zobacz [porady: wymiany komunikatów z punktami końcowymi WCF i aplikacji usługi kolejkowania komunikatów](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md).</span><span class="sxs-lookup"><span data-stu-id="d4fed-122"> relevant standard bindings and how to choose one, see [How to: Exchange Messages with WCF Endpoints and Message Queuing Applications](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d4fed-123">Tworzenie niestandardowych powiązań, zobacz [niestandardowego powiązania](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="d4fed-123"> creating custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4fed-124">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="d4fed-124">In This Section</span></span>  
 [<span data-ttu-id="d4fed-125">Omówienie kolejek</span><span class="sxs-lookup"><span data-stu-id="d4fed-125">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 <span data-ttu-id="d4fed-126">Omówienie koncepcji usługi kolejkowania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d4fed-126">An overview of message queuing concepts.</span></span>  
  
 [<span data-ttu-id="d4fed-127">Usługi kolejkowania wiadomości w programie WCF</span><span class="sxs-lookup"><span data-stu-id="d4fed-127">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 <span data-ttu-id="d4fed-128">Omówienie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kolejka pomocy technicznej.</span><span class="sxs-lookup"><span data-stu-id="d4fed-128">An overview of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] queue support.</span></span>  
  
 [<span data-ttu-id="d4fed-129">Porady: wymiana komunikatów z punktami końcowymi WCF umieszczonych w kolejce</span><span class="sxs-lookup"><span data-stu-id="d4fed-129">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 <span data-ttu-id="d4fed-130">Wyjaśniono, jak używać <xref:System.ServiceModel.NetMsmqBinding> klasy do komunikacji między [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta i [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usługi.</span><span class="sxs-lookup"><span data-stu-id="d4fed-130">Explains how to use the <xref:System.ServiceModel.NetMsmqBinding> class to communicate between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [<span data-ttu-id="d4fed-131">Porady: wymiana komunikatów z punktami końcowymi WCF i aplikacji usługi kolejkowania komunikatów</span><span class="sxs-lookup"><span data-stu-id="d4fed-131">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 <span data-ttu-id="d4fed-132">Wyjaśniono, jak używać <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> do komunikacji między [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] i aplikacji usługi kolejkowania komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d4fed-132">Explains how to use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> to communicate between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Message Queuing applications.</span></span>  
  
 [<span data-ttu-id="d4fed-133">Grupowanie w kolejce wiadomości w sesji</span><span class="sxs-lookup"><span data-stu-id="d4fed-133">Grouping Queued Messages in a Session</span></span>](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 <span data-ttu-id="d4fed-134">Wyjaśniono, jak wiadomości w kolejce ułatwiające przetwarzania komunikatów skorelowane przez aplikację odbierającą jednej grupy.</span><span class="sxs-lookup"><span data-stu-id="d4fed-134">Explains how to group messages in a queue to facilitate correlated message processing by a single receiving application.</span></span>  
  
 [<span data-ttu-id="d4fed-135">Tworzenie partii komunikatów w ramach transakcji</span><span class="sxs-lookup"><span data-stu-id="d4fed-135">Batching Messages in a Transaction</span></span>](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 <span data-ttu-id="d4fed-136">Wyjaśniono, jak partii komunikatów w ramach transakcji.</span><span class="sxs-lookup"><span data-stu-id="d4fed-136">Explains how to batch messages in a transaction.</span></span>  
  
 [<span data-ttu-id="d4fed-137">Przy użyciu kolejki utraconych wiadomości do obsługi transferów komunikatów zakończonych niepowodzeniem</span><span class="sxs-lookup"><span data-stu-id="d4fed-137">Using Dead-Letter Queues to Handle Message Transfer Failures</span></span>](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 <span data-ttu-id="d4fed-138">Opisano sposób obsługi błędów transferu i dostarczania wiadomości przy użyciu kolejki utraconych wiadomości oraz do przetwarzania komunikatów z kolejki utraconych wiadomości.</span><span class="sxs-lookup"><span data-stu-id="d4fed-138">Explains how to handle message transfer and delivery failures using dead letter queues and how to process messages from the dead letter queue.</span></span>  
  
 [<span data-ttu-id="d4fed-139">Obsługa komunikatów zanieczyszczonych</span><span class="sxs-lookup"><span data-stu-id="d4fed-139">Poison Message Handling</span></span>](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 <span data-ttu-id="d4fed-140">Wyjaśnia sposób obsługi wiadomości (wiadomości, które przekroczyły maksymalną liczbę prób dostarczenia do aplikacji odbierającej).</span><span class="sxs-lookup"><span data-stu-id="d4fed-140">Explains how to handle poison messages (messages that have exceeded the maximum number of delivery attempts to the receiving application).</span></span>  
  
 [<span data-ttu-id="d4fed-141">Różnice w funkcjach kolejkowania w systemach Windows Vista, Windows Server 2003 i Windows XP</span><span class="sxs-lookup"><span data-stu-id="d4fed-141">Differences in Queuing Features in Windows Vista, Windows Server 2003, and Windows XP</span></span>](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 <span data-ttu-id="d4fed-142">Zawiera podsumowanie różnic w [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kolejki funkcji między [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], i [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4fed-142">Summarizes the differences in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] queues feature between [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>  
  
 [<span data-ttu-id="d4fed-143">Zabezpieczanie komunikatów za pomocą zabezpieczeń transportu</span><span class="sxs-lookup"><span data-stu-id="d4fed-143">Securing Messages Using Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 <span data-ttu-id="d4fed-144">Opisuje sposób użyć zabezpieczeń transportu do zabezpieczenia wiadomości w kolejce.</span><span class="sxs-lookup"><span data-stu-id="d4fed-144">Describes how to use transport security to secure queued messages.</span></span>  
  
 [<span data-ttu-id="d4fed-145">Korzystanie z zabezpieczeń komunikatów</span><span class="sxs-lookup"><span data-stu-id="d4fed-145">Securing Messages Using Message Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 <span data-ttu-id="d4fed-146">Opisuje sposób skorzystaj z zabezpieczeń wiadomości w celu zabezpieczenia wiadomości w kolejce.</span><span class="sxs-lookup"><span data-stu-id="d4fed-146">Describes how to use message security to secure queued messages.</span></span>  
  
 [<span data-ttu-id="d4fed-147">Rozwiązywanie problemów obsługi komunikatów kolejek</span><span class="sxs-lookup"><span data-stu-id="d4fed-147">Troubleshooting Queued Messaging</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)  
 <span data-ttu-id="d4fed-148">Wyjaśniono, jak rozwiązać typowe problemy z kolejkowania wiadomości.</span><span class="sxs-lookup"><span data-stu-id="d4fed-148">Explains how to troubleshoot common queuing problems.</span></span>  
  
 [<span data-ttu-id="d4fed-149">Najlepsze rozwiązania w zakresie komunikacji z obsługą kolejek</span><span class="sxs-lookup"><span data-stu-id="d4fed-149">Best Practices for Queued Communication</span></span>](../../../../docs/framework/wcf/feature-details/best-practices-for-queued-communication.md)  
 <span data-ttu-id="d4fed-150">Wyjaśniono, najlepsze rozwiązania dotyczące używania [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] komunikatu w kolejce.</span><span class="sxs-lookup"><span data-stu-id="d4fed-150">Explains best practices for using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] queued communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4fed-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d4fed-151">See Also</span></span>  
 [<span data-ttu-id="d4fed-152">Usługi kolejkowania komunikatów</span><span class="sxs-lookup"><span data-stu-id="d4fed-152">Message Queuing</span></span>](http://msdn.microsoft.com/en-us/ff917e87-05d5-478f-9430-0f560675ece1)