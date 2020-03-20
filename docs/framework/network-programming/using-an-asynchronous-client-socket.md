---
title: Uso di un socket client asincrono
ms.date: 03/30/2017
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
ms.openlocfilehash: 748745ca6799005dccdbfcbcc37a8c2a38f2a88e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180641"
---
# <a name="using-an-asynchronous-client-socket"></a><span data-ttu-id="a957d-102">Uso di un socket client asincrono</span><span class="sxs-lookup"><span data-stu-id="a957d-102">Using an Asynchronous Client Socket</span></span>
<span data-ttu-id="a957d-103">Un socket client asincrono non sospende l'applicazione durante l'attesa del completamento delle operazioni di rete.</span><span class="sxs-lookup"><span data-stu-id="a957d-103">An asynchronous client socket does not suspend the application while waiting for network operations to complete.</span></span> <span data-ttu-id="a957d-104">Usa invece il modello di programmazione asincrona standard di .NET Framework per elaborare la connessione di rete su un singolo thread mentre l'esecuzione dell'applicazione continua sul thread originale.</span><span class="sxs-lookup"><span data-stu-id="a957d-104">Instead, it uses the standard .NET Framework asynchronous programming model to process the network connection on one thread while the application continues to run on the original thread.</span></span> <span data-ttu-id="a957d-105">I socket asincroni sono appropriati per le applicazioni che fanno un uso massiccio della rete o che non possano attendere il completamento delle operazioni di rete prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="a957d-105">Asynchronous sockets are appropriate for applications that make heavy use of the network or that cannot wait for network operations to complete before continuing.</span></span>  
  
 <span data-ttu-id="a957d-106">La classe <xref:System.Net.Sockets.Socket> segue il modello di denominazione di .NET Framework per i metodi asincroni. Ad esempio, il metodo sincrono <xref:System.Net.Sockets.Socket.Receive%2A> corrisponde ai metodi asincroni <xref:System.Net.Sockets.Socket.BeginReceive%2A> e <xref:System.Net.Sockets.Socket.EndReceive%2A>.</span><span class="sxs-lookup"><span data-stu-id="a957d-106">The <xref:System.Net.Sockets.Socket> class follows the .NET Framework naming pattern for asynchronous methods; for example, the synchronous <xref:System.Net.Sockets.Socket.Receive%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginReceive%2A> and <xref:System.Net.Sockets.Socket.EndReceive%2A> methods.</span></span>  
  
 <span data-ttu-id="a957d-107">Le operazioni asincrone richiedono un metodo di callback per restituire il risultato dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="a957d-107">Asynchronous operations require a callback method to return the result of the operation.</span></span> <span data-ttu-id="a957d-108">Se non è necessario che l'applicazione conosca il risultato, non sarà necessario alcun metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="a957d-108">If your application does not need to know the result, then no callback method is required.</span></span> <span data-ttu-id="a957d-109">L'esempio di codice in questa sezione illustra l'uso di un metodo per avviare la connessione a un dispositivo di rete e un metodo di callback per completare la connessione, un metodo per avviare l'invio dei dati e un metodo di callback per completare l'invio, un metodo per avviare la ricezione di dati e un metodo di callback per terminare la ricezione di dati.</span><span class="sxs-lookup"><span data-stu-id="a957d-109">The example code in this section demonstrates using a method to start connecting to a network device and a callback method to complete the connection, a method to start sending data and a callback method to complete the send, and a method to start receiving data and a callback method to end receiving data.</span></span>  
  
 <span data-ttu-id="a957d-110">I socket asincroni usano più thread dal pool di thread di sistema per elaborare le connessioni di rete.</span><span class="sxs-lookup"><span data-stu-id="a957d-110">Asynchronous sockets use multiple threads from the system thread pool to process network connections.</span></span> <span data-ttu-id="a957d-111">Un thread è responsabile dell'avvio dell'invio o della ricezione dei dati. Gli altri thread completano la connessione al dispositivo di rete e inviano o ricevono i dati.</span><span class="sxs-lookup"><span data-stu-id="a957d-111">One thread is responsible for initiating the sending or receiving of data; other threads complete the connection to the network device and send or receive the data.</span></span> <span data-ttu-id="a957d-112">Negli esempi seguenti, le istanze della classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> vengono usate per sospendere l'esecuzione del thread principale e segnalare quando l'esecuzione può continuare.</span><span class="sxs-lookup"><span data-stu-id="a957d-112">In the following examples, instances of the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class are used to suspend execution of the main thread and signal when execution can continue.</span></span>  
  
 <span data-ttu-id="a957d-113">Nell'esempio seguente, per connettere un socket asincrono a un dispositivo di rete, il metodo `Connect` inizializza un **Socket** e quindi chiama il metodo <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType>, passando un endpoint remoto che rappresenta il dispositivo di rete, il metodo di callback per la connessione e un oggetto di stato (il **Socket** client), che viene usato per passare le informazioni sullo stato tra chiamate asincrone.</span><span class="sxs-lookup"><span data-stu-id="a957d-113">In the following example, to connect an asynchronous socket to a network device, the `Connect` method initializes a **Socket** and then calls the <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType> method, passing a remote endpoint that represents the network device, the connect callback method, and a state object (the client **Socket**), which is used to pass state information between asynchronous calls.</span></span> <span data-ttu-id="a957d-114">L'esempio implementa il metodo `Connect` per connettere il **Socket** specificato all'endpoint specificato.</span><span class="sxs-lookup"><span data-stu-id="a957d-114">The example implements the `Connect` method to connect the specified **Socket** to the specified endpoint.</span></span> <span data-ttu-id="a957d-115">Si presuppone l'esistenza di un **ManualResetEvent** globale denominato `connectDone`.</span><span class="sxs-lookup"><span data-stu-id="a957d-115">It assumes a global **ManualResetEvent** named `connectDone`.</span></span>  
  
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
  
 <span data-ttu-id="a957d-116">Il metodo di callback per la connessione `ConnectCallback` implementa il delegato <xref:System.AsyncCallback>.</span><span class="sxs-lookup"><span data-stu-id="a957d-116">The connect callback method `ConnectCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="a957d-117">Si connette al dispositivo remoto quando è disponibile e segnala al thread dell'applicazione che la connessione è stata completata, impostando \*\*ManualResetEvent su \*\* `connectDone`.</span><span class="sxs-lookup"><span data-stu-id="a957d-117">It connects to the remote device when the remote device is available and then signals the application thread that the connection is complete by setting the **ManualResetEvent** `connectDone`.</span></span> <span data-ttu-id="a957d-118">Il codice seguente implementa il metodo `ConnectCallback`.</span><span class="sxs-lookup"><span data-stu-id="a957d-118">The following code implements the `ConnectCallback` method.</span></span>  
  
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
  
 <span data-ttu-id="a957d-119">Il metodo `Send` dell'esempio codifica i dati stringa specificati in formato ASCII e li invia in modo asincrono al dispositivo di rete rappresentato dal socket specificato.</span><span class="sxs-lookup"><span data-stu-id="a957d-119">The example method `Send` encodes the specified string data in ASCII format and sends it asynchronously to the network device represented by the specified socket.</span></span> <span data-ttu-id="a957d-120">L'esempio seguente implementa il metodo `Send`.</span><span class="sxs-lookup"><span data-stu-id="a957d-120">The following example implements the `Send` method.</span></span>  
  
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
  
 <span data-ttu-id="a957d-121">Il metodo di callback per l'invio `SendCallback` implementa il delegato <xref:System.AsyncCallback></span><span class="sxs-lookup"><span data-stu-id="a957d-121">The send callback method `SendCallback` implements the <xref:System.AsyncCallback> delegate.</span></span> <span data-ttu-id="a957d-122">e invia i dati quando il dispositivo di rete è pronto a ricevere.</span><span class="sxs-lookup"><span data-stu-id="a957d-122">It sends the data when the network device is ready to receive.</span></span> <span data-ttu-id="a957d-123">L'esempio seguente mostra l'implementazione del metodo `SendCallback`.</span><span class="sxs-lookup"><span data-stu-id="a957d-123">The following example shows the implementation of the `SendCallback` method.</span></span> <span data-ttu-id="a957d-124">Si presuppone l'esistenza di un **ManualResetEvent** globale denominato `sendDone`.</span><span class="sxs-lookup"><span data-stu-id="a957d-124">It assumes a global **ManualResetEvent** named `sendDone`.</span></span>  
  
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
  
 <span data-ttu-id="a957d-125">Per la lettura dei dati da un socket client è necessario un oggetto stato che passa i valori tra chiamate asincrone.</span><span class="sxs-lookup"><span data-stu-id="a957d-125">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="a957d-126">La classe seguente è un esempio di oggetto di stato per la ricezione di dati da un socket client.</span><span class="sxs-lookup"><span data-stu-id="a957d-126">The following class is an example state object for receiving data from a client socket.</span></span> <span data-ttu-id="a957d-127">Contiene un campo per il socket client, un buffer per i dati ricevuti e un <xref:System.Text.StringBuilder> per contenere la stringa di dati in ingresso.</span><span class="sxs-lookup"><span data-stu-id="a957d-127">It contains a field for the client socket, a buffer for the received data, and a <xref:System.Text.StringBuilder> to hold the incoming data string.</span></span> <span data-ttu-id="a957d-128">Il posizionamento di questi campi nell'oggetto stato consente di mantenerne i valori tra più chiamate per leggere i dati dal socket client.</span><span class="sxs-lookup"><span data-stu-id="a957d-128">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
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
  
 <span data-ttu-id="a957d-129">Il metodo `Receive` dell'esempio imposta l'oggetto di stato e quindi chiama il metodo **BeginReceive** per leggere i dati dal socket client in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="a957d-129">The example `Receive` method sets up the state object and then calls the **BeginReceive** method to read the data from the client socket asynchronously.</span></span> <span data-ttu-id="a957d-130">L'esempio seguente implementa il metodo `Receive`.</span><span class="sxs-lookup"><span data-stu-id="a957d-130">The following example implements the `Receive` method.</span></span>  
  
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
  
 <span data-ttu-id="a957d-131">Il metodo di callback per la ricezione `ReceiveCallback` implementa il delegato **AsyncCallback**</span><span class="sxs-lookup"><span data-stu-id="a957d-131">The receive callback method `ReceiveCallback` implements the **AsyncCallback** delegate.</span></span> <span data-ttu-id="a957d-132">e riceve i dati dal dispositivo di rete, quindi crea una stringa di messaggio.</span><span class="sxs-lookup"><span data-stu-id="a957d-132">It receives the data from the network device and builds a message string.</span></span> <span data-ttu-id="a957d-133">Questo metodo legge uno o più byte di dati dalla rete nel buffer di dati e quindi chiama di nuovo il metodo **BeginReceive** del metodo finché al completamento dei dati inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="a957d-133">It reads one or more bytes of data from the network into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="a957d-134">Una volta letti tutti i dati dal client, `ReceiveCallback` segnala al thread dell'applicazione che i dati sono completi impostando \*\*ManualResetEvent su \*\* `sendDone`.</span><span class="sxs-lookup"><span data-stu-id="a957d-134">Once all the data is read from the client, `ReceiveCallback` signals the application thread that the data is complete by setting the **ManualResetEvent** `sendDone`.</span></span>  
  
 <span data-ttu-id="a957d-135">Il codice di esempio seguente implementa il metodo `ReceiveCallback`.</span><span class="sxs-lookup"><span data-stu-id="a957d-135">The following example code implements the `ReceiveCallback` method.</span></span> <span data-ttu-id="a957d-136">Si presuppone l'esistenza di una stringa globale denominata `response` che contiene la stringa ricevuta e di un **ManualResetEvent** globale denominato `receiveDone`.</span><span class="sxs-lookup"><span data-stu-id="a957d-136">It assumes a global string named `response` that holds the received string and a global **ManualResetEvent** named `receiveDone`.</span></span> <span data-ttu-id="a957d-137">Il server deve chiudere correttamente il socket client per terminare la sessione di rete.</span><span class="sxs-lookup"><span data-stu-id="a957d-137">The server must shut down the client socket gracefully to end the network session.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a957d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a957d-138">See also</span></span>

- [<span data-ttu-id="a957d-139">Uso di un socket client sincrono</span><span class="sxs-lookup"><span data-stu-id="a957d-139">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="a957d-140">Attesa con socket</span><span class="sxs-lookup"><span data-stu-id="a957d-140">Listening with Sockets</span></span>](listening-with-sockets.md)
- [<span data-ttu-id="a957d-141">Esempio di socket client asincrono</span><span class="sxs-lookup"><span data-stu-id="a957d-141">Asynchronous Client Socket Example</span></span>](asynchronous-client-socket-example.md)
