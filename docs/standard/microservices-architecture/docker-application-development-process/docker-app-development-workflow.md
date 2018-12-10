---
title: Flusso di lavoro di sviluppo per app Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Flusso di lavoro di sviluppo per app Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/05/2018
ms.openlocfilehash: bc6b1796ed7b12a04affc521ac2efee515c48ae2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53150550"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="4656d-103">Flusso di lavoro di sviluppo per app Docker</span><span class="sxs-lookup"><span data-stu-id="4656d-103">Development workflow for Docker apps</span></span>

<span data-ttu-id="4656d-104">Il ciclo di vita dello sviluppo applicativo inizia al computer di ogni sviluppatore quando l'applicazione viene scritta usando un determinato linguaggio e viene testata in locale.</span><span class="sxs-lookup"><span data-stu-id="4656d-104">The application development life cycle starts at each developer’s machine, where the developer codes the application using their preferred language and tests it locally.</span></span> <span data-ttu-id="4656d-105">Indipendentemente dal linguaggio, il framework e la piattaforma scelti, con questo flusso di lavoro lo sviluppatore scrive e testa sempre contenitori Docker, ma localmente.</span><span class="sxs-lookup"><span data-stu-id="4656d-105">No matter which language, framework, and platform the developer chooses, with this workflow, the developer is always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="4656d-106">Ogni contenitore, ovvero un'istanza di un'immagine Docker, include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4656d-106">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="4656d-107">Un sistema operativo a scelta, come una distribuzione Linux, Windows Nano Server o Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="4656d-107">An operating system selection (for example, a Linux distribution, Windows Nano Server, or Windows Server Core).</span></span>

- <span data-ttu-id="4656d-108">File aggiunti dallo sviluppatore, ovvero file binari dell'applicazione e così via.</span><span class="sxs-lookup"><span data-stu-id="4656d-108">Files added by the developer (application binaries, etc.).</span></span>

- <span data-ttu-id="4656d-109">Informazioni di configurazione, come impostazioni di ambiente e dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4656d-109">Configuration information (environment settings and dependencies).</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="4656d-110">Flusso di lavoro per lo sviluppo di applicazioni Docker basate su contenitore</span><span class="sxs-lookup"><span data-stu-id="4656d-110">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="4656d-111">Questa sezione descrive il flusso di lavoro di sviluppo a *ciclo interno* per applicazioni Docker basate su contenitore.</span><span class="sxs-lookup"><span data-stu-id="4656d-111">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="4656d-112">Flusso di lavoro a ciclo interno significa che non tiene conto del flusso di lavoro DevOps più ampio e si concentra solo sul lavoro di sviluppo eseguito sul computer dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="4656d-112">The inner-loop workflow means it is not taking into account the broader DevOps workflow and just focuses on the development work done on the developer’s computer.</span></span> <span data-ttu-id="4656d-113">I passaggi iniziali per configurare l'ambiente non sono inclusi, in quanto sono eseguiti una sola volta.</span><span class="sxs-lookup"><span data-stu-id="4656d-113">The initial steps to set up the environment are not included, since those are done only once.</span></span>

<span data-ttu-id="4656d-114">Un'applicazione è costituita da servizi e raccolte aggiuntive, ossia dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4656d-114">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="4656d-115">Di seguito sono indicati i passaggi di base che si eseguono in genere quando si compila un'applicazione Docker, come illustrato nella figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="4656d-115">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![Immagine per il flusso di lavoro passo per passo per lo sviluppo di applicazioni Docker in contenitori](./media/image1.png)

<span data-ttu-id="4656d-117">**Figura 5-1.**</span><span class="sxs-lookup"><span data-stu-id="4656d-117">**Figure 5-1.**</span></span> <span data-ttu-id="4656d-118">Flusso di lavoro passo per passo per lo sviluppo di applicazioni Docker in contenitori</span><span class="sxs-lookup"><span data-stu-id="4656d-118">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="4656d-119">Questa guida descrive nei dettagli l'intero processo e ogni passaggio principale è spiegato con riferimento all'ambiente Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4656d-119">In this guide, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="4656d-120">Quando si usa un approccio di sviluppo editor/CLI, ad esempio codice Visual Studio e CLI di Docker in macOS o Windows, di solito è necessario conoscere ogni passaggio in modo più dettagliato rispetto all'uso di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4656d-120">When you are using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you are using Visual Studio.</span></span> <span data-ttu-id="4656d-121">Per altre informazioni sull'uso di un ambiente CLI, vedere l'e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo di vita di un'applicazione Docker in un contenitore con piattaforme e strumenti Microsoft).</span><span class="sxs-lookup"><span data-stu-id="4656d-121">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="4656d-122">Quando si usa Visual Studio molti di questi passaggi sono gestiti automaticamente e questo migliora notevolmente la produttività.</span><span class="sxs-lookup"><span data-stu-id="4656d-122">When you're using Visual Studio, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="4656d-123">Ciò vale soprattutto quando si usa Visual Studio 2017 con applicazioni a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="4656d-123">This is especially true when you are using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="4656d-124">Ad esempio, con un solo clic, Visual Studio aggiunge ai progetti il *Dockerfile* e i file *docker-compose.yml* con la configurazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4656d-124">For instance, with just one mouse click, Visual Studio adds the *Dockerfile* and *docker-compose.yml* files to your projects with the configuration for your application.</span></span> <span data-ttu-id="4656d-125">Quando si esegue l'applicazione in Visual Studio, viene creata l'immagine Docker e l'applicazione a più contenitori viene eseguita direttamente in Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-125">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker.</span></span> <span data-ttu-id="4656d-126">Si può anche eseguire il debug di diversi contenitori contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="4656d-126">It even allows you to debug several containers at once.</span></span> <span data-ttu-id="4656d-127">Queste funzionalità rendono lo sviluppo più veloce.</span><span class="sxs-lookup"><span data-stu-id="4656d-127">These features boost your development speed.</span></span>

<span data-ttu-id="4656d-128">Il materiale sussidiario che segue spiega cosa accade "dietro le quinte" con Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-128">In the guidance that follows, we explain what's happening "under the covers" with Docker.</span></span>

![Immagine per Passaggio 1: scrivere il codice dell'app](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="4656d-130">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="4656d-130">Step 1.</span></span> <span data-ttu-id="4656d-131">Iniziare a scrivere il codice e ad abbozzare l'applicazione o il servizio</span><span class="sxs-lookup"><span data-stu-id="4656d-131">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="4656d-132">Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-132">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="4656d-133">La differenza è che, quando si sviluppa per Docker, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale.</span><span class="sxs-lookup"><span data-stu-id="4656d-133">The difference is that while developing for Docker, you are deploying and testing your application or services running within Docker containers in your local environment.</span></span> <span data-ttu-id="4656d-134">Il contenitore può essere di tipo Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="4656d-134">The container can be either a Linux container or a Windows container.</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="4656d-135">Configurare l'ambiente locale con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4656d-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="4656d-136">Per iniziare, accertarsi che sia installato [Docker Community Edition (CE)](https://www.docker.com/community-edition) per Windows, come spiegato nelle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4656d-136">To begin, make sure you have [Docker Community Edition (CE)](https://www.docker.com/community-edition) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="4656d-137">Introduzione a Docker CE per Windows</span><span class="sxs-lookup"><span data-stu-id="4656d-137">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="4656d-138">Inoltre, è necessario Visual Studio 2017 con il carico di lavoro **Sviluppo multipiattaforma .NET Core** installato, come illustra la figura 5-2.</span><span class="sxs-lookup"><span data-stu-id="4656d-138">In addition, you need Visual Studio 2017 with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![](./media/image3.png)

<span data-ttu-id="4656d-139">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="4656d-139">**Figure 5-2**.</span></span> <span data-ttu-id="4656d-140">Selezione del carico di lavoro **.NET Core e Docker** durante l'installazione di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4656d-140">Selecting the **.NET Core and Docker** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="4656d-141">È possibile iniziare a scrivere il codice dell'applicazione in .NET normale, di solito in .NET Core se si prevede di usare contenitori, anche prima di attivare Docker nell'applicazione e di eseguire la distribuzione e i test in Docker,</span><span class="sxs-lookup"><span data-stu-id="4656d-141">You can start coding your application in plain .NET (usually in .NET Core if you are planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="4656d-142">ma si consiglia di iniziare a lavorare in Docker appena possibile, perché quello sarà l'ambiente reale e gli eventuali problemi possono essere individuati velocemente.</span><span class="sxs-lookup"><span data-stu-id="4656d-142">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="4656d-143">Si consiglia di procedere in questo modo perché Visual Studio facilita così tanto il lavoro con Docker da diventare quasi trasparente, soprattutto quando lo si usa per eseguire il debug di applicazioni a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="4656d-143">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent — the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4656d-144">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4656d-144">Additional resources</span></span>

- <span data-ttu-id="4656d-145">**Introduzione a Docker CE per Windows**</span><span class="sxs-lookup"><span data-stu-id="4656d-145">**Get started with Docker CE for Windows**</span></span>

   [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- <span data-ttu-id="4656d-146">**Visual Studio 2017**</span><span class="sxs-lookup"><span data-stu-id="4656d-146">**Visual Studio 2017**</span></span>

   [*https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![Immagine per Passaggio 2: scrivere i Dockerfile](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="4656d-148">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="4656d-148">Step 2.</span></span> <span data-ttu-id="4656d-149">Creare un Dockerfile correlato a un'immagine di base .NET esistente</span><span class="sxs-lookup"><span data-stu-id="4656d-149">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="4656d-150">È necessario un Dockerfile per ogni immagine personalizzata che si vuole creare, nonché per ogni contenitore da distribuire, sia che si esegua la distribuzione automaticamente da Visual Studio o manualmente con la CLI di Docker (comandi docker run e docker-compose).</span><span class="sxs-lookup"><span data-stu-id="4656d-150">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="4656d-151">Se l'applicazione contiene un solo servizio personalizzato, è necessario un solo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="4656d-151">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="4656d-152">Se l'applicazione contiene più servizi, come in un'architettura a microservizi, è necessario un Dockerfile per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="4656d-152">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="4656d-153">Il Dockerfile viene inserito nella cartella radice dell'applicazione o del servizio.</span><span class="sxs-lookup"><span data-stu-id="4656d-153">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="4656d-154">Contiene i comandi che indicano a Docker come configurare ed eseguire l'applicazione o il servizio in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="4656d-154">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="4656d-155">È possibile creare manualmente un Dockerfile nel codice e aggiungerlo al progetto insieme alle dipendenze .NET.</span><span class="sxs-lookup"><span data-stu-id="4656d-155">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="4656d-156">Con Visual Studio Tools per Docker questa attività richiede solo pochi clic del mouse.</span><span class="sxs-lookup"><span data-stu-id="4656d-156">With Visual Studio Tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="4656d-157">Quando si crea un nuovo progetto in Visual Studio 2017, è disponibile un'opzione denominata **Abilita supporto Docker**, come illustrato nella figura 5-3.</span><span class="sxs-lookup"><span data-stu-id="4656d-157">When you create a new project in Visual Studio 2017, there's an option named **Enable Docker Support**, as shown in Figure 5-3.</span></span>

![Abilitazione del supporto Docker quando si crea un nuovo progetto in Visual Studio 2017](./media/image5.png)

<span data-ttu-id="4656d-159">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="4656d-159">**Figure 5-3**.</span></span> <span data-ttu-id="4656d-160">Abilitazione del supporto Docker quando si crea un nuovo progetto in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4656d-160">Enabling Docker Support when creating a new project in Visual Studio 2017</span></span>

<span data-ttu-id="4656d-161">È anche possibile abilitare il supporto Docker in un progetto di app Web .NET Core esistente facendo clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionando **Aggiungi** > **Supporto Docker**, come illustrato nella figura 5-4.</span><span class="sxs-lookup"><span data-stu-id="4656d-161">You can also enable Docker support on an existing .NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Opzione di menu Supporto Docker in Visual Studio](./media/add-docker-support.png)

<span data-ttu-id="4656d-163">**Figura 5-4**.</span><span class="sxs-lookup"><span data-stu-id="4656d-163">**Figure 5-4**.</span></span> <span data-ttu-id="4656d-164">Abilitazione del supporto Docker in un progetto Visual Studio 2017 esistente</span><span class="sxs-lookup"><span data-stu-id="4656d-164">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="4656d-165">Questa azione aggiunge un *Dockerfile* al progetto con la configurazione richiesta ed è disponibile solo nei progetti di app Web .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4656d-165">This action adds a *Dockerfile* to the project with the required configuration, and is only available on .NET Core web app projects.</span></span>

<span data-ttu-id="4656d-166">Per aggiungere un file *docker-compose.yml* per l'intera soluzione, fare clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionare **Aggiungi** > **Container Orchestrator Support** (Supporto per agente di orchestrazione dei contenitori), come illustrato nella figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="4656d-166">To add a *docker-compose.yml* file for the whole solution, right-click on the project in **Solution Explorer** and select **Add** > **Container Orchestrator Support**, as shown in Figure 5-5.</span></span>

![Opzione di menu per aggiunta del supporto per agente di orchestrazione dei contenitori in Visual Studio](./media/add-container-orchestrator-support.png)

<span data-ttu-id="4656d-168">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="4656d-168">**Figure 5-5**.</span></span> <span data-ttu-id="4656d-169">Aggiunta del supporto per agente di orchestrazione dei contenitori a un progetto esistente in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="4656d-169">Adding container orchestrator support to an existing project in Visual Studio 2017.</span></span>

<span data-ttu-id="4656d-170">Nelle sezioni seguenti sono descritte le informazioni da inserire in ciascuno di questi file.</span><span class="sxs-lookup"><span data-stu-id="4656d-170">In the following sections, we describe the information that goes into each of those files.</span></span> <span data-ttu-id="4656d-171">Visual Studio fa tutto questo automaticamente, ma è utile sapere cosa deve contenere un Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="4656d-171">Visual Studio can do this work for you, but it is useful to understand what goes into a Dockerfile.</span></span>

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a><span data-ttu-id="4656d-172">Opzione A: creazione di un progetto con un'immagine Docker .NET ufficiale esistente</span><span class="sxs-lookup"><span data-stu-id="4656d-172">Option A: Creating a project using an existing official .NET Docker image</span></span>

<span data-ttu-id="4656d-173">In genere si crea un'immagine personalizzata per il contenitore sopra un'immagine di base che è possibile ottenere da un repository ufficiale nel registro [Hub Docker](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="4656d-173">You usually build a custom image for your container on top of a base image you can get from an official repository at the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="4656d-174">Questo è esattamente ciò che accade dietro le quinte quando si attiva il supporto Docker in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4656d-174">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="4656d-175">Il Dockerfile usa un'immagine aspnetcore esistente.</span><span class="sxs-lookup"><span data-stu-id="4656d-175">The Dockerfile uses an existing aspnetcore image.</span></span>

<span data-ttu-id="4656d-176">In precedenza si è visto le immagini e repository Docker da usare in base al framework e al sistema operativo scelto.</span><span class="sxs-lookup"><span data-stu-id="4656d-176">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="4656d-177">Ad esempio, se si desidera usare ASP.NET Core (Linux o Windows), l'immagine da utilizzare è microsoft/aspnetcore:2.0.</span><span class="sxs-lookup"><span data-stu-id="4656d-177">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is microsoft/aspnetcore:2.0.</span></span> <span data-ttu-id="4656d-178">Pertanto è sufficiente specificare l'immagine Docker di base che sarà usata per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="4656d-178">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="4656d-179">Lo si fa aggiungendo FROM microsoft/aspnetcore:2.0 al Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="4656d-179">You do that by adding FROM microsoft/aspnetcore:2.0 to your Dockerfile.</span></span> <span data-ttu-id="4656d-180">Visual Studio esegue l'operazione automaticamente, ma se si aggiorna la versione, viene aggiornato anche questo valore.</span><span class="sxs-lookup"><span data-stu-id="4656d-180">This is automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="4656d-181">L'uso di un repository ufficiale di immagini .NET di Docker Hub con un numero di versione garantisce che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.</span><span class="sxs-lookup"><span data-stu-id="4656d-181">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="4656d-182">L'esempio seguente illustra un esempio di Dockerfile per un contenitore ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4656d-182">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0

ARG source

WORKDIR /app

EXPOSE 80

COPY ${source:-obj/Docker/publish} .

ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="4656d-183">In questo caso il contenitore è basato sulla versione 2.0 dell'immagine ASP.NET Core Docker ufficiale (multi-arch per Linux e Windows).</span><span class="sxs-lookup"><span data-stu-id="4656d-183">In this case, the container is based on version 2.0 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="4656d-184">Si tratta dell'impostazione `FROM microsoft/aspnetcore:2.0`.</span><span class="sxs-lookup"><span data-stu-id="4656d-184">This is the setting `FROM microsoft/aspnetcore:2.0`.</span></span> <span data-ttu-id="4656d-185">Per altre informazioni su questa immagine di base, vedere la pagina [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) (Immagine ASP.NET Core Docker) e la pagina [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) (Immagine .NET Core Docker). Nel Dockerfile è necessario anche indicare al Docker di rimanere in ascolto sulla porta TCP che sarà usata in fase di esecuzione, in questo caso la porta 80 configurata con l'impostazione EXPOSE.</span><span class="sxs-lookup"><span data-stu-id="4656d-185">(For more information about this base image, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="4656d-186">Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso.</span><span class="sxs-lookup"><span data-stu-id="4656d-186">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you are using.</span></span> <span data-ttu-id="4656d-187">Ad esempio, la riga ENTRYPOINT con \["dotnet", "MySingleContainerWebApp.dll"\] indica a Docker di eseguire un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4656d-187">For instance, the ENTRYPOINT line with \["dotnet", "MySingleContainerWebApp.dll"\] tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="4656d-188">Se si usa l'SDK e la CLI di .NET Core, ovvero la CLI dotnet per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa.</span><span class="sxs-lookup"><span data-stu-id="4656d-188">If you are using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="4656d-189">In sostanza la riga ENTRYPOINT e altre impostazioni saranno diverse a seconda del linguaggio e della piattaforma scelti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4656d-189">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4656d-190">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4656d-190">Additional resources</span></span>

- <span data-ttu-id="4656d-191">**Compilazione di immagini Docker per applicazioni .NET Core**</span><span class="sxs-lookup"><span data-stu-id="4656d-191">**Building Docker Images for .NET Core Applications**</span></span>

   [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="4656d-192">**Creare un'immagine**.</span><span class="sxs-lookup"><span data-stu-id="4656d-192">**Build your own image**.</span></span> <span data-ttu-id="4656d-193">Nella documentazione ufficiale di Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-193">In the official Docker documentation.</span></span>

   [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="4656d-194">Uso di repository di immagini multi-arch</span><span class="sxs-lookup"><span data-stu-id="4656d-194">Using multi-arch image repositories</span></span>

<span data-ttu-id="4656d-195">Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows.</span><span class="sxs-lookup"><span data-stu-id="4656d-195">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="4656d-196">Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="4656d-196">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="4656d-197">Ad esempio, il repository [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) disponibile nel registro Docker Hub fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di repository.</span><span class="sxs-lookup"><span data-stu-id="4656d-197">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="4656d-198">Se si specifica un tag, ci si rivolge a una piattaforma esplicita come nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="4656d-198">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- <span data-ttu-id="4656d-199">**microsoft/aspnetcore:2.0.0-jessie**</span><span class="sxs-lookup"><span data-stu-id="4656d-199">**microsoft/aspnetcore:2.0.0-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

- <span data-ttu-id="4656d-200">**microsoft/aspnetcore:2.0.0-nanoserver**</span><span class="sxs-lookup"><span data-stu-id="4656d-200">**microsoft/aspnetcore:2.0.0-nanoserver**</span></span>

        .NET Core 2.0 runtime-only on Windows Nano Server

<span data-ttu-id="4656d-201">Ma, e questa è una novità da metà 2017, se si specifica lo stesso nome di immagine, anche con lo stesso tag, le nuove immagini multi-arch, come l'immagine aspnetcore che supporta multi-arch, useranno la versione Linux o Windows in base al sistema operativo host Docker che si sta distribuendo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4656d-201">But, and this is new since mid-2017, if you specify the same image name, even with the same tag, the new multi-arch images (like the aspnetcore image, which supports multi-arch) will use the Linux or Windows version depending on the Docker host OS you are deploying, as shown in the following example:</span></span>

- <span data-ttu-id="4656d-202">**microsoft/aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="4656d-202">**microsoft/aspnetcore:2.0**</span></span>

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

<span data-ttu-id="4656d-203">In questo modo, se si esegue il pull di un'immagine da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome di immagine da un host Linux si ottiene la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="4656d-203">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="option-b-creating-your-base-image-from-scratch"></a><span data-ttu-id="4656d-204">Opzione B: creazione dell'immagine di base da zero</span><span class="sxs-lookup"><span data-stu-id="4656d-204">Option B: Creating your base image from scratch</span></span>

<span data-ttu-id="4656d-205">È possibile creare un'immagine Docker di base da zero.</span><span class="sxs-lookup"><span data-stu-id="4656d-205">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="4656d-206">Questo scenario non è consigliato se non si conosce bene Docker, ma se si vuole creare la propria immagine di base è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="4656d-206">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4656d-207">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4656d-207">Additional resources</span></span>

- <span data-ttu-id="4656d-208">**Immagini multi-arch .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="4656d-208">**Multi-arch .NET Core images**.</span></span>

   https://github.com/dotnet/announcements/issues/14

- <span data-ttu-id="4656d-209">**Creare un'immagine di base**.</span><span class="sxs-lookup"><span data-stu-id="4656d-209">**Create a base image**.</span></span> <span data-ttu-id="4656d-210">Documentazione ufficiale di Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-210">Official Docker documentation.</span></span>

   [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![Immagine per Passaggio 3: creare le immagini](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="4656d-212">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="4656d-212">Step 3.</span></span> <span data-ttu-id="4656d-213">Creare le immagini Docker personalizzate e incorporare l'applicazione o il servizio in esse</span><span class="sxs-lookup"><span data-stu-id="4656d-213">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="4656d-214">Per ogni servizio dell'applicazione è necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="4656d-214">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="4656d-215">Se l'applicazione è costituita da un singolo servizio o applicazione Web, è sufficiente una singola immagine.</span><span class="sxs-lookup"><span data-stu-id="4656d-215">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="4656d-216">Le immagini Docker vengono create automaticamente in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4656d-216">The Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="4656d-217">I passaggi seguenti sono necessari solo per il flusso di lavoro editor/CLI e sono descritti per chiarire meglio ciò che succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4656d-217">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="4656d-218">Lo sviluppatore deve eseguire lo sviluppo e i test localmente finché non esegue il push di una funzionalità o di una modifica completa nel sistema di controllo del codice sorgente, ad esempio in GitHub.</span><span class="sxs-lookup"><span data-stu-id="4656d-218">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="4656d-219">Ciò significa che è necessario creare le immagini Docker e distribuire i contenitori in un host Docker locale, ovvero una VM Windows o Linux, nonché eseguire, testare ed eseguire il debug in tali contenitori locale.</span><span class="sxs-lookup"><span data-stu-id="4656d-219">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="4656d-220">Per creare un'immagine personalizzata nell'ambiente locale usando l'infrastruttura CLI di Docker e il Dockerfile, è possibile usare il comando docker build, come illustrato nella figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="4656d-220">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Creazione di un'immagine Docker personalizzata](./media/image8.png)

<span data-ttu-id="4656d-222">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="4656d-222">**Figure 5-5**.</span></span> <span data-ttu-id="4656d-223">Creazione di un'immagine Docker personalizzata</span><span class="sxs-lookup"><span data-stu-id="4656d-223">Creating a custom Docker image</span></span>

<span data-ttu-id="4656d-224">Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è possibile generare innanzitutto una cartella distribuibile con le raccolte .NET e i file binari necessari eseguendo dotnet publish e quindi usando il comando docker build.</span><span class="sxs-lookup"><span data-stu-id="4656d-224">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running dotnet publish, and then use the docker build command.</span></span>

<span data-ttu-id="4656d-225">Verrà così creata un'immagine Docker con il nome **cesardl/netcore-webapi-microservice-docker:first**.</span><span class="sxs-lookup"><span data-stu-id="4656d-225">This will create a Docker image with the name **cesardl/netcore-webapi-microservice-docker:first**.</span></span> <span data-ttu-id="4656d-226">In questo caso :first è un tag che rappresenta una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="4656d-226">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="4656d-227">È possibile ripetere questo passaggio per ogni immagine personalizzata da creare per l'applicazione Docker composta.</span><span class="sxs-lookup"><span data-stu-id="4656d-227">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="4656d-228">Quando un'applicazione è costituita da più contenitori, è un'applicazione a più contenitori, è anche possibile usare il comando docker-compose up --build per compilare tutte le immagini correlate con un singolo comando usando i metadati esposti nei file docker-compose.yml correlati.</span><span class="sxs-lookup"><span data-stu-id="4656d-228">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the docker-compose up --build command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="4656d-229">È possibile trovare le immagini esistenti nel repository locale tramite il comando docker images, come illustrato nella figura 5-6.</span><span class="sxs-lookup"><span data-stu-id="4656d-229">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Visualizzazione di immagini esistenti con il comando docker images](./media/image9.png)

<span data-ttu-id="4656d-231">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="4656d-231">**Figure 5-6.**</span></span> <span data-ttu-id="4656d-232">Visualizzazione di immagini esistente con il comando docker images</span><span class="sxs-lookup"><span data-stu-id="4656d-232">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="4656d-233">Creazione di immagini Docker con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4656d-233">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="4656d-234">Quando si usa Visual Studio per creare un progetto con il supporto Docker, non si crea un'immagine in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="4656d-234">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="4656d-235">L'immagine viene invece creata automaticamente quando si preme **F5** e si esegue l'applicazione o il servizio Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-235">Instead, the image is created for you when you press **F5** to run the dockerized application or service.</span></span> <span data-ttu-id="4656d-236">Questo passaggio è automatico e invisibile in Visual Studio, ma è importante sapere cosa succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4656d-236">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![Immagine per Passaggio 4: definire i servizi](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="4656d-238">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="4656d-238">Step 4.</span></span> <span data-ttu-id="4656d-239">Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori</span><span class="sxs-lookup"><span data-stu-id="4656d-239">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="4656d-240">Il file [docker compose.yml](https://docs.docker.com/compose/compose-file/) consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4656d-240">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span>

<span data-ttu-id="4656d-241">Per usare un file docker-compose.yml, è necessario creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4656d-241">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

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

<span data-ttu-id="4656d-242">Questo file docker-compose.yml è una versione semplificata e unita.</span><span class="sxs-lookup"><span data-stu-id="4656d-242">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="4656d-243">Contiene dati di configurazione statici per ogni contenitore, ad esempio il nome dell'immagine personalizzata, sempre applicabili, nonché informazioni di configurazione che potrebbero dipendere dall'ambiente di distribuzione, ad esempio la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="4656d-243">It contains static configuration data for each container (like the name of the custom image), which always applies, plus configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="4656d-244">In seguito si vedrà come suddividere la configurazione di docker-compose.yml in più file docker-compose e sostituire valori a seconda del tipo di ambiente e di esecuzione, ovvero debug o release.</span><span class="sxs-lookup"><span data-stu-id="4656d-244">In later sections, you will learn how you can split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="4656d-245">L'esempio del file docker-compose.yml definisce quattro servizi: il servizio webmvc, che è un'applicazione Web; due microservizi, ovvero catalog.api e ordering.api; un contenitore origine dati, sql.data, basato su SQL Server per Linux eseguito come contenitore.</span><span class="sxs-lookup"><span data-stu-id="4656d-245">The docker-compose.yml file example defines four services: the webmvc service (a web application), two microservices (catalog.api and ordering.api), and one data source container, sql.data, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="4656d-246">Ogni servizio è distribuito come contenitore, quindi è necessaria un'immagine Docker per ciascuno.</span><span class="sxs-lookup"><span data-stu-id="4656d-246">Each service is deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="4656d-247">Il file docker-compose.yml specifica non solo quali contenitori vengono usati, ma come sono configurati singolarmente.</span><span class="sxs-lookup"><span data-stu-id="4656d-247">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="4656d-248">Ad esempio, la definizione del contenitore webmvc nel file .yml:</span><span class="sxs-lookup"><span data-stu-id="4656d-248">For instance, the webmvc container definition in the .yml file:</span></span>

- <span data-ttu-id="4656d-249">Usa un'immagine eshop/web:latest precompilata.</span><span class="sxs-lookup"><span data-stu-id="4656d-249">Uses a pre-built eshop/web:latest image.</span></span> <span data-ttu-id="4656d-250">Tuttavia, è anche possibile configurare l'immagine in modo che sia compilata come parte dell'esecuzione di docker-compose con una configurazione aggiuntiva basata su una sezione build: nel file docker-compose.</span><span class="sxs-lookup"><span data-stu-id="4656d-250">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="4656d-251">Inizializza due variabili di ambiente, ovvero CatalogUrl e OrderingUrl.</span><span class="sxs-lookup"><span data-stu-id="4656d-251">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="4656d-252">Inoltra la porta 80 esposta sul contenitore alla porta esterna 80 sul computer host.</span><span class="sxs-lookup"><span data-stu-id="4656d-252">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="4656d-253">Collega l'app Web al catalogo e al servizio di ordinazione con l'impostazione depends\_on.</span><span class="sxs-lookup"><span data-stu-id="4656d-253">Links the web app to the catalog and ordering service with the depends\_on setting.</span></span> <span data-ttu-id="4656d-254">In questo modo il servizio attende fino a quando vengono avviati i servizi.</span><span class="sxs-lookup"><span data-stu-id="4656d-254">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="4656d-255">Il file docker-compose.yml sarà esaminato di nuovo in una sezione successiva in cui sarà descritto come implementare microservizi e app a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="4656d-255">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="4656d-256">Utilizzo di docker-compose.yml in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4656d-256">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="4656d-257">Quando si aggiunge il supporto per l'agente di orchestrazione dei contenitori a un progetto di app Web, come illustrato nella figura 5-7, Visual Studio aggiunge una sezione del servizio (progetto) alla soluzione che contiene un file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="4656d-257">When you add container orchestrator support to a web app project, as shown in Figure 5-7, Visual Studio adds a service section (project) to the solution that contains a docker-compose.yml file.</span></span> <span data-ttu-id="4656d-258">Questo è un modo semplice per iniziare a comporre una soluzione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="4656d-258">This is an easy way to start composing a multiple-container solution.</span></span>

![Voce di menu per aggiunta del supporto per agente di orchestrazione dei contenitori in Visual Studio](./media/add-container-orchestrator-support.png)

<span data-ttu-id="4656d-260">**Figura 5-7**.</span><span class="sxs-lookup"><span data-stu-id="4656d-260">**Figure 5-7**.</span></span> <span data-ttu-id="4656d-261">Aggiunta del supporto Docker in Visual Studio 2017 facendo clic con il pulsante destro del mouse su un progetto ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4656d-261">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="4656d-262">L'aggiunta del supporto per l'agente di orchestrazione dei contenitori consente di aggiungere il Dockerfile al progetto, se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="4656d-262">Adding container orchestrator support adds the Dockerfile to your project (if it doesn't already exist).</span></span> <span data-ttu-id="4656d-263">Aggiunge anche informazioni sulla configurazione a un file docker-compose.yml globale a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4656d-263">It also adds configuration information to a global docker-compose.yml file at the solution level.</span></span> <span data-ttu-id="4656d-264">Si noterà un nuovo nodo di progetto, il file di progetto *docker-compose.dcproj*, in **Esplora soluzioni** che contiene il file docker-compose.yml, come illustrato nella figura 5-8.</span><span class="sxs-lookup"><span data-stu-id="4656d-264">You'll see a new project node (the *docker-compose.dcproj* project file) in **Solution Explorer** that contains the docker-compose.yml file, as shown in Figure 5-8.</span></span>

![Nodo docker-compose in Esplora soluzioni](./media/docker-compose-files.png)

<span data-ttu-id="4656d-266">**Figura 5-8**.</span><span class="sxs-lookup"><span data-stu-id="4656d-266">**Figure 5-8**.</span></span> <span data-ttu-id="4656d-267">Il nodo dell'albero **docker-compose** aggiunto in Esplora soluzioni di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4656d-267">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="4656d-268">È quindi possibile aprire il file docker-compose.yml e aggiornarlo con funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4656d-268">You can then open the docker-compose.yml file and update it with additional features.</span></span>

<span data-ttu-id="4656d-269">È possibile distribuire un'applicazione a più contenitori con un singolo file docker-compose.yml usando il comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="4656d-269">You can deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span>

![Immagine per Passaggio 5: eseguire l'app](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="4656d-271">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="4656d-271">Step 5.</span></span> <span data-ttu-id="4656d-272">Compilare ed eseguire l'applicazione Docker</span><span class="sxs-lookup"><span data-stu-id="4656d-272">Build and run your Docker application</span></span>

<span data-ttu-id="4656d-273">Se l'applicazione ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, ovvero una VM o un server fisico.</span><span class="sxs-lookup"><span data-stu-id="4656d-273">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="4656d-274">Se invece l'applicazione contiene più servizi, è possibile distribuirla come applicazione composta, usando un unico comando della CLI, ossia docker-compose up, o con Visual Studio, che userà lo stesso comando dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="4656d-274">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="4656d-275">Le diverse opzioni sono esaminate di seguito.</span><span class="sxs-lookup"><span data-stu-id="4656d-275">Let’s look at the different options.</span></span>

### <a name="option-a-run-a-single-container-app"></a><span data-ttu-id="4656d-276">Opzione A: eseguire un'applicazione a singolo contenitore</span><span class="sxs-lookup"><span data-stu-id="4656d-276">Option A: Run a single-container app</span></span>

#### <a name="docker-cli"></a><span data-ttu-id="4656d-277">CLI Docker</span><span class="sxs-lookup"><span data-stu-id="4656d-277">Docker CLI</span></span>

<span data-ttu-id="4656d-278">È possibile eseguire un contenitore Docker usando il comando docker run, come illustrato nella figura 5-9:</span><span class="sxs-lookup"><span data-stu-id="4656d-278">You can run a Docker container using the docker run command, as in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![Esecuzione di un contenitore Docker usando il comando docker run](./media/image13.png)

<span data-ttu-id="4656d-280">**Figura 5-9**.</span><span class="sxs-lookup"><span data-stu-id="4656d-280">**Figure 5-9**.</span></span> <span data-ttu-id="4656d-281">Esecuzione di un contenitore Docker usando il comando docker run</span><span class="sxs-lookup"><span data-stu-id="4656d-281">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="4656d-282">In questo caso il comando associa la porta interna 5000 del contenitore alla porta 80 del computer host.</span><span class="sxs-lookup"><span data-stu-id="4656d-282">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="4656d-283">Ciò significa che l'host è in ascolto sulla porta 80 e inoltra alla porta 5000 nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="4656d-283">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

#### <a name="visual-studio"></a><span data-ttu-id="4656d-284">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4656d-284">Visual Studio</span></span>

<span data-ttu-id="4656d-285">Se non è stato aggiunto il supporto per l'agente di orchestrazione dei contenitori, è anche possibile eseguire un'applicazione a singolo contenitore in Visual Studio premendo **F5**.</span><span class="sxs-lookup"><span data-stu-id="4656d-285">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **F5**.</span></span> <span data-ttu-id="4656d-286">Il contenitore viene eseguito in locale usando docker run.</span><span class="sxs-lookup"><span data-stu-id="4656d-286">The container runs locally using docker run.</span></span>

### <a name="option-b-run-a-multi-container-app"></a><span data-ttu-id="4656d-287">Opzione B: eseguire un'applicazione a più contenitori</span><span class="sxs-lookup"><span data-stu-id="4656d-287">Option B: Run a multi-container app</span></span>

<span data-ttu-id="4656d-288">Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà composta da più servizi, perciò sarà necessario eseguire un'applicazione a più contenitori, come illustrato nella figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="4656d-288">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![Immagine che illustra una macchina virtuale con contenitori Docker distribuiti](./media/image14.png)

<span data-ttu-id="4656d-290">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="4656d-290">**Figure 5-10**.</span></span> <span data-ttu-id="4656d-291">VM con contenitori Docker distribuiti</span><span class="sxs-lookup"><span data-stu-id="4656d-291">VM with Docker containers deployed</span></span>

#### <a name="docker-cli"></a><span data-ttu-id="4656d-292">CLI Docker</span><span class="sxs-lookup"><span data-stu-id="4656d-292">Docker CLI</span></span>

<span data-ttu-id="4656d-293">Per eseguire un'applicazione a più contenitori con la CLI di Docker, è possibile eseguire il comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="4656d-293">To run a multi-container application with the Docker CLI, you can run the docker-compose up command.</span></span> <span data-ttu-id="4656d-294">Questo comando usa il file docker-compose.yml disponibile a livello di soluzione per distribuire un'applicazione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="4656d-294">This command uses the docker-compose.yml file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="4656d-295">La figura 5-11 mostra i risultati che si ottengono quando si esegue il comando dalla directory principale del progetto, che contiene il file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="4656d-295">Figure 5-11 shows the results when running the command from your main project directory, which contains the docker-compose.yml file.</span></span>

![Esempio di risultati ottenuti eseguendo il comando docker-compose up](./media/image15.png)

<span data-ttu-id="4656d-297">**Figura 5-11**.</span><span class="sxs-lookup"><span data-stu-id="4656d-297">**Figure 5-11**.</span></span> <span data-ttu-id="4656d-298">Esempio di risultati ottenuti eseguendo il comando docker-compose up</span><span class="sxs-lookup"><span data-stu-id="4656d-298">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="4656d-299">Dopo l'esecuzione del comando docker-compose up, l'applicazione e i contenitori correlati vengono distribuiti nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-299">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host.</span></span>

#### <a name="visual-studio"></a><span data-ttu-id="4656d-300">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4656d-300">Visual Studio</span></span>

<span data-ttu-id="4656d-301">Eseguire un'applicazione a più contenitori con Visual Studio 2017 è semplice.</span><span class="sxs-lookup"><span data-stu-id="4656d-301">Running a multi-container application using Visual Studio 2017 is simple.</span></span> <span data-ttu-id="4656d-302">Non solo è possibile eseguire l'applicazione a più contenitori, ma è possibile eseguire il debug di tutti i relativi contenitori direttamente da Visual Studio impostando punti di interruzione normali.</span><span class="sxs-lookup"><span data-stu-id="4656d-302">Not only can you run the multi-container application, but you're able to debug all its containers directly from Visual Studio by setting regular breakpoints.</span></span>

<span data-ttu-id="4656d-303">Come accennato in precedenza, ogni volta che si aggiunge il supporto per l'agente di orchestrazione dei contenitori a un progetto all'interno di una soluzione, il progetto viene configurato nel file docker-compose.yml globale, a livello di soluzione, che consente di eseguire l'intera soluzione o di eseguirne il debug in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="4656d-303">As mentioned before, each time you add container orchestrator support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="4656d-304">Visual Studio avvia un solo contenitore per ogni progetto che ha il supporto Docker abilitato ed esegue automaticamente tutti i passaggi interni (dotnet publish, docker build e così via).</span><span class="sxs-lookup"><span data-stu-id="4656d-304">Visual Studio will start one container for each project that has Docker solution support enabled and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="4656d-305">La cosa importante è che, come illustrato nella figura 5-12, in Visual Studio 2017 è presente un ulteriore comando **Docker** per il tasto funzione **F5**.</span><span class="sxs-lookup"><span data-stu-id="4656d-305">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there's an additional **Docker** command for the **F5** key action.</span></span> <span data-ttu-id="4656d-306">Questa opzione consente di eseguire un'applicazione a più contenitori o di eseguirne il debug eseguendo tutti i contenitori definiti nei file docker-compose.yml a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="4656d-306">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="4656d-307">Grazie alla capacità di eseguire il debug delle soluzioni a più contenitori, è possibile impostare più punti di interruzione, ciascuno in un progetto (contenitore) diverso, e durante il debug da Visual Studio l'esecuzione viene arrestata in corrispondenza dei punti di interruzione definiti in progetti diversi ed eseguiti in contenitori diversi.</span><span class="sxs-lookup"><span data-stu-id="4656d-307">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Esecuzione di applicazioni a più contenitori in Visual Studio 2017](./media/image16.png)

<span data-ttu-id="4656d-309">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="4656d-309">**Figure 5-12**.</span></span> <span data-ttu-id="4656d-310">Esecuzione di applicazioni a più contenitori in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4656d-310">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4656d-311">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4656d-311">Additional resources</span></span>

-  <span data-ttu-id="4656d-312">**Distribuire un contenitore ASP.NET a un host Docker remoto**</span><span class="sxs-lookup"><span data-stu-id="4656d-312">**Deploy an ASP.NET container to a remote Docker host**</span></span>

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="4656d-313">Una nota sul test e la distribuzione con agenti di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="4656d-313">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="4656d-314">I comandi docker-compose up e docker run, o l'esecuzione e il debug dei contenitori in Visual Studio, sono adeguati per eseguire test sui contenitori nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4656d-314">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="4656d-315">Questo approccio invece non si deve usare se la destinazione è costituita da cluster e agenti di orchestrazione Docker come Swarm, Mesosphere DC/OS o Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4656d-315">But you should not use this approach if you are targeting Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes.</span></span> <span data-ttu-id="4656d-316">Se si usa un cluster come la [modalità Docker Swarm](https://docs.docker.com/engine/swarm/), disponibile in Docker CE per Windows e Mac dalla versione 1.12, è necessario eseguire la distribuzione e i test con altri comandi, ad esempio [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) per servizi singoli.</span><span class="sxs-lookup"><span data-stu-id="4656d-316">If you are using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker CE for Windows and Mac since version 1.12), you need to deploy and test with additional commands like [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) for single services.</span></span> <span data-ttu-id="4656d-317">Se si distribuisce un'applicazione composta da diversi contenitori, usare [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) e [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) per distribuire l'applicazione composta come *stack*.</span><span class="sxs-lookup"><span data-stu-id="4656d-317">If you are deploying an application composed of several containers, you use [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) and [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) to deploy the composed application as a *stack*.</span></span> <span data-ttu-id="4656d-318">Per altre informazioni, vedere il post di blog [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) (Presentazione di bundle applicativi distribuiti sperimentali) nella documentazione di Docker</span><span class="sxs-lookup"><span data-stu-id="4656d-318">For more information, see the blog post [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) in the Docker documentation.</span></span> <span data-ttu-id="4656d-319">nel sito di Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-319">on the Docker site.</span></span>

<span data-ttu-id="4656d-320">Per [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) si usano comandi di distribuzione e script diversi.</span><span class="sxs-lookup"><span data-stu-id="4656d-320">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/) you would use different deployment commands and scripts as well.</span></span>

![Immagine per Passaggio 6](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="4656d-322">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="4656d-322">Step 6.</span></span> <span data-ttu-id="4656d-323">Testare l'applicazione Docker usando l'host Docker locale</span><span class="sxs-lookup"><span data-stu-id="4656d-323">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="4656d-324">Questo passaggio varia in base a ciò che l'applicazione sta facendo.</span><span class="sxs-lookup"><span data-stu-id="4656d-324">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="4656d-325">In un'applicazione Web .NET Core semplice che viene distribuita come contenitore o servizio singolo è possibile accedere al servizio aprendo un browser nell'host Docker e passando a quel sito, come illustrato nella figura 5-13.</span><span class="sxs-lookup"><span data-stu-id="4656d-325">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="4656d-326">Se la configurazione nel Dockerfile abbina il contenitore a una porta dell'host diversa dalla 80, includere la porta host nell'URL.</span><span class="sxs-lookup"><span data-stu-id="4656d-326">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Esempio di test dell'applicazione Docker in locale mediante localhost](./media/image18.png)

<span data-ttu-id="4656d-328">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="4656d-328">**Figure 5-13**.</span></span> <span data-ttu-id="4656d-329">Esempio di test dell'applicazione Docker in locale mediante localhost</span><span class="sxs-lookup"><span data-stu-id="4656d-329">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="4656d-330">Se localhost non punta all'IP dell'host Docker, come succede per impostazione predefinita quando si usa Docker CE, per passare al servizio usare l'indirizzo IP della scheda di rete del computer.</span><span class="sxs-lookup"><span data-stu-id="4656d-330">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine’s network card.</span></span>

<span data-ttu-id="4656d-331">Questo URL nel browser usa la porta 80 per lo specifico contenitore di esempio di cui si tratta.</span><span class="sxs-lookup"><span data-stu-id="4656d-331">This URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="4656d-332">Tuttavia internamente le richieste vengono reindirizzate alla porta 5000 perché è stato distribuito in questo modo con il comando docker run, come illustrato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="4656d-332">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="4656d-333">È anche possibile testare l'applicazione usando curl dal terminale, come illustrato nella figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="4656d-333">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="4656d-334">In un'installazione di Docker in Windows, il valore IP dell'host Docker predefinito è sempre 10.0.75.1 in aggiunta all'indirizzo IP effettivo del computer.</span><span class="sxs-lookup"><span data-stu-id="4656d-334">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine’s actual IP address.</span></span>

![Esempio di test dell'applicazione Docker in locale mediante curl](./media/image19.png)

<span data-ttu-id="4656d-336">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="4656d-336">**Figure 5-14**.</span></span> <span data-ttu-id="4656d-337">Esempio di test dell'applicazione Docker in locale mediante curl</span><span class="sxs-lookup"><span data-stu-id="4656d-337">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="4656d-338">Test e debug di contenitori con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="4656d-338">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="4656d-339">Quando si eseguono contenitori e se ne esegue il debug con Visual Studio 2017, è possibile eseguire il debug dell'applicazione .NET nello stesso modo che si userebbe per l'esecuzione senza contenitori.</span><span class="sxs-lookup"><span data-stu-id="4656d-339">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="4656d-340">Test e debug senza Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4656d-340">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="4656d-341">Se si sviluppa usando l'approccio editor/CLI, eseguire il debug dei contenitori è più difficile ed è preferibile farlo tramite la generazione di tracce.</span><span class="sxs-lookup"><span data-stu-id="4656d-341">If you are developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4656d-342">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4656d-342">Additional resources</span></span>

- <span data-ttu-id="4656d-343">**Debug delle applicazioni in un contenitore Docker locale**</span><span class="sxs-lookup"><span data-stu-id="4656d-343">**Debugging apps in a local Docker container**</span></span>

   [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- <span data-ttu-id="4656d-344">**Steve Lasker. Compilare, eseguire il debug e distribuire app ASP.NET Core con Docker.**</span><span class="sxs-lookup"><span data-stu-id="4656d-344">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="4656d-345">Video.</span><span class="sxs-lookup"><span data-stu-id="4656d-345">Video.</span></span>

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="4656d-346">Flusso di lavoro semplificato per lo sviluppo di contenitori con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4656d-346">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="4656d-347">Il flusso di lavoro quando si usa Visual Studio è molto più semplice rispetto all'uso dell'approccio editor/CLI.</span><span class="sxs-lookup"><span data-stu-id="4656d-347">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="4656d-348">La maggior parte dei passaggi richiesti da Docker correlati ai file Dockerfile e docker-compose.yml sono nascosti o semplificati da Visual Studio, come illustrato nella figura 5-15.</span><span class="sxs-lookup"><span data-stu-id="4656d-348">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![Flusso di lavoro semplificato per lo sviluppo con Visual Studio](./media/image20.png)

<span data-ttu-id="4656d-350">**Figura 5-15**.</span><span class="sxs-lookup"><span data-stu-id="4656d-350">**Figure 5-15**.</span></span> <span data-ttu-id="4656d-351">Flusso di lavoro semplificato per lo sviluppo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4656d-351">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="4656d-352">Inoltre è sufficiente eseguire una sola volta il passaggio 2, ovvero l'aggiunta del supporto Docker ai progetti.</span><span class="sxs-lookup"><span data-stu-id="4656d-352">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="4656d-353">Pertanto il flusso di lavoro è simile alle attività di sviluppo normale quando si usa .NET per qualsiasi altro tipo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4656d-353">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="4656d-354">È necessario sapere cosa succede dietro le quinte, ad esempio il processo di creazione delle immagini, quali immagini di base vengono usate, la distribuzione dei contenitori e così via; in alcuni casi è anche necessario modificare il file Dockerfile o docker-compose.ym per personalizzare i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="4656d-354">You need to know what is going on under the covers (the image build process, what base images you are using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="4656d-355">Se si usa Visual Studio la maggior parte del lavoro viene notevolmente semplificata e la produttività è maggiore.</span><span class="sxs-lookup"><span data-stu-id="4656d-355">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4656d-356">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4656d-356">Additional resources</span></span>

- <span data-ttu-id="4656d-357">**Steve Lasker. .NET Docker Development with Visual Studio 2017** (Sviluppo di Docker .NET con Visual Studio 2017)</span><span class="sxs-lookup"><span data-stu-id="4656d-357">**Steve Lasker. .NET Docker Development with Visual Studio 2017**</span></span>

   [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

- <span data-ttu-id="4656d-358">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio** (Inserire un'app di .NET Core in un contenitore con i nuovi strumenti di Docker per Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="4656d-358">**Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio**</span></span>

   [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="4656d-359">Uso dei comandi di PowerShell in un Dockerfile per configurare contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="4656d-359">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="4656d-360">I [contenitori Windows](/virtualization/windowscontainers/about/) consentono di convertire applicazioni Windows esistenti in immagini Docker e distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker.</span><span class="sxs-lookup"><span data-stu-id="4656d-360">[Windows Containers](/virtualization/windowscontainers/about/) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="4656d-361">Per usare i contenitori Windows si eseguono i comandi di PowerShell in Dockerfile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="4656d-361">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore

LABEL Description="IIS" Vendor="Microsoft" Version="10"

RUN powershell -Command Add-WindowsFeature Web-Server

CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="4656d-362">In questo caso si usa un'immagine di base di Windows Server Core (impostazione FROM) e si installa IIS con un comando di PowerShell (impostazione RUN).</span><span class="sxs-lookup"><span data-stu-id="4656d-362">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="4656d-363">In modo analogo è possibile usare i comandi di PowerShell anche per configurare componenti aggiuntivi come ASP.NET 4. x, .NET 4.6 o qualsiasi altro software Windows.</span><span class="sxs-lookup"><span data-stu-id="4656d-363">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="4656d-364">Ad esempio il comando seguente in un Dockerfile configura ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="4656d-364">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="4656d-365">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4656d-365">Additional resources</span></span>

- <span data-ttu-id="4656d-366">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="4656d-366">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="4656d-367">Comandi di Powershell di esempio eseguibili da dockerfile per includere funzionalità di Windows.</span><span class="sxs-lookup"><span data-stu-id="4656d-367">Example Powershell commands to run from dockerfiles to include Windows features.</span></span>

   [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
><span data-ttu-id="4656d-368">[Precedente](index.md)
>[Successivo](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="4656d-368">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
