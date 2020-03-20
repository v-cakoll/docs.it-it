---
title: attesa con socket
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
ms.openlocfilehash: cf8316ede6888b99a8b0c87cfa3426b33be18b7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180732"
---
# <a name="listening-with-sockets"></a><span data-ttu-id="361e7-102">attesa con socket</span><span class="sxs-lookup"><span data-stu-id="361e7-102">Listening with Sockets</span></span>
<span data-ttu-id="361e7-103">I socket listener o server aprono una porta in rete e quindi attendono che un client si connetta alla porta.</span><span class="sxs-lookup"><span data-stu-id="361e7-103">Listener or server sockets open a port on the network and then wait for a client to connect to that port.</span></span> <span data-ttu-id="361e7-104">Anche se esistono altre famiglie di indirizzi di rete e protocolli, questo esempio mostra come creare un servizio remoto per una rete TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="361e7-104">Although other network address families and protocols exist, this example shows how to create remote service for a TCP/IP network.</span></span>  
  
 <span data-ttu-id="361e7-105">L'indirizzo univoco di un servizio TCP/IP è definito dalla combinazione dell'indirizzo IP dell'host con il numero di porta del servizio, in modo da creare un endpoint per il servizio.</span><span class="sxs-lookup"><span data-stu-id="361e7-105">The unique address of a TCP/IP service is defined by combining the IP address of the host with the port number of the service to create an endpoint for the service.</span></span> <span data-ttu-id="361e7-106">La classe <xref:System.Net.Dns> fornisce i metodi che restituiscono informazioni sugli indirizzi di rete supportati dal dispositivo di rete locale.</span><span class="sxs-lookup"><span data-stu-id="361e7-106">The <xref:System.Net.Dns> class provides methods that return information about the network addresses supported by the local network device.</span></span> <span data-ttu-id="361e7-107">Quando il dispositivo di rete locale ha più di un indirizzo di rete o se il sistema locale supporta più di un dispositivo di rete, la classe **Dns** restituisce informazioni su tutti gli indirizzi di rete e l'applicazione deve scegliere quello appropriato per il servizio.</span><span class="sxs-lookup"><span data-stu-id="361e7-107">When the local network device has more than one network address, or if the local system supports more than one network device, the **Dns** class returns information about all network addresses, and the application must choose the proper address for the service.</span></span> <span data-ttu-id="361e7-108">L'Internet Assigned Numbers Authority (Iana) definisce i numeri di porta per i servizi comuni; Per ulteriori informazioni, vedere [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/port-numbers).</span><span class="sxs-lookup"><span data-stu-id="361e7-108">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services; for more information, see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="361e7-109">Altri servizi possono avere numeri di porta registrati nell'intervallo da 1024 a 65.535.</span><span class="sxs-lookup"><span data-stu-id="361e7-109">Other services can have registered port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="361e7-110">L'esempio seguente crea un oggetto <xref:System.Net.IPEndPoint> per un server combinando il primo indirizzo IP restituito da **Dns** per l'host computer con un numero di porta scelto dall'intervallo di numeri di porta registrato.</span><span class="sxs-lookup"><span data-stu-id="361e7-110">The following example creates an <xref:System.Net.IPEndPoint> for a server by combining the first IP address returned by **Dns** for the host computer with a port number chosen from the registered port numbers range.</span></span>  
  
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
  
 <span data-ttu-id="361e7-111">Una volta determinato l'endpoint locale, <xref:System.Net.Sockets.Socket> deve essere associato all'endpoint tramite il metodo <xref:System.Net.Sockets.Socket.Bind%2A> e impostato in modo da essere in ascolto nell'endpoint tramite il metodo <xref:System.Net.Sockets.Socket.Listen%2A>.</span><span class="sxs-lookup"><span data-stu-id="361e7-111">After the local endpoint is determined, the <xref:System.Net.Sockets.Socket> must be associated with that endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> method and set to listen on the endpoint using the <xref:System.Net.Sockets.Socket.Listen%2A> method.</span></span> <span data-ttu-id="361e7-112">**Bind** genera un'eccezione se la combinazione specifica di indirizzo e porta è già in uso.</span><span class="sxs-lookup"><span data-stu-id="361e7-112">**Bind** throws an exception if the specific address and port combination is already in use.</span></span> <span data-ttu-id="361e7-113">L'esempio seguente mostra l'associazione di un oggetto **Socket** a un oggetto **IPEndPoint**.</span><span class="sxs-lookup"><span data-stu-id="361e7-113">The following example demonstrates associating a **Socket** with an **IPEndPoint**.</span></span>  
  
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
  
 <span data-ttu-id="361e7-114">Il metodo **Listen** accetta un singolo parametro che specifica il numero di connessioni in sospeso consentito in **Socket** prima che venga restituito un errore di server occupato al client che si connette.</span><span class="sxs-lookup"><span data-stu-id="361e7-114">The **Listen** method takes a single parameter that specifies how many pending connections to the **Socket** are allowed before a server busy error is returned to the connecting client.</span></span> <span data-ttu-id="361e7-115">In questo caso, vengono inseriti fino a 100 client nella coda di connessione prima che venga restituita una risposta di server occupato al client numero 101.</span><span class="sxs-lookup"><span data-stu-id="361e7-115">In this case, up to 100 clients are placed in the connection queue before a server busy response is returned to client number 101.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="361e7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="361e7-116">See also</span></span>

- [<span data-ttu-id="361e7-117">Uso di un socket server sincrono</span><span class="sxs-lookup"><span data-stu-id="361e7-117">Using a Synchronous Server Socket</span></span>](using-a-synchronous-server-socket.md)
- [<span data-ttu-id="361e7-118">Uso di un socket server asincrono</span><span class="sxs-lookup"><span data-stu-id="361e7-118">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="361e7-119">Uso di socket client</span><span class="sxs-lookup"><span data-stu-id="361e7-119">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="361e7-120">Procedura: Creare un socket</span><span class="sxs-lookup"><span data-stu-id="361e7-120">How to: Create a Socket</span></span>](how-to-create-a-socket.md)
- [<span data-ttu-id="361e7-121">socket</span><span class="sxs-lookup"><span data-stu-id="361e7-121">Sockets</span></span>](sockets.md)
