---
title: Uso di un socket server sincrono
description: Questo esempio mostra un socket server sincrono in .NET Framework, che sospende un'applicazione fino a quando non viene ricevuta una richiesta di connessione sul socket.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: 9e7d32595f554b32ecc72bbb1f1a469ad5935467
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502054"
---
# <a name="using-a-synchronous-server-socket"></a>Uso di un socket server sincrono
I socket server sincroni sospendono l'esecuzione dell'applicazione fino a quando non viene ricevuta una richiesta di connessione sul socket. I socket server sincroni non sono adatti per le applicazioni che fanno un uso massiccio della rete per le loro operazioni, ma possono essere appropriati per applicazioni di rete semplici.  
  
 Dopo aver impostato un <xref:System.Net.Sockets.Socket> per l'ascolto su un endpoint tramite i metodi <xref:System.Net.Sockets.Socket.Bind%2A> e <xref:System.Net.Sockets.Socket.Listen%2A>, il socket è pronto per accettare le richieste di connessione in ingresso tramite il metodo <xref:System.Net.Sockets.Socket.Accept%2A>. L'applicazione viene sospesa fino a quando non viene ricevuta una richiesta di connessione quando viene chiamato il metodo **Accept**.  
  
 Quando viene ricevuta una richiesta di connessione, **Accept** restituisce una nuova istanza di **Socket** associata al client che si connette. L'esempio seguente legge i dati dal client, li visualizza nella console e li restituisce al client. Il **socket** non specifica alcun protocollo di messaggistica, quindi la stringa " \<EOF> " contrassegna la fine dei dati del messaggio. Si presuppone che un **Socket** denominato `listener` sia stato inizializzato e associato a un endpoint.  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un socket server asincrono](using-an-asynchronous-server-socket.md)
- [Esempio di socket server sincrono](synchronous-server-socket-example.md)
- [Attesa con socket](listening-with-sockets.md)
