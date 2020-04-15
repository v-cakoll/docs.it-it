---
title: Flusso di lavoro di sviluppo per app Docker
description: Informazioni dettagliate sul flusso di lavoro richiesto per lo sviluppo delle applicazioni basate su Docker. Iniziare gradualmente e approfondire alcuni dettagli per ottimizzare i Dockerfile e terminare con il flusso di lavoro semplificato disponibile quando si usa Visual Studio.
ms.date: 01/30/2020
ms.openlocfilehash: 2f380c840e186c345f9222aa6b0cf1097a74874e
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389194"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="b0b9d-104">Flusso di lavoro di sviluppo per app Docker</span><span class="sxs-lookup"><span data-stu-id="b0b9d-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="b0b9d-105">Il ciclo di vita dello sviluppo applicativo inizia nel computer dello sviluppatore, che qui scrive l'applicazione usando il linguaggio preferito ed esegue i relativi test in locale.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="b0b9d-106">Con questo flusso di lavoro, indipendentemente dal linguaggio, dal framework e dalla piattaforma scelti, si sviluppano e testano sempre contenitori Docker, ma a livello locale.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="b0b9d-107">Ogni contenitore, ovvero un'istanza di un'immagine Docker, include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="b0b9d-108">Un sistema operativo a scelta, ad esempio una distribuzione Linux, Windows Nano Server o Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="b0b9d-109">I file aggiunti durante lo sviluppo, ad esempio, il codice sorgente e i file binari dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="b0b9d-110">Informazioni di configurazione, ad esempio impostazioni di ambiente e dipendenze.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="b0b9d-111">Flusso di lavoro per lo sviluppo di applicazioni Docker basate su contenitore</span><span class="sxs-lookup"><span data-stu-id="b0b9d-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="b0b9d-112">Questa sezione descrive il flusso di lavoro di sviluppo a *ciclo interno* per applicazioni Docker basate su contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="b0b9d-113">Il flusso di lavoro del ciclo interno significa che non sta prendendo in considerazione il flusso di lavoro DevOps più ampio, che può includere fino alla distribuzione di produzione, e si concentra solo sul lavoro di sviluppo eseguito nel computer dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-113">The inner-loop workflow means it's not considering the broader DevOps workflow, which can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="b0b9d-114">I passaggi iniziali per configurare l'ambiente non sono inclusi, poiché vengono eseguiti una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="b0b9d-115">Un'applicazione è costituita da servizi e raccolte aggiuntive, ossia dipendenze.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="b0b9d-116">Di seguito sono indicati i passaggi di base che si eseguono in genere quando si compila un'applicazione Docker, come illustrato nella figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramma che mostra i 7 passaggi necessari per creare un'app in contenitori.":::
<span data-ttu-id="b0b9d-118">Il processo di sviluppo per le app Docker: 1 - Codificare l'app, 2 - Scrivere Dockerfile/s, 3 - Creare immagini definite in Dockerfile/s, 4 - (facoltativo) Componi servizi nel file docker-compose.yml, 5 - Esegui app contenitore o docker-compose, 6 - Testl'app o microservizi, 7 - Push per ripetere e ripetere.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-118">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="b0b9d-119">**Come illustrato nella figura 5-1.**</span><span class="sxs-lookup"><span data-stu-id="b0b9d-119">**Figure 5-1.**</span></span> <span data-ttu-id="b0b9d-120">Flusso di lavoro passo per passo per lo sviluppo di applicazioni Docker in contenitori</span><span class="sxs-lookup"><span data-stu-id="b0b9d-120">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="b0b9d-121">Questa sezione descrive nei dettagli l'intero processo e ogni passaggio principale è spiegato con riferimento all'ambiente Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-121">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="b0b9d-122">Quando si usa un approccio di sviluppo editor/CLI, ad esempio codice Visual Studio e CLI di Docker in macOS o Windows, di solito è necessario conoscere ogni passaggio in modo più dettagliato rispetto all'uso di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-122">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="b0b9d-123">Per altre informazioni sull'uso di un ambiente CLI, vedere l'e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo di vita di un'applicazione Docker in un contenitore con piattaforme e strumenti Microsoft).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-123">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="b0b9d-124">Quando si usa Visual Studio 2019, molti di questi passaggi vengono gestiti per l'utente, aumentando notevolmente la produttività.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-124">When you're using Visual Studio 2019, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="b0b9d-125">Ciò è particolarmente vero quando si utilizza Visual Studio 2019 e la destinazione di applicazioni multi-contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-125">This is especially true when you're using Visual Studio 2019 and targeting multi-container applications.</span></span> <span data-ttu-id="b0b9d-126">Ad esempio, con un solo clic `Dockerfile` del `docker-compose.yml` mouse, Visual Studio aggiunge il file e ai progetti con la configurazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-126">For instance, with just one mouse click, Visual Studio adds the `Dockerfile` and `docker-compose.yml` file to your projects with the configuration for your application.</span></span> <span data-ttu-id="b0b9d-127">Quando si esegue l'applicazione in Visual Studio, viene creata l'immagine Docker e l'applicazione a più contenitori viene eseguita direttamente in Docker; è anche possibile eseguire il debug di diversi contenitori contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-127">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="b0b9d-128">Queste funzionalità rendono lo sviluppo più veloce.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-128">These features will boost your development speed.</span></span>

<span data-ttu-id="b0b9d-129">Tuttavia, anche se Visual Studio automatizza questi passaggi, ciò non significa che non sia necessario sapere cosa succede dietro le quinte con Docker.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-129">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="b0b9d-130">Di conseguenza, il materiale sussidiario seguente illustra in dettaglio ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-130">Therefore, the following guidance details every step.</span></span>

![Immagine per il passaggio 1.](./media/docker-app-development-workflow/step-1-code-your-app.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="b0b9d-132">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-132">Step 1.</span></span> <span data-ttu-id="b0b9d-133">Iniziare a scrivere il codice e ad abbozzare l'applicazione o il servizio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-133">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="b0b9d-134">Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza Docker.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-134">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="b0b9d-135">La differenza è che, quando si sviluppa per Docker, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale (una macchina virtuale Linux configurata da Docker o direttamente Windows se si usano i contenitori Windows).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-135">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="b0b9d-136">Configurare l'ambiente locale con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-136">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="b0b9d-137">Per iniziare, accertarsi che sia installato [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) per Windows, come spiegato nelle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-137">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="b0b9d-138">Introduzione a Docker CE per Windows</span><span class="sxs-lookup"><span data-stu-id="b0b9d-138">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="b0b9d-139">Inoltre, è necessario Visual Studio 2019 versione 16.4 o successiva, con il carico di lavoro di **sviluppo multipiattaforma .NET Core** installato, come illustrato nella Figura 5-2.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-139">In addition, you need Visual Studio 2019 version 16.4 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Screenshot della selezione dello sviluppo multipiattaforma .NET Core.](./media/docker-app-development-workflow/dotnet-core-cross-platform-development.png)

<span data-ttu-id="b0b9d-141">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-141">**Figure 5-2**.</span></span> <span data-ttu-id="b0b9d-142">Selezione del carico di lavoro di **sviluppo multipiattaforma .NET Core** durante l'installazione di Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b0b9d-142">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2019 setup</span></span>

<span data-ttu-id="b0b9d-143">È possibile iniziare a scrivere il codice dell'applicazione in .NET normale, di solito in .NET Core se si prevede di usare contenitori, anche prima di attivare Docker nell'applicazione e di eseguire la distribuzione e i test in Docker,</span><span class="sxs-lookup"><span data-stu-id="b0b9d-143">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="b0b9d-144">ma si consiglia di iniziare a lavorare in Docker appena possibile, perché quello sarà l'ambiente reale e gli eventuali problemi possono essere individuati velocemente.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-144">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="b0b9d-145">Si consiglia di procedere in questo modo perché Visual Studio facilita così tanto il lavoro con Docker da diventare quasi trasparente, soprattutto quando lo si usa per eseguire il debug di applicazioni a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-145">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b0b9d-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0b9d-146">Additional resources</span></span>

- <span data-ttu-id="b0b9d-147">**Introduzione a Docker CE per Windows** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-147">**Get started with Docker CE for Windows** </span></span>\
  <https://docs.docker.com/docker-for-windows/>

- <span data-ttu-id="b0b9d-148">**Visual Studio 2019** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-148">**Visual Studio 2019** </span></span>\
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)

![Immagine per il passaggio 2.](./media/docker-app-development-workflow/step-2-write-dockerfile.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="b0b9d-150">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-150">Step 2.</span></span> <span data-ttu-id="b0b9d-151">Creare un Dockerfile correlato a un'immagine di base .NET esistente</span><span class="sxs-lookup"><span data-stu-id="b0b9d-151">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="b0b9d-152">È necessario un Dockerfile per ogni immagine personalizzata che si desidera creare; è necessario un Dockerfile per ogni contenitore da distribuire, sia che si esegua la distribuzione automaticamente da Visual Studio o manualmente con la CLI di Docker: comandi docker run e docker-compose.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-152">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="b0b9d-153">Se l'applicazione contiene un solo servizio personalizzato, è necessario un solo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-153">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="b0b9d-154">Se l'applicazione contiene più servizi, come in un'architettura a microservizi, è necessario un Dockerfile per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-154">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="b0b9d-155">Il Dockerfile viene inserito nella cartella radice dell'applicazione o del servizio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-155">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="b0b9d-156">Contiene i comandi che indicano a Docker come configurare ed eseguire l'applicazione o il servizio in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-156">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="b0b9d-157">È possibile creare manualmente un Dockerfile nel codice e aggiungerlo al progetto insieme alle dipendenze .NET.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-157">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="b0b9d-158">Con Visual Studio e i relativi strumenti per Docker questa attività richiede solo pochi clic del mouse.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-158">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="b0b9d-159">Quando si crea un nuovo progetto in Visual Studio 2019, è disponibile un'opzione denominata **Abilita supporto Docker**, come illustrato nella Figura 5-3.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-159">When you create a new project in Visual Studio 2019, there's an option named **Enable Docker Support**, as shown in Figure 5-3.</span></span>

![Screenshot della casella di controllo Abilita supporto Docker.](./media/docker-app-development-workflow/enable-docker-support-check-box.png)

<span data-ttu-id="b0b9d-161">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-161">**Figure 5-3**.</span></span> <span data-ttu-id="b0b9d-162">Abilitazione del supporto Docker durante la creazione di un nuovo progetto ASP.NET Core in Visual Studio 2019Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b0b9d-162">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2019</span></span>

<span data-ttu-id="b0b9d-163">È inoltre possibile abilitare il supporto Docker in un progetto di app Web ASP.NET Core esistente facendo clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionando **Aggiungi** > **supporto Docker...**, come illustrato nella Figura 5-4.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-163">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support...**, as shown in Figure 5-4.</span></span>

![Screenshot che mostra l'opzione Supporto Docker nel menu Aggiungi.](./media/docker-app-development-workflow/add-docker-support-option.png)

<span data-ttu-id="b0b9d-165">**Figura 5-4**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-165">**Figure 5-4**.</span></span> <span data-ttu-id="b0b9d-166">Abilitazione del supporto Docker in un progetto Visual Studio 2019 esistenteEnabling Docker support in an existing Visual Studio 2019 project</span><span class="sxs-lookup"><span data-stu-id="b0b9d-166">Enabling Docker support in an existing Visual Studio 2019 project</span></span>

<span data-ttu-id="b0b9d-167">Questa azione aggiunge un *Dockerfile* al progetto con la configurazione richiesta ed è disponibile solo nei progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-167">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="b0b9d-168">In modo analogo, Visual Studio `docker-compose.yml` può anche aggiungere un file per l'intera soluzione con l'opzione Aggiungi > supporto dell'orchestratore **contenitore...**. Nel passaggio 4 verrà esaminata questa opzione in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-168">In a similar fashion, Visual Studio can also add a `docker-compose.yml` file for the whole solution with the option **Add > Container Orchestrator Support...**. In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="b0b9d-169">Uso di un'immagine Docker .NET ufficiale esistente</span><span class="sxs-lookup"><span data-stu-id="b0b9d-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="b0b9d-170">In genere per il contenitore si crea un'immagine personalizzata sopra un'immagine di base che è possibile ottenere da un repository ufficiale come il registro [Hub Docker](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="b0b9d-171">Questo è esattamente ciò che accade dietro le quinte quando si attiva il supporto Docker in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="b0b9d-172">Il Dockerfile userà un'immagine `dotnet/core/aspnet` esistente.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-172">Your Dockerfile will use an existing `dotnet/core/aspnet` image.</span></span>

<span data-ttu-id="b0b9d-173">In precedenza si è visto le immagini e repository Docker da usare in base al framework e al sistema operativo scelto.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="b0b9d-174">Ad esempio, se si usa ASP.NET Core (Linux o Windows), l'immagine da usare è `mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="b0b9d-175">Pertanto è sufficiente specificare l'immagine Docker di base che sarà usata per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="b0b9d-176">A tale scopo, aggiungere `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1` al Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-176">You do that by adding `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1` to your Dockerfile.</span></span> <span data-ttu-id="b0b9d-177">Visual Studio esegue l'operazione automaticamente, ma se si aggiornasse la versione, verrebbe aggiornato anche questo valore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="b0b9d-178">L'uso di un repository ufficiale di immagini .NET di Docker Hub con un numero di versione garantisce che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="b0b9d-179">L'esempio seguente illustra un esempio di Dockerfile per un contenitore ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="b0b9d-180">In questo caso, l'immagine si basa sulla versione 3.1 dell'immagine ufficiale ASP.NET Core Docker (multi-arch per Linux e Windows).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-180">In this case, the image is based on version 3.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="b0b9d-181">Si tratta dell'impostazione `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-181">This is the setting `FROM mcr.microsoft.com/dotnet/core/aspnet:3.1`.</span></span> <span data-ttu-id="b0b9d-182">Per altre informazioni su questa immagine di base, vedere la pagina [.NET Core Docker Image.](https://hub.docker.com/_/microsoft-dotnet-core/) Nel Dockerfile, è inoltre necessario indicare Docker per l'ascolto sulla porta TCP che verrà utilizzato in fase di esecuzione (in questo caso, la porta 80, come configurato con l'impostazione EXPOSE).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="b0b9d-183">Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="b0b9d-184">Ad esempio, la riga ENTRYPOINT con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker di eseguire un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="b0b9d-185">Se si usa l'SDK e l'interfaccia della riga di comando di .NET Core, ovvero l'interfaccia della riga di comando dotnet, per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="b0b9d-186">In sostanza la riga ENTRYPOINT e altre impostazioni saranno diverse a seconda del linguaggio e della piattaforma scelti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b0b9d-187">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0b9d-187">Additional resources</span></span>

- <span data-ttu-id="b0b9d-188">**Creazione di immagini Docker per applicazioni .NET CoreBuilding Docker Images for .NET Core Applications** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-188">**Building Docker Images for .NET Core Applications** </span></span>\
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

- <span data-ttu-id="b0b9d-189">**Creare un'immagine**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-189">**Build your own image**.</span></span> <span data-ttu-id="b0b9d-190">Nella documentazione ufficiale di Docker.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-190">In the official Docker documentation.</span></span>\
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- <span data-ttu-id="b0b9d-191">**Rimanere aggiornati con le immagini del contenitore .NET** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-191">**Staying up-to-date with .NET Container Images** </span></span>\
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- <span data-ttu-id="b0b9d-192">**Utilizzo di .NET e Docker insieme - Aggiornamento DockerCon 2018** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-192">**Using .NET and Docker Together - DockerCon 2018 Update** </span></span>\
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="b0b9d-193">Uso di repository di immagini multi-arch</span><span class="sxs-lookup"><span data-stu-id="b0b9d-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="b0b9d-194">Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="b0b9d-195">Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="b0b9d-196">Ad esempio, il repository [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) disponibile nel registro dell'hub Docker fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di repository.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-196">For example, the [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="b0b9d-197">Se si specifica un tag, ci si rivolge a una piattaforma esplicita come nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim` \
  <span data-ttu-id="b0b9d-198">Destinazioni: .NET Core 3.1 solo runtime in LinuxTargets: .NET Core 3.1 runtime-only on Linux</span><span class="sxs-lookup"><span data-stu-id="b0b9d-198">Targets: .NET Core 3.1 runtime-only on Linux</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1-nanoserver-1909` \
  <span data-ttu-id="b0b9d-199">Destinazioni: .NET Core 3.1 solo runtime in Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="b0b9d-199">Targets: .NET Core 3.1 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="b0b9d-200">Ma se si specifica lo stesso nome di immagine, anche con lo stesso tag, le immagini multi-arch, ad esempio l'immagine `aspnet`, useranno la versione Linux o Windows in base al sistema operativo host Docker che si sta distribuendo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnet` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `mcr.microsoft.com/dotnet/core/aspnet:3.1` \
  <span data-ttu-id="b0b9d-201">Multi-arch: .NET Core 3.1 solo runtime su Linux o Windows Nano Server a seconda del sistema operativo host Docker</span><span class="sxs-lookup"><span data-stu-id="b0b9d-201">Multi-arch: .NET Core 3.1 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="b0b9d-202">In questo modo, se si esegue il pull di un'immagine da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome di immagine da un host Linux si ottiene la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="b0b9d-203">Compilazioni in più fasi in Dockerfile</span><span class="sxs-lookup"><span data-stu-id="b0b9d-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="b0b9d-204">Il Dockerfile è simile a uno script batch.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="b0b9d-205">Esegue le operazioni che sarebbe necessario eseguire per configurare il computer dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="b0b9d-206">Inizia con un'immagine di base che imposta il contesto iniziale, analogamente al filesystem di avvio, e si trova nella parte superiore del sistema operativo host.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="b0b9d-207">Non è un sistema operativo, ma si può pensare ad esso come "il" Sistema operativo all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-207">It's not an OS, but you can think of it like "the" OS inside the container.</span></span>

<span data-ttu-id="b0b9d-208">L'esecuzione di ogni riga di comando crea un nuovo livello nel filesystem con le modifiche di quello precedente, in modo che la combinazione generi il filesystem risultante.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="b0b9d-209">Poiché ogni nuovo livello viene creato sopra il livello precedente e le dimensioni dell'immagine risultante aumentano ad ogni comando, le immagini possono diventare molto grandi se devono includere, ad esempio, l'SDK necessario per compilare e pubblicare un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="b0b9d-210">Qui è dove le compilazioni in più fasi entrano in gioco (da Docker 17.05 e versioni successive) e dimostrano tutta la loro efficacia.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="b0b9d-211">L'idea di base è che è possibile separare il processo di esecuzione Dockerfile in più fasi, in cui una fase è un'immagine iniziale seguita da uno o più comandi e l'ultima fase determina le dimensioni dell'immagine finale.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="b0b9d-212">In breve, le compilazioni in più fasi consentono di suddividere la creazione in diversi passaggi e quindi assemblare l'immagine finale usando solo le directory pertinenti delle fasi intermedie.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="b0b9d-213">La strategia generale per usare questa funzionalità è:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="b0b9d-214">Usare un'immagine di base dell'SDK (le dimensioni non sono importanti), con tutto ciò che serve per compilare e pubblicare l'applicazione in una cartella e quindi</span><span class="sxs-lookup"><span data-stu-id="b0b9d-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="b0b9d-215">usare un'immagine di base, piccola e solo di runtime, e copiare la cartella di pubblicazione della fase precedente per produrre un'immagine finale di dimensioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="b0b9d-216">Probabilmente il modo migliore per comprendere la compilazione in più fasi è esaminare un Dockerfile in dettaglio, riga per riga, quindi si può iniziare con il Dockerfile creato da Visual Studio quando si aggiunge il supporto Docker a un progetto e vedere alcune ottimizzazioni in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="b0b9d-217">Il Dockerfile iniziale può avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks …
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="b0b9d-218">E questi sono i dettagli, riga per riga:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-218">And these are the details, line by line:</span></span>

- <span data-ttu-id="b0b9d-219">**Linea #1:** Iniziare una fase con un'immagine di base "piccola" di sola runtime, chiamarla **base** per riferimento.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-219">**Line #1:** Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>

- <span data-ttu-id="b0b9d-220">**Linea #2:** Creare la directory **/app** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-220">**Line #2:** Create the **/app** directory in the image.</span></span>

- <span data-ttu-id="b0b9d-221">**Linea #3:** Esporre la porta **80**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-221">**Line #3:** Expose port **80**.</span></span>

- <span data-ttu-id="b0b9d-222">**Linea #5:** Inizia una nuova fase con l'immagine "grande" per la costruzione/pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-222">**Line #5:** Begin a new stage with the "large" image for building/publishing.</span></span> <span data-ttu-id="b0b9d-223">Chiamarlo **build** per riferimento.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-223">Call it **build** for reference.</span></span>

- <span data-ttu-id="b0b9d-224">**#6 linea:** Creare la directory **/src** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-224">**Line #6:** Create directory **/src** in the image.</span></span>

- <span data-ttu-id="b0b9d-225">**#7 linea:** Fino alla riga 16, copiare i file di progetto **con estensione csproj** per poter ripristinare i pacchetti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-225">**Line #7:** Up to line 16, copy referenced **.csproj** project files to be able to restore packages later.</span></span>

- <span data-ttu-id="b0b9d-226">**Linea #17:** Ripristinare i pacchetti per il progetto **Catalog.API** e i progetti a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-226">**Line #17:** Restore packages for the **Catalog.API** project and the referenced projects.</span></span>

- <span data-ttu-id="b0b9d-227">**#18 linea:** Copiare tutta la struttura di **directory per la soluzione** (ad eccezione dei file/directory inclusi nel file **.dockerignore)** nella directory **/src** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-227">**Line #18:** Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) to the **/src** directory in the image.</span></span>

- <span data-ttu-id="b0b9d-228">**Linea #19:** Modificare la cartella corrente nel progetto **Catalog.API.**</span><span class="sxs-lookup"><span data-stu-id="b0b9d-228">**Line #19:** Change the current folder to the **Catalog.API** project.</span></span>

- <span data-ttu-id="b0b9d-229">**Linea #20:** Compilare il progetto (e altre dipendenze del progetto) e l'output nella directory **/app** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-229">**Line #20:** Build the project (and other project dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="b0b9d-230">**Linea #22:** Iniziare una nuova fase continuando dalla compilazione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-230">**Line #22:** Begin a new stage continuing from the build.</span></span> <span data-ttu-id="b0b9d-231">Chiamarlo **pubblicare** come riferimento.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-231">Call it **publish** for reference.</span></span>

- <span data-ttu-id="b0b9d-232">**#23 linea:** Pubblicare il progetto (e le dipendenze) e l'output nella directory **/app** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-232">**Line #23:** Publish the project (and dependencies) and output to the **/app** directory in the image.</span></span>

- <span data-ttu-id="b0b9d-233">**Linea #25:** Iniziare una nuova fase continuando dalla **base** e chiamarlo **finale**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-233">**Line #25:** Begin a new stage continuing from **base** and call it **final**.</span></span>

- <span data-ttu-id="b0b9d-234">**Linea #26:** Modificare la directory corrente in **/app**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-234">**Line #26:** Change the current directory to **/app**.</span></span>

- <span data-ttu-id="b0b9d-235">**#27 linea:** Copiare la directory **/app** dalla **pubblicazione** della fase nella directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-235">**Line #27:** Copy the **/app** directory from stage **publish** to the current directory.</span></span>

- <span data-ttu-id="b0b9d-236">**Linea #28:** Definire il comando da eseguire all'avvio del contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-236">**Line #28:** Define the command to run when the container is started.</span></span>

<span data-ttu-id="b0b9d-237">Esaminare ora alcune ottimizzazioni che consentono di migliorare le prestazioni generali del processo che, nel caso di eShopOnContainers, corrispondono a circa 22 minuti o più per la compilazione della soluzione completa nei contenitori Linux.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-237">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="b0b9d-238">Si può sfruttare la funzionalità di cache per i livelli di Docker, che è piuttosto semplice: se l'immagine di base e i comandi corrispondono ad altri già eseguiti in precedenza, è possibile usare solo il livello risultante senza dover eseguire i comandi, risparmiando tempo.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-238">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="b0b9d-239">Quindi, concentrarsi sulla fase **build**, dove le righe 5 e 6 sono praticamente le stesse, ma le righe da 7 a 17 sono diverse per ogni servizio di eShopOnContainers, quindi devono essere eseguite ogni singola volta. Tuttavia, se le righe da 7 a 16 sono state modificate in:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-239">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```Dockerfile
COPY . .
```

<span data-ttu-id="b0b9d-240">Si avrebbe lo stesso per ogni servizio, verrebbe copiata l'intera soluzione e verrebbe creato un livello di dimensioni maggiori ma:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-240">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1. <span data-ttu-id="b0b9d-241">Il processo di copia verrebbe eseguito solo la prima volta (e quando si ricompila se viene modificato un file) e userebbe la cache per tutti gli altri servizi e</span><span class="sxs-lookup"><span data-stu-id="b0b9d-241">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2. <span data-ttu-id="b0b9d-242">Poiché l'immagine più grande si verifica in una fase intermedia, non influisce sulle dimensioni dell'immagine finale.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-242">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="b0b9d-243">Un'altra ottimizzazione significativa riguarda il comando `restore` eseguito alla riga 17, che è diverso per ogni servizio di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-243">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="b0b9d-244">Se si modifica tale riga semplicemente in:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-244">If you change that line to just:</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="b0b9d-245">I pacchetti verrebbero ripristinati per l'intera soluzione, ma anche in questo caso l'operazione verrebbe eseguita una sola volta, anziché 15 volte come con la strategia attuale.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-245">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="b0b9d-246">Tuttavia, `dotnet restore` viene eseguito solo se è presente un solo progetto o file di soluzione nella cartella, quindi ottenere questo risultato è un po' più complesso e il modo per ottenerlo, senza entrare troppo nel dettaglio, è questo:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-246">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1. <span data-ttu-id="b0b9d-247">Aggiungere le righe seguenti al file **DOCKERIGNORE**:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-247">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="b0b9d-248">`*.sln`, per ignorare tutti i file di soluzione nella struttura della cartella principale</span><span class="sxs-lookup"><span data-stu-id="b0b9d-248">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="b0b9d-249">`!eShopOnContainers-ServicesAndWebApps.sln`, per includere solo questo file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-249">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2. <span data-ttu-id="b0b9d-250">Includere l'argomento `/ignoreprojectextensions:.dcproj` a `dotnet restore`, in modo che ignori anche il progetto docker-compose e ripristini solo i pacchetti per la soluzione eShopOnContainers-ServicesAndWebApps.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-250">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="b0b9d-251">Per l'ottimizzazione finale, la riga 20 risulta ridondante, poiché anche la riga 23 compila l'applicazione e praticamente viene subito dopo la riga 20, quindi si ha un altro comando che richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-251">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="b0b9d-252">Il file risultante quindi è:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-252">The resulting file is then:</span></span>

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -o /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="b0b9d-253">Creazione dell'immagine di base da zero</span><span class="sxs-lookup"><span data-stu-id="b0b9d-253">Creating your base image from scratch</span></span>

<span data-ttu-id="b0b9d-254">È possibile creare un'immagine Docker di base da zero.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-254">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="b0b9d-255">Questo scenario non è consigliato se non si conosce bene Docker, ma se si vuole creare la propria immagine di base è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-255">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b0b9d-256">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0b9d-256">Additional resources</span></span>

- <span data-ttu-id="b0b9d-257">**Immagini .NET Core multi-arco.**</span><span class="sxs-lookup"><span data-stu-id="b0b9d-257">**Multi-arch .NET Core images**.\</span></span>
  <https://github.com/dotnet/announcements/issues/14>

- <span data-ttu-id="b0b9d-258">**Creare un'immagine di base**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-258">**Create a base image**.</span></span> <span data-ttu-id="b0b9d-259">Documentazione ufficiale di Docker.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-259">Official Docker documentation.</span></span>\
  <https://docs.docker.com/develop/develop-images/baseimages/>

![Immagine per il passaggio 3.](./media/docker-app-development-workflow/step-3-create-dockerfile-defined-images.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="b0b9d-261">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-261">Step 3.</span></span> <span data-ttu-id="b0b9d-262">Creare le immagini Docker personalizzate e incorporare l'applicazione o il servizio in esse</span><span class="sxs-lookup"><span data-stu-id="b0b9d-262">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="b0b9d-263">Per ogni servizio dell'applicazione è necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-263">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="b0b9d-264">Se l'applicazione è costituita da un singolo servizio o applicazione Web, è sufficiente una singola immagine.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-264">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="b0b9d-265">Si noti che le immagini Docker vengono create automaticamente in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-265">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="b0b9d-266">I passaggi seguenti sono necessari solo per il flusso di lavoro editor/CLI e sono descritti per chiarire meglio ciò che succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-266">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="b0b9d-267">Lo sviluppatore deve eseguire lo sviluppo e i test localmente finché non esegue il push di una funzionalità o di una modifica completa nel sistema di controllo del codice sorgente, ad esempio in GitHub.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-267">You, as a developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="b0b9d-268">Ciò significa che è necessario creare le immagini Docker e distribuire i contenitori in un host Docker locale, ovvero una VM Windows o Linux, nonché eseguire, testare ed eseguire il debug in tali contenitori locale.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-268">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="b0b9d-269">Per creare un'immagine personalizzata nell'ambiente locale tramite la CLI di Docker e il Dockerfile, è possibile usare il comando docker build, come illustrato nella figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-269">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Screenshot che mostra l'output della console del comando docker build.](./media/docker-app-development-workflow/run-docker-build-command.png)

<span data-ttu-id="b0b9d-271">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-271">**Figure 5-5**.</span></span> <span data-ttu-id="b0b9d-272">Creazione di un'immagine Docker personalizzata</span><span class="sxs-lookup"><span data-stu-id="b0b9d-272">Creating a custom Docker image</span></span>

<span data-ttu-id="b0b9d-273">Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è possibile generare innanzitutto una cartella distribuibile con le raccolte .NET e i file binari necessari eseguendo `dotnet publish` e quindi usando il comando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-273">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="b0b9d-274">Verrà creata un'immagine Docker con il nome `cesardl/netcore-webapi-microservice-docker:first`.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-274">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="b0b9d-275">In questo caso :first è un tag che rappresenta una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-275">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="b0b9d-276">È possibile ripetere questo passaggio per ogni immagine personalizzata da creare per l'applicazione Docker composta.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-276">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="b0b9d-277">Quando un'applicazione è costituita da più contenitori, ovvero è un'applicazione a più contenitori, è anche possibile usare il comando `docker-compose up --build` per compilare tutte le immagini correlate con un singolo comando usando i metadati esposti nei file docker-compose.yml correlati.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-277">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="b0b9d-278">È possibile trovare le immagini esistenti nel repository locale tramite il comando docker images, come illustrato nella figura 5-6.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-278">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Output della console del comando docker images che illustra le immagini esistenti.](./media/docker-app-development-workflow/view-existing-images-with-docker-images.png)

<span data-ttu-id="b0b9d-280">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="b0b9d-280">**Figure 5-6.**</span></span> <span data-ttu-id="b0b9d-281">Visualizzazione di immagini esistente con il comando docker images</span><span class="sxs-lookup"><span data-stu-id="b0b9d-281">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="b0b9d-282">Creazione di immagini Docker con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-282">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="b0b9d-283">Quando si usa Visual Studio per creare un progetto con il supporto Docker, non si crea un'immagine in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-283">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="b0b9d-284">L'immagine viene invece creata automaticamente quando si preme **F5** (o **CTRL-F5**) e si esegue l'applicazione o il servizio Docker.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-284">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="b0b9d-285">Questo passaggio è automatico e invisibile in Visual Studio, ma è importante sapere cosa succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-285">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![Immagine per il passaggio facoltativo 4.](./media/docker-app-development-workflow/step-4-define-services-docker-compose-yml.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="b0b9d-287">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-287">Step 4.</span></span> <span data-ttu-id="b0b9d-288">Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori</span><span class="sxs-lookup"><span data-stu-id="b0b9d-288">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="b0b9d-289">Il file [docker compose.yml](https://docs.docker.com/compose/compose-file/) consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-289">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="b0b9d-290">Configura inoltre le proprie relazioni di dipendenza e la configurazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-290">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="b0b9d-291">Per usare un file docker-compose.yml, è necessario creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-291">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
    ports:
      - "80:80"
    depends_on:
      - catalog-api
      - ordering-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Port=1433;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sqldata

  sqldata:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

<span data-ttu-id="b0b9d-292">Questo file docker-compose.yml è una versione semplificata e unita.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-292">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="b0b9d-293">Contiene dati di configurazione statici per ogni contenitore, ad esempio il nome dell'immagine personalizzata, che sono sempre richiesti, nonché informazioni di configurazione che possono dipendere dall'ambiente di distribuzione, ad esempio la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-293">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="b0b9d-294">Nelle sezioni successive si vedrà come suddividere la configurazione di docker-compose.yml in più file docker-compose e come sostituire valori a seconda del tipo di ambiente e di esecuzione (debug o release).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-294">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="b0b9d-295">L'esempio di file docker-compose.yml definisce quattro servizi: il servizio `webmvc` (un'applicazione Web), due microservizi (`ordering-api` e `basket-api`) e un contenitore origine dati, `sqldata`, basato su SQL Server per Linux eseguito come contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-295">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering-api` and `basket-api`), and one data source container, `sqldata`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="b0b9d-296">Ogni servizio verrà distribuito come contenitore, quindi è necessaria un'immagine Docker per ognuno.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-296">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="b0b9d-297">Il file docker-compose.yml specifica non solo quali contenitori vengono usati, ma come sono configurati singolarmente.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-297">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="b0b9d-298">Ad esempio, la definizione del contenitore `webmvc` nel file YML:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-298">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="b0b9d-299">Usa un'immagine `eshop/web:latest` predefinita.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-299">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="b0b9d-300">Tuttavia, è anche possibile configurare l'immagine in modo che sia compilata come parte dell'esecuzione di docker-compose con una configurazione aggiuntiva basata su una sezione build: nel file docker-compose.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-300">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="b0b9d-301">Inizializza due variabili di ambiente, ovvero CatalogUrl e OrderingUrl.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-301">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="b0b9d-302">Inoltra la porta 80 esposta sul contenitore alla porta esterna 80 sul computer host.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-302">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="b0b9d-303">Collega l'app Web al catalogo e al servizio di ordinazione con l'impostazione depends_on.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-303">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="b0b9d-304">In questo modo il servizio attende fino a quando vengono avviati i servizi.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-304">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="b0b9d-305">Il file docker-compose.yml sarà esaminato di nuovo in una sezione successiva in cui sarà descritto come implementare microservizi e app a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-305">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2019"></a><span data-ttu-id="b0b9d-306">Utilizzo di docker-compose.yml in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b0b9d-306">Working with docker-compose.yml in Visual Studio 2019</span></span>

<span data-ttu-id="b0b9d-307">Oltre ad aggiungere un Dockerfile a un progetto, come accennato in precedenza, Visual Studio 2017 (dalla versione 15.8 in poi) può aggiungere il supporto dell'agente di orchestrazione per Docker Compose a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-307">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from version 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="b0b9d-308">Quando si aggiunge il supporto dell'agente di orchestrazione del contenitore, come illustrato nella figura 5-7, per la prima volta, Visual Studio crea il Dockerfile per il progetto e crea un nuovo progetto (sezione servizio) nella soluzione con diversi file `docker-compose*.yml` globali e quindi aggiunge il progetto a tali file.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-308">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="b0b9d-309">È quindi possibile aprire i file docker-compose.yml e aggiornarli con funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-309">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="b0b9d-310">È necessario ripetere questa operazione per ogni progetto che si vuole includere nel file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-310">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="b0b9d-311">Al momento della stesura di questo articolo, Visual Studio supporta gli orchestratori **Docker Compose** e **Kubernetes/Helm.**</span><span class="sxs-lookup"><span data-stu-id="b0b9d-311">At the time of this writing, Visual Studio supports **Docker Compose** and **Kubernetes/Helm** orchestrators.</span></span>

![Screenshot che mostra l'opzione Supporto orchestrator contenitore nel menu di scelta rapida del progetto.](./media/docker-app-development-workflow/add-container-orchestrator-support-option.png)

<span data-ttu-id="b0b9d-313">**Figura 5-7**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-313">**Figure 5-7**.</span></span> <span data-ttu-id="b0b9d-314">Aggiunta del supporto Docker in Visual Studio 2019 facendo clic con il pulsante destro del mouse su un progetto ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b0b9d-314">Adding Docker support in Visual Studio 2019 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="b0b9d-315">Dopo aver aggiunto il supporto dell'agente di orchestrazione alla soluzione in Visual Studio, si noterà anche un nuovo nodo nel file di progetto `docker-compose.dcproj` in Esplora soluzioni, che contiene i file docker-compose.yml aggiunti, come illustrato nella figura 5-8.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-315">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![Screenshot del nodo docker-compose in Esplora soluzioni.](./media/docker-app-development-workflow/docker-compose-tree-node.png)

<span data-ttu-id="b0b9d-317">**Figura 5-8**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-317">**Figure 5-8**.</span></span> <span data-ttu-id="b0b9d-318">Nodo della struttura ad albero docker-compose aggiunto in Esplora soluzioni di Visual Studio 2019The **docker-compose** tree node added in Visual Studio 2019 Solution Explorer</span><span class="sxs-lookup"><span data-stu-id="b0b9d-318">The **docker-compose** tree node added in Visual Studio 2019 Solution Explorer</span></span>

<span data-ttu-id="b0b9d-319">È possibile distribuire un'applicazione a più contenitori con un singolo file docker-compose.yml usando il comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-319">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="b0b9d-320">Tuttavia Visual Studio ne aggiunge un gruppo, quindi è possibile sostituire i valori in base all'ambiente, che può essere di sviluppo o di produzione, e al tipo di esecuzione (versione o debug).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-320">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="b0b9d-321">Questa funzionalità sarà spiegata nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-321">This capability will be explained in later sections.</span></span>

![Immagine per il passaggio 5.](./media/docker-app-development-workflow/step-5-run-containers-compose-app.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="b0b9d-323">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-323">Step 5.</span></span> <span data-ttu-id="b0b9d-324">Compilare ed eseguire l'applicazione Docker</span><span class="sxs-lookup"><span data-stu-id="b0b9d-324">Build and run your Docker application</span></span>

<span data-ttu-id="b0b9d-325">Se l'applicazione ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, ovvero una VM o un server fisico.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-325">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="b0b9d-326">Tuttavia, se l'applicazione contiene più servizi, è possibile distribuirla`docker-compose up)`come applicazione composta, utilizzando un singolo comando CLI ( , o con Visual Studio, che utilizzerà tale comando sotto le copertine.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-326">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (`docker-compose up)`, or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="b0b9d-327">Le diverse opzioni sono esaminate di seguito.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-327">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="b0b9d-328">Opzione A: Esecuzione di un'applicazione a contenitore singoloOption A: Running a single-container application</span><span class="sxs-lookup"><span data-stu-id="b0b9d-328">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="b0b9d-329">Con l'interfaccia della riga di comando di Docker</span><span class="sxs-lookup"><span data-stu-id="b0b9d-329">Using Docker CLI</span></span>

<span data-ttu-id="b0b9d-330">È possibile eseguire un contenitore Docker usando il comando `docker run`, come illustrato nella figura 5-9:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-330">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="b0b9d-331">Il comando precedente crea una nuova istanza di contenitore dall'immagine specificata, ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-331">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="b0b9d-332">È possibile `--name` utilizzare il parametro per assegnare `docker start {name}` un nome al contenitore e quindi utilizzare (o utilizzare l'ID del contenitore o il nome automatico) per eseguire un'istanza del contenitore esistente.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-332">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container ID or automatic name) to run an existing container instance.</span></span>

![Screenshot che esegue un contenitore Docker utilizzando il comando docker run.](./media/docker-app-development-workflow/use-docker-run-command.png)

<span data-ttu-id="b0b9d-334">**Figura 5-9**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-334">**Figure 5-9**.</span></span> <span data-ttu-id="b0b9d-335">Esecuzione di un contenitore Docker usando il comando docker run</span><span class="sxs-lookup"><span data-stu-id="b0b9d-335">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="b0b9d-336">In questo caso il comando associa la porta interna 5000 del contenitore alla porta 80 del computer host.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-336">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="b0b9d-337">Ciò significa che l'host è in ascolto sulla porta 80 e inoltra alla porta 5000 nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-337">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="b0b9d-338">L'hash visualizzato è l'ID contenitore e gli viene `--name` assegnato anche un nome leggibile casuale se l'opzione non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-338">The hash shown is the container ID and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="b0b9d-339">Con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-339">Using Visual Studio</span></span>

<span data-ttu-id="b0b9d-340">Se non è stato aggiunto il supporto dell'agente di orchestrazione dei contenitori, è anche possibile eseguire un'applicazione a singolo contenitore in Visual Studio premendo **CTRL+F5** e usare **F5** per eseguire il debug dell'applicazione all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-340">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="b0b9d-341">Il contenitore viene eseguito in locale usando docker run.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-341">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="b0b9d-342">Opzione B: esecuzione di un'applicazione a più contenitori</span><span class="sxs-lookup"><span data-stu-id="b0b9d-342">Option B: Running a multi-container application</span></span>

<span data-ttu-id="b0b9d-343">Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà composta da più servizi, perciò sarà necessario eseguire un'applicazione a più contenitori, come illustrato nella figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-343">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![Macchina virtuale con diversi contenitori Docker](./media/docker-app-development-workflow/vm-with-docker-containers-deployed.png)

<span data-ttu-id="b0b9d-345">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-345">**Figure 5-10**.</span></span> <span data-ttu-id="b0b9d-346">VM con contenitori Docker distribuiti</span><span class="sxs-lookup"><span data-stu-id="b0b9d-346">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="b0b9d-347">Con l'interfaccia della riga di comando di Docker</span><span class="sxs-lookup"><span data-stu-id="b0b9d-347">Using Docker CLI</span></span>

<span data-ttu-id="b0b9d-348">Per eseguire un'applicazione a più contenitori con l'interfaccia della riga di comando di Docker, si usa il comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-348">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="b0b9d-349">Questo comando usa il file **docker-compose.yml** disponibile a livello di soluzione per distribuire un'applicazione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-349">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="b0b9d-350">La figura 5-11 illustra i risultati che si ottengono quando si esegue il comando dalla directory principale della soluzione, che contiene il file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-350">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![Schermata visualizzata quando si esegue il comando docker-compose up](./media/docker-app-development-workflow/results-docker-compose-up.png)

<span data-ttu-id="b0b9d-352">**Figura 5-11**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-352">**Figure 5-11**.</span></span> <span data-ttu-id="b0b9d-353">Esempio di risultati ottenuti eseguendo il comando docker-compose up</span><span class="sxs-lookup"><span data-stu-id="b0b9d-353">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="b0b9d-354">Dopo l'esecuzione del comando docker-compose up, l'applicazione e i contenitori correlati vengono distribuiti nell'host Docker, come illustra la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-354">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="b0b9d-355">Con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-355">Using Visual Studio</span></span>

<span data-ttu-id="b0b9d-356">L'esecuzione di un'applicazione multicontenitore con Visual Studio 2019 non è possibile ottenere alcun più semplice.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-356">Running a multi-container application using Visual Studio 2019 can't get any simpler.</span></span> <span data-ttu-id="b0b9d-357">Basta premere **CTRL+F5** per l'esecuzione o **F5** per il debug, come di consueto, impostando il progetto **docker-compose** come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-357">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="b0b9d-358">Visual Studio gestisce tutte le impostazioni necessarie, in modo da poter creare punti di interruzione come al solito ed eseguire il debug di quelli che diventano finalmente processi indipendenti in esecuzione in "server remoti", con il debugger già collegato, proprio così.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-358">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", with the debugger already attached, just like that.</span></span>

<span data-ttu-id="b0b9d-359">Come accennato in precedenza, ogni volta che si aggiungere il supporto Docker a un progetto all'interno di una soluzione, il progetto è configurato nel file docker-compose.yml globale, a livello di soluzione, che consente di eseguire l'intera soluzione o di eseguirne il debug in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-359">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="b0b9d-360">Visual Studio avvia un solo contenitore per ogni progetto che ha il supporto Docker abilitato ed esegue automaticamente tutti i passaggi interni, ovvero pubblicazione dotnet, compilazione docker, ecc.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-360">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="b0b9d-361">Per avere un'idea di tutta la complessità, esaminare il file:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-361">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="b0b9d-362">Il punto importante è che, come illustrato nella figura 5-12, in Visual Studio 2019 è disponibile un comando **Docker** aggiuntivo per l'azione del tasto F5.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-362">The important point here is that, as shown in Figure 5-12, in Visual Studio 2019 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="b0b9d-363">Questa opzione consente di eseguire un'applicazione a più contenitori o di eseguirne il debug eseguendo tutti i contenitori definiti nei file docker-compose.yml a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-363">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="b0b9d-364">Grazie alla capacità di eseguire il debug delle soluzioni a più contenitori, è possibile impostare più punti di interruzione, ciascuno in un progetto (contenitore) diverso, e durante il debug da Visual Studio l'esecuzione viene arrestata in corrispondenza dei punti di interruzione definiti in progetti diversi ed eseguiti in contenitori diversi.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-364">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Screenshot della barra degli strumenti di debug che esegue un progetto docker-compose.](./media/docker-app-development-workflow/debug-toolbar-docker-compose-project.png)

<span data-ttu-id="b0b9d-366">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-366">**Figure 5-12**.</span></span> <span data-ttu-id="b0b9d-367">Esecuzione di app multi-contenitore in Visual Studio 2019Running multi-container apps in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b0b9d-367">Running multi-container apps in Visual Studio 2019</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b0b9d-368">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0b9d-368">Additional resources</span></span>

- <span data-ttu-id="b0b9d-369">**Distribuire un contenitore di ASP.NET a un host Docker remotoDeploy an ASP.NET container to a remote Docker host** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-369">**Deploy an ASP.NET container to a remote Docker host** </span></span>\
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="b0b9d-370">Una nota sul test e la distribuzione con agenti di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="b0b9d-370">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="b0b9d-371">I comandi docker-compose up e docker run, o l'esecuzione e il debug dei contenitori in Visual Studio, sono adeguati per eseguire test sui contenitori nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-371">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="b0b9d-372">È consigliabile non usare questo approccio per le distribuzioni di produzione, in cui la destinazione deve essere un agente di orchestrazione, ad esempio [Kubernetes](https://kubernetes.io/) o [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-372">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="b0b9d-373">Se si utilizzaKubernetes, è necessario utilizzare [i pod](https://kubernetes.io/docs/concepts/workloads/pods/pod/) per organizzare i contenitori e i [servizi](https://kubernetes.io/docs/concepts/services-networking/service/) per metterli in rete.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-373">If you're using Kubernetes, you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="b0b9d-374">Si usano anche le [distribuzioni](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) per organizzare la creazione e la modifica dei pod.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-374">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![Immagine per il passaggio 6.](./media/docker-app-development-workflow/step-6-test-app-microservices.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="b0b9d-376">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-376">Step 6.</span></span> <span data-ttu-id="b0b9d-377">Testare l'applicazione Docker usando l'host Docker locale</span><span class="sxs-lookup"><span data-stu-id="b0b9d-377">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="b0b9d-378">Questo passaggio varia in base a ciò che l'applicazione sta facendo.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-378">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="b0b9d-379">In un'applicazione Web .NET Core semplice che viene distribuita come contenitore o servizio singolo è possibile accedere al servizio aprendo un browser nell'host Docker e passando a quel sito, come illustrato nella figura 5-13.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-379">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="b0b9d-380">Se la configurazione nel Dockerfile abbina il contenitore a una porta dell'host diversa dalla 80, includere la porta host nell'URL.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-380">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Screenshot della risposta da localhost/API/values.](./media/docker-app-development-workflow/test-docker-app-locally-localhost.png)

<span data-ttu-id="b0b9d-382">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-382">**Figure 5-13**.</span></span> <span data-ttu-id="b0b9d-383">Esempio di test dell'applicazione Docker in locale mediante localhost</span><span class="sxs-lookup"><span data-stu-id="b0b9d-383">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="b0b9d-384">Se localhost non punta all'IP dell'host Docker, come accade per impostazione predefinita quando si usa Docker CE, per passare al servizio usare l'indirizzo IP della scheda di rete del computer.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-384">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="b0b9d-385">Si noti che questo URL nel browser usa la porta 80 per lo specifico contenitore di esempio di cui si tratta.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-385">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="b0b9d-386">Tuttavia internamente le richieste vengono reindirizzate alla porta 5000 perché è stato distribuito in questo modo con il comando docker run, come illustrato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-386">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="b0b9d-387">È anche possibile testare l'applicazione usando curl dal terminale, come illustrato nella figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-387">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="b0b9d-388">In un'installazione di Docker in Windows, il valore IP dell'host Docker predefinito è sempre 10.0.75.1 in aggiunta all'indirizzo IP effettivo del computer.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-388">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![Uscita della console http://10.0.75.1/API/values da ottenere il con ricciolo.](./media/docker-app-development-workflow/test-docker-app-locally-curl.png)

<span data-ttu-id="b0b9d-390">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-390">**Figure 5-14**.</span></span> <span data-ttu-id="b0b9d-391">Esempio di test dell'applicazione Docker in locale mediante curl</span><span class="sxs-lookup"><span data-stu-id="b0b9d-391">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2019"></a><span data-ttu-id="b0b9d-392">Test e debug di contenitori con Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="b0b9d-392">Testing and debugging containers with Visual Studio 2019</span></span>

<span data-ttu-id="b0b9d-393">Quando si eseguono e debug i contenitori con Visual Studio 2019, è possibile eseguire il debug dell'applicazione .NET in modo molto simile a quello che si esegue quando si esegue senza contenitori.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-393">When running and debugging the containers with Visual Studio 2019, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="b0b9d-394">Test e debug senza Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-394">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="b0b9d-395">Se si sta sviluppando usando l'approccio editor/CLI, il debug dei contenitori è più difficile e probabilmente vorrai eseguire il debug generando tracce.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-395">If you're developing using the editor/CLI approach, debugging containers is more difficult and you'll probably want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b0b9d-396">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0b9d-396">Additional resources</span></span>

- <span data-ttu-id="b0b9d-397">**Debug di app in un contenitore Docker localeDebugging apps in a local Docker container** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-397">**Debugging apps in a local Docker container** </span></span>\
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- <span data-ttu-id="b0b9d-398">**Steve Lasker. Compilare, eseguire il debug, distribuire ASP.NET applicazioni principali con Docker.Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span><span class="sxs-lookup"><span data-stu-id="b0b9d-398">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="b0b9d-399">Video.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-399">Video.</span></span> \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="b0b9d-400">Flusso di lavoro semplificato per lo sviluppo di contenitori con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-400">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="b0b9d-401">Il flusso di lavoro quando si usa Visual Studio è molto più semplice rispetto all'uso dell'approccio editor/CLI.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-401">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="b0b9d-402">La maggior parte dei passaggi richiesti da Docker correlati ai file Dockerfile e docker-compose.yml sono nascosti o semplificati da Visual Studio, come illustrato nella figura 5-15.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-402">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

:::image type="complex" source="./media/docker-app-development-workflow/simplified-life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramma che mostra i cinque passaggi semplificati necessari per creare un'app.":::
<span data-ttu-id="b0b9d-404">Il processo di sviluppo per le app Docker: 1 - Codificare l'app, 2 - Scrivere Dockerfile/s, 3 - Creare immagini definite in Dockerfile/s, 4 - (facoltativo) Componi servizi nel file docker-compose.yml, 5 - Esegui app contenitore o docker-compose, 6 - Testl'app o microservizi, 7 - Push per ripetere e ripetere.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-404">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span>
:::image-end:::

<span data-ttu-id="b0b9d-405">**Figura 5-15**.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-405">**Figure 5-15**.</span></span> <span data-ttu-id="b0b9d-406">Flusso di lavoro semplificato per lo sviluppo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b0b9d-406">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="b0b9d-407">Inoltre è sufficiente eseguire una sola volta il passaggio 2, ovvero l'aggiunta del supporto Docker ai progetti.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-407">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="b0b9d-408">Pertanto il flusso di lavoro è simile alle attività di sviluppo normale quando si usa .NET per qualsiasi altro tipo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-408">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="b0b9d-409">È necessario sapere cosa succede dietro le quinte, ad esempio il processo di creazione delle immagini, le immagini di base in uso, la distribuzione dei contenitori e così via. In alcuni casi è anche necessario modificare il Dockerfile o il file docker-compose.yml per personalizzare i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-409">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="b0b9d-410">Se si usa Visual Studio la maggior parte del lavoro viene notevolmente semplificata e la produttività è maggiore.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-410">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="b0b9d-411">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0b9d-411">Additional resources</span></span>

- <span data-ttu-id="b0b9d-412">**Steve Lasker. Sviluppo di .NET Docker con Visual Studio (2017)** </span><span class="sxs-lookup"><span data-stu-id="b0b9d-412">**Steve Lasker. .NET Docker Development with Visual Studio (2017)** </span></span>\
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="b0b9d-413">Uso dei comandi di PowerShell in un Dockerfile per configurare contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="b0b9d-413">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span>

<span data-ttu-id="b0b9d-414">I [contenitori Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index) consentono di convertire applicazioni Windows esistenti in immagini Docker e distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-414">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="b0b9d-415">Per usare i contenitori Windows si eseguono i comandi di PowerShell in Dockerfile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-415">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM mcr.microsoft.com/windows/servercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="b0b9d-416">In questo caso si usa un'immagine di base di Windows Server Core (impostazione FROM) e si installa IIS con un comando di PowerShell (impostazione RUN).</span><span class="sxs-lookup"><span data-stu-id="b0b9d-416">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="b0b9d-417">In modo analogo è possibile usare i comandi di PowerShell anche per configurare componenti aggiuntivi come ASP.NET 4. x, .NET 4.6 o qualsiasi altro software Windows.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-417">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="b0b9d-418">Ad esempio il comando seguente in un Dockerfile configura ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="b0b9d-418">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="b0b9d-419">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b0b9d-419">Additional resources</span></span>

- <span data-ttu-id="b0b9d-420">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="b0b9d-420">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="b0b9d-421">Esempi di comandi di PowerShell eseguibili da Dockerfile per includere funzionalità di Windows.</span><span class="sxs-lookup"><span data-stu-id="b0b9d-421">Example PowerShell commands to run from dockerfiles to include Windows features.</span></span>\
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
><span data-ttu-id="b0b9d-422">[Successivo](index.md)
>[precedente](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="b0b9d-422">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
