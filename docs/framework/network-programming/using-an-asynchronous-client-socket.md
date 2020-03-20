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
# <a name="using-an-asynchronous-client-socket"></a>Uso di un socket client asincrono
Un socket client asincrono non sospende l'applicazione durante l'attesa del completamento delle operazioni di rete. Usa invece il modello di programmazione asincrona standard di .NET Framework per elaborare la connessione di rete su un singolo thread mentre l'esecuzione dell'applicazione continua sul thread originale. I socket asincroni sono appropriati per le applicazioni che fanno un uso massiccio della rete o che non possano attendere il completamento delle operazioni di rete prima di continuare.  
  
 La classe <xref:System.Net.Sockets.Socket> segue il modello di denominazione di .NET Framework per i metodi asincroni. Ad esempio, il metodo sincrono <xref:System.Net.Sockets.Socket.Receive%2A> corrisponde ai metodi asincroni <xref:System.Net.Sockets.Socket.BeginReceive%2A> e <xref:System.Net.Sockets.Socket.EndReceive%2A>.  
  
 Le operazioni asincrone richiedono un metodo di callback per restituire il risultato dell'operazione. Se non è necessario che l'applicazione conosca il risultato, non sarà necessario alcun metodo di callback. L'esempio di codice in questa sezione illustra l'uso di un metodo per avviare la connessione a un dispositivo di rete e un metodo di callback per completare la connessione, un metodo per avviare l'invio dei dati e un metodo di callback per completare l'invio, un metodo per avviare la ricezione di dati e un metodo di callback per terminare la ricezione di dati.  
  
 I socket asincroni usano più thread dal pool di thread di sistema per elaborare le connessioni di rete. Un thread è responsabile dell'avvio dell'invio o della ricezione dei dati. Gli altri thread completano la connessione al dispositivo di rete e inviano o ricevono i dati. Negli esempi seguenti, le istanze della classe <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> vengono usate per sospendere l'esecuzione del thread principale e segnalare quando l'esecuzione può continuare.  
  
 Nell'esempio seguente, per connettere un socket asincrono a un dispositivo di rete, il metodo `Connect` inizializza un **Socket** e quindi chiama il metodo <xref:System.Net.Sockets.Socket.Connect%2A?displayProperty=nameWithType>, passando un endpoint remoto che rappresenta il dispositivo di rete, il metodo di callback per la connessione e un oggetto di stato (il **Socket** client), che viene usato per passare le informazioni sullo stato tra chiamate asincrone. L'esempio implementa il metodo `Connect` per connettere il **Socket** specificato all'endpoint specificato. Si presuppone l'esistenza di un **ManualResetEvent** globale denominato `connectDone`.  
  
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
  
 Il metodo di callback per la connessione `ConnectCallback` implementa il delegato <xref:System.AsyncCallback>. Si connette al dispositivo remoto quando è disponibile e segnala al thread dell'applicazione che la connessione è stata completata, impostando **ManualResetEvent su ** `connectDone`. Il codice seguente implementa il metodo `ConnectCallback`.  
  
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
  
 Il metodo `Send` dell'esempio codifica i dati stringa specificati in formato ASCII e li invia in modo asincrono al dispositivo di rete rappresentato dal socket specificato. L'esempio seguente implementa il metodo `Send`.  
  
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
  
 Il metodo di callback per l'invio `SendCallback` implementa il delegato <xref:System.AsyncCallback> e invia i dati quando il dispositivo di rete è pronto a ricevere. L'esempio seguente mostra l'implementazione del metodo `SendCallback`. Si presuppone l'esistenza di un **ManualResetEvent** globale denominato `sendDone`.  
  
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
  
 Per la lettura dei dati da un socket client è necessario un oggetto stato che passa i valori tra chiamate asincrone. La classe seguente è un esempio di oggetto di stato per la ricezione di dati da un socket client. Contiene un campo per il socket client, un buffer per i dati ricevuti e un <xref:System.Text.StringBuilder> per contenere la stringa di dati in ingresso. Il posizionamento di questi campi nell'oggetto stato consente di mantenerne i valori tra più chiamate per leggere i dati dal socket client.  
  
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
  
 Il metodo `Receive` dell'esempio imposta l'oggetto di stato e quindi chiama il metodo **BeginReceive** per leggere i dati dal socket client in modo asincrono. L'esempio seguente implementa il metodo `Receive`.  
  
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
  
 Il metodo di callback per la ricezione `ReceiveCallback` implementa il delegato **AsyncCallback** e riceve i dati dal dispositivo di rete, quindi crea una stringa di messaggio. Questo metodo legge uno o più byte di dati dalla rete nel buffer di dati e quindi chiama di nuovo il metodo **BeginReceive** del metodo finché al completamento dei dati inviati dal client. Una volta letti tutti i dati dal client, `ReceiveCallback` segnala al thread dell'applicazione che i dati sono completi impostando **ManualResetEvent su ** `sendDone`.  
  
 Il codice di esempio seguente implementa il metodo `ReceiveCallback`. Si presuppone l'esistenza di una stringa globale denominata `response` che contiene la stringa ricevuta e di un **ManualResetEvent** globale denominato `receiveDone`. Il server deve chiudere correttamente il socket client per terminare la sessione di rete.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Uso di un socket client sincrono](using-a-synchronous-client-socket.md)
- [Attesa con socket](listening-with-sockets.md)
- [Esempio di socket client asincrono](asynchronous-client-socket-example.md)
