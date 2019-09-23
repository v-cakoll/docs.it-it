---
title: Kubernetes-gRPC per sviluppatori WCF
description: Esecuzione di ASP.NET Core Servizi gRPC in un cluster Kubernetes.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 3af1b92ade106cf2338816ec69e6b13312681339
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184407"
---
# <a name="kubernetes"></a><span data-ttu-id="79f69-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="79f69-103">Kubernetes</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="79f69-104">Sebbene sia possibile eseguire manualmente i contenitori negli host Docker, per i sistemi di produzione affidabili è preferibile usare un motore di orchestrazione contenitore per gestire più istanze in esecuzione in più server in un cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's preferable to use a Container Orchestration Engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="79f69-105">Sono disponibili vari motori di orchestrazione del contenitore, tra cui Kubernetes, Docker Swarm e Apache Mesos.</span><span class="sxs-lookup"><span data-stu-id="79f69-105">There are various Container Orchestration Engines available, including Kubernetes, Docker Swarm and Apache Mesos.</span></span> <span data-ttu-id="79f69-106">Tuttavia, con questi motori, Kubernetes è molto più usato, quindi sarà l'obiettivo di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="79f69-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="79f69-107">Kubernetes include le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="79f69-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="79f69-108">La **pianificazione** esegue i contenitori su più nodi all'interno di un cluster, garantendo un uso bilanciato della risorsa disponibile, mantenendo i contenitori in esecuzione in caso di interruzioni e gestendo gli aggiornamenti in sequenza alle nuove versioni di immagini o nuove configurazioni.</span><span class="sxs-lookup"><span data-stu-id="79f69-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="79f69-109">I **controlli di integrità** monitorano i contenitori per garantire un servizio continuo.</span><span class="sxs-lookup"><span data-stu-id="79f69-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="79f69-110">Il **servizio di individuazione DNS &** gestisce il routing tra i servizi all'interno di un cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="79f69-111">Il traffico in **ingresso** espone i servizi selezionati esternamente e in genere fornisce il bilanciamento del carico tra le istanze di tali servizi.</span><span class="sxs-lookup"><span data-stu-id="79f69-111">**Ingress** exposes selected services externally, and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="79f69-112">**Gestione risorse** connette risorse esterne, ad esempio l'archiviazione ai contenitori.</span><span class="sxs-lookup"><span data-stu-id="79f69-112">**Resource management** attaches external resources such as storage to containers.</span></span>

<span data-ttu-id="79f69-113">In questo capitolo viene illustrato in dettaglio come distribuire un servizio ASP.NET Core gRPC e un sito Web che utilizza il servizio in un cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="79f69-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="79f69-114">L'applicazione di esempio usata è disponibile nel repository [RendleLabs/grpc-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="79f69-114">The sample application used is available from on the [RendleLabs/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub,</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="79f69-115">Terminologia di Kubernetes</span><span class="sxs-lookup"><span data-stu-id="79f69-115">Kubernetes terminology</span></span>

<span data-ttu-id="79f69-116">Kubernetes USA DSC ( *desired state Configuration*): l'API viene usata per descrivere oggetti quali *Pod*, *distribuzioni* e *Servizi*e il *piano di controllo* si occupa dell'implementazione dello stato desiderato in tutti i *nodi.* in un *cluster*.</span><span class="sxs-lookup"><span data-stu-id="79f69-116">Kubernetes uses *desired state configuration*: the API is used to describe objects such as *Pods*, *Deployments* and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="79f69-117">Un cluster Kubernetes dispone di un nodo *Master* che esegue l' *API Kubernetes*, che può essere comunicata con a livello di `kubectl` codice o tramite lo strumento da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="79f69-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which can be communicated with programmatically or using the `kubectl` command-line tool.</span></span> <span data-ttu-id="79f69-118">`kubectl`consente di creare e gestire oggetti usando argomenti della riga di comando, ma funziona meglio con i file YAML che contengono dati di dichiarazione per gli oggetti Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="79f69-118">`kubectl` can create and manage objects using command-line arguments, but works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="79f69-119">File YAML Kubernetes</span><span class="sxs-lookup"><span data-stu-id="79f69-119">Kubernetes YAML files</span></span>

<span data-ttu-id="79f69-120">Ogni file YAML di Kubernetes avrà almeno tre proprietà di primo livello.</span><span class="sxs-lookup"><span data-stu-id="79f69-120">Every Kubernetes YAML file will have at least three top-level properties.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="79f69-121">La `apiVersion` proprietà viene usata per specificare la versione (e l'API) per cui il file è destinato.</span><span class="sxs-lookup"><span data-stu-id="79f69-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="79f69-122">La `kind` proprietà specifica il tipo di oggetto rappresentato da YAML.</span><span class="sxs-lookup"><span data-stu-id="79f69-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="79f69-123">La `metadata` proprietà contiene le proprietà dell'oggetto `name`, `namespace`ad esempio `labels`, o.</span><span class="sxs-lookup"><span data-stu-id="79f69-123">The `metadata` property contains object properties such as `name`, `namespace`, or `labels`.</span></span>

<span data-ttu-id="79f69-124">La maggior parte dei file YAML di Kubernetes `spec` include anche una sezione che descrive le risorse e la configurazione necessarie per creare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="79f69-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="79f69-125">Baccelli</span><span class="sxs-lookup"><span data-stu-id="79f69-125">Pods</span></span>

<span data-ttu-id="79f69-126">I pod sono le unità di base di esecuzione in Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="79f69-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="79f69-127">Possono eseguire più contenitori, ma vengono usati anche per eseguire singoli contenitori.</span><span class="sxs-lookup"><span data-stu-id="79f69-127">They can run multiple containers, but are also used to run single containers.</span></span> <span data-ttu-id="79f69-128">Il Pod include anche le risorse di archiviazione richieste dai contenitori e l'indirizzo IP di rete.</span><span class="sxs-lookup"><span data-stu-id="79f69-128">The pod also includes any storage resources required by the container(s), and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="79f69-129">Servizi</span><span class="sxs-lookup"><span data-stu-id="79f69-129">Services</span></span>

<span data-ttu-id="79f69-130">I servizi sono metaoggetti che descrivono pod (o set di Pod) e forniscono un modo per accedervi all'interno del cluster, ad esempio il mapping di un nome di servizio a un set di indirizzi IP pod tramite il servizio DNS del cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-130">Services are meta-objects that describe pods (or sets of pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="79f69-131">Distribuzioni</span><span class="sxs-lookup"><span data-stu-id="79f69-131">Deployments</span></span>

<span data-ttu-id="79f69-132">Le distribuzioni sono gli oggetti di *stato descritti* per i pod.</span><span class="sxs-lookup"><span data-stu-id="79f69-132">Deployments are the *described state* objects for Pods.</span></span> <span data-ttu-id="79f69-133">Se si crea un pod manualmente, al termine non verrà riavviato.</span><span class="sxs-lookup"><span data-stu-id="79f69-133">If you create a Pod manually, when it terminates it won't be restarted.</span></span> <span data-ttu-id="79f69-134">Le distribuzioni vengono usate per indicare al cluster quali pod e quante repliche di tali Pod devono essere in esecuzione al momento attuale.</span><span class="sxs-lookup"><span data-stu-id="79f69-134">Deployments are used to tell the cluster which pods, and how many replicas of those pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="79f69-135">Altri oggetti</span><span class="sxs-lookup"><span data-stu-id="79f69-135">Other objects</span></span>

<span data-ttu-id="79f69-136">Pod, servizi e distribuzioni sono solo tre dei tipi di oggetti di base.</span><span class="sxs-lookup"><span data-stu-id="79f69-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="79f69-137">Sono disponibili dozzine di altri tipi di oggetti gestiti da un cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="79f69-137">There are dozens of other types of object that are managed by a Kubernetes cluster.</span></span> <span data-ttu-id="79f69-138">Per ulteriori informazioni, vedere la documentazione relativa ai [concetti relativi a Kubernetes](https://kubernetes.io/docs/concepts/) .</span><span class="sxs-lookup"><span data-stu-id="79f69-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="79f69-139">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="79f69-139">Namespaces</span></span>

<span data-ttu-id="79f69-140">I cluster Kubernetes sono progettati per la scalabilità fino a centinaia o migliaia di nodi ed eseguono un numero simile di servizi.</span><span class="sxs-lookup"><span data-stu-id="79f69-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes, and run similar numbers of services.</span></span> <span data-ttu-id="79f69-141">Per evitare conflitti tra i nomi degli oggetti, gli spazi dei nomi vengono utilizzati per raggruppare gli oggetti come parte delle applicazioni più grandi.</span><span class="sxs-lookup"><span data-stu-id="79f69-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="79f69-142">I servizi di Kubernetes vengono eseguiti `default` in uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="79f69-142">Kubernetes own services run in a `default` namespace.</span></span> <span data-ttu-id="79f69-143">Tutti gli oggetti utente devono essere creati nei rispettivi spazi dei nomi per evitare potenziali conflitti con gli oggetti predefiniti o altri tenant nel cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="79f69-144">Introduzione a Kubernetes</span><span class="sxs-lookup"><span data-stu-id="79f69-144">Get started with Kubernetes</span></span>

<span data-ttu-id="79f69-145">Se si sta eseguendo Docker desktop per Windows o macOS, Kubernetes è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="79f69-145">If you're running Docker Desktop for Windows or macOS, Kubernetes is already available.</span></span> <span data-ttu-id="79f69-146">È sufficiente abilitarla nella sezione Kubernetes della finestra impostazioni.</span><span class="sxs-lookup"><span data-stu-id="79f69-146">Just enable it in the Kubernetes section of the Settings window.</span></span>

![Abilitare Kubernetes in Docker desktop](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="79f69-148">Per eseguire un cluster Kubernetes locale in Linux, vedere [minikube](https://github.com/kubernetes/minikube)o [MicroK8s](https://microk8s.io/) se la distribuzione di Linux supporta gli [snap](https://snapcraft.io/)-in.</span><span class="sxs-lookup"><span data-stu-id="79f69-148">To run a local Kubernetes cluster in Linux, look at [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="79f69-149">Per verificare che il cluster sia in esecuzione e accessibile, eseguire `kubectl version` il comando.</span><span class="sxs-lookup"><span data-stu-id="79f69-149">To check that your cluster is running and accessible, run the `kubectl version` command.</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="79f69-150">In questo esempio, sia l' `kubectl` interfaccia della riga di comando che il server Kubernetes eseguono la versione 1.14.6.</span><span class="sxs-lookup"><span data-stu-id="79f69-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="79f69-151">Ogni versione di `kubectl` deve supportare la versione precedente e successiva del server, pertanto `kubectl` 1,14 dovrebbe funzionare anche con le versioni del server 1,13 e 1,15.</span><span class="sxs-lookup"><span data-stu-id="79f69-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="79f69-152">Eseguire i servizi in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="79f69-152">Run services on Kubernetes</span></span>

<span data-ttu-id="79f69-153">Nell'applicazione di esempio è `kube` presente una directory contenente tre file YAML.</span><span class="sxs-lookup"><span data-stu-id="79f69-153">The sample application has a `kube` directory containing three YAML files.</span></span> <span data-ttu-id="79f69-154">Il `namespace.yml` file dichiara uno spazio dei nomi personalizzato `stocks`,.</span><span class="sxs-lookup"><span data-stu-id="79f69-154">The `namespace.yml` file declares a custom namespace, `stocks`.</span></span> <span data-ttu-id="79f69-155">Il `stockdata.yml` file dichiara la distribuzione e il servizio per l'applicazione gRPC e il `stockweb.yml` file dichiara la distribuzione e il servizio per un ASP.NET Core applicazione Web MVC 3,0 che utilizza il servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="79f69-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="79f69-156">Per utilizzare un `YAML` file con `kubectl`, utilizzare il `apply -f` comando.</span><span class="sxs-lookup"><span data-stu-id="79f69-156">To use a `YAML` file with `kubectl`, use the `apply -f` command.</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="79f69-157">Il `apply` comando verificherà la validità del file YAML e visualizzerà gli eventuali errori ricevuti dall'API, ma non attenderà che tutti gli oggetti dichiarati nel file siano stati creati perché questa operazione può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="79f69-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created as this can take some time.</span></span> <span data-ttu-id="79f69-158">Usare il `kubectl get` comando con i tipi di oggetto pertinenti per verificare la creazione di oggetti nel cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="79f69-159">Dichiarazione dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="79f69-159">The namespace declaration</span></span>

<span data-ttu-id="79f69-160">La dichiarazione dello spazio dei nomi è semplice e richiede `name`solo l'assegnazione di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="79f69-160">Namespace declaration is simple and requires only assigning a `name`.</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="79f69-161">Utilizzare `kubectl` per applicare il `namespace.yml` file e verificare che lo spazio dei nomi venga creato correttamente.</span><span class="sxs-lookup"><span data-stu-id="79f69-161">Use `kubectl` to apply the `namespace.yml` file and check the namespace is created successfully.</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="79f69-162">Applicazione StockData</span><span class="sxs-lookup"><span data-stu-id="79f69-162">The StockData application</span></span>

<span data-ttu-id="79f69-163">Il `stockdata.yml` file dichiara due oggetti: una distribuzione e un servizio.</span><span class="sxs-lookup"><span data-stu-id="79f69-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="79f69-164">Distribuzione di StockData</span><span class="sxs-lookup"><span data-stu-id="79f69-164">The StockData Deployment</span></span>

<span data-ttu-id="79f69-165">La parte della distribuzione fornisce `spec` per la distribuzione stessa, incluso il numero di repliche necessarie `template` e per gli oggetti pod da creare e gestire tramite la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="79f69-165">The Deployment part provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="79f69-166">Si noti che gli oggetti di distribuzione vengono `apps` gestiti con l'API, `apiVersion`come specificato in, anziché l'API principale di Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="79f69-166">Note that Deployment objects are managed with the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

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
  replicas: 1
  template:
    metadata:
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

<span data-ttu-id="79f69-167">La `spec.selector` proprietà viene usata per associare i pod in esecuzione alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="79f69-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="79f69-168">La `metadata.labels` proprietà del Pod deve corrispondere alla `matchLabels` proprietà o la chiamata API avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="79f69-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="79f69-169">La `template.spec` sezione dichiara il contenitore da eseguire.</span><span class="sxs-lookup"><span data-stu-id="79f69-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="79f69-170">Quando si usa un cluster Kubernetes locale, ad esempio quello fornito da Docker desktop, è possibile specificare le immagini che sono state compilate localmente, purché dispongano di un tag Version.</span><span class="sxs-lookup"><span data-stu-id="79f69-170">When working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79f69-171">Per impostazione predefinita, Kubernetes verificherà sempre e tenterà di eseguire il pull di una nuova immagine.</span><span class="sxs-lookup"><span data-stu-id="79f69-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="79f69-172">Se non riesce a trovare l'immagine in uno dei repository noti, la creazione del Pod avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="79f69-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="79f69-173">Per usare le `imagePullPolicy` immagini locali, impostare su `Never`.</span><span class="sxs-lookup"><span data-stu-id="79f69-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="79f69-174">La `ports` proprietà specifica quali porte del contenitore devono essere pubblicate sul Pod.</span><span class="sxs-lookup"><span data-stu-id="79f69-174">The `ports` property specifies which container ports should be published on the Pod.</span></span>  <span data-ttu-id="79f69-175">L' `stockservice` immagine esegue il servizio sulla porta HTTP standard, quindi viene pubblicata la porta 80.</span><span class="sxs-lookup"><span data-stu-id="79f69-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="79f69-176">La `resources` sezione applica i limiti delle risorse al contenitore in esecuzione nel pod.</span><span class="sxs-lookup"><span data-stu-id="79f69-176">The `resources` section applies resource limits to the container running within the pod.</span></span> <span data-ttu-id="79f69-177">Si tratta di una procedura consigliata che impedisce a un singolo pod di consumare tutta la CPU o la memoria disponibile in un nodo.</span><span class="sxs-lookup"><span data-stu-id="79f69-177">This is good practice as it prevents an individual pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="79f69-178">ASP.NET Core 3,0 è stato ottimizzato e ottimizzato per l'esecuzione in contenitori con limitazioni di `dotnet/core/aspnet` risorse e l'immagine Docker imposta una variabile di `dotnet` ambiente per indicare al runtime che si trova in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="79f69-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers, and the `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="79f69-179">Il servizio StockData</span><span class="sxs-lookup"><span data-stu-id="79f69-179">The StockData Service</span></span>

<span data-ttu-id="79f69-180">La parte del servizio del file YAML dichiara il servizio che fornisce l'accesso ai pod all'interno del cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-180">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

<span data-ttu-id="79f69-181">La specifica del servizio usa `selector` la proprietà per trovare `Pods`la corrispondenza con l'esecuzione, in questo caso la `run: stockdata`ricerca di Pod con un'etichetta.</span><span class="sxs-lookup"><span data-stu-id="79f69-181">The Service spec uses the `selector` property to match running `Pods`, in this case looking for Pods with a label `run: stockdata`.</span></span> <span data-ttu-id="79f69-182">L'oggetto `port` specificato nei Pod corrispondenti viene pubblicato dal servizio denominato.</span><span class="sxs-lookup"><span data-stu-id="79f69-182">The specified `port` on matching Pods are published by the named service.</span></span> <span data-ttu-id="79f69-183">Altri pod in esecuzione nello `stocks` spazio dei nomi possono accedere a http su `http://stockdata` questo servizio usando come indirizzo.</span><span class="sxs-lookup"><span data-stu-id="79f69-183">Other Pods running in the `stocks` namespace can access HTTP on this service using `http://stockdata` as the address.</span></span> <span data-ttu-id="79f69-184">I pod in esecuzione in altri spazi dei nomi `http://stockdata.stocks` possono usare il nome host.</span><span class="sxs-lookup"><span data-stu-id="79f69-184">Pods running in other namespaces can use the `http://stockdata.stocks` hostname.</span></span> <span data-ttu-id="79f69-185">È possibile controllare l'accesso al servizio tra gli spazi dei nomi usando i [criteri di rete](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span><span class="sxs-lookup"><span data-stu-id="79f69-185">You can control cross-namespace service access using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="79f69-186">Distribuire l'applicazione StockData</span><span class="sxs-lookup"><span data-stu-id="79f69-186">Deploy the StockData application</span></span>

<span data-ttu-id="79f69-187">Utilizzare `kubectl` per applicare il `stockdata.yml` file e verificare che la distribuzione e il servizio siano stati creati.</span><span class="sxs-lookup"><span data-stu-id="79f69-187">Use `kubectl` to apply the `stockdata.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a><span data-ttu-id="79f69-188">Applicazione StockWeb</span><span class="sxs-lookup"><span data-stu-id="79f69-188">The StockWeb application</span></span>

<span data-ttu-id="79f69-189">Il `stockweb.yml` file dichiara la distribuzione e il servizio per l'applicazione MVC.</span><span class="sxs-lookup"><span data-stu-id="79f69-189">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a><span data-ttu-id="79f69-190">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="79f69-190">Environment variables</span></span>

<span data-ttu-id="79f69-191">La `env` sezione dell'oggetto di distribuzione specifica le variabili di ambiente da impostare nel contenitore che esegue `stockweb:1.0.0` le immagini.</span><span class="sxs-lookup"><span data-stu-id="79f69-191">The `env` section of the Deployment object specifies environment variables to be set in the container running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="79f69-192">La **`StockData__Address`** variabile`StockData:Address` di ambiente viene mappata all'impostazione di configurazione grazie al provider di configurazione EnvironmentVariables.</span><span class="sxs-lookup"><span data-stu-id="79f69-192">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="79f69-193">Questa impostazione Usa doppi caratteri di sottolineatura tra i nomi per separare le sezioni.</span><span class="sxs-lookup"><span data-stu-id="79f69-193">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="79f69-194">L'indirizzo USA il nome del `stockdata` servizio, che viene eseguito nello stesso spazio dei nomi Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="79f69-194">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="79f69-195">La **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** variabile di ambiente imposta <xref:System.AppContext> un'opzione che consente connessioni http/2 non crittografate per <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="79f69-195">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="79f69-196">Questa variabile di ambiente equivale a impostare l'opzione nel codice come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="79f69-196">This environment variable is the equivalent of setting the switch in code as shown here.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="79f69-197">L'uso di una variabile di ambiente per l'opzione indica che l'impostazione può essere facilmente modificata a seconda del contesto in cui l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="79f69-197">Using an environment variable for the switch means the setting can easily be changed depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="79f69-198">Tipi di servizio</span><span class="sxs-lookup"><span data-stu-id="79f69-198">Service types</span></span>

<span data-ttu-id="79f69-199">Per rendere accessibile l'applicazione Web dall'esterno del cluster, viene `type: NodePort` utilizzata la proprietà.</span><span class="sxs-lookup"><span data-stu-id="79f69-199">To make the Web application accessible from outside the cluster, the `type: NodePort` property is used.</span></span> <span data-ttu-id="79f69-200">Questo tipo di proprietà fa in modo che Kubernetes pubblichi la porta 80 nel servizio in una porta arbitraria sui socket di rete esterni del cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-200">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="79f69-201">La porta assegnata può essere trovata tramite `kubectl get service` il comando.</span><span class="sxs-lookup"><span data-stu-id="79f69-201">The port assigned can be found using the `kubectl get service` command.</span></span>

<span data-ttu-id="79f69-202">Il `stockdata` servizio non deve essere accessibile dall'esterno del cluster, quindi ha usato il `ClusterIP`tipo predefinito.</span><span class="sxs-lookup"><span data-stu-id="79f69-202">The `stockdata` service shouldn't be accessible from outside the cluster, so it used the default type, `ClusterIP`.</span></span>

<span data-ttu-id="79f69-203">I sistemi di produzione utilizzeranno con maggiore probabilità un servizio di bilanciamento del carico integrato per esporre le applicazioni pubbliche a utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="79f69-203">Production systems will most likely use an integrated load-balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="79f69-204">I servizi esposti in questo modo devono usare `LoadBalancer` il tipo.</span><span class="sxs-lookup"><span data-stu-id="79f69-204">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="79f69-205">Per ulteriori informazioni sui tipi di servizio, vedere la documentazione relativa ai [servizi di pubblicazione Kubernetes](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .</span><span class="sxs-lookup"><span data-stu-id="79f69-205">For more information on service types, see the [Kubernetes' Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="79f69-206">Distribuire l'applicazione StockWeb</span><span class="sxs-lookup"><span data-stu-id="79f69-206">Deploy the StockWeb application</span></span>

<span data-ttu-id="79f69-207">Utilizzare `kubectl` per applicare il `stockweb.yml` file e verificare che la distribuzione e il servizio siano stati creati.</span><span class="sxs-lookup"><span data-stu-id="79f69-207">Use `kubectl` to apply the `stockweb.yml` file and check that the Deployment and Service were created.</span></span>

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

<span data-ttu-id="79f69-208">L'output `get service` del comando Mostra che la porta HTTP è stata pubblicata sulla porta `32564` sulla rete esterna. per Docker desktop, questo sarà localhost.</span><span class="sxs-lookup"><span data-stu-id="79f69-208">The output from the `get service` command shows that the HTTP port has been published to port `32564` on the external network; for Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="79f69-209">Per accedere all'applicazione, è possibile passare `http://localhost:32564`a.</span><span class="sxs-lookup"><span data-stu-id="79f69-209">The application can be accessed by browsing to `http://localhost:32564`.</span></span>

### <a name="testing-the-application"></a><span data-ttu-id="79f69-210">Test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="79f69-210">Testing the application</span></span>

<span data-ttu-id="79f69-211">L'applicazione StockWeb Visualizza un elenco delle scorte del NASDAQ che vengono recuperate da un semplice servizio request/reply.</span><span class="sxs-lookup"><span data-stu-id="79f69-211">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="79f69-212">A scopo dimostrativo, ogni riga Mostra anche l'ID univoco dell'istanza del servizio che lo ha restituito.</span><span class="sxs-lookup"><span data-stu-id="79f69-212">For demonstration purposes, each line also shows the unique ID of the service instance that returned it.</span></span>

![Schermata StockWeb](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="79f69-214">Se il numero di repliche del `stockdata` servizio è aumentato, è possibile che il valore del **server** cambi da riga a riga, ma che tutti i record 100 vengano sempre restituiti dalla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="79f69-214">If the number of replicas of the `stockdata` service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="79f69-215">Se si aggiorna la pagina a intervalli di pochi secondi, l'ID del server rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="79f69-215">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="79f69-216">Perché si verifica questo problema?</span><span class="sxs-lookup"><span data-stu-id="79f69-216">Why does this happen?</span></span> <span data-ttu-id="79f69-217">Ci sono due fattori da giocare qui.</span><span class="sxs-lookup"><span data-stu-id="79f69-217">There are two factors at play here.</span></span>

<span data-ttu-id="79f69-218">In primo luogo, il sistema di individuazione del servizio Kubernetes usa il bilanciamento del carico "Round Robin" per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="79f69-218">First, the Kubernetes service discovery system uses "round-robin" load-balancing by default.</span></span> <span data-ttu-id="79f69-219">La prima volta che si esegue una query sul server DNS, viene restituito il primo indirizzo IP corrispondente per il servizio.</span><span class="sxs-lookup"><span data-stu-id="79f69-219">The first time the DNS server is queried, it will return the first matching IP address for the service.</span></span> <span data-ttu-id="79f69-220">La volta successiva, l'indirizzo IP successivo nell'elenco e così via fino alla fine, a quel punto viene eseguito il loopback fino all'inizio.</span><span class="sxs-lookup"><span data-stu-id="79f69-220">The next time, the next IP address in the list, and so on, until the end, at which point it loops back to the start.</span></span>

<span data-ttu-id="79f69-221">In secondo luogo `HttpClient` , il usato per il client gRPC dell'applicazione StockWeb viene creato e gestito dal [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)e una singola istanza di questo client viene usata per ogni chiamata alla pagina.</span><span class="sxs-lookup"><span data-stu-id="79f69-221">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="79f69-222">Il client esegue solo una ricerca DNS, quindi tutte le richieste vengono instradate allo stesso indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="79f69-222">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="79f69-223">Inoltre, poiché il `HttpClientHandler` viene memorizzato nella cache per motivi di prestazioni, più richieste in rapida successione utilizzeranno *tutti* lo stesso indirizzo IP, fino alla scadenza della voce DNS memorizzata nella cache o all'eliminazione dell'istanza del gestore per qualche motivo.</span><span class="sxs-lookup"><span data-stu-id="79f69-223">Furthermore, because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="79f69-224">Ciò significa che per impostazione predefinita le richieste a un servizio gRPC non sono bilanciate tra tutte le istanze del servizio nel cluster.</span><span class="sxs-lookup"><span data-stu-id="79f69-224">This means that by default requests to a gRPC service aren't balanced across all instances of that service in the cluster.</span></span> <span data-ttu-id="79f69-225">Diversi consumer utilizzeranno istanze diverse, ma ciò non garantisce una distribuzione adeguata delle richieste e un uso bilanciato delle risorse.</span><span class="sxs-lookup"><span data-stu-id="79f69-225">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests and a balanced use of resources.</span></span>

<span data-ttu-id="79f69-226">Il capitolo successivo, [mesh dei servizi](service-mesh.md), esaminerà il modo in cui risolvere questo problema.</span><span class="sxs-lookup"><span data-stu-id="79f69-226">The next chapter, [Service Meshes](service-mesh.md), will look at how to address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="79f69-227">[Precedente](docker.md)
>[Successivo](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="79f69-227">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
