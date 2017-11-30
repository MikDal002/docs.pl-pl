---
title: 108 - CustomTrackingRecordInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5bee501e-4e00-42cd-b949-e88009c3d4e8
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fbbae172ea5030b44656dfe850cddfd498764fed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="108---customtrackingrecordinfo"></a><span data-ttu-id="76b99-102">108 - CustomTrackingRecordInfo</span><span class="sxs-lookup"><span data-stu-id="76b99-102">108 - CustomTrackingRecordInfo</span></span>
## <a name="properties"></a><span data-ttu-id="76b99-103">Właściwości</span><span class="sxs-lookup"><span data-stu-id="76b99-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76b99-104">Identyfikator</span><span class="sxs-lookup"><span data-stu-id="76b99-104">Id</span></span>|<span data-ttu-id="76b99-105">108</span><span class="sxs-lookup"><span data-stu-id="76b99-105">108</span></span>|  
|<span data-ttu-id="76b99-106">Słowa kluczowe</span><span class="sxs-lookup"><span data-stu-id="76b99-106">Keywords</span></span>|<span data-ttu-id="76b99-107">UserEvents EndToEndMonitoring, rozwiązywania problemów, HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="76b99-107">UserEvents, EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="76b99-108">Poziom</span><span class="sxs-lookup"><span data-stu-id="76b99-108">Level</span></span>|<span data-ttu-id="76b99-109">Informacje</span><span class="sxs-lookup"><span data-stu-id="76b99-109">Information</span></span>|  
|<span data-ttu-id="76b99-110">Kanał</span><span class="sxs-lookup"><span data-stu-id="76b99-110">Channel</span></span>|<span data-ttu-id="76b99-111">Microsoft-Windows aplikacji Server aplikacje/analityczne</span><span class="sxs-lookup"><span data-stu-id="76b99-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76b99-112">Opis</span><span class="sxs-lookup"><span data-stu-id="76b99-112">Description</span></span>  
 <span data-ttu-id="76b99-113">To zdarzenie jest emitowane przez uczestnika śledzenia zdarzeń systemu Windows podczas działania w ramach wystąpienia przepływu pracy emituje CustomTrackingRecord z poziomu Info.</span><span class="sxs-lookup"><span data-stu-id="76b99-113">This event is emitted by the ETW tracking participant when a activity within a workflow instance emits CustomTrackingRecord with level Info.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76b99-114">Komunikat</span><span class="sxs-lookup"><span data-stu-id="76b99-114">Message</span></span>  
 <span data-ttu-id="76b99-115">TrackRecord = CustomTrackingRecord, identyfikator wystąpienia = %1, RecordNumber = %2, EventTime = %3, nazwa = %4, ActivityName = %5, identyfikator = %6, ActivityInstanceId = %7 ActivityTypeName = %8, dane = %9 adnotacje = % 10 ProfileName = % 11</span><span class="sxs-lookup"><span data-stu-id="76b99-115">TrackRecord = CustomTrackingRecord, InstanceID = %1, RecordNumber=%2, EventTime=%3,  Name=%4, ActivityName=%5, ActivityId=%6, ActivityInstanceId=%7, ActivityTypeName=%8, Data=%9, Annotations=%10, ProfileName = %11</span></span>  
  
## <a name="details"></a><span data-ttu-id="76b99-116">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="76b99-116">Details</span></span>  
  
|<span data-ttu-id="76b99-117">Nazwa elementu danych</span><span class="sxs-lookup"><span data-stu-id="76b99-117">Data Item Name</span></span>|<span data-ttu-id="76b99-118">Typ elementu danych</span><span class="sxs-lookup"><span data-stu-id="76b99-118">Data Item Type</span></span>|<span data-ttu-id="76b99-119">Opis</span><span class="sxs-lookup"><span data-stu-id="76b99-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76b99-120">Identyfikator wystąpienia</span><span class="sxs-lookup"><span data-stu-id="76b99-120">InstanceId</span></span>|<span data-ttu-id="76b99-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="76b99-121">xs:GUID</span></span>|<span data-ttu-id="76b99-122">Identyfikator wystąpienia przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="76b99-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="76b99-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="76b99-123">RecordNumber</span></span>|<span data-ttu-id="76b99-124">xs:Long</span><span class="sxs-lookup"><span data-stu-id="76b99-124">xs:long</span></span>|<span data-ttu-id="76b99-125">Numer sekwencyjny emitowany rekordu</span><span class="sxs-lookup"><span data-stu-id="76b99-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="76b99-126">eventTime</span><span class="sxs-lookup"><span data-stu-id="76b99-126">EventTime</span></span>|<span data-ttu-id="76b99-127">xs: DateTime</span><span class="sxs-lookup"><span data-stu-id="76b99-127">xs:dateTime</span></span>|<span data-ttu-id="76b99-128">Godzina w formacie UTC podczas zdarzenia zostały wyemitowane</span><span class="sxs-lookup"><span data-stu-id="76b99-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="76b99-129">Nazwa</span><span class="sxs-lookup"><span data-stu-id="76b99-129">Name</span></span>|<span data-ttu-id="76b99-130">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-130">xs:string</span></span>|<span data-ttu-id="76b99-131">Nazwa CustomTrackingRecord</span><span class="sxs-lookup"><span data-stu-id="76b99-131">The name of the CustomTrackingRecord</span></span>|  
|<span data-ttu-id="76b99-132">activityName</span><span class="sxs-lookup"><span data-stu-id="76b99-132">ActivityName</span></span>|<span data-ttu-id="76b99-133">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-133">xs:string</span></span>|<span data-ttu-id="76b99-134">Nazwa działania, które są emitowane CustomTrackingRecord</span><span class="sxs-lookup"><span data-stu-id="76b99-134">The name of the activity that emitted the CustomTrackingRecord</span></span>|  
|<span data-ttu-id="76b99-135">Identyfikator działania</span><span class="sxs-lookup"><span data-stu-id="76b99-135">ActivityId</span></span>|<span data-ttu-id="76b99-136">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-136">xs:string</span></span>|<span data-ttu-id="76b99-137">Identyfikator działania, które są emitowane CustomTrackingRecord</span><span class="sxs-lookup"><span data-stu-id="76b99-137">The id of the activity that emitted the CustomTrackingRecord</span></span>|  
|<span data-ttu-id="76b99-138">ActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="76b99-138">ActivityInstanceId</span></span>|<span data-ttu-id="76b99-139">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-139">xs:string</span></span>|<span data-ttu-id="76b99-140">Identyfikator wystąpienia działania wysyłanego CustomTrackingRecord</span><span class="sxs-lookup"><span data-stu-id="76b99-140">The instance id of the activity that emitted the CustomTrackingRecord</span></span>|  
|<span data-ttu-id="76b99-141">ActivityTypeName</span><span class="sxs-lookup"><span data-stu-id="76b99-141">ActivityTypeName</span></span>|<span data-ttu-id="76b99-142">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-142">xs:string</span></span>|<span data-ttu-id="76b99-143">Nazwa działania, które są emitowane CustomTrackingRecord</span><span class="sxs-lookup"><span data-stu-id="76b99-143">The name of the activity that emitted the CustomTrackingRecord</span></span>|  
|<span data-ttu-id="76b99-144">Dane</span><span class="sxs-lookup"><span data-stu-id="76b99-144">Data</span></span>|<span data-ttu-id="76b99-145">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-145">xs:string</span></span>|<span data-ttu-id="76b99-146">Dane, które zostało śledzone z tym zdarzeniem.</span><span class="sxs-lookup"><span data-stu-id="76b99-146">The data that was tracked with this event.</span></span>  <span data-ttu-id="76b99-147">Wartości są przechowywane w elemencie xml w formacie \<elementy >\< nazwa elementu = "dataName" type="System.String" > wartości danych\</elementu > \< /elementy >.</span><span class="sxs-lookup"><span data-stu-id="76b99-147">The values are stored in an xml element in the format \<items>\< item  name = "dataName" type="System.String">dataValue\</item>\</items>.</span></span>  <span data-ttu-id="76b99-148">Jeśli został śledzone żadne dane, a następnie ciąg zawiera \<elementów / >.</span><span class="sxs-lookup"><span data-stu-id="76b99-148">If no data was tracked then the string contains \<items/>.</span></span> <span data-ttu-id="76b99-149">Rozmiar zdarzenia ETW jest ograniczona przez rozmiar bufora ETW lub max ładunku zdarzenia ETW.</span><span class="sxs-lookup"><span data-stu-id="76b99-149">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="76b99-150">Jeśli limity ETW przekracza rozmiar zdarzenia, a następnie zdarzenia został obcięty przez usunięcie adnotacje i zastąpienie wartości danych z \<elementy >...  \< /elementy >.</span><span class="sxs-lookup"><span data-stu-id="76b99-150">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the data value with \<items>...\</items>.</span></span>  <span data-ttu-id="76b99-151">Następujące typy są przechowywane jako wartości zwracane przez ToString(); String,char,bool,int,short,Long,uint,ushort,ulong,system.Single,float,Double,system.GUID,system.DateTimeOffset,system.DateTime.</span><span class="sxs-lookup"><span data-stu-id="76b99-151">The following types are stored as their value as returned by ToString(); string,char,bool,int,short,long,uint,ushort,ulong,System.Single,float,double,System.Guid,System.DateTimeOffset,System.DateTime.</span></span>  <span data-ttu-id="76b99-152">Wszystkie inne typy są serializowane, przy użyciu System.Runtime.Serialization.NetDataContractSerializer.</span><span class="sxs-lookup"><span data-stu-id="76b99-152">All other types are serialized using System.Runtime.Serialization.NetDataContractSerializer.</span></span>|  
|<span data-ttu-id="76b99-153">Adnotacje</span><span class="sxs-lookup"><span data-stu-id="76b99-153">Annotations</span></span>|<span data-ttu-id="76b99-154">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-154">xs:string</span></span>|<span data-ttu-id="76b99-155">Adnotacje, które zostały dodane do tego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="76b99-155">The annotations that were added to this event.</span></span>  <span data-ttu-id="76b99-156">Wartości są przechowywane w elemencie xml w formacie \<elementy >\< nazwa elementu = "annotationName" type="System.String" > annotationValue\</elementu > \< /elementy >.</span><span class="sxs-lookup"><span data-stu-id="76b99-156">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="76b99-157">Jeśli nie określono bez adnotacji, a następnie ciąg zawiera \<elementów / >.</span><span class="sxs-lookup"><span data-stu-id="76b99-157">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="76b99-158">Rozmiar zdarzenia ETW jest ograniczona przez rozmiar bufora ETW lub max ładunku zdarzenia ETW.</span><span class="sxs-lookup"><span data-stu-id="76b99-158">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="76b99-159">Jeśli limity ETW przekracza rozmiar zdarzenia, a następnie zdarzenia został obcięty przez usunięcie adnotacje i zastąpienie wartości adnotacji z \<elementy >...  \< /elementy >.</span><span class="sxs-lookup"><span data-stu-id="76b99-159">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="76b99-160">ProfileName</span><span class="sxs-lookup"><span data-stu-id="76b99-160">ProfileName</span></span>|<span data-ttu-id="76b99-161">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-161">xs:string</span></span>|<span data-ttu-id="76b99-162">Nazwa lub profilu śledzenia, które spowodowały to zdarzenie jest emitowany</span><span class="sxs-lookup"><span data-stu-id="76b99-162">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="76b99-163">HostReference</span><span class="sxs-lookup"><span data-stu-id="76b99-163">HostReference</span></span>|<span data-ttu-id="76b99-164">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-164">xs:string</span></span>|<span data-ttu-id="76b99-165">Dla usług sieci web hostowanych w tym polu unikatowo identyfikuje usługę w hierarchii sieci web.</span><span class="sxs-lookup"><span data-stu-id="76b99-165">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="76b99-166">Jego format jest zdefiniowany jako "Ścieżka wirtualna aplikacji Nazwa witryny sieci Web &#124; Ścieżka wirtualna usługi &#124; ServiceName "przykład:" Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService "</span><span class="sxs-lookup"><span data-stu-id="76b99-166">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="76b99-167">Domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="76b99-167">AppDomain</span></span>|<span data-ttu-id="76b99-168">xs:String</span><span class="sxs-lookup"><span data-stu-id="76b99-168">xs:string</span></span>|<span data-ttu-id="76b99-169">Długość ciągu zwróconego przez AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="76b99-169">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|