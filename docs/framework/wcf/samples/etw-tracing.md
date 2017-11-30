---
title: "Śledzenie za pomocą funkcji ETW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
caps.latest.revision: "42"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d45852a8e03ac63ea6412e6f5b176f06fe83eb03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2017
---
# <a name="etw-tracing"></a><span data-ttu-id="396ad-102">Śledzenie za pomocą funkcji ETW</span><span class="sxs-lookup"><span data-stu-id="396ad-102">ETW Tracing</span></span>
<span data-ttu-id="396ad-103">W tym przykładzie pokazano, jak wdrożyć śledzenia End-to-End (E2E) przy użyciu zdarzenia śledzenia dla systemu Windows (ETW) i `ETWTraceListener` dostarczanym z tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="396ad-103">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="396ad-104">Próbki jest oparta na [wprowadzenie](../../../../docs/framework/wcf/samples/getting-started-sample.md) i obejmuje śledzenia zdarzeń systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="396ad-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="396ad-105">Procedury i kompilacji instrukcje dotyczące konfiguracji dla tego przykładu znajdują się na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="396ad-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="396ad-106">W tym przykładzie przyjęto założenie, że czytelnik zna [śledzenie i rejestrowanie komunikatów](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="396ad-106">This sample assumes that you are familiar with [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="396ad-107">Każde źródło śledzenia w <xref:System.Diagnostics> śledzenie model może mieć wiele obiektów nasłuchujących śledzenia, które określają, jak i gdzie dane są śledzone.</span><span class="sxs-lookup"><span data-stu-id="396ad-107">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="396ad-108">Typ odbiornika definiuje format, w którym rejestrowane są dane śledzenia.</span><span class="sxs-lookup"><span data-stu-id="396ad-108">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="396ad-109">Poniższy przykładowy kod przedstawia sposób Dodaj do konfiguracji odbiornika.</span><span class="sxs-lookup"><span data-stu-id="396ad-109">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="396ad-110">Przed użyciem tego odbiornika, można uruchomić sesję śledzenia funkcji ETW.</span><span class="sxs-lookup"><span data-stu-id="396ad-110">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="396ad-111">Za pomocą Logman.exe lub Tracelog.exe można uruchomić tej sesji.</span><span class="sxs-lookup"><span data-stu-id="396ad-111">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="396ad-112">Plik SetupETW.bat jest uwzględniona w tym przykładzie, dzięki czemu możesz skonfigurować sesję śledzenia funkcji ETW wraz z plikiem CleanupETW.bat zamykania sesji i uzupełniania w pliku dziennika.</span><span class="sxs-lookup"><span data-stu-id="396ad-112">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="396ad-113">Procedury i kompilacji instrukcje dotyczące instalacji dla tego przykładu znajdują się na końcu tego tematu.</span><span class="sxs-lookup"><span data-stu-id="396ad-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="396ad-114">Aby uzyskać więcej informacji na temat tych narzędzi, zobacz [http://go.microsoft.com/fwlink/?LinkId=56580](http://go.microsoft.com/fwlink/?LinkId=56580)</span><span class="sxs-lookup"><span data-stu-id="396ad-114">For more information about these tools, see [http://go.microsoft.com/fwlink/?LinkId=56580](http://go.microsoft.com/fwlink/?LinkId=56580)</span></span>  
  
 <span data-ttu-id="396ad-115">Używając ETWTraceListener, dane śledzenia są rejestrowane w plikach binarnych ETL.</span><span class="sxs-lookup"><span data-stu-id="396ad-115">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="396ad-116">Z włączonym śledzeniem ServiceModel jest włączona, wszystkie ślady generowane są wyświetlane w tym samym pliku.</span><span class="sxs-lookup"><span data-stu-id="396ad-116">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="396ad-117">Użyj [narzędzia podglądu śledzenia usług (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) dotyczące wyświetlania plików dziennika ETL i .svclog.</span><span class="sxs-lookup"><span data-stu-id="396ad-117">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="396ad-118">Podgląd komunikatów o tworzy widok end-to-end systemu, dzięki któremu można wyśledzić komunikatu od źródła do miejsca docelowego i punktem zużycia.</span><span class="sxs-lookup"><span data-stu-id="396ad-118">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="396ad-119">Odbiornik śledzenia zdarzeń systemu Windows obsługuje logowanie cykliczne.</span><span class="sxs-lookup"><span data-stu-id="396ad-119">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="396ad-120">Aby włączyć tę funkcję, przejdź do **Start**, **Uruchom** i typ `cmd` można uruchomić konsoli poleceń.</span><span class="sxs-lookup"><span data-stu-id="396ad-120">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="396ad-121">W poniższym poleceniu zastąp `<logfilename>` parametr o nazwie pliku dziennika.</span><span class="sxs-lookup"><span data-stu-id="396ad-121">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="396ad-122">`-f` i `-max` przełączniki są opcjonalne.</span><span class="sxs-lookup"><span data-stu-id="396ad-122">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="396ad-123">Określa format binarny cykliczne i dziennika maksymalny rozmiar 1000MB odpowiednio.</span><span class="sxs-lookup"><span data-stu-id="396ad-123">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="396ad-124">`-p` Przełącznik jest używany do określenia dostawcy śledzenia.</span><span class="sxs-lookup"><span data-stu-id="396ad-124">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="396ad-125">W naszym przykładzie `"{411a0819-c24b-428c-83e2-26b41091702e}"` oznacza identyfikator GUID "Dostawcy próbki ETW XML".</span><span class="sxs-lookup"><span data-stu-id="396ad-125">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="396ad-126">Aby rozpocząć sesję, wpisz następujące polecenie.</span><span class="sxs-lookup"><span data-stu-id="396ad-126">To start the session, type in the following command.</span></span>  
  
```  
Logman start Wcf  
```  
  
 <span data-ttu-id="396ad-127">Po zakończeniu rejestrowania, można zatrzymać sesji przy użyciu następującego polecenia.</span><span class="sxs-lookup"><span data-stu-id="396ad-127">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```  
Logman stop Wcf  
```  
  
 <span data-ttu-id="396ad-128">Ten proces generuje dzienniki cyklicznych binarne, przetwarzające z narzędziem wyboru, w tym [narzędzia podglądu śledzenia usług (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) lub Tracerpt.</span><span class="sxs-lookup"><span data-stu-id="396ad-128">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="396ad-129">Można również przejrzeć [śledzenie cykliczne](../../../../docs/framework/wcf/samples/circular-tracing.md) przykładowa uzyskać więcej informacji o alternatywnych odbiornika przeprowadzić logowanie cykliczne.</span><span class="sxs-lookup"><span data-stu-id="396ad-129">You can also review the [Circular Tracing](../../../../docs/framework/wcf/samples/circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="396ad-130">Aby skonfigurować, kompilacji, a następnie uruchom próbki</span><span class="sxs-lookup"><span data-stu-id="396ad-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="396ad-131">Pamiętaj, że wykonano procedurę [jednorazowego procedurę instalacji dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="396ad-131">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="396ad-132">Postępuj zgodnie z instrukcjami w celu skompilowania rozwiązania, [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="396ad-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="396ad-133">Aby używać poleceń RegisterProvider.bat, SetupETW.bat i CleanupETW.bat, należy uruchomić przy użyciu konta administratora lokalnego.</span><span class="sxs-lookup"><span data-stu-id="396ad-133">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="396ad-134">Jeśli używasz [!INCLUDE[wv](../../../../includes/wv-md.md)] lub później, należy także uruchomić wiersz polecenia z podwyższonym poziomem uprawnień.</span><span class="sxs-lookup"><span data-stu-id="396ad-134">If you are using [!INCLUDE[wv](../../../../includes/wv-md.md)] or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="396ad-135">Aby to zrobić, kliknij prawym przyciskiem myszy ikonę wiersz polecenia, a następnie kliknij przycisk **Uruchom jako administrator**.</span><span class="sxs-lookup"><span data-stu-id="396ad-135">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="396ad-136">Przed uruchomieniem próbki, należy uruchomić RegisterProvider.bat na kliencie i serwerze.</span><span class="sxs-lookup"><span data-stu-id="396ad-136">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="396ad-137">Wynikowy plik ETWTracingSampleLog.etl to konfiguruje do generowania danych śledzenia, które mogą być odczytywane przez Podgląd śledzenia usługi.</span><span class="sxs-lookup"><span data-stu-id="396ad-137">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="396ad-138">Ten plik znajduje się w folderze C:\logs.</span><span class="sxs-lookup"><span data-stu-id="396ad-138">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="396ad-139">Jeśli ten folder nie istnieje, należy utworzyć lub są generowane nie dane śledzenia.</span><span class="sxs-lookup"><span data-stu-id="396ad-139">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="396ad-140">Następnie uruchom SetupETW.bat na komputery klienckie i serwery, aby rozpocząć sesję śledzenia funkcji ETW.</span><span class="sxs-lookup"><span data-stu-id="396ad-140">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="396ad-141">Plik SetupETW.bat znajduje się w folderze CS\Client.</span><span class="sxs-lookup"><span data-stu-id="396ad-141">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4.  <span data-ttu-id="396ad-142">Aby uruchomić przykładowy w konfiguracji pojedynczej lub między komputerami, postępuj zgodnie z instrukcjami w [uruchamiania przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="396ad-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="396ad-143">Po zakończeniu próbki, należy uruchomić CleanupETW.bat, aby zakończyć tworzenie pliku ETWTracingSampleLog.etl.</span><span class="sxs-lookup"><span data-stu-id="396ad-143">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6.  <span data-ttu-id="396ad-144">Otwórz plik ETWTracingSampleLog.etl od w podglądzie śledzenia usługi.</span><span class="sxs-lookup"><span data-stu-id="396ad-144">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="396ad-145">Pojawi się monit można zapisać pliku binarnego sformatowane jako plik .svclog.</span><span class="sxs-lookup"><span data-stu-id="396ad-145">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7.  <span data-ttu-id="396ad-146">Otworzyć plik .svclog nowo utworzonego w ramach podglądu śledzenia usługi, aby wyświetlić dane śledzenia zdarzeń systemu Windows i ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="396ad-146">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="396ad-147">Próbki mogą być zainstalowane na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="396ad-147">The samples may already be installed on your computer.</span></span> <span data-ttu-id="396ad-148">Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).</span><span class="sxs-lookup"><span data-stu-id="396ad-148">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="396ad-149">Jeśli ten katalog nie istnieje, przejdź do [Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) przykłady dla programu .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) pobrać wszystkie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] próbek.</span><span class="sxs-lookup"><span data-stu-id="396ad-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="396ad-150">W tym przykładzie znajduje się w następującym katalogu.</span><span class="sxs-lookup"><span data-stu-id="396ad-150">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="396ad-151">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="396ad-151">See Also</span></span>  
 [<span data-ttu-id="396ad-152">Przykłady monitorowania AppFabric</span><span class="sxs-lookup"><span data-stu-id="396ad-152">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)