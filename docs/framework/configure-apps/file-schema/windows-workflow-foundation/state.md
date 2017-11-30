---
title: '&lt;Stan&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca170740fbe55547c9897054f9c4782c2d25afdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt"></a><span data-ttu-id="e7f48-102">&lt;Stan&gt;</span><span class="sxs-lookup"><span data-stu-id="e7f48-102">&lt;state&gt;</span></span>
<span data-ttu-id="e7f48-103">Reprezentuje kolekcję subskrybowanego stanów z wystąpienia śledzonych przepływu pracy podczas tworzenia rekordów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="e7f48-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="e7f48-104">Aby uzyskać więcej informacji na zapytania dotyczące profilu śledzenia, zobacz [profile śledzenia](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e7f48-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e7f48-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e7f48-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e7f48-106">\<Śledzenie ></span><span class="sxs-lookup"><span data-stu-id="e7f48-106">\<tracking></span></span>  
<span data-ttu-id="e7f48-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e7f48-107">\<trackingProfile></span></span>  
<span data-ttu-id="e7f48-108">\<przepływ pracy ></span><span class="sxs-lookup"><span data-stu-id="e7f48-108">\<workflow></span></span>  
<span data-ttu-id="e7f48-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="e7f48-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="e7f48-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="e7f48-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="e7f48-111">\<Stany ></span><span class="sxs-lookup"><span data-stu-id="e7f48-111">\<states></span></span>  
<span data-ttu-id="e7f48-112">\<Stan ></span><span class="sxs-lookup"><span data-stu-id="e7f48-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f48-113">Składnia</span><span class="sxs-lookup"><span data-stu-id="e7f48-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7f48-114">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="e7f48-114">Attributes and Elements</span></span>  
 <span data-ttu-id="e7f48-115">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="e7f48-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7f48-116">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="e7f48-116">Attributes</span></span>  
  
|<span data-ttu-id="e7f48-117">Atrybut</span><span class="sxs-lookup"><span data-stu-id="e7f48-117">Attribute</span></span>|<span data-ttu-id="e7f48-118">Opis</span><span class="sxs-lookup"><span data-stu-id="e7f48-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e7f48-119">nazwa</span><span class="sxs-lookup"><span data-stu-id="e7f48-119">name</span></span>|<span data-ttu-id="e7f48-120">Ciąg, który określa subskrybowanego stanu z wystąpienia śledzonych przepływu pracy podczas rekordem śledzenia.</span><span class="sxs-lookup"><span data-stu-id="e7f48-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e7f48-121">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="e7f48-121">Child Elements</span></span>  
 <span data-ttu-id="e7f48-122">Brak.</span><span class="sxs-lookup"><span data-stu-id="e7f48-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e7f48-123">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="e7f48-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e7f48-124">Element</span><span class="sxs-lookup"><span data-stu-id="e7f48-124">Element</span></span>|<span data-ttu-id="e7f48-125">Opis</span><span class="sxs-lookup"><span data-stu-id="e7f48-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7f48-126">\<Stany ></span><span class="sxs-lookup"><span data-stu-id="e7f48-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="e7f48-127">Kolekcja subskrybowanego stanów z wystąpienia elementu śledzonych przepływu pracy podczas tworzenia rekordów śledzenia.</span><span class="sxs-lookup"><span data-stu-id="e7f48-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7f48-128">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e7f48-128">Remarks</span></span>  
 <span data-ttu-id="e7f48-129">Zwracane rekordy są filtrowane według stanów w tej kolekcji.</span><span class="sxs-lookup"><span data-stu-id="e7f48-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="e7f48-130">Stan możliwe wartości są opisane w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="e7f48-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="e7f48-131">Stan</span><span class="sxs-lookup"><span data-stu-id="e7f48-131">State</span></span>|<span data-ttu-id="e7f48-132">Opis</span><span class="sxs-lookup"><span data-stu-id="e7f48-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e7f48-133">Zostało przerwane</span><span class="sxs-lookup"><span data-stu-id="e7f48-133">Aborted</span></span>|<span data-ttu-id="e7f48-134">Wystąpienie przepływu pracy zostało przerwane.</span><span class="sxs-lookup"><span data-stu-id="e7f48-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="e7f48-135">Zakończone</span><span class="sxs-lookup"><span data-stu-id="e7f48-135">Completed</span></span>|<span data-ttu-id="e7f48-136">Wystąpienie przepływu pracy jest zakończone.</span><span class="sxs-lookup"><span data-stu-id="e7f48-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="e7f48-137">Usunięte</span><span class="sxs-lookup"><span data-stu-id="e7f48-137">Deleted</span></span>|<span data-ttu-id="e7f48-138">Wystąpienie przepływu pracy, został usunięty.</span><span class="sxs-lookup"><span data-stu-id="e7f48-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="e7f48-139">Bezczynności (%)</span><span class="sxs-lookup"><span data-stu-id="e7f48-139">Idle</span></span>|<span data-ttu-id="e7f48-140">Wystąpienie przepływu pracy jest bezczynny.</span><span class="sxs-lookup"><span data-stu-id="e7f48-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="e7f48-141">Trwały</span><span class="sxs-lookup"><span data-stu-id="e7f48-141">Persisted</span></span>|<span data-ttu-id="e7f48-142">Wystąpienie przepływu pracy jest trwały.</span><span class="sxs-lookup"><span data-stu-id="e7f48-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="e7f48-143">Wznowione</span><span class="sxs-lookup"><span data-stu-id="e7f48-143">Resumed</span></span>|<span data-ttu-id="e7f48-144">Wystąpienie przepływu pracy zostanie wznowione.</span><span class="sxs-lookup"><span data-stu-id="e7f48-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="e7f48-145">Rozpoczęto</span><span class="sxs-lookup"><span data-stu-id="e7f48-145">Started</span></span>|<span data-ttu-id="e7f48-146">Wystąpienie przepływu pracy zostało rozpoczęte.</span><span class="sxs-lookup"><span data-stu-id="e7f48-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="e7f48-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="e7f48-147">UnhandledException</span></span>|<span data-ttu-id="e7f48-148">Wystąpienie przepływu pracy napotkał nieobsługiwany wyjątek.</span><span class="sxs-lookup"><span data-stu-id="e7f48-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="e7f48-149">Zwolniono</span><span class="sxs-lookup"><span data-stu-id="e7f48-149">Unloaded</span></span>|<span data-ttu-id="e7f48-150">Wystąpienie przepływu pracy nie jest załadowany.</span><span class="sxs-lookup"><span data-stu-id="e7f48-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="e7f48-151">Anulowane</span><span class="sxs-lookup"><span data-stu-id="e7f48-151">Canceled</span></span>|<span data-ttu-id="e7f48-152">Wystąpienie przepływu pracy zostało anulowane.</span><span class="sxs-lookup"><span data-stu-id="e7f48-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="e7f48-153">Wstrzymane</span><span class="sxs-lookup"><span data-stu-id="e7f48-153">Suspended</span></span>|<span data-ttu-id="e7f48-154">Wystąpienie przepływu pracy jest zawieszone.</span><span class="sxs-lookup"><span data-stu-id="e7f48-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="e7f48-155">Zakończone</span><span class="sxs-lookup"><span data-stu-id="e7f48-155">Terminated</span></span>|<span data-ttu-id="e7f48-156">Wystąpienie przepływu pracy jest zakończone.</span><span class="sxs-lookup"><span data-stu-id="e7f48-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="e7f48-157">Anulowano</span><span class="sxs-lookup"><span data-stu-id="e7f48-157">Unsuspended</span></span>|<span data-ttu-id="e7f48-158">Anulowano to wystąpienie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="e7f48-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e7f48-159">Przykład</span><span class="sxs-lookup"><span data-stu-id="e7f48-159">Example</span></span>  
 <span data-ttu-id="e7f48-160">Następująca konfiguracja subskrybuje przepływu rekordów dla śledzenia na poziomie wystąpienia `Started` stan wystąpienia przy użyciu tego zapytania.</span><span class="sxs-lookup"><span data-stu-id="e7f48-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7f48-161">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e7f48-161">See Also</span></span>  
 <span data-ttu-id="e7f48-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e7f48-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="e7f48-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e7f48-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="e7f48-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e7f48-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>      
 [<span data-ttu-id="e7f48-165">Przepływ pracy, kontrola i śledzenie</span><span class="sxs-lookup"><span data-stu-id="e7f48-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e7f48-166">Profile śledzenia</span><span class="sxs-lookup"><span data-stu-id="e7f48-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)