---
title: Klient ASMX z usługą WCF
ms.date: 03/30/2017
ms.assetid: 3ea381ee-ac7d-4d62-8c6c-12dc3650879f
ms.openlocfilehash: d526bc01d7809aa2672dcfcf194ad9c7d2e7baa5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527516"
---
# <a name="asmx-client-with-a-wcf-service"></a>Klient ASMX z usługą WCF
W tym przykładzie przedstawiono sposób tworzenia usługi przy użyciu usługi Windows Communication Foundation (WCF) i następnie uzyskać dostęp do usługi z klienta inne niż WCF, takich jak klient ASMX.  
  
> [!NOTE]
>  Procedury i kompilacja instrukcje dotyczące instalacji w tym przykładzie znajdują się na końcu tego tematu.  
  
 W tym przykładzie składa się z konsoli programu klienckiego (.exe) i usługi biblioteki (.dll), hostowanej przez Internetowe usługi informacyjne (IIS). Usługa implementuje kontraktu, który definiuje wzorzec komunikacji "żądanie-odpowiedź". Kontrakt jest definiowany przez `ICalculator` interfejs, który udostępnia operacje matematyczne (`Add`, `Subtract`, `Multiply`, i `Divide`). Klient ASMX wysyła żądań synchronicznych operacji matematycznych i odpowiedzi usługi z wynikiem.  
  
 Implementuje usługi `ICalculator` Umowę zgodnie z definicją w poniższym kodzie.  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <xref:System.Runtime.Serialization.DataContractSerializer> i <xref:System.Xml.Serialization.XmlSerializer> mapowania typów CLR reprezentację XML. <xref:System.Runtime.Serialization.DataContractSerializer> Inaczej niż element XmlSerializer interpretuje niektóre reprezentacji XML. Generatory serwera proxy spoza WCF, takich jak Wsdl.exe, generowania bardziej użyteczne interfejsu używanego elementu XmlSerializer. <xref:System.ServiceModel.XmlSerializerFormatAttribute> Jest stosowany do `ICalculator` interfejsu, aby upewnić się, że element XmlSerializer służy do mapowania typów CLR do pliku XML. Implementacja usługi oblicza i zwraca odpowiedni wynik.  
  
 Usługa udostępnia jeden punkt końcowy do komunikacji z usługą zdefiniowane przy użyciu pliku konfiguracji (Web.config). Punkt końcowy składa się z adresu, powiązanie i kontrakt. Usługa udostępnia punkt końcowy pod podstawowym adresem udostępniane przez hosta usług Internet Information Services (IIS). `binding` Atrybut jest ustawiony na basicHttpBinding, zapewniająca komunikacji HTTP przy użyciu protokołu SOAP 1.1, który jest zgodny z protokołu WS-I BasicProfile 1.1, jak pokazano w poniższym Przykładowa konfiguracja.  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc.  -->  
    <endpoint address=""  
              binding="basicHttpBinding"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </service>  
</services>  
```  
  
 Klient ASMX komunikuje się z usługą WCF, za pomocą typizowanego serwera proxy, który jest generowany przez narzędzie Web Services Description Language (WSDL) (Wsdl.exe). Typizowanego serwera proxy znajduje się w generatedClient.cs pliku. Narzędzie WSDL pobiera metadane dla określonej usługi i generuje typizowanego serwera proxy do użytku przez klienta do komunikacji. Domyślnie struktura nie ujawnia żadnych metadanych. Aby udostępnić metadane wymagane do generowania serwera proxy, należy dodać [ \<serviceMetadata w pliku >](../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md) i ustaw jego `httpGetEnabled` atrybutu `True` jak pokazano na następującej konfiguracji.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- Setting httpGetEnabled to True on the serviceMetadata  
           behavior exposes the service's wsdl at <base address>?wsdl :  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Uruchom następujące polecenie w wierszu polecenia w katalogu klienta można wygenerować typizowanego serwera proxy.  
  
```console  
wsdl /n:Microsoft.ServiceModel.Samples /o:generatedClient.cs /urlkey:CalculatorServiceAddress http://localhost/servicemodelsamples/service.svc?wsdl  
```  
  
 Za pomocą wygenerowanego typizowanego serwera proxy, ten klient uzyskuje dostęp danego punktu końcowego, konfigurując odpowiedni adres. Klient korzysta z do określania punktu końcowego do komunikowania się z plikiem konfiguracyjnym (App.config).  
  
```xml  
<appSettings>  
  <add key="CalculatorServiceAddress"   
       value="http://localhost/ServiceModelSamples/service.svc"/>  
</appSettings>  
```  
  
 Implementacja klienta tworzy wystąpienie klasy typizowanego serwera proxy, aby rozpocząć, komunikacji z usługą.  
  
```csharp
// Create a client to the CalculatorService.  
using (CalculatorService client = new CalculatorService())  
{  
    // Call the Add service operation.  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    value1 = 145.00D;  
    value2 = 76.54D;  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    value1 = 9.00D;  
    value2 = 81.25D;  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    value1 = 22.00D;  
    value2 = 7.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
}  
  
Console.WriteLine();  
Console.WriteLine("Press <ENTER> to terminate client.");  
Console.ReadLine();  
```  
  
 Po uruchomieniu przykładu, operacja żądań i odpowiedzi są wyświetlane w oknie konsoli klienta. Naciśnij klawisz ENTER w oknie klienta, aby zamknąć klienta.  
  
```console 
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Aby skonfigurować, tworzenie i uruchamianie aplikacji przykładowej  
  
1.  Upewnij się, że wykonano [procedura konfiguracji jednorazowe dla przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Aby kompilować rozwiązania w wersji języka C# lub Visual Basic .NET, postępuj zgodnie z instrukcjami [kompilowanie przykładów programu Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Do uruchomienia przykładu w konfiguracji o jednym lub wielu maszyny, postępuj zgodnie z instrukcjami [uruchamianie przykładów Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!NOTE]
>  Aby uzyskać więcej informacji na temat przekazywanie i zwracanie danych złożonych typów zobacz: [Powiązanie danych w Windows Forms klienta](../../../../docs/framework/wcf/samples/data-binding-in-a-windows-forms-client.md), [powiązanie danych w kliencie systemu Windows Presentation Foundation](../../../../docs/framework/wcf/samples/data-binding-in-a-wpf-client.md), i [powiązanie danych w kliencie programu ASP.NET](../../../../docs/framework/wcf/samples/data-binding-in-an-aspnet-client.md)  
  
> [!IMPORTANT]
>  Przykłady może już być zainstalowany na tym komputerze. Przed kontynuowaniem sprawdź, czy są dostępne dla następującego katalogu (ustawienie domyślne).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Jeśli ten katalog nie istnieje, przejdź do strony [Windows Communication Foundation (WCF) i przykłady Windows Workflow Foundation (WF) dla platformy .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) do pobierania wszystkich Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykładów. W tym przykładzie znajduje się w następującym katalogu.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\ASMX`  
  
## <a name="see-also"></a>Zobacz także
