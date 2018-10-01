---
title: socket
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ce7ded81ad23c2df55afa9360435e8391fea7a63
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47176825"
---
# <a name="sockets"></a><span data-ttu-id="6325e-102">socket</span><span class="sxs-lookup"><span data-stu-id="6325e-102">Sockets</span></span>
<span data-ttu-id="6325e-103">Lo spazio dei nomi <xref:System.Net.Sockets> contiene un'implementazione gestita dell'interfaccia Windows Sockets.</span><span class="sxs-lookup"><span data-stu-id="6325e-103">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="6325e-104">Tutte le altre classi di accesso alla rete nello spazio dei nomi <xref:System.Net> si basano su questa implementazione dei socket.</span><span class="sxs-lookup"><span data-stu-id="6325e-104">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="6325e-105">La classe <xref:System.Net.Sockets.Socket> .NET Framework è una versione per codice gestito dei servizi socket forniti dall'API di Winsock32.</span><span class="sxs-lookup"><span data-stu-id="6325e-105">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="6325e-106">Nella maggior parte dei casi, i metodi della classe **Socket** eseguono semplicemente il marshalling dei dati nelle rispettive controparti Win32 native e gestiscono gli eventuali controlli di sicurezza necessari.</span><span class="sxs-lookup"><span data-stu-id="6325e-106">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="6325e-107">La classe **Socket** supporta due modalità di base, sincrona e asincrona.</span><span class="sxs-lookup"><span data-stu-id="6325e-107">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="6325e-108">In modalità sincrona, le chiamate a funzioni che eseguono operazioni di rete (ad esempio <xref:System.Net.Sockets.Socket.Send%2A> e <xref:System.Net.Sockets.Socket.Receive%2A>) attendono il completamento dell'operazione prima di restituire il controllo al programma chiamante.</span><span class="sxs-lookup"><span data-stu-id="6325e-108">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="6325e-109">In modalità asincrona, queste chiamate restituiscono il controllo immediatamente.</span><span class="sxs-lookup"><span data-stu-id="6325e-109">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6325e-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6325e-110">See Also</span></span>  
 [<span data-ttu-id="6325e-111">Procedura: Creare un socket</span><span class="sxs-lookup"><span data-stu-id="6325e-111">How to: Create a Socket</span></span>](../../../docs/framework/network-programming/how-to-create-a-socket.md)  
    
 [<span data-ttu-id="6325e-112">Uso di protocolli applicativi</span><span class="sxs-lookup"><span data-stu-id="6325e-112">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
