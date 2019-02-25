---
title: Flusso di lavoro di sviluppo per app Docker
description: Informazioni dettagliate sul flusso di lavoro richiesto per lo sviluppo delle applicazioni basate su Docker. Iniziare gradualmente e approfondire alcuni dettagli per ottimizzare i Dockerfile e terminare con il flusso di lavoro semplificato disponibile quando si usa Visual Studio.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: c34d49307408520afc6223a43d1c347dd6cffb97
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584304"
---
# <a name="development-workflow-for-docker-apps"></a><span data-ttu-id="0718c-104">Flusso di lavoro di sviluppo per app Docker</span><span class="sxs-lookup"><span data-stu-id="0718c-104">Development workflow for Docker apps</span></span>

<span data-ttu-id="0718c-105">Il ciclo di vita dello sviluppo applicativo inizia nel computer dello sviluppatore, che qui scrive l'applicazione usando il linguaggio preferito ed esegue i relativi test in locale.</span><span class="sxs-lookup"><span data-stu-id="0718c-105">The application development life cycle starts at your computer, as a developer, where you code the application using your preferred language and test it locally.</span></span> <span data-ttu-id="0718c-106">Con questo flusso di lavoro, indipendentemente dal linguaggio, dal framework e dalla piattaforma scelti, si sviluppano e testano sempre contenitori Docker, ma a livello locale.</span><span class="sxs-lookup"><span data-stu-id="0718c-106">With this workflow, no matter which language, framework, and platform you choose, you're always developing and testing Docker containers, but doing so locally.</span></span>

<span data-ttu-id="0718c-107">Ogni contenitore, ovvero un'istanza di un'immagine Docker, include i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0718c-107">Each container (an instance of a Docker image) includes the following components:</span></span>

- <span data-ttu-id="0718c-108">Un sistema operativo a scelta, ad esempio una distribuzione Linux, Windows Nano Server o Windows Server Core.</span><span class="sxs-lookup"><span data-stu-id="0718c-108">An operating system selection, for example, a Linux distribution, Windows Nano Server, or Windows Server Core.</span></span>

- <span data-ttu-id="0718c-109">I file aggiunti durante lo sviluppo, ad esempio, il codice sorgente e i file binari dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0718c-109">Files added during development, for example, source code and application binaries.</span></span>

- <span data-ttu-id="0718c-110">Informazioni di configurazione, ad esempio impostazioni di ambiente e dipendenze.</span><span class="sxs-lookup"><span data-stu-id="0718c-110">Configuration information, such as environment settings and dependencies.</span></span>

## <a name="workflow-for-developing-docker-container-based-applications"></a><span data-ttu-id="0718c-111">Flusso di lavoro per lo sviluppo di applicazioni Docker basate su contenitore</span><span class="sxs-lookup"><span data-stu-id="0718c-111">Workflow for developing Docker container-based applications</span></span>

<span data-ttu-id="0718c-112">Questa sezione descrive il flusso di lavoro di sviluppo a *ciclo interno* per applicazioni Docker basate su contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-112">This section describes the *inner-loop* development workflow for Docker container-based applications.</span></span> <span data-ttu-id="0718c-113">Flusso di lavoro a ciclo interno significa che non tiene conto del flusso di lavoro DevOps più ampio, che può arrivare fino alla distribuzione di produzione, e si concentra solo sul lavoro di sviluppo eseguito sul computer dello sviluppatore.</span><span class="sxs-lookup"><span data-stu-id="0718c-113">The inner-loop workflow means it's not considering the broader DevOps workflow, that can include up to production deployment, and just focuses on the development work done on the developer's computer.</span></span> <span data-ttu-id="0718c-114">I passaggi iniziali per configurare l'ambiente non sono inclusi, poiché vengono eseguiti una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0718c-114">The initial steps to set up the environment aren't included, since those steps are done only once.</span></span>

<span data-ttu-id="0718c-115">Un'applicazione è costituita da servizi e raccolte aggiuntive, ossia dipendenze.</span><span class="sxs-lookup"><span data-stu-id="0718c-115">An application is composed of your own services plus additional libraries (dependencies).</span></span> <span data-ttu-id="0718c-116">Di seguito sono indicati i passaggi di base che si eseguono in genere quando si compila un'applicazione Docker, come illustrato nella figura 5-1.</span><span class="sxs-lookup"><span data-stu-id="0718c-116">The following are the basic steps you usually take when building a Docker application, as illustrated in Figure 5-1.</span></span>

![<span data-ttu-id="0718c-117">Il processo di sviluppo per le applicazioni Docker: 1 - Scrivere il codice dell'app, 2 - Scrivere i Dockerfile, 3 - Creare immagini definite nei Dockerfile, 4 - (facoltativo) Comporre i servizi nel file docker-compose.yml, 5 - Eseguire l'app contenitore o docker-compose, 6: Testare l'app o i microservizi, 7 - Eseguire il push al repository e ripetere.</span><span class="sxs-lookup"><span data-stu-id="0718c-117">The development process for Docker apps: 1 - Code your App, 2 - Write Dockerfile/s, 3 - Create images defined at Dockerfile/s, 4 - (optional) Compose services in the docker-compose.yml file, 5 - Run container or docker-compose app, 6 - Test your app or microservices, 7 - Push to repo and repeat.</span></span> ](./media/image1.png)

<span data-ttu-id="0718c-118">**Figura 5-1.**</span><span class="sxs-lookup"><span data-stu-id="0718c-118">**Figure 5-1.**</span></span> <span data-ttu-id="0718c-119">Flusso di lavoro passo per passo per lo sviluppo di applicazioni Docker in contenitori</span><span class="sxs-lookup"><span data-stu-id="0718c-119">Step-by-step workflow for developing Docker containerized apps</span></span>

<span data-ttu-id="0718c-120">Questa sezione descrive nei dettagli l'intero processo e ogni passaggio principale è spiegato con riferimento all'ambiente Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0718c-120">In this section, this whole process is detailed and every major step is explained by focusing on a Visual Studio environment.</span></span>

<span data-ttu-id="0718c-121">Quando si usa un approccio di sviluppo editor/CLI, ad esempio codice Visual Studio e CLI di Docker in macOS o Windows, di solito è necessario conoscere ogni passaggio in modo più dettagliato rispetto all'uso di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0718c-121">When you're using an editor/CLI development approach (for example, Visual Studio Code plus Docker CLI on macOS or Windows), you need to know every step, generally in more detail than if you're using Visual Studio.</span></span> <span data-ttu-id="0718c-122">Per altre informazioni sull'uso di un ambiente CLI, vedere l'e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo di vita di un'applicazione Docker in un contenitore con piattaforme e strumenti Microsoft).</span><span class="sxs-lookup"><span data-stu-id="0718c-122">For more information about working in a CLI environment, see the e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/).</span></span>

<span data-ttu-id="0718c-123">Se si usa Visual Studio 2017, molti passaggi sono gestiti automaticamente e questo migliora notevolmente la produttività.</span><span class="sxs-lookup"><span data-stu-id="0718c-123">When you're using Visual Studio 2017, many of those steps are handled for you, which dramatically improves your productivity.</span></span> <span data-ttu-id="0718c-124">Ciò vale soprattutto quando si usa Visual Studio 2017 con applicazioni a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="0718c-124">This is especially true when you're using Visual Studio 2017 and targeting multi-container applications.</span></span> <span data-ttu-id="0718c-125">Ad esempio, con un solo clic, Visual Studio aggiunge ai progetti il Dockerfile e il file docker-compose.yml con la configurazione per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0718c-125">For instance, with just one mouse click, Visual Studio adds the Dockerfile and docker-compose.yml file to your projects with the configuration for your application.</span></span> <span data-ttu-id="0718c-126">Quando si esegue l'applicazione in Visual Studio, viene creata l'immagine Docker e l'applicazione a più contenitori viene eseguita direttamente in Docker; è anche possibile eseguire il debug di diversi contenitori contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="0718c-126">When you run the application in Visual Studio, it builds the Docker image and runs the multi-container application directly in Docker; it even allows you to debug several containers at once.</span></span> <span data-ttu-id="0718c-127">Queste funzionalità rendono lo sviluppo più veloce.</span><span class="sxs-lookup"><span data-stu-id="0718c-127">These features will boost your development speed.</span></span>

<span data-ttu-id="0718c-128">Tuttavia, anche se Visual Studio automatizza questi passaggi, ciò non significa che non sia necessario sapere cosa succede dietro le quinte con Docker.</span><span class="sxs-lookup"><span data-stu-id="0718c-128">However, just because Visual Studio makes those steps automatic doesn't mean that you don't need to know what's going on underneath with Docker.</span></span> <span data-ttu-id="0718c-129">Di conseguenza, il materiale sussidiario seguente illustra in dettaglio ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="0718c-129">Therefore, the following guidance details every step.</span></span>

![1- Scrivere il codice dell'app](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a><span data-ttu-id="0718c-131">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="0718c-131">Step 1.</span></span> <span data-ttu-id="0718c-132">Iniziare a scrivere il codice e ad abbozzare l'applicazione o il servizio</span><span class="sxs-lookup"><span data-stu-id="0718c-132">Start coding and create your initial application or service baseline</span></span>

<span data-ttu-id="0718c-133">Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza Docker.</span><span class="sxs-lookup"><span data-stu-id="0718c-133">Developing a Docker application is similar to the way you develop an application without Docker.</span></span> <span data-ttu-id="0718c-134">La differenza è che, quando si sviluppa per Docker, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale (una macchina virtuale Linux configurata da Docker o direttamente Windows se si usano i contenitori Windows).</span><span class="sxs-lookup"><span data-stu-id="0718c-134">The difference is that while developing for Docker, you're deploying and testing your application or services running within Docker containers in your local environment (either a Linux VM setup by Docker or directly Windows if using Windows Containers).</span></span>

### <a name="set-up-your-local-environment-with-visual-studio"></a><span data-ttu-id="0718c-135">Configurare l'ambiente locale con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0718c-135">Set up your local environment with Visual Studio</span></span>

<span data-ttu-id="0718c-136">Per iniziare, accertarsi che sia installato [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) per Windows, come spiegato nelle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0718c-136">To begin, make sure you have [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) for Windows installed, as explained in the following instructions:</span></span>

[<span data-ttu-id="0718c-137">Introduzione a Docker CE per Windows</span><span class="sxs-lookup"><span data-stu-id="0718c-137">Get started with Docker CE for Windows</span></span>](https://docs.docker.com/docker-for-windows/)

<span data-ttu-id="0718c-138">Inoltre, è necessario Visual Studio 2017 versione 15.7 o successive con il carico di lavoro **Sviluppo multipiattaforma .NET Core** installato, come illustra la figura 5-2.</span><span class="sxs-lookup"><span data-stu-id="0718c-138">In addition, you need Visual Studio 2017 version 15.7 or later, with the **.NET Core cross-platform development** workload installed, as shown in Figure 5-2.</span></span>

![Selezione del carico di lavoro Sviluppo multipiattaforma .NET Core durante l'installazione di Visual Studio.](./media/image3.png)

<span data-ttu-id="0718c-140">**Figura 5-2**.</span><span class="sxs-lookup"><span data-stu-id="0718c-140">**Figure 5-2**.</span></span> <span data-ttu-id="0718c-141">Selezione del carico di lavoro **Sviluppo multipiattaforma .NET Core** durante l'installazione di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0718c-141">Selecting the **.NET Core cross-platform development** workload during Visual Studio 2017 setup</span></span>

<span data-ttu-id="0718c-142">È possibile iniziare a scrivere il codice dell'applicazione in .NET normale, di solito in .NET Core se si prevede di usare contenitori, anche prima di attivare Docker nell'applicazione e di eseguire la distribuzione e i test in Docker,</span><span class="sxs-lookup"><span data-stu-id="0718c-142">You can start coding your application in plain .NET (usually in .NET Core if you're planning to use containers) even before enabling Docker in your application and deploying and testing in Docker.</span></span> <span data-ttu-id="0718c-143">ma si consiglia di iniziare a lavorare in Docker appena possibile, perché quello sarà l'ambiente reale e gli eventuali problemi possono essere individuati velocemente.</span><span class="sxs-lookup"><span data-stu-id="0718c-143">However, it is recommended that you start working on Docker as soon as possible, because that will be the real environment and any issues can be discovered as soon as possible.</span></span> <span data-ttu-id="0718c-144">Si consiglia di procedere in questo modo perché Visual Studio facilita così tanto il lavoro con Docker da diventare quasi trasparente, soprattutto quando lo si usa per eseguire il debug di applicazioni a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="0718c-144">This is encouraged because Visual Studio makes it so easy to work with Docker that it almost feels transparent—the best example when debugging multi-container applications from Visual Studio.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0718c-145">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0718c-145">Additional resources</span></span>

- <span data-ttu-id="0718c-146">**Introduzione a Docker CE per Windows** \\</span><span class="sxs-lookup"><span data-stu-id="0718c-146">**Get started with Docker CE for Windows** \\</span></span>
  [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

- <span data-ttu-id="0718c-147">**Visual Studio 2017** \\</span><span class="sxs-lookup"><span data-stu-id="0718c-147">**Visual Studio 2017** \\</span></span>
  [*https://visualstudio.microsoft.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![2 - Scrivere i Dockerfile](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a><span data-ttu-id="0718c-149">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="0718c-149">Step 2.</span></span> <span data-ttu-id="0718c-150">Creare un Dockerfile correlato a un'immagine di base .NET esistente</span><span class="sxs-lookup"><span data-stu-id="0718c-150">Create a Dockerfile related to an existing .NET base image</span></span>

<span data-ttu-id="0718c-151">È necessario un Dockerfile per ogni immagine personalizzata che si desidera creare; è necessario un Dockerfile per ogni contenitore da distribuire, sia che si esegua la distribuzione automaticamente da Visual Studio o manualmente con la CLI di Docker: comandi docker run e docker-compose.</span><span class="sxs-lookup"><span data-stu-id="0718c-151">You need a Dockerfile for each custom image you want to build; you also need a Dockerfile for each container to be deployed, whether you deploy automatically from Visual Studio or manually using the Docker CLI (docker run and docker-compose commands).</span></span> <span data-ttu-id="0718c-152">Se l'applicazione contiene un solo servizio personalizzato, è necessario un solo Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="0718c-152">If your application contains a single custom service, you need a single Dockerfile.</span></span> <span data-ttu-id="0718c-153">Se l'applicazione contiene più servizi, come in un'architettura a microservizi, è necessario un Dockerfile per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="0718c-153">If your application contains multiple services (as in a microservices architecture), you need one Dockerfile for each service.</span></span>

<span data-ttu-id="0718c-154">Il Dockerfile viene inserito nella cartella radice dell'applicazione o del servizio.</span><span class="sxs-lookup"><span data-stu-id="0718c-154">The Dockerfile is placed in the root folder of your application or service.</span></span> <span data-ttu-id="0718c-155">Contiene i comandi che indicano a Docker come configurare ed eseguire l'applicazione o il servizio in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-155">It contains the commands that tell Docker how to set up and run your application or service in a container.</span></span> <span data-ttu-id="0718c-156">È possibile creare manualmente un Dockerfile nel codice e aggiungerlo al progetto insieme alle dipendenze .NET.</span><span class="sxs-lookup"><span data-stu-id="0718c-156">You can manually create a Dockerfile in code and add it to your project along with your .NET dependencies.</span></span>

<span data-ttu-id="0718c-157">Con Visual Studio e i relativi strumenti per Docker questa attività richiede solo pochi clic del mouse.</span><span class="sxs-lookup"><span data-stu-id="0718c-157">With Visual Studio and its tools for Docker, this task requires only a few mouse clicks.</span></span> <span data-ttu-id="0718c-158">Quando si crea un nuovo progetto in Visual Studio 2017, è disponibile un'opzione denominata **Abilita supporto Docker**, come illustrato nella figura 5-3.</span><span class="sxs-lookup"><span data-stu-id="0718c-158">When you create a new project in Visual Studio 2017, there's an option named **Enable Container (Docker) Support**, as shown in Figure 5-3.</span></span>

![Casella di controllo Abilita supporto Docker quando si crea un nuovo progetto ASP.NET Core in Visual Studio 2017](./media/image5.png)

<span data-ttu-id="0718c-160">**Figura 5-3**.</span><span class="sxs-lookup"><span data-stu-id="0718c-160">**Figure 5-3**.</span></span> <span data-ttu-id="0718c-161">Abilitazione del supporto Docker quando si crea un nuovo progetto ASP.NET Core in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0718c-161">Enabling Docker Support when creating a new ASP.NET Core project in Visual Studio 2017</span></span>

<span data-ttu-id="0718c-162">È anche possibile abilitare il supporto Docker in un progetto di app Web ASP.NET Core esistente facendo clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionando **Aggiungi** > **Supporto Docker**, come illustrato nella figura 5-4.</span><span class="sxs-lookup"><span data-stu-id="0718c-162">You can also enable Docker support on an existing ASP.NET Core web app project by right-clicking the project in **Solution Explorer** and selecting **Add** > **Docker Support**, as shown in Figure 5-4.</span></span>

![Opzione di menu Supporto Docker in Visual Studio](./media/image6.png)

<span data-ttu-id="0718c-164">**Figura 5-4**.</span><span class="sxs-lookup"><span data-stu-id="0718c-164">**Figure 5-4**.</span></span> <span data-ttu-id="0718c-165">Abilitazione del supporto Docker in un progetto Visual Studio 2017 esistente</span><span class="sxs-lookup"><span data-stu-id="0718c-165">Enabling Docker support in an existing Visual Studio 2017 project</span></span>

<span data-ttu-id="0718c-166">Questa azione aggiunge un *Dockerfile* al progetto con la configurazione richiesta ed è disponibile solo nei progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0718c-166">This action adds a *Dockerfile* to the project with the required configuration, and is only available on ASP.NET Core projects.</span></span>

<span data-ttu-id="0718c-167">In modo analogo, Visual Studio può anche aggiungere un file docker-compose.yml per l'intera soluzione con l'opzione di **aggiunta del supporto dell'agente di orchestrazione dei contenitori**.</span><span class="sxs-lookup"><span data-stu-id="0718c-167">In a similar fashion, Visual Studio can also add a docker-compose.yml file for the whole solution with the option **Add > Container Orchestrator Support**.</span></span> <span data-ttu-id="0718c-168">Nel passaggio 4 questa opzione verrà esaminata in modo più dettagliato.</span><span class="sxs-lookup"><span data-stu-id="0718c-168">In step 4, we'll explore this option in greater detail.</span></span>

### <a name="using-an-existing-official-net-docker-image"></a><span data-ttu-id="0718c-169">Uso di un'immagine Docker .NET ufficiale esistente</span><span class="sxs-lookup"><span data-stu-id="0718c-169">Using an existing official .NET Docker image</span></span>

<span data-ttu-id="0718c-170">In genere per il contenitore si crea un'immagine personalizzata sopra un'immagine di base che è possibile ottenere da un repository ufficiale come il registro [Hub Docker](https://hub.docker.com/).</span><span class="sxs-lookup"><span data-stu-id="0718c-170">You usually build a custom image for your container on top of a base image you get from an official repository like the [Docker Hub](https://hub.docker.com/) registry.</span></span> <span data-ttu-id="0718c-171">Questo è esattamente ciò che accade dietro le quinte quando si attiva il supporto Docker in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0718c-171">That is precisely what happens under the covers when you enable Docker support in Visual Studio.</span></span> <span data-ttu-id="0718c-172">Il Dockerfile userà un'immagine `aspnetcore` esistente.</span><span class="sxs-lookup"><span data-stu-id="0718c-172">Your Dockerfile will use an existing `aspnetcore` image.</span></span>

<span data-ttu-id="0718c-173">In precedenza si è visto le immagini e repository Docker da usare in base al framework e al sistema operativo scelto.</span><span class="sxs-lookup"><span data-stu-id="0718c-173">Earlier we explained which Docker images and repos you can use, depending on the framework and OS you have chosen.</span></span> <span data-ttu-id="0718c-174">Ad esempio, se si usa ASP.NET Core (Linux o Windows), l'immagine da usare è `microsoft/dotnet:2.2-aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="0718c-174">For instance, if you want to use ASP.NET Core (Linux or Windows), the image to use is `microsoft/dotnet:2.2-aspnetcore-runtime`.</span></span> <span data-ttu-id="0718c-175">Pertanto è sufficiente specificare l'immagine Docker di base che sarà usata per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-175">Therefore, you just need to specify what base Docker image you will use for your container.</span></span> <span data-ttu-id="0718c-176">A tale scopo, aggiungere `FROM microsoft/dotnet:2.2-aspnetcore-runtime` al Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="0718c-176">You do that by adding `FROM microsoft/dotnet:2.2-aspnetcore-runtime` to your Dockerfile.</span></span> <span data-ttu-id="0718c-177">Visual Studio esegue l'operazione automaticamente, ma se si aggiornasse la versione, verrebbe aggiornato anche questo valore.</span><span class="sxs-lookup"><span data-stu-id="0718c-177">This will be automatically performed by Visual Studio, but if you were to update the version, you update this value.</span></span>

<span data-ttu-id="0718c-178">L'uso di un repository ufficiale di immagini .NET di Docker Hub con un numero di versione garantisce che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.</span><span class="sxs-lookup"><span data-stu-id="0718c-178">Using an official .NET image repository from Docker Hub with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="0718c-179">L'esempio seguente illustra un esempio di Dockerfile per un contenitore ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="0718c-179">The following example shows a sample Dockerfile for an ASP.NET Core container.</span></span>

```Dockerfile
FROM microsoft/dotnet:2.2-aspnetcore-runtime
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

<span data-ttu-id="0718c-180">In questo caso l'immagine si basa sulla versione 2.2 dell'immagine Docker ufficiale di ASP.NET Core (multiarchitettura per Linux e Windows).</span><span class="sxs-lookup"><span data-stu-id="0718c-180">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows).</span></span> <span data-ttu-id="0718c-181">Si tratta dell'impostazione `FROM microsoft/dotnet:2.2-aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="0718c-181">This is the setting `FROM microsoft/dotnet:2.2-aspnetcore-runtime`.</span></span> <span data-ttu-id="0718c-182">Per altre informazioni su questa immagine di base, vedere la pagina [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) (Immagine .NET Core Docker). Nel Dockerfile è necessario anche indicare al Docker di rimanere in ascolto sulla porta TCP che sarà usata in fase di esecuzione, in questo caso la porta 80 configurata con l'impostazione EXPOSE.</span><span class="sxs-lookup"><span data-stu-id="0718c-182">(For more information about this base image, see the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page.) In the Dockerfile, you also need to instruct Docker to listen on the TCP port you will use at runtime (in this case, port 80, as configured with the EXPOSE setting).</span></span>

<span data-ttu-id="0718c-183">Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso.</span><span class="sxs-lookup"><span data-stu-id="0718c-183">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="0718c-184">Ad esempio, la riga ENTRYPOINT con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker di eseguire un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0718c-184">For instance, the ENTRYPOINT line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="0718c-185">Se si usa l'SDK e l'interfaccia della riga di comando di .NET Core, ovvero l'interfaccia della riga di comando dotnet, per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa.</span><span class="sxs-lookup"><span data-stu-id="0718c-185">If you're using the SDK and the .NET Core CLI (dotnet CLI) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="0718c-186">In sostanza la riga ENTRYPOINT e altre impostazioni saranno diverse a seconda del linguaggio e della piattaforma scelti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0718c-186">The bottom line is that the ENTRYPOINT line and other settings will be different depending on the language and platform you choose for your application.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0718c-187">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0718c-187">Additional resources</span></span>

- <span data-ttu-id="0718c-188">**Compilazione di immagini Docker per applicazioni .NET Core** \\</span><span class="sxs-lookup"><span data-stu-id="0718c-188">**Building Docker Images for .NET Core Applications** \\</span></span>
  [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

- <span data-ttu-id="0718c-189">**Creare un'immagine**.</span><span class="sxs-lookup"><span data-stu-id="0718c-189">**Build your own image**.</span></span> <span data-ttu-id="0718c-190">Nella documentazione ufficiale di Docker.\\</span><span class="sxs-lookup"><span data-stu-id="0718c-190">In the official Docker documentation.\\</span></span>
  [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

- <span data-ttu-id="0718c-191">**Staying up-to-date with .NET Container Images** \ (Rimanere aggiornati con le immagini del contenitore .NET)</span><span class="sxs-lookup"><span data-stu-id="0718c-191">**Staying up-to-date with .NET Container Images** \\</span></span>
  [*https://blogs.msdn.microsoft.com/dotnet/2018/06/18/staying-up-to-date-with-net-container-images/*](https://blogs.msdn.microsoft.com/dotnet/2018/06/18/staying-up-to-date-with-net-container-images/)

- <span data-ttu-id="0718c-192">**Using .NET and Docker Together - DockerCon 2018 Update** \ (Uso combinato di .NET e Docker - Aggiornamento DockerCon 2018)</span><span class="sxs-lookup"><span data-stu-id="0718c-192">**Using .NET and Docker Together - DockerCon 2018 Update** \\</span></span>
  [*https://blogs.msdn.microsoft.com/dotnet/2018/06/13/using-net-and-docker-together-dockercon-2018-update/*](https://blogs.msdn.microsoft.com/dotnet/2018/06/13/using-net-and-docker-together-dockercon-2018-update/)

### <a name="using-multi-arch-image-repositories"></a><span data-ttu-id="0718c-193">Uso di repository di immagini multi-arch</span><span class="sxs-lookup"><span data-stu-id="0718c-193">Using multi-arch image repositories</span></span>

<span data-ttu-id="0718c-194">Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows.</span><span class="sxs-lookup"><span data-stu-id="0718c-194">A single repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="0718c-195">Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="0718c-195">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is Linux and Windows).</span></span> <span data-ttu-id="0718c-196">Ad esempio, il repository [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) disponibile nel registro Docker Hub fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di repository.</span><span class="sxs-lookup"><span data-stu-id="0718c-196">For example, the [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same repo name.</span></span>

<span data-ttu-id="0718c-197">Se si specifica un tag, ci si rivolge a una piattaforma esplicita come nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0718c-197">If you specify a tag, targeting a platform that is explicit like in the following cases:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  <span data-ttu-id="0718c-198">Destinazioni: solo runtime .NET Core 2.2 in Linux</span><span class="sxs-lookup"><span data-stu-id="0718c-198">Targets: .NET Core 2.2 runtime-only on Linux</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  <span data-ttu-id="0718c-199">Destinazioni: solo runtime .NET Core 2.2 in Windows Nano Server</span><span class="sxs-lookup"><span data-stu-id="0718c-199">Targets: .NET Core 2.2 runtime-only on Windows Nano Server</span></span>

<span data-ttu-id="0718c-200">Ma se si specifica lo stesso nome di immagine, anche con lo stesso tag, le immagini multi-arch, ad esempio l'immagine `aspnetcore`, useranno la versione Linux o Windows in base al sistema operativo host Docker che si sta distribuendo, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0718c-200">But, if you specify the same image name, even with the same tag, the multi-arch images (like the `aspnetcore` image) will use the Linux or Windows version depending on the Docker host OS you're deploying, as shown in the following example:</span></span>

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  <span data-ttu-id="0718c-201">Multiarchitettura: solo runtime .NET Core 2.2 in Linux e Windows Nano Server in base al sistema operativo dell'host Docker</span><span class="sxs-lookup"><span data-stu-id="0718c-201">Multi-arch: .NET Core 2.2 runtime-only on Linux or Windows Nano Server depending on the Docker host OS</span></span>

<span data-ttu-id="0718c-202">In questo modo, se si esegue il pull di un'immagine da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome di immagine da un host Linux si ottiene la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="0718c-202">This way, when you pull an image from a Windows host, it will pull the Windows variant, and pulling the same image name from a Linux host will pull the Linux variant.</span></span>

### <a name="multi-stage-builds-in-dockerfile"></a><span data-ttu-id="0718c-203">Compilazioni in più fasi in Dockerfile</span><span class="sxs-lookup"><span data-stu-id="0718c-203">Multi-stage builds in Dockerfile</span></span>

<span data-ttu-id="0718c-204">Il Dockerfile è simile a uno script batch.</span><span class="sxs-lookup"><span data-stu-id="0718c-204">The Dockerfile is similar to a batch script.</span></span> <span data-ttu-id="0718c-205">Esegue le operazioni che sarebbe necessario eseguire per configurare il computer dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0718c-205">Similar to what you would do if you had to set up the machine from the command line.</span></span>

<span data-ttu-id="0718c-206">Inizia con un'immagine di base che imposta il contesto iniziale, analogamente al filesystem di avvio, e si trova nella parte superiore del sistema operativo host.</span><span class="sxs-lookup"><span data-stu-id="0718c-206">It starts with a base image that sets up the initial context, it's like the startup filesystem, that sits on top of the host OS.</span></span> <span data-ttu-id="0718c-207">Non è un sistema operativo, ma si può considerare come "il" sistema operativo all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-207">It's not an OS, but you can think of if like "the" OS inside the container.</span></span>

<span data-ttu-id="0718c-208">L'esecuzione di ogni riga di comando crea un nuovo livello nel filesystem con le modifiche di quello precedente, in modo che la combinazione generi il filesystem risultante.</span><span class="sxs-lookup"><span data-stu-id="0718c-208">The execution of every command line creates a new layer on the filesystem with the changes from the previous one, so that, when combined, produce the resulting filesystem.</span></span>

<span data-ttu-id="0718c-209">Poiché ogni nuovo livello viene creato sopra il livello precedente e le dimensioni dell'immagine risultante aumentano ad ogni comando, le immagini possono diventare molto grandi se devono includere, ad esempio, l'SDK necessario per compilare e pubblicare un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0718c-209">Since every new layer "rests" on top of the previous one and the resulting image size increases with every command, images can get very large if they have to include, for example, the SDK needed to build and publish an application.</span></span>

<span data-ttu-id="0718c-210">Qui è dove le compilazioni in più fasi entrano in gioco (da Docker 17.05 e versioni successive) e dimostrano tutta la loro efficacia.</span><span class="sxs-lookup"><span data-stu-id="0718c-210">This is where multi-stage builds get into the plot (from Docker 17.05 and higher) to do their magic.</span></span>

<span data-ttu-id="0718c-211">L'idea di base è che è possibile separare il processo di esecuzione Dockerfile in più fasi, in cui una fase è un'immagine iniziale seguita da uno o più comandi e l'ultima fase determina le dimensioni dell'immagine finale.</span><span class="sxs-lookup"><span data-stu-id="0718c-211">The core idea is that you can separate the Dockerfile execution process in stages, where a stage is an initial image followed by one or more commands, and the last stage determines the final image size.</span></span>

<span data-ttu-id="0718c-212">In breve, le compilazioni in più fasi consentono di suddividere la creazione in diversi passaggi e quindi assemblare l'immagine finale usando solo le directory pertinenti delle fasi intermedie.</span><span class="sxs-lookup"><span data-stu-id="0718c-212">In short, multi-stage builds allow splitting the creation in different "phases" and then assemble the final image taking only the relevant directories from the intermediate stages.</span></span> <span data-ttu-id="0718c-213">La strategia generale per usare questa funzionalità è:</span><span class="sxs-lookup"><span data-stu-id="0718c-213">The general strategy to use this feature is:</span></span>

1. <span data-ttu-id="0718c-214">Usare un'immagine di base dell'SDK (le dimensioni non sono importanti), con tutto ciò che serve per compilare e pubblicare l'applicazione in una cartella e quindi</span><span class="sxs-lookup"><span data-stu-id="0718c-214">Use a base SDK image (doesn't matter how large), with everything needed to build and publish the application to a folder and then</span></span>

2. <span data-ttu-id="0718c-215">usare un'immagine di base, piccola e solo di runtime, e copiare la cartella di pubblicazione della fase precedente per produrre un'immagine finale di dimensioni ridotte.</span><span class="sxs-lookup"><span data-stu-id="0718c-215">Use a base, small, runtime-only image and copy the publishing folder from the previous stage to produce a small final image.</span></span>

<span data-ttu-id="0718c-216">Probabilmente il modo migliore per comprendere la compilazione in più fasi è esaminare un Dockerfile in dettaglio, riga per riga, quindi si può iniziare con il Dockerfile creato da Visual Studio quando si aggiunge il supporto Docker a un progetto e vedere alcune ottimizzazioni in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0718c-216">Probably the best way to understand multi-stage is going through a Dockerfile in detail, line by line, so let's begin with the initial Dockerfile created by Visual Studio when adding Docker support to a project and will get into some optimizations later.</span></span>

<span data-ttu-id="0718c-217">Il Dockerfile iniziale può avere un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0718c-217">The initial Dockerfile might look something like this:</span></span>

```Dockerfile
 1  FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM microsoft/dotnet:2.2-sdk AS build
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
20  RUN dotnet build Catalog.API.csproj -c Release -0 /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

<span data-ttu-id="0718c-218">E questi sono i dettagli, riga per riga:</span><span class="sxs-lookup"><span data-stu-id="0718c-218">And these are the details, line by line:</span></span>

1.  <span data-ttu-id="0718c-219">Avviare una fase con una "piccola" immagine di base solo di runtime, denominarla **base** per riferimento.</span><span class="sxs-lookup"><span data-stu-id="0718c-219">Begin a stage with a "small" runtime-only base image, call it **base** for reference.</span></span>
2.  <span data-ttu-id="0718c-220">Creare la directory **/app** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0718c-220">Create **/app** directory in the image.</span></span>
3.  <span data-ttu-id="0718c-221">Esporre la porta **80**.</span><span class="sxs-lookup"><span data-stu-id="0718c-221">Expose port **80**.</span></span>
<!-- skip -->
5.  <span data-ttu-id="0718c-222">Iniziare una nuova fase con una "grande" immagine per la compilazione e la pubblicazione, denominarla **build** per riferimento.</span><span class="sxs-lookup"><span data-stu-id="0718c-222">Begin a new stage with "large" image for building/publishing, call it **build** for reference.</span></span>
6.  <span data-ttu-id="0718c-223">Creare la directory **/src** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0718c-223">Create directory **/src** in the image.</span></span>
7.  <span data-ttu-id="0718c-224">Fino alla riga 16, copiare i file **CSPROJ** dei progetti di riferimento, per poter ripristinare i pacchetti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0718c-224">Up to line 16, copy referenced projects **.csproj** files, to be able to restore packages later.</span></span>
<!-- skip -->
17. <span data-ttu-id="0718c-225">Ripristinare i pacchetti per il progetto **Catalog.API** e i progetti di riferimento.</span><span class="sxs-lookup"><span data-stu-id="0718c-225">Restore packages for the **Catalog.API** project and the referenced projects.</span></span>
18. <span data-ttu-id="0718c-226">Copiare **tutti gli alberi di directory per soluzione** (tranne le directory e i file inclusi nel file **DOCKERIGNORE**) dalla directory **/src** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0718c-226">Copy **all directory tree for the solution** (except the files/directories included in the **.dockerignore** file) from to the **/src** directory in the image.</span></span>
19. <span data-ttu-id="0718c-227">Impostare come cartella corrente il progetto **Catalog.API**.</span><span class="sxs-lookup"><span data-stu-id="0718c-227">Change current folder to **Catalog.API** project.</span></span>
20. <span data-ttu-id="0718c-228">Compilare il progetto (e altre dipendenze del progetto) e l'output nella directory **/app** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0718c-228">Build project (and other project dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
22. <span data-ttu-id="0718c-229">Iniziare una nuova fase continuando dalla compilazione, denominarla **publish** per riferimento.</span><span class="sxs-lookup"><span data-stu-id="0718c-229">Begin a new stage continuing from build, call it **publish** for reference.</span></span>
23. <span data-ttu-id="0718c-230">Pubblicare il progetto (e le dipendenze) e l'output nella directory **/app** nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0718c-230">Publish project (and dependencies) and output to **/app** directory in the image.</span></span>
<!-- skip -->
25. <span data-ttu-id="0718c-231">Iniziare una nuova fase continuando da **base** e denominarla **final**</span><span class="sxs-lookup"><span data-stu-id="0718c-231">Begin a new stage continuing from **base** and call it **final**</span></span>
26. <span data-ttu-id="0718c-232">Selezionare **/app** come directory corrente</span><span class="sxs-lookup"><span data-stu-id="0718c-232">Change current directory to **/app**</span></span>
27. <span data-ttu-id="0718c-233">Copiare la directory **/app** dalla fase **publish** nella directory corrente</span><span class="sxs-lookup"><span data-stu-id="0718c-233">Copy the **/app** directory from stage **publish** to the current directory</span></span>
28. <span data-ttu-id="0718c-234">Definire il comando da eseguire quando viene avviato il contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-234">Define the command to run when the container is started.</span></span>

<span data-ttu-id="0718c-235">Esaminare ora alcune ottimizzazioni che consentono di migliorare le prestazioni generali del processo che, nel caso di eShopOnContainers, corrispondono a circa 22 minuti o più per la compilazione della soluzione completa nei contenitori Linux.</span><span class="sxs-lookup"><span data-stu-id="0718c-235">Now let's explore some optimizations to improve the whole process performance that, in the case of eShopOnContainers, means about 22 minutes or more to build the complete solution in Linux containers.</span></span>

<span data-ttu-id="0718c-236">Si può sfruttare la funzionalità di cache per i livelli di Docker, che è piuttosto semplice: se l'immagine di base e i comandi corrispondono ad altri già eseguiti in precedenza, è possibile usare solo il livello risultante senza dover eseguire i comandi, risparmiando tempo.</span><span class="sxs-lookup"><span data-stu-id="0718c-236">You'll take advantage of Docker's layer cache feature, which is quite simple: if the base image and the commands are the same as some previously executed, it can just use the resulting layer without the need to execute the commands, thus saving some time.</span></span>

<span data-ttu-id="0718c-237">Quindi, concentrarsi sulla fase **build**, dove le righe 5 e 6 sono praticamente le stesse, ma le righe da 7 a 17 sono diverse per ogni servizio di eShopOnContainers, quindi devono essere eseguite ogni singola volta. Tuttavia, se le righe da 7 a 16 sono state modificate in:</span><span class="sxs-lookup"><span data-stu-id="0718c-237">So, let's focus on the **build** stage, lines 5-6 are mostly the same, but lines 7-17 are different for every service from eShopOnContainers, so they have to execute every single time, however if you changed lines 7-16 to:</span></span>

```
COPY . .
```

<span data-ttu-id="0718c-238">Si avrebbe lo stesso per ogni servizio, verrebbe copiata l'intera soluzione e verrebbe creato un livello di dimensioni maggiori ma:</span><span class="sxs-lookup"><span data-stu-id="0718c-238">Then it would be just the same for every service, it would copy the whole solution and would create a larger layer but:</span></span>

1) <span data-ttu-id="0718c-239">Il processo di copia verrebbe eseguito solo la prima volta (e quando si ricompila se viene modificato un file) e userebbe la cache per tutti gli altri servizi e</span><span class="sxs-lookup"><span data-stu-id="0718c-239">The copy process would only be executed the first time (and when rebuilding if a file is changed) and would use the cache for all other services and</span></span>

2) <span data-ttu-id="0718c-240">Poiché l'immagine più grande si verifica in una fase intermedia, non influisce sulle dimensioni dell'immagine finale.</span><span class="sxs-lookup"><span data-stu-id="0718c-240">Since the larger image occurs in an intermediate stage it, doesn't affect the final image size.</span></span>

<span data-ttu-id="0718c-241">Un'altra ottimizzazione significativa riguarda il comando `restore` eseguito alla riga 17, che è diverso per ogni servizio di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="0718c-241">The next significant optimization involves the `restore` command executed in line 17, which is also different for every service of eShopOnContainers.</span></span> <span data-ttu-id="0718c-242">Se si modifica tale riga semplicemente in:</span><span class="sxs-lookup"><span data-stu-id="0718c-242">If you change that line to just:</span></span>

```console
RUN dotnet restore
```

<span data-ttu-id="0718c-243">I pacchetti verrebbero ripristinati per l'intera soluzione, ma anche in questo caso l'operazione verrebbe eseguita una sola volta, anziché 15 volte come con la strategia attuale.</span><span class="sxs-lookup"><span data-stu-id="0718c-243">It would restore the packages for the whole solution, but then again, it would do it just once, instead of the 15 times with the current strategy.</span></span>

<span data-ttu-id="0718c-244">Tuttavia, `dotnet restore` viene eseguito solo se è presente un solo progetto o file di soluzione nella cartella, quindi ottenere questo risultato è un po' più complesso e il modo per ottenerlo, senza entrare troppo nel dettaglio, è questo:</span><span class="sxs-lookup"><span data-stu-id="0718c-244">However, `dotnet restore` only runs if there's a single project or solution file in the folder, so achieving this is a bit more complicated and the way to solve it, without getting into too many details, is this:</span></span>

1) <span data-ttu-id="0718c-245">Aggiungere le righe seguenti al file **DOCKERIGNORE**:</span><span class="sxs-lookup"><span data-stu-id="0718c-245">Add the following lines to **.dockerignore**:</span></span>

   - <span data-ttu-id="0718c-246">`*.sln`, per ignorare tutti i file di soluzione nella struttura della cartella principale</span><span class="sxs-lookup"><span data-stu-id="0718c-246">`*.sln`, to ignore all solution files in the main folder tree</span></span>

   - <span data-ttu-id="0718c-247">`!eShopOnContainers-ServicesAndWebApps.sln`, per includere solo questo file di soluzione.</span><span class="sxs-lookup"><span data-stu-id="0718c-247">`!eShopOnContainers-ServicesAndWebApps.sln`, to include only this solution file.</span></span>

2) <span data-ttu-id="0718c-248">Includere l'argomento `/ignoreprojectextensions:.dcproj` a `dotnet restore`, in modo che ignori anche il progetto docker-compose e ripristini solo i pacchetti per la soluzione eShopOnContainers-ServicesAndWebApps.</span><span class="sxs-lookup"><span data-stu-id="0718c-248">Include the `/ignoreprojectextensions:.dcproj` argument to `dotnet restore`, so it also ignores the docker-compose project and only restores the packages for the eShopOnContainers-ServicesAndWebApps solution.</span></span>

<span data-ttu-id="0718c-249">Per l'ottimizzazione finale, la riga 20 risulta ridondante, poiché anche la riga 23 compila l'applicazione e praticamente viene subito dopo la riga 20, quindi si ha un altro comando che richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="0718c-249">For the final optimization, it just happens that line 20 is redundant, as line 23 also builds the application and comes, in essence, right after line 20, so there goes another time-consuming command.</span></span>

<span data-ttu-id="0718c-250">Il file risultante quindi è:</span><span class="sxs-lookup"><span data-stu-id="0718c-250">The resulting file is then:</span></span>

```Dockerfile
 1  FROM microsoft/dotnet:2.2-aspnetcore-runtime AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM microsoft/dotnet:2.2-sdk AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a><span data-ttu-id="0718c-251">Creazione dell'immagine di base da zero</span><span class="sxs-lookup"><span data-stu-id="0718c-251">Creating your base image from scratch</span></span>

<span data-ttu-id="0718c-252">È possibile creare un'immagine Docker di base da zero.</span><span class="sxs-lookup"><span data-stu-id="0718c-252">You can create your own Docker base image from scratch.</span></span> <span data-ttu-id="0718c-253">Questo scenario non è consigliato se non si conosce bene Docker, ma se si vuole creare la propria immagine di base è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="0718c-253">This scenario is not recommended for someone who is starting with Docker, but if you want to set the specific bits of your own base image, you can do so.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0718c-254">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0718c-254">Additional resources</span></span>

- <span data-ttu-id="0718c-255">**Immagini multi-arch .NET Core**.\\</span><span class="sxs-lookup"><span data-stu-id="0718c-255">**Multi-arch .NET Core images**.\\</span></span>
  [*https://github.com/dotnet/announcements/issues/14*](https://github.com/dotnet/announcements/issues/14)

- <span data-ttu-id="0718c-256">**Creare un'immagine di base**.</span><span class="sxs-lookup"><span data-stu-id="0718c-256">**Create a base image**.</span></span> <span data-ttu-id="0718c-257">Documentazione ufficiale di Docker.\\</span><span class="sxs-lookup"><span data-stu-id="0718c-257">Official Docker documentation.\\</span></span>
  [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![3 - Creare immagini definite nei Dockerfile](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a><span data-ttu-id="0718c-259">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="0718c-259">Step 3.</span></span> <span data-ttu-id="0718c-260">Creare le immagini Docker personalizzate e incorporare l'applicazione o il servizio in esse</span><span class="sxs-lookup"><span data-stu-id="0718c-260">Create your custom Docker images and embed your application or service in them</span></span>

<span data-ttu-id="0718c-261">Per ogni servizio dell'applicazione è necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="0718c-261">For each service in your application, you need to create a related image.</span></span> <span data-ttu-id="0718c-262">Se l'applicazione è costituita da un singolo servizio o applicazione Web, è sufficiente una singola immagine.</span><span class="sxs-lookup"><span data-stu-id="0718c-262">If your application is made up of a single service or web application, you just need a single image.</span></span>

<span data-ttu-id="0718c-263">Si noti che le immagini Docker vengono create automaticamente in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0718c-263">Note that the Docker images are built automatically for you in Visual Studio.</span></span> <span data-ttu-id="0718c-264">I passaggi seguenti sono necessari solo per il flusso di lavoro editor/CLI e sono descritti per chiarire meglio ciò che succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="0718c-264">The following steps are only needed for the editor/CLI workflow and explained for clarity about what happens underneath.</span></span>

<span data-ttu-id="0718c-265">Lo sviluppatore deve eseguire lo sviluppo e i test localmente finché non esegue il push di una funzionalità o di una modifica completa nel sistema di controllo del codice sorgente, ad esempio in GitHub.</span><span class="sxs-lookup"><span data-stu-id="0718c-265">You, as developer, need to develop and test locally until you push a completed feature or change to your source control system (for example, to GitHub).</span></span> <span data-ttu-id="0718c-266">Ciò significa che è necessario creare le immagini Docker e distribuire i contenitori in un host Docker locale, ovvero una VM Windows o Linux, nonché eseguire, testare ed eseguire il debug in tali contenitori locale.</span><span class="sxs-lookup"><span data-stu-id="0718c-266">This means that you need to create the Docker images and deploy containers to a local Docker host (Windows or Linux VM) and run, test, and debug against those local containers.</span></span>

<span data-ttu-id="0718c-267">Per creare un'immagine personalizzata nell'ambiente locale tramite la CLI di Docker e il Dockerfile, è possibile usare il comando docker build, come illustrato nella figura 5-5.</span><span class="sxs-lookup"><span data-stu-id="0718c-267">To create a custom image in your local environment by using Docker CLI and your Dockerfile, you can use the docker build command, as in Figure 5-5.</span></span>

![Schermata di avanzamento per la creazione di un'immagine Docker](./media/image8.png)

<span data-ttu-id="0718c-269">**Figura 5-5**.</span><span class="sxs-lookup"><span data-stu-id="0718c-269">**Figure 5-5**.</span></span> <span data-ttu-id="0718c-270">Creazione di un'immagine Docker personalizzata</span><span class="sxs-lookup"><span data-stu-id="0718c-270">Creating a custom Docker image</span></span>

<span data-ttu-id="0718c-271">Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è possibile generare innanzitutto una cartella distribuibile con le raccolte .NET e i file binari necessari eseguendo `dotnet publish` e quindi usando il comando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="0718c-271">Optionally, instead of directly running docker build from the project folder, you can first generate a deployable folder with the required .NET libraries and binaries by running `dotnet publish`, and then use the `docker build` command.</span></span>

<span data-ttu-id="0718c-272">Verrà creata un'immagine Docker con il nome `cesardl/netcore-webapi-microservice-docker:first`.</span><span class="sxs-lookup"><span data-stu-id="0718c-272">This will create a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first`.</span></span> <span data-ttu-id="0718c-273">In questo caso :first è un tag che rappresenta una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="0718c-273">In this case, :first is a tag representing a specific version.</span></span> <span data-ttu-id="0718c-274">È possibile ripetere questo passaggio per ogni immagine personalizzata da creare per l'applicazione Docker composta.</span><span class="sxs-lookup"><span data-stu-id="0718c-274">You can repeat this step for each custom image you need to create for your composed Docker application.</span></span>

<span data-ttu-id="0718c-275">Quando un'applicazione è costituita da più contenitori, ovvero è un'applicazione a più contenitori, è anche possibile usare il comando `docker-compose up --build` per compilare tutte le immagini correlate con un singolo comando usando i metadati esposti nei file docker-compose.yml correlati.</span><span class="sxs-lookup"><span data-stu-id="0718c-275">When an application is made of multiple containers (that is, it is a multi-container application), you can also use the `docker-compose up --build` command to build all the related images with a single command by using the metadata exposed in the related docker-compose.yml files.</span></span>

<span data-ttu-id="0718c-276">È possibile trovare le immagini esistenti nel repository locale tramite il comando docker images, come illustrato nella figura 5-6.</span><span class="sxs-lookup"><span data-stu-id="0718c-276">You can find the existing images in your local repository by using the docker images command, as shown in Figure 5-6.</span></span>

![Visualizzazione schermata dell'elenco di immagini del comando docker images](./media/image9.png)

<span data-ttu-id="0718c-278">**Figura 5-6.**</span><span class="sxs-lookup"><span data-stu-id="0718c-278">**Figure 5-6.**</span></span> <span data-ttu-id="0718c-279">Visualizzazione di immagini esistente con il comando docker images</span><span class="sxs-lookup"><span data-stu-id="0718c-279">Viewing existing images using the docker images command</span></span>

### <a name="creating-docker-images-with-visual-studio"></a><span data-ttu-id="0718c-280">Creazione di immagini Docker con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0718c-280">Creating Docker images with Visual Studio</span></span>

<span data-ttu-id="0718c-281">Quando si usa Visual Studio per creare un progetto con il supporto Docker, non si crea un'immagine in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="0718c-281">When you use Visual Studio to create a project with Docker support, you don't explicitly create an image.</span></span> <span data-ttu-id="0718c-282">L'immagine viene invece creata automaticamente quando si preme **F5** (o **CTRL-F5**) e si esegue l'applicazione o il servizio Docker.</span><span class="sxs-lookup"><span data-stu-id="0718c-282">Instead, the image is created for you when you press **F5** (or **Ctrl-F5**) to run the dockerized application or service.</span></span> <span data-ttu-id="0718c-283">Questo passaggio è automatico e invisibile in Visual Studio, ma è importante sapere cosa succede dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="0718c-283">This step is automatic in Visual Studio and you won't see it happen, but it's important that you know what's going on underneath.</span></span>

![4 - (facoltativo) Comporre i servizi nel file docker-compose.yml](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a><span data-ttu-id="0718c-285">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="0718c-285">Step 4.</span></span> <span data-ttu-id="0718c-286">Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori</span><span class="sxs-lookup"><span data-stu-id="0718c-286">Define your services in docker-compose.yml when building a multi-container Docker application</span></span>

<span data-ttu-id="0718c-287">Il file [docker compose.yml](https://docs.docker.com/compose/compose-file/) consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0718c-287">The [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file lets you define a set of related services to be deployed as a composed application with deployment commands.</span></span> <span data-ttu-id="0718c-288">Configura inoltre le proprie relazioni di dipendenza e la configurazione di runtime.</span><span class="sxs-lookup"><span data-stu-id="0718c-288">It also configures its dependency relations and run-time configuration.</span></span>

<span data-ttu-id="0718c-289">Per usare un file docker-compose.yml, è necessario creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0718c-289">To use a docker-compose.yml file, you need to create the file in your main or root solution folder, with content similar to that in the following example:</span></span>

```yml
version: '3.4'

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
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
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

<span data-ttu-id="0718c-290">Questo file docker-compose.yml è una versione semplificata e unita.</span><span class="sxs-lookup"><span data-stu-id="0718c-290">This docker-compose.yml file is a simplified and merged version.</span></span> <span data-ttu-id="0718c-291">Contiene dati di configurazione statici per ogni contenitore, ad esempio il nome dell'immagine personalizzata, che sono sempre richiesti, nonché informazioni di configurazione che possono dipendere dall'ambiente di distribuzione, ad esempio la stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="0718c-291">It contains static configuration data for each container (like the name of the custom image), which is always required, and configuration information that might depend on the deployment environment, like the connection string.</span></span> <span data-ttu-id="0718c-292">Nelle sezioni successive si vedrà come suddividere la configurazione di docker-compose.yml in più file docker-compose e come sostituire valori a seconda del tipo di ambiente e di esecuzione (debug o release).</span><span class="sxs-lookup"><span data-stu-id="0718c-292">In later sections, you will learn how to split the docker-compose.yml configuration into multiple docker-compose files and override values depending on the environment and execution type (debug or release).</span></span>

<span data-ttu-id="0718c-293">L'esempio di file docker-compose.yml definisce quattro servizi: il servizio `webmvc` (un'applicazione Web), due microservizi (`ordering.api` e `basket.api`) e un contenitore origine dati, `sql.data`, basato su SQL Server per Linux eseguito come contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-293">The docker-compose.yml file example defines four services: the `webmvc` service (a web application), two microservices (`ordering.api` and `basket.api`), and one data source container, `sql.data`, based on SQL Server for Linux running as a container.</span></span> <span data-ttu-id="0718c-294">Ogni servizio verrà distribuito come contenitore, quindi è necessaria un'immagine Docker per ognuno.</span><span class="sxs-lookup"><span data-stu-id="0718c-294">Each service will be deployed as a container, so a Docker image is required for each.</span></span>

<span data-ttu-id="0718c-295">Il file docker-compose.yml specifica non solo quali contenitori vengono usati, ma come sono configurati singolarmente.</span><span class="sxs-lookup"><span data-stu-id="0718c-295">The docker-compose.yml file specifies not only what containers are being used, but how they are individually configured.</span></span> <span data-ttu-id="0718c-296">Ad esempio, la definizione del contenitore `webmvc` nel file YML:</span><span class="sxs-lookup"><span data-stu-id="0718c-296">For instance, the `webmvc` container definition in the .yml file:</span></span>

- <span data-ttu-id="0718c-297">Usa un'immagine `eshop/web:latest` predefinita.</span><span class="sxs-lookup"><span data-stu-id="0718c-297">Uses a pre-built `eshop/web:latest` image.</span></span> <span data-ttu-id="0718c-298">Tuttavia, è anche possibile configurare l'immagine in modo che sia compilata come parte dell'esecuzione di docker-compose con una configurazione aggiuntiva basata su una sezione build: nel file docker-compose.</span><span class="sxs-lookup"><span data-stu-id="0718c-298">However, you could also configure the image to be built as part of the docker-compose execution with an additional configuration based on a build: section in the docker-compose file.</span></span>

- <span data-ttu-id="0718c-299">Inizializza due variabili di ambiente, ovvero CatalogUrl e OrderingUrl.</span><span class="sxs-lookup"><span data-stu-id="0718c-299">Initializes two environment variables (CatalogUrl and OrderingUrl).</span></span>

- <span data-ttu-id="0718c-300">Inoltra la porta 80 esposta sul contenitore alla porta esterna 80 sul computer host.</span><span class="sxs-lookup"><span data-stu-id="0718c-300">Forwards the exposed port 80 on the container to the external port 80 on the host machine.</span></span>

- <span data-ttu-id="0718c-301">Collega l'app Web al catalogo e al servizio di ordinazione con l'impostazione depends_on.</span><span class="sxs-lookup"><span data-stu-id="0718c-301">Links the web app to the catalog and ordering service with the depends_on setting.</span></span> <span data-ttu-id="0718c-302">In questo modo il servizio attende fino a quando vengono avviati i servizi.</span><span class="sxs-lookup"><span data-stu-id="0718c-302">This causes the service to wait until those services are started.</span></span>

<span data-ttu-id="0718c-303">Il file docker-compose.yml sarà esaminato di nuovo in una sezione successiva in cui sarà descritto come implementare microservizi e app a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="0718c-303">We will revisit the docker-compose.yml file in a later section when we cover how to implement microservices and multi-container apps.</span></span>

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a><span data-ttu-id="0718c-304">Utilizzo di docker-compose.yml in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0718c-304">Working with docker-compose.yml in Visual Studio 2017</span></span>

<span data-ttu-id="0718c-305">Oltre ad aggiungere un Dockerfile a un progetto, come si è visto in precedenza, Visual Studio 2017 (dalla versione 15.8 in poi) è in grado di aggiungere il supporto di un agente di orchestrazione per Docker Compose a una soluzione.</span><span class="sxs-lookup"><span data-stu-id="0718c-305">Besides adding a Dockerfile to a project, as we mentioned before, Visual Studio 2017 (from 15.8 on) can add orchestrator support for Docker Compose to a solution.</span></span>

<span data-ttu-id="0718c-306">Quando si aggiunge il supporto dell'agente di orchestrazione del contenitore, come illustrato nella figura 5-7, per la prima volta, Visual Studio crea il Dockerfile per il progetto e crea un nuovo progetto (sezione servizio) nella soluzione con diversi file `docker-compose*.yml` globali e quindi aggiunge il progetto a tali file.</span><span class="sxs-lookup"><span data-stu-id="0718c-306">When you add container orchestrator support, as shown in Figure 5-7, for the first time, Visual Studio creates the Dockerfile for the project and creates a new (service section) project in your solution with several global `docker-compose*.yml` files, and then adds the project to those files.</span></span> <span data-ttu-id="0718c-307">È quindi possibile aprire i file docker-compose.yml e aggiornarli con funzionalità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="0718c-307">You can then open the docker-compose.yml files and update them with additional features.</span></span>

<span data-ttu-id="0718c-308">È necessario ripetere questa operazione per ogni progetto che si vuole includere nel file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="0718c-308">You have to repeat this operation form every project you want to include in the docker-compose.yml file.</span></span>

<span data-ttu-id="0718c-309">Al momento della stesura di questo articolo, Visual Studio supporta gli agenti di orchestrazione Docker Compose e Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="0718c-309">At the time of this writing, Visual Studio supports Docker Compose and Service Fabric orchestrators.</span></span>

![Opzione del menu di scelta rapida che aggiunge il supporto dell'agente di orchestrazione a un progetto ASP.NET Core](./media/image21.png)

<span data-ttu-id="0718c-311">**Figura 5-7**.</span><span class="sxs-lookup"><span data-stu-id="0718c-311">**Figure 5-7**.</span></span> <span data-ttu-id="0718c-312">Aggiunta del supporto Docker in Visual Studio 2017 facendo clic con il pulsante destro del mouse su un progetto ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0718c-312">Adding Docker support in Visual Studio 2017 by right-clicking an ASP.NET Core project</span></span>

<span data-ttu-id="0718c-313">Dopo aver aggiunto il supporto dell'agente di orchestrazione alla soluzione in Visual Studio, si noterà anche un nuovo nodo nel file di progetto `docker-compose.dcproj` in Esplora soluzioni, che contiene i file docker-compose.yml aggiunti, come illustrato nella figura 5-8.</span><span class="sxs-lookup"><span data-stu-id="0718c-313">After you add orchestrator support to your solution in Visual Studio, you will also see a new node (in the `docker-compose.dcproj` project file) in Solution Explorer that contains the added docker-compose.yml files, as shown in Figure 5-8.</span></span>

![Nodo docker-compose in Esplora soluzioni](./media/image11.png)

<span data-ttu-id="0718c-315">**Figura 5-8**.</span><span class="sxs-lookup"><span data-stu-id="0718c-315">**Figure 5-8**.</span></span> <span data-ttu-id="0718c-316">Il nodo dell'albero **docker-compose** aggiunto in Esplora soluzioni di Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0718c-316">The **docker-compose** tree node added in Visual Studio 2017 Solution Explorer</span></span>

<span data-ttu-id="0718c-317">È possibile distribuire un'applicazione a più contenitori con un singolo file docker-compose.yml usando il comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="0718c-317">You could deploy a multi-container application with a single docker-compose.yml file by using the `docker-compose up` command.</span></span> <span data-ttu-id="0718c-318">Tuttavia Visual Studio ne aggiunge un gruppo, quindi è possibile sostituire i valori in base all'ambiente, che può essere di sviluppo o di produzione, e al tipo di esecuzione (versione o debug).</span><span class="sxs-lookup"><span data-stu-id="0718c-318">However, Visual Studio adds a group of them so you can override values depending on the environment (development or production) and execution type (release or debug).</span></span> <span data-ttu-id="0718c-319">Questa funzionalità sarà spiegata nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="0718c-319">This capability will be explained in later sections.</span></span>

![5 - Eseguire l'app contenitore o composta](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a><span data-ttu-id="0718c-321">Passaggio 5.</span><span class="sxs-lookup"><span data-stu-id="0718c-321">Step 5.</span></span> <span data-ttu-id="0718c-322">Compilare ed eseguire l'applicazione Docker</span><span class="sxs-lookup"><span data-stu-id="0718c-322">Build and run your Docker application</span></span>

<span data-ttu-id="0718c-323">Se l'applicazione ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, ovvero una VM o un server fisico.</span><span class="sxs-lookup"><span data-stu-id="0718c-323">If your application only has a single container, you can run it by deploying it to your Docker host (VM or physical server).</span></span> <span data-ttu-id="0718c-324">Se invece l'applicazione contiene più servizi, è possibile distribuirla come applicazione composta, usando un unico comando della CLI, ossia docker-compose up, o con Visual Studio, che userà lo stesso comando dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="0718c-324">However, if your application contains multiple services, you can deploy it as a composed application, either using a single CLI command (docker-compose up), or with Visual Studio, which will use that command under the covers.</span></span> <span data-ttu-id="0718c-325">Le diverse opzioni sono esaminate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0718c-325">Let's look at the different options.</span></span>

### <a name="option-a-running-a-single-container-application"></a><span data-ttu-id="0718c-326">Opzione A: esecuzione di un'applicazione a un solo contenitore</span><span class="sxs-lookup"><span data-stu-id="0718c-326">Option A: Running a single-container application</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="0718c-327">Con l'interfaccia della riga di comando di Docker</span><span class="sxs-lookup"><span data-stu-id="0718c-327">Using Docker CLI</span></span>

<span data-ttu-id="0718c-328">È possibile eseguire un contenitore Docker usando il comando `docker run`, come illustrato nella figura 5-9:</span><span class="sxs-lookup"><span data-stu-id="0718c-328">You can run a Docker container using the `docker run` command, as shown in Figure 5-9:</span></span>

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="0718c-329">Il comando precedente crea una nuova istanza di contenitore dall'immagine specificata, ogni volta che viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="0718c-329">The above command will create a new container instance from the specified image, every time it's run.</span></span> <span data-ttu-id="0718c-330">È possibile usare il parametro `--name` per assegnare un nome al contenitore e quindi usare `docker start {name}`, o il nome automatico o ID del contenitore, per eseguire un'istanza di contenitore esistente.</span><span class="sxs-lookup"><span data-stu-id="0718c-330">You can use the `--name` parameter to give a name to the container and then use `docker start {name}` (or use the container id or automatic name) to run an existing container instance.</span></span>

![Schermata che appare quando si esegue un contenitore Docker usando il comando docker run](./media/image13.png)

<span data-ttu-id="0718c-332">**Figura 5-9**.</span><span class="sxs-lookup"><span data-stu-id="0718c-332">**Figure 5-9**.</span></span> <span data-ttu-id="0718c-333">Esecuzione di un contenitore Docker usando il comando docker run</span><span class="sxs-lookup"><span data-stu-id="0718c-333">Running a Docker container using the docker run command</span></span>

<span data-ttu-id="0718c-334">In questo caso il comando associa la porta interna 5000 del contenitore alla porta 80 del computer host.</span><span class="sxs-lookup"><span data-stu-id="0718c-334">In this case, the command binds the internal port 5000 of the container to port 80 of the host machine.</span></span> <span data-ttu-id="0718c-335">Ciò significa che l'host è in ascolto sulla porta 80 e inoltra alla porta 5000 nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-335">This means that the host is listening on port 80 and forwarding to port 5000 on the container.</span></span>

<span data-ttu-id="0718c-336">L'hash illustrato è l'ID del contenitore a cui viene anche assegnato un nome casuale leggibile se non si usa l'opzione `--name`.</span><span class="sxs-lookup"><span data-stu-id="0718c-336">The hash shown is the container id and it’s also assigned a random readable name if the `--name` option is not used.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="0718c-337">Utilizzo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0718c-337">Using Visual Studio</span></span>

<span data-ttu-id="0718c-338">Se non è stato aggiunto il supporto dell'agente di orchestrazione dei contenitori, è anche possibile eseguire un'applicazione a singolo contenitore in Visual Studio premendo **CTRL+F5** e usare **F5** per eseguire il debug dell'applicazione all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="0718c-338">If you haven't added container orchestrator support, you can also run a single container app in Visual Studio by pressing **Ctrl-F5** and you can also use **F5** to debug the application within the container.</span></span> <span data-ttu-id="0718c-339">Il contenitore viene eseguito in locale usando docker run.</span><span class="sxs-lookup"><span data-stu-id="0718c-339">The container runs locally using docker run.</span></span>

### <a name="option-b-running-a-multi-container-application"></a><span data-ttu-id="0718c-340">Opzione B: esecuzione di un'applicazione a più contenitori</span><span class="sxs-lookup"><span data-stu-id="0718c-340">Option B: Running a multi-container application</span></span>

<span data-ttu-id="0718c-341">Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà composta da più servizi, perciò sarà necessario eseguire un'applicazione a più contenitori, come illustrato nella figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="0718c-341">In most enterprise scenarios, a Docker application will be composed of multiple services, which means you need to run a multi-container application, as shown in Figure 5-10.</span></span>

![Macchina virtuale con diversi contenitori Docker](./media/image14.png)

<span data-ttu-id="0718c-343">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="0718c-343">**Figure 5-10**.</span></span> <span data-ttu-id="0718c-344">VM con contenitori Docker distribuiti</span><span class="sxs-lookup"><span data-stu-id="0718c-344">VM with Docker containers deployed</span></span>

#### <a name="using-docker-cli"></a><span data-ttu-id="0718c-345">Con l'interfaccia della riga di comando di Docker</span><span class="sxs-lookup"><span data-stu-id="0718c-345">Using Docker CLI</span></span>

<span data-ttu-id="0718c-346">Per eseguire un'applicazione a più contenitori con l'interfaccia della riga di comando di Docker, si usa il comando `docker-compose up`.</span><span class="sxs-lookup"><span data-stu-id="0718c-346">To run a multi-container application with the Docker CLI, you use the `docker-compose up` command.</span></span> <span data-ttu-id="0718c-347">Questo comando usa il file **docker-compose.yml** disponibile a livello di soluzione per distribuire un'applicazione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="0718c-347">This command uses the **docker-compose.yml** file that you have at the solution level to deploy a multi-container application.</span></span> <span data-ttu-id="0718c-348">La figura 5-11 illustra i risultati che si ottengono quando si esegue il comando dalla directory principale della soluzione, che contiene il file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="0718c-348">Figure 5-11 shows the results when running the command from your main solution directory, which contains the docker-compose.yml file.</span></span>

![Schermata visualizzata quando si esegue il comando docker-compose up](./media/image15.png)

<span data-ttu-id="0718c-350">**Figura 5-11**.</span><span class="sxs-lookup"><span data-stu-id="0718c-350">**Figure 5-11**.</span></span> <span data-ttu-id="0718c-351">Esempio di risultati ottenuti eseguendo il comando docker-compose up</span><span class="sxs-lookup"><span data-stu-id="0718c-351">Example results when running the docker-compose up command</span></span>

<span data-ttu-id="0718c-352">Dopo l'esecuzione del comando docker-compose up, l'applicazione e i contenitori correlati vengono distribuiti nell'host Docker, come illustra la figura 5-10.</span><span class="sxs-lookup"><span data-stu-id="0718c-352">After the docker-compose up command runs, the application and its related containers are deployed into your Docker host, as depicted in Figure 5-10.</span></span>

#### <a name="using-visual-studio"></a><span data-ttu-id="0718c-353">Utilizzo di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0718c-353">Using Visual Studio</span></span>

<span data-ttu-id="0718c-354">Eseguire un'applicazione a più contenitori con Visual Studio 2017 è molto semplice.</span><span class="sxs-lookup"><span data-stu-id="0718c-354">Running a multi-container application using Visual Studio 2017 can't get any simpler.</span></span> <span data-ttu-id="0718c-355">Basta premere **CTRL+F5** per l'esecuzione o **F5** per il debug, come di consueto, impostando il progetto **docker-compose** come progetto di avvio.</span><span class="sxs-lookup"><span data-stu-id="0718c-355">You just press **Ctrl-F5** to run or **F5** to debug, as usual, setting up the **docker-compose** project as the startup project.</span></span>  <span data-ttu-id="0718c-356">Visual Studio gestisce tutte le impostazioni necessarie, quindi è possibile creare punti di interruzione come di consueto ed eseguire il debug del risultato finale, ovvero processi indipendenti in esecuzione in "server remoti".</span><span class="sxs-lookup"><span data-stu-id="0718c-356">Visual Studio handles all needed setup, so you can create breakpoints as usual and debug what finally become independent processes running in "remote servers", just like that.</span></span>

<span data-ttu-id="0718c-357">Come accennato in precedenza, ogni volta che si aggiungere il supporto Docker a un progetto all'interno di una soluzione, il progetto è configurato nel file docker-compose.yml globale, a livello di soluzione, che consente di eseguire l'intera soluzione o di eseguirne il debug in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="0718c-357">As mentioned before, each time you add Docker solution support to a project within a solution, that project is configured in the global (solution-level) docker-compose.yml file, which lets you run or debug the whole solution at once.</span></span> <span data-ttu-id="0718c-358">Visual Studio avvia un solo contenitore per ogni progetto che ha il supporto Docker abilitato ed esegue automaticamente tutti i passaggi interni, ovvero pubblicazione dotnet, compilazione docker, ecc.</span><span class="sxs-lookup"><span data-stu-id="0718c-358">Visual Studio will start one container for each project that has Docker solution support enabled, and perform all the internal steps for you (dotnet publish, docker build, etc.).</span></span>

<span data-ttu-id="0718c-359">Per avere un'idea di tutta la complessità, esaminare il file:</span><span class="sxs-lookup"><span data-stu-id="0718c-359">If you want to take a peek at all the drudgery, take a look at the file:</span></span>

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

<span data-ttu-id="0718c-360">La cosa importante è che, come illustrato nella figura 5-12, in Visual Studio 2017 è presente un ulteriore comando **Docker** per il tasto funzione F5.</span><span class="sxs-lookup"><span data-stu-id="0718c-360">The important point here is that, as shown in Figure 5-12, in Visual Studio 2017 there is an additional **Docker** command for the F5 key action.</span></span> <span data-ttu-id="0718c-361">Questa opzione consente di eseguire un'applicazione a più contenitori o di eseguirne il debug eseguendo tutti i contenitori definiti nei file docker-compose.yml a livello di soluzione.</span><span class="sxs-lookup"><span data-stu-id="0718c-361">This option lets you run or debug a multi-container application by running all the containers that are defined in the docker-compose.yml files at the solution level.</span></span> <span data-ttu-id="0718c-362">Grazie alla capacità di eseguire il debug delle soluzioni a più contenitori, è possibile impostare più punti di interruzione, ciascuno in un progetto (contenitore) diverso, e durante il debug da Visual Studio l'esecuzione viene arrestata in corrispondenza dei punti di interruzione definiti in progetti diversi ed eseguiti in contenitori diversi.</span><span class="sxs-lookup"><span data-stu-id="0718c-362">The ability to debug multiple-container solutions means that you can set several breakpoints, each breakpoint in a different project (container), and while debugging from Visual Studio you will stop at breakpoints defined in different projects and running on different containers.</span></span>

![Barra degli strumenti di debug di Visual Studio che esegue il progetto docker-compose](./media/image16.png)

<span data-ttu-id="0718c-364">**Figura 5-12**.</span><span class="sxs-lookup"><span data-stu-id="0718c-364">**Figure 5-12**.</span></span> <span data-ttu-id="0718c-365">Esecuzione di applicazioni a più contenitori in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0718c-365">Running multi-container apps in Visual Studio 2017</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0718c-366">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0718c-366">Additional resources</span></span>

- <span data-ttu-id="0718c-367">**Distribuire un contenitore ASP.NET a un host Docker remoto** \\</span><span class="sxs-lookup"><span data-stu-id="0718c-367">**Deploy an ASP.NET container to a remote Docker host** \\</span></span>
  [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a><span data-ttu-id="0718c-368">Una nota sul test e la distribuzione con agenti di orchestrazione</span><span class="sxs-lookup"><span data-stu-id="0718c-368">A note about testing and deploying with orchestrators</span></span>

<span data-ttu-id="0718c-369">I comandi docker-compose up e docker run, o l'esecuzione e il debug dei contenitori in Visual Studio, sono adeguati per eseguire test sui contenitori nell'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="0718c-369">The docker-compose up and docker run commands (or running and debugging the containers in Visual Studio) are adequate for testing containers in your development environment.</span></span> <span data-ttu-id="0718c-370">È consigliabile non usare questo approccio per le distribuzioni di produzione, in cui la destinazione deve essere un agente di orchestrazione, ad esempio [Kubernetes](https://kubernetes.io/) o [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span><span class="sxs-lookup"><span data-stu-id="0718c-370">But you should not use this approach for production deployments, where you should target orchestrators like [Kubernetes](https://kubernetes.io/) or [Service Fabric](https://azure.microsoft.com/services/service-fabric/).</span></span> <span data-ttu-id="0718c-371">Se si usa Kubernetes, è necessario usare [pod](https://kubernetes.io/docs/concepts/workloads/pods/pod/) per organizzare i contenitori e [servizi](https://kubernetes.io/docs/concepts/services-networking/service/) per collegarli in rete.</span><span class="sxs-lookup"><span data-stu-id="0718c-371">If you're using Kubernetes you have to use [pods](https://kubernetes.io/docs/concepts/workloads/pods/pod/) to organize containers and [services](https://kubernetes.io/docs/concepts/services-networking/service/) to network them.</span></span> <span data-ttu-id="0718c-372">Si usano anche le [distribuzioni](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) per organizzare la creazione e la modifica dei pod.</span><span class="sxs-lookup"><span data-stu-id="0718c-372">You also use [deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) to organize pod creation and modification.</span></span>

![6 - Testare l'app o i microservizi](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a><span data-ttu-id="0718c-374">Passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="0718c-374">Step 6.</span></span> <span data-ttu-id="0718c-375">Testare l'applicazione Docker usando l'host Docker locale</span><span class="sxs-lookup"><span data-stu-id="0718c-375">Test your Docker application using your local Docker host</span></span>

<span data-ttu-id="0718c-376">Questo passaggio varia in base a ciò che l'applicazione sta facendo.</span><span class="sxs-lookup"><span data-stu-id="0718c-376">This step will vary depending on what your application is doing.</span></span> <span data-ttu-id="0718c-377">In un'applicazione Web .NET Core semplice che viene distribuita come contenitore o servizio singolo è possibile accedere al servizio aprendo un browser nell'host Docker e passando a quel sito, come illustrato nella figura 5-13.</span><span class="sxs-lookup"><span data-stu-id="0718c-377">In a simple .NET Core Web application that is deployed as a single container or service, you can access the service by opening a browser on the Docker host and navigating to that site, as shown in Figure 5-13.</span></span> <span data-ttu-id="0718c-378">Se la configurazione nel Dockerfile abbina il contenitore a una porta dell'host diversa dalla 80, includere la porta host nell'URL.</span><span class="sxs-lookup"><span data-stu-id="0718c-378">(If the configuration in the Dockerfile maps the container to a port on the host that is anything other than 80, include the host port in the URL.)</span></span>

![Visualizzazione browser di una risposta dell'endpoint API](./media/image18.png)

<span data-ttu-id="0718c-380">**Figura 5-13**.</span><span class="sxs-lookup"><span data-stu-id="0718c-380">**Figure 5-13**.</span></span> <span data-ttu-id="0718c-381">Esempio di test dell'applicazione Docker in locale mediante localhost</span><span class="sxs-lookup"><span data-stu-id="0718c-381">Example of testing your Docker application locally using localhost</span></span>

<span data-ttu-id="0718c-382">Se localhost non punta all'IP dell'host Docker, come accade per impostazione predefinita quando si usa Docker CE, per passare al servizio usare l'indirizzo IP della scheda di rete del computer.</span><span class="sxs-lookup"><span data-stu-id="0718c-382">If localhost is not pointing to the Docker host IP (by default, when using Docker CE, it should), to navigate to your service, use the IP address of your machine's network card.</span></span>

<span data-ttu-id="0718c-383">Si noti che questo URL nel browser usa la porta 80 per lo specifico contenitore di esempio di cui si tratta.</span><span class="sxs-lookup"><span data-stu-id="0718c-383">Note that this URL in the browser uses port 80 for the particular container example being discussed.</span></span> <span data-ttu-id="0718c-384">Tuttavia internamente le richieste vengono reindirizzate alla porta 5000 perché è stato distribuito in questo modo con il comando docker run, come illustrato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="0718c-384">However, internally the requests are being redirected to port 5000, because that was how it was deployed with the docker run command, as explained in a previous step.</span></span>

<span data-ttu-id="0718c-385">È anche possibile testare l'applicazione usando curl dal terminale, come illustrato nella figura 5-14.</span><span class="sxs-lookup"><span data-stu-id="0718c-385">You can also test the application using curl from the terminal, as shown in Figure 5-14.</span></span> <span data-ttu-id="0718c-386">In un'installazione di Docker in Windows, il valore IP dell'host Docker predefinito è sempre 10.0.75.1 in aggiunta all'indirizzo IP effettivo del computer.</span><span class="sxs-lookup"><span data-stu-id="0718c-386">In a Docker installation on Windows, the default Docker Host IP is always 10.0.75.1 in addition to your machine's actual IP address.</span></span>

![Visualizzazione schermata di una risposta dell'endpoint API con curl](./media/image19.png)

<span data-ttu-id="0718c-388">**Figura 5-14**.</span><span class="sxs-lookup"><span data-stu-id="0718c-388">**Figure 5-14**.</span></span> <span data-ttu-id="0718c-389">Esempio di test dell'applicazione Docker in locale mediante curl</span><span class="sxs-lookup"><span data-stu-id="0718c-389">Example of testing your Docker application locally using curl</span></span>

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a><span data-ttu-id="0718c-390">Test e debug di contenitori con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0718c-390">Testing and debugging containers with Visual Studio 2017</span></span>

<span data-ttu-id="0718c-391">Quando si eseguono contenitori e se ne esegue il debug con Visual Studio 2017, è possibile eseguire il debug dell'applicazione .NET nello stesso modo che si userebbe per l'esecuzione senza contenitori.</span><span class="sxs-lookup"><span data-stu-id="0718c-391">When running and debugging the containers with Visual Studio 2017, you can debug the .NET application in much the same way as you would when running without containers.</span></span>

### <a name="testing-and-debugging-without-visual-studio"></a><span data-ttu-id="0718c-392">Test e debug senza Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0718c-392">Testing and debugging without Visual Studio</span></span>

<span data-ttu-id="0718c-393">Se si sviluppa usando l'approccio editor/CLI, eseguire il debug dei contenitori è più difficile ed è preferibile farlo usando la generazione di tracce.</span><span class="sxs-lookup"><span data-stu-id="0718c-393">If you're developing using the editor/CLI approach, debugging containers is more difficult and you will want to debug by generating traces.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0718c-394">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0718c-394">Additional resources</span></span>

- <span data-ttu-id="0718c-395">**Debug delle applicazioni in un contenitore Docker locale** \\</span><span class="sxs-lookup"><span data-stu-id="0718c-395">**Debugging apps in a local Docker container** \\</span></span>
  [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

- <span data-ttu-id="0718c-396">**Steve Lasker. Compilare, eseguire il debug e distribuire app ASP.NET Core con Docker.**</span><span class="sxs-lookup"><span data-stu-id="0718c-396">**Steve Lasker. Build, Debug, Deploy ASP.NET Core Apps with Docker.**</span></span> <span data-ttu-id="0718c-397">Video.</span><span class="sxs-lookup"><span data-stu-id="0718c-397">Video.</span></span> \
  [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a><span data-ttu-id="0718c-398">Flusso di lavoro semplificato per lo sviluppo di contenitori con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0718c-398">Simplified workflow when developing containers with Visual Studio</span></span>

<span data-ttu-id="0718c-399">Il flusso di lavoro quando si usa Visual Studio è molto più semplice rispetto all'uso dell'approccio editor/CLI.</span><span class="sxs-lookup"><span data-stu-id="0718c-399">Effectively, the workflow when using Visual Studio is a lot simpler than if you use the editor/CLI approach.</span></span> <span data-ttu-id="0718c-400">La maggior parte dei passaggi richiesti da Docker correlati ai file Dockerfile e docker-compose.yml sono nascosti o semplificati da Visual Studio, come illustrato nella figura 5-15.</span><span class="sxs-lookup"><span data-stu-id="0718c-400">Most of the steps required by Docker related to the Dockerfile and docker-compose.yml files are hidden or simplified by Visual Studio, as shown in Figure 5-15.</span></span>

![Flusso di lavoro semplificato con i contenitori in Visual Studio: 1 - Scrivere il codice dell'app, 2 - Aggiungere il supporto Docker ai progetti (solo una volta), 3 - Eseguire l'app contenitore o docker-compose, 4 - Testare l'app o i microservizi, 5 - Eseguire il push al repository e ripetere.](./media/image20.png)

<span data-ttu-id="0718c-402">**Figura 5-15**.</span><span class="sxs-lookup"><span data-stu-id="0718c-402">**Figure 5-15**.</span></span> <span data-ttu-id="0718c-403">Flusso di lavoro semplificato per lo sviluppo con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="0718c-403">Simplified workflow when developing with Visual Studio</span></span>

<span data-ttu-id="0718c-404">Inoltre è sufficiente eseguire una sola volta il passaggio 2, ovvero l'aggiunta del supporto Docker ai progetti.</span><span class="sxs-lookup"><span data-stu-id="0718c-404">In addition, you need to perform step 2 (adding Docker support to your projects) just once.</span></span> <span data-ttu-id="0718c-405">Pertanto il flusso di lavoro è simile alle attività di sviluppo normale quando si usa .NET per qualsiasi altro tipo di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="0718c-405">Therefore, the workflow is similar to your usual development tasks when using .NET for any other development.</span></span> <span data-ttu-id="0718c-406">È necessario sapere cosa succede dietro le quinte, ad esempio il processo di creazione delle immagini, le immagini di base in uso, la distribuzione dei contenitori e così via. In alcuni casi è anche necessario modificare il Dockerfile o il file docker-compose.yml per personalizzare i comportamenti.</span><span class="sxs-lookup"><span data-stu-id="0718c-406">You need to know what is going on under the covers (the image build process, what base images you're using, deployment of containers, etc.) and sometimes you will also need to edit the Dockerfile or docker-compose.yml file to customize behaviors.</span></span> <span data-ttu-id="0718c-407">Se si usa Visual Studio la maggior parte del lavoro viene notevolmente semplificata e la produttività è maggiore.</span><span class="sxs-lookup"><span data-stu-id="0718c-407">But most of the work is greatly simplified by using Visual Studio, making you a lot more productive.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="0718c-408">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0718c-408">Additional resources</span></span>

- <span data-ttu-id="0718c-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017** \ (Sviluppo di Docker .NET con Visual Studio 2017)</span><span class="sxs-lookup"><span data-stu-id="0718c-409">**Steve Lasker. .NET Docker Development with Visual Studio 2017** \\</span></span>
  [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a><span data-ttu-id="0718c-410">Uso dei comandi di PowerShell in un Dockerfile per configurare contenitori Windows</span><span class="sxs-lookup"><span data-stu-id="0718c-410">Using PowerShell commands in a Dockerfile to set up Windows Containers</span></span> 

<span data-ttu-id="0718c-411">I [contenitori Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index) consentono di convertire applicazioni Windows esistenti in immagini Docker e distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker.</span><span class="sxs-lookup"><span data-stu-id="0718c-411">[Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/index) allow you to convert your existing Windows applications into Docker images and deploy them with the same tools as the rest of the Docker ecosystem.</span></span> <span data-ttu-id="0718c-412">Per usare i contenitori Windows si eseguono i comandi di PowerShell in Dockerfile, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0718c-412">To use Windows Containers, you run PowerShell commands in the Dockerfile, as shown in the following example:</span></span>

```Dockerfile
FROM microsoft/windowsservercore
LABEL Description="IIS" Vendor="Microsoft" Version="10"
RUN powershell -Command Add-WindowsFeature Web-Server
CMD [ "ping", "localhost", "-t" ]
```

<span data-ttu-id="0718c-413">In questo caso si usa un'immagine di base di Windows Server Core (impostazione FROM) e si installa IIS con un comando di PowerShell (impostazione RUN).</span><span class="sxs-lookup"><span data-stu-id="0718c-413">In this case, we are using a Windows Server Core base image (the FROM setting) and installing IIS with a PowerShell command (the RUN setting).</span></span> <span data-ttu-id="0718c-414">In modo analogo è possibile usare i comandi di PowerShell anche per configurare componenti aggiuntivi come ASP.NET 4. x, .NET 4.6 o qualsiasi altro software Windows.</span><span class="sxs-lookup"><span data-stu-id="0718c-414">In a similar way, you could also use PowerShell commands to set up additional components like ASP.NET 4.x, .NET 4.6, or any other Windows software.</span></span> <span data-ttu-id="0718c-415">Ad esempio il comando seguente in un Dockerfile configura ASP.NET 4.5:</span><span class="sxs-lookup"><span data-stu-id="0718c-415">For example, the following command in a Dockerfile sets up ASP.NET 4.5:</span></span>

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a><span data-ttu-id="0718c-416">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0718c-416">Additional resources</span></span>

- <span data-ttu-id="0718c-417">**aspnet-docker/Dockerfile.**</span><span class="sxs-lookup"><span data-stu-id="0718c-417">**aspnet-docker/Dockerfile.**</span></span> <span data-ttu-id="0718c-418">Esempi di comandi di PowerShell eseguibili da Dockerfile per includere funzionalità di Windows.\\</span><span class="sxs-lookup"><span data-stu-id="0718c-418">Example PowerShell commands to run from dockerfiles to include Windows features.\\</span></span>
  [*https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile)

>[!div class="step-by-step"]
><span data-ttu-id="0718c-419">[Precedente](index.md)
>[Successivo](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="0718c-419">[Previous](index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
