---
title: "Instrukcje: Konfigurowanie zachowania bezczynności za pomocą elementu WorkflowServiceHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04ab5e657ffae42e9e52a7f392070a7d6ecf680c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="7c1ef-102">Instrukcje: Konfigurowanie zachowania bezczynności za pomocą elementu WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="7c1ef-102">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="7c1ef-103">Przepływy pracy Przejdź bezczynności, po napotkaniu zakładki, która musi zostać wznowiony przez niektóre bodźca zewnętrznych, np. gdy wystąpienie przepływu pracy oczekuje na być dostarczane za pomocą wiadomości <xref:System.ServiceModel.Activities.Receive> działania.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-103">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="7c1ef-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>jest to zachowanie, który umożliwia określenie czasu między po wystąpieniu usługi przechodzi bezczynności i gdy wystąpienie jest utrwalona lub zwalnianie modułu.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="7c1ef-105">Zawiera dwie właściwości, które umożliwiają skonfigurowanie tych okresów.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-105">It contains two properties that enable you to set these time spans.</span></span> <span data-ttu-id="7c1ef-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A>Określa przedział czasu między po bezczynności przechodzi wystąpienia usługi przepływu pracy i gdy wystąpienie usługi przepływu pracy jest trwały.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="7c1ef-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>Określa przedział czasu między gdy przepływ pracy usługi wystąpienie przechodzi bezczynności i gdy wystąpienie usługi przepływu pracy jest zwolniony, gdzie zwolnienie oznacza przechowywanie wystąpienie w magazynie wystąpień i usunięcie go z pamięci.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="7c1ef-108">W tym temacie opisano sposób konfigurowania <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-108">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="7c1ef-109">Aby skonfigurować WorkflowIdleBehavior</span><span class="sxs-lookup"><span data-stu-id="7c1ef-109">To configure WorkflowIdleBehavior</span></span>  
  
1.  <span data-ttu-id="7c1ef-110">Dodaj <`workflowIdle`> elementu <`behavior`> w elemencie <`serviceBehaviors`> element, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-110">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="7c1ef-111">`timeToUnload` Atrybut określa okres czasu między po bezczynności przechodzi wystąpienia usługi przepływu pracy i kiedy zwolniony jest usługi przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-111">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="7c1ef-112">`timeToPersist` Atrybut określa okres czasu między po bezczynności przechodzi wystąpienia usługi przepływu pracy i gdy wystąpienie usługi przepływu pracy jest trwały.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-112">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="7c1ef-113">Wartość domyślna dla `timeToUnload` to 1 minuta.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-113">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="7c1ef-114">Wartość domyślna dla `timeToPersist` jest <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-114">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="7c1ef-115">Jeśli chcesz zachować bezczynne wystąpienia w pamięci, ale zachowywał je dla niezawodności, ustaw wartości, aby `timeToPersist`  <  `timeToUnload`.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-115">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="7c1ef-116">Aby zapobiec zwalnianie bezczynne wystąpienia, należy ustawić `timeToUnload` do <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-116">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="7c1ef-117"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, zobacz [rozszerzalność hosta usługi przepływu pracy](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="7c1ef-117"> <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c1ef-118">Uproszczona konfiguracja używa powyższego przykładu konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-118">The preceding configuration sample is using simplified configuration.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7c1ef-119">[Uproszczony konfiguracji](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7c1ef-119"> [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="7c1ef-120">Aby zmienić zachowanie bezczynności w kodzie</span><span class="sxs-lookup"><span data-stu-id="7c1ef-120">To change idle behavior in code</span></span>  
  
-   <span data-ttu-id="7c1ef-121">Poniższy przykład umożliwia zmianę czasu oczekiwania przed wprowadzeniem trwałych i zwalnianie programowo.</span><span class="sxs-lookup"><span data-stu-id="7c1ef-121">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7c1ef-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7c1ef-122">See Also</span></span>  
 [<span data-ttu-id="7c1ef-123">Rozszerzalność hosta usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7c1ef-123">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="7c1ef-124">Uproszczona konfiguracja</span><span class="sxs-lookup"><span data-stu-id="7c1ef-124">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="7c1ef-125">Usługi przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="7c1ef-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)