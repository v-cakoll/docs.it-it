---
title: Uso di socket client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- receiving data, sockets
- Socket class, client sockets
- protocols, sockets
- Internet, sockets
- sockets, client sockets
- client sockets
ms.assetid: 81de9f59-8177-4d98-b25d-43fc32a98383
ms.openlocfilehash: fe2ad55c3f60347369c0e92bc834d81d98f3870e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "71046948"
---
# <a name="using-client-sockets"></a>Uso di socket client
Prima di poter avviare una conversazione tramite un <xref:System.Net.Sockets.Socket>, è necessario creare una pipe di dati tra l'applicazione e il dispositivo remoto. Anche se esistono altre famiglie di indirizzi di rete e protocolli, questo esempio mostra come creare una connessione TCP/IP a un servizio remoto.  
  
 TCP/IP usa un indirizzo di rete e un numero di porta del servizio per identificare in modo univoco un servizio. L'indirizzo di rete identifica un determinato dispositivo in rete. Il numero di porta identifica il servizio specifico in tale dispositivo a cui connettersi. La combinazione di indirizzo di rete e porta del servizio viene denominata endpoint, rappresentato in .NET Framework dalla classe <xref:System.Net.EndPoint>. Viene definito un discendente di **EndPoint** per ogni famiglia di indirizzi supportata. Per la famiglia di indirizzi IP, la classe è <xref:System.Net.IPEndPoint>.  
  
 La classe <xref:System.Net.Dns> fornisce servizi DNS alle applicazioni che usano i servizi TCP/IP Internet. Il metodo <xref:System.Net.Dns.Resolve%2A> richiede a un server DNS di eseguire il mapping di un nome descrittivo di dominio (ad esempio "host.contoso.com") a un indirizzo Internet numerico (ad esempio 192.168.1.1). **Resolve** restituisce una voce <xref:System.Net.IPHostEntry> che contiene un elenco di indirizzi e alias per il nome richiesto. Nella maggior parte dei casi, è possibile usare il primo indirizzo restituito nella matrice <xref:System.Net.IPHostEntry.AddressList%2A>. Il codice seguente ottiene un <xref:System.Net.IPAddress> contenente l'indirizzo IP del server host.contoso.com.  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 IANA (Internet Assigned Numbers Authority) definisce i numeri di porta per i servizi comuni. Per altre informazioni, vedere [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro dei numeri di porta per nomi di servizio e protocolli di trasporto). Altri servizi possono avere numeri di porta registrati nell'intervallo da 1024 a 65.535. Il codice seguente combina l'indirizzo IP per host.contoso.com con un numero di porta per creare un endpoint remoto per una connessione.  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 Dopo aver determinato l'indirizzo del dispositivo remoto e aver scelto la porta da usare per la connessione, l'applicazione può tentare di stabilire una connessione con il dispositivo remoto. L'esempio seguente usa un **IPEndPoint** esistente per connettersi a un dispositivo remoto e intercetta le eventuali eccezioni generate.  
  
```vb  
Try  
    s.Connect(ipe)  
Catch ae As ArgumentNullException  
    Console.WriteLine("ArgumentNullException : {0}", _  
        ae.ToString())  
Catch se As SocketException  
    Console.WriteLine("SocketException : {0}", se.ToString())  
Catch e As Exception  
    Console.WriteLine("Unexpected exception : {0}", e.ToString())  
End Try  
```  
  
```csharp  
try {  
    s.Connect(ipe);  
} catch(ArgumentNullException ae) {  
    Console.WriteLine("ArgumentNullException : {0}", ae.ToString());  
} catch(SocketException se) {  
    Console.WriteLine("SocketException : {0}", se.ToString());  
} catch(Exception e) {  
    Console.WriteLine("Unexpected exception : {0}", e.ToString());  
}  
```  
  
## <a name="see-also"></a>Vedere anche

- [Uso di un socket client sincrono](using-a-synchronous-client-socket.md)
- [Uso di un socket client asincrono](using-an-asynchronous-client-socket.md)
- [Procedura: Creare un socket](how-to-create-a-socket.md)
- [socket](sockets.md)
