---
title: Uso di un socket client sincrono
description: Questo esempio mostra un socket client sincrono nella .NET Framework, che sospende il programma dell'applicazione durante il completamento dell'operazione di rete.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
ms.openlocfilehash: ef682af33c10cf06ffc398c22e4a7dc1adf8290e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502067"
---
# <a name="using-a-synchronous-client-socket"></a>Uso di un socket client sincrono
Un socket client sincrono sospende il programma dell'applicazione in attesa del completamento dell'operazione di rete. I socket sincroni non sono adatti per le applicazioni che fanno un uso massiccio della rete per le loro operazioni, ma consentono di abilitare l'accesso semplice ai servizi di rete per altre applicazioni.  
  
 Per l'invio di dati, passare una matrice di byte a uno dei metodi di invio dei dati della classe <xref:System.Net.Sockets.Socket> (<xref:System.Net.Sockets.Socket.Send%2A> e <xref:System.Net.Sockets.Socket.SendTo%2A>). L'esempio seguente codifica una stringa in un buffer di matrice di byte usando la proprietà <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> e quindi trasmette il buffer al dispositivo di rete usando il metodo **Send**. Il metodo **Send** restituisce il numero di byte inviati al dispositivo di rete.  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 Il metodo **Send** rimuove i byte dal buffer e li accoda con l'interfaccia di rete per l'invio al dispositivo di rete. L'interfaccia di rete potrebbe non inviare i dati immediatamente, ma li invierà alla fine, a condizione che la connessione venga chiusa normalmente con il metodo <xref:System.Net.Sockets.Socket.Shutdown%2A>.  
  
 Per ricevere dati da un dispositivo di rete, passare un buffer a uno dei metodi per la ricezione dei dati della classe **Socket** (<xref:System.Net.Sockets.Socket.Receive%2A> e <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>). I socket sincroni sospenderanno l'applicazione fino a quando i byte vengono ricevuti dalla rete o fino alla chiusura del socket. L'esempio seguente riceve dati dalla rete e successivamente li visualizza nella console. L'esempio presuppone che i dati provenienti dalla rete siano testo con codifica ASCII. Il metodo **Receive** restituisce il numero di byte ricevuti dalla rete.  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 Quando il socket non è più necessario, è necessario rilasciarlo chiamando il metodo <xref:System.Net.Sockets.Socket.Shutdown%2A> e poi il metodo **Close**. L'esempio seguente illustra come rilasciare un **Socket**. L'enumerazione <xref:System.Net.Sockets.SocketShutdown> definisce le costanti che indicano se il socket deve essere chiuso per l'invio, per la ricezione o per entrambi.  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un socket client asincrono](using-an-asynchronous-client-socket.md)
- [Attesa con socket](listening-with-sockets.md)
- [Esempio di socket client sincrono](synchronous-client-socket-example.md)
