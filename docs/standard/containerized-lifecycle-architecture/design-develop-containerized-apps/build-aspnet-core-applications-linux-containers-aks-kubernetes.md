---
title: Creazione di applicazioni ASP.NET Core 2.1 distribuite come contenitori Linux nel cluster AKS/Kubernetes
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b03b6fab9dcd53e97c2bc4d7e5c958ca4b931077
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221487"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-akskubernetes-orchestrator"></a><span data-ttu-id="c400c-103">Creazione di applicazioni ASP.NET Core 2.1 distribuite come contenitori Linux nel servizio contenitore di AZURE/Kubernetes orchestrator</span><span class="sxs-lookup"><span data-stu-id="c400c-103">Build ASP.NET Core 2.1 applications deployed as Linux containers into AKS/Kubernetes orchestrator</span></span>

<span data-ttu-id="c400c-104">Servizi di Kubernetes Azure (AKS) è managed Kubernetes orchestrazioni i servizi di Azure che semplificano la gestione e distribuzione di contenitori.</span><span class="sxs-lookup"><span data-stu-id="c400c-104">Azure Kubernetes Services (AKS) is Azure's managed Kubernetes orchestrations services that simplify container deployment and management.</span></span>

<span data-ttu-id="c400c-105">Funzionalità principali di servizio contenitore di AZURE sono:</span><span class="sxs-lookup"><span data-stu-id="c400c-105">AKS main features are:</span></span>

- <span data-ttu-id="c400c-106">Un piano di controllo ospitato in Azure</span><span class="sxs-lookup"><span data-stu-id="c400c-106">An Azure-hosted control plane</span></span>
- <span data-ttu-id="c400c-107">Aggiornamenti automatici</span><span class="sxs-lookup"><span data-stu-id="c400c-107">Automated upgrades</span></span>
- <span data-ttu-id="c400c-108">Riparazione automatica</span><span class="sxs-lookup"><span data-stu-id="c400c-108">Self-healing</span></span>
- <span data-ttu-id="c400c-109">Ridimensionamento configurabile utente</span><span class="sxs-lookup"><span data-stu-id="c400c-109">User configurable scaling</span></span>
- <span data-ttu-id="c400c-110">Un'esperienza utente più semplice per gli sviluppatori e operatori di cluster.</span><span class="sxs-lookup"><span data-stu-id="c400c-110">A simpler user experience for both developers and cluster operators.</span></span>

<span data-ttu-id="c400c-111">Negli esempi seguenti esplorare la creazione di un'applicazione ASP.NET Core 2.1 che viene eseguito in Linux e distribuisce a un Cluster servizio contenitore di AZURE in Azure, mentre avviene lo sviluppo con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c400c-111">The following examples explore the creation of an ASP.NET Core 2.1 application that runs on Linux and deploys to an AKS Cluster in Azure, while development is done using Visual Studio 2017.</span></span>

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a><span data-ttu-id="c400c-112">Creazione progetto ASP.NET Core 2.1 con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c400c-112">Creating the ASP.NET Core 2.1 Project using Visual Studio 2017</span></span>

<span data-ttu-id="c400c-113">ASP.NET Core è una piattaforma di sviluppo generale gestita da Microsoft e dalla community .NET su GitHub.</span><span class="sxs-lookup"><span data-stu-id="c400c-113">ASP.NET Core is a general-purpose development platform maintained by Microsoft and the .NET community on GitHub.</span></span> <span data-ttu-id="c400c-114">È multipiattaforma, supporta Windows, macOS e Linux e può essere usata su dispositivi, ambienti cloud e scenari IoT/incorporati.</span><span class="sxs-lookup"><span data-stu-id="c400c-114">It is cross-platform, supporting Windows, macOS and Linux, and can be used in device, cloud, and embedded/IoT scenarios.</span></span>

<span data-ttu-id="c400c-115">Questo esempio Usa un progetto semplice che si basa basato su un modello API Web di Visual Studio, in modo non occorre alcuna conoscenza aggiuntiva per creare il codice di esempio.</span><span class="sxs-lookup"><span data-stu-id="c400c-115">This example uses a simple project that's based based on a Visual Studio Web API template, so you don't need any additional knowledge to create the sample.</span></span> <span data-ttu-id="c400c-116">È sufficiente creare il progetto usando un modello standard che include tutti gli elementi per eseguire un progetto di piccole dimensioni con un'API REST, mediante la tecnologia di ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="c400c-116">You only have to create the project using a standard template that includes all the elements to run a small project with a REST API, using ASP.NET Core 2.1 technology.</span></span>

![Aggiungi finestra Nuovo progetto in Visual Studio, selezionare l'applicazione Web ASP.NET Core.](media/create-aspnet-core-application.png)

<span data-ttu-id="c400c-118">**Figura 4-36**.</span><span class="sxs-lookup"><span data-stu-id="c400c-118">**Figure 4-36**.</span></span> <span data-ttu-id="c400c-119">Creazione di applicazioni ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c400c-119">Creating ASP.NET Core Application</span></span>

<span data-ttu-id="c400c-120">Per creare il progetto di esempio, è necessario selezionare **File** > **New** > **progetto** su Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c400c-120">To create the sample project, you have to select **File** > **New** > **Project** on Visual Studio.</span></span> <span data-ttu-id="c400c-121">Verrà visualizzato un elenco di modelli per diversi tipi di progetto, in cui è necessario cercare **Web** > **.NET Core** nel Pannello di sinistra.</span><span class="sxs-lookup"><span data-stu-id="c400c-121">Then you'll see a list of templates for several types of projects, where you have to look for **Web** > **.NET Core** on the left panel.</span></span> <span data-ttu-id="c400c-122">Per questo esempio selezionare **applicazione Web ASP.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="c400c-122">For this example select **ASP.NET Core Web Application**.</span></span>

<span data-ttu-id="c400c-123">Nella finestra di dialogo successiva, assicurarsi di aver selezionato .NET Core e ASP.NET Core 2.1 come framework di destinazione nel pulldowns superiore, come illustrato nella figura 4-37 e quindi selezionare l'opzione di API, creare un'applicazione API Web ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c400c-123">In the next dialog ensure that you have selected .NET Core and ASP.NET Core 2.1 as the target framework in the top pulldowns, as shown in figure 4-37, and then select the API option, to create an ASP.NET Core Web API application.</span></span>

<span data-ttu-id="c400c-124">.NET Core 2.1 è inclusa in Visual Studio 2017 versione 15.7.0 o versione successiva e viene automaticamente installato e configurato automaticamente quando si seleziona il **sviluppo multipiattaforma .NET Core** carico di lavoro durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="c400c-124">The .NET Core 2.1 is included in Visual Studio 2017 version 15.7.0 or higher and is automatically installed and configured for you when you select the **.NET Core cross-platform development** workload during installation.</span></span>

![Finestra di Studio Visual per la selezione del tipo di un'applicazione Web ASP.NET Core con l'opzione API selezionata.](media/create-web-api-application.png)

<span data-ttu-id="c400c-126">**Figura 4-37**.</span><span class="sxs-lookup"><span data-stu-id="c400c-126">**Figure 4-37**.</span></span> <span data-ttu-id="c400c-127">Tipo di progetto API Web e selezionando ASP.NET CORE 2.1</span><span class="sxs-lookup"><span data-stu-id="c400c-127">Selecting ASP.NET CORE 2.1 and Web API project type</span></span>

<span data-ttu-id="c400c-128">Se si dispone di qualsiasi versione precedente di .NET Core, è possibile scaricare e installare la versione 2.1 dal <https://www.microsoft.com/net/download/core#/sdk>.</span><span class="sxs-lookup"><span data-stu-id="c400c-128">If you have any previous version of .NET Core, you can download and install the 2.1 version from <https://www.microsoft.com/net/download/core#/sdk>.</span></span>

<span data-ttu-id="c400c-129">È possibile aggiungere supporto per Docker durante la creazione del progetto nel passaggio precedente, o versione successiva, in caso di necessità dopo l'avvio del progetto.</span><span class="sxs-lookup"><span data-stu-id="c400c-129">You can add Docker support when creating the project in the previous step, or later, if the need arises after starting the project.</span></span> <span data-ttu-id="c400c-130">Per aggiungere il supporto per Docker dopo la creazione del progetto, fare doppio clic sul file di progetto nel **Esplora soluzioni** e selezionare **Add** > **supporto Docker** su menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="c400c-130">To add the Docker support after the project creation, right-click on the project file in the **Solution Explorer** and select **Add** > **Docker support** on the context menu.</span></span>

![Opzione di menu di scelta rapida per aggiungere il supporto Docker a un progetto esistente: Fare clic con il pulsante destro (sul progetto) > Aggiungi > supporto Docker.](media/add-docker-support-to-project.png)

<span data-ttu-id="c400c-132">**Figura 4-38**.</span><span class="sxs-lookup"><span data-stu-id="c400c-132">**Figure 4-38**.</span></span> <span data-ttu-id="c400c-133">Aggiunta del supporto Docker al progetto esistente</span><span class="sxs-lookup"><span data-stu-id="c400c-133">Adding Docker support to existing project</span></span>

<span data-ttu-id="c400c-134">Per completare l'aggiunta del supporto Docker, è possibile scegliere di Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="c400c-134">To complete adding Docker support, you have the choice of Windows or Linux.</span></span> <span data-ttu-id="c400c-135">In questo caso, selezionare **Linux**, in quanto servizio contenitore di AZURE non supporta i contenitori di Windows (come di ritardo 2018).</span><span class="sxs-lookup"><span data-stu-id="c400c-135">In this case, select **Linux**, because AKS doesn’t support Windows Containers (as of late 2018).</span></span>

![Finestra di dialogo Opzioni selezionare sistema operativo di destinazione per Dockerfile.](media/select-linux-docker-support.png)

<span data-ttu-id="c400c-137">**Figura 4-39**.</span><span class="sxs-lookup"><span data-stu-id="c400c-137">**Figure 4-39**.</span></span> <span data-ttu-id="c400c-138">Se si seleziona contenitori Linux.</span><span class="sxs-lookup"><span data-stu-id="c400c-138">Selecting Linux containers.</span></span>

<span data-ttu-id="c400c-139">Con questi semplici passaggi, si avrà l'applicazione ASP.NET Core 2.1 in esecuzione in un contenitore Linux.</span><span class="sxs-lookup"><span data-stu-id="c400c-139">With these simple steps, you will have your ASP.NET Core 2.1 application running on a Linux container.</span></span>

<span data-ttu-id="c400c-140">Come può notare, l'integrazione tra Visual Studio 2017 e Docker è totalmente orientato alla produttività dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="c400c-140">As you can see, the integration between Visual Studio 2017 and Docker is totally oriented to the developer’s productivity.</span></span>

<span data-ttu-id="c400c-141">A questo punto è possibile premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c400c-141">Now you can press **F5** to build and run your application.</span></span>

<span data-ttu-id="c400c-142">Dopo aver eseguito il progetto, è possibile elencare le immagini usando il `docker images` comando.</span><span class="sxs-lookup"><span data-stu-id="c400c-142">After running the project, you can list the images using the `docker images` command.</span></span> <span data-ttu-id="c400c-143">Verrà visualizzato il `mssampleapplication` immagine creata con la distribuzione automatica del progetto con Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="c400c-143">You should see the `mssampleapplication` image created with the automatic deploy of our project with Visual Studio 2017.</span></span>

```console
docker images
```

![Console di output del comando di immagini docker, viene visualizzato un elenco con: Repository, Tag, ID immagine, Created (date) e dimensioni.](media/docker-images-command.png)

<span data-ttu-id="c400c-145">**Figura 4-40**.</span><span class="sxs-lookup"><span data-stu-id="c400c-145">**Figure 4-40**.</span></span> <span data-ttu-id="c400c-146">Visualizzazione delle immagini Docker</span><span class="sxs-lookup"><span data-stu-id="c400c-146">View of Docker images</span></span>

## <a name="register-the-solution-in-the-azure-container-registry"></a><span data-ttu-id="c400c-147">Registrare la soluzione nel registro contenitori di Azure</span><span class="sxs-lookup"><span data-stu-id="c400c-147">Register the Solution in the Azure Container Registry</span></span>

<span data-ttu-id="c400c-148">Caricare l'immagine in un registro Docker, ad esempio [registro contenitori di Azure (ACR)](https://azure.microsoft.com/services/container-registry/) o in Docker Hub in modo che le immagini possono essere distribuite nel cluster AKS da tale registro.</span><span class="sxs-lookup"><span data-stu-id="c400c-148">Upload the image to any Docker registry, like [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) or Docker Hub so the images can be deployed to the AKS cluster from that registry.</span></span> <span data-ttu-id="c400c-149">In questo caso, si sta caricando l'immagine in Registro contenitori di Azure.</span><span class="sxs-lookup"><span data-stu-id="c400c-149">In this case, we’re uploading the image to Azure Container Registry.</span></span>

### <a name="create-the-image-in-release-mode"></a><span data-ttu-id="c400c-150">Creare l'immagine in modalità di rilascio</span><span class="sxs-lookup"><span data-stu-id="c400c-150">Create the image in Release mode</span></span>

<span data-ttu-id="c400c-151">Creare l'immagine nel **rilascio** (pronta per la produzione) in modalità di modifica alla versione come illustrato di seguito e premere F5 per eseguire nuovamente l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c400c-151">Create the image in **Release** Mode (ready for production) changing to Release as shown here and press F5 to run the application again.</span></span>

![Opzione della barra degli strumenti in Visual Studio per compilare in modalità di rilascio.](media/select-release-mode.png)

<span data-ttu-id="c400c-153">**Figura 4-41**.</span><span class="sxs-lookup"><span data-stu-id="c400c-153">**Figure 4-41**.</span></span> <span data-ttu-id="c400c-154">Se si seleziona la modalità di rilascio</span><span class="sxs-lookup"><span data-stu-id="c400c-154">Selecting Release Mode</span></span>

<span data-ttu-id="c400c-155">Se si esegue il `docker image` comando, si noterà entrambe le immagini create.</span><span class="sxs-lookup"><span data-stu-id="c400c-155">If you execute the `docker image` command, you'll see both images created.</span></span> <span data-ttu-id="c400c-156">Uno per `debug` e l'altro per `release` modalità.</span><span class="sxs-lookup"><span data-stu-id="c400c-156">One for `debug` and the other for `release` mode.</span></span>

### <a name="create-a-new-tag-for-the-image"></a><span data-ttu-id="c400c-157">Creare un nuovo Tag dell'immagine</span><span class="sxs-lookup"><span data-stu-id="c400c-157">Create a new Tag for the Image</span></span>

<span data-ttu-id="c400c-158">Ogni immagine del contenitore deve essere contrassegnata con il `loginServer` nome del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="c400c-158">Each container image needs to be tagged with the `loginServer` name of the registry.</span></span> <span data-ttu-id="c400c-159">Questo tag viene usato per il routing quando si effettua il push delle immagini del contenitore nel registro delle immagini.</span><span class="sxs-lookup"><span data-stu-id="c400c-159">This tag is used for routing when pushing container images to an image registry.</span></span>

<span data-ttu-id="c400c-160">È possibile visualizzare il `loginServer` nome dal portale di Azure, tenuto le informazioni dal registro contenitori di Azure</span><span class="sxs-lookup"><span data-stu-id="c400c-160">You can view the `loginServer` name from the Azure portal, taking the information from the Azure Container Registry</span></span>

![Visualizzazione di esplorazione del nome del Registro di sistema del contenitore di Azure, in alto a destra.](media/loginServer-name.png)

<span data-ttu-id="c400c-162">**Figura 4-42**.</span><span class="sxs-lookup"><span data-stu-id="c400c-162">**Figure 4-42**.</span></span> <span data-ttu-id="c400c-163">Visualizzazione del nome del Registro di sistema</span><span class="sxs-lookup"><span data-stu-id="c400c-163">View of the name of the Registry</span></span>

<span data-ttu-id="c400c-164">O eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c400c-164">Or by running the following command:</span></span>

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Output del comando precedente della console.](media/az-cli-loginServer-name.png)

<span data-ttu-id="c400c-166">**Figura 4-43**.</span><span class="sxs-lookup"><span data-stu-id="c400c-166">**Figure 4-43**.</span></span> <span data-ttu-id="c400c-167">Ottenere il nome del Registro di sistema usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="c400c-167">Get the name of the registry using PowerShell</span></span>

<span data-ttu-id="c400c-168">In entrambi i casi, è possibile ottenere il nome.</span><span class="sxs-lookup"><span data-stu-id="c400c-168">In both cases, you'll obtain the name.</span></span> <span data-ttu-id="c400c-169">In questo esempio, `mssampleacr.azurecr.io`.</span><span class="sxs-lookup"><span data-stu-id="c400c-169">In our example, `mssampleacr.azurecr.io`.</span></span>

<span data-ttu-id="c400c-170">A questo punto è possibile contrassegnare l'immagine, prendendo l'immagine più recente (versione immagine), con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c400c-170">Now you can tag the image, taking the latest image (Release image), with the following command:</span></span>

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="c400c-171">Dopo aver eseguito il `docker tag` comando, elencare le immagini con il `docker images` comando.</span><span class="sxs-lookup"><span data-stu-id="c400c-171">After running the `docker tag` command, list the images with the `docker images` command.</span></span> <span data-ttu-id="c400c-172">Verrà visualizzata l'immagine con il nuovo tag.</span><span class="sxs-lookup"><span data-stu-id="c400c-172">You should see the image with the new tag.</span></span>

![Console di output del comando di immagini docker.](media/tagged-docker-images-list.png)

<span data-ttu-id="c400c-174">**Figura 4-44**.</span><span class="sxs-lookup"><span data-stu-id="c400c-174">**Figure 4-44**.</span></span> <span data-ttu-id="c400c-175">Visualizzazione di immagini con tag</span><span class="sxs-lookup"><span data-stu-id="c400c-175">View of tagged images</span></span>

### <a name="push-the-image-into-the-azure-acr"></a><span data-ttu-id="c400c-176">Eseguire il push dell'immagine in Registro contenitori di AZURE di Azure</span><span class="sxs-lookup"><span data-stu-id="c400c-176">Push the image into the Azure ACR</span></span>

<span data-ttu-id="c400c-177">Eseguire il push dell'immagine in Registro contenitori di AZURE Azure, usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c400c-177">Push the image into the Azure ACR, using the following command:</span></span>

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

<span data-ttu-id="c400c-178">Questo comando accetta un po' di tempo caricamento delle immagini, ma ti offre commenti e suggerimenti nel processo.</span><span class="sxs-lookup"><span data-stu-id="c400c-178">This command takes a while uploading the images but gives you feedback in the process.</span></span>

![Console di output del comando di push di docker: mostra un indicatore di stato basato su caratteri per ogni livello.](media/uploading-image-to-acr.png)

<span data-ttu-id="c400c-180">**Figura 4-45**.</span><span class="sxs-lookup"><span data-stu-id="c400c-180">**Figure 4-45**.</span></span> <span data-ttu-id="c400c-181">Caricare l'immagine per il registro contenitori di AZURE</span><span class="sxs-lookup"><span data-stu-id="c400c-181">Uploading the image to the ACR</span></span>

<span data-ttu-id="c400c-182">È possibile vedere di seguito il risultato che dovrebbe essere visualizzata al termine del processo:</span><span class="sxs-lookup"><span data-stu-id="c400c-182">You can see below the result you should get when the process completes:</span></span>

![Output del comando di push di docker, completato, che mostra tutti i livelli o i nodi della console.](media/uploading-docker-images-complete.png)

<span data-ttu-id="c400c-184">**Figura 4-46**.</span><span class="sxs-lookup"><span data-stu-id="c400c-184">**Figure 4-46**.</span></span> <span data-ttu-id="c400c-185">Visualizzazione dei nodi</span><span class="sxs-lookup"><span data-stu-id="c400c-185">View of nodes</span></span>

<span data-ttu-id="c400c-186">Il passaggio successivo consiste nel distribuire il contenitore nel cluster AKS Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="c400c-186">The next step is to deploy your container into your AKS Kubernetes cluster.</span></span> <span data-ttu-id="c400c-187">Per cui è necessario un file (**yml distribuire file**), in questo caso, contenente:</span><span class="sxs-lookup"><span data-stu-id="c400c-187">For that you need a file (**.yml deploy file**) that, in this case, contains:</span></span>

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
> <span data-ttu-id="c400c-188">Per altre informazioni sulla distribuzione con Kubernetes, vedere: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span><span class="sxs-lookup"><span data-stu-id="c400c-188">For more information on deployment with Kubernetes see: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/></span></span>

<span data-ttu-id="c400c-189">A questo punto è quasi pronti per eseguire la distribuzione usando **Kubectl**, ma prima di tutto è necessario ottenere le credenziali per il Cluster AKS con questo comando:</span><span class="sxs-lookup"><span data-stu-id="c400c-189">Now you're almost ready to deploy using **Kubectl**, but first you must get the credentials to the AKS Cluster with this command:</span></span>

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Console di output del comando precedente: Unito MSSampleK8Cluster"come contesto corrente in /root/.kube/config](media/getting-aks-credentials.png)

<span data-ttu-id="c400c-191">**Figura 4-47**.</span><span class="sxs-lookup"><span data-stu-id="c400c-191">**Figure 4-47**.</span></span> <span data-ttu-id="c400c-192">ottenere le credenziali</span><span class="sxs-lookup"><span data-stu-id="c400c-192">getting credentials</span></span>

<span data-ttu-id="c400c-193">Usare quindi il `kubectl create` comando per avviare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c400c-193">Then, use the `kubectl create` command to launch the deployment.</span></span>

```console
kubectl create -f mssample-deploy.yml
```

![Console di output del comando precedente: distribuzione "mssamplesbook" creata.](media/kubectl-create-command.png)

<span data-ttu-id="c400c-196">**Figura 4-48**.</span><span class="sxs-lookup"><span data-stu-id="c400c-196">**Figure 4-48**.</span></span> <span data-ttu-id="c400c-197">Distribuisci in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c400c-197">Deploy to Kubernetes</span></span>

<span data-ttu-id="c400c-198">Al termine della distribuzione, è possibile accedere alla console di Kubernetes con un proxy locale che è possibile accedere temporaneamente con questo comando:</span><span class="sxs-lookup"><span data-stu-id="c400c-198">When the deployment completes, you can access the Kubernetes console with a local proxy that you can temporally access with this command:</span></span>

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

<span data-ttu-id="c400c-199">E l'accesso all'url `http://127.0.0.1:8001`.</span><span class="sxs-lookup"><span data-stu-id="c400c-199">And accessing the url `http://127.0.0.1:8001`.</span></span>

![Visualizzazione di esplorazione del dashboard Kubernetes, che mostra le distribuzioni, i POD, set di repliche e i servizi.](media/kubernetes-cluster-information.png)

<span data-ttu-id="c400c-201">**Figura 4-49**.</span><span class="sxs-lookup"><span data-stu-id="c400c-201">**Figure 4-49**.</span></span> <span data-ttu-id="c400c-202">Visualizzare le informazioni del cluster Kubernetes</span><span class="sxs-lookup"><span data-stu-id="c400c-202">View Kubernetes cluster information</span></span>

<span data-ttu-id="c400c-203">È ora disponibile un'applicazione distribuita in Azure, usando un contenitore Linux e un Kubernetes del Cluster servizio contenitore di AZURE.</span><span class="sxs-lookup"><span data-stu-id="c400c-203">Now you have your application deployed on Azure, using a Linux Container, and an AKS Kubernetes Cluster.</span></span> <span data-ttu-id="c400c-204">È possibile accedere all'app di esplorazione per l'indirizzo IP pubblico del servizio, che è possibile ottenere dal portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="c400c-204">You can access your app browsing to the public IP of your service, which you can get from the Azure portal.</span></span>

> [!NOTE]
> <span data-ttu-id="c400c-205">È possibile vedere come creare il Cluster AKS per questo esempio nella sezione [ **Distribuisci a Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) in questa Guida.</span><span class="sxs-lookup"><span data-stu-id="c400c-205">You can see how to create the AKS Cluster for this sample in section [**Deploy to Azure Kubernetes Service (AKS)**](deploy-azure-kubernetes-service.md) on this guide.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c400c-206">[Precedente](set-up-windows-containers-with-powershell.md)
>[Successivo](../docker-devops-workflow/index.md)</span><span class="sxs-lookup"><span data-stu-id="c400c-206">[Previous](set-up-windows-containers-with-powershell.md)
[Next](../docker-devops-workflow/index.md)</span></span>
