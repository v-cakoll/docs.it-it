---
title: Bilanciamento del carico gRPC-gRPC per sviluppatori WCF
description: Scelta di un servizio di bilanciamento del carico per lavorare con i servizi gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 18965b9c4765ac693c6ba36ad3ea9848ce858a5c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846626"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="b1c2c-103">Bilanciamento del carico gRPC</span><span class="sxs-lookup"><span data-stu-id="b1c2c-103">Load balancing gRPC</span></span>

<span data-ttu-id="b1c2c-104">Una distribuzione tipica di un'applicazione gRPC include un numero di istanze identiche del servizio, garantendo resilienza e scalabilità orizzontale.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="b1c2c-105">Bilanciamento del carico delle richieste in ingresso distribuite in queste istanze per fornire l'utilizzo completo di tutte le risorse disponibili.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-105">Load balancing distributed incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="b1c2c-106">Per rendere invisibile questo bilanciamento del carico al client, è comune usare un server del servizio di bilanciamento del carico proxy per gestire le richieste provenienti dai client e instradarle alle istanze back-end.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="b1c2c-107">I bilanciamenti del carico sono classificati in base al *livello* su cui operano.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="b1c2c-108">I bilanciamenti del carico di livello 4 funzionano a livello di *trasporto* , ad esempio con socket TCP, connessioni e pacchetti.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections and packets.</span></span> <span data-ttu-id="b1c2c-109">I bilanciamenti del carico di livello 7 funzionano a livello di *applicazione* , gestendo in modo specifico le richieste http/2 per le applicazioni gRPC.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="b1c2c-110">Bilanciamento del carico L4</span><span class="sxs-lookup"><span data-stu-id="b1c2c-110">L4 load balancers</span></span>

<span data-ttu-id="b1c2c-111">Un servizio di bilanciamento del carico L4 accetta una richiesta di connessione TCP da un client, apre un'altra connessione a una delle istanze back-end e copia i dati tra le due connessioni senza alcuna elaborazione reale.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="b1c2c-112">L4 offre prestazioni ottimali e bassa latenza, ma un controllo o un'intelligenza molto limitata.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="b1c2c-113">Fino a quando il client mantiene la connessione aperta, tutte le richieste verranno indirizzate alla stessa istanza back-end.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

<span data-ttu-id="b1c2c-114">Un esempio di servizio di bilanciamento del carico L4 è il [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span><span class="sxs-lookup"><span data-stu-id="b1c2c-114">An example of an L4 load balancer is the [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="b1c2c-115">Bilanciamento del carico L7</span><span class="sxs-lookup"><span data-stu-id="b1c2c-115">L7 load balancers</span></span>

<span data-ttu-id="b1c2c-116">Un servizio di bilanciamento del carico L7 analizza le richieste HTTP/2 in ingresso e le passa alle istanze back-end in base a una richiesta per richiesta, indipendentemente dal tempo di attesa della connessione da parte del client.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="b1c2c-117">Esempi di bilanciamenti del carico L7 includono:</span><span class="sxs-lookup"><span data-stu-id="b1c2c-117">Examples of L7 load balancers include:</span></span>

- [<span data-ttu-id="b1c2c-118">Nginx</span><span class="sxs-lookup"><span data-stu-id="b1c2c-118">Nginx</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="b1c2c-119">HAproxy</span><span class="sxs-lookup"><span data-stu-id="b1c2c-119">HAproxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="b1c2c-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="b1c2c-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="b1c2c-121">Come regola generale, i bilanciamenti del carico L7 rappresentano la scelta migliore per gRPC e altre applicazioni HTTP/2 (e, in realtà, per le applicazioni HTTP).</span><span class="sxs-lookup"><span data-stu-id="b1c2c-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="b1c2c-122">I bilanciamenti del carico *L4 funzioneranno con le* applicazioni gRPC, ma sono principalmente utili quando la bassa latenza e il sovraccarico basso sono di importanza fondamentale.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-122">L4 load balancers will *work* with gRPC applications, but are primarily useful when low latency and low overhead are of paramount importance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b1c2c-123">Al momento della stesura di questo articolo, non tutti i servizi di bilanciamento del carico L7 supportano tutte le parti della specifica HTTP/2 richieste dai servizi gRPC, ad esempio le intestazioni finali.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-123">At the time of this writing, not all L7 load balancers support all parts of the HTTP/2 specification required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="b1c2c-124">Quando si usa la crittografia TLS, i bilanciamenti del carico possono terminare la connessione TLS e passare le richieste non crittografate all'applicazione back-end oppure passare la richiesta crittografata insieme.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-124">When using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or pass the encrypted request along.</span></span> <span data-ttu-id="b1c2c-125">In entrambi i casi, è necessario configurare il servizio di bilanciamento del carico con la chiave pubblica e privata del server, in modo che sia in grado di decrittografare le richieste di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-125">Either way, the load balancer will need to be configured with the server's public and private key, so that it can decrypt requests for processing.</span></span>

<span data-ttu-id="b1c2c-126">Per informazioni su come configurarlo per gestire le richieste HTTP/2 con i servizi back-end, vedere la documentazione relativa al servizio di bilanciamento del carico preferito.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-126">Refer to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="b1c2c-127">Bilanciamento del carico in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="b1c2c-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="b1c2c-128">Per una discussione sul bilanciamento del carico tra servizi interni in Kubernetes, vedere [la sezione sulle reti mesh](service-mesh.md) dei servizi.</span><span class="sxs-lookup"><span data-stu-id="b1c2c-128">See [the section on Service Meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b1c2c-129">[Precedente](service-mesh.md)
>[Successivo](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="b1c2c-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
