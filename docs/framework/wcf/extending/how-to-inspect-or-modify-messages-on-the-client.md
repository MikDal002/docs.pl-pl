---
title: "Instrukcje: Inspekcja lub modyfikowanie komunikatów na kliencie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 164e19891e576b6d310839a1221ad8ed0d315444
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a><span data-ttu-id="d3681-102">Instrukcje: Inspekcja lub modyfikowanie komunikatów na kliencie</span><span class="sxs-lookup"><span data-stu-id="d3681-102">How to: Inspect or Modify Messages on the Client</span></span>
<span data-ttu-id="d3681-103">Można inspekcja lub modyfikowanie komunikatów przychodzących lub wychodzących między [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta zaimplementowanie <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> oraz wstawieniu ich do środowiska uruchomieniowego klienta.</span><span class="sxs-lookup"><span data-stu-id="d3681-103">You can inspect or modify the incoming or outgoing messages across a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client by implementing a <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> and inserting it into the client runtime.</span></span> <span data-ttu-id="d3681-104">Aby uzyskać więcej informacji, zobacz [rozszerzanie klientów](../../../../docs/framework/wcf/extending/extending-clients.md).</span><span class="sxs-lookup"><span data-stu-id="d3681-104">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md).</span></span> <span data-ttu-id="d3681-105">Jest równoważna funkcji w usłudze <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d3681-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d3681-106">Pełny przykład kodu dla [Messageinspector](../../../../docs/framework/wcf/samples/message-inspectors.md) próbki.</span><span class="sxs-lookup"><span data-stu-id="d3681-106">For a complete code example see the [Message Inspectors](../../../../docs/framework/wcf/samples/message-inspectors.md) sample.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="d3681-107">Aby inspekcja lub modyfikowanie komunikatów</span><span class="sxs-lookup"><span data-stu-id="d3681-107">To inspect or modify messages</span></span>  
  
1.  <span data-ttu-id="d3681-108">Implementowanie <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="d3681-108">Implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2.  <span data-ttu-id="d3681-109">Implementowanie <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> lub <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> w zależności od zakresu, jaką chcesz wstawić inspektora komunikat klienta.</span><span class="sxs-lookup"><span data-stu-id="d3681-109">Implement a <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> depending upon the scope at which you want to insert the client message inspector.</span></span> <span data-ttu-id="d3681-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>Umożliwia zmianę zachowania na poziomie punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="d3681-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> allows you to change behavior at the endpoint level.</span></span> <span data-ttu-id="d3681-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>Umożliwia zmianę zachowania na poziomie kontraktu.</span><span class="sxs-lookup"><span data-stu-id="d3681-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> allows you to change behavior at the contract level.</span></span>  
  
3.  <span data-ttu-id="d3681-112">Wstaw działanie przed wywołaniem <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> lub <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> metoda <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d3681-112">Insert the behavior prior to calling the <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d3681-113">Aby uzyskać więcej informacji, zobacz [Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="d3681-113">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3681-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="d3681-114">Example</span></span>  
 <span data-ttu-id="d3681-115">W poniższych przykładach kodu pokazano, w kolejności:</span><span class="sxs-lookup"><span data-stu-id="d3681-115">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="d3681-116">Implementacja inspektora klienta.</span><span class="sxs-lookup"><span data-stu-id="d3681-116">A client inspector implementation.</span></span>  
  
-   <span data-ttu-id="d3681-117">Zachowanie punktu końcowego, która wstawia Inspektor.</span><span class="sxs-lookup"><span data-stu-id="d3681-117">An endpoint behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="d3681-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>-klasy, która pozwala na dodanie zachowania w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="d3681-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- derived class that allows you to add the behavior in a configuration file.</span></span>  
  
-   <span data-ttu-id="d3681-119">Plik konfiguracji, który dodaje zachowanie punktu końcowego, która wstawia inspektora komunikat klienta do środowiska uruchomieniowego klienta.</span><span class="sxs-lookup"><span data-stu-id="d3681-119">A configuration file that adds the endpoint behavior which inserts the client message inspector into the client runtime.</span></span>  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client   
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they   
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element   
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
```  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"   
                      binding="wsHttpBinding"  
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3681-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3681-120">See Also</span></span>  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>  
 [<span data-ttu-id="d3681-121">Konfigurowanie i rozszerzanie środowiska uruchomieniowego za pomocą zachowań</span><span class="sxs-lookup"><span data-stu-id="d3681-121">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)