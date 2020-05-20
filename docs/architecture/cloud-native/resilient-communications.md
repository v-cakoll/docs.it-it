---
title: Comunicazione resiliente
description: Architettura di app .NET cloud native per Azure | Comunicazione resiliente
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 33e4c03c1f3d8c01f72c588326fbb0bdfa512cdd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613746"
---
# <a name="resilient-communications"></a><span data-ttu-id="c98a9-103">Comunicazioni resilienti</span><span class="sxs-lookup"><span data-stu-id="c98a9-103">Resilient communications</span></span>

<span data-ttu-id="c98a9-104">In questo libro abbiamo adottato un approccio architetturale basato su microservizi.</span><span class="sxs-lookup"><span data-stu-id="c98a9-104">Throughout this book, we've embraced a microservice-based architectural approach.</span></span> <span data-ttu-id="c98a9-105">Sebbene tale architettura offra vantaggi importanti, presenta diverse problemi:</span><span class="sxs-lookup"><span data-stu-id="c98a9-105">While such an architecture provides important benefits, it presents many challenges:</span></span>

- <span data-ttu-id="c98a9-106">*Comunicazione di rete out-of-process.*</span><span class="sxs-lookup"><span data-stu-id="c98a9-106">*Out-of-process network communication.*</span></span> <span data-ttu-id="c98a9-107">Ogni microservizio comunica tramite un protocollo di rete che introduce congestioni di rete, latenza ed errori temporanei.</span><span class="sxs-lookup"><span data-stu-id="c98a9-107">Each microservice communicates over a network protocol that introduces network congestion, latency, and transient faults.</span></span>

- <span data-ttu-id="c98a9-108">*Individuazione del servizio.*</span><span class="sxs-lookup"><span data-stu-id="c98a9-108">*Service discovery.*</span></span> <span data-ttu-id="c98a9-109">In che modo i microservizi scoprono e comunicano tra loro durante l'esecuzione in un cluster di computer con indirizzi IP e porte personali?</span><span class="sxs-lookup"><span data-stu-id="c98a9-109">How do microservices discover and communicate with each other when running across a cluster of machines with their own IP addresses and ports?</span></span>

- <span data-ttu-id="c98a9-110">*Resilienza.*</span><span class="sxs-lookup"><span data-stu-id="c98a9-110">*Resiliency.*</span></span> <span data-ttu-id="c98a9-111">Come si gestiscono gli errori di breve durata e si mantiene stabile il sistema?</span><span class="sxs-lookup"><span data-stu-id="c98a9-111">How do you manage short-lived failures and keep the system stable?</span></span>

- <span data-ttu-id="c98a9-112">*Bilanciamento del carico.*</span><span class="sxs-lookup"><span data-stu-id="c98a9-112">*Load balancing.*</span></span> <span data-ttu-id="c98a9-113">In che modo il traffico in ingresso viene distribuito tra più istanze di un microservizio?</span><span class="sxs-lookup"><span data-stu-id="c98a9-113">How does inbound traffic get distributed across multiple instances of a microservice?</span></span>

- <span data-ttu-id="c98a9-114">*Sicurezza.*</span><span class="sxs-lookup"><span data-stu-id="c98a9-114">*Security.*</span></span> <span data-ttu-id="c98a9-115">In che modo vengono applicati problemi di sicurezza, ad esempio la crittografia a livello di trasporto e la gestione dei certificati?</span><span class="sxs-lookup"><span data-stu-id="c98a9-115">How are security concerns such as transport-level encryption and certificate management enforced?</span></span>

- <span data-ttu-id="c98a9-116">*Monitoraggio distribuito.*</span><span class="sxs-lookup"><span data-stu-id="c98a9-116">*Distributed Monitoring.*</span></span> <span data-ttu-id="c98a9-117">-In che modo è possibile correlare e acquisire la tracciabilità e il monitoraggio per una singola richiesta tra più microservizi?</span><span class="sxs-lookup"><span data-stu-id="c98a9-117">- How do you correlate and capture traceability and monitoring for a single request across multiple consuming microservices?</span></span>

<span data-ttu-id="c98a9-118">È possibile risolvere questi problemi con librerie e Framework diversi, ma l'implementazione può essere costosa, complessa e dispendiosa in termini di tempo.</span><span class="sxs-lookup"><span data-stu-id="c98a9-118">You can address these concerns with different libraries and frameworks, but the implementation can be expensive, complex, and time-consuming.</span></span> <span data-ttu-id="c98a9-119">Si finiranno anche i problemi di infrastruttura associati alla logica di business.</span><span class="sxs-lookup"><span data-stu-id="c98a9-119">You also end up with infrastructure concerns coupled to business logic.</span></span>

## <a name="service-mesh"></a><span data-ttu-id="c98a9-120">Mesh del servizio</span><span class="sxs-lookup"><span data-stu-id="c98a9-120">Service mesh</span></span>

<span data-ttu-id="c98a9-121">Un approccio migliore è una tecnologia in evoluzione denominata *mesh di servizi*.</span><span class="sxs-lookup"><span data-stu-id="c98a9-121">A better approach is an evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="c98a9-122">Una [rete mesh di servizi](https://www.nginx.com/blog/what-is-a-service-mesh/) è un livello di infrastruttura configurabile con funzionalità predefinite per gestire la comunicazione dei servizi e gli altri problemi menzionati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c98a9-122">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service communication and the other challenges mentioned above.</span></span> <span data-ttu-id="c98a9-123">Per separare questi problemi, spostarli in un proxy del servizio.</span><span class="sxs-lookup"><span data-stu-id="c98a9-123">It decouples these concerns by moving them into a service proxy.</span></span> <span data-ttu-id="c98a9-124">Il proxy viene distribuito in un processo separato (denominato [sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar)) per fornire isolamento dal codice business.</span><span class="sxs-lookup"><span data-stu-id="c98a9-124">The proxy is deployed into a separate process (called a [sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar)) to provide isolation from business code.</span></span> <span data-ttu-id="c98a9-125">Tuttavia, il sidecar è collegato al servizio, che viene creato con esso e ne condivide il ciclo di vita.</span><span class="sxs-lookup"><span data-stu-id="c98a9-125">However, the sidecar is linked to the service - it's created with it and shares its lifecycle.</span></span> <span data-ttu-id="c98a9-126">Nella figura 6-7 è illustrato questo scenario.</span><span class="sxs-lookup"><span data-stu-id="c98a9-126">Figure 6-7 shows this scenario.</span></span>

![Rete di servizi con un'auto laterale](./media/service-mesh-with-side-car.png)

<span data-ttu-id="c98a9-128">**Figura 6-7**.</span><span class="sxs-lookup"><span data-stu-id="c98a9-128">**Figure 6-7**.</span></span> <span data-ttu-id="c98a9-129">Rete di servizi con un'auto laterale</span><span class="sxs-lookup"><span data-stu-id="c98a9-129">Service mesh with a side car</span></span>

<span data-ttu-id="c98a9-130">Nella figura precedente si noti il modo in cui il proxy intercetta e gestisce le comunicazioni tra i microservizi e il cluster.</span><span class="sxs-lookup"><span data-stu-id="c98a9-130">In the previous figure, note how the proxy intercepts and manages communication among the microservices and the cluster.</span></span>

<span data-ttu-id="c98a9-131">Una mesh di servizi viene suddivisa logicamente in due componenti diversi: un [piano dati](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) e un [piano di controllo](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span><span class="sxs-lookup"><span data-stu-id="c98a9-131">A service mesh is logically split into two disparate components: A [data plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) and [control plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span></span> <span data-ttu-id="c98a9-132">La figura 6-8 illustra questi componenti e le relative responsabilità.</span><span class="sxs-lookup"><span data-stu-id="c98a9-132">Figure 6-8 shows these components and their responsibilities.</span></span>

![Controllo mesh di servizi e piano dati](./media/istio-control-and-data-plane.png)

<span data-ttu-id="c98a9-134">**Figura 6-8.**</span><span class="sxs-lookup"><span data-stu-id="c98a9-134">**Figure 6-8.**</span></span> <span data-ttu-id="c98a9-135">Controllo mesh di servizi e piano dati</span><span class="sxs-lookup"><span data-stu-id="c98a9-135">Service mesh control and data plane</span></span>

<span data-ttu-id="c98a9-136">Una volta configurata, una mesh del servizio è altamente funzionante.</span><span class="sxs-lookup"><span data-stu-id="c98a9-136">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="c98a9-137">Può recuperare un pool di istanze corrispondente da un endpoint di individuazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="c98a9-137">It can retrieve a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="c98a9-138">La mesh può quindi inviare una richiesta a un'istanza specifica, registrando la latenza e il tipo di risposta del risultato.</span><span class="sxs-lookup"><span data-stu-id="c98a9-138">The mesh can then send a request to a specific instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="c98a9-139">Una mesh può scegliere l'istanza con maggiore probabilità di restituire una risposta rapida in base a molti fattori, inclusa la latenza osservata per le richieste recenti.</span><span class="sxs-lookup"><span data-stu-id="c98a9-139">A mesh can choose the instance most likely to return a fast response based on many factors, including its observed latency for recent requests.</span></span>

<span data-ttu-id="c98a9-140">Se un'istanza non risponde o non riesce, la mesh tenterà di ripetere la richiesta in un'altra istanza.</span><span class="sxs-lookup"><span data-stu-id="c98a9-140">If an instance is unresponsive or fails, the mesh will retry the request on another instance.</span></span> <span data-ttu-id="c98a9-141">Se vengono restituiti errori, una mesh eliminerà l'istanza dal pool di bilanciamento del carico e lo ricaricherà dopo la correzione.</span><span class="sxs-lookup"><span data-stu-id="c98a9-141">If it returns errors, a mesh will evict the instance from the load-balancing pool and restate it after it heals.</span></span> <span data-ttu-id="c98a9-142">Se una richiesta scade, una mesh può avere esito negativo e quindi ripetere la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c98a9-142">If a request times out, a mesh can fail and then retry the request.</span></span> <span data-ttu-id="c98a9-143">Una mesh acquisisce ed emette metriche e analisi distribuite in un sistema di metriche centralizzate.</span><span class="sxs-lookup"><span data-stu-id="c98a9-143">A mesh captures and emits metrics and distributed tracing to a centralized metrics system.</span></span>

## <a name="istio-and-envoy"></a><span data-ttu-id="c98a9-144">Istio e inviato</span><span class="sxs-lookup"><span data-stu-id="c98a9-144">Istio and Envoy</span></span>

<span data-ttu-id="c98a9-145">Sebbene esistano alcune opzioni di mesh del servizio, [Istio](https://istio.io/docs/concepts/what-is-istio/) è il più diffuso al momento della stesura di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="c98a9-145">While a few service mesh options currently exist, [Istio](https://istio.io/docs/concepts/what-is-istio/) is the most popular at the time of this writing.</span></span> <span data-ttu-id="c98a9-146">Istio è una joint venture tra IBM, Google e Lyft.</span><span class="sxs-lookup"><span data-stu-id="c98a9-146">Istio is a joint venture from IBM, Google, and Lyft.</span></span> <span data-ttu-id="c98a9-147">Si tratta di un'offerta open source che può essere integrata in un'applicazione distribuita nuova o esistente.</span><span class="sxs-lookup"><span data-stu-id="c98a9-147">It's an open-source offering that can be integrated into a new or existing distributed application.</span></span> <span data-ttu-id="c98a9-148">La tecnologia fornisce una soluzione coerente e completa per proteggere, connettere e monitorare i microservizi.</span><span class="sxs-lookup"><span data-stu-id="c98a9-148">The technology provides a consistent and complete solution to secure, connect, and monitor microservices.</span></span> <span data-ttu-id="c98a9-149">Le funzionalità includono:</span><span class="sxs-lookup"><span data-stu-id="c98a9-149">Its features include:</span></span>

- <span data-ttu-id="c98a9-150">Comunicazione da servizio a servizio sicura in un cluster con autenticazione e autorizzazione basate sulle identità complesse.</span><span class="sxs-lookup"><span data-stu-id="c98a9-150">Secure service-to-service communication in a cluster with strong identity-based authentication and authorization.</span></span>
- <span data-ttu-id="c98a9-151">Bilanciamento del carico automatico per il traffico HTTP, [gRPC](https://grpc.io/), WEBSOCKET e TCP.</span><span class="sxs-lookup"><span data-stu-id="c98a9-151">Automatic load balancing for HTTP, [gRPC](https://grpc.io/), WebSocket, and TCP traffic.</span></span>
- <span data-ttu-id="c98a9-152">Controllo con granularità fine del comportamento del traffico con regole di routing avanzate, tentativi, failover e attacchi di errore.</span><span class="sxs-lookup"><span data-stu-id="c98a9-152">Fine-grained control of traffic behavior with rich routing rules, retries, failovers, and fault injection.</span></span>
- <span data-ttu-id="c98a9-153">Un livello di criteri e un'API di configurazione collegabili che supportano i controlli di accesso, i limiti di frequenza e le quote.</span><span class="sxs-lookup"><span data-stu-id="c98a9-153">A pluggable policy layer and configuration API supporting access controls, rate limits, and quotas.</span></span>
- <span data-ttu-id="c98a9-154">Metriche automatiche, log e tracce per tutto il traffico all'interno di un cluster, tra cui ingresso e uscita del cluster.</span><span class="sxs-lookup"><span data-stu-id="c98a9-154">Automatic metrics, logs, and traces for all traffic within a cluster, including cluster ingress and egress.</span></span>

<span data-ttu-id="c98a9-155">Un componente chiave per un'implementazione di Istio è un servizio proxy denominato [proxy di invio](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span><span class="sxs-lookup"><span data-stu-id="c98a9-155">A key component for an Istio implementation is a proxy service entitled the [Envoy proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span></span> <span data-ttu-id="c98a9-156">Viene eseguito insieme a ogni servizio e fornisce una base indipendente dalla piattaforma per le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="c98a9-156">It runs alongside each service and provides a platform-agnostic foundation for the following features:</span></span>

- <span data-ttu-id="c98a9-157">Individuazione dinamica del servizio.</span><span class="sxs-lookup"><span data-stu-id="c98a9-157">Dynamic service discovery.</span></span>
- <span data-ttu-id="c98a9-158">Bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="c98a9-158">Load balancing.</span></span>
- <span data-ttu-id="c98a9-159">Terminazione TLS.</span><span class="sxs-lookup"><span data-stu-id="c98a9-159">TLS termination.</span></span>
- <span data-ttu-id="c98a9-160">Proxy HTTP e gRPC.</span><span class="sxs-lookup"><span data-stu-id="c98a9-160">HTTP and gRPC proxies.</span></span>
- <span data-ttu-id="c98a9-161">Resilienza degli interruttori.</span><span class="sxs-lookup"><span data-stu-id="c98a9-161">Circuit breaker resiliency.</span></span>
- <span data-ttu-id="c98a9-162">Controlli di integrità.</span><span class="sxs-lookup"><span data-stu-id="c98a9-162">Health checks.</span></span>
- <span data-ttu-id="c98a9-163">Aggiornamenti in sequenza con distribuzioni [Canarie](https://martinfowler.com/bliki/CanaryRelease.html) .</span><span class="sxs-lookup"><span data-stu-id="c98a9-163">Rolling updates with [canary](https://martinfowler.com/bliki/CanaryRelease.html) deployments.</span></span>

<span data-ttu-id="c98a9-164">Come descritto in precedenza, l'inviato viene distribuito come sidecar a ogni microservizio del cluster.</span><span class="sxs-lookup"><span data-stu-id="c98a9-164">As previously discussed, Envoy is deployed as a sidecar to each microservice in the cluster.</span></span>

## <a name="integration-with-azure-kubernetes-services"></a><span data-ttu-id="c98a9-165">Integrazione con i servizi Kubernetes di Azure</span><span class="sxs-lookup"><span data-stu-id="c98a9-165">Integration with Azure Kubernetes Services</span></span>

<span data-ttu-id="c98a9-166">Il cloud di Azure abbraccia Istio e fornisce il supporto diretto per l'it all'interno dei servizi Kubernetes di Azure.</span><span class="sxs-lookup"><span data-stu-id="c98a9-166">The Azure cloud embraces Istio and provides direct support for it within Azure Kubernetes Services.</span></span> <span data-ttu-id="c98a9-167">I collegamenti seguenti possono essere utili per iniziare:</span><span class="sxs-lookup"><span data-stu-id="c98a9-167">The following links can help you get started:</span></span>

- [<span data-ttu-id="c98a9-168">Installazione di Istio in AKS</span><span class="sxs-lookup"><span data-stu-id="c98a9-168">Installing Istio in AKS</span></span>](https://docs.microsoft.com/azure/aks/istio-install)
- [<span data-ttu-id="c98a9-169">Uso di AKS e Istio</span><span class="sxs-lookup"><span data-stu-id="c98a9-169">Using AKS and Istio</span></span>](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

### <a name="references"></a><span data-ttu-id="c98a9-170">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="c98a9-170">References</span></span>

- [<span data-ttu-id="c98a9-171">Polly</span><span class="sxs-lookup"><span data-stu-id="c98a9-171">Polly</span></span>](http://www.thepollyproject.org/)

- [<span data-ttu-id="c98a9-172">Modello di ripetizione dei tentativi</span><span class="sxs-lookup"><span data-stu-id="c98a9-172">Retry pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/retry)

- [<span data-ttu-id="c98a9-173">Modello di interruttore</span><span class="sxs-lookup"><span data-stu-id="c98a9-173">Circuit Breaker pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

- [<span data-ttu-id="c98a9-174">White paper sulla resilienza in Azure</span><span class="sxs-lookup"><span data-stu-id="c98a9-174">Resilience in Azure whitepaper</span></span>](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [<span data-ttu-id="c98a9-175">latenza di rete</span><span class="sxs-lookup"><span data-stu-id="c98a9-175">network latency</span></span>](https://www.techopedia.com/definition/8553/network-latency)

- [<span data-ttu-id="c98a9-176">Ridondanza</span><span class="sxs-lookup"><span data-stu-id="c98a9-176">Redundancy</span></span>](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy)

- [<span data-ttu-id="c98a9-177">replica geografica</span><span class="sxs-lookup"><span data-stu-id="c98a9-177">geo-replication</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)

- [<span data-ttu-id="c98a9-178">Gestione traffico di Azure</span><span class="sxs-lookup"><span data-stu-id="c98a9-178">Azure Traffic Manager</span></span>](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview)

- [<span data-ttu-id="c98a9-179">Indicazioni sulla scalabilità automatica</span><span class="sxs-lookup"><span data-stu-id="c98a9-179">Autoscaling guidance</span></span>](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling)

- [<span data-ttu-id="c98a9-180">Istio</span><span class="sxs-lookup"><span data-stu-id="c98a9-180">Istio</span></span>](https://istio.io/docs/concepts/what-is-istio/)

- [<span data-ttu-id="c98a9-181">Proxy inviato</span><span class="sxs-lookup"><span data-stu-id="c98a9-181">Envoy proxy</span></span>](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
><span data-ttu-id="c98a9-182">[Precedente](infrastructure-resiliency-azure.md) 
> [Avanti](monitoring-health.md)</span><span class="sxs-lookup"><span data-stu-id="c98a9-182">[Previous](infrastructure-resiliency-azure.md)
[Next](monitoring-health.md)</span></span>
