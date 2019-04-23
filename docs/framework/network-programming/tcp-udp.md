---
title: TCP-UDP
ms.date: 03/30/2017
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
ms.openlocfilehash: e074a487c39dfaf1c4704f9dadf7ed8e430fb630
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172549"
---
# <a name="tcp-udp"></a>TCP-UDP
Le applicazioni possono usare servizi TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) con le classi <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> e <xref:System.Net.Sockets.UdpClient>. Queste classi protocollo sono basate sulla classe <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> e possono gestire i dettagli del trasferimento dei dati.  
  
 Le classi protocollo usano i metodi sincroni della classe **Socket** per fornire un accesso semplice e diretto ai servizi di rete senza il sovraccarico di gestione delle informazioni sullo stato o senza conoscere i dettagli di configurazione per socket specifici del protocollo. Per usare i metodi **Socket** asincroni, è possibile usare i metodi asincroni forniti dalla classe <xref:System.Net.Sockets.NetworkStream>. Per accedere alle funzionalità della classe **Socket** non esposte dalle classi protocollo, è necessario usare la classe **Socket**.  
  
 **TcpClient** e **TcpListener** rappresentano la rete tramite la classe **NetworkStream**. Si usa il metodo <xref:System.Net.Sockets.TcpClient.GetStream%2A> per restituire il flusso di rete e quindi si chiamano i metodi <xref:System.Net.Sockets.NetworkStream.Read%2A> e <xref:System.Net.Sockets.NetworkStream.Write%2A> del flusso. Il socket sottostante delle classi protocollo non è di proprietà di **NetworkStream**, quindi la sua chiusura non influisce sul socket.  
  
 La classe **UdpClient** usa una matrice di byte per contenere il datagramma UDP. Si usa il metodo <xref:System.Net.Sockets.UdpClient.Send%2A> per inviare i dati alla rete e il metodo <xref:System.Net.Sockets.UdpClient.Receive%2A> per ricevere un datagramma in ingresso.  
  
## <a name="see-also"></a>Vedere anche

- [Uso dei servizi TCP](../../../docs/framework/network-programming/using-tcp-services.md)
- [Uso dei servizi UDP](../../../docs/framework/network-programming/using-udp-services.md)
- [Uso di flussi nella rete](../../../docs/framework/network-programming/using-streams-on-the-network.md)
- [Uso di un socket server asincrono](../../../docs/framework/network-programming/using-an-asynchronous-server-socket.md)
- [Uso di un socket client asincrono](../../../docs/framework/network-programming/using-an-asynchronous-client-socket.md)
- [Uso di protocolli applicativi](../../../docs/framework/network-programming/using-application-protocols.md)
