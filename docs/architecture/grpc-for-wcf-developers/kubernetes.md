---
title: Kubernetes-gRPC per sviluppatori WCF
description: Esecuzione di ASP.NET Core Servizi gRPC in un cluster Kubernetes.
ms.date: 09/02/2019
ms.openlocfilehash: 22271343f8f0d0454469b2f35e717f5b7e939294
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711281"
---
# <a name="kubernetes"></a><span data-ttu-id="fba1c-103">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fba1c-103">Kubernetes</span></span>

<span data-ttu-id="fba1c-104">Sebbene sia possibile eseguire manualmente i contenitori negli host Docker, per i sistemi di produzione affidabili è preferibile usare un motore di orchestrazione contenitore per gestire più istanze in esecuzione in più server in un cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-104">Although it's possible to run containers manually on Docker hosts, for reliable production systems it's better to use a container orchestration engine to manage multiple instances running across several servers in a cluster.</span></span> <span data-ttu-id="fba1c-105">Sono disponibili vari motori di orchestrazione del contenitore, tra cui Kubernetes, Docker Swarm e Apache Mesos.</span><span class="sxs-lookup"><span data-stu-id="fba1c-105">There are various container orchestration engines available, including Kubernetes, Docker Swarm, and Apache Mesos.</span></span> <span data-ttu-id="fba1c-106">Tuttavia, con questi motori, Kubernetes è molto più usato, quindi sarà l'obiettivo di questo capitolo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-106">But of these engines, Kubernetes is far and away the most widely used, so it will be the focus of this chapter.</span></span>

<span data-ttu-id="fba1c-107">Kubernetes include le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="fba1c-107">Kubernetes includes the following functionality:</span></span>

- <span data-ttu-id="fba1c-108">La **pianificazione** esegue i contenitori su più nodi all'interno di un cluster, garantendo un uso bilanciato della risorsa disponibile, mantenendo i contenitori in esecuzione in caso di interruzioni e gestendo gli aggiornamenti in sequenza alle nuove versioni di immagini o nuove configurazioni.</span><span class="sxs-lookup"><span data-stu-id="fba1c-108">**Scheduling** runs containers on multiple nodes within a cluster, ensuring balanced usage of the available resource, keeping containers running if there are outages, and handling rolling updates to new versions of images or new configurations.</span></span>
- <span data-ttu-id="fba1c-109">I **controlli di integrità** monitorano i contenitori per garantire un servizio continuo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-109">**Health checks** monitor containers to ensure continued service.</span></span>
- <span data-ttu-id="fba1c-110">Il **servizio di individuazione DNS &** gestisce il routing tra i servizi all'interno di un cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-110">**DNS & service discovery** handles routing between services within a cluster.</span></span>
- <span data-ttu-id="fba1c-111">Il traffico in **ingresso** espone i servizi selezionati esternamente e in genere fornisce il bilanciamento del carico tra le istanze di tali servizi.</span><span class="sxs-lookup"><span data-stu-id="fba1c-111">**Ingress** exposes selected services externally and generally provides load-balancing across instances of those services.</span></span>
- <span data-ttu-id="fba1c-112">**Gestione risorse** connette risorse esterne come l'archiviazione ai contenitori.</span><span class="sxs-lookup"><span data-stu-id="fba1c-112">**Resource management** attaches external resources like storage to containers.</span></span>

<span data-ttu-id="fba1c-113">In questo capitolo viene illustrato in dettaglio come distribuire un servizio ASP.NET Core gRPC e un sito Web che utilizza il servizio in un cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fba1c-113">This chapter will detail how to deploy an ASP.NET Core gRPC service and a website that consumes the service into a Kubernetes cluster.</span></span> <span data-ttu-id="fba1c-114">L'applicazione di esempio usata è disponibile nel repository [DotNet-Architecture/grpc-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="fba1c-114">The sample application used is available in the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="kubernetes-terminology"></a><span data-ttu-id="fba1c-115">Terminologia di Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fba1c-115">Kubernetes terminology</span></span>

<span data-ttu-id="fba1c-116">Kubernetes USA DSC ( *desired state Configuration*): l'API viene usata per descrivere oggetti come *Pod*, *distribuzioni*e *Servizi*e il *piano di controllo* si occupa dell'implementazione dello stato desiderato in tutti i *nodi* di un *cluster*.</span><span class="sxs-lookup"><span data-stu-id="fba1c-116">Kubernetes uses *desired state configuration*: the API is used to describe objects like *Pods*, *Deployments*, and *Services*, and the *Control Plane* takes care of implementing the desired state across all the *nodes* in a *cluster*.</span></span> <span data-ttu-id="fba1c-117">Un cluster Kubernetes dispone di un nodo *Master* che esegue l' *API Kubernetes*, che è possibile comunicare con a livello di codice o tramite lo strumento da riga di comando `kubectl`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-117">A Kubernetes cluster has a *Master* node that runs the *Kubernetes API*, which you can communicate with programmatically or by using the `kubectl` command-line tool.</span></span> <span data-ttu-id="fba1c-118">`kubectl` possibile creare e gestire oggetti tramite argomenti della riga di comando, ma funziona meglio con i file YAML che contengono dati di dichiarazione per gli oggetti Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fba1c-118">`kubectl` can create and manage objects through command-line arguments, but it works best with YAML files that contain declaration data for Kubernetes objects.</span></span>

### <a name="kubernetes-yaml-files"></a><span data-ttu-id="fba1c-119">File YAML Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fba1c-119">Kubernetes YAML files</span></span>

<span data-ttu-id="fba1c-120">Ogni file YAML di Kubernetes avrà almeno tre proprietà di primo livello:</span><span class="sxs-lookup"><span data-stu-id="fba1c-120">Every Kubernetes YAML file will have at least three top-level properties:</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

<span data-ttu-id="fba1c-121">La proprietà `apiVersion` viene utilizzata per specificare la versione (e l'API) per cui il file è destinato.</span><span class="sxs-lookup"><span data-stu-id="fba1c-121">The `apiVersion` property is used to specify which version (and which API) the file is intended for.</span></span> <span data-ttu-id="fba1c-122">La proprietà `kind` specifica il tipo di oggetto rappresentato da YAML.</span><span class="sxs-lookup"><span data-stu-id="fba1c-122">The `kind` property specifies the kind of object the YAML represents.</span></span> <span data-ttu-id="fba1c-123">La proprietà `metadata` contiene proprietà dell'oggetto, ad esempio `name`, `namespace`e `labels`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-123">The `metadata` property contains object properties like `name`, `namespace`, and `labels`.</span></span>

<span data-ttu-id="fba1c-124">La maggior parte dei file YAML di Kubernetes include anche una sezione `spec` che descrive le risorse e la configurazione necessarie per creare l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fba1c-124">Most Kubernetes YAML files will also have a `spec` section that describes the resources and configuration necessary to create the object.</span></span>

### <a name="pods"></a><span data-ttu-id="fba1c-125">Baccelli</span><span class="sxs-lookup"><span data-stu-id="fba1c-125">Pods</span></span>

<span data-ttu-id="fba1c-126">I pod sono le unità di base di esecuzione in Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fba1c-126">Pods are the basic units of execution in Kubernetes.</span></span> <span data-ttu-id="fba1c-127">Possono eseguire più contenitori, ma sono usati anche per eseguire singoli contenitori.</span><span class="sxs-lookup"><span data-stu-id="fba1c-127">They can run multiple containers, but they're also used to run single containers.</span></span> <span data-ttu-id="fba1c-128">Il Pod include anche le risorse di archiviazione richieste dai contenitori e l'indirizzo IP di rete.</span><span class="sxs-lookup"><span data-stu-id="fba1c-128">The pod also includes any storage resources required by the containers, and the network IP address.</span></span>

### <a name="services"></a><span data-ttu-id="fba1c-129">Servizi</span><span class="sxs-lookup"><span data-stu-id="fba1c-129">Services</span></span>

<span data-ttu-id="fba1c-130">I servizi sono metaoggetti che descrivono pod (o set di Pod) e forniscono un modo per accedervi all'interno del cluster, ad esempio il mapping di un nome di servizio a un set di indirizzi IP pod usando il servizio DNS del cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-130">Services are meta-objects that describe Pods (or sets of Pods) and provide a way to access them within the cluster, such as mapping a service name to a set of pod IP addresses by using the cluster DNS service.</span></span>

### <a name="deployments"></a><span data-ttu-id="fba1c-131">Distribuzioni</span><span class="sxs-lookup"><span data-stu-id="fba1c-131">Deployments</span></span>

<span data-ttu-id="fba1c-132">Le distribuzioni sono gli oggetti di *stato desiderati* per i pod.</span><span class="sxs-lookup"><span data-stu-id="fba1c-132">Deployments are the *desired state* objects for Pods.</span></span> <span data-ttu-id="fba1c-133">Se si crea un pod manualmente, non verrà riavviato al termine della fase.</span><span class="sxs-lookup"><span data-stu-id="fba1c-133">If you create a pod manually, it won't be restarted when it terminates.</span></span> <span data-ttu-id="fba1c-134">Le distribuzioni vengono usate per indicare al cluster quali pod e quante repliche di tali Pod devono essere in esecuzione al momento attuale.</span><span class="sxs-lookup"><span data-stu-id="fba1c-134">Deployments are used to tell the cluster which Pods, and how many replicas of those Pods, should be running at the present time.</span></span>

### <a name="other-objects"></a><span data-ttu-id="fba1c-135">Altri oggetti</span><span class="sxs-lookup"><span data-stu-id="fba1c-135">Other objects</span></span>

<span data-ttu-id="fba1c-136">Pod, servizi e distribuzioni sono solo tre dei tipi di oggetti di base.</span><span class="sxs-lookup"><span data-stu-id="fba1c-136">Pods, Services, and Deployments are just three of the most basic object types.</span></span> <span data-ttu-id="fba1c-137">Sono disponibili dozzine di altri tipi di oggetti gestiti dai cluster Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fba1c-137">There are dozens of other object types that are managed by Kubernetes clusters.</span></span> <span data-ttu-id="fba1c-138">Per ulteriori informazioni, vedere la documentazione relativa ai [concetti relativi a Kubernetes](https://kubernetes.io/docs/concepts/) .</span><span class="sxs-lookup"><span data-stu-id="fba1c-138">For more information, see the [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) documentation.</span></span>

### <a name="namespaces"></a><span data-ttu-id="fba1c-139">Spazi dei nomi</span><span class="sxs-lookup"><span data-stu-id="fba1c-139">Namespaces</span></span>

<span data-ttu-id="fba1c-140">I cluster Kubernetes sono progettati per la scalabilità a centinaia o migliaia di nodi e per l'esecuzione di un numero simile di servizi.</span><span class="sxs-lookup"><span data-stu-id="fba1c-140">Kubernetes clusters are designed to scale to hundreds or thousands of nodes and to run similar numbers of services.</span></span> <span data-ttu-id="fba1c-141">Per evitare conflitti tra i nomi degli oggetti, gli spazi dei nomi vengono utilizzati per raggruppare gli oggetti come parte delle applicazioni più grandi.</span><span class="sxs-lookup"><span data-stu-id="fba1c-141">To avoid clashes between object names, namespaces are used to group objects together as part of larger applications.</span></span> <span data-ttu-id="fba1c-142">I servizi di Kubernetes vengono eseguiti in uno spazio dei nomi `default`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-142">Kubernetes's own services run in a `default` namespace.</span></span> <span data-ttu-id="fba1c-143">Tutti gli oggetti utente devono essere creati nei rispettivi spazi dei nomi per evitare potenziali conflitti con gli oggetti predefiniti o altri tenant nel cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-143">All user objects should be created in their own namespaces to avoid potential clashes with default objects or other tenants in the cluster.</span></span>

## <a name="get-started-with-kubernetes"></a><span data-ttu-id="fba1c-144">Introduzione a Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fba1c-144">Get started with Kubernetes</span></span>

<span data-ttu-id="fba1c-145">Se si sta eseguendo Docker desktop per Windows o Docker desktop per Mac, Kubernetes è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="fba1c-145">If you're running Docker Desktop for Windows or Docker Desktop for Mac, Kubernetes is already available.</span></span> <span data-ttu-id="fba1c-146">È sufficiente abilitarla nella sezione **Kubernetes** della finestra **Impostazioni** :</span><span class="sxs-lookup"><span data-stu-id="fba1c-146">Just enable it in the **Kubernetes** section of the **Settings** window:</span></span>

![Abilitare Kubernetes in Docker desktop](media/kubernetes/enable-kubernetes-docker-desktop.png)

<span data-ttu-id="fba1c-148">Per eseguire un cluster Kubernetes locale in Linux, prendere in considerazione [minikube](https://github.com/kubernetes/minikube)o [MicroK8s](https://microk8s.io/) se la distribuzione di Linux supporta gli [snap](https://snapcraft.io/).</span><span class="sxs-lookup"><span data-stu-id="fba1c-148">To run a local Kubernetes cluster on Linux, consider [minikube](https://github.com/kubernetes/minikube), or [MicroK8s](https://microk8s.io/) if your Linux distribution supports [snaps](https://snapcraft.io/).</span></span>

<span data-ttu-id="fba1c-149">Per verificare che il cluster sia in esecuzione e accessibile, eseguire il comando `kubectl version`:</span><span class="sxs-lookup"><span data-stu-id="fba1c-149">To confirm that your cluster is running and accessible, run the `kubectl version` command:</span></span>

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:13:49Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"14", GitVersion:"v1.14.6", GitCommit:"96fac5cd13a5dc064f7d9f4f23030a6aeface6cc", GitTreeState:"clean", BuildDate:"2019-08-19T11:05:16Z", GoVersion:"go1.12.9", Compiler:"gc", Platform:"linux/amd64"}
```

<span data-ttu-id="fba1c-150">In questo esempio, sia l'interfaccia della riga di comando di `kubectl` che il server Kubernetes eseguono la versione 1.14.6.</span><span class="sxs-lookup"><span data-stu-id="fba1c-150">In this example, both the `kubectl` CLI and the Kubernetes server are running version 1.14.6.</span></span> <span data-ttu-id="fba1c-151">Ogni versione di `kubectl` dovrebbe supportare la versione precedente e successiva del server, pertanto `kubectl` 1,14 dovrebbe funzionare anche con le versioni del server 1,13 e 1,15.</span><span class="sxs-lookup"><span data-stu-id="fba1c-151">Each version of `kubectl` is supposed to support the previous and next version of the server, so `kubectl` 1.14 should work with server versions 1.13 and 1.15 as well.</span></span>

## <a name="run-services-on-kubernetes"></a><span data-ttu-id="fba1c-152">Eseguire i servizi in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="fba1c-152">Run services on Kubernetes</span></span>

<span data-ttu-id="fba1c-153">L'applicazione di esempio ha una `kube` directory che contiene tre file YAML.</span><span class="sxs-lookup"><span data-stu-id="fba1c-153">The sample application has a `kube` directory that contains three YAML files.</span></span> <span data-ttu-id="fba1c-154">Il file di `namespace.yml` dichiara uno spazio dei nomi personalizzato: `stocks`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-154">The `namespace.yml` file declares a custom namespace: `stocks`.</span></span> <span data-ttu-id="fba1c-155">Il file di `stockdata.yml` dichiara la distribuzione e il servizio per l'applicazione gRPC e il file di `stockweb.yml` dichiara la distribuzione e il servizio per un'applicazione Web MVC ASP.NET Core 3,0 che usa il servizio gRPC.</span><span class="sxs-lookup"><span data-stu-id="fba1c-155">The `stockdata.yml` file declares the Deployment and the Service for the gRPC application, and the `stockweb.yml` file declares the Deployment and Service for an ASP.NET Core 3.0 MVC web application that consumes the gRPC service.</span></span>

<span data-ttu-id="fba1c-156">Per usare un file di `YAML` con `kubectl`, eseguire il comando `apply -f`:</span><span class="sxs-lookup"><span data-stu-id="fba1c-156">To use a `YAML` file with `kubectl`, run the `apply -f` command:</span></span>

```console
kubectl apply -f object.yml
```

<span data-ttu-id="fba1c-157">Il comando `apply` verificherà la validità del file YAML e visualizzerà gli eventuali errori ricevuti dall'API, ma non attenderà che tutti gli oggetti dichiarati nel file siano stati creati perché questa operazione può richiedere del tempo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-157">The `apply` command will check the validity of the YAML file and display any errors received from the API, but doesn't wait until all the objects declared in the file have been created because this can take some time.</span></span> <span data-ttu-id="fba1c-158">Usare il comando `kubectl get` con i tipi di oggetto pertinenti per verificare la creazione di oggetti nel cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-158">Use the `kubectl get` command with the relevant object types to check on object creation in the cluster.</span></span>

### <a name="the-namespace-declaration"></a><span data-ttu-id="fba1c-159">Dichiarazione dello spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="fba1c-159">The namespace declaration</span></span>

<span data-ttu-id="fba1c-160">La dichiarazione dello spazio dei nomi è semplice e richiede solo l'assegnazione di un `name`:</span><span class="sxs-lookup"><span data-stu-id="fba1c-160">Namespace declaration is simple and requires only assigning a `name`:</span></span>

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

<span data-ttu-id="fba1c-161">Utilizzare `kubectl` per applicare il file di `namespace.yml` e verificare che lo spazio dei nomi venga creato correttamente:</span><span class="sxs-lookup"><span data-stu-id="fba1c-161">Use `kubectl` to apply the `namespace.yml` file and to confirm the namespace is created successfully:</span></span>

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a><span data-ttu-id="fba1c-162">Applicazione StockData</span><span class="sxs-lookup"><span data-stu-id="fba1c-162">The StockData application</span></span>

<span data-ttu-id="fba1c-163">Il file di `stockdata.yml` dichiara due oggetti: una distribuzione e un servizio.</span><span class="sxs-lookup"><span data-stu-id="fba1c-163">The `stockdata.yml` file declares two objects: a Deployment and a Service.</span></span>

#### <a name="the-stockdata-deployment"></a><span data-ttu-id="fba1c-164">Distribuzione di StockData</span><span class="sxs-lookup"><span data-stu-id="fba1c-164">The StockData Deployment</span></span>

<span data-ttu-id="fba1c-165">La parte relativa alla distribuzione del file YAML fornisce le `spec` per la distribuzione stessa, incluso il numero di repliche necessarie e un `template` per la creazione e la gestione degli oggetti pod da parte della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fba1c-165">The Deployment part of the YAML file provides the `spec` for the deployment itself, including the number of replicas required, and a `template` for the Pod objects to be created and managed by the deployment.</span></span> <span data-ttu-id="fba1c-166">Si noti che gli oggetti di distribuzione vengono gestiti dall'API di `apps`, come specificato in `apiVersion`, invece che dall'API Kubernetes principale.</span><span class="sxs-lookup"><span data-stu-id="fba1c-166">Note that Deployment objects are managed by the `apps` API, as specified in `apiVersion`, rather than the main Kubernetes API.</span></span>

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

<span data-ttu-id="fba1c-167">La proprietà `spec.selector` viene utilizzata per associare i pod in esecuzione alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="fba1c-167">The `spec.selector` property is used to match running Pods to the Deployment.</span></span> <span data-ttu-id="fba1c-168">La proprietà `metadata.labels` del Pod deve corrispondere alla proprietà `matchLabels` o la chiamata API avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-168">The Pod's `metadata.labels` property must match the `matchLabels` property or the API call will fail.</span></span>

<span data-ttu-id="fba1c-169">La sezione `template.spec` dichiara il contenitore da eseguire.</span><span class="sxs-lookup"><span data-stu-id="fba1c-169">The `template.spec` section declares the container to be run.</span></span> <span data-ttu-id="fba1c-170">Quando si usa un cluster Kubernetes locale, ad esempio quello fornito da Docker desktop, è possibile specificare le immagini che sono state compilate localmente, purché dispongano di un tag Version.</span><span class="sxs-lookup"><span data-stu-id="fba1c-170">When you're working with a local Kubernetes cluster, such as the one provided by Docker Desktop, you can specify images that were built locally as long as they have a version tag.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fba1c-171">Per impostazione predefinita, Kubernetes verificherà sempre e tenterà di eseguire il pull di una nuova immagine.</span><span class="sxs-lookup"><span data-stu-id="fba1c-171">By default, Kubernetes will always check for and try to pull a new image.</span></span> <span data-ttu-id="fba1c-172">Se non riesce a trovare l'immagine in uno dei repository noti, la creazione del Pod avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-172">If it can't find the image in any of its known repositories, the Pod creation will fail.</span></span> <span data-ttu-id="fba1c-173">Per usare le immagini locali, impostare il `imagePullPolicy` su `Never`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-173">To work with local images, set the `imagePullPolicy` to `Never`.</span></span>

<span data-ttu-id="fba1c-174">La proprietà `ports` specifica quali porte del contenitore devono essere pubblicate sul Pod.</span><span class="sxs-lookup"><span data-stu-id="fba1c-174">The `ports` property specifies which container ports should be published on the Pod.</span></span> <span data-ttu-id="fba1c-175">L'immagine `stockservice` esegue il servizio sulla porta HTTP standard, quindi viene pubblicata la porta 80.</span><span class="sxs-lookup"><span data-stu-id="fba1c-175">The `stockservice` image runs the service on the standard HTTP port, so port 80 is published.</span></span>

<span data-ttu-id="fba1c-176">La sezione `resources` applica i limiti delle risorse al contenitore in esecuzione nel pod.</span><span class="sxs-lookup"><span data-stu-id="fba1c-176">The `resources` section applies resource limits to the container running within the Pod.</span></span> <span data-ttu-id="fba1c-177">Si tratta di una procedura consigliata perché impedisce a un singolo pod di consumare tutta la CPU o la memoria disponibile in un nodo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-177">This is a good practice because it prevents an individual Pod from consuming all the available CPU or memory on a node.</span></span>

> [!NOTE]
> <span data-ttu-id="fba1c-178">ASP.NET Core 3,0 è stato ottimizzato e ottimizzato per l'esecuzione in contenitori con limitazioni di risorse.</span><span class="sxs-lookup"><span data-stu-id="fba1c-178">ASP.NET Core 3.0 has been optimized and tuned to run in resource-limited containers.</span></span> <span data-ttu-id="fba1c-179">L'immagine Docker `dotnet/core/aspnet` imposta una variabile di ambiente per indicare al runtime di `dotnet` che si trova in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="fba1c-179">The `dotnet/core/aspnet` Docker image sets an environment variable to tell the `dotnet` runtime that it's in a container.</span></span>

#### <a name="the-stockdata-service"></a><span data-ttu-id="fba1c-180">Il servizio StockData</span><span class="sxs-lookup"><span data-stu-id="fba1c-180">The StockData Service</span></span>

<span data-ttu-id="fba1c-181">La parte del servizio del file YAML dichiara il servizio che fornisce l'accesso ai pod all'interno del cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-181">The Service part of the YAML file declares the service that provides access to the Pods within the cluster.</span></span>

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

<span data-ttu-id="fba1c-182">Il `spec` del servizio usa la proprietà `selector` per trovare la corrispondenza dell'esecuzione `Pods`, in questo caso la ricerca di Pod con etichetta `run: stockdata`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-182">The Service `spec` uses the `selector` property to match running `Pods`, in this case looking for Pods that have a label `run: stockdata`.</span></span> <span data-ttu-id="fba1c-183">Il `port` specificato nei Pod corrispondenti viene pubblicato dal servizio denominato.</span><span class="sxs-lookup"><span data-stu-id="fba1c-183">The specified `port` on matching Pods is published by the named service.</span></span> <span data-ttu-id="fba1c-184">Gli altri pod in esecuzione nello spazio dei nomi `stocks` possono accedere a HTTP su questo servizio usando `http://stockdata` come indirizzo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-184">Other Pods running in the `stocks` namespace can access HTTP on this service by using `http://stockdata` as the address.</span></span> <span data-ttu-id="fba1c-185">I pod in esecuzione in altri spazi dei nomi possono usare il nome host `http://stockdata.stocks`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-185">Pods running in other namespaces can use the `http://stockdata.stocks` host name.</span></span> <span data-ttu-id="fba1c-186">È possibile controllare l'accesso al servizio tra gli spazi dei nomi usando i [criteri di rete](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span><span class="sxs-lookup"><span data-stu-id="fba1c-186">You can control cross-namespace service access by using [Network Policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/).</span></span>

#### <a name="deploy-the-stockdata-application"></a><span data-ttu-id="fba1c-187">Distribuire l'applicazione StockData</span><span class="sxs-lookup"><span data-stu-id="fba1c-187">Deploy the StockData application</span></span>

<span data-ttu-id="fba1c-188">Usare `kubectl` per applicare il file di `stockdata.yml` e verificare che la distribuzione e il servizio siano stati creati:</span><span class="sxs-lookup"><span data-stu-id="fba1c-188">Use `kubectl` to apply the `stockdata.yml` file and confirm that the Deployment and Service were created:</span></span>

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

### <a name="the-stockweb-application"></a><span data-ttu-id="fba1c-189">Applicazione StockWeb</span><span class="sxs-lookup"><span data-stu-id="fba1c-189">The StockWeb application</span></span>

<span data-ttu-id="fba1c-190">Il file di `stockweb.yml` dichiara la distribuzione e il servizio per l'applicazione MVC.</span><span class="sxs-lookup"><span data-stu-id="fba1c-190">The `stockweb.yml` file declares the Deployment and Service for the MVC application.</span></span>

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

#### <a name="environment-variables"></a><span data-ttu-id="fba1c-191">Variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="fba1c-191">Environment variables</span></span>

<span data-ttu-id="fba1c-192">La sezione `env` dell'oggetto di distribuzione specifica le variabili di ambiente da impostare nel contenitore in cui sono in esecuzione le immagini del `stockweb:1.0.0`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-192">The `env` section of the Deployment object specifies environment variables to be set in the container that's running the `stockweb:1.0.0` images.</span></span>

<span data-ttu-id="fba1c-193">La variabile di ambiente **`StockData__Address`** viene mappata all'impostazione di configurazione `StockData:Address` grazie al provider di configurazione EnvironmentVariables.</span><span class="sxs-lookup"><span data-stu-id="fba1c-193">The **`StockData__Address`** environment variable will map to the `StockData:Address` configuration setting thanks to the EnvironmentVariables configuration provider.</span></span> <span data-ttu-id="fba1c-194">Questa impostazione Usa doppi caratteri di sottolineatura tra i nomi per separare le sezioni.</span><span class="sxs-lookup"><span data-stu-id="fba1c-194">This setting uses double underscores between names to separate sections.</span></span> <span data-ttu-id="fba1c-195">L'indirizzo USA il nome del servizio `stockdata`, che viene eseguito nello stesso spazio dei nomi Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="fba1c-195">The address uses the service name of the `stockdata` Service, which is running in the same Kubernetes namespace.</span></span>

<span data-ttu-id="fba1c-196">La variabile di ambiente **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** imposta un'opzione di <xref:System.AppContext> che consente connessioni http/2 non crittografate per <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="fba1c-196">The **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** environment variable sets an <xref:System.AppContext> switch that enables unencrypted HTTP/2 connections for <xref:System.Net.Http.HttpClient>.</span></span> <span data-ttu-id="fba1c-197">Questa variabile di ambiente equivale a impostare l'opzione nel codice, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fba1c-197">This environment variable does the same thing as setting the switch in code, as shown here:</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="fba1c-198">Se si usa una variabile di ambiente per l'opzione, è possibile modificare facilmente il contesto a seconda del contesto in cui l'applicazione è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fba1c-198">If you use an environment variable for the switch, you can easily change the context depending on the context in which the application is running.</span></span>

#### <a name="service-types"></a><span data-ttu-id="fba1c-199">Tipi di servizio</span><span class="sxs-lookup"><span data-stu-id="fba1c-199">Service types</span></span>

<span data-ttu-id="fba1c-200">La proprietà `type: NodePort` viene utilizzata per rendere accessibile l'applicazione Web dall'esterno del cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-200">The `type: NodePort` property is used to make the web application accessible from outside the cluster.</span></span> <span data-ttu-id="fba1c-201">Questo tipo di proprietà fa in modo che Kubernetes pubblichi la porta 80 nel servizio in una porta arbitraria sui socket di rete esterni del cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-201">This property type causes Kubernetes to publish port 80 on the Service to an arbitrary port on the cluster's external network sockets.</span></span> <span data-ttu-id="fba1c-202">È possibile trovare la porta assegnata usando il comando `kubectl get service`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-202">You can find the assigned port by using the `kubectl get service` command.</span></span>

<span data-ttu-id="fba1c-203">Il servizio `stockdata` non deve essere accessibile dall'esterno del cluster, quindi usa il tipo predefinito, `ClusterIP`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-203">The `stockdata` Service shouldn't be accessible from outside the cluster, so it uses the default type, `ClusterIP`.</span></span>

<span data-ttu-id="fba1c-204">I sistemi di produzione utilizzeranno con maggiore probabilità un servizio di bilanciamento del carico integrato per esporre le applicazioni pubbliche a utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="fba1c-204">Production systems will most likely use an integrated load balancer to expose public applications to external consumers.</span></span> <span data-ttu-id="fba1c-205">I servizi esposti in questo modo devono usare il tipo di `LoadBalancer`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-205">Services exposed in this way should use the `LoadBalancer` type.</span></span>

<span data-ttu-id="fba1c-206">Per ulteriori informazioni sui tipi di servizio, vedere la documentazione di [Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .</span><span class="sxs-lookup"><span data-stu-id="fba1c-206">For more information on Service types, see the [Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) documentation.</span></span>

#### <a name="deploy-the-stockweb-application"></a><span data-ttu-id="fba1c-207">Distribuire l'applicazione StockWeb</span><span class="sxs-lookup"><span data-stu-id="fba1c-207">Deploy the StockWeb application</span></span>

<span data-ttu-id="fba1c-208">Usare `kubectl` per applicare il file di `stockweb.yml` e verificare che la distribuzione e il servizio siano stati creati:</span><span class="sxs-lookup"><span data-stu-id="fba1c-208">Use `kubectl` to apply the `stockweb.yml` file and confirm that the Deployment and Service were created:</span></span>

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

<span data-ttu-id="fba1c-209">L'output del comando `get service` indica che la porta HTTP è stata pubblicata sulla porta 32564 sulla rete esterna.</span><span class="sxs-lookup"><span data-stu-id="fba1c-209">The output of the `get service` command shows that the HTTP port has been published to port 32564 on the external network.</span></span> <span data-ttu-id="fba1c-210">Per Docker desktop, questo sarà localhost.</span><span class="sxs-lookup"><span data-stu-id="fba1c-210">For Docker Desktop, this will be localhost.</span></span> <span data-ttu-id="fba1c-211">È possibile accedere all'applicazione passando a `http://localhost:32564`.</span><span class="sxs-lookup"><span data-stu-id="fba1c-211">You can access the application by browsing to `http://localhost:32564`.</span></span>

### <a name="test-the-application"></a><span data-ttu-id="fba1c-212">Testare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="fba1c-212">Test the application</span></span>

<span data-ttu-id="fba1c-213">L'applicazione StockWeb Visualizza un elenco delle scorte del NASDAQ che vengono recuperate da un semplice servizio request/reply.</span><span class="sxs-lookup"><span data-stu-id="fba1c-213">The StockWeb application displays a list of NASDAQ stocks that are retrieved from a simple request-reply service.</span></span> <span data-ttu-id="fba1c-214">Per questa dimostrazione, ogni riga Mostra anche l'ID univoco dell'istanza del servizio che lo ha restituito.</span><span class="sxs-lookup"><span data-stu-id="fba1c-214">For this demonstration, each line also shows the unique ID of the Service instance that returned it.</span></span>

![Schermata StockWeb](media/kubernetes/stockweb-screenshot.png)

<span data-ttu-id="fba1c-216">Se il numero di repliche del servizio `stockdata` è stato aumentato, è possibile che il valore del **Server** venga modificato da riga a riga, ma di fatto tutti i record 100 vengono sempre restituiti dalla stessa istanza.</span><span class="sxs-lookup"><span data-stu-id="fba1c-216">If the number of replicas of the `stockdata` Service were increased, you might expect the **Server** value to change from line to line, but in fact all 100 records are always returned from the same instance.</span></span> <span data-ttu-id="fba1c-217">Se si aggiorna la pagina a intervalli di pochi secondi, l'ID del server rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="fba1c-217">If you refresh the page every few seconds, the server ID remains the same.</span></span> <span data-ttu-id="fba1c-218">Perché si verifica questo problema?</span><span class="sxs-lookup"><span data-stu-id="fba1c-218">Why does this happen?</span></span> <span data-ttu-id="fba1c-219">Ci sono due fattori da giocare qui.</span><span class="sxs-lookup"><span data-stu-id="fba1c-219">There are two factors at play here.</span></span>

<span data-ttu-id="fba1c-220">Per prima cosa, il sistema di individuazione del servizio Kubernetes usa il bilanciamento del carico Round Robin per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fba1c-220">First, the Kubernetes Service discovery system uses round-robin load balancing by default.</span></span> <span data-ttu-id="fba1c-221">La prima volta che si esegue una query sul server DNS, viene restituito il primo indirizzo IP corrispondente per il servizio.</span><span class="sxs-lookup"><span data-stu-id="fba1c-221">The first time the DNS server is queried, it will return the first matching IP address for the Service.</span></span> <span data-ttu-id="fba1c-222">La volta successiva, restituirà l'indirizzo IP successivo nell'elenco e così via fino alla fine.</span><span class="sxs-lookup"><span data-stu-id="fba1c-222">The next time, it will return the next IP address in the list, and so on, until the end.</span></span> <span data-ttu-id="fba1c-223">A questo punto viene eseguito il loopback fino all'inizio.</span><span class="sxs-lookup"><span data-stu-id="fba1c-223">At that point it loops back to the start.</span></span>

<span data-ttu-id="fba1c-224">In secondo luogo, il `HttpClient` usato per il client gRPC dell'applicazione StockWeb viene creato e gestito da [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)e una singola istanza di questo client viene usata per ogni chiamata alla pagina.</span><span class="sxs-lookup"><span data-stu-id="fba1c-224">Second, the `HttpClient` used for the StockWeb application's gRPC client is created and managed by the [ASP.NET Core HttpClientFactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md), and a single instance of this client is used for every call to the page.</span></span> <span data-ttu-id="fba1c-225">Il client esegue solo una ricerca DNS, quindi tutte le richieste vengono instradate allo stesso indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="fba1c-225">The client only does one DNS lookup, so all requests are routed to the same IP address.</span></span> <span data-ttu-id="fba1c-226">Poiché il `HttpClientHandler` viene memorizzato nella cache per motivi di prestazioni, più richieste in rapida successione utilizzeranno *tutti* lo stesso indirizzo IP, fino alla scadenza della voce DNS memorizzata nella cache o all'eliminazione dell'istanza del gestore per qualche motivo.</span><span class="sxs-lookup"><span data-stu-id="fba1c-226">And because the `HttpClientHandler` is cached for performance reasons, multiple requests in quick succession will *all* use the same IP address, until the cached DNS entry expires or the handler instance is disposed for some reason.</span></span>

<span data-ttu-id="fba1c-227">Il risultato è che, per impostazione predefinita, le richieste a un servizio gRPC non sono bilanciate tra tutte le istanze del servizio nel cluster.</span><span class="sxs-lookup"><span data-stu-id="fba1c-227">The result is that by default requests to a gRPC Service aren't balanced across all instances of that Service in the cluster.</span></span> <span data-ttu-id="fba1c-228">Diversi consumer utilizzeranno istanze diverse, ma ciò non garantisce una distribuzione adeguata delle richieste o un uso bilanciato delle risorse.</span><span class="sxs-lookup"><span data-stu-id="fba1c-228">Different consumers will use different instances, but that doesn't guarantee a good distribution of requests or a balanced use of resources.</span></span>

<span data-ttu-id="fba1c-229">Il capitolo successivo, [mesh del servizio](service-mesh.md), risolverà questo problema.</span><span class="sxs-lookup"><span data-stu-id="fba1c-229">The next chapter, [Service meshes](service-mesh.md), will address this problem.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fba1c-230">[Precedente](docker.md)
>[Successivo](service-mesh.md)</span><span class="sxs-lookup"><span data-stu-id="fba1c-230">[Previous](docker.md)
[Next](service-mesh.md)</span></span>
