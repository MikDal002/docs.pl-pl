---
title: Niestandardowe demultipleksowanie
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: "41"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d7c74648a249ec833f2b0fc8b8f5eea9247dc364
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="custom-demux"></a><span data-ttu-id="a0fa9-102">Niestandardowe demultipleksowanie</span><span class="sxs-lookup"><span data-stu-id="a0fa9-102">Custom Demux</span></span>
<span data-ttu-id="a0fa9-103">W przykładzie pokazano, jak nagłówki wiadomości usługi MSMQ mogą być mapowane do operacji innej usługi, aby [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] usługi używające <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> nie są ograniczone do przy użyciu jednej operacji usługi, jak pokazano w [usługi kolejkowania komunikatów Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) i [Windows Communication Foundation, do usługi kolejkowania komunikatów](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) próbek.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-103">This sample demonstrates how MSMQ message headers can be mapped to different service operations so that [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services that use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> are not limited to using one service operation as demonstrated in the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) and [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) samples.</span></span>  
  
 <span data-ttu-id="a0fa9-104">Usługi w tym przykładzie jest aplikacji konsoli siebie umożliwiają przyjrzeć się, że usługa, która odbiera wiadomości w kolejce.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-104">The service in this sample is a self-hosted console application to enable you to observe the service that receives queued messages.</span></span>  
  
 <span data-ttu-id="a0fa9-105">Kontrakt usługi jest `IOrderProcessor`i definiuje usługę jednokierunkowe, które są odpowiednie do użycia w przypadku kolejek.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-105">The service contract is `IOrderProcessor`, and defines a one-way service that is suitable for use with queues.</span></span>  
  
```  
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```  
  
 <span data-ttu-id="a0fa9-106">Wiadomości MSMQ nie ma nagłówka Action.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-106">An MSMQ message does not have an Action header.</span></span> <span data-ttu-id="a0fa9-107">Nie jest możliwe do mapowania różnych wiadomości usługi MSMQ kontrakty operacji automatycznie.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-107">It is not possible to map different MSMQ messages to operation contracts automatically.</span></span> <span data-ttu-id="a0fa9-108">W związku z tym może istnieć tylko jeden kontrakt operacji.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-108">Therefore, there can be only one operation contract.</span></span> <span data-ttu-id="a0fa9-109">Aby obejść to ograniczenie implementuje usługi <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> metody <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-109">To overcome this limitation, the service implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method of the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface.</span></span> <span data-ttu-id="a0fa9-110"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> — Metoda włącza usługę zamapować określony nagłówek komunikatu z operacją określonej usługi.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-110">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> method enables the service to map a given header of the message to a particular service operation.</span></span> <span data-ttu-id="a0fa9-111">W tym przykładzie nagłówek Etykieta wiadomości jest mapowany do operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-111">In this sample, the message's label header is mapped to the service operations.</span></span> <span data-ttu-id="a0fa9-112">`Name` Parametr kontrakt operacji określa operacji usługi, które muszą być wysyłane etykiety podanym komunikatem.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-112">The `Name` parameter of the operation contract determines which service operation must be dispatched for a given message label.</span></span> <span data-ttu-id="a0fa9-113">Na przykład jeśli nagłówek Etykieta wiadomości zawiera "SubmitPurchaseOrder", "SubmitPurchaseOrder" usługi wywołaniu operacji.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-113">For example, if the message's label header contains "SubmitPurchaseOrder", the "SubmitPurchaseOrder" service operation is invoked.</span></span>  
  
```  
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```  
  
 <span data-ttu-id="a0fa9-114">Usługa musi implementować <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> metody <xref:System.ServiceModel.Description.IContractBehavior> interfejsu, jak pokazano w poniższym kodzie próbki.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-114">The service must implement the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> method of the <xref:System.ServiceModel.Description.IContractBehavior> interface as shown in the following sample code.</span></span> <span data-ttu-id="a0fa9-115">Dotyczy to niestandardowa `OperationSelector` do środowiska uruchomieniowego wysyłania framework usługi.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-115">This applies the custom `OperationSelector` to the service framework dispatch runtime.</span></span>  
  
```  
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```  
  
 <span data-ttu-id="a0fa9-116">Wiadomość musi przechodzić przez dyspozytora <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> przed przejściem do parametr OperationSelector.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-116">A message must pass through the dispatcher's <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> before getting to the OperationSelector.</span></span> <span data-ttu-id="a0fa9-117">Domyślnie komunikat zostanie odrzucony, jeżeli nie można odnaleźć swoje działania na żadną umową zaimplementowanych przez usługę.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-117">By default a message is rejected if its action cannot be found on any contract implemented by the service.</span></span> <span data-ttu-id="a0fa9-118">Aby uniknąć tego wyboru, wdrożymy <xref:System.ServiceModel.Description.IEndpointBehavior> o nazwie `MatchAllFilterBehavior`, dzięki czemu wszystkie wiadomości do przekazywania `ContractFilter` przez zastosowanie <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-118">To avoid this check, we implement an <xref:System.ServiceModel.Description.IEndpointBehavior> named `MatchAllFilterBehavior`, which allows any message to pass through the `ContractFilter` by applying the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> as follows.</span></span>  
  
```  
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```  
  
 <span data-ttu-id="a0fa9-119">Po odebraniu komunikatu przez usługę wywoływane jest operacja odpowiednią usługę, korzystając z informacji podanych w nagłówku etykiety.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-119">When a message is received by the service, the appropriate service operation is dispatched using the information provided by the label header.</span></span> <span data-ttu-id="a0fa9-120">Deserializacji treści komunikatu do `PurchaseOrder` obiektów, jak pokazano w poniższym kodzie próbki.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-120">The body of the message is deserialized into a `PurchaseOrder` object, as shown in the following sample code.</span></span>  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```  
  
 <span data-ttu-id="a0fa9-121">Usługa jest samodzielnie hostowana.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-121">The service is self-hosted.</span></span> <span data-ttu-id="a0fa9-122">Przy użyciu usługi MSMQ, kolejki, która jest używana musi zostać utworzona z wyprzedzeniem.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-122">When using the MSMQ, the queue that is used must be created in advance.</span></span> <span data-ttu-id="a0fa9-123">Można to zrobić ręcznie lub za pomocą kodu.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-123">This can be done manually or through code.</span></span> <span data-ttu-id="a0fa9-124">W tym przykładzie Usługa zawiera kod, aby sprawdzić obecność kolejki i tworzy go, jeśli kolejka nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-124">In this sample, the service contains code to check for the existence of the queue and creates it if the queue does not exist.</span></span> <span data-ttu-id="a0fa9-125">Nazwa kolejki jest do odczytu z pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-125">The queue name is read from the configuration file.</span></span>  
  
```  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```  
  
 <span data-ttu-id="a0fa9-126">Nazwa kolejki usługi MSMQ jest określona w sekcji appSettings pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-126">The MSMQ queue name is specified in an appSettings section of the configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0fa9-127">Nazwa kolejki używa pojedynczego znaku kropki (.) dla komputera lokalnego i separatory ukośnika w jego ścieżki.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-127">The queue name uses a dot (.) for the local computer and backslash separators in its path.</span></span> <span data-ttu-id="a0fa9-128">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Adres punktu końcowego określa schematu postać msmq.formatname i korzysta z hosta lokalnego na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-128">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint address specifies a msmq.formatname scheme, and uses localhost for the local computer.</span></span> <span data-ttu-id="a0fa9-129">Poniżej schemat jest adresem kolejki poprawnie sformatowana zgodnie z nazwy formatu MSMQ adresowania wytyczne.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-129">What follows the scheme is a properly formatted queue address according to the MSMQ Format name addressing guidelines.</span></span>  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  <span data-ttu-id="a0fa9-130">W tym przykładzie wymaga zainstalowania [usługi kolejkowania komunikatów](http://go.microsoft.com/fwlink/?LinkId=95143).</span><span class="sxs-lookup"><span data-stu-id="a0fa9-130">This sample requires the installation of [Message Queuing](http://go.microsoft.com/fwlink/?LinkId=95143).</span></span>  
  
 <span data-ttu-id="a0fa9-131">Uruchom usługę i uruchom klienta.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-131">Start the service and run the client.</span></span>  
  
 <span data-ttu-id="a0fa9-132">Następujące dane wyjściowe jest widoczna na kliencie.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-132">The following output is seen on the client.</span></span>  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="a0fa9-133">Następujące dane wyjściowe muszą być widoczne w usłudze.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-133">The following output must be seen on the service.</span></span>  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a0fa9-134">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="a0fa9-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a0fa9-135">Upewnij się, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a0fa9-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="a0fa9-136">Jeśli usługa jest uruchamiana pierwszy, sprawdza, upewnij się, że kolejka jest obecny.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-136">If the service is run first, it will check to ensure that the queue is present.</span></span> <span data-ttu-id="a0fa9-137">Jeśli kolejka nie jest obecny, będzie utworzyć usługę.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-137">If the queue is not present, the service will create one.</span></span> <span data-ttu-id="a0fa9-138">Można uruchomić usługi, aby najpierw utworzyć kolejkę, lub można go utworzyć za pomocą Menedżera kolejki usługi MSMQ.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-138">You can run the service first to create the queue, or you can create one via the MSMQ Queue Manager.</span></span> <span data-ttu-id="a0fa9-139">Wykonaj następujące kroki, aby utworzyć kolejkę w systemie Windows 2008.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-139">Follow these steps to create a queue in Windows 2008.</span></span>  
  
    1.  <span data-ttu-id="a0fa9-140">Otwórz Menedżera serwera w [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a0fa9-140">Open Server Manager in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
    2.  <span data-ttu-id="a0fa9-141">Rozwiń węzeł **funkcje** kartę.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-141">Expand the **Features** tab.</span></span>  
  
    3.  <span data-ttu-id="a0fa9-142">Kliknij prawym przyciskiem myszy **kolejki wiadomości prywatne**i wybierz **nowy**, **kolejki prywatnej**.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-142">Right-click **Private Message Queues**, and select **New**, **Private Queue**.</span></span>  
  
    4.  <span data-ttu-id="a0fa9-143">Sprawdź **transakcyjna** pole.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-143">Check the **Transactional** box.</span></span>  
  
    5.  <span data-ttu-id="a0fa9-144">Wprowadź `ServiceModelSamplesTransacted` jako nazwę nowej kolejki.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-144">Enter `ServiceModelSamplesTransacted` as the name of the new queue.</span></span>  
  
3.  <span data-ttu-id="a0fa9-145">Tworzenie wersji języka C# lub Visual Basic .NET rozwiązania, postępuj zgodnie z instrukcjami [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a0fa9-145">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="a0fa9-146">Aby uruchomić przykładowy w konfiguracji pojedynczej lub między komputerami, postępuj zgodnie z instrukcjami w [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a0fa9-146">To run the sample in a single- or cross- computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="a0fa9-147">Aby uruchomić przykład na komputerach</span><span class="sxs-lookup"><span data-stu-id="a0fa9-147">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="a0fa9-148">Skopiuj pliki programu usługi z folderu \service\bin\ w folderze danego języka na komputerze usługi.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-148">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service computer.</span></span>  
  
2.  <span data-ttu-id="a0fa9-149">Skopiuj pliki programu klienta z folderu \client\bin\ w folderze danego języka na komputerze klienckim.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-149">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
3.  <span data-ttu-id="a0fa9-150">W pliku Client.exe.config zmienić orderQueueName do określenia nazwy komputera usługi zamiast ".".</span><span class="sxs-lookup"><span data-stu-id="a0fa9-150">In the Client.exe.config file, change the orderQueueName to specify the service computer name instead of ".".</span></span>  
  
4.  <span data-ttu-id="a0fa9-151">Na komputerze, usługi uruchom Service.exe z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-151">On the service computer, launch Service.exe from a command prompt.</span></span>  
  
5.  <span data-ttu-id="a0fa9-152">Na komputerze klienckim należy uruchomić Client.exe z wiersza polecenia.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-152">On the client computer, launch Client.exe from a command prompt.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a0fa9-153">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a0fa9-154">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="a0fa9-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a0fa9-155">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a0fa9-156">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="a0fa9-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a><span data-ttu-id="a0fa9-157">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a0fa9-157">See Also</span></span>  
 [<span data-ttu-id="a0fa9-158">Usługi kolejkowania wiadomości w programie WCF</span><span class="sxs-lookup"><span data-stu-id="a0fa9-158">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [<span data-ttu-id="a0fa9-159">Usługi kolejkowania komunikatów</span><span class="sxs-lookup"><span data-stu-id="a0fa9-159">Message Queuing</span></span>](http://go.microsoft.com/fwlink/?LinkId=95143)