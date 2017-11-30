---
title: "Trwałość przepływu pracy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e51873533d75e85c59baf0c77f587ed38a689770
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-persistence"></a><span data-ttu-id="25a78-102">Trwałość przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="25a78-102">Workflow Persistence</span></span>
<span data-ttu-id="25a78-103">Trwałość przepływu pracy jest trwałe przechwytywania stanu wystąpienia przepływu pracy, niezależnie od informacji procesu lub komputera.</span><span class="sxs-lookup"><span data-stu-id="25a78-103">Workflow persistence is the durable capture of a workflow instance's state, independent of process or computer information.</span></span> <span data-ttu-id="25a78-104">Jest to zrobić, aby przekazać dobrze znanego punktu odzyskiwania dla wystąpienia przepływu pracy w przypadku awarii systemu lub zachować pamięci przez zwalnianie wystąpienia przepływu pracy, które są aktywnie niewykonania pracy lub przenoszenie stanu wystąpienia przepływu pracy z jednego węzła do innego węzeł w farmie serwerów.</span><span class="sxs-lookup"><span data-stu-id="25a78-104">This is done to provide a well-known point of recovery for the workflow instance in the event of system failure, or to preserve memory by unloading workflow instances that are not actively doing work, or to move the state of the workflow instance from one node to another node in a server farm.</span></span>  
  
 <span data-ttu-id="25a78-105">Trwałość umożliwia elastyczność procesu, skalowalność, odzyskiwania w wypadku awarii i możliwość bardziej wydajnie zarządzać pamięcią.</span><span class="sxs-lookup"><span data-stu-id="25a78-105">Persistence enables process agility, scalability, recovery in the face of failure, and the ability to manage memory more efficiently.</span></span> <span data-ttu-id="25a78-106">Proces trwałości obejmuje określenie punktu trwałości, zbieranie danych można zapisać i na koniec delegowania rzeczywistego magazynu danych do dostawcy trwałości.</span><span class="sxs-lookup"><span data-stu-id="25a78-106">The persistence process includes the identification of a persistence point, the gathering of the data to be saved, and finally the delegation of the actual storage of the data to a persistence provider.</span></span>  
  
 <span data-ttu-id="25a78-107">Włączanie utrwalania przepływu pracy, należy skojarzyć magazyn wystąpienia z **WorkflowApplication** lub **obiektu WorkflowServiceHost** wymienionych w [jak: Włącz trwałość dla Przepływy pracy i przepływ pracy usług](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="25a78-107">To enable persistence for a workflow, you need to associate an instance store with the **WorkflowApplication** or **WorkflowServiceHost** as mentioned in [How to: Enable Persistence for Workflows and Workflow Services](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="25a78-108">**WorkflowApplication** i **obiektu WorkflowServiceHost** umożliwiają w magazynie wystąpień skojarzonych z nimi utrwalanie wystąpienia przepływu pracy w magazynie informacji o trwałości i ładowanie wystąpienia przepływu pracy do pamięć oparte na dane wystąpienia przepływu pracy, które są przechowywane w magazynie informacji o trwałości.</span><span class="sxs-lookup"><span data-stu-id="25a78-108">The **WorkflowApplication** and **WorkflowServiceHost** use the instance store associated with them to enable persisting workflow instances into a persistence store and loading workflow instances into memory based on the workflow instance data stored in the persistence store.</span></span>  
  
 <span data-ttu-id="25a78-109">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] Jest dostarczany z **SqlWorkflowInstanceStore** klasy, która zezwala na trwałość danych i metadane dotyczące wystąpienia przepływu pracy w bazie danych programu SQL Server 2005 lub SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="25a78-109">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with the **SqlWorkflowInstanceStore** class, which allows persistence of data and metadata about workflow instances into a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="25a78-110">Zobacz [magazyn wystąpienia przepływu pracy SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) więcej szczegółów.</span><span class="sxs-lookup"><span data-stu-id="25a78-110">See [SQL Workflow Instance Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) for more details.</span></span>  
  
 <span data-ttu-id="25a78-111">Do przechowywania i załaduj swoje dane specyficzne dla aplikacji, oraz informacje dotyczące wystąpienia przepływu pracy, można utworzyć uczestników trwałości, które rozszerzają <xref:System.Activities.Persistence.PersistenceParticipant> klasy.</span><span class="sxs-lookup"><span data-stu-id="25a78-111">To store and load your application-specific data along with the workflow instance-related information, you can create persistence participants that extend the <xref:System.Activities.Persistence.PersistenceParticipant> class.</span></span> <span data-ttu-id="25a78-112">Uczestnika trwałości uczestniczy w procesie trwałości można zapisać w magazynie informacji o trwałości, aby załadować dane z magazynu wystąpień w pamięci i wykonywać żadnych dodatkowych logiki w ramach transakcji trwałości niestandardowe dane do serializacji.</span><span class="sxs-lookup"><span data-stu-id="25a78-112">A persistence participant participates in the persistence process to save custom serializable data into the persistence store, to load the data from the instance store into memory, and to perform any additional logic under a persistence transaction.</span></span> <span data-ttu-id="25a78-113">Aby uzyskać więcej informacji, zobacz [uczestników trwałości](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span><span class="sxs-lookup"><span data-stu-id="25a78-113">For more information, see [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).</span></span>  
  
 <span data-ttu-id="25a78-114">Windows Server AppFabric upraszcza proces konfigurowania trwałości.</span><span class="sxs-lookup"><span data-stu-id="25a78-114">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="25a78-115">[Koncepcji trwałości z systemu Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span><span class="sxs-lookup"><span data-stu-id="25a78-115"> [Persistence Concepts with Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)</span></span>  
  
## <a name="implicit-persistence-points"></a><span data-ttu-id="25a78-116">Niejawne punktów trwałości</span><span class="sxs-lookup"><span data-stu-id="25a78-116">Implicit Persistence Points</span></span>  
 <span data-ttu-id="25a78-117">Poniższa lista zawiera przykłady warunków, od których przepływu pracy jest trwały, gdy magazyn wystąpienia jest skojarzony z przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="25a78-117">The following list contains examples of the conditions upon which a workflow is persisted when an instance store is associated with a workflow.</span></span>  
  
-   <span data-ttu-id="25a78-118">Gdy **TransactionScope** zakończeniu działania lub **TransactedReceiveScope** ukończeniu działania.</span><span class="sxs-lookup"><span data-stu-id="25a78-118">When a **TransactionScope** activity completes or a **TransactedReceiveScope** activity completes.</span></span>  
  
-   <span data-ttu-id="25a78-119">Kiedy zostanie bezczynne wystąpienia przepływu pracy i **WorkflowIdleBehavior** jest ustawiony na hosta przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="25a78-119">When a workflow instance becomes idle and the **WorkflowIdleBehavior** is set on workflow host.</span></span> <span data-ttu-id="25a78-120">Dzieje się tak, na przykład, korzystając z komunikatów działania lub w **opóźnienie** działania.</span><span class="sxs-lookup"><span data-stu-id="25a78-120">This occurs, for example, when you use messaging activities or a **Delay** activity.</span></span>  
  
-   <span data-ttu-id="25a78-121">Gdy obiekt WorkflowApplication staje się bezczynności i **PersistableIdle** właściwości aplikacji ustawiono **PersistableIdleAction.Persist**.</span><span class="sxs-lookup"><span data-stu-id="25a78-121">When a WorkflowApplication becomes idle and the **PersistableIdle** property of the application is set to **PersistableIdleAction.Persist**.</span></span>  
  
-   <span data-ttu-id="25a78-122">Gdy aplikacja hosta jest instrukcją utrwalić lub zwolnić wystąpienia przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="25a78-122">When a host application is instructed to persist or unload a workflow instance.</span></span>  
  
-   <span data-ttu-id="25a78-123">Jeśli wystąpienia przepływu pracy zostało zakończone lub zakończeniu.</span><span class="sxs-lookup"><span data-stu-id="25a78-123">When a workflow instance is terminated or finishes.</span></span>  
  
-   <span data-ttu-id="25a78-124">Gdy **utrwalanie** wykonuje działania.</span><span class="sxs-lookup"><span data-stu-id="25a78-124">When a **Persist** activity executes.</span></span>  
  
-   <span data-ttu-id="25a78-125">Gdy wystąpienia przepływu pracy utworzony przy użyciu poprzedniej wersji programu Windows Workflow Foundation napotkał punkt trwałości podczas wykonywania interoperacyjne.</span><span class="sxs-lookup"><span data-stu-id="25a78-125">When an instance of a workflow developed using a previous version of Windows Workflow Foundation encounters a persistence point during interoperable execution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="25a78-126">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="25a78-126">In This Section</span></span>  
  
-   [<span data-ttu-id="25a78-127">Magazyn wystąpienia przepływu pracy SQL</span><span class="sxs-lookup"><span data-stu-id="25a78-127">SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="25a78-128">Wystąpienie magazynów</span><span class="sxs-lookup"><span data-stu-id="25a78-128">Instance Stores</span></span>](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [<span data-ttu-id="25a78-129">Uczestnicy trwałości</span><span class="sxs-lookup"><span data-stu-id="25a78-129">Persistence Participants</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [<span data-ttu-id="25a78-130">Najlepsze rozwiązania w zakresie trwałości</span><span class="sxs-lookup"><span data-stu-id="25a78-130">Persistence Best Practices</span></span>](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [<span data-ttu-id="25a78-131">Wystąpienia-utrwalony przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="25a78-131">Non-Persisted Workflow Instances</span></span>](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [<span data-ttu-id="25a78-132">Wstrzymywanie i wznawianie przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="25a78-132">Pausing and Resuming a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)