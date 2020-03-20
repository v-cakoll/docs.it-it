---
title: 'Procedura: Creare un socket'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- Networking
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- Socket class, creating sockets
- Network Resources
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- sockets, creating
ms.assetid: c64a049c-5981-43bc-a2dc-1851473589c7
ms.openlocfilehash: e71e7e235048361580c65bdb551919fe3038130b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180830"
---
# <a name="how-to-create-a-socket"></a><span data-ttu-id="baa67-102">Procedura: Creare un socket</span><span class="sxs-lookup"><span data-stu-id="baa67-102">How to: Create a Socket</span></span>
<span data-ttu-id="baa67-103">Prima di usare un socket per comunicare con dispositivi remoti, è necessario inizializzare il socket con informazioni su protocollo e indirizzo di rete.</span><span class="sxs-lookup"><span data-stu-id="baa67-103">Before you can use a socket to communicate with remote devices, the socket must be initialized with protocol and network address information.</span></span> <span data-ttu-id="baa67-104">Il costruttore per la classe <xref:System.Net.Sockets.Socket> dispone di parametri che specificano la famiglia di indirizzi, il tipo di socket e il tipo di protocollo usato per stabilire connessioni.</span><span class="sxs-lookup"><span data-stu-id="baa67-104">The constructor for the <xref:System.Net.Sockets.Socket> class has parameters that specify the address family, socket type, and protocol type that the socket uses to make connections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baa67-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="baa67-105">Example</span></span>  
 <span data-ttu-id="baa67-106">L'esempio seguente crea un socket che può essere usato per comunicare in una rete basata su TCP/IP, come Internet.</span><span class="sxs-lookup"><span data-stu-id="baa67-106">The following example creates a Socket that can be used to communicate on a TCP/IP-based network, such as the Internet.</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Stream, ProtocolType.Tcp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Stream, ProtocolType.Tcp)  
```  
  
 <span data-ttu-id="baa67-107">Per usare UDP anziché TCP, modificare il tipo di protocollo, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="baa67-107">To use UDP instead of TCP, change the protocol type, as in the following example:</span></span>  
  
```csharp  
Socket s = new Socket(AddressFamily.InterNetwork,
   SocketType.Dgram, ProtocolType.Udp);  
```  
  
```vb  
Dim s as New Socket(AddressFamily.InterNetwork, _  
   SocketType.Dgram, ProtocolType.Udp)  
```  
  
 <span data-ttu-id="baa67-108">L'enumerazione <xref:System.Net.Sockets.AddressFamily> specifica le famiglie di indirizzi standard usate dalla classe **Socket** per risolvere gli indirizzi di rete (ad esempio, il membro **AddressFamily.InterNetwork** specifica la famiglia di indirizzi IP versione 4).</span><span class="sxs-lookup"><span data-stu-id="baa67-108">The <xref:System.Net.Sockets.AddressFamily> enumeration specifies the standard address families used by the **Socket** class to resolve network addresses (for example, the **AddressFamily.InterNetwork** member specifies the IP version 4 address family).</span></span>  
  
 <span data-ttu-id="baa67-109">L'enumerazione <xref:System.Net.Sockets.SocketType> specifica il tipo di socket (ad esempio, il membro **SocketType.Stream** indica un socket standard per l'invio e la ricezione di dati con il controllo di flusso).</span><span class="sxs-lookup"><span data-stu-id="baa67-109">The <xref:System.Net.Sockets.SocketType> enumeration specifies the type of socket (for example, the **SocketType.Stream** member indicates a standard socket for sending and receiving data with flow control).</span></span>  
  
 <span data-ttu-id="baa67-110">L'enumerazione <xref:System.Net.Sockets.ProtocolType> specifica il protocollo di rete da usare durante la comunicazione sul **Socket** (ad esempio, **ProtocolType.Tcp** indica che il socket usa TCP e **ProtocolType.Udp** indica che il socket usa il protocollo UDP).</span><span class="sxs-lookup"><span data-stu-id="baa67-110">The <xref:System.Net.Sockets.ProtocolType> enumeration specifies the network protocol to use when communicating on the **Socket** (for example, **ProtocolType.Tcp** indicates that the socket uses TCP; **ProtocolType.Udp** indicates that the socket uses UDP).</span></span>  
  
 <span data-ttu-id="baa67-111">Dopo la creazione di un **Socket** è possibile avviare una connessione a un endpoint remoto o ricevere connessioni da dispositivi remoti.</span><span class="sxs-lookup"><span data-stu-id="baa67-111">After a **Socket** is created, it can either initiate a connection to a remote endpoint or receive connections from remote devices.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa67-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baa67-112">See also</span></span>

- [<span data-ttu-id="baa67-113">Uso di socket client</span><span class="sxs-lookup"><span data-stu-id="baa67-113">Using Client Sockets</span></span>](using-client-sockets.md)
- [<span data-ttu-id="baa67-114">Attesa con socket</span><span class="sxs-lookup"><span data-stu-id="baa67-114">Listening with Sockets</span></span>](listening-with-sockets.md)
