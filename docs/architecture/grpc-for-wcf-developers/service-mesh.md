---
title: Mesh del servizio-gRPC per sviluppatori WCF
description: Uso di una rete mesh di servizi per indirizzare e bilanciare le richieste ai servizi gRPC in un cluster Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: a29d6893e585c7eb60c847cef0149afeeaebcdab
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503393"
---
# <a name="service-meshes"></a><span data-ttu-id="fcfd3-103">Mesh del servizio</span><span class="sxs-lookup"><span data-stu-id="fcfd3-103">Service meshes</span></span>

<span data-ttu-id="fcfd3-104">Una mesh di servizi è un componente dell'infrastruttura che prende il controllo del routing delle richieste di servizio all'interno di una rete.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="fcfd3-105">Le mesh del servizio possono gestire tutti i tipi di problemi a livello di rete all'interno di un cluster Kubernetes, tra cui:</span><span class="sxs-lookup"><span data-stu-id="fcfd3-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="fcfd3-106">Individuazione del servizio</span><span class="sxs-lookup"><span data-stu-id="fcfd3-106">Service discovery</span></span>
- <span data-ttu-id="fcfd3-107">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="fcfd3-107">Load balancing</span></span>
- <span data-ttu-id="fcfd3-108">Tolleranza di errore</span><span class="sxs-lookup"><span data-stu-id="fcfd3-108">Fault tolerance</span></span>
- <span data-ttu-id="fcfd3-109">Crittografia</span><span class="sxs-lookup"><span data-stu-id="fcfd3-109">Encryption</span></span>
- <span data-ttu-id="fcfd3-110">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="fcfd3-110">Monitoring</span></span>

<span data-ttu-id="fcfd3-111">Il servizio Kubernetes mesh funziona aggiungendo un contenitore aggiuntivo, denominato *sidecar proxy*, a ogni pod incluso nella rete.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="fcfd3-112">Il proxy acquisisce la gestione di tutte le richieste di rete in ingresso e in uscita.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-112">The proxy takes over handling all inbound and outbound network requests.</span></span> <span data-ttu-id="fcfd3-113">È quindi possibile gestire la configurazione e la gestione delle questioni di rete separate dai contenitori di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-113">You can then keep configuration and management of networking matters separate from the application containers.</span></span> <span data-ttu-id="fcfd3-114">In molti casi, questa separazione non richiede alcuna modifica al codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-114">In many cases, this separation doesn't require any changes to the application code.</span></span>

<span data-ttu-id="fcfd3-115">Nell' [esempio del capitolo precedente](kubernetes.md#test-the-application), le richieste gRPC dall'applicazione Web sono state indirizzate a una singola istanza del servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-115">In the [previous chapter's example](kubernetes.md#test-the-application), the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="fcfd3-116">Questo problema si verifica perché il nome host del servizio viene risolto in un indirizzo IP e tale indirizzo IP viene memorizzato nella cache per la durata dell'istanza di `HttpClientHandler`.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-116">This happens because the service's host name is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="fcfd3-117">Potrebbe essere possibile aggirare questo problema gestendo manualmente le ricerche DNS o creando più client.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-117">It might be possible to work around this by handling DNS lookups manually or creating multiple clients.</span></span> <span data-ttu-id="fcfd3-118">Questa soluzione potrebbe tuttavia complicare il codice dell'applicazione senza aggiungere alcun valore aziendale o del cliente.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-118">But this workaround would complicate the application code without adding any business or customer value.</span></span>

<span data-ttu-id="fcfd3-119">Quando si usa una mesh di servizi, le richieste provenienti dal contenitore dell'applicazione vengono inviate al proxy sidecar.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-119">When you use a service mesh, the requests from the application container are sent to the sidecar proxy.</span></span> <span data-ttu-id="fcfd3-120">Il proxy sidecar può quindi distribuirli in modo intelligente in tutte le istanze dell'altro servizio.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-120">The sidecar proxy can then distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="fcfd3-121">Il mesh può anche:</span><span class="sxs-lookup"><span data-stu-id="fcfd3-121">The mesh can also:</span></span>

- <span data-ttu-id="fcfd3-122">Rispondere facilmente agli errori delle singole istanze di un servizio.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-122">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="fcfd3-123">Gestire la semantica di ripetizione dei tentativi per le chiamate non riuscite o i timeout.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-123">Handle retry semantics for failed calls or timeouts.</span></span>
- <span data-ttu-id="fcfd3-124">Reindirizzare le richieste non riuscite a un'istanza alternativa senza tornare all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-124">Reroute failed requests to an alternate instance without returning to the client application.</span></span>

<span data-ttu-id="fcfd3-125">Lo screenshot seguente illustra l'applicazione StockWeb in esecuzione con la mesh del servizio Linkerd.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-125">The following screenshot shows the StockWeb application running with the Linkerd service mesh.</span></span> <span data-ttu-id="fcfd3-126">Non sono state apportate modifiche al codice dell'applicazione e l'immagine Docker non è in uso.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-126">There are no changes to the application code, and the Docker image isn't being used.</span></span> <span data-ttu-id="fcfd3-127">L'unica modifica necessaria è l'aggiunta di un'annotazione alla distribuzione nei file YAML per i servizi `stockdata` e `stockweb`.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-127">The only change required was the addition of an annotation to the deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![StockWeb con mesh del servizio](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="fcfd3-129">Dalla colonna **Server** è possibile vedere che le richieste dall'applicazione StockWeb sono state indirizzate a entrambe le repliche del servizio StockData, anche se originate da una singola istanza `HttpClient` nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-129">You can see from the **Server** column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="fcfd3-130">Infatti, se si esamina il codice, si noterà che tutte le richieste 100 al servizio StockData vengono effettuate simultaneamente utilizzando la stessa istanza di `HttpClient`.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-130">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously by using the same `HttpClient` instance.</span></span> <span data-ttu-id="fcfd3-131">Con la mesh dei servizi, le richieste verranno bilanciate tra loro, ma sono disponibili molte istanze del servizio.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-131">With the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="fcfd3-132">Le mesh del servizio si applicano solo al traffico all'interno di un cluster.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-132">Service meshes apply only to traffic within a cluster.</span></span> <span data-ttu-id="fcfd3-133">Per i client esterni, vedere il capitolo successivo, [bilanciamento del carico](load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="fcfd3-133">For external clients, see the next chapter, [Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="fcfd3-134">Opzioni di mesh del servizio</span><span class="sxs-lookup"><span data-stu-id="fcfd3-134">Service mesh options</span></span>

<span data-ttu-id="fcfd3-135">Sono attualmente disponibili tre implementazioni di rete di servizi generici per l'uso con Kubernetes: [Istio](https://istio.io), [Linkerd](https://linkerd.io)e [console connect](https://consul.io/mesh.html).</span><span class="sxs-lookup"><span data-stu-id="fcfd3-135">Three general-purpose service mesh implementations are currently available for use with Kubernetes: [Istio](https://istio.io), [Linkerd](https://linkerd.io), and [Consul Connect](https://consul.io/mesh.html).</span></span> <span data-ttu-id="fcfd3-136">Tutte e tre forniscono routing/inoltro delle richieste, crittografia del traffico, resilienza, autenticazione da host a host e controllo del traffico.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-136">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="fcfd3-137">La scelta di una mesh di servizi dipende da diversi fattori:</span><span class="sxs-lookup"><span data-stu-id="fcfd3-137">Choosing a service mesh depends on multiple factors:</span></span>

- <span data-ttu-id="fcfd3-138">Requisiti specifici dell'organizzazione relativi ai costi, alla conformità, ai piani di supporto a pagamento e così via.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-138">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="fcfd3-139">La natura del cluster, le dimensioni, il numero di servizi distribuiti e il volume di traffico all'interno della rete cluster.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-139">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="fcfd3-140">Semplifica la distribuzione e la gestione della rete e la sua uso con i servizi.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-140">Ease of deploying and managing the mesh and using it with services.</span></span>

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="fcfd3-141">Esempio: aggiungere Linkerd a una distribuzione</span><span class="sxs-lookup"><span data-stu-id="fcfd3-141">Example: Add Linkerd to a deployment</span></span>

<span data-ttu-id="fcfd3-142">In questo esempio si apprenderà come usare la mesh del servizio Linkerd con l'applicazione *StockKube* della [sezione precedente](kubernetes.md).</span><span class="sxs-lookup"><span data-stu-id="fcfd3-142">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="fcfd3-143">Per seguire questo esempio, è necessario [installare l'interfaccia della](https://linkerd.io/2/getting-started/#step-1-install-the-cli)riga di comando di Linkerd.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-143">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="fcfd3-144">È possibile scaricare i file binari di Windows dalla sezione che elenca le versioni di GitHub.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-144">You can download Windows binaries from the section that lists GitHub releases.</span></span> <span data-ttu-id="fcfd3-145">Assicurarsi di usare la versione *stabile* più recente e non una delle versioni perimetrali.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-145">Be sure to use the most recent *stable* release and not one of the edge releases.</span></span>

<span data-ttu-id="fcfd3-146">Con l'interfaccia della riga di comando di Linkerd installata, seguire le istruzioni [Introduzione](https://linkerd.io/2/getting-started/index.html) per installare i componenti di Linkerd nel cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-146">With the Linkerd CLI installed, follow the [Getting Started](https://linkerd.io/2/getting-started/index.html) instructions to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="fcfd3-147">Le istruzioni sono semplici e l'installazione dovrebbe richiedere solo un paio di minuti in un'istanza locale di Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-147">The instructions are straightforward, and installation should take only a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="fcfd3-148">Aggiungere Linkerd alle distribuzioni di Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fcfd3-148">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="fcfd3-149">L'interfaccia della riga di comando di Linkerd fornisce un comando `inject` per aggiungere le sezioni e le proprietà necessarie ai file Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-149">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="fcfd3-150">È possibile eseguire il comando e scrivere l'output in un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-150">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="fcfd3-151">È possibile esaminare i nuovi file per vedere quali modifiche sono state apportate.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-151">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="fcfd3-152">Per gli oggetti di distribuzione, viene aggiunta un'annotazione dei metadati per indicare a Linkerd di inserire un contenitore del proxy sidecar nel pod quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-152">For deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the pod when it's created.</span></span>

<span data-ttu-id="fcfd3-153">È anche possibile inviare tramite pipe l'output del comando `linkerd inject` per `kubectl` direttamente.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-153">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="fcfd3-154">I comandi seguenti funzioneranno in PowerShell o in qualsiasi shell Linux.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-154">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="fcfd3-155">Esaminare i servizi nel dashboard di Linkerd</span><span class="sxs-lookup"><span data-stu-id="fcfd3-155">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="fcfd3-156">Aprire il dashboard di Linkerd usando l'interfaccia della riga di comando `linkerd`.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-156">Open the Linkerd dashboard by using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="fcfd3-157">Il dashboard fornisce informazioni dettagliate su tutti i servizi connessi alla rete.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-157">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![Dashboard Linkerd che mostra le applicazioni StockKube](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="fcfd3-159">Se si aumenta il numero di repliche del servizio StockData gRPC, come illustrato nell'esempio seguente, e si aggiorna la pagina StockWeb nel browser, viene visualizzata una combinazione di ID nella colonna **Server** .</span><span class="sxs-lookup"><span data-stu-id="fcfd3-159">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the **Server** column.</span></span> <span data-ttu-id="fcfd3-160">Questa combinazione indica che tutte le istanze disponibili sono in grado di soddisfare le richieste.</span><span class="sxs-lookup"><span data-stu-id="fcfd3-160">This mix indicates that all the available instances are serving requests.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
><span data-ttu-id="fcfd3-161">[Precedente](kubernetes.md)
>[Successivo](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="fcfd3-161">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
