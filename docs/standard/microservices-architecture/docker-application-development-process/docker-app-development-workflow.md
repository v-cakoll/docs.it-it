---
title: Flusso di lavoro di sviluppo per app Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Flusso di lavoro di sviluppo per app Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a0f20e5b568a464b5c860e3da51e52d4f7d79972
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="86dce-104">Flusso di lavoro di sviluppo per app Docker</span><span class="sxs-lookup"><span data-stu-id="86dce-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="86dce-105">Il ciclo di vita dello sviluppo applicativo inizia al computer di ogni sviluppatore quando l'applicazione viene scritta usando un determinato linguaggio e viene testata in locale.</span><span class="sxs-lookup"><span data-stu-id="86dce-105">The application development lifecycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="86dce-106">Indipendentemente dal linguaggio, il framework e la piattaforma scelti, con questo flusso di lavoro lo sviluppatore scrive e testa sempre contenitori Docker, ma localmente.</span><span class="sxs-lookup"><span data-stu-id="86dce-106">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="86dce-107">Ogni contenitore, ovvero un'istanza di un'immagine Docker, include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="86dce-107">Each container (an instance of a Docker image) includes the following components:</span></span>

-   <span data-ttu-id="86dce-108">Un sistema operativo a scelta, come una distribuzione Linux, Windows Nano Server o Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="86dce-108">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

-   <span data-ttu-id="86dce-109">File aggiunti dallo sviluppatore, ovvero file binari dell'applicazione e così via.</span><span class="sxs-lookup"><span data-stu-id="86dce-109">Files added by the developer (application binaries, etc.).</span></span>

-   <span data-ttu-id="86dce-110">Informazioni di configurazione, come impostazioni di ambiente e dipendenze.</span><span class="sxs-lookup"><span data-stu-id="86dce-110">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="86dce-111">Flusso di lavoro per lo sviluppo di applicazioni Docker basate su contenitore</span><span class="sxs-lookup"><span data-stu-id="86dce-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="86dce-112">Questa sezione descrive il flusso di lavoro di sviluppo a *ciclo interno* per applicazioni Docker basate su contenitore.</span><span class="sxs-lookup"><span data-stu-id="86dce-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="86dce-113">Flusso di lavoro a ciclo interno significa che non tiene conto del flusso di lavoro DevOps più ampio e si concentra solo sul lavoro di sviluppo eseguito sul computer dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="86dce-113">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="86dce-114">I passaggi iniziali per configurare l'ambiente non sono inclusi, in quanto sono eseguiti una sola volta.</span><span class="sxs-lookup"><span data-stu-id="86dce-114">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="86dce-115">Un'applicazione è costituita da servizi e raccolte aggiuntive, ossia dipendenze.</span><span class="sxs-lookup"><span data-stu-id="86dce-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="86dce-116">Di seguito sono indicati i passaggi di base che si eseguono in genere quando si compila un'applicazione Docker, come illustrato nella figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="86dce-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="86dce-117">**Figura 5-1.**</span><span class="sxs-lookup"><span data-stu-id="86dce-117">**Figure 5-1.**</span></span> <span data-ttu-id="86dce-118">Flusso di lavoro passo per passo per lo sviluppo di applicazioni Docker in contenitori</span><span class="sxs-lookup"><span data-stu-id="86dce-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="86dce-119">Questa guida descrive nei dettagli l'intero processo e ogni passaggio principale è spiegato con riferimento all'ambiente Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86dce-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="86dce-120">Quando si usa un approccio di sviluppo editor/CLI, ad esempio codice Visual Studio e CLI di Docker in macOS o Windows, di solito è necessario conoscere ogni passaggio in modo più dettagliato rispetto all'uso di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86dce-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="86dce-121">Per altre informazioni sull'uso di un ambiente CLI, vedere l'e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/) (Ciclo di vita di un'applicazione Docker in un contenitore con piattaforme e strumenti Microsoft).</span><span class="sxs-lookup"><span data-stu-id="86dce-121">For more details about working in a CLI environment, refer to the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="86dce-122">Quando si usa Visual Studio 2015 o Visual Studio 2017, molti di questi passaggi sono gestiti automaticamente e questo migliora notevolmente la produttività.</span><span class="sxs-lookup"><span data-stu-id="86dce-122">When you are using Visual Studio 2015 or Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="86dce-123">Ciò vale soprattutto quando si usa Visual Studio 2017 con applicazioni a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="86dce-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="86dce-124">Ad esempio, con un solo clic, Visual Studio aggiunge ai progetti il Dockerfile e il file docker-compose.yml con la configurazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86dce-124">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="86dce-125">Quando si esegue l'applicazione in Visual Studio, viene creata l'immagine Docker e l'applicazione a più contenitori viene eseguita direttamente in Docker; è anche possibile eseguire il debug di diversi contenitori contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="86dce-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="86dce-126">Queste funzionalità rendono lo sviluppo più veloce.</span><span class="sxs-lookup"><span data-stu-id="86dce-126">These features will boost your development speed.</span></span>

<span data-ttu-id="86dce-127">Tuttavia, anche se Visual Studio automatizza questi passaggi, ciò non significa che non sia necessario sapere cosa succede dietro le quinte con Docker.</span><span class="sxs-lookup"><span data-stu-id="86dce-127">However, just because Visual Studio makes those steps automatic does not mean that you do not need to know what is going on underneath with Docker.</span></span> <span data-ttu-id="86dce-128">Perciò il materiale sussidiario che segue descrive dettagliatamente ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="86dce-128">Therefore, in the guidance that follows, we detail every step.</span></span>

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="86dce-129">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="86dce-129">Step 1.</span></span> <span data-ttu-id="86dce-130">Iniziare a scrivere il codice e ad abbozzare l'applicazione o il servizio</span><span class="sxs-lookup"><span data-stu-id="86dce-130">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="86dce-131">Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza Docker.</span><span class="sxs-lookup"><span data-stu-id="86dce-131">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="86dce-132">La differenza è che, quando si sviluppa per Docker, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="86dce-132">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="86dce-133">Il contenitore può essere di tipo Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="86dce-133">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="86dce-134">Configurare l'ambiente locale con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86dce-134">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="86dce-135">Per iniziare, accertarsi che sia installato [Docker Community Edition (CE)](https://www.docker.com/community-edition) per Windows, come spiegato nelle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="86dce-135">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="86dce-136">Introduzione a Docker CE per Windows</span><span class="sxs-lookup"><span data-stu-id="86dce-136">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="86dce-137">Inoltre è necessario avere installato Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="86dce-137">In addition, you will need Visual Studio 2017 installed.</span></span> <span data-ttu-id="86dce-138">Questa versione è preferibile rispetto a Visual Studio 2015 con il componente aggiuntivo Visual Studio Tools for Docker perché Visual Studio 2017 è dotato di un supporto più avanzato per Docker, ad esempio supporta il debug dei contenitori.</span><span class="sxs-lookup"><span data-stu-id="86dce-138">This is preferred over Visual Studio 2015 with the Visual Studio Tools for Docker add-in, because Visual Studio 2017 has more advanced support for Docker, like support for debugging containers.</span></span> <span data-ttu-id="86dce-139">Visual Studio 2017 include gli strumenti per Docker se è stato selezionato il carico di lavoro **.NET Core e Docker** durante l'installazione, come illustrato nella figura 5-2.</span><span class="sxs-lookup"><span data-stu-id="86dce-139">Visual Studio 2017 includes the tooling for Docker if you selected the **.NET Core and Docker** workload during installation, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="86dce-140">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="86dce-140">**Figure 5-2**.</span></span> <span data-ttu-id="86dce-141">Selezione del carico di lavoro **.NET Core e Docker** durante l'installazione di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="86dce-141">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="86dce-142">È possibile iniziare a scrivere il codice dell'applicazione in .NET normale, di solito in .NET Core se si prevede di usare contenitori, anche prima di attivare Docker nell'applicazione e di eseguire la distribuzione e i test in Docker,</span><span class="sxs-lookup"><span data-stu-id="86dce-142">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="86dce-143">ma si consiglia di iniziare a lavorare in Docker appena possibile, perché quello sarà l'ambiente reale e gli eventuali problemi possono essere individuati velocemente.</span><span class="sxs-lookup"><span data-stu-id="86dce-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="86dce-144">Si consiglia di procedere in questo modo perché Visual Studio facilita così tanto il lavoro con Docker da diventare quasi trasparente, soprattutto quando lo si usa per eseguire il debug di applicazioni a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="86dce-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="86dce-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86dce-145">Additional resources</span></span>

-   <span data-ttu-id="86dce-146">**Introduzione a Docker CE per Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span><span class="sxs-lookup"><span data-stu-id="86dce-146">**Get started with Docker CE for Windows**
[*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)</span></span>

-   <span data-ttu-id="86dce-147">**Visual Studio 2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span><span class="sxs-lookup"><span data-stu-id="86dce-147">**Visual Studio 2017**
[*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)</span></span>

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="86dce-148">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="86dce-148">Step 2.</span></span> <span data-ttu-id="86dce-149">Creare un Dockerfile correlato a un'immagine di base .NET esistente</span><span class="sxs-lookup"><span data-stu-id="86dce-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="86dce-150">È necessario un Dockerfile per ogni immagine personalizzata che si desidera creare; è necessario un Dockerfile per ogni contenitore da distribuire, sia che si esegua la distribuzione automaticamente da Visual Studio o manualmente con la CLI di Docker: comandi docker run e docker-compose.</span><span class="sxs-lookup"><span data-stu-id="86dce-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="86dce-151">Se l'applicazione contiene un solo servizio personalizzato, è necessario un solo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="86dce-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="86dce-152">Se l'applicazione contiene più servizi, come in un'architettura a microservizi, è necessario un Dockerfile per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="86dce-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="86dce-153">Il Dockerfile viene inserito nella cartella radice dell'applicazione o del servizio.</span><span class="sxs-lookup"><span data-stu-id="86dce-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="86dce-154">Contiene i comandi che indicano a Docker come configurare ed eseguire l'applicazione o il servizio in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="86dce-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="86dce-155">È possibile creare manualmente un Dockerfile nel codice e aggiungerlo al progetto insieme alle dipendenze .NET.</span><span class="sxs-lookup"><span data-stu-id="86dce-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="86dce-156">Con Visual Studio e i relativi strumenti per Docker questa attività richiede solo pochi clic del mouse.</span><span class="sxs-lookup"><span data-stu-id="86dce-156">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="86dce-157">Quando si crea un nuovo progetto in Visual Studio 2017, è disponibile un'opzione denominata **Abilita supporto Docker**, come illustrato nella figura 5-3.</span><span class="sxs-lookup"><span data-stu-id="86dce-157">When you create a new project in Visual Studio 2017, there is an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![](./media/image5.png)

<span data-ttu-id="86dce-158">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="86dce-158">**Figure 5-3**.</span></span> <span data-ttu-id="86dce-159">Abilitazione del supporto Docker quando si crea un nuovo progetto in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="86dce-159">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="86dce-160">È possibile abilitare il supporto Docker in un progetto nuovo o esistente facendo clic con il pulsante destro del mouse sul file di progetto in Visual Studio e selezionando l'opzione **Aggiungi Supporto Docker**, come illustrato nella figura 5-4.</span><span class="sxs-lookup"><span data-stu-id="86dce-160">You can also enable Docker support on a new or existing project by right-clicking your project file in Visual Studio and selecting the option **Add-Docker Project Support**, as shown in Figure 5-4.</span></span>

![](./media/image6.png)

<span data-ttu-id="86dce-161">**Figura 5-4**.</span><span class="sxs-lookup"><span data-stu-id="86dce-161">**Figure 5-4**.</span></span> <span data-ttu-id="86dce-162">Abilitazione del supporto Docker in un progetto Visual Studio 2017 esistente</span><span class="sxs-lookup"><span data-stu-id="86dce-162">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="86dce-163">Questa azione eseguita su un progetto, come un'applicazione Web ASP.NET o un servizio Web API, aggiunge un Dockerfile al progetto con la configurazione necessaria.</span><span class="sxs-lookup"><span data-stu-id="86dce-163">This action on a project (like an ASP.NET Web application or Web API service) adds a Dockerfile to the project with the required configuration.</span></span> <span data-ttu-id="86dce-164">Aggiunge anche un file docker-compose.yml per l'intera soluzione.</span><span class="sxs-lookup"><span data-stu-id="86dce-164">It also adds a docker-compose.yml file for the whole solution.</span></span> <span data-ttu-id="86dce-165">Nelle sezioni seguenti sono descritte le informazioni da inserire in ciascuno di questi file.</span><span class="sxs-lookup"><span data-stu-id="86dce-165">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="86dce-166">Visual Studio fa tutto questo automaticamente, ma è utile sapere cosa deve contenere un Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="86dce-166">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="86dce-167">Opzione A: creazione di un progetto con un'immagine Docker .NET ufficiale esistente</span><span class="sxs-lookup"><span data-stu-id="86dce-167">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="86dce-168">In genere si crea un'immagine personalizzata per il contenitore sopra un'immagine di base che è possibile ottenere da un repository ufficiale nel registro [Hub Docker](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="86dce-168">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="86dce-169">Questo è esattamente ciò che accade dietro le quinte quando si attiva il supporto Docker in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86dce-169">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="86dce-170">Il Dockerfile userà un'immagine aspnetcore esistente.</span><span class="sxs-lookup"><span data-stu-id="86dce-170">Your Dockerfile will use an existing aspnetcore image.</span></span>

<span data-ttu-id="86dce-171">In precedenza si è visto le immagini e repository Docker da usare in base al framework e al sistema operativo scelto.</span><span class="sxs-lookup"><span data-stu-id="86dce-171">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="86dce-172">Ad esempio, se si desidera usare ASP.NET Core (Linux o Windows), l'immagine da utilizzare è microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="86dce-172">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="86dce-173">Pertanto è sufficiente specificare l'immagine Docker di base che sarà usata per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="86dce-173">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="86dce-174">Lo si fa aggiungendo FROM microsoft/aspnetcore:2.0 al Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="86dce-174">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="86dce-175">Visual Studio esegue l'operazione automaticamente, ma se si aggiornasse la versione, verrebbe aggiornato anche questo valore.</span><span class="sxs-lookup"><span data-stu-id="86dce-175">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="86dce-176">L'uso di un repository ufficiale di immagini .NET di Docker Hub con un numero di versione garantisce che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.</span><span class="sxs-lookup"><span data-stu-id="86dce-176">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="86dce-177">L'esempio seguente illustra un esempio di Dockerfile per un contenitore ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="86dce-177">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="86dce-178">In questo caso il contenitore è basato sulla versione 2.0 dell'immagine ASP.NET Core Docker ufficiale (multi-arch per Linux e Windows).</span><span class="sxs-lookup"><span data-stu-id="86dce-178">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="86dce-179">Si tratta dell'impostazione `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="86dce-179">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="86dce-180">Per altre informazioni su questa immagine di base, vedere la pagina [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) (Immagine ASP.NET Core Docker) e la pagina [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) (Immagine .NET Core Docker). Nel Dockerfile è necessario anche indicare al Docker di rimanere in ascolto sulla porta TCP che sarà usata in fase di esecuzione, in questo caso la porta 80 configurata con l'impostazione EXPOSE.</span><span class="sxs-lookup"><span data-stu-id="86dce-180">(For further details about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="86dce-181">Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso.</span><span class="sxs-lookup"><span data-stu-id="86dce-181">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="86dce-182">Ad esempio, la riga ENTRYPOINT con \["dotnet", "MySingleContainerWebApp.dll"\] indica a Docker di eseguire un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="86dce-182">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="86dce-183">Se si usa l'SDK e la CLI di .NET Core, ovvero la CLI dotnet per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa.</span><span class="sxs-lookup"><span data-stu-id="86dce-183">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="86dce-184">In sostanza la riga ENTRYPOINT e altre impostazioni saranno diverse a seconda del linguaggio e della piattaforma scelti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="86dce-184">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="86dce-185">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86dce-185">Additional resources</span></span>

-   <span data-ttu-id="86dce-186">**Creazione di immagini Docker per applicazioni .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span><span class="sxs-lookup"><span data-stu-id="86dce-186">**Building Docker Images for .NET Core Applications**
[*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)</span></span>

-   <span data-ttu-id="86dce-187">**Creare un'immagine**.</span><span class="sxs-lookup"><span data-stu-id="86dce-187">**Build your own image**.</span></span> <span data-ttu-id="86dce-188">Nella documentazione ufficiale di Docker.</span><span class="sxs-lookup"><span data-stu-id="86dce-188">In the official Docker documentation.</span></span>
    [<span data-ttu-id="86dce-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span><span class="sxs-lookup"><span data-stu-id="86dce-189">*https://docs.docker.com/engine/tutorials/dockerimages/*</span></span>](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="86dce-190">Uso di repository di immagini multi-arch</span><span class="sxs-lookup"><span data-stu-id="86dce-190">Using multi-arch image repositories</span></span>

<span data-ttu-id="86dce-191">Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows.</span><span class="sxs-lookup"><span data-stu-id="86dce-191">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="86dce-192">Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="86dce-192">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="86dce-193">Ad esempio, il repository [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) disponibile nel registro Docker Hub fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di repository.</span><span class="sxs-lookup"><span data-stu-id="86dce-193">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="86dce-194">Se si specifica un tag, ci si rivolge a una piattaforma esplicita come nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="86dce-194">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

-   <span data-ttu-id="86dce-195">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="86dce-195">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux 

-   <span data-ttu-id="86dce-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="86dce-196">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="86dce-197">Ma, e questa è una novità da metà 2017, se si specifica lo stesso nome di immagine, anche con lo stesso tag, le nuove immagini multi-arch, come l'immagine aspnetcore che supporta multi-arch, useranno la versione Linux o Windows in base al sistema operativo host Docker che si sta distribuendo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="86dce-197">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

-   <span data-ttu-id="86dce-198">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="86dce-198">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="86dce-199">In questo modo, se si esegue il pull di un'immagine da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome di immagine da un host Linux si ottiene la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="86dce-199">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="86dce-200">Opzione B: creazione dell'immagine di base da zero</span><span class="sxs-lookup"><span data-stu-id="86dce-200">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="86dce-201">È possibile creare un'immagine Docker di base da zero.</span><span class="sxs-lookup"><span data-stu-id="86dce-201">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="86dce-202">Questo scenario non è consigliato se non si conosce bene Docker, ma se si vuole creare la propria immagine di base è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="86dce-202">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="86dce-203">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86dce-203">Additional resources</span></span>

-   <span data-ttu-id="86dce-204">**Immagini multi-arch .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="86dce-204">**Multi-arch .NET Core images**.</span></span>
<span data-ttu-id="86dce-205">https://github.com/dotnet/announcements/issues/14</span><span class="sxs-lookup"><span data-stu-id="86dce-205">https://github.com/dotnet/announcements/issues/14</span></span> 
-   <span data-ttu-id="86dce-206">**Creare un'immagine di base**.</span><span class="sxs-lookup"><span data-stu-id="86dce-206">**Create a base image**.</span></span> <span data-ttu-id="86dce-207">Documentazione ufficiale di Docker.</span><span class="sxs-lookup"><span data-stu-id="86dce-207">Official Docker documentation.</span></span>
    [<span data-ttu-id="86dce-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span><span class="sxs-lookup"><span data-stu-id="86dce-208">*https://docs.docker.com/engine/userguide/eng-image/baseimages/*</span></span>](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="86dce-209">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="86dce-209">Step 3.</span></span> <span data-ttu-id="86dce-210">Creare le immagini Docker personalizzate e incorporare l'applicazione o il servizio in esse</span><span class="sxs-lookup"><span data-stu-id="86dce-210">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="86dce-211">Per ogni servizio dell'applicazione è necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="86dce-211">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="86dce-212">Se l'applicazione è costituita da un singolo servizio o applicazione Web, è sufficiente una singola immagine.</span><span class="sxs-lookup"><span data-stu-id="86dce-212">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="86dce-213">Si noti che le immagini Docker vengono create automaticamente in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="86dce-213">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="86dce-214">I passaggi seguenti sono necessari solo per il flusso di lavoro editor/CLI e sono descritti per chiarire meglio ciò che succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="86dce-214">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="86dce-215">Lo sviluppatore deve eseguire lo sviluppo e i test localmente finché non esegue il push di una funzionalità o di una modifica completa nel sistema di controllo del codice sorgente, ad esempio in GitHub.</span><span class="sxs-lookup"><span data-stu-id="86dce-215">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="86dce-216">Ciò significa che è necessario creare le immagini Docker e distribuire i contenitori in un host Docker locale, ovvero una VM Windows o Linux, nonché eseguire, testare ed eseguire il debug in tali contenitori locale.</span><span class="sxs-lookup"><span data-stu-id="86dce-216">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="86dce-217">Per creare un'immagine personalizzata nell'ambiente locale tramite la CLI di Docker e il Dockerfile, è possibile usare il comando docker build, come illustrato nella figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="86dce-217">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![](./media/image8.png)

<span data-ttu-id="86dce-218">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="86dce-218">**Figure 5-5**.</span></span> <span data-ttu-id="86dce-219">Creazione di un'immagine Docker personalizzata</span><span class="sxs-lookup"><span data-stu-id="86dce-219">Creating a custom Docker image</span></span>

<span data-ttu-id="86dce-220">Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è possibile generare innanzitutto una cartella distribuibile con le raccolte .NET e i file binari necessari eseguendo dotnet publish e quindi usando il comando docker build.</span><span class="sxs-lookup"><span data-stu-id="86dce-220">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="86dce-221">Verrà creata così un'immagine Docker con il nome cesardl/netcore-webapi-microservice-docker:first.</span><span class="sxs-lookup"><span data-stu-id="86dce-221">This will create a Docker image with the name cesardl/netcore-webapi-microservice-docker:first.</span></span> <span data-ttu-id="86dce-222">In questo caso :first è un tag che rappresenta una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="86dce-222">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="86dce-223">È possibile ripetere questo passaggio per ogni immagine personalizzata da creare per l'applicazione Docker composta.</span><span class="sxs-lookup"><span data-stu-id="86dce-223">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="86dce-224">Quando un'applicazione è costituita da più contenitori, è un'applicazione a più contenitori, è anche possibile usare il comando docker-compose up --build per compilare tutte le immagini correlate con un singolo comando usando i metadati esposti nei file docker-compose.yml correlati.</span><span class="sxs-lookup"><span data-stu-id="86dce-224">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="86dce-225">È possibile trovare le immagini esistenti nel repository locale tramite il comando docker images, come illustrato nella figura 5-6.</span><span class="sxs-lookup"><span data-stu-id="86dce-225">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![](./media/image9.png)

<span data-ttu-id="86dce-226">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="86dce-226">**Figure 5-6.**</span></span> <span data-ttu-id="86dce-227">Visualizzazione di immagini esistente con il comando docker images</span><span class="sxs-lookup"><span data-stu-id="86dce-227">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="86dce-228">Creazione di immagini Docker con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86dce-228">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="86dce-229">Quando si usa Visual Studio per creare un progetto con il supporto Docker, non si crea un'immagine in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="86dce-229">When you are using Visual Studio to create a project with Docker support, you do not explicitly create an image.</span></span> <span data-ttu-id="86dce-230">L'immagine viene invece creata automaticamente quando si premere F5 e si esegue l'applicazione o il servizio Docker.</span><span class="sxs-lookup"><span data-stu-id="86dce-230">Instead, the image is created for you when you press F5 and run the dockerized application or service.</span></span> <span data-ttu-id="86dce-231">Questo passaggio è automatico e invisibile in Visual Studio, ma è importante sapere cosa succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="86dce-231">This step is automatic in Visual Studio, and you will not see it happen, but it is important that you know what is going on underneath.</span></span>

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="86dce-232">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="86dce-232">Step 4.</span></span> <span data-ttu-id="86dce-233">Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori</span><span class="sxs-lookup"><span data-stu-id="86dce-233">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="86dce-234">Il file [docker compose.yml](https://docs.docker.com/compose/compose-file/) consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="86dce-234">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="86dce-235">Per usare un file docker-compose.yml, è necessario creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="86dce-235">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

<span data-ttu-id="86dce-236">Si noti che questo file docker-compose.yml è una versione semplificata e unita.</span><span class="sxs-lookup"><span data-stu-id="86dce-236">Note that this docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="86dce-237">Contiene dati di configurazione statici per ogni contenitore, ad esempio il nome dell'immagine personalizzata, sempre applicabili, nonché informazioni di configurazione che potrebbero dipendere dall'ambiente di distribuzione, ad esempio la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="86dce-237">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="86dce-238">In seguito si vedrà come suddividere la configurazione di docker-compose.yml in più file docker-compose e sostituire valori a seconda del tipo di ambiente e di esecuzione, ovvero debug o release.</span><span class="sxs-lookup"><span data-stu-id="86dce-238">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="86dce-239">L'esempio del file docker-compose.yml definisce cinque servizi: il servizio webmvc, che è un'applicazione Web; due microservizi, ovvero catalog.api e ordering.api; un contenitore origine dati, sql.data, basato su SQL Server per Linux eseguito come contenitore.</span><span class="sxs-lookup"><span data-stu-id="86dce-239">The docker-compose.yml file example defines five services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="86dce-240">Ogni servizio è distribuito come contenitore, quindi è necessaria un'immagine Docker per ciascuno.</span><span class="sxs-lookup"><span data-stu-id="86dce-240">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="86dce-241">Il file docker-compose.yml specifica non solo quali contenitori vengono usati, ma come sono configurati singolarmente.</span><span class="sxs-lookup"><span data-stu-id="86dce-241">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="86dce-242">Ad esempio, la definizione del contenitore webmvc nel file .yml:</span><span class="sxs-lookup"><span data-stu-id="86dce-242">For instance, the webmvc container definition in the .yml file:</span></span>

-   <span data-ttu-id="86dce-243">Usa un'immagine eshop/web:latest precompilata.</span><span class="sxs-lookup"><span data-stu-id="86dce-243">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="86dce-244">Tuttavia, è anche possibile configurare l'immagine in modo che sia compilata come parte dell'esecuzione di docker-compose con una configurazione aggiuntiva basata su una sezione build: nel file docker-compose.</span><span class="sxs-lookup"><span data-stu-id="86dce-244">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

-   <span data-ttu-id="86dce-245">Inizializza due variabili di ambiente, ovvero CatalogUrl e OrderingUrl.</span><span class="sxs-lookup"><span data-stu-id="86dce-245">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

-   <span data-ttu-id="86dce-246">Inoltra la porta 80 esposta sul contenitore alla porta esterna 80 sul computer host.</span><span class="sxs-lookup"><span data-stu-id="86dce-246">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

-   <span data-ttu-id="86dce-247">Collega l'app Web al catalogo e al servizio di ordinazione con l'impostazione depends\_on.</span><span class="sxs-lookup"><span data-stu-id="86dce-247">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="86dce-248">In questo modo il servizio attende fino a quando vengono avviati i servizi.</span><span class="sxs-lookup"><span data-stu-id="86dce-248">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="86dce-249">Il file docker-compose.yml sarà esaminato di nuovo in una sezione successiva in cui sarà descritto come implementare microservizi e app a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="86dce-249">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="86dce-250">Utilizzo di docker-compose.yml in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="86dce-250">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="86dce-251">Quando si aggiunge il supporto per soluzioni Docker a un progetto di servizio in una soluzione Visual Studio, come illustrato nella figura 5-7, Visual Studio aggiunge al progetto un Dockerfile e aggiunge una sezione di servizio (progetto) alla soluzione con i file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="86dce-251">When you add Docker solution support to a service project in a Visual Studio solution, as shown in Figure 5-7, Visual Studio adds a Dockerfile to your project, and it adds a service section (project) in your solution with the docker-compose.yml files.</span></span> <span data-ttu-id="86dce-252">Questo è un modo semplice per iniziare a comporre una soluzione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="86dce-252">It is an easy way to start composing your multiple-container solution.</span></span> <span data-ttu-id="86dce-253">È quindi possibile aprire i file docker-compose.yml e aggiornarli con funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="86dce-253">You can then open the docker-compose.yml files and update them with additional features.</span></span>

![](./media/image6.png)

<span data-ttu-id="86dce-254">**Figura 5-7**.</span><span class="sxs-lookup"><span data-stu-id="86dce-254">**Figure 5-7**.</span></span> <span data-ttu-id="86dce-255">Aggiunta del supporto Docker in Visual Studio 2017 facendo clic con il pulsante destro del mouse su un progetto ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="86dce-255">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="86dce-256">Aggiungendo il supporto Docker in Visual Studio non solo viene aggiunto il Dockerfile al progetto, ma vengono aggiunte le informazioni di configurazione a più file docker-compose.yml globali che sono impostati a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="86dce-256">Adding Docker support in Visual Studio not only adds the Dockerfile to your project, but adds the configuration information to several global docker-compose.yml files that are set at the solution level.</span></span>

<span data-ttu-id="86dce-257">Dopo aver aggiunto il supporto Docker alla soluzione in Visual Studio, si noterà anche un nuovo nodo in Esplora soluzioni, nel file di progetto docker-compose.dcproj, che contiene i file docker-compose.yml aggiunti, come illustrato nella figura 5-8.</span><span class="sxs-lookup"><span data-stu-id="86dce-257">After you add Docker support to your solution in Visual Studio, you will also see a new node (in the docker-compose.dcproj project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![](./media/image11.PNG)

<span data-ttu-id="86dce-258">**Figura 5-8**.</span><span class="sxs-lookup"><span data-stu-id="86dce-258">**Figure 5-8**.</span></span> <span data-ttu-id="86dce-259">Il nodo dell'albero **docker-compose** aggiunto in Esplora soluzioni di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="86dce-259">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="86dce-260">È possibile distribuire un'applicazione a più contenitori con un file docker-compose.yml singolo usando il comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="86dce-260">You could deploy a multi-container application with a single docker-compose.yml file by using the docker-compose up command.</span></span> <span data-ttu-id="86dce-261">Tuttavia Visual Studio ne aggiunge un gruppo, perciò è possibile sostituire i valori a seconda dell'ambiente, ovvero sviluppo o produzione, e del tipo di esecuzione, ossia release o debug.</span><span class="sxs-lookup"><span data-stu-id="86dce-261">However, Visual Studio adds a group of them so you can override values depending on the environment (development versus production) and execution type (release versus debug).</span></span> <span data-ttu-id="86dce-262">Questa funzionalità sarà spiegata nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="86dce-262">This capability will be explained in later sections.</span></span>

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="86dce-263">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="86dce-263">Step 5.</span></span> <span data-ttu-id="86dce-264">Compilare ed eseguire l'applicazione Docker</span><span class="sxs-lookup"><span data-stu-id="86dce-264">Build and run your Docker application</span></span>

<span data-ttu-id="86dce-265">Se l'applicazione ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, ovvero una VM o un server fisico.</span><span class="sxs-lookup"><span data-stu-id="86dce-265">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="86dce-266">Se invece l'applicazione contiene più servizi, è possibile distribuirla come applicazione composta, usando un unico comando della CLI, ossia docker-compose up, o con Visual Studio, che userà lo stesso comando dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="86dce-266">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="86dce-267">Le diverse opzioni sono esaminate di seguito.</span><span class="sxs-lookup"><span data-stu-id="86dce-267">Let’s look at the different options.</span></span>

### <a name="option-a-running-a-single-container-with-docker-cli"></a><span data-ttu-id="86dce-268">Opzione A: esecuzione di un singolo contenitore con la CLI di Docker</span><span class="sxs-lookup"><span data-stu-id="86dce-268">Option A: Running a single-container with Docker CLI</span></span>

<span data-ttu-id="86dce-269">È possibile eseguire un contenitore Docker usando il comando docker run, come illustrato nella figura 5-9:</span><span class="sxs-lookup"><span data-stu-id="86dce-269">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

<span data-ttu-id="86dce-270">**Figura 5-9**.</span><span class="sxs-lookup"><span data-stu-id="86dce-270">**Figure 5-9**.</span></span> <span data-ttu-id="86dce-271">Esecuzione di un contenitore Docker usando il comando docker run</span><span class="sxs-lookup"><span data-stu-id="86dce-271">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="86dce-272">In questo caso il comando associa la porta interna 5000 del contenitore alla porta 80 del computer host.</span><span class="sxs-lookup"><span data-stu-id="86dce-272">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="86dce-273">Ciò significa che l'host è in ascolto sulla porta 80 e inoltra alla porta 5000 nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="86dce-273">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="86dce-274">Opzione B: esecuzione di un'applicazione a più contenitori</span><span class="sxs-lookup"><span data-stu-id="86dce-274">Option B: Running a multi-container application</span></span>

<span data-ttu-id="86dce-275">Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà composta da più servizi, perciò sarà necessario eseguire un'applicazione a più contenitori, come illustrato nella figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="86dce-275">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![](./media/image14.png)

<span data-ttu-id="86dce-276">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="86dce-276">**Figure 5-10**.</span></span> <span data-ttu-id="86dce-277">VM con contenitori Docker distribuiti</span><span class="sxs-lookup"><span data-stu-id="86dce-277">VM with Docker containers deployed</span></span>

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a><span data-ttu-id="86dce-278">Esecuzione di un'applicazione a più contenitori con la CLI di Docker</span><span class="sxs-lookup"><span data-stu-id="86dce-278">Running a multi-container application with the Docker CLI</span></span>

<span data-ttu-id="86dce-279">Per eseguire un'applicazione a più contenitori con la CLI di Docker, è possibile eseguire il comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="86dce-279">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="86dce-280">Questo comando usa il file docker-compose.yml disponibile a livello di soluzione per distribuire un'applicazione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="86dce-280">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="86dce-281">La figura 5-11 mostra i risultati che si ottengono quando si esegue il comando dalla directory principale del progetto, che contiene il file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="86dce-281">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![](./media/image15.png)

<span data-ttu-id="86dce-282">**Figura 5-11**.</span><span class="sxs-lookup"><span data-stu-id="86dce-282">**Figure 5-11**.</span></span> <span data-ttu-id="86dce-283">Esempio di risultati ottenuti eseguendo il comando docker-compose up</span><span class="sxs-lookup"><span data-stu-id="86dce-283">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="86dce-284">Dopo l'esecuzione del comando docker-compose up, l'applicazione e i contenitori correlati vengono distribuiti nell'host Docker, come illustrato nella rappresentazione di VM della figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="86dce-284">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as illustrated in the VM representation in Figure 5-10.</span></span>

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a><span data-ttu-id="86dce-285">Esecuzione e debug di un'applicazione a più contenitori con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86dce-285">Running and debugging a multi-container application with Visual Studio</span></span> 

<span data-ttu-id="86dce-286">Eseguire un'applicazione a più contenitori con Visual Studio 2017 è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="86dce-286">Running a multi-container application using Visual Studio 2017 cannot get simpler.</span></span> <span data-ttu-id="86dce-287">Non solo è possibile eseguire l'applicazione a più contenitori, ma è possibile eseguire il debug di tutti i relativi contenitori direttamente da Visual Studio impostando punti di interruzione normali.</span><span class="sxs-lookup"><span data-stu-id="86dce-287">You can not only run the multi-container application, but you are able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="86dce-288">Come accennato in precedenza, ogni volta che si aggiungere il supporto Docker a un progetto all'interno di una soluzione, il progetto è configurato nel file docker-compose.yml globale, a livello di soluzione, che consente di eseguire l'intera soluzione o di eseguirne il debug in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="86dce-288">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="86dce-289">Visual Studio avvia un solo contenitore per ogni progetto che ha il supporto Docker abilitato ed esegue automaticamente tutti i passaggi interni, ovvero pubblicazione dotnet, compilazione docker, ecc.</span><span class="sxs-lookup"><span data-stu-id="86dce-289">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="86dce-290">La cosa importante è che, come illustrato nella figura 5-12, in Visual Studio 2017 è presente un ulteriore comando **Docker** per il tasto funzione F5.</span><span class="sxs-lookup"><span data-stu-id="86dce-290">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="86dce-291">Questa opzione consente di eseguire un'applicazione a più contenitori o di eseguirne il debug eseguendo tutti i contenitori definiti nei file docker-compose.yml a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="86dce-291">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="86dce-292">Grazie alla capacità di eseguire il debug delle soluzioni a più contenitori, è possibile impostare più punti di interruzione, ciascuno in un progetto (contenitore) diverso, e durante il debug da Visual Studio l'esecuzione viene arrestata in corrispondenza dei punti di interruzione definiti in progetti diversi ed eseguiti in contenitori diversi.</span><span class="sxs-lookup"><span data-stu-id="86dce-292">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![](./media/image16.png)

<span data-ttu-id="86dce-293">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="86dce-293">**Figure 5-12**.</span></span> <span data-ttu-id="86dce-294">Esecuzione di applicazioni a più contenitori in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="86dce-294">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="86dce-295">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86dce-295">Additional resources</span></span>

-   <span data-ttu-id="86dce-296">**Distribuire un contenitore ASP.NET in un host Docker remoto**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span><span class="sxs-lookup"><span data-stu-id="86dce-296">**Deploy an ASP.NET container to a remote Docker host**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)</span></span>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="86dce-297">Una nota sul test e la distribuzione con agenti di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="86dce-297">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="86dce-298">I comandi docker-compose up e docker run, o l'esecuzione e il debug dei contenitori in Visual Studio, sono adeguati per eseguire test sui contenitori nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="86dce-298">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="86dce-299">Questo approccio invece non si deve usare se la destinazione è costituita da cluster e agenti di orchestrazione Docker come Swarm, Mesosphere DC/OS o Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="86dce-299">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="86dce-300">Se si usa un cluster come la [modalità Docker Swarm](https://docs.docker.com/engine/swarm/), disponibile in Docker CE per Windows e Mac dalla versione 1.12, è necessario eseguire la distribuzione e i test con altri comandi, ad esempio [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) per servizi singoli.</span><span class="sxs-lookup"><span data-stu-id="86dce-300">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="86dce-301">Se si distribuisce un'applicazione composta da diversi contenitori, usare [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) e [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) per distribuire l'applicazione composta come *stack*.</span><span class="sxs-lookup"><span data-stu-id="86dce-301">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="86dce-302">Per altre informazioni, vedere il post di blog [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) (Presentazione di bundle applicativi distribuiti sperimentali) nella documentazione di Docker</span><span class="sxs-lookup"><span data-stu-id="86dce-302">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="86dce-303">nel sito di Docker.</span><span class="sxs-lookup"><span data-stu-id="86dce-303">on the Docker site.</span></span>

<span data-ttu-id="86dce-304">Per [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) si usano comandi di distribuzione e script diversi.</span><span class="sxs-lookup"><span data-stu-id="86dce-304">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="86dce-305">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="86dce-305">Step 6.</span></span> <span data-ttu-id="86dce-306">Testare l'applicazione Docker usando l'host Docker locale</span><span class="sxs-lookup"><span data-stu-id="86dce-306">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="86dce-307">Questo passaggio varia in base a ciò che l'applicazione sta facendo.</span><span class="sxs-lookup"><span data-stu-id="86dce-307">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="86dce-308">In un'applicazione Web .NET Core semplice che viene distribuita come contenitore o servizio singolo è possibile accedere al servizio aprendo un browser nell'host Docker e passando a quel sito, come illustrato nella figura 5-13.</span><span class="sxs-lookup"><span data-stu-id="86dce-308">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site as shown in Figure 5-13.</span></span> <span data-ttu-id="86dce-309">Se la configurazione nel Dockerfile abbina il contenitore a una porta dell'host diversa dalla 80, includere la porta host nell'URL.</span><span class="sxs-lookup"><span data-stu-id="86dce-309">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host post in the URL.)</span></span>

![](./media/image18.png)

<span data-ttu-id="86dce-310">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="86dce-310">**Figure 5-13**.</span></span> <span data-ttu-id="86dce-311">Esempio di test dell'applicazione Docker in locale mediante localhost</span><span class="sxs-lookup"><span data-stu-id="86dce-311">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="86dce-312">Se localhost non punta all'IP dell'host Docker, come succede per impostazione predefinita quando si usa Docker CE, per passare al servizio usare l'indirizzo IP della scheda di rete del computer.</span><span class="sxs-lookup"><span data-stu-id="86dce-312">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="86dce-313">Si noti che questo URL nel browser usa la porta 80 per lo specifico contenitore di esempio di cui si tratta.</span><span class="sxs-lookup"><span data-stu-id="86dce-313">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="86dce-314">Tuttavia internamente le richieste vengono reindirizzate alla porta 5000 perché è stato distribuito in questo modo con il comando docker run, come illustrato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="86dce-314">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="86dce-315">È anche possibile testare l'applicazione usando curl dal terminale, come illustrato nella figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="86dce-315">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="86dce-316">In un'installazione di Docker in Windows, il valore IP dell'host Docker predefinito è sempre 10.0.75.1 in aggiunta all'indirizzo IP effettivo del computer.</span><span class="sxs-lookup"><span data-stu-id="86dce-316">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![](./media/image19.png)

<span data-ttu-id="86dce-317">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="86dce-317">**Figure 5-14**.</span></span> <span data-ttu-id="86dce-318">Esempio di test dell'applicazione Docker in locale mediante curl</span><span class="sxs-lookup"><span data-stu-id="86dce-318">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="86dce-319">Test e debug di contenitori con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="86dce-319">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="86dce-320">Quando si eseguono contenitori e se ne esegue il debug con Visual Studio 2017, è possibile eseguire il debug dell'applicazione .NET nello stesso modo che si userebbe per l'esecuzione senza contenitori.</span><span class="sxs-lookup"><span data-stu-id="86dce-320">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="86dce-321">Test e debug senza Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86dce-321">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="86dce-322">Se si sviluppa usando l'approccio editor/CLI, eseguire il debug dei contenitori è più difficile ed è preferibile farlo tramite la generazione di tracce.</span><span class="sxs-lookup"><span data-stu-id="86dce-322">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="86dce-323">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86dce-323">Additional resources</span></span>

-   <span data-ttu-id="86dce-324">**Debug di app in un contenitore Docker locale**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span><span class="sxs-lookup"><span data-stu-id="86dce-324">**Debugging apps in a local Docker container**
[*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)</span></span>

-   <span data-ttu-id="86dce-325">**Steve Lasker. Compilare, eseguire il debug e distribuire app ASP.NET Core con Docker.**</span><span class="sxs-lookup"><span data-stu-id="86dce-325">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="86dce-326">Video.</span><span class="sxs-lookup"><span data-stu-id="86dce-326">Video.</span></span>
    [<span data-ttu-id="86dce-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span><span class="sxs-lookup"><span data-stu-id="86dce-327">*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*</span></span>](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="86dce-328">Flusso di lavoro semplificato per lo sviluppo di contenitori con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86dce-328">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="86dce-329">Il flusso di lavoro quando si usa Visual Studio è molto più semplice rispetto all'uso dell'approccio editor/CLI.</span><span class="sxs-lookup"><span data-stu-id="86dce-329">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="86dce-330">La maggior parte dei passaggi richiesti da Docker correlati ai file Dockerfile e docker-compose.yml sono nascosti o semplificati da Visual Studio, come illustrato nella figura 5-15.</span><span class="sxs-lookup"><span data-stu-id="86dce-330">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![](./media/image20.png)

<span data-ttu-id="86dce-331">**Figura 5-15**.</span><span class="sxs-lookup"><span data-stu-id="86dce-331">**Figure 5-15**.</span></span> <span data-ttu-id="86dce-332">Flusso di lavoro semplificato per lo sviluppo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="86dce-332">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="86dce-333">Inoltre è sufficiente eseguire una sola volta il passaggio 2, ovvero l'aggiunta del supporto Docker ai progetti.</span><span class="sxs-lookup"><span data-stu-id="86dce-333">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="86dce-334">Pertanto il flusso di lavoro è simile alle attività di sviluppo normale quando si usa .NET per qualsiasi altro tipo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="86dce-334">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="86dce-335">È necessario sapere cosa succede dietro le quinte, ad esempio il processo di creazione delle immagini, quali immagini di base vengono usate, la distribuzione dei contenitori e così via; in alcuni casi è anche necessario modificare il file Dockerfile o docker-compose.ym per personalizzare i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="86dce-335">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="86dce-336">Se si usa Visual Studio la maggior parte del lavoro viene notevolmente semplificata e la produttività è maggiore.</span><span class="sxs-lookup"><span data-stu-id="86dce-336">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="86dce-337">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86dce-337">Additional resources</span></span>

-   <span data-ttu-id="86dce-338">**Steve Lasker. Sviluppo di .NET Docker con Visual Studio 2017**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span><span class="sxs-lookup"><span data-stu-id="86dce-338">**Steve Lasker. .NET Docker Development with Visual Studio 2017**
[*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)</span></span>

-   <span data-ttu-id="86dce-339">**Jeffrey T. Fritz. Inserire un'app .NET Core in un contenitore con i nuovi strumenti Docker per Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span><span class="sxs-lookup"><span data-stu-id="86dce-339">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**
[*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)</span></span>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="86dce-340">Uso dei comandi di PowerShell in un Dockerfile per configurare contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="86dce-340">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="86dce-341">I [contenitori Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) consentono di convertire applicazioni Windows esistenti in immagini Docker e distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker.</span><span class="sxs-lookup"><span data-stu-id="86dce-341">[Windows Containers](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="86dce-342">Per usare i contenitori Windows si eseguono i comandi di PowerShell in Dockerfile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="86dce-342">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="86dce-343">In questo caso si usa un'immagine di base di Windows Server Core (impostazione FROM) e si installa IIS con un comando di PowerShell (impostazione RUN).</span><span class="sxs-lookup"><span data-stu-id="86dce-343">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="86dce-344">In modo analogo è possibile usare i comandi di PowerShell anche per configurare componenti aggiuntivi come ASP.NET 4. x, .NET 4.6 o qualsiasi altro software Windows.</span><span class="sxs-lookup"><span data-stu-id="86dce-344">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="86dce-345">Ad esempio il comando seguente in un Dockerfile configura ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="86dce-345">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="86dce-346">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="86dce-346">Additional resources</span></span>

-   <span data-ttu-id="86dce-347">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="86dce-347">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="86dce-348">Comandi di Powershell di esempio eseguibili da dockerfile per includere funzionalità di Windows.</span><span class="sxs-lookup"><span data-stu-id="86dce-348">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>
    [<span data-ttu-id="86dce-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span><span class="sxs-lookup"><span data-stu-id="86dce-349">*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*</span></span>](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
<span data-ttu-id="86dce-350">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span><span class="sxs-lookup"><span data-stu-id="86dce-350">[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)</span></span>
