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
# <a name="using-client-sockets"></a><span data-ttu-id="21e51-102">Uso di socket client</span><span class="sxs-lookup"><span data-stu-id="21e51-102">Using Client Sockets</span></span>
<span data-ttu-id="21e51-103">Prima di poter avviare una conversazione tramite un <xref:System.Net.Sockets.Socket>, è necessario creare una pipe di dati tra l'applicazione e il dispositivo remoto.</span><span class="sxs-lookup"><span data-stu-id="21e51-103">Before you can initiate a conversation through a <xref:System.Net.Sockets.Socket>, you must create a data pipe between your application and the remote device.</span></span> <span data-ttu-id="21e51-104">Anche se esistono altre famiglie di indirizzi di rete e protocolli, questo esempio mostra come creare una connessione TCP/IP a un servizio remoto.</span><span class="sxs-lookup"><span data-stu-id="21e51-104">Although other network address families and protocols exist, this example shows how to create a TCP/IP connection to a remote service.</span></span>  
  
 <span data-ttu-id="21e51-105">TCP/IP usa un indirizzo di rete e un numero di porta del servizio per identificare in modo univoco un servizio.</span><span class="sxs-lookup"><span data-stu-id="21e51-105">TCP/IP uses a network address and a service port number to uniquely identify a service.</span></span> <span data-ttu-id="21e51-106">L'indirizzo di rete identifica un determinato dispositivo in rete. Il numero di porta identifica il servizio specifico in tale dispositivo a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="21e51-106">The network address identifies a specific device on the network; the port number identifies the specific service on that device to connect to.</span></span> <span data-ttu-id="21e51-107">La combinazione di indirizzo di rete e porta del servizio viene denominata endpoint, rappresentato in .NET Framework dalla classe <xref:System.Net.EndPoint>.</span><span class="sxs-lookup"><span data-stu-id="21e51-107">The combination of network address and service port is called an endpoint, which is represented in the .NET Framework by the <xref:System.Net.EndPoint> class.</span></span> <span data-ttu-id="21e51-108">Viene definito un discendente di **EndPoint** per ogni famiglia di indirizzi supportata. Per la famiglia di indirizzi IP, la classe è <xref:System.Net.IPEndPoint>.</span><span class="sxs-lookup"><span data-stu-id="21e51-108">A descendant of **EndPoint** is defined for each supported address family; for the IP address family, the class is <xref:System.Net.IPEndPoint>.</span></span>  
  
 <span data-ttu-id="21e51-109">La classe <xref:System.Net.Dns> fornisce servizi DNS alle applicazioni che usano i servizi TCP/IP Internet.</span><span class="sxs-lookup"><span data-stu-id="21e51-109">The <xref:System.Net.Dns> class provides domain-name services to applications that use TCP/IP Internet services.</span></span> <span data-ttu-id="21e51-110">Il metodo <xref:System.Net.Dns.Resolve%2A> richiede a un server DNS di eseguire il mapping di un nome descrittivo di dominio (ad esempio "host.contoso.com") a un indirizzo Internet numerico (ad esempio 192.168.1.1).</span><span class="sxs-lookup"><span data-stu-id="21e51-110">The <xref:System.Net.Dns.Resolve%2A> method queries a DNS server to map a user-friendly domain name (such as "host.contoso.com") to a numeric Internet address (such as 192.168.1.1).</span></span> <span data-ttu-id="21e51-111">**Resolve** restituisce una voce <xref:System.Net.IPHostEntry> che contiene un elenco di indirizzi e alias per il nome richiesto.</span><span class="sxs-lookup"><span data-stu-id="21e51-111">**Resolve** returns an <xref:System.Net.IPHostEntry> that contains a list of addresses and aliases for the requested name.</span></span> <span data-ttu-id="21e51-112">Nella maggior parte dei casi, è possibile usare il primo indirizzo restituito nella matrice <xref:System.Net.IPHostEntry.AddressList%2A>.</span><span class="sxs-lookup"><span data-stu-id="21e51-112">In most cases, you can use the first address returned in the <xref:System.Net.IPHostEntry.AddressList%2A> array.</span></span> <span data-ttu-id="21e51-113">Il codice seguente ottiene un <xref:System.Net.IPAddress> contenente l'indirizzo IP del server host.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="21e51-113">The following code gets an <xref:System.Net.IPAddress> containing the IP address for the server host.contoso.com.</span></span>  
  
```vb  
Dim ipHostInfo As IPHostEntry = Dns.Resolve("host.contoso.com")  
Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
```  
  
```csharp  
IPHostEntry ipHostInfo = Dns.Resolve("host.contoso.com");  
IPAddress ipAddress = ipHostInfo.AddressList[0];  
```  
  
 <span data-ttu-id="21e51-114">IANA (Internet Assigned Numbers Authority) definisce i numeri di porta per i servizi comuni. Per altre informazioni, vedere [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro dei numeri di porta per nomi di servizio e protocolli di trasporto).</span><span class="sxs-lookup"><span data-stu-id="21e51-114">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="21e51-115">Altri servizi possono avere numeri di porta registrati nell'intervallo da 1024 a 65.535.</span><span class="sxs-lookup"><span data-stu-id="21e51-115">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span> <span data-ttu-id="21e51-116">Il codice seguente combina l'indirizzo IP per host.contoso.com con un numero di porta per creare un endpoint remoto per una connessione.</span><span class="sxs-lookup"><span data-stu-id="21e51-116">The following code combines the IP address for host.contoso.com with a port number to create a remote endpoint for a connection.</span></span>  
  
```vb  
Dim ipe As New IPEndPoint(ipAddress, 11000)  
```  
  
```csharp  
IPEndPoint ipe = new IPEndPoint(ipAddress,11000);  
```  
  
 <span data-ttu-id="21e51-117">Dopo aver determinato l'indirizzo del dispositivo remoto e aver scelto la porta da usare per la connessione, l'applicazione può tentare di stabilire una connessione con il dispositivo remoto.</span><span class="sxs-lookup"><span data-stu-id="21e51-117">After determining the address of the remote device and choosing a port to use for the connection, the application can attempt to establish a connection with the remote device.</span></span> <span data-ttu-id="21e51-118">L'esempio seguente usa un **IPEndPoint** esistente per connettersi a un dispositivo remoto e intercetta le eventuali eccezioni generate.</span><span class="sxs-lookup"><span data-stu-id="21e51-118">The following example uses an existing **IPEndPoint** to connect to a remote device and catches any exceptions that are thrown.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21e51-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21e51-119">See also</span></span>

- [<span data-ttu-id="21e51-120">Uso di un socket client sincrono</span><span class="sxs-lookup"><span data-stu-id="21e51-120">Using a Synchronous Client Socket</span></span>](using-a-synchronous-client-socket.md)
- [<span data-ttu-id="21e51-121">Uso di un socket client asincrono</span><span class="sxs-lookup"><span data-stu-id="21e51-121">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="21e51-122">Procedura: Creare un socket</span><span class="sxs-lookup"><span data-stu-id="21e51-122">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="21e51-123">socket</span><span class="sxs-lookup"><span data-stu-id="21e51-123">Sockets</span></span>](sockets.md)
