---
title: TCP-UDP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- protocols, TCP/UDP
- network resources, TCP/UDP
- sending data, TCP/UDP
- TCP/UDP
- TcpClient class, about TcpClient class
- application protocols, TCP/UDP
- receiving data, TCP/UDP
- TcpListener class, about TcpListener class
- Socket class, about Socket class
- UDP
- data requests, TCP/UDP
- requesting data from Internet, TCP/UDP
- Internet, TCP/UDP
ms.assetid: df29b4b0-49e8-4923-82b9-13150dfc40f5
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 04a3bb1c7499a60175aaaa9715e780ea5ddceb31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="tcp-udp"></a><span data-ttu-id="c16c4-102">TCP-UDP</span><span class="sxs-lookup"><span data-stu-id="c16c4-102">TCP-UDP</span></span>
<span data-ttu-id="c16c4-103">Le applicazioni possono usare servizi TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) con le classi <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> e <xref:System.Net.Sockets.UdpClient>.</span><span class="sxs-lookup"><span data-stu-id="c16c4-103">Applications can use Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) services with the <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes.</span></span> <span data-ttu-id="c16c4-104">Queste classi protocollo sono basate sulla classe <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> e possono gestire i dettagli del trasferimento dei dati.</span><span class="sxs-lookup"><span data-stu-id="c16c4-104">These protocol classes are built on top of the <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> class and take care of the details of transferring data.</span></span>  
  
 <span data-ttu-id="c16c4-105">Le classi protocollo usano i metodi sincroni della classe **Socket** per fornire un accesso semplice e diretto ai servizi di rete senza il sovraccarico di gestione delle informazioni sullo stato o senza conoscere i dettagli di configurazione per socket specifici del protocollo.</span><span class="sxs-lookup"><span data-stu-id="c16c4-105">The protocol classes use the synchronous methods of the **Socket** class to provide simple and straightforward access to network services without the overhead of maintaining state information or knowing the details of setting up protocol-specific sockets.</span></span> <span data-ttu-id="c16c4-106">Per usare i metodi **Socket** asincroni, è possibile usare i metodi asincroni forniti dalla classe <xref:System.Net.Sockets.NetworkStream>.</span><span class="sxs-lookup"><span data-stu-id="c16c4-106">To use asynchronous **Socket** methods, you can use the asynchronous methods supplied by the <xref:System.Net.Sockets.NetworkStream> class.</span></span> <span data-ttu-id="c16c4-107">Per accedere alle funzionalità della classe **Socket** non esposte dalle classi protocollo, è necessario usare la classe **Socket**.</span><span class="sxs-lookup"><span data-stu-id="c16c4-107">To access features of the **Socket** class not exposed by the protocol classes, you must use the **Socket** class.</span></span>  
  
 <span data-ttu-id="c16c4-108">**TcpClient** e **TcpListener** rappresentano la rete tramite la classe **NetworkStream**.</span><span class="sxs-lookup"><span data-stu-id="c16c4-108">**TcpClient** and **TcpListener** represent the network using the **NetworkStream** class.</span></span> <span data-ttu-id="c16c4-109">Si usa il metodo <xref:System.Net.Sockets.TcpClient.GetStream%2A> per restituire il flusso di rete e quindi si chiamano i metodi <xref:System.Net.Sockets.NetworkStream.Read%2A> e <xref:System.Net.Sockets.NetworkStream.Write%2A> del flusso.</span><span class="sxs-lookup"><span data-stu-id="c16c4-109">You use the <xref:System.Net.Sockets.TcpClient.GetStream%2A> method to return the network stream, and then call the stream's <xref:System.Net.Sockets.NetworkStream.Read%2A> and <xref:System.Net.Sockets.NetworkStream.Write%2A> methods.</span></span> <span data-ttu-id="c16c4-110">Il socket sottostante delle classi protocollo non è di proprietà di **NetworkStream**, quindi la sua chiusura non influisce sul socket.</span><span class="sxs-lookup"><span data-stu-id="c16c4-110">The **NetworkStream** does not own the protocol classes' underlying socket, so closing it does not affect the socket.</span></span>  
  
 <span data-ttu-id="c16c4-111">La classe **UdpClient** usa una matrice di byte per contenere il datagramma UDP.</span><span class="sxs-lookup"><span data-stu-id="c16c4-111">The **UdpClient** class uses an array of bytes to hold the UDP datagram.</span></span> <span data-ttu-id="c16c4-112">Si usa il metodo <xref:System.Net.Sockets.UdpClient.Send%2A> per inviare i dati alla rete e il metodo <xref:System.Net.Sockets.UdpClient.Receive%2A> per ricevere un datagramma in ingresso.</span><span class="sxs-lookup"><span data-stu-id="c16c4-112">You use the <xref:System.Net.Sockets.UdpClient.Send%2A> method to send the data to the network and the <xref:System.Net.Sockets.UdpClient.Receive%2A> method to receive an incoming datagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16c4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c16c4-113">See Also</span></span>  
 [<span data-ttu-id="c16c4-114">Utilizzo dei servizi TCP</span><span class="sxs-lookup"><span data-stu-id="c16c4-114">Using TCP Services</span></span>](../../../docs/framework/network-programming/using-tcp-services.md)  
 [<span data-ttu-id="c16c4-115">Utilizzo dei servizi UDP</span><span class="sxs-lookup"><span data-stu-id="c16c4-115">Using UDP Services</span></span>](../../../docs/framework/network-programming/using-udp-services.md)  
 [<span data-ttu-id="c16c4-116">L'uso di flussi di rete</span><span class="sxs-lookup"><span data-stu-id="c16c4-116">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="c16c4-117">Utilizzo di un Socket Server asincroni</span><span class="sxs-lookup"><span data-stu-id="c16c4-117">Using an Asynchronous Server Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)  
 [<span data-ttu-id="c16c4-118">Utilizzo di un Socket Client asincrono</span><span class="sxs-lookup"><span data-stu-id="c16c4-118">Using an Asynchronous Client Socket</span></span>](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)  
 [<span data-ttu-id="c16c4-119">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="c16c4-119">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
