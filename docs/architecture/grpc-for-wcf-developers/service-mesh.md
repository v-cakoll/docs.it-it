---
title: Mesh del servizio-gRPC per sviluppatori WCF
description: Uso di una rete mesh di servizi per indirizzare e bilanciare le richieste ai servizi gRPC in un cluster Kubernetes.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6bdfa57ba47ba0105092d1c140705599b7023c78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090180"
---
# <a name="service-meshes"></a><span data-ttu-id="241f9-103">Mesh del servizio</span><span class="sxs-lookup"><span data-stu-id="241f9-103">Service meshes</span></span>

<span data-ttu-id="241f9-104">Una mesh di servizi è un componente dell'infrastruttura che prende il controllo del routing delle richieste di servizio all'interno di una rete.</span><span class="sxs-lookup"><span data-stu-id="241f9-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="241f9-105">Le mesh del servizio possono gestire tutti i tipi di problemi a livello di rete all'interno di un cluster Kubernetes, tra cui:</span><span class="sxs-lookup"><span data-stu-id="241f9-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="241f9-106">Individuazione del servizio</span><span class="sxs-lookup"><span data-stu-id="241f9-106">Service discovery</span></span>
- <span data-ttu-id="241f9-107">Bilanciamento del carico</span><span class="sxs-lookup"><span data-stu-id="241f9-107">Load balancing</span></span>
- <span data-ttu-id="241f9-108">Tolleranza di errore</span><span class="sxs-lookup"><span data-stu-id="241f9-108">Fault tolerance</span></span>
- <span data-ttu-id="241f9-109">Crittografia</span><span class="sxs-lookup"><span data-stu-id="241f9-109">Encryption</span></span>
- <span data-ttu-id="241f9-110">Monitoraggio</span><span class="sxs-lookup"><span data-stu-id="241f9-110">Monitoring</span></span>

<span data-ttu-id="241f9-111">Il servizio Kubernetes mesh funziona aggiungendo un contenitore aggiuntivo, denominato *sidecar proxy*, a ogni pod incluso nella rete.</span><span class="sxs-lookup"><span data-stu-id="241f9-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="241f9-112">Il proxy acquisisce la gestione di tutte le richieste di rete in ingresso e in uscita, consentendo la configurazione e la gestione delle operazioni di rete da mantenere separate dai contenitori dell'applicazione e, in molti casi, senza richiedere alcuna modifica al codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="241f9-112">The proxy takes over handling all inbound and outbound network requests, allowing configuration and management of networking matters to be kept separate from the application containers and, in many cases, without requiring any changes to the application code.</span></span>

<span data-ttu-id="241f9-113">Prendere l' [esempio del capitolo precedente](kubernetes.md#testing-the-application), in cui le richieste gRPC dall'applicazione Web sono state indirizzate a una singola istanza del servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="241f9-113">Take the [previous chapter's example](kubernetes.md#testing-the-application), where the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="241f9-114">Questo problema si verifica perché il nome host del servizio viene risolto in un indirizzo IP e tale indirizzo IP viene memorizzato nella cache per la durata dell'istanza di `HttpClientHandler`.</span><span class="sxs-lookup"><span data-stu-id="241f9-114">This happens because the service's hostname is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="241f9-115">Potrebbe essere possibile aggirare questo problema gestendo manualmente le ricerche DNS o creando più client, ma ciò complica notevolmente il codice dell'applicazione senza aggiungere alcun valore aziendale o cliente.</span><span class="sxs-lookup"><span data-stu-id="241f9-115">It might be possible to work around this by handling DNS lookups manually or creating multiple clients, but this would complicate the application code considerably without adding any business or customer value.</span></span>

<span data-ttu-id="241f9-116">Usando una mesh di servizi, le richieste provenienti dal contenitore dell'applicazione vengono inviate al proxy sidecar, che può distribuirle in modo intelligente in tutte le istanze dell'altro servizio.</span><span class="sxs-lookup"><span data-stu-id="241f9-116">Using a service mesh, the requests from the application container are sent to the sidecar proxy, which can distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="241f9-117">Il mesh può anche:</span><span class="sxs-lookup"><span data-stu-id="241f9-117">The mesh can also:</span></span>

- <span data-ttu-id="241f9-118">Rispondere facilmente agli errori delle singole istanze di un servizio.</span><span class="sxs-lookup"><span data-stu-id="241f9-118">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="241f9-119">Gestire la semantica di ripetizione dei tentativi per le chiamate non riuscite o i timeout</span><span class="sxs-lookup"><span data-stu-id="241f9-119">Handle retry semantics for failed calls or timeouts</span></span>
- <span data-ttu-id="241f9-120">Reindirizzare le richieste non riuscite a un'istanza alternativa senza tornare all'applicazione client.</span><span class="sxs-lookup"><span data-stu-id="241f9-120">Reroute failed requests to an alternate instance without returning to the client application at all.</span></span>

<span data-ttu-id="241f9-121">Lo screenshot seguente illustra l'applicazione StockWeb in esecuzione con la mesh del servizio Linkerd, senza modifiche al codice dell'applicazione o anche all'immagine Docker usata.</span><span class="sxs-lookup"><span data-stu-id="241f9-121">The following screenshot shows the StockWeb application running with the Linkerd service mesh, with no changes to the application code, or even the Docker image being used.</span></span> <span data-ttu-id="241f9-122">L'unica modifica necessaria è l'aggiunta di un'annotazione alla distribuzione nei file YAML per i servizi `stockdata` e `stockweb`.</span><span class="sxs-lookup"><span data-stu-id="241f9-122">The only change required was the addition of an annotation to the Deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![StockWeb con mesh del servizio](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="241f9-124">Dalla colonna Server è possibile vedere che le richieste dall'applicazione StockWeb sono state indirizzate a entrambe le repliche del servizio StockData, anche se originate da una singola istanza `HttpClient` nel codice dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="241f9-124">You can see from the Server column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="241f9-125">Infatti, se si esamina il codice, si noterà che tutte le richieste 100 al servizio StockData vengono effettuate simultaneamente utilizzando la stessa istanza di `HttpClient`, ma con la mesh del servizio, tali richieste verranno bilanciate in molte istanze del servizio disponibili.</span><span class="sxs-lookup"><span data-stu-id="241f9-125">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously using the same `HttpClient` instance, yet with the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="241f9-126">Le mesh del servizio si applicano solo al traffico all'interno di un cluster.</span><span class="sxs-lookup"><span data-stu-id="241f9-126">Service meshes only apply to traffic within a cluster.</span></span> <span data-ttu-id="241f9-127">Per i client esterni, vedere [il capitolo successivo, bilanciamento del carico](load-balancing.md).</span><span class="sxs-lookup"><span data-stu-id="241f9-127">For external clients, see [the next chapter, Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="241f9-128">Opzioni di mesh del servizio</span><span class="sxs-lookup"><span data-stu-id="241f9-128">Service mesh options</span></span>

<span data-ttu-id="241f9-129">Sono attualmente disponibili tre implementazioni di rete di servizi generiche da usare con Kubernetes: Istio, Linkerd e console connect.</span><span class="sxs-lookup"><span data-stu-id="241f9-129">There are three general-purpose service mesh implementations currently available for use with Kubernetes: Istio, Linkerd, and Consul Connect.</span></span> <span data-ttu-id="241f9-130">Tutte e tre forniscono routing/inoltro delle richieste, crittografia del traffico, resilienza, autenticazione da host a host e controllo del traffico.</span><span class="sxs-lookup"><span data-stu-id="241f9-130">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="241f9-131">La scelta di una mesh di servizi dipende da diversi fattori:</span><span class="sxs-lookup"><span data-stu-id="241f9-131">Choosing a service mesh depends multiple factors:</span></span>

- <span data-ttu-id="241f9-132">Requisiti specifici dell'organizzazione relativi ai costi, alla conformità, ai piani di supporto a pagamento e così via.</span><span class="sxs-lookup"><span data-stu-id="241f9-132">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="241f9-133">La natura del cluster, le dimensioni, il numero di servizi distribuiti e il volume di traffico all'interno della rete cluster.</span><span class="sxs-lookup"><span data-stu-id="241f9-133">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="241f9-134">Semplifica la distribuzione e la gestione della rete e la sua uso con i servizi.</span><span class="sxs-lookup"><span data-stu-id="241f9-134">Ease of deploying and managing the mesh and using it with services.</span></span>

<span data-ttu-id="241f9-135">Altre informazioni su ogni mesh di servizi sono disponibili nei rispettivi siti Web.</span><span class="sxs-lookup"><span data-stu-id="241f9-135">More information on each service mesh is available from their respective websites.</span></span>

- [<span data-ttu-id="241f9-136">**Istio** -Istio.io</span><span class="sxs-lookup"><span data-stu-id="241f9-136">**Istio** - istio.io</span></span>](https://istio.io)
- [<span data-ttu-id="241f9-137">**Linkerd** -linkerd.io</span><span class="sxs-lookup"><span data-stu-id="241f9-137">**Linkerd** - linkerd.io</span></span>](https://linkerd.io)
- [<span data-ttu-id="241f9-138">**Console** -Consul.io/mesh.html</span><span class="sxs-lookup"><span data-stu-id="241f9-138">**Consul** - consul.io/mesh.html</span></span>](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="241f9-139">Esempio: aggiungere Linkerd a una distribuzione</span><span class="sxs-lookup"><span data-stu-id="241f9-139">Example: add Linkerd to a deployment</span></span>

<span data-ttu-id="241f9-140">In questo esempio si apprenderà come usare la mesh del servizio Linkerd con l'applicazione *StockKube* della [sezione precedente](kubernetes.md).</span><span class="sxs-lookup"><span data-stu-id="241f9-140">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="241f9-141">Per seguire questo esempio, è necessario [installare l'interfaccia della](https://linkerd.io/2/getting-started/#step-1-install-the-cli)riga di comando di Linkerd.</span><span class="sxs-lookup"><span data-stu-id="241f9-141">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="241f9-142">I file binari di Windows possono essere scaricati dalla sezione relativa alle versioni di GitHub. Assicurarsi di usare la versione **stabile** più recente e non una delle versioni perimetrali.</span><span class="sxs-lookup"><span data-stu-id="241f9-142">Windows binaries can be downloaded from the GitHub releases section; make sure to use the most recent **stable** release and not one of the edge releases.</span></span>

<span data-ttu-id="241f9-143">Con l'interfaccia della riga di comando di Linkerd installata, seguire le [istruzioni*Introduzione* nel sito Web Linkerd] per installare i componenti Linkerd nel cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="241f9-143">With the Linkerd CLI installed, follow the [*Getting Started* instructions on the Linkerd web site] to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="241f9-144">Le istruzioni sono semplici e l'installazione dovrebbe richiedere solo alcuni minuti in un'istanza locale di Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="241f9-144">The instructions are straight-forward and installation should only take a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="241f9-145">Aggiungere Linkerd alle distribuzioni di Kubernetes</span><span class="sxs-lookup"><span data-stu-id="241f9-145">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="241f9-146">L'interfaccia della riga di comando di Linkerd fornisce un comando `inject` per aggiungere le sezioni e le proprietà necessarie ai file Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="241f9-146">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="241f9-147">È possibile eseguire il comando e scrivere l'output in un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="241f9-147">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="241f9-148">È possibile esaminare i nuovi file per vedere quali modifiche sono state apportate.</span><span class="sxs-lookup"><span data-stu-id="241f9-148">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="241f9-149">Per gli oggetti di distribuzione, viene aggiunta un'annotazione dei metadati per indicare a Linkerd di inserire un contenitore del proxy sidecar nel pod quando viene creato.</span><span class="sxs-lookup"><span data-stu-id="241f9-149">For Deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the Pod when it's created.</span></span>

<span data-ttu-id="241f9-150">È anche possibile inviare tramite pipe l'output del comando `linkerd inject` per `kubectl` direttamente.</span><span class="sxs-lookup"><span data-stu-id="241f9-150">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="241f9-151">I comandi seguenti funzioneranno in PowerShell o in qualsiasi shell Linux.</span><span class="sxs-lookup"><span data-stu-id="241f9-151">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="241f9-152">Esaminare i servizi nel dashboard di Linkerd</span><span class="sxs-lookup"><span data-stu-id="241f9-152">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="241f9-153">Avviare il dashboard di Linkerd usando l'interfaccia della riga di comando `linkerd`.</span><span class="sxs-lookup"><span data-stu-id="241f9-153">Launch the Linkerd dashboard using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="241f9-154">Il dashboard fornisce informazioni dettagliate su tutti i servizi connessi alla rete.</span><span class="sxs-lookup"><span data-stu-id="241f9-154">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![Dashboard Linkerd che mostra le applicazioni StockKube](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="241f9-156">Se si aumenta il numero di repliche del servizio StockData gRPC, come illustrato nell'esempio seguente, e si aggiorna la pagina StockWeb nel browser, viene visualizzata una combinazione di ID nella colonna Server, che indica che le richieste vengono gestite da tutte le istanze disponibili .</span><span class="sxs-lookup"><span data-stu-id="241f9-156">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the Server column, indicating that requests are being served by all the available instances.</span></span>

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
><span data-ttu-id="241f9-157">[Precedente](kubernetes.md)
>[Successivo](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="241f9-157">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
