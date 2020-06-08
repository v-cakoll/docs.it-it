---
title: attesa con socket
description: Informazioni su come creare un servizio remoto, in cui un socket del server apre una porta sulla rete e attende che un client si connetta a tale porta.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- sockets, listening with sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- protocols, sockets
- listening with sockets
- Internet, sockets
ms.assetid: 40e426cc-13db-4371-95eb-f7388bd23ebf
ms.openlocfilehash: 0b6de67772bae397373e307ec02ce69a71b0542e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502314"
---
# <a name="listening-with-sockets"></a>attesa con socket
I socket listener o server aprono una porta in rete e quindi attendono che un client si connetta alla porta. Anche se esistono altre famiglie di indirizzi di rete e protocolli, questo esempio mostra come creare un servizio remoto per una rete TCP/IP.  
  
 L'indirizzo univoco di un servizio TCP/IP è definito dalla combinazione dell'indirizzo IP dell'host con il numero di porta del servizio, in modo da creare un endpoint per il servizio. La classe <xref:System.Net.Dns> fornisce i metodi che restituiscono informazioni sugli indirizzi di rete supportati dal dispositivo di rete locale. Quando il dispositivo di rete locale ha più di un indirizzo di rete o se il sistema locale supporta più di un dispositivo di rete, la classe **Dns** restituisce informazioni su tutti gli indirizzi di rete e l'applicazione deve scegliere quello appropriato per il servizio. IANA (Internet Assigned Numbers Authority) definisce i numeri di porta per i servizi comuni; Per ulteriori informazioni, vedere il [Registro di sistema numero di porta del protocollo di trasporto e il nome del servizio](https://www.iana.org/assignments/port-numbers). Altri servizi possono avere numeri di porta registrati nell'intervallo da 1024 a 65.535.  
  
 L'esempio seguente crea un oggetto <xref:System.Net.IPEndPoint> per un server combinando il primo indirizzo IP restituito da **Dns** per l'host computer con un numero di porta scelto dall'intervallo di numeri di porta registrato.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.GetHostEntry(Dns.GetHostName());  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
```  
  
 Una volta determinato l'endpoint locale, <xref:System.Net.Sockets.Socket> deve essere associato all'endpoint tramite il metodo <xref:System.Net.Sockets.Socket.Bind%2A> e impostato in modo da essere in ascolto nell'endpoint tramite il metodo <xref:System.Net.Sockets.Socket.Listen%2A>. **Bind** genera un'eccezione se la combinazione specifica di indirizzo e porta è già in uso. L'esempio seguente mostra l'associazione di un oggetto **Socket** a un oggetto **IPEndPoint**.  
  
```vb  
Dim listener As New Socket(ipAddress.AddressFamily, _  
    SocketType.Stream, ProtocolType.Tcp)
listener.Bind(localEndPoint)  
listener.Listen(100)  
```  
  
```csharp  
Socket listener = new Socket(ipAddress.AddressFamily,
    SocketType.Stream, ProtocolType.Tcp);
listener.Bind(localEndPoint);  
listener.Listen(100);  
```  
  
 Il metodo **Listen** accetta un singolo parametro che specifica il numero di connessioni in sospeso consentito in **Socket** prima che venga restituito un errore di server occupato al client che si connette. In questo caso, vengono inseriti fino a 100 client nella coda di connessione prima che venga restituita una risposta di server occupato al client numero 101.  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un socket server sincrono](using-a-synchronous-server-socket.md)
- [Uso di un socket server asincrono](using-an-asynchronous-server-socket.md)
- [Uso di socket client](using-client-sockets.md)
- [Procedura: Creare un socket](how-to-create-a-socket.md)
- [Socket](sockets.md)
