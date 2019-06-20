---
title: Compilare applicazioni ASP.NET Core 2.2 distribuite come contenitori Linux nell'agente nei cluster AKS/Kubernetes
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
ms.date: 02/25/2019
ms.openlocfilehash: 89843e0041c12f001f974360da2e5903499155d1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644788"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="f401b-103">Compilare applicazioni ASP.NET Core 2.2 distribuite come contenitori Linux in un agente di orchestrazione AKS/Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f401b-103">Build ASP.NET Core 2.2 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="f401b-104">Servizio Azure Kubernetes (AKS) include i servizi di orchestrazione Kubernetes gestiti di Azure che semplificano la gestione e la distribuzione dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="f401b-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="f401b-105">Le funzionalità principali di AKS sono:</span><span class="sxs-lookup"><span data-stu-id="f401b-105">AKS main features are:</span></span>

- <span data-ttu-id="f401b-106">Un piano di controllo ospitato in Azure</span><span class="sxs-lookup"><span data-stu-id="f401b-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="f401b-107">Aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="f401b-107">Automated upgrades</span></span>
- <span data-ttu-id="f401b-108">Riparazione automatica</span><span class="sxs-lookup"><span data-stu-id="f401b-108">Self-healing</span></span>
- <span data-ttu-id="f401b-109">Ridimensionamento configurabile dall'utente</span><span class="sxs-lookup"><span data-stu-id="f401b-109">User configurable scaling</span></span>
- <span data-ttu-id="f401b-110">Un'esperienza utente più semplice sia per gli sviluppatori che per gli operatori di cluster.</span><span class="sxs-lookup"><span data-stu-id="f401b-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="f401b-111">Negli esempi seguenti viene illustrata la creazione di un'applicazione ASP.NET Core 2.2 che viene eseguita in Linux e distribuita in un cluster AKS in Azure, mentre lo sviluppo avviene con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f401b-111">The following examples explore the creation of an ASP.NET Core 2.2 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a><span data-ttu-id="f401b-112">Creazione del progetto ASP.NET Core 2.2 con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="f401b-112">Creating the ASP.NET Core 2.2 Project using Visual Studio 2017</span></span>

<span data-ttu-id="f401b-113">ASP.NET Core è una piattaforma di sviluppo generale gestita da Microsoft e dalla community .NET su GitHub.</span><span class="sxs-lookup"><span data-stu-id="f401b-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="f401b-114">È multipiattaforma, supporta Windows, macOS e Linux e può essere usata in dispositivi, ambienti cloud e scenari IoT/incorporati.</span><span class="sxs-lookup"><span data-stu-id="f401b-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="f401b-115">Questo esempio usa un semplice progetto che si basa su un modello API Web di Visual Studio, quindi non occorre alcuna conoscenza aggiuntiva per creare il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="f401b-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="f401b-116">È sufficiente creare il progetto usando un modello standard che include tutti gli elementi per eseguire un progetto di piccole dimensioni con un'API REST, con la tecnologia ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f401b-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.2 technology.</span></span>

![Finestra di aggiunta di un nuovo progetto in Visual Studio, con selezione di un'applicazione Web ASP.NET Core.](media/create-aspnet-core-application.png)

<span data-ttu-id="f401b-118">**Figura 4-36**.</span><span class="sxs-lookup"><span data-stu-id="f401b-118">**Figure 4-36**.</span></span> <span data-ttu-id="f401b-119">Creazione di un'applicazione ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f401b-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="f401b-120">Per creare il progetto di esempio in Visual Studio, selezionare **File** > **Nuovo** > **Progetto**, selezionare i tipi di progetto **Web**nel riquadro a sinistra e quindi **Applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f401b-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="f401b-121">Visual Studio elenca i modelli per i progetti Web.</span><span class="sxs-lookup"><span data-stu-id="f401b-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="f401b-122">Per questo esempio, selezionare **API** per creare un'applicazione API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f401b-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="f401b-123">Verificare di avere selezionato come framework ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="f401b-123">Verify that you've selected ASP.NET Core 2.2 as the framework.</span></span> <span data-ttu-id="f401b-124">.NET core 2.2 è incluso nell'ultima versione di Visual Studio 2017 e viene installato e configurato automaticamente quando si installa Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f401b-124">.NET Core 2.2 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Finestra di dialogo di Visual Studio per selezionare il tipo di applicazione Web ASP.NET Core con l'opzione API selezionata.](media/create-web-api-application.png)

<span data-ttu-id="f401b-126">**Figura 4-37**.</span><span class="sxs-lookup"><span data-stu-id="f401b-126">**Figure 4-37**.</span></span> <span data-ttu-id="f401b-127">Selezione di ASP.NET CORE 2.2 e del tipo di progetto API Web</span><span class="sxs-lookup"><span data-stu-id="f401b-127">Selecting ASP.NET CORE 2.2 and Web API project type</span></span>

<span data-ttu-id="f401b-128">Se si ha una versione precedente di .NET Core, è possibile scaricare e installare la versione 2.2 da <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="f401b-128">If you have any previous version of .NET Core, you can download and install the 2.2 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="f401b-129">È possibile aggiungere il supporto per Docker al momento della creazione del progetto o in seguito, in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="f401b-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="f401b-130">Per aggiungere il supporto per Docker dopo la creazione del progetto, fare clic con il pulsante destro del mouse sul nodo del progetto in Esplora soluzioni e selezionare **Aggiungi** > **Supporto Docker** nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="f401b-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Opzione del menu di scelta rapida per aggiungere il supporto per Docker a un progetto esistente: Fare clic con il pulsante destro sul progetto > Aggiungi > Supporto Docker.](media/add-docker-support-to-project.png)

<span data-ttu-id="f401b-132">**Figura 4-38**.</span><span class="sxs-lookup"><span data-stu-id="f401b-132">**Figure 4-38**.</span></span> <span data-ttu-id="f401b-133">Aggiunta del supporto per Docker a un progetto esistente</span><span class="sxs-lookup"><span data-stu-id="f401b-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="f401b-134">Per completare l'aggiunta del supporto per Docker, è possibile scegliere Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="f401b-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="f401b-135">In questo caso, selezionare **Linux**, in quanto AKS non supporta i contenitori di Windows (a partire da fine 2018).</span><span class="sxs-lookup"><span data-stu-id="f401b-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Finestra di dialogo delle opzioni per selezionare il sistema operativo di destinazione per Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="f401b-137">**Figura 4-39**.</span><span class="sxs-lookup"><span data-stu-id="f401b-137">**Figure 4-39**.</span></span> <span data-ttu-id="f401b-138">Selezione dei contenitori Linux.</span><span class="sxs-lookup"><span data-stu-id="f401b-138">Selecting Linux containers.</span></span>

<span data-ttu-id="f401b-139">Bastano questi semplici passaggi per avere un'applicazione ASP.NET Core 2.2 in esecuzione in un contenitore Linux.</span><span class="sxs-lookup"><span data-stu-id="f401b-139">With these simple steps, you have your ASP.NET Core 2.2 application running on a Linux container.</span></span>

<span data-ttu-id="f401b-140">Si noti come l'integrazione tra Visual Studio 2017 e Docker è totalmente orientata alla produttività dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="f401b-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="f401b-141">A questo punto è possibile eseguire l'applicazione premendo **F5** o il pulsante **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="f401b-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="f401b-142">Dopo aver eseguito il progetto, è possibile elencare le immagini usando il comando `docker images`.</span><span class="sxs-lookup"><span data-stu-id="f401b-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="f401b-143">Verrà visualizzata l'immagine `mssampleapplication` creata dalla distribuzione automatica del progetto con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="f401b-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![L'output della console del comando delle immagini Docker visualizza un elenco con: Repository, Tag, Image ID, Created (date) e Size.](media/docker-images-command.png)

<span data-ttu-id="f401b-145">**Figura 4-40**.</span><span class="sxs-lookup"><span data-stu-id="f401b-145">**Figure 4-40**.</span></span> <span data-ttu-id="f401b-146">Visualizzazione immagini Docker</span><span class="sxs-lookup"><span data-stu-id="f401b-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="f401b-147">Registrare la soluzione nel Registro Azure Container</span><span class="sxs-lookup"><span data-stu-id="f401b-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="f401b-148">Caricare l'immagine in un registro Docker, ad esempio [Registro Azure Container](https://azure.microsoft.com/services/container-registry/) o in Docker Hub, in modo che le immagini possano essere distribuite nel cluster AKS dal registro.</span><span class="sxs-lookup"><span data-stu-id="f401b-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="f401b-149">In questo caso l'immagine viene caricata nel Registro Azure Container.</span><span class="sxs-lookup"><span data-stu-id="f401b-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="f401b-150">Creare l'immagine in modalità Rilascio</span><span class="sxs-lookup"><span data-stu-id="f401b-150">Create the image in Release mode</span></span>

<span data-ttu-id="f401b-151">A questo punto viene creata l'immagine in modalità **Rilascio** (pronta per la produzione) modificando l'opzione relativa in **Rilascio**, come illustrato nella figura 4-41, ed eseguendo l'applicazione come in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f401b-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![Opzione della barra degli strumenti in Visual Studio per compilare in modalità di rilascio.](media/select-release-mode.png)

<span data-ttu-id="f401b-153">**Figura 4-41**.</span><span class="sxs-lookup"><span data-stu-id="f401b-153">**Figure 4-41**.</span></span> <span data-ttu-id="f401b-154">Selezione della modalità Rilascio</span><span class="sxs-lookup"><span data-stu-id="f401b-154">Selecting Release Mode</span></span>

<span data-ttu-id="f401b-155">Se si esegue il comando `docker image`, vengono visualizzate entrambe le immagini create, una per la modalità `debug` e l'altra per la modalità `release`.</span><span class="sxs-lookup"><span data-stu-id="f401b-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="f401b-156">Creare un nuovo tag per l'immagine</span><span class="sxs-lookup"><span data-stu-id="f401b-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="f401b-157">Ogni immagine del contenitore deve essere contrassegnata con il nome `loginServer` del registro.</span><span class="sxs-lookup"><span data-stu-id="f401b-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="f401b-158">Questo tag viene usato per il routing quando si esegue il push delle immagini del contenitore nel registro delle immagini.</span><span class="sxs-lookup"><span data-stu-id="f401b-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="f401b-159">È possibile visualizzare il nome `loginServer` dal portale di Azure. L'informazione deriva dal Registro Azure Container.</span><span class="sxs-lookup"><span data-stu-id="f401b-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Visualizzazione di esplorazione del nome del registro contenitori, in alto a destra.](media/loginServer-name.png)

<span data-ttu-id="f401b-161">**Figura 4-42**.</span><span class="sxs-lookup"><span data-stu-id="f401b-161">**Figure 4-42**.</span></span> <span data-ttu-id="f401b-162">Visualizzazione del nome del registro</span><span class="sxs-lookup"><span data-stu-id="f401b-162">View of the name of the Registry</span></span>

<span data-ttu-id="f401b-163">In alternativa, è possibile eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f401b-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Output della console del comando riportato sopra.](media/az-cli-loginServer-name.png)

<span data-ttu-id="f401b-165">**Figura 4-43**.</span><span class="sxs-lookup"><span data-stu-id="f401b-165">**Figure 4-43**.</span></span> <span data-ttu-id="f401b-166">Ottenere il nome del registro usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="f401b-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="f401b-167">In entrambi i casi, si ottiene il nome.</span><span class="sxs-lookup"><span data-stu-id="f401b-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="f401b-168">Nell'esempio il nome è `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="f401b-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="f401b-169">A questo punto è possibile contrassegnare l'immagine, prendendo l'immagine più recente (modalità Rilascio), con il comando:</span><span class="sxs-lookup"><span data-stu-id="f401b-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="f401b-170">Dopo aver eseguito il comando `docker tag`, elencare le immagini con il comando `docker images` che dovrebbe visualizzare l'immagine con il nuovo tag.</span><span class="sxs-lookup"><span data-stu-id="f401b-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Output della console del comando delle immagini Docker.](media/tagged-docker-images-list.png)

<span data-ttu-id="f401b-172">**Figura 4-44**.</span><span class="sxs-lookup"><span data-stu-id="f401b-172">**Figure 4-44**.</span></span> <span data-ttu-id="f401b-173">Visualizzazione di immagini con tag</span><span class="sxs-lookup"><span data-stu-id="f401b-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="f401b-174">Eseguire il push dell'immagine nel Registro Azure Container</span><span class="sxs-lookup"><span data-stu-id="f401b-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="f401b-175">Accedere al Registro Azure Container</span><span class="sxs-lookup"><span data-stu-id="f401b-175">Log in to the Azure Container Registry</span></span>

```console
az acr login --name mssampleacr
```

<span data-ttu-id="f401b-176">Eseguire il push dell'immagine nel Registro Azure Container usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f401b-176">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="f401b-177">Questo comando richiede un po' di tempo per caricare le immagini, ma offre feedback durante il processo.</span><span class="sxs-lookup"><span data-stu-id="f401b-177">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Output della console del comando di push di Docker: visualizza una barra di avanzamento basata su caratteri per ogni livello.](media/uploading-image-to-acr.png)

<span data-ttu-id="f401b-179">**Figura 4-45**.</span><span class="sxs-lookup"><span data-stu-id="f401b-179">**Figure 4-45**.</span></span> <span data-ttu-id="f401b-180">Caricamento dell'immagine nel Registro Azure Container</span><span class="sxs-lookup"><span data-stu-id="f401b-180">Uploading the image to the ACR</span></span>

<span data-ttu-id="f401b-181">È possibile visualizzare di seguito il risultato che dovrebbe essere visualizzato al termine del processo:</span><span class="sxs-lookup"><span data-stu-id="f401b-181">You can see below the result you should get when the process completes:</span></span>

![Output della console del comando di push di Docker, completato, che visualizza tutti i livelli o i nodi.](media/uploading-docker-images-complete.png)

<span data-ttu-id="f401b-183">**Figura 4-46**.</span><span class="sxs-lookup"><span data-stu-id="f401b-183">**Figure 4-46**.</span></span> <span data-ttu-id="f401b-184">Visualizzazione dei nodi</span><span class="sxs-lookup"><span data-stu-id="f401b-184">View of nodes</span></span>

<span data-ttu-id="f401b-185">Il passaggio successivo consiste nel distribuire il contenitore nel cluster AKS Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="f401b-185">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="f401b-186">A tale scopo, è necessario un file (**file di distribuzione con estensione yml**) che contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f401b-186">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - name: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> <span data-ttu-id="f401b-187">Per altre informazioni sulla distribuzione con Kubernetes, vedere: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="f401b-187">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="f401b-188">A questo punto si è quasi pronti per eseguire la distribuzione usando **Kubectl**, ma prima di tutto è necessario ottenere le credenziali per il cluster AKS con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f401b-188">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Output della console del comando riportato sopra: Merged "MSSampleK8Cluster as current context in  /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="f401b-190">**Figura 4-47**.</span><span class="sxs-lookup"><span data-stu-id="f401b-190">**Figure 4-47**.</span></span> <span data-ttu-id="f401b-191">Ottenere le credenziali</span><span class="sxs-lookup"><span data-stu-id="f401b-191">getting credentials</span></span>

<span data-ttu-id="f401b-192">Usare quindi il comando `kubectl create` per avviare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f401b-192">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Output della console del comando riportato sopra: deployment "mssamplesbook" created.](media/kubectl-create-command.png)

<span data-ttu-id="f401b-195">**Figura 4-48**.</span><span class="sxs-lookup"><span data-stu-id="f401b-195">**Figure 4-48**.</span></span> <span data-ttu-id="f401b-196">Eseguire la distribuzione in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f401b-196">Deploy to Kubernetes</span></span>

<span data-ttu-id="f401b-197">Al termine della distribuzione, è possibile accedere alla console di Kubernetes con un proxy locale cui è possibile accedere temporaneamente con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="f401b-197">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="f401b-198">In seguito, accedere all'URL `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="f401b-198">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Visualizzazione di esplorazione del dashboard Kubernetes, che visualizza le distribuzioni, i pod, i set di repliche e i servizi.](media/kubernetes-cluster-information.png)

<span data-ttu-id="f401b-200">**Figura 4-49**.</span><span class="sxs-lookup"><span data-stu-id="f401b-200">**Figure 4-49**.</span></span> <span data-ttu-id="f401b-201">Visualizzazione delle informazioni del cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f401b-201">View Kubernetes cluster information</span></span>

<span data-ttu-id="f401b-202">L'applicazione è stata distribuita in Azure usando un contenitore Linux e un cluster AKS Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="f401b-202">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="f401b-203">È possibile accedere all'app passando all'indirizzo IP pubblico del servizio, che può essere ottenuto dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="f401b-203">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="f401b-204">Per informazioni su come creare il cluster AKS per questo esempio, vedere la sezione [**Distribuire in servizio Azure Kubernetes**](deploy-azure-kubernetes-service.md) in questa Guida.</span><span class="sxs-lookup"><span data-stu-id="f401b-204">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f401b-205">[Precedente](set-up-windows-containers-with-powershell.md)
>[Successivo](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="f401b-205">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
