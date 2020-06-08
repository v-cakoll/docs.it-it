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
# <a name="using-an-asynchronous-server-socket"></a>Uso di un socket server asincrono
I socket server asincroni usano il modello di programmazione asincrona di .NET Framework per elaborare le richieste di servizio di rete. La classe <xref:System.Net.Sockets.Socket> segue il modello di denominazione asincrona di .NET Framework standard. Ad esempio, il metodo sincrono <xref:System.Net.Sockets.Socket.Accept%2A> corrisponde ai metodi asincroni <xref:System.Net.Sockets.Socket.BeginAccept%2A> e <xref:System.Net.Sockets.Socket.EndAccept%2A>.  
  
 Un socket server asincrono richiede un metodo per iniziare ad accettare le richieste di connessione dalla rete, un metodo di callback per gestire le richieste di connessione e iniziare a ricevere dati dalla rete e un metodo di callback per terminare la ricezione dei dati. Tutti questi metodi vengono descritti più avanti in questa sezione.  
  
 Nell'esempio seguente, per iniziare ad accettare le richieste di connessione dalla rete, il metodo `StartListening` inizializza **Socket** e quindi usa il metodo **BeginAccept** per iniziare ad accettare nuove connessioni. Il metodo di callback per l'accettazione viene chiamato alla ricezione di una nuova richiesta di connessione sul socket. È responsabile del recupero dell'istanza di **Socket** che gestirà la connessione e del passaggio di tale **Socket** al thread che elaborerà la richiesta. Il metodo di callback per l'accettazione implementa il delegato <xref:System.AsyncCallback>, restituisce un void e accetta un singolo parametro di tipo <xref:System.IAsyncResult>. L'esempio seguente è la shell di un metodo di callback per l'accettazione.  
  
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
  
 Il metodo **BeginAccept** accetta due parametri, un delegato **AsyncCallback** che punta al metodo di callback per l'accettazione e un oggetto usato per passare le informazioni sullo stato al metodo di callback. Nell'esempio seguente il **Socket** in ascolto viene passato al metodo di callback tramite il parametro *state*. Questo esempio crea un delegato **AsyncCallback** e inizia ad accettare connessioni dalla rete.  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.AcceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(new AsyncCallback(SocketListener.AcceptCallback), listener);  
```  
  
 I socket asincroni usano thread dal pool di thread di sistema per elaborare le connessioni in ingresso. Un thread è responsabile dell'accettazione di connessioni, un altro thread viene usato per gestire ogni connessione in ingresso e un altro thread è responsabile della ricezione di dati dalla connessione. Può trattarsi dello stesso thread, a seconda di quale thread viene assegnato dal pool di thread. Nell'esempio seguente la classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> sospende l'esecuzione del thread principale e segnala quando l'esecuzione può continuare.  
  
 L'esempio seguente mostra un metodo asincrono che crea un socket TCP/IP asincrono nel computer locale e inizia ad accettare connessioni. Si presuppone che esista un **ManualResetEvent** globale denominato `allDone`, che il metodo sia un membro di una classe denominata `SocketListener` e che sia stato definito un metodo di callback denominato `AcceptCallback`.  
  
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
  
 Il metodo di callback per l'accettazione (`AcceptCallback` nell'esempio precedente) ha la responsabilità di segnalare al thread principale dell'applicazione di continuare l'elaborazione, di stabilire la connessione con il client e di avviare la lettura asincrona dei dati dal client. L'esempio seguente è la prima parte di un'implementazione del metodo `AcceptCallback`. Questa sezione del metodo segnala al thread principale dell'applicazione di continuare l'elaborazione e stabilisce la connessione al client. Si presuppone l'esistenza di un **ManualResetEvent** globale denominato `allDone`.  
  
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
  
 Per la lettura dei dati da un socket client è necessario un oggetto stato che passa i valori tra chiamate asincrone. L'esempio seguente implementa un oggetto di stato per la ricezione di una stringa dal client remoto. Contiene i campi per il socket client, un buffer di dati per la ricezione dei dati e un <xref:System.Text.StringBuilder> per creare la stringa di dati inviata dal client. Il posizionamento di questi campi nell'oggetto stato consente di mantenerne i valori tra più chiamate per leggere i dati dal socket client.  
  
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
  
 La sezione del metodo `AcceptCallback` che avvia la ricezione dei dati dal socket client inizializza prima di tutto un'istanza della classe `StateObject` e quindi chiama il metodo <xref:System.Net.Sockets.Socket.BeginReceive%2A> per avviare la lettura dei dati dal socket client in modo asincrono.  
  
 L'esempio seguente mostra il metodo `AcceptCallback` completo. Si presuppone che esista un **ManualResetEvent** globale denominato `allDone,`, che sia stata definita la classe `StateObject` e che sia stato definito il metodo `ReadCallback` in una classe denominata `SocketListener`.  
  
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
  
 Il metodo finale che deve essere implementato per il socket server asincrono è il metodo di callback per la lettura che restituisce i dati inviati dal client. Come nel caso del metodo di callback per l'accettazione, il metodo di callback per la lettura è un delegato **AsyncCallback**. Questo metodo legge uno o più byte dal socket client nel buffer di dati e quindi chiama di nuovo il metodo **BeginReceive** fino al completamento dei dati inviati dal client. Quando l'intero messaggio è stato letto dal client, la stringa viene visualizzata nella console e il socket server che gestisce la connessione al client viene chiuso.  
  
 L'esempio seguente implementa il metodo `ReadCallback`. Si presuppone che la classe `StateObject` sia definita.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Uso di un socket server sincrono](using-a-synchronous-server-socket.md)
- [Esempio di socket server asincrono](asynchronous-server-socket-example.md)
- [Threading](../../standard/threading/index.md)
- [Attesa con socket](listening-with-sockets.md)
