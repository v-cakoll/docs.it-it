---
title: Bilanciamento del carico gRPC-gRPC per sviluppatori WCF
description: Scelta di un servizio di bilanciamento del carico per lavorare con i servizi gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 215c0983146bbf9168f01956d64733f80cea6faf
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711167"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="943bc-103">Bilanciamento del carico gRPC</span><span class="sxs-lookup"><span data-stu-id="943bc-103">Load balancing gRPC</span></span>

<span data-ttu-id="943bc-104">Una distribuzione tipica di un'applicazione gRPC include un numero di istanze identiche del servizio, garantendo resilienza e scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="943bc-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="943bc-105">Il bilanciamento del carico distribuisce le richieste in ingresso tra queste istanze per fornire l'utilizzo completo di tutte le risorse disponibili.</span><span class="sxs-lookup"><span data-stu-id="943bc-105">Load balancing distributes incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="943bc-106">Per rendere invisibile questo bilanciamento del carico al client, è comune usare un server del servizio di bilanciamento del carico proxy per gestire le richieste provenienti dai client e instradarle alle istanze back-end.</span><span class="sxs-lookup"><span data-stu-id="943bc-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="943bc-107">I bilanciamenti del carico sono classificati in base al *livello* su cui operano.</span><span class="sxs-lookup"><span data-stu-id="943bc-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="943bc-108">I bilanciamenti del carico di livello 4 funzionano a livello di *trasporto* , ad esempio con socket TCP, connessioni e pacchetti.</span><span class="sxs-lookup"><span data-stu-id="943bc-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections, and packets.</span></span> <span data-ttu-id="943bc-109">I bilanciamenti del carico di livello 7 funzionano a livello di *applicazione* , gestendo in modo specifico le richieste http/2 per le applicazioni gRPC.</span><span class="sxs-lookup"><span data-stu-id="943bc-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="943bc-110">Bilanciamento del carico L4</span><span class="sxs-lookup"><span data-stu-id="943bc-110">L4 load balancers</span></span>

<span data-ttu-id="943bc-111">Un servizio di bilanciamento del carico L4 accetta una richiesta di connessione TCP da un client, apre un'altra connessione a una delle istanze back-end e copia i dati tra le due connessioni senza alcuna elaborazione reale.</span><span class="sxs-lookup"><span data-stu-id="943bc-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="943bc-112">L4 offre prestazioni ottimali e bassa latenza, ma un controllo o un'intelligenza molto limitata.</span><span class="sxs-lookup"><span data-stu-id="943bc-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="943bc-113">Fino a quando il client mantiene la connessione aperta, tutte le richieste verranno indirizzate alla stessa istanza back-end.</span><span class="sxs-lookup"><span data-stu-id="943bc-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

 <span data-ttu-id="943bc-114">[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) è un esempio di servizio di bilanciamento del carico L4.</span><span class="sxs-lookup"><span data-stu-id="943bc-114">[Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/) is an example of an L4 load balancer.</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="943bc-115">Bilanciamento del carico L7</span><span class="sxs-lookup"><span data-stu-id="943bc-115">L7 load balancers</span></span>

<span data-ttu-id="943bc-116">Un servizio di bilanciamento del carico L7 analizza le richieste HTTP/2 in ingresso e le passa alle istanze back-end in base a una richiesta per richiesta, indipendentemente dal tempo di attesa della connessione da parte del client.</span><span class="sxs-lookup"><span data-stu-id="943bc-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="943bc-117">Esempi di bilanciamenti del carico L7:</span><span class="sxs-lookup"><span data-stu-id="943bc-117">Examples of L7 load balancers:</span></span>

- [<span data-ttu-id="943bc-118">NGINX</span><span class="sxs-lookup"><span data-stu-id="943bc-118">NGINX</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="943bc-119">HAProxy</span><span class="sxs-lookup"><span data-stu-id="943bc-119">HAProxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="943bc-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="943bc-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="943bc-121">Come regola generale, i bilanciamenti del carico L7 rappresentano la scelta migliore per gRPC e altre applicazioni HTTP/2 (e, in realtà, per le applicazioni HTTP).</span><span class="sxs-lookup"><span data-stu-id="943bc-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="943bc-122">I bilanciamenti del carico *L4 funzioneranno con le* applicazioni gRPC, ma sono particolarmente utili quando sono importanti la bassa latenza e il sovraccarico basso.</span><span class="sxs-lookup"><span data-stu-id="943bc-122">L4 load balancers will *work* with gRPC applications, but they're mainly useful when low latency and low overhead are important.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="943bc-123">Al momento della stesura di questo articolo, alcuni servizi di bilanciamento del carico L7 non supportano tutte le parti della specifica HTTP/2 richieste dai servizi gRPC, ad esempio le intestazioni finali.</span><span class="sxs-lookup"><span data-stu-id="943bc-123">At the time of this writing, some L7 load balancers don't support all the parts of the HTTP/2 specification that are required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="943bc-124">Se si usa la crittografia TLS, i bilanciamenti del carico possono terminare la connessione TLS e passare le richieste non crittografate all'applicazione back-end oppure possono passare la richiesta crittografata insieme a.</span><span class="sxs-lookup"><span data-stu-id="943bc-124">If you're using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or they can pass the encrypted request along.</span></span> <span data-ttu-id="943bc-125">In entrambi i casi, è necessario configurare il servizio di bilanciamento del carico con la chiave pubblica e privata del server, in modo che sia in grado di decrittografare le richieste di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="943bc-125">Either way, the load balancer will need to be configured with the server's public and private key so it can decrypt requests for processing.</span></span>

<span data-ttu-id="943bc-126">Vedere la documentazione per il servizio di bilanciamento del carico preferito per informazioni su come configurarlo per gestire le richieste HTTP/2 con i servizi back-end.</span><span class="sxs-lookup"><span data-stu-id="943bc-126">See to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="943bc-127">Bilanciamento del carico in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="943bc-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="943bc-128">Per una discussione sul bilanciamento del carico tra servizi interni in Kubernetes, vedere [la sezione sulle reti mesh](service-mesh.md) dei servizi.</span><span class="sxs-lookup"><span data-stu-id="943bc-128">See [the section on service meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="943bc-129">[Precedente](service-mesh.md)
>[Successivo](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="943bc-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
