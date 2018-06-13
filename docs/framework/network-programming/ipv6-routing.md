---
title: Routing IPv6
ms.date: 03/30/2017
ms.assetid: c98731b4-b542-46a2-9947-1cea63c186b2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c3e2662eb444c70d2376a05e44ac84f472f27384
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397806"
---
# <a name="ipv6-routing"></a><span data-ttu-id="d3431-102">Routing IPv6</span><span class="sxs-lookup"><span data-stu-id="d3431-102">IPv6 Routing</span></span>
<span data-ttu-id="d3431-103">Uno dei vantaggi di IPv6 è che fornisce un meccanismo di routing flessibile.</span><span class="sxs-lookup"><span data-stu-id="d3431-103">A flexible routing mechanism is a benefit of IPv6.</span></span> <span data-ttu-id="d3431-104">A causa del modo in cui gli ID rete IPv4 venivano e vengono allocati, tabelle di routing di grandi dimensioni devono essere gestite dai router che si trovano sulle backbone Internet.</span><span class="sxs-lookup"><span data-stu-id="d3431-104">Due to the way in which IPv4 network IDs were and are allocated, large routing tables need to be maintained by the routers that are on the Internet backbones.</span></span> <span data-ttu-id="d3431-105">Questi router devono conoscere tutte le route per poter inoltrare i pacchetti potenzialmente indirizzati a qualsiasi nodo in Internet.</span><span class="sxs-lookup"><span data-stu-id="d3431-105">These routers must know all the routes in order to forward packets that are potentially directed to any node on the Internet.</span></span> <span data-ttu-id="d3431-106">Grazie a questa capacità di aggregare indirizzi, IPv6 consente un indirizzamento flessibile e riduce drasticamente le dimensioni delle tabelle di routing.</span><span class="sxs-lookup"><span data-stu-id="d3431-106">With its ability to aggregate addresses, IPv6 allows flexible addressing and drastically reduces the size of routing tables.</span></span> <span data-ttu-id="d3431-107">In questa nuova architettura di indirizzamento i router intermedi devono tenere traccia solo della parte locale della rete per poter inoltrare i messaggi nel modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3431-107">In this new addressing architecture, intermediate routers must keep track only of the local portion of their network in order to forward the messages appropriately.</span></span>  
  
## <a name="neighbor-discovery"></a><span data-ttu-id="d3431-108">Individuazione router adiacenti</span><span class="sxs-lookup"><span data-stu-id="d3431-108">Neighbor Discovery</span></span>  
 <span data-ttu-id="d3431-109">Ecco alcune delle funzionalità offerte da Individuazione router adiacenti:</span><span class="sxs-lookup"><span data-stu-id="d3431-109">Some of the features provided by Neighbor Discovery are:</span></span>  
  
-   <span data-ttu-id="d3431-110">Individuazione dei router.</span><span class="sxs-lookup"><span data-stu-id="d3431-110">Router discovery.</span></span> <span data-ttu-id="d3431-111">Permette agli host di identificare i router locali.</span><span class="sxs-lookup"><span data-stu-id="d3431-111">This allows hosts to identify local routers.</span></span>  
  
-   <span data-ttu-id="d3431-112">Risoluzione degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="d3431-112">Address resolution.</span></span> <span data-ttu-id="d3431-113">Permette ai nodi di risolvere un indirizzo a livello di collegamento per un indirizzo dell'hop successivo corrispondente (in sostituzione ad Address Resolution Protocol, ARP).</span><span class="sxs-lookup"><span data-stu-id="d3431-113">This allows nodes to resolve a link-layer address for a corresponding next-hop address (a replacement for Address Resolution Protocol [ARP]).</span></span>  
  
-   <span data-ttu-id="d3431-114">Configurazione automatica degli indirizzi.</span><span class="sxs-lookup"><span data-stu-id="d3431-114">Address auto-configuration.</span></span> <span data-ttu-id="d3431-115">Permette agli host di configurare automaticamente gli indirizzi locali rispetto al sito e gli indirizzi globali.</span><span class="sxs-lookup"><span data-stu-id="d3431-115">This allows hosts to automatically configure site-local and global addresses.</span></span>  
  
 <span data-ttu-id="d3431-116">Individuazione router adiacenti usa messaggi ICMPv6 (Internet Control Message Protocol for IPv6) che includono:</span><span class="sxs-lookup"><span data-stu-id="d3431-116">Neighbor Discovery uses Internet Control Message Protocol for IPv6 (ICMPv6) messages that include:</span></span>  
  
-   <span data-ttu-id="d3431-117">Router Advertisement.</span><span class="sxs-lookup"><span data-stu-id="d3431-117">Router advertisement.</span></span> <span data-ttu-id="d3431-118">Inviato da un router con una frequenza più o meno periodica o in risposta a un messaggio Router Solicitation.</span><span class="sxs-lookup"><span data-stu-id="d3431-118">Sent by a router on a pseudo-periodic basis or in response to a router solicitation.</span></span> <span data-ttu-id="d3431-119">I router IPv6 usano messaggi Router Advertisement per comunicare la propria disponibilità, i prefissi di indirizzo e altri parametri.</span><span class="sxs-lookup"><span data-stu-id="d3431-119">IPv6 routers use router advertisements to advertise their availability, address prefixes, and other parameters.</span></span>  
  
-   <span data-ttu-id="d3431-120">Router Solicitation.</span><span class="sxs-lookup"><span data-stu-id="d3431-120">Router solicitation.</span></span> <span data-ttu-id="d3431-121">Inviato da un host per richiedere che i router nel collegamento inviino immediatamente un messaggio Router Solicitation.</span><span class="sxs-lookup"><span data-stu-id="d3431-121">Sent by a host to request that routers on the link send a router advertisement immediately.</span></span>  
  
-   <span data-ttu-id="d3431-122">Neighbor Solicitation.</span><span class="sxs-lookup"><span data-stu-id="d3431-122">Neighbor solicitation.</span></span> <span data-ttu-id="d3431-123">Inviato dai nodi per la risoluzione degli indirizzi, il rilevamento di indirizzi duplicati o la verifica che un router adiacente sia ancora raggiungibile.</span><span class="sxs-lookup"><span data-stu-id="d3431-123">Sent by nodes for address resolution, duplicate address detection, or to verify that a neighbor is still reachable.</span></span>  
  
-   <span data-ttu-id="d3431-124">Neighbor Advertisement.</span><span class="sxs-lookup"><span data-stu-id="d3431-124">Neighbor advertisement.</span></span> <span data-ttu-id="d3431-125">Inviato dai nodi per rispondere a un messaggio Neighbor Solicitation o per comunicare ai router adiacenti una modifica nell'indirizzo a livello di collegamento.</span><span class="sxs-lookup"><span data-stu-id="d3431-125">Sent by nodes to respond to a neighbor solicitation or to notify neighbors of a change in link-layer address.</span></span>  
  
-   <span data-ttu-id="d3431-126">Redirect.</span><span class="sxs-lookup"><span data-stu-id="d3431-126">Redirect.</span></span> <span data-ttu-id="d3431-127">Inviato dai router per indicare un indirizzo dell'hop successivo migliore a una destinazione specifica per un nodo di invio.</span><span class="sxs-lookup"><span data-stu-id="d3431-127">Sent by routers to indicate a better next-hop address to a particular destination for a sending node.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3431-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3431-128">See Also</span></span>  
 [<span data-ttu-id="d3431-129">Protocollo IPv6</span><span class="sxs-lookup"><span data-stu-id="d3431-129">Internet Protocol Version 6</span></span>](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 [<span data-ttu-id="d3431-130">Socket</span><span class="sxs-lookup"><span data-stu-id="d3431-130">Sockets</span></span>](../../../docs/framework/network-programming/sockets.md)
