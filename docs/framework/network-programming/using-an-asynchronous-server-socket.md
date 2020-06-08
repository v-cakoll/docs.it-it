---
title: Uso di un socket server asincrono
description: Questo esempio mostra un socket server asincrono. La classe Socket USA .NET Framework programmazione asincrona per elaborare le richieste di servizio di rete.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- sockets, asynchronous server sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- asynchronous server sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
ms.openlocfilehash: 8b85afb3ffdf69973eff37ccbb067b470ed44e3a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502028"
---
# <a name="using-an-asynchronous-server-socket"></a><span data-ttu-id="c2c48-104">Uso di un socket server asincrono</span><span class="sxs-lookup"><span data-stu-id="c2c48-104">Using an Asynchronous Server Socket</span></span>
<span data-ttu-id="c2c48-105">I socket server asincroni usano il modello di programmazione asincrona di .NET Framework per elaborare le richieste di servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="c2c48-105">Asynchronous server sockets use the .NET Framework asynchronous programming model to process network service requests.</span></span> <span data-ttu-id="c2c48-106">La classe <xref:System.Net.Sockets.Socket> segue il modello di denominazione asincrona di .NET Framework standard. Ad esempio, il metodo sincrono <xref:System.Net.Sockets.Socket.Accept%2A> corrisponde ai metodi asincroni <xref:System.Net.Sockets.Socket.BeginAccept%2A> e <xref:System.Net.Sockets.Socket.EndAccept%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2c48-106">The <xref:System.Net.Sockets.Socket> class follows the standard .NET Framework asynchronous naming pattern; for example, the synchronous <xref:System.Net.Sockets.Socket.Accept%2A> method corresponds to the asynchronous <xref:System.Net.Sockets.Socket.BeginAccept%2A> and <xref:System.Net.Sockets.Socket.EndAccept%2A> methods.</span></span>  
  
 <span data-ttu-id="c2c48-107">Un socket server asincrono richiede un metodo per iniziare ad accettare le richieste di connessione dalla rete, un metodo di callback per gestire le richieste di connessione e iniziare a ricevere dati dalla rete e un metodo di callback per terminare la ricezione dei dati.</span><span class="sxs-lookup"><span data-stu-id="c2c48-107">An asynchronous server socket requires a method to begin accepting connection requests from the network, a callback method to handle the connection requests and begin receiving data from the network, and a callback method to end receiving the data.</span></span> <span data-ttu-id="c2c48-108">Tutti questi metodi vengono descritti più avanti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="c2c48-108">All these methods are discussed further in this section.</span></span>  
  
 <span data-ttu-id="c2c48-109">Nell'esempio seguente, per iniziare ad accettare le richieste di connessione dalla rete, il metodo `StartListening` inizializza **Socket** e quindi usa il metodo **BeginAccept** per iniziare ad accettare nuove connessioni.</span><span class="sxs-lookup"><span data-stu-id="c2c48-109">In the following example, to begin accepting connection requests from the network, the method `StartListening` initializes the **Socket** and then uses the **BeginAccept** method to start accepting new connections.</span></span> <span data-ttu-id="c2c48-110">Il metodo di callback per l'accettazione viene chiamato alla ricezione di una nuova richiesta di connessione sul socket.</span><span class="sxs-lookup"><span data-stu-id="c2c48-110">The accept callback method is called when a new connection request is received on the socket.</span></span> <span data-ttu-id="c2c48-111">È responsabile del recupero dell'istanza di **Socket** che gestirà la connessione e del passaggio di tale **Socket** al thread che elaborerà la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c2c48-111">It is responsible for getting the **Socket** instance that will handle the connection and handing that **Socket** off to the thread that will process the request.</span></span> <span data-ttu-id="c2c48-112">Il metodo di callback per l'accettazione implementa il delegato <xref:System.AsyncCallback>, restituisce un void e accetta un singolo parametro di tipo <xref:System.IAsyncResult>.</span><span class="sxs-lookup"><span data-stu-id="c2c48-112">The accept callback method implements the <xref:System.AsyncCallback> delegate; it returns a void and takes a single parameter of type <xref:System.IAsyncResult>.</span></span> <span data-ttu-id="c2c48-113">L'esempio seguente è la shell di un metodo di callback per l'accettazione.</span><span class="sxs-lookup"><span data-stu-id="c2c48-113">The following example is the shell of an accept callback method.</span></span>  
  
```vb  
Sub AcceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
void AcceptCallback(IAsyncResult ar)
{  
    // Add the callback code here.  
}  
```  
  
 <span data-ttu-id="c2c48-114">Il metodo **BeginAccept** accetta due parametri, un delegato **AsyncCallback** che punta al metodo di callback per l'accettazione e un oggetto usato per passare le informazioni sullo stato al metodo di callback.</span><span class="sxs-lookup"><span data-stu-id="c2c48-114">The **BeginAccept** method takes two parameters, an **AsyncCallback** delegate that points to the accept callback method and an object that is used to pass state information to the callback method.</span></span> <span data-ttu-id="c2c48-115">Nell'esempio seguente il **Socket** in ascolto viene passato al metodo di callback tramite il parametro *state*.</span><span class="sxs-lookup"><span data-stu-id="c2c48-115">In the following example, the listening **Socket** is passed to the callback method through the *state* parameter.</span></span> <span data-ttu-id="c2c48-116">Questo esempio crea un delegato **AsyncCallback** e inizia ad accettare connessioni dalla rete.</span><span class="sxs-lookup"><span data-stu-id="c2c48-116">This example creates an **AsyncCallback** delegate and starts accepting connections from the network.</span></span>  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.AcceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
```  
  
 <span data-ttu-id="c2c48-117">I socket asincroni usano thread dal pool di thread di sistema per elaborare le connessioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c2c48-117">Asynchronous sockets use threads from the system thread pool to process incoming connections.</span></span> <span data-ttu-id="c2c48-118">Un thread è responsabile dell'accettazione di connessioni, un altro thread viene usato per gestire ogni connessione in ingresso e un altro thread è responsabile della ricezione di dati dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="c2c48-118">One thread is responsible for accepting connections, another thread is used to handle each incoming connection, and another thread is responsible for receiving data from the connection.</span></span> <span data-ttu-id="c2c48-119">Può trattarsi dello stesso thread, a seconda di quale thread viene assegnato dal pool di thread.</span><span class="sxs-lookup"><span data-stu-id="c2c48-119">These could be the same thread, depending on which thread is assigned by the thread pool.</span></span> <span data-ttu-id="c2c48-120">Nell'esempio seguente la classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> sospende l'esecuzione del thread principale e segnala quando l'esecuzione può continuare.</span><span class="sxs-lookup"><span data-stu-id="c2c48-120">In the following example, the <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class suspends execution of the main thread and signals when execution can continue.</span></span>  
  
 <span data-ttu-id="c2c48-121">L'esempio seguente mostra un metodo asincrono che crea un socket TCP/IP asincrono nel computer locale e inizia ad accettare connessioni.</span><span class="sxs-lookup"><span data-stu-id="c2c48-121">The following example shows an asynchronous method that creates an asynchronous TCP/IP socket on the local computer and begins accepting connections.</span></span> <span data-ttu-id="c2c48-122">Si presuppone che esista un **ManualResetEvent** globale denominato `allDone`, che il metodo sia un membro di una classe denominata `SocketListener` e che sia stato definito un metodo di callback denominato `AcceptCallback`.</span><span class="sxs-lookup"><span data-stu-id="c2c48-122">It assumes that there is a global **ManualResetEvent** named `allDone`, that the method is a member of a class named `SocketListener`, and that a callback method named `AcceptCallback` is defined.</span></span>  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}")  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.AcceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
```  
  
```csharp  
public void StartListening()
{  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0], 11000);  
  
    Console.WriteLine($"Local address and port : {localEP.ToString()}");  
  
    Socket listener = new Socket(localEP.Address.AddressFamily, SocketType.Stream, ProtocolType.Tcp);  
  
    try
    {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true)
        {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
  
            allDone.WaitOne();  
        }  
    }
    catch (Exception e)
    {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine("Closing the listener...");  
}  
```  
  
 <span data-ttu-id="c2c48-123">Il metodo di callback per l'accettazione (`AcceptCallback` nell'esempio precedente) ha la responsabilità di segnalare al thread principale dell'applicazione di continuare l'elaborazione, di stabilire la connessione con il client e di avviare la lettura asincrona dei dati dal client.</span><span class="sxs-lookup"><span data-stu-id="c2c48-123">The accept callback method (`AcceptCallback` in the preceding example) is responsible for signaling the main application thread to continue processing, establishing the connection with the client, and starting the asynchronous read of data from the client.</span></span> <span data-ttu-id="c2c48-124">L'esempio seguente è la prima parte di un'implementazione del metodo `AcceptCallback`.</span><span class="sxs-lookup"><span data-stu-id="c2c48-124">The following example is the first part of an implementation of the `AcceptCallback` method.</span></span> <span data-ttu-id="c2c48-125">Questa sezione del metodo segnala al thread principale dell'applicazione di continuare l'elaborazione e stabilisce la connessione al client.</span><span class="sxs-lookup"><span data-stu-id="c2c48-125">This section of the method signals the main application thread to continue processing and establishes the connection to the client.</span></span> <span data-ttu-id="c2c48-126">Si presuppone l'esistenza di un **ManualResetEvent** globale denominato `allDone`.</span><span class="sxs-lookup"><span data-stu-id="c2c48-126">It assumes a global **ManualResetEvent** named `allDone`.</span></span>  
  
```vb  
Public Sub AcceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'AcceptCallback  
```  
  
```csharp  
public void AcceptCallback(IAsyncResult ar)
{  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.
}  
```  
  
 <span data-ttu-id="c2c48-127">Per la lettura dei dati da un socket client è necessario un oggetto stato che passa i valori tra chiamate asincrone.</span><span class="sxs-lookup"><span data-stu-id="c2c48-127">Reading data from a client socket requires a state object that passes values between asynchronous calls.</span></span> <span data-ttu-id="c2c48-128">L'esempio seguente implementa un oggetto di stato per la ricezione di una stringa dal client remoto.</span><span class="sxs-lookup"><span data-stu-id="c2c48-128">The following example implements a state object for receiving a string from the remote client.</span></span> <span data-ttu-id="c2c48-129">Contiene i campi per il socket client, un buffer di dati per la ricezione dei dati e un <xref:System.Text.StringBuilder> per creare la stringa di dati inviata dal client.</span><span class="sxs-lookup"><span data-stu-id="c2c48-129">It contains fields for the client socket, a data buffer for receiving data, and a <xref:System.Text.StringBuilder> for creating the data string sent by the client.</span></span> <span data-ttu-id="c2c48-130">Il posizionamento di questi campi nell'oggetto stato consente di mantenerne i valori tra più chiamate per leggere i dati dal socket client.</span><span class="sxs-lookup"><span data-stu-id="c2c48-130">Placing these fields in the state object allows their values to be preserved across multiple calls to read data from the client socket.</span></span>  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject
{  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 <span data-ttu-id="c2c48-131">La sezione del metodo `AcceptCallback` che avvia la ricezione dei dati dal socket client inizializza prima di tutto un'istanza della classe `StateObject` e quindi chiama il metodo <xref:System.Net.Sockets.Socket.BeginReceive%2A> per avviare la lettura dei dati dal socket client in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="c2c48-131">The section of the `AcceptCallback` method that starts receiving the data from the client socket first initializes an instance of the `StateObject` class and then calls the <xref:System.Net.Sockets.Socket.BeginReceive%2A> method to start reading the data from the client socket asynchronously.</span></span>  
  
 <span data-ttu-id="c2c48-132">L'esempio seguente mostra il metodo `AcceptCallback` completo.</span><span class="sxs-lookup"><span data-stu-id="c2c48-132">The following example shows the complete `AcceptCallback` method.</span></span> <span data-ttu-id="c2c48-133">Si presuppone che esista un **ManualResetEvent** globale denominato `allDone,`, che sia stata definita la classe `StateObject` e che sia stato definito il metodo `ReadCallback` in una classe denominata `SocketListener`.</span><span class="sxs-lookup"><span data-stu-id="c2c48-133">It assumes that there is a global **ManualResetEvent** named `allDone,` that the `StateObject` class is defined, and that the `ReadCallback` method is defined in a class named `SocketListener`.</span></span>  
  
```vb  
Public Shared Sub AcceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.ReadCallback, state)  
End Sub 'AcceptCallback  
```  
  
```csharp  
public static void AcceptCallback(IAsyncResult ar)
{  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.ReadCallback), state);  
}  
```  
  
 <span data-ttu-id="c2c48-134">Il metodo finale che deve essere implementato per il socket server asincrono è il metodo di callback per la lettura che restituisce i dati inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="c2c48-134">The final method that needs to be implemented for the asynchronous socket server is the read callback method that returns the data sent by the client.</span></span> <span data-ttu-id="c2c48-135">Come nel caso del metodo di callback per l'accettazione, il metodo di callback per la lettura è un delegato **AsyncCallback**.</span><span class="sxs-lookup"><span data-stu-id="c2c48-135">Like the accept callback method, the read callback method is an **AsyncCallback** delegate.</span></span> <span data-ttu-id="c2c48-136">Questo metodo legge uno o più byte dal socket client nel buffer di dati e quindi chiama di nuovo il metodo **BeginReceive** fino al completamento dei dati inviati dal client.</span><span class="sxs-lookup"><span data-stu-id="c2c48-136">This method reads one or more bytes from the client socket into the data buffer and then calls the **BeginReceive** method again until the data sent by the client is complete.</span></span> <span data-ttu-id="c2c48-137">Quando l'intero messaggio è stato letto dal client, la stringa viene visualizzata nella console e il socket server che gestisce la connessione al client viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="c2c48-137">Once the entire message has been read from the client, the string is displayed on the console and the server socket handling the connection to the client is closed.</span></span>  
  
 <span data-ttu-id="c2c48-138">L'esempio seguente implementa il metodo `ReadCallback`.</span><span class="sxs-lookup"><span data-stu-id="c2c48-138">The following sample implements the `ReadCallback` method.</span></span> <span data-ttu-id="c2c48-139">Si presuppone che la classe `StateObject` sia definita.</span><span class="sxs-lookup"><span data-stu-id="c2c48-139">It assumes that the `StateObject` class is defined.</span></span>  
  
```vb  
Public Shared Sub ReadCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReadCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine($"Read {content.Length} bytes from socket. {ControlChars.Cr} Data : {content}")  
        End If  
    End If  
End Sub 'ReadCallback  
```  
  
```csharp  
public static void ReadCallback(IAsyncResult ar)
{  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0)
    {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReadCallback), state);  
    }
    else
    {  
        if (state.sb.Length > 1)
        {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine($"Read {content.Length} bytes from socket.\n Data : {content}");
        }  
        handler.Close();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2c48-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2c48-140">See also</span></span>

- [<span data-ttu-id="c2c48-141">Uso di un socket server sincrono</span><span class="sxs-lookup"><span data-stu-id="c2c48-141">Using a Synchronous Server Socket</span></span>](using-a-synchronous-server-socket.md)
- [<span data-ttu-id="c2c48-142">Esempio di socket server asincrono</span><span class="sxs-lookup"><span data-stu-id="c2c48-142">Asynchronous Server Socket Example</span></span>](asynchronous-server-socket-example.md)
- [<span data-ttu-id="c2c48-143">Threading</span><span class="sxs-lookup"><span data-stu-id="c2c48-143">Threading</span></span>](../../standard/threading/index.md)
- [<span data-ttu-id="c2c48-144">Attesa con socket</span><span class="sxs-lookup"><span data-stu-id="c2c48-144">Listening with Sockets</span></span>](listening-with-sockets.md)
