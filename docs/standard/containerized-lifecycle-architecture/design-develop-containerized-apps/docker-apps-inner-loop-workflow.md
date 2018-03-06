---
title: Flusso di lavoro di sviluppo ciclo interno per le app di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 632c04507c1478238a5dc2573542f8c88bae2a51
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2018
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="35cf3-104">Flusso di lavoro di sviluppo ciclo interno per le app di Docker</span><span class="sxs-lookup"><span data-stu-id="35cf3-104">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="35cf3-105">Prima di attivare il flusso di lavoro ciclo esterno spanning DevOps l'intero ciclo, inizia in ogni computer dello sviluppatore, la codifica app stessa, usando le lingue preferite o piattaforme e testarlo in locale (figura 4-14).</span><span class="sxs-lookup"><span data-stu-id="35cf3-105">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="35cf3-106">Ma in ogni caso, sarà necessario un punto molto importante in comune, indipendentemente da quali lingua, un framework o piattaforme prescelto.</span><span class="sxs-lookup"><span data-stu-id="35cf3-106">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="35cf3-107">In questo flusso di lavoro specifico, sempre sviluppo e verifica i contenitori di Docker, ma in locale.</span><span class="sxs-lookup"><span data-stu-id="35cf3-107">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="35cf3-108">Contesto di sviluppo interna ciclo figura 4-14:</span><span class="sxs-lookup"><span data-stu-id="35cf3-108">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="35cf3-109">Il contenitore o l'istanza di un'immagine Docker conterrà questi componenti:</span><span class="sxs-lookup"><span data-stu-id="35cf3-109">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="35cf3-110">Una selezione del sistema operativo (ad esempio, una distribuzione di Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="35cf3-110">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="35cf3-111">File aggiunti dallo sviluppatore (ad esempio, file binari dell'app)</span><span class="sxs-lookup"><span data-stu-id="35cf3-111">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="35cf3-112">Configurazione (ad esempio, le impostazioni di ambiente e le dipendenze)</span><span class="sxs-lookup"><span data-stu-id="35cf3-112">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="35cf3-113">Istruzioni per quali processi eseguiti da Docker</span><span class="sxs-lookup"><span data-stu-id="35cf3-113">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="35cf3-114">È possibile impostare il flusso di lavoro di sviluppo ciclo interno che utilizza Docker del processo (descritto nella sezione successiva).</span><span class="sxs-lookup"><span data-stu-id="35cf3-114">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="35cf3-115">Prendere in considerazione che i passaggi iniziali per configurare l'ambiente non è incluso, poiché è necessario eseguire questa operazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="35cf3-115">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="35cf3-116">La creazione di una singola app in un contenitore Docker con codice di Visual Studio e CLI di Docker</span><span class="sxs-lookup"><span data-stu-id="35cf3-116">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="35cf3-117">Le applicazioni sono composti dal proprio servizi più librerie aggiuntive (dipendenze).</span><span class="sxs-lookup"><span data-stu-id="35cf3-117">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="35cf3-118">Figura 4-15 mostra i passaggi di base che in genere è necessario eseguire quando si compila un'app di Docker, seguita da una descrizione dettagliata di ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="35cf3-118">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="35cf3-119">Figura 4-15: flusso di lavoro generale per il ciclo di vita delle applicazioni di Docker contenitore con Docker CLI</span><span class="sxs-lookup"><span data-stu-id="35cf3-119">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="35cf3-120">Passaggio 1: Avviare la codifica nel codice di Visual Studio e creare la linea di base iniziale/servizio app</span><span class="sxs-lookup"><span data-stu-id="35cf3-120">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="35cf3-121">Il modo in cui si sviluppa l'applicazione è molto simile a quello che eseguire questa operazione senza Docker.</span><span class="sxs-lookup"><span data-stu-id="35cf3-121">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="35cf3-122">La differenza è che durante lo sviluppo, si distribuisce e si verifica l'applicazione o i servizi in esecuzione all'interno di contenitori di Docker inseriti nell'ambiente locale (ad esempio, una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="35cf3-122">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="35cf3-123">**Impostazione dell'ambiente locale**</span><span class="sxs-lookup"><span data-stu-id="35cf3-123">**Setting up your local environment**</span></span>

<span data-ttu-id="35cf3-124">Con le versioni più recenti di Docker per Mac e Windows, è più semplice che mai per sviluppare applicazioni di Docker e l'installazione è semplice.</span><span class="sxs-lookup"><span data-stu-id="35cf3-124">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="35cf3-125">**Altre informazioni** per istruzioni sulla configurazione di Docker per Windows, visitare [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="35cf3-125">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="35cf3-126">Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="35cf3-126">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="35cf3-127">Inoltre, è necessario un editor di codice in modo che è effettivamente possibile sviluppare l'applicazione durante l'utilizzo di Docker CLI.</span><span class="sxs-lookup"><span data-stu-id="35cf3-127">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="35cf3-128">Microsoft fornisce codice di Visual Studio, che è un editor di codice semplice che è supportato in Mac, Windows e Linux e fornisce IntelliSense con [il supporto per molte lingue](https://code.visualstudio.com/docs/languages/overview) (JavaScript, la maggior parte, Python, Ruby, Java, Go e .NET linguaggi moderni), [debug](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [supporto delle estensioni di](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="35cf3-128">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="35cf3-129">Questo editor è ideale per gli sviluppatori Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="35cf3-129">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="35cf3-130">In Windows, è anche possibile usare l'applicazione di Visual Studio completo.</span><span class="sxs-lookup"><span data-stu-id="35cf3-130">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="35cf3-131">**Altre informazioni** per istruzioni sull'installazione di Visual Studio per Windows, Mac o Linux, vedere [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span><span class="sxs-lookup"><span data-stu-id="35cf3-131">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to [http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).</span></span>

<span data-ttu-id="35cf3-132">È possibile lavorare con Docker CLI e scrivere il codice utilizzando qualsiasi editor di codice, ma se si utilizza codice di Visual Studio, rende facile autore Dockerfile e docker compose.yml file nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="35cf3-132">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="35cf3-133">Inoltre, è possibile eseguire attività di codice di Visual Studio dall'IDE che richiederà script che può essere in esecuzione di operazioni elaborate tramite Docker CLI sotto.</span><span class="sxs-lookup"><span data-stu-id="35cf3-133">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="35cf3-134">Codice di Visual Studio viene fornito da un'estensione, che è necessario installare.</span><span class="sxs-lookup"><span data-stu-id="35cf3-134">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="35cf3-135">A tale scopo, premere Ctrl + MAIUSC + P, digitare **ext installare**, quindi eseguire le estensioni: comando per l'installazione di estensione per visualizzare l'elenco di estensioni di Marketplace.</span><span class="sxs-lookup"><span data-stu-id="35cf3-135">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="35cf3-136">Digitare quindi **docker** per filtrare i risultati e quindi selezionare il Dockerfile e Docker comporre File (yml) estensione del supporto tecnico, come illustrato nella figura 4-16.</span><span class="sxs-lookup"><span data-stu-id="35cf3-136">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="35cf3-137">Figura 4-16: installazione dell'estensione Docker nel codice di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35cf3-137">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="35cf3-138">Passaggio 2: Creare un DockerFile correlato a un'immagine esistente (normale del sistema operativo o ambienti di sviluppo come Ruby, Node.js e .NET Core)</span><span class="sxs-lookup"><span data-stu-id="35cf3-138">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="35cf3-139">È necessario un DockerFile all'immagine personalizzata da compilare per contenitore da distribuire, pertanto, se l'app è costituita da un singolo servizio personalizzato, è necessario un DockerFile singolo.</span><span class="sxs-lookup"><span data-stu-id="35cf3-139">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="35cf3-140">Tuttavia, se l'app è costituita da più servizi (come in un'architettura di microservizi), è necessario un Dockerfile per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="35cf3-140">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="35cf3-141">DockerFile viene in genere posizionato all'interno della cartella radice dell'applicazione o del servizio e contiene i comandi necessari in modo che Docker sia in grado di configurare ed eseguire tale app o un servizio.</span><span class="sxs-lookup"><span data-stu-id="35cf3-141">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="35cf3-142">È possibile creare i DockerFile e aggiungerlo al progetto insieme al codice (node.js, .NET Core, e così via), o, se si ha familiarità con l'ambiente, esaminare la descrizione seguente.</span><span class="sxs-lookup"><span data-stu-id="35cf3-142">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="35cf3-143">È possibile utilizzare uno strumento da riga di comando denominato [, docker](https://github.com/Microsoft/generator-docker), quali strutture file dal progetto in linguaggio si sceglie e aggiunge i file di configurazione di Docker necessari.</span><span class="sxs-lookup"><span data-stu-id="35cf3-143">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="35cf3-144">In pratica, per assistere gli sviluppatori di introduzione, viene creato il DockerFile appropriato, docker compose.yml e altri script associato per compilare ed eseguire i contenitori di Docker.</span><span class="sxs-lookup"><span data-stu-id="35cf3-144">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="35cf3-145">Il generatore yeoman richiederà con alcune domande, porre l'host del contenitore selezionato sviluppo linguaggio e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="35cf3-145">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![messaggio docker](./media/image21.png)

<span data-ttu-id="35cf3-147">Ad esempio, nella figura 4-17 mostra due schermate dai terminali in Windows e su un Mac, in entrambi i casi, in esecuzione, docker, che genera i codice progetti di esempio (attualmente .NET Core, Golang e Node.js come le lingue supportate) già configurati per l'utilizzo in parte superiore di Docker.</span><span class="sxs-lookup"><span data-stu-id="35cf3-147">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="35cf3-148">Figura 4-17:, docker strumento di comando in Windows (a sinistra) e su un Mac</span><span class="sxs-lookup"><span data-stu-id="35cf3-148">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="35cf3-149">Figura 4-18 viene presentato un esempio di utilizzo, docker dopo aver creato un progetto esistente di .NET Core in grado di essere scaffolding.</span><span class="sxs-lookup"><span data-stu-id="35cf3-149">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="35cf3-150">Figura 4-18:, docker con una versione esistente di .NET Core progetto sul posto</span><span class="sxs-lookup"><span data-stu-id="35cf3-150">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="35cf3-151">Del dockerfile, specificare quale immagine di Docker base sarà possibile usare (ad esempio tramite "da microsoft/dotnet:1.0.0-core").</span><span class="sxs-lookup"><span data-stu-id="35cf3-151">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="35cf3-152">Verrà compilato in genere l'immagine personalizzata nella parte superiore di un'immagine di base che è possibile ottenere da qualsiasi repository ufficiale al [Registro di sistema Hub Docker](https://hub.docker.com/) (ad esempio un [immagine per .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o uno [per Node.js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="35cf3-152">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="35cf3-153">***Opzione a: usare un'immagine Docker ufficiale esistente***</span><span class="sxs-lookup"><span data-stu-id="35cf3-153">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="35cf3-154">L'utilizzo di un repository ufficiale di uno stack di lingua con un numero di versione garantisce che la stessa funzionalità del linguaggio disponibili in tutti i computer (tra cui sviluppo, test e produzione).</span><span class="sxs-lookup"><span data-stu-id="35cf3-154">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="35cf3-155">Di seguito è riportato un esempio DockerFile per un contenitore di .NET Core:</span><span class="sxs-lookup"><span data-stu-id="35cf3-155">Following is a sample DockerFile for a .NET Core container:</span></span>

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="35cf3-156">In questo caso, utilizza la versione 1.0.1 dell'immagine di ASP.NET Core Docker ufficiale per Linux denominato microsoft/aspnetcore:1.0.1.</span><span class="sxs-lookup"><span data-stu-id="35cf3-156">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="35cf3-157">Per ulteriori dettagli, consultare il [pagina ASP.NET Core Docker immagine](https://hub.docker.com/r/microsoft/aspnetcore/) e [.NET Core Docker immagine](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="35cf3-157">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="35cf3-158">È inoltre possibile utilizzare un'altra immagine comparabile come nodo: 4-onbuild per Node.js o molte altre immagini preconfigurate per i linguaggi di sviluppo, sono disponibili all'indirizzo [Hub Docker](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="35cf3-158">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="35cf3-159">Nel documento DockerFile, è necessario anche indicano a Docker di in ascolto sulla porta TCP che verrà utilizzato in fase di esecuzione (ad esempio la porta 80).</span><span class="sxs-lookup"><span data-stu-id="35cf3-159">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="35cf3-160">Sono presenti altre righe di configurazione che è possibile aggiungere in DockerFile a seconda del linguaggio/framework in uso, in modo Docker sia in grado di eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="35cf3-160">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="35cf3-161">Ad esempio, è necessario alla riga di punto di ingresso \["dotnet", "MyCustomMicroservice.dll"\] per eseguire un'applicazione .NET Core, anche se è possibile avere più varianti a seconda di approccio per compilare ed eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="35cf3-161">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="35cf3-162">Se si utilizza per compilare ed eseguire l'app .NET SDK e dotnet CLI, sarebbe leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="35cf3-162">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="35cf3-163">La riga inferiore è che la riga di punto di ingresso più righe aggiuntive sarà diverse a seconda della lingua/piattaforma che scelto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="35cf3-163">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="35cf3-164">**Altre informazioni** per informazioni sulla creazione di immagini Docker per le applicazioni .NET Core, passare a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="35cf3-164">**More info** For information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>

<span data-ttu-id="35cf3-165">Per ulteriori informazioni sulla creazione di immagini personalizzate, passare a [https://docs.docker.com/engine/ \esercitazioni/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="35cf3-165">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="35cf3-166">**Repository di immagini multipiattaforma**</span><span class="sxs-lookup"><span data-stu-id="35cf3-166">**Multiplatform image repositories**</span></span>

<span data-ttu-id="35cf3-167">Come contenitori di Windows più diffonderanno, un unico archivio può contenere le varianti della piattaforma, ad esempio un'immagine Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="35cf3-167">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="35cf3-168">Si tratta di una nuova funzionalità presto in Docker che rende possibile per i fornitori di utilizzare un unico repository per coprire più piattaforme, ad esempio [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, è disponibile a DockerHub del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="35cf3-168">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="35cf3-169">La funzionalità è attiva, questa immagine il pull da un host Windows eseguirà il pull la variante di Windows, mentre lo stesso nome di immagine il pull da un host Linux estrarrà la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="35cf3-169">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="35cf3-170">***Opzione b: creare l'immagine di base da zero***</span><span class="sxs-lookup"><span data-stu-id="35cf3-170">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="35cf3-171">È possibile creare la propria immagine di base di Docker da zero, come illustrato in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) da Docker.</span><span class="sxs-lookup"><span data-stu-id="35cf3-171">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="35cf3-172">Si tratta di uno scenario che probabilmente non è adatto alle proprie esigenze se si sta avviando solo con Docker, ma se si desidera impostare i bit specifici della propria immagine di base, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="35cf3-172">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="35cf3-173">Passaggio 3: Creare immagini personalizzate Docker incorporamento del servizio in essa contenuti</span><span class="sxs-lookup"><span data-stu-id="35cf3-173">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="35cf3-174">Per ogni servizio personalizzata che comprende l'app, è necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="35cf3-174">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="35cf3-175">Se l'app è costituito da un singolo servizio o un'app web, è necessario solo una singola immagine.</span><span class="sxs-lookup"><span data-stu-id="35cf3-175">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="35cf3-176">Quando si prende in considerazione il "ciclo esterno DevOps flusso di lavoro", le immagini verranno create da un processo di compilazione automatizzato ogni volta che si esegue il push del codice sorgente in un repository Git (integrazione continua) in modo verranno create le immagini in tale ambiente globale dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="35cf3-176">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="35cf3-177">Tuttavia, prima che il passaggio alla route ciclo esterno, è necessario garantire che l'applicazione di Docker effettivamente funziona correttamente in modo da essi non inserire il codice che potrebbe non funzionare correttamente al sistema di controllo di origine (Git e così via).</span><span class="sxs-lookup"><span data-stu-id="35cf3-177">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="35cf3-178">Pertanto, ogni sviluppatore deve prima eseguire l'intero processo di ciclo interna per i test in locale e continuare a sviluppare fino a quando non si desidera il push di una funzionalità di completamento o modificare per il controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="35cf3-178">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="35cf3-179">Per creare un'immagine nell'ambiente locale e l'utilizzo di DockerFile, è possibile utilizzare il comando di compilazione docker, come illustrato nella figura 4-19 (è anche possibile eseguire comporre docker backup - compilazione per le applicazioni composte da diversi contenitori e servizi).</span><span class="sxs-lookup"><span data-stu-id="35cf3-179">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="35cf3-180">Figura 4-19: compilazione di docker in esecuzione</span><span class="sxs-lookup"><span data-stu-id="35cf3-180">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="35cf3-181">Facoltativamente, anziché eseguire direttamente docker compilazione dalla cartella del progetto, è innanzitutto possibile generare una cartella distribuibile con le librerie .NET necessarie tramite l'esecuzione dotnet comando pubblica e quindi eseguire la compilazione docker.</span><span class="sxs-lookup"><span data-stu-id="35cf3-181">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="35cf3-182">In questo esempio, si crea un'immagine di Docker con il nome cesardl/netcore-webapi-microservizio-docker: first (: per primo è un tag, ad esempio una versione specifica).</span><span class="sxs-lookup"><span data-stu-id="35cf3-182">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="35cf3-183">È possibile eseguire questo passaggio per ogni immagine personalizzata, che è necessario creare per l'applicazione di Docker composto con diversi contenitori.</span><span class="sxs-lookup"><span data-stu-id="35cf3-183">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="35cf3-184">È possibile trovare immagini esistenti nel repository locale (computer di sviluppo) tramite docker immagini comando, come illustrato nella figura 4-20.</span><span class="sxs-lookup"><span data-stu-id="35cf3-184">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="35cf3-185">Figura 4-20: visualizzazione di immagini esistenti utilizzando le immagini docker</span><span class="sxs-lookup"><span data-stu-id="35cf3-185">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="35cf3-186">Passaggio 4: (Facoltativo) definire i servizi in docker compose.yml quando si compila un'app di Docker composta con più servizi</span><span class="sxs-lookup"><span data-stu-id="35cf3-186">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="35cf3-187">Con il file docker compose.yml è possibile definire un set di servizi correlati da distribuire come un'applicazione composta con i comandi di distribuzione illustrati nella sezione Passaggio successiva.</span><span class="sxs-lookup"><span data-stu-id="35cf3-187">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="35cf3-188">È necessario creare il file in principale o una cartella della soluzione radice; deve essere un contenuto simile al file docker compose.yml seguente:</span><span class="sxs-lookup"><span data-stu-id="35cf3-188">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

```yml
version: '2'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

<span data-ttu-id="35cf3-189">In questo caso particolare, questo file definisce due servizi: il servizio web (il servizio personalizzato) e il servizio di redis (servizio di cache più diffusi).</span><span class="sxs-lookup"><span data-stu-id="35cf3-189">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="35cf3-190">Ogni servizio verrà distribuito come un contenitore, pertanto è necessario utilizzare un'immagine Docker concreta per ogni.</span><span class="sxs-lookup"><span data-stu-id="35cf3-190">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="35cf3-191">Per questo servizio web specifico, l'immagine sarà necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="35cf3-191">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="35cf3-192">Compilazione del dockerfile nella directory corrente</span><span class="sxs-lookup"><span data-stu-id="35cf3-192">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="35cf3-193">Inoltrare la porta 80 del contenitore su porta 81 del computer host esposta</span><span class="sxs-lookup"><span data-stu-id="35cf3-193">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="35cf3-194">Montare la directory del progetto dell'host /code all'interno del contenitore, rendendo possibile modificare il codice senza dover ricreare l'immagine</span><span class="sxs-lookup"><span data-stu-id="35cf3-194">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="35cf3-195">Collegare il servizio web per il servizio di redis</span><span class="sxs-lookup"><span data-stu-id="35cf3-195">Link the web service to the redis service</span></span>

<span data-ttu-id="35cf3-196">Il servizio utilizza redis il [immagine redis pubblica più recente](https://hub.docker.com/_/redis/) estratti dal Registro di sistema Hub Docker.</span><span class="sxs-lookup"><span data-stu-id="35cf3-196">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="35cf3-197">[redis](http://redis.io/) è un sistema cache molto diffuso per applicazioni lato server.</span><span class="sxs-lookup"><span data-stu-id="35cf3-197">[redis](http://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="35cf3-198">Passaggio 5: Compilare ed eseguire l'app di Docker</span><span class="sxs-lookup"><span data-stu-id="35cf3-198">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="35cf3-199">Se l'applicazione ha solo un singolo contenitore, è sufficiente per l'esecuzione mediante la distribuzione nell'host Docker (macchina virtuale o server fisico).</span><span class="sxs-lookup"><span data-stu-id="35cf3-199">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="35cf3-200">Tuttavia, se l'app è costituita da più servizi, è necessario *comporlo*anche.</span><span class="sxs-lookup"><span data-stu-id="35cf3-200">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="35cf3-201">Esaminare le diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="35cf3-201">Let's see the different options.</span></span>

<span data-ttu-id="35cf3-202">***Opzione r: eseguire un singolo contenitore o un servizio***</span><span class="sxs-lookup"><span data-stu-id="35cf3-202">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="35cf3-203">È possibile eseguire l'immagine di Docker usando il comando docker run, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="35cf3-203">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="35cf3-204">Si noti che per questo tipo di distribuzione, si verranno essere reindirizzando le richieste inviate alla porta 80 per la porta interna 5000.</span><span class="sxs-lookup"><span data-stu-id="35cf3-204">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="35cf3-205">A questo punto, l'applicazione è in ascolto sulla porta 80 a livello di host esterna.</span><span class="sxs-lookup"><span data-stu-id="35cf3-205">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="35cf3-206">***Opzione b: comporre ed eseguire un'applicazione contenitore di più***</span><span class="sxs-lookup"><span data-stu-id="35cf3-206">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="35cf3-207">Nella maggior parte degli scenari aziendali, un'applicazione di Docker sarà costituita più servizi.</span><span class="sxs-lookup"><span data-stu-id="35cf3-207">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="35cf3-208">In questi casi, è possibile eseguire il comando comporre docker backup (figura 4-21), che verrà utilizzato il file docker compose.yml potrebbe essere creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="35cf3-208">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="35cf3-209">Eseguendo questo comando consente di distribuire un'applicazione composta con tutti i relativi contenitori correlati.</span><span class="sxs-lookup"><span data-stu-id="35cf3-209">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="35cf3-210">Figura 4-21: risultati dell'esecuzione del comando "docker-comporre backup"</span><span class="sxs-lookup"><span data-stu-id="35cf3-210">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="35cf3-211">Dopo l'esecuzione di docker-comporre backup, distribuire l'applicazione e il failover dei contenitori correlati in Host Docker, come illustrato nella figura 4-22, la rappresentazione in forma di macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="35cf3-211">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="35cf3-212">Figura 4-22: macchina virtuale con i contenitori di Docker distribuito</span><span class="sxs-lookup"><span data-stu-id="35cf3-212">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="35cf3-213">Nota docker-comporre backup e docker eseguire potrebbero essere sufficienti per i contenitori di test nell'ambiente di sviluppo, ma si potrebbe non usarle se si prevede di gestire i cluster di Docker e orchestrators Docker Swarm, Mesosphere DC/OS o Kubernetes Per poter applicare la scalabilità verticale.</span><span class="sxs-lookup"><span data-stu-id="35cf3-213">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="35cf3-214">Se si utilizza un cluster come [Docker Swarm modalità](https://docs.docker.com/engine/swarm/) (disponibile in Docker per Windows e Mac dalla versione 1.12), è necessario distribuire e testare con altri comandi, ad esempio il servizio docker di creare servizi single, o quando si è distribuzione di un'applicazione composta da diversi contenitori, usando docker comporre bundle e docker distribuire myBundleFile, distribuendo l'app composto come uno stack, come illustrato nell'articolo [bundle dell'applicazione distribuita](https://blog.docker.com/2016/06/docker-app-bundle/) da Docker.</span><span class="sxs-lookup"><span data-stu-id="35cf3-214">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="35cf3-215">Per [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) si usano i comandi di distribuzione diversi e gli script, nonché.</span><span class="sxs-lookup"><span data-stu-id="35cf3-215">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="35cf3-216">Passaggio 6: Testare l'applicazione di Docker (in locale, nella macchina virtuale locale CD)</span><span class="sxs-lookup"><span data-stu-id="35cf3-216">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="35cf3-217">Questo passaggio può variare a seconda di operazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="35cf3-217">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="35cf3-218">In un molto .NET Core API Web semplice "Hello World" distribuito come un singolo contenitore o un servizio, è sufficiente accedere al servizio, fornendo la porta TCP specificata nel documento DockerFile.</span><span class="sxs-lookup"><span data-stu-id="35cf3-218">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="35cf3-219">Se localhost non è attivato, per passare al servizio, individuare l'indirizzo IP per il computer con il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="35cf3-219">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="35cf3-220">ip macchina docker *nome contenitore*</span><span class="sxs-lookup"><span data-stu-id="35cf3-220">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="35cf3-221">Nell'host Docker, aprire un browser e passare a tale sito. verrà visualizzata l'app o servizio in esecuzione, come illustrato nella figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="35cf3-221">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="35cf3-222">Figura 4-23: il test dell'applicazione di Docker in locale utilizzando localhost</span><span class="sxs-lookup"><span data-stu-id="35cf3-222">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="35cf3-223">Si noti che utilizza la porta 80, ma internamente è stata viene reindirizzata alla porta 5000, in quanto si tratta di come è stato distribuito con docker run, come spiegato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="35cf3-223">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="35cf3-224">È possibile testare questo utilizzando CURL dal terminale.</span><span class="sxs-lookup"><span data-stu-id="35cf3-224">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="35cf3-225">In un'installazione di Docker in Windows, l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4-24.</span><span class="sxs-lookup"><span data-stu-id="35cf3-225">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="35cf3-226">Figura 4-24: test di un'applicazione di Docker in locale usando CURL</span><span class="sxs-lookup"><span data-stu-id="35cf3-226">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="35cf3-227">**Debug di un contenitore in esecuzione in Docker**</span><span class="sxs-lookup"><span data-stu-id="35cf3-227">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="35cf3-228">Codice di Visual Studio supporta Docker debug se si utilizza Node.js e altre piattaforme quali contenitori .NET Core.</span><span class="sxs-lookup"><span data-stu-id="35cf3-228">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="35cf3-229">È anche possibile eseguire il debug dei contenitori di .NET Core in Docker quando si utilizza Visual Studio, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="35cf3-229">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="35cf3-230">**Altre informazioni:** per ulteriori informazioni sul debug di contenitori di Node.js Docker, passare a <https://blog.docker.com/2016/07/live-debugging-docker/> e [https://blogs.msdn.microsoft.com/ \ utente\_ed/2016/02/27 / Visual-Studio-code-New-Features-13-big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="35cf3-230">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="35cf3-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="35cf3-231">[Previous] (docker-apps-development-environment.md) [Next] (visual-studio-tools-for-docker.md)</span></span>
