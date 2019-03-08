---
title: Creazione di applicazioni ASP.NET Core 2.1 distribuite come contenitori Linux nel cluster AKS/Kubernetes
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/25/2019
ms.openlocfilehash: c6d778d345466b1b852d06bc01ce40ccfdebf964
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676655"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a><span data-ttu-id="1151d-103">Creazione di applicazioni ASP.NET Core 2.1 distribuite come contenitori Linux in un servizio contenitore di AZURE/Kubernetes orchestrator</span><span class="sxs-lookup"><span data-stu-id="1151d-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into an AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="1151d-104">Servizi di Kubernetes Azure (AKS) è managed Kubernetes orchestrazioni i servizi di Azure che semplificano la gestione e distribuzione di contenitori.</span><span class="sxs-lookup"><span data-stu-id="1151d-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="1151d-105">Funzionalità principali di servizio contenitore di AZURE sono:</span><span class="sxs-lookup"><span data-stu-id="1151d-105">AKS main features are:</span></span>

- <span data-ttu-id="1151d-106">Un piano di controllo ospitato in Azure</span><span class="sxs-lookup"><span data-stu-id="1151d-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="1151d-107">Aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="1151d-107">Automated upgrades</span></span>
- <span data-ttu-id="1151d-108">Riparazione automatica</span><span class="sxs-lookup"><span data-stu-id="1151d-108">Self-healing</span></span>
- <span data-ttu-id="1151d-109">Ridimensionamento configurabile utente</span><span class="sxs-lookup"><span data-stu-id="1151d-109">User configurable scaling</span></span>
- <span data-ttu-id="1151d-110">Un'esperienza utente più semplice per gli sviluppatori e operatori di cluster.</span><span class="sxs-lookup"><span data-stu-id="1151d-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="1151d-111">Negli esempi seguenti esplorare la creazione di un'applicazione ASP.NET Core 2.1 che viene eseguito in Linux e distribuisce a un Cluster servizio contenitore di AZURE in Azure, mentre avviene lo sviluppo con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="1151d-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="1151d-112">Creazione progetto ASP.NET Core 2.1 con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="1151d-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="1151d-113">ASP.NET Core è una piattaforma di sviluppo generale gestita da Microsoft e dalla community .NET su GitHub.</span><span class="sxs-lookup"><span data-stu-id="1151d-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="1151d-114">È multipiattaforma, supporta Windows, macOS e Linux e può essere usato in scenari IoT/incorporati, cloud e dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1151d-114">It's cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="1151d-115">Questo esempio Usa un semplice progetto che si basa su un modello API Web di Visual Studio, in modo non occorre alcuna conoscenza aggiuntiva per creare il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="1151d-115">This example uses a simple project that's based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="1151d-116">È sufficiente creare il progetto usando un modello standard che include tutti gli elementi per eseguire un progetto di piccole dimensioni con un'API REST, mediante la tecnologia di ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="1151d-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![Aggiungi finestra Nuovo progetto in Visual Studio, selezionare l'applicazione Web ASP.NET Core.](media/create-aspnet-core-application.png)

<span data-ttu-id="1151d-118">**Figura 4-36**.</span><span class="sxs-lookup"><span data-stu-id="1151d-118">**Figure 4-36**.</span></span> <span data-ttu-id="1151d-119">Creazione di applicazioni ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1151d-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="1151d-120">Per creare il progetto di esempio in Visual Studio, selezionare **File** > **New** > **progetto**, selezionare la **Web**nel riquadro sinistro, seguite da tipi di progetto **applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="1151d-120">To create the sample project in Visual Studio, select **File** > **New** > **Project**, select the **Web** project types in the left pane, followed by **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="1151d-121">Visual Studio vengono elencati i modelli per progetti web.</span><span class="sxs-lookup"><span data-stu-id="1151d-121">Visual Studio lists templates for web projects.</span></span> <span data-ttu-id="1151d-122">Per questo esempio, selezionare **API** per creare un'applicazione API Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="1151d-122">For our example, select **API** to create an ASP.NET Web API Application.</span></span>

<span data-ttu-id="1151d-123">Verificare di avere selezionato come framework di ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="1151d-123">Verify that you've selected ASP.NET Core 2.1 as the framework.</span></span> <span data-ttu-id="1151d-124">.NET core 2.1 è incluso nell'ultima versione di Visual Studio 2017 e viene automaticamente installato e configurato automaticamente quando si installa Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="1151d-124">.NET Core 2.1 is included in the last version of Visual Studio 2017 and is automatically installed and configured for you when you install Visual Studio 2017.</span></span>

![Finestra di Studio Visual per la selezione del tipo di un'applicazione Web ASP.NET Core con l'opzione API selezionata.](media/create-web-api-application.png)

<span data-ttu-id="1151d-126">**Figura 4-37**.</span><span class="sxs-lookup"><span data-stu-id="1151d-126">**Figure 4-37**.</span></span> <span data-ttu-id="1151d-127">Tipo di progetto API Web e selezionando ASP.NET CORE 2.1</span><span class="sxs-lookup"><span data-stu-id="1151d-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="1151d-128">Se si dispone di qualsiasi versione precedente di .NET Core, è possibile scaricare e installare la versione 2.1 dal <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="1151d-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="1151d-129">È possibile aggiungere il supporto Docker quando si crea il progetto o in un secondo momento, pertanto, è possibile "inserirla" il progetto in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="1151d-129">You can add Docker support when creating the project or afterwards, so you can "Dockerize" your project at any time.</span></span> <span data-ttu-id="1151d-130">Per aggiungere supporto per Docker dopo la creazione del progetto, fare doppio clic sul nodo del progetto in Esplora soluzioni e selezionare **Add** > **supporto Docker** nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="1151d-130">To add Docker support after project creation, right-click on the project node in Solution Explorer and select **Add** > **Docker support** on the context menu.</span></span>

![Opzione di menu di scelta rapida per aggiungere il supporto Docker a un progetto esistente: Fare clic con il pulsante destro (sul progetto) > Aggiungi > supporto Docker.](media/add-docker-support-to-project.png)

<span data-ttu-id="1151d-132">**Figura 4-38**.</span><span class="sxs-lookup"><span data-stu-id="1151d-132">**Figure 4-38**.</span></span> <span data-ttu-id="1151d-133">Aggiunta del supporto Docker al progetto esistente</span><span class="sxs-lookup"><span data-stu-id="1151d-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="1151d-134">Per completare l'aggiunta del supporto Docker, è possibile scegliere Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="1151d-134">To complete adding Docker support, you can choose Windows or Linux.</span></span> <span data-ttu-id="1151d-135">In questo caso, selezionare **Linux**, in quanto servizio contenitore di AZURE non supporta i contenitori di Windows (come di ritardo 2018).</span><span class="sxs-lookup"><span data-stu-id="1151d-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Finestra di dialogo Opzioni selezionare sistema operativo di destinazione per Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="1151d-137">**Figura 4-39**.</span><span class="sxs-lookup"><span data-stu-id="1151d-137">**Figure 4-39**.</span></span> <span data-ttu-id="1151d-138">Se si seleziona contenitori Linux.</span><span class="sxs-lookup"><span data-stu-id="1151d-138">Selecting Linux containers.</span></span>

<span data-ttu-id="1151d-139">Con questi semplici passaggi, è necessario l'applicazione ASP.NET Core 2.1 in esecuzione in un contenitore Linux.</span><span class="sxs-lookup"><span data-stu-id="1151d-139">With these simple steps, you have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="1151d-140">Come può notare, l'integrazione tra Visual Studio 2017 e Docker è totalmente orientato alla produttività dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="1151d-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="1151d-141">A questo punto è possibile eseguire l'applicazione con il **F5** chiave oppure tramite il **riprodurre** pulsante.</span><span class="sxs-lookup"><span data-stu-id="1151d-141">Now you can run your application with the **F5** key or by using the **Play** button.</span></span>

<span data-ttu-id="1151d-142">Dopo aver eseguito il progetto, è possibile elencare le immagini usando il `docker images` comando.</span><span class="sxs-lookup"><span data-stu-id="1151d-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="1151d-143">Verrà visualizzato il `mssampleapplication` immagine creato dalla distribuzione automatica del progetto con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="1151d-143">You should see the `mssampleapplication` image created by the automatic deployment of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Console di output del comando di immagini docker, viene visualizzato un elenco con: Repository, Tag, ID immagine, Created (date) e dimensioni.](media/docker-images-command.png)

<span data-ttu-id="1151d-145">**Figura 4-40**.</span><span class="sxs-lookup"><span data-stu-id="1151d-145">**Figure 4-40**.</span></span> <span data-ttu-id="1151d-146">Visualizzazione delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="1151d-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="1151d-147">Registrare la soluzione nel registro contenitori di Azure</span><span class="sxs-lookup"><span data-stu-id="1151d-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="1151d-148">Caricare l'immagine in un registro Docker, ad esempio [registro contenitori di Azure (ACR)](https://azure.microsoft.com/services/container-registry/) o in Docker Hub, in modo che le immagini possono essere distribuite nel cluster AKS da tale registro.</span><span class="sxs-lookup"><span data-stu-id="1151d-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub, so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="1151d-149">In questo caso, si sta caricando l'immagine in Registro contenitori di Azure.</span><span class="sxs-lookup"><span data-stu-id="1151d-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="1151d-150">Creare l'immagine in modalità di rilascio</span><span class="sxs-lookup"><span data-stu-id="1151d-150">Create the image in Release mode</span></span>

<span data-ttu-id="1151d-151">Ora verrà creata l'immagine nella **Release** modalità (pronta per la produzione) modificando in **rilascio**, come illustrato nella figura 4-41 e l'esecuzione dell'applicazione come fatto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1151d-151">We'll now create the image in **Release** mode (ready for production) by changing to **Release**, as shown in Figure 4-41, and running the application as we did before.</span></span>

![Opzione della barra degli strumenti in Visual Studio per compilare in modalità di rilascio.](media/select-release-mode.png)

<span data-ttu-id="1151d-153">**Figura 4-41**.</span><span class="sxs-lookup"><span data-stu-id="1151d-153">**Figure 4-41**.</span></span> <span data-ttu-id="1151d-154">Se si seleziona la modalità di rilascio</span><span class="sxs-lookup"><span data-stu-id="1151d-154">Selecting Release Mode</span></span>

<span data-ttu-id="1151d-155">Se si esegue la `docker image` comando, si noterà entrambe le immagini create, uno per `debug` e l'altro per `release` modalità.</span><span class="sxs-lookup"><span data-stu-id="1151d-155">If you execute the `docker image` command, you'll see both images created, one for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="1151d-156">Creare un nuovo Tag dell'immagine</span><span class="sxs-lookup"><span data-stu-id="1151d-156">Create a new Tag for the Image</span></span>

<span data-ttu-id="1151d-157">Ogni immagine del contenitore deve essere contrassegnata con il `loginServer` nome del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="1151d-157">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="1151d-158">Questo tag viene usato per il routing quando si effettua il push delle immagini del contenitore nel registro delle immagini.</span><span class="sxs-lookup"><span data-stu-id="1151d-158">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="1151d-159">È possibile visualizzare il `loginServer` nome dal portale di Azure, tenuto le informazioni dal registro contenitori di Azure</span><span class="sxs-lookup"><span data-stu-id="1151d-159">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Visualizzazione di esplorazione del nome del Registro di sistema del contenitore di Azure, in alto a destra.](media/loginServer-name.png)

<span data-ttu-id="1151d-161">**Figura 4-42**.</span><span class="sxs-lookup"><span data-stu-id="1151d-161">**Figure 4-42**.</span></span> <span data-ttu-id="1151d-162">Visualizzazione del nome del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="1151d-162">View of the name of the Registry</span></span>

<span data-ttu-id="1151d-163">O eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1151d-163">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Output del comando precedente della console.](media/az-cli-loginServer-name.png)

<span data-ttu-id="1151d-165">**Figura 4-43**.</span><span class="sxs-lookup"><span data-stu-id="1151d-165">**Figure 4-43**.</span></span> <span data-ttu-id="1151d-166">Ottenere il nome del Registro di sistema usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="1151d-166">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="1151d-167">In entrambi i casi, è possibile ottenere il nome.</span><span class="sxs-lookup"><span data-stu-id="1151d-167">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="1151d-168">In questo esempio, `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="1151d-168">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="1151d-169">A questo punto è possibile contrassegnare l'immagine, prendendo l'immagine più recente (dell'immagine della versione), con il comando:</span><span class="sxs-lookup"><span data-stu-id="1151d-169">Now you can tag the image, taking the latest image (the Release image), with the command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="1151d-170">Dopo aver eseguito il `docker tag` comando, elencare le immagini con il `docker images` comando che dovrebbe mostrare l'immagine con il nuovo tag.</span><span class="sxs-lookup"><span data-stu-id="1151d-170">After running the `docker tag` command, list the images with the `docker images` command, and you should see the image with the new tag.</span></span>

![Console di output del comando di immagini docker.](media/tagged-docker-images-list.png)

<span data-ttu-id="1151d-172">**Figura 4-44**.</span><span class="sxs-lookup"><span data-stu-id="1151d-172">**Figure 4-44**.</span></span> <span data-ttu-id="1151d-173">Visualizzazione di immagini con tag</span><span class="sxs-lookup"><span data-stu-id="1151d-173">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="1151d-174">Eseguire il push dell'immagine in Registro contenitori di AZURE di Azure</span><span class="sxs-lookup"><span data-stu-id="1151d-174">Push the image into the Azure ACR</span></span>

<span data-ttu-id="1151d-175">Eseguire il push dell'immagine in Registro contenitori di AZURE Azure, usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1151d-175">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="1151d-176">Questo comando accetta un po' di tempo caricamento delle immagini, ma ti offre commenti e suggerimenti nel processo.</span><span class="sxs-lookup"><span data-stu-id="1151d-176">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Console di output del comando di push di docker: mostra un indicatore di stato basato su caratteri per ogni livello.](media/uploading-image-to-acr.png)

<span data-ttu-id="1151d-178">**Figura 4-45**.</span><span class="sxs-lookup"><span data-stu-id="1151d-178">**Figure 4-45**.</span></span> <span data-ttu-id="1151d-179">Caricare l'immagine per il registro contenitori di AZURE</span><span class="sxs-lookup"><span data-stu-id="1151d-179">Uploading the image to the ACR</span></span>

<span data-ttu-id="1151d-180">È possibile vedere di seguito il risultato che dovrebbe essere visualizzata al termine del processo:</span><span class="sxs-lookup"><span data-stu-id="1151d-180">You can see below the result you should get when the process completes:</span></span>

![Output del comando di push di docker, completato, che mostra tutti i livelli o i nodi della console.](media/uploading-docker-images-complete.png)

<span data-ttu-id="1151d-182">**Figura 4-46**.</span><span class="sxs-lookup"><span data-stu-id="1151d-182">**Figure 4-46**.</span></span> <span data-ttu-id="1151d-183">Visualizzazione dei nodi</span><span class="sxs-lookup"><span data-stu-id="1151d-183">View of nodes</span></span>

<span data-ttu-id="1151d-184">Il passaggio successivo consiste nel distribuire il contenitore nel cluster AKS Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="1151d-184">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="1151d-185">A tal fine, è necessario un file (**yml distribuire file**) che contiene gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1151d-185">For that, you need a file (**.yml deploy file**) that contains the following:</span></span>

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
        - mane: mssample-services-app
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
> <span data-ttu-id="1151d-186">Per altre informazioni sulla distribuzione con Kubernetes, vedere: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="1151d-186">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="1151d-187">A questo punto è quasi pronti per eseguire la distribuzione usando **Kubectl**, ma prima di tutto è necessario ottenere le credenziali per il Cluster AKS con questo comando:</span><span class="sxs-lookup"><span data-stu-id="1151d-187">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Console di output del comando precedente: Unito MSSampleK8Cluster"come contesto corrente in /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="1151d-189">**Figura 4-47**.</span><span class="sxs-lookup"><span data-stu-id="1151d-189">**Figure 4-47**.</span></span> <span data-ttu-id="1151d-190">ottenere le credenziali</span><span class="sxs-lookup"><span data-stu-id="1151d-190">getting credentials</span></span>

<span data-ttu-id="1151d-191">Usare quindi il `kubectl create` comando per avviare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1151d-191">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Console di output del comando precedente: distribuzione "mssamplesbook" creata.](media/kubectl-create-command.png)

<span data-ttu-id="1151d-194">**Figura 4-48**.</span><span class="sxs-lookup"><span data-stu-id="1151d-194">**Figure 4-48**.</span></span> <span data-ttu-id="1151d-195">Distribuisci in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="1151d-195">Deploy to Kubernetes</span></span>

<span data-ttu-id="1151d-196">Al termine della distribuzione, è possibile accedere alla console di Kubernetes con un proxy locale che è possibile accedere temporaneamente con questo comando:</span><span class="sxs-lookup"><span data-stu-id="1151d-196">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="1151d-197">E l'accesso all'url `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="1151d-197">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Visualizzazione di esplorazione del dashboard Kubernetes, che mostra le distribuzioni, i POD, set di repliche e i servizi.](media/kubernetes-cluster-information.png)

<span data-ttu-id="1151d-199">**Figura 4-49**.</span><span class="sxs-lookup"><span data-stu-id="1151d-199">**Figure 4-49**.</span></span> <span data-ttu-id="1151d-200">Visualizzare le informazioni del cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="1151d-200">View Kubernetes cluster information</span></span>

<span data-ttu-id="1151d-201">È ora disponibile un'applicazione distribuita in Azure, usando un contenitore Linux e un Kubernetes del Cluster servizio contenitore di AZURE.</span><span class="sxs-lookup"><span data-stu-id="1151d-201">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="1151d-202">È possibile accedere all'app di esplorazione per l'indirizzo IP pubblico del servizio, che è possibile ottenere dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="1151d-202">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="1151d-203">È possibile vedere come creare il Cluster AKS per questo esempio nella sezione [ **Distribuisci a Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) in questa Guida.</span><span class="sxs-lookup"><span data-stu-id="1151d-203">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1151d-204">[Precedente](set-up-windows-containers-with-powershell.md)
>[Successivo](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="1151d-204">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
