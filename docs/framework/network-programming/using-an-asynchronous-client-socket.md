---
title: "Przy użyciu gniazda asynchroniczne klienta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- asynchronous client sockets
- Socket class, asynchronous client sockets
- requesting data from Internet, sockets
- sockets, asynchronous client sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 263d8a82bf70ac86e776f28d660ef08c58a33384
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="using-an-asynchronous-client-socket"></a><span data-ttu-id="b1ee3-102">Przy użyciu gniazda asynchroniczne klienta</span><span class="sxs-lookup"><span data-stu-id="b1ee3-102">Using an Asynchronous Client Socket</span></span>
<span data-ttu-id="b1ee3-103">Gniazdo klienta asynchronicznego nie wstrzymuje aplikacji podczas oczekiwania na zakończenie operacji sieciowych.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-103">An asynchronous client socket does not suspend the application while waiting for network operations to complete.</span></span> <span data-ttu-id="b1ee3-104">Zamiast tego używa standardowych model programowania asynchronicznego .NET Framework do przetwarzania połączenia sieciowego w jednym wątku, gdy aplikacja nadal działa w oryginalnym wątku.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-104">Instead, it uses the standard .NET Framework asynchronous programming model to process the network connection on one thread while the application continues to run on the original thread.</span></span> <span data-ttu-id="b1ee3-105">Gniazda asynchroniczne są odpowiednie dla aplikacji, która w znacznym stopniu wykorzystywane w sieci lub który nie może czekać na zakończenie przed kontynuowaniem operacji sieciowych.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-105">Asynchronous sockets are appropriate for applications that make heavy use of the network or that cannot wait for network operations to complete before continuing.</span></span>  
  
 <span data-ttu-id="b1ee3-106"><xref:System.Net.Sockets.Socket> Następujące klasy wzorzec nazewnictwa .NET Framework dla metod asynchronicznych; na przykład synchroniczne <xref:System.Net.Sockets.Socket.Receive%2A> metody odpowiada asynchroniczną <xref:System.Net.Sockets.Socket.BeginReceive%2A> i <xref:System.Net.Sockets.Socket.EndReceive%2A> metody.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-106">The <xref:System.Net.Sockets.Socket> class follows the .NET Framework naming pattern for asynchronous methods; for example, the synchronous <xref:System.Net.Sockets.Socket.Receive%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginReceive%2A> and <xref:System.Net.Sockets.Socket.EndReceive%2A> methods.</span></span>  
  
 <span data-ttu-id="b1ee3-107">Operacje asynchroniczne wymagają Metoda wywołania zwrotnego zwracają wyniki operacji.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-107">Asynchronous operations require a callback method to return the result of the operation.</span></span> <span data-ttu-id="b1ee3-108">Jeśli aplikacja nie trzeba znać wynik, brak metody wywołania zwrotnego jest wymagana.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-108">If your application does not need to know the result, then no callback method is required.</span></span> <span data-ttu-id="b1ee3-109">Przykład kodu w tej sekcji przedstawiono uruchamiania nawiązywania połączenia z urządzeniem sieciowym a metody wywołania zwrotnego, aby zakończyć połączenie, metody, aby rozpocząć wysyłanie danych i metoda wywołania zwrotnego do ukończenia wysyłania i metody, aby rozpocząć odbieranie danych przy użyciu metody i Metoda wywołania zwrotnego do końca odbierania danych.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-109">The example code in this section demonstrates using a method to start connecting to a network device and a callback method to complete the connection, a method to start sending data and a callback method to complete the send, and a method to start receiving data and a callback method to end receiving data.</span></span>  
  
 <span data-ttu-id="b1ee3-110">Asynchroniczne sockets umożliwia wiele wątków z puli wątków systemu procesu połączeń sieciowych.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-110">Asynchronous sockets use multiple threads from the system thread pool to process network connections.</span></span> <span data-ttu-id="b1ee3-111">Jeden wątek jest odpowiedzialny za inicjowanie wysyłania i odbierania danych. inne wątki nawiązać połączenie z urządzeniem sieciowym i wysyłać ani odbierać dane.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-111">One thread is responsible for initiating the sending or receiving of data; other threads complete the connection to the network device and send or receive the data.</span></span> <span data-ttu-id="b1ee3-112">W poniższych przykładach wystąpienia <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> klasy służą do Wstrzymaj wykonywanie wątku głównego i sygnału, gdy można kontynuować wykonywania.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-112">In the following examples, instances of the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class are used to suspend execution of the main thread and signal when execution can continue.</span></span>  
  
 <span data-ttu-id="b1ee3-113">W poniższym przykładzie nawiązywania połączenia z urządzeniem sieciowym asynchroniczne gniazda `Connect` inicjuje metody **gniazda** , a następnie wywołuje <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType> jest metoda zdalny punkt końcowy, który reprezentuje urządzenie sieciowe , metody wywołania zwrotnego connect i obiektu stanu (klient **gniazda**), który jest używany do przekazywania informacji o stanie między wywołania asynchroniczne.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-113">In the following example, to connect an asynchronous socket to a network device, the `Connect` method initializes a **Socket** and then calls the <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType> method, passing a remote endpoint that represents the network device, the connect callback method, and a state object (the client **Socket**), which is used to pass state information between asynchronous calls.</span></span> <span data-ttu-id="b1ee3-114">Przykład implementuje `Connect` metodę, aby połączyć z określonym **gniazda** do określonego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-114">The example implements the `Connect` method to connect the specified **Socket** to the specified endpoint.</span></span> <span data-ttu-id="b1ee3-115">Przyjęto założenie, globalnym **ManualResetEvent** o nazwie `connectDone`.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-115">It assumes a global **ManualResetEvent** named `connectDone`.</span></span>  
  
```vb  
Public Shared Sub Connect(remoteEP As EndPoint, client As Socket)  
    client.BeginConnect(remoteEP, _  
       AddressOf ConnectCallback, client)  
  
    connectDone.WaitOne()  
End Sub 'Connect  
```  
  
```csharp  
public static void Connect(EndPoint remoteEP, Socket client) {  
    client.BeginConnect(remoteEP,   
        new AsyncCallback(ConnectCallback), client );  
  
   connectDone.WaitOne();  
}  
```  
  
 <span data-ttu-id="b1ee3-116">Metoda wywołania zwrotnego connect `ConnectCallback` implementuje <xref:System.AsyncCallback> delegowanie.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-116">The connect callback method `ConnectCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="b1ee3-117">Po udostępnieniu urządzenie zdalne i następnie sygnały wątku aplikacji połączenie zostało wykonane przez ustawienie łączy do urządzenia zdalnego **ManualResetEvent** `connectDone`.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-117">It connects to the remote device when the remote device is available and then signals the application thread that the connection is complete by setting the **ManualResetEvent** `connectDone`.</span></span> <span data-ttu-id="b1ee3-118">Poniższy kod implementuje `ConnectCallback` metody.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-118">The following code implements the `ConnectCallback` method.</span></span>  
  
```vb  
Private Shared Sub ConnectCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete the connection.  
        client.EndConnect(ar)  
  
        Console.WriteLine("Socket connected to {0}", _  
            client.RemoteEndPoint.ToString())  
  
        ' Signal that the connection has been made.  
        connectDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ConnectCallback  
```  
  
```csharp  
private static void ConnectCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete the connection.  
        client.EndConnect(ar);  
  
        Console.WriteLine("Socket connected to {0}",  
            client.RemoteEndPoint.ToString());  
  
        // Signal that the connection has been made.  
        connectDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="b1ee3-119">Przykładowa metoda `Send` koduje danych określonego ciągu w formacie ASCII i wysyła je asynchronicznie na urządzeniu sieci reprezentowany przez określony gniazda.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-119">The example method `Send` encodes the specified string data in ASCII format and sends it asynchronously to the network device represented by the specified socket.</span></span> <span data-ttu-id="b1ee3-120">Poniższy przykład implementuje `Send` metody.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-120">The following example implements the `Send` method.</span></span>  
  
```vb  
Private Shared Sub Send(client As Socket, data As [String])  
    ' Convert the string data to byte data using ASCII encoding.  
    Dim byteData As Byte() = Encoding.ASCII.GetBytes(data)  
  
    ' Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None, _  
        AddressOf SendCallback, client)  
End Sub 'Send  
```  
  
```csharp  
private static void Send(Socket client, String data) {  
    // Convert the string data to byte data using ASCII encoding.  
    byte[] byteData = Encoding.ASCII.GetBytes(data);  
  
    // Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None,  
        new AsyncCallback(SendCallback), client);  
}  
```  
  
 <span data-ttu-id="b1ee3-121">Metoda wywołania zwrotnego wysyłania `SendCallback` implementuje <xref:System.AsyncCallback> delegowanie.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-121">The send callback method `SendCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="b1ee3-122">Gdy urządzenie sieciowe jest gotowa do odbioru, wysyła dane.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-122">It sends the data when the network device is ready to receive.</span></span> <span data-ttu-id="b1ee3-123">Poniższy przykład przedstawia implementację `SendCallback` metody.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-123">The following example shows the implementation of the `SendCallback` method.</span></span> <span data-ttu-id="b1ee3-124">Przyjęto założenie, globalnym **ManualResetEvent** o nazwie `sendDone`.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-124">It assumes a global **ManualResetEvent** named `sendDone`.</span></span>  
  
```vb  
Private Shared Sub SendCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete sending the data to the remote device.  
        Dim bytesSent As Integer = client.EndSend(ar)  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent)  
  
        ' Signal that all bytes have been sent.  
        sendDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'SendCallback  
```  
  
```csharp  
private static void SendCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete sending the data to the remote device.  
        int bytesSent = client.EndSend(ar);  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent);  
  
        // Signal that all bytes have been sent.  
        sendDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="b1ee3-125">Odczyt danych z gniazda klienta wymaga przesyłane wartości między asynchroniczne wywołania obiektu stanu.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-125">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="b1ee3-126">Następujące klasy jest przykład obiekt stanu do odbierania danych z gniazda klienta.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-126">The following class is an example state object for receiving data from a client socket.</span></span> <span data-ttu-id="b1ee3-127">Zawiera on pole dla gniazda klienta, buforu dla odebranych danych i <xref:System.Text.StringBuilder> do przechowywania przychodzącego ciągu danych.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-127">It contains a field for the client socket, a buffer for the received data, and a <xref:System.Text.StringBuilder> to hold the incoming data string.</span></span> <span data-ttu-id="b1ee3-128">Umieszczenie tych pól w obiekt stanu umożliwia ich wartości, które mają być zachowane w wielu wywołań można odczytać danych z gniazda klienta.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-128">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
```vb  
Public Class StateObject  
    ' Client socket.  
    Public workSocket As Socket = Nothing   
    ' Size of receive buffer.  
    Public BufferSize As Integer = 256  
    ' Receive buffer.  
    Public buffer(256) As Byte   
    ' Received data string.  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    // Client socket.  
    public Socket workSocket = null;  
    // Size of receive buffer.  
    public const int BufferSize = 256;  
    // Receive buffer.  
    public byte[] buffer = new byte[BufferSize];  
    // Received data string.  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 <span data-ttu-id="b1ee3-129">Przykład `Receive` metoda konfiguruje obiekt stanu, a następnie wywołuje **BeginReceive** metodę, aby odczytać danych z gniazda klienta asynchronicznie.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-129">The example `Receive` method sets up the state object and then calls the **BeginReceive** method to read the data from the client socket asynchronously.</span></span> <span data-ttu-id="b1ee3-130">Poniższy przykład implementuje `Receive` metody.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-130">The following example implements the `Receive` method.</span></span>  
  
```vb  
Private Shared Sub Receive(client As Socket)  
    Try  
        ' Create the state object.  
        Dim state As New StateObject()  
        state.workSocket = client  
  
        ' Begin receiving the data from the remote device.  
        client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReceiveCallback, state)  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'Receive  
```  
  
```csharp  
private static void Receive(Socket client) {  
    try {  
        // Create the state object.  
        StateObject state = new StateObject();  
        state.workSocket = client;  
  
        // Begin receiving the data from the remote device.  
        client.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReceiveCallback), state);  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 <span data-ttu-id="b1ee3-131">Metody wywołania zwrotnego receive `ReceiveCallback` implementuje **AsyncCallback** delegowanie.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-131">The receive callback method `ReceiveCallback` implements the **AsyncCallback** delegate.</span></span> <span data-ttu-id="b1ee3-132">Odbiera dane z urządzenia sieciowego, a kompilacje ciąg komunikatu.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-132">It receives the data from the network device and builds a message string.</span></span> <span data-ttu-id="b1ee3-133">Odczytuje jeden lub więcej bajtów danych z sieci do buforu danych, a następnie wywołuje **BeginReceive** zakończeniu metody ponownie do czasu dane wysyłane przez klienta.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-133">It reads one or more bytes of data from the network into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="b1ee3-134">Gdy wszystkie dane są odczytywane z klienta, `ReceiveCallback` wątku aplikacji sygnalizuje, że dane są kompletne przez ustawienie **ManualResetEvent** `sendDone`.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-134">Once all the data is read from the client, `ReceiveCallback` signals the application thread that the data is complete by setting the **ManualResetEvent** `sendDone`.</span></span>  
  
 <span data-ttu-id="b1ee3-135">Poniższy przykładowy kod implementuje `ReceiveCallback` metody.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-135">The following example code implements the `ReceiveCallback` method.</span></span> <span data-ttu-id="b1ee3-136">Przyjęto założenie, globalne ciągu o nazwie `response` przechowuje odebranego ciągu i globalną **ManualResetEvent** o nazwie `receiveDone`.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-136">It assumes a global string named `response` that holds the received string and a global **ManualResetEvent** named `receiveDone`.</span></span> <span data-ttu-id="b1ee3-137">Serwer musi zamykany gniazdo klienta, aby zakończyć sesję sieci.</span><span class="sxs-lookup"><span data-stu-id="b1ee3-137">The server must shut down the client socket gracefully to end the network session.</span></span>  
  
```vb  
Private Shared Sub ReceiveCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the state object and the client socket   
        ' from the asynchronous state object.  
        Dim state As StateObject = CType(ar.AsyncState, StateObject)  
        Dim client As Socket = state.workSocket  
  
        ' Read data from the remote device.  
        Dim bytesRead As Integer = client.EndReceive(ar)  
  
        If bytesRead > 0 Then  
            ' There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, _  
                bytesRead))  
  
            '  Get the rest of the data.  
            client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
                AddressOf ReceiveCallback, state)  
        Else  
            ' All the data has arrived; put it in response.  
            If state.sb.Length > 1 Then  
                response = state.sb.ToString()  
            End If  
            ' Signal that all bytes have been received.  
            receiveDone.Set()  
        End If  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ReceiveCallback  
```  
  
```csharp  
private static void ReceiveCallback( IAsyncResult ar ) {  
    try {  
        // Retrieve the state object and the client socket   
        // from the asynchronous state object.  
        StateObject state = (StateObject) ar.AsyncState;  
        Socket client = state.workSocket;  
        // Read data from the remote device.  
        int bytesRead = client.EndReceive(ar);  
        if (bytesRead > 0) {  
            // There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,bytesRead));  
                //  Get the rest of the data.  
            client.BeginReceive(state.buffer,0,StateObject.BufferSize,0,  
                new AsyncCallback(ReceiveCallback), state);  
        } else {  
            // All the data has arrived; put it in response.  
            if (state.sb.Length > 1) {  
                response = state.sb.ToString();  
            }  
            // Signal that all bytes have been received.  
            receiveDone.Set();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1ee3-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1ee3-138">See Also</span></span>  
 [<span data-ttu-id="b1ee3-139">Przy użyciu gniazda synchroniczne klienta</span><span class="sxs-lookup"><span data-stu-id="b1ee3-139">Using a Synchronous Client Socket</span></span>](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)  
 [<span data-ttu-id="b1ee3-140">Nasłuchiwanie z gniazda</span><span class="sxs-lookup"><span data-stu-id="b1ee3-140">Listening with Sockets</span></span>](../../../docs/framework/network-programming/listening-with-sockets.md)  
 [<span data-ttu-id="b1ee3-141">Przykład gniazda asynchroniczne klienta</span><span class="sxs-lookup"><span data-stu-id="b1ee3-141">Asynchronous Client Socket Example</span></span>](../../../docs/framework/network-programming/asynchronous-client-socket-example.md)