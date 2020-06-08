---
title: TCP-UDP
description: Informazioni sul modo in cui le classi TcpClient, TcpListener e UdpClient gestiscono i servizi TCP e UDP, che si occupano dei dettagli del trasferimento dei dati nel .NET Framework.
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
ms.openlocfilehash: ae6d2f9ced2235aa1b9b8fada8064d7e4be970a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502093"
---
# <a name="tcp-udp"></a>TCP-UDP
Le applicazioni possono usare servizi TCP (Transmission Control Protocol) e UDP (User Datagram Protocol) con le classi <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> e <xref:System.Net.Sockets.UdpClient>. Queste classi protocollo sono basate sulla classe <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> e possono gestire i dettagli del trasferimento dei dati.  
  
 Le classi protocollo usano i metodi sincroni della classe **Socket** per fornire un accesso semplice e diretto ai servizi di rete senza il sovraccarico di gestione delle informazioni sullo stato o senza conoscere i dettagli di configurazione per socket specifici del protocollo. Per usare i metodi **Socket** asincroni, è possibile usare i metodi asincroni forniti dalla classe <xref:System.Net.Sockets.NetworkStream>. Per accedere alle funzionalità della classe **Socket** non esposte dalle classi protocollo, è necessario usare la classe **Socket**.  
  
 **TcpClient** e **TcpListener** rappresentano la rete tramite la classe **NetworkStream**. Si usa il metodo <xref:System.Net.Sockets.TcpClient.GetStream%2A> per restituire il flusso di rete e quindi si chiamano i metodi <xref:System.Net.Sockets.NetworkStream.Read%2A> e <xref:System.Net.Sockets.NetworkStream.Write%2A> del flusso. Il socket sottostante delle classi protocollo non è di proprietà di **NetworkStream**, quindi la sua chiusura non influisce sul socket.  
  
 La classe **UdpClient** usa una matrice di byte per contenere il datagramma UDP. Si usa il metodo <xref:System.Net.Sockets.UdpClient.Send%2A> per inviare i dati alla rete e il metodo <xref:System.Net.Sockets.UdpClient.Receive%2A> per ricevere un datagramma in ingresso.  
  
## <a name="see-also"></a>Vedere anche

- [Uso dei servizi TCP](using-tcp-services.md)
- [Uso dei servizi UDP](using-udp-services.md)
- [Uso di flussi nella rete](using-streams-on-the-network.md)
- [Uso di un socket server asincrono](using-an-asynchronous-server-socket.md)
- [Uso di un socket client asincrono](using-an-asynchronous-client-socket.md)
- [Uso di protocolli applicativi](using-application-protocols.md)
