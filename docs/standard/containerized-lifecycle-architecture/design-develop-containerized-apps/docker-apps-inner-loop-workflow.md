---
title: Flusso di lavoro di sviluppo a ciclo interno per le app Docker
description: Descrive il flusso di lavoro "ciclo interno" per lo sviluppo di applicazioni Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 2d592f92153040d910dcf529ec21770693f5973c
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56442321"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="b4625-103">Flusso di lavoro di sviluppo a ciclo interno per le app Docker</span><span class="sxs-lookup"><span data-stu-id="b4625-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="b4625-104">Prima di attivare il flusso di lavoro ciclo esterno che si estende l'intera DevOps del ciclo, tutto ha inizio in ogni computer dello sviluppatore, scrittura di codice dell'app stessa, usando i propri linguaggi Preferiti o piattaforme e testarla in locale (figura 4-14).</span><span class="sxs-lookup"><span data-stu-id="b4625-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-14).</span></span> <span data-ttu-id="b4625-105">Ma in ogni caso, si avrà un aspetto molto importante in comune, indipendentemente da quale linguaggio, framework o piattaforme scelto.</span><span class="sxs-lookup"><span data-stu-id="b4625-105">But in every case, you will have a very important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="b4625-106">In questo flusso di lavoro specifico, sempre sviluppa e si testa i contenitori di Docker, ma in locale.</span><span class="sxs-lookup"><span data-stu-id="b4625-106">In this specific workflow, you are always developing and testing Docker containers, but locally.</span></span>

![](./media/image18.png)

<span data-ttu-id="b4625-107">Figura 4-14: Contesto di sviluppo a ciclo interno</span><span class="sxs-lookup"><span data-stu-id="b4625-107">Figure 4-14: Inner-loop development context</span></span>

<span data-ttu-id="b4625-108">Il contenitore o l'istanza di un'immagine Docker conterrà questi componenti:</span><span class="sxs-lookup"><span data-stu-id="b4625-108">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="b4625-109">Una selezione del sistema operativo (ad esempio, una distribuzione Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="b4625-109">An operating system selection (for example, a Linux distribution or Windows)</span></span>

-   <span data-ttu-id="b4625-110">File aggiunti dallo sviluppatore (ad esempio, file binari dell'app)</span><span class="sxs-lookup"><span data-stu-id="b4625-110">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="b4625-111">Configurazione (ad esempio, le impostazioni di ambiente e le dipendenze)</span><span class="sxs-lookup"><span data-stu-id="b4625-111">Configuration (for example, environment settings and dependencies)</span></span>

-   <span data-ttu-id="b4625-112">Istruzioni per i processi eseguiti da Docker</span><span class="sxs-lookup"><span data-stu-id="b4625-112">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="b4625-113">È possibile impostare il flusso di lavoro di sviluppo a ciclo interno che prevede l'utilizzo di Docker come il processo (descritto nella sezione successiva).</span><span class="sxs-lookup"><span data-stu-id="b4625-113">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="b4625-114">Tenere conto che i passaggi iniziali per configurare l'ambiente non è incluso, perché è necessario eseguire tale operazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="b4625-114">Take into account that the initial steps to set up the environment is not included, because you need to do that just once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="b4625-115">Creazione di una singola app all'interno di un contenitore Docker usando Visual Studio Code e CLI di Docker</span><span class="sxs-lookup"><span data-stu-id="b4625-115">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="b4625-116">Le app sono composti da servizi e librerie aggiuntive (dipendenze).</span><span class="sxs-lookup"><span data-stu-id="b4625-116">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="b4625-117">Figura 4-15 illustra i passaggi di base che è in genere necessario eseguire durante la creazione di un'app Docker, seguita da una descrizione dettagliata di ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="b4625-117">Figure 4-15 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![](./media/image19.png)

<span data-ttu-id="b4625-118">Figura 4-15: Flusso di lavoro generale per il ciclo di vita per applicazioni Docker in contenitori usando l'interfaccia CLI di Docker</span><span class="sxs-lookup"><span data-stu-id="b4625-118">Figure 4-15: High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="b4625-119">Passaggio 1: Iniziare a scrivere codice in Visual Studio Code e creare la linea di base di app/servizio iniziale</span><span class="sxs-lookup"><span data-stu-id="b4625-119">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="b4625-120">Il modo in cui si sviluppa l'applicazione è molto simile al modo in che cui avviene senza Docker.</span><span class="sxs-lookup"><span data-stu-id="b4625-120">The way you develop your application is pretty similar to the way you do it without Docker.</span></span> <span data-ttu-id="b4625-121">La differenza è che durante lo sviluppo, distribuzione e test di applicazioni o servizi in esecuzione all'interno di contenitori Docker inseriti nell'ambiente locale (ad esempio, una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="b4625-121">The difference is that while developing, you are deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="b4625-122">**Configurazione dell'ambiente locale**</span><span class="sxs-lookup"><span data-stu-id="b4625-122">**Setting up your local environment**</span></span>

<span data-ttu-id="b4625-123">Con le versioni più recenti di Docker per Mac e Windows, è più facile che mai per lo sviluppo di applicazioni di Docker, e il programma di installazione è semplice.</span><span class="sxs-lookup"><span data-stu-id="b4625-123">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

<span data-ttu-id="b4625-124">**Altre informazioni** per istruzioni sulla configurazione di Docker per Windows, vedere [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="b4625-124">**More info** For instructions on setting up Docker for Windows, go to [https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/).</span></span>

<span data-ttu-id="b4625-125">Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="b4625-125">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="b4625-126">Inoltre, è necessario un editor di codice in modo che è effettivamente possibile sviluppare l'applicazione quando si usa l'interfaccia CLI di Docker.</span><span class="sxs-lookup"><span data-stu-id="b4625-126">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="b4625-127">Microsoft fornisce Visual Studio Code, ovvero un editor di codice leggero che è supportato in Mac, Windows e Linux e offre il supporto IntelliSense con [supporto per molti linguaggi](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python e la maggior parte moderni linguaggi), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [supporto delle estensioni](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="b4625-127">Microsoft provides Visual Studio Code, which is a lightweight code editor that is supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="b4625-128">Questo editor è un candidato ideale per sviluppatori Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="b4625-128">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="b4625-129">In Windows, è anche possibile usare l'applicazione completa di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b4625-129">In Windows, you also can use the full Visual Studio application.</span></span>

<span data-ttu-id="b4625-130">**Altre informazioni** per istruzioni sull'installazione di Visual Studio per Windows, Mac o Linux, vedere <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="b4625-130">**More info** For instructions on installing Visual Studio for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>

<span data-ttu-id="b4625-131">È possibile lavorare con CLI di Docker e scrivere il codice usando qualsiasi editor di codice, ma se si usa Visual Studio Code, rende il è più facile autore Dockerfile e docker-Compose. yml file nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="b4625-131">You can work with Docker CLI and write your code using any code editor, but if you use Visual Studio Code, it makes it easy to author Dockerfile and docker-compose.yml files in your workspace.</span></span> <span data-ttu-id="b4625-132">Inoltre, è possibile eseguire le attività Visual Studio Code dall'IDE che richiederà gli script che possono essere in esecuzione di operazioni elaborate tramite la CLI di Docker di sotto.</span><span class="sxs-lookup"><span data-stu-id="b4625-132">Plus, you can run Visual Studio Code tasks from the IDE that will prompt scripts that can be running elaborated operations using Docker CLI underneath.</span></span>

<span data-ttu-id="b4625-133">Visual Studio Code viene fornito da un'estensione, che è necessario installare.</span><span class="sxs-lookup"><span data-stu-id="b4625-133">Visual Studio Code is provided by an extension, which you'll need to install.</span></span> <span data-ttu-id="b4625-134">A tale scopo, premere Ctrl + MAIUSC + P, digitare **ext installare**, quindi eseguire le estensioni: Installare il comando di estensione per visualizzare l'elenco di estensioni di Marketplace.</span><span class="sxs-lookup"><span data-stu-id="b4625-134">To do so, Press Ctrl+Shift+P, type **ext install**, and then run the Extensions: Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="b4625-135">Successivamente, digitare **docker** per filtrare i risultati e quindi selezionare il file Dockerfile e il File Docker Compose (yml) estensione del supporto, come illustrato nella figura 4-16.</span><span class="sxs-lookup"><span data-stu-id="b4625-135">Next, type **docker** to filter the results, and then select the Dockerfile And Docker Compose File (yml) Support extension, as depicted in Figure 4-16.</span></span>

![](./media/image20.png)

<span data-ttu-id="b4625-136">Figura 4-16: Installazione dell'estensione Docker in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b4625-136">Figure 4-16: Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="b4625-137">Passaggio 2: Creare un DockerFile correlato a un'immagine esistente (normale del sistema operativo o ambienti di sviluppo, come Ruby, Node. js e .NET Core)</span><span class="sxs-lookup"><span data-stu-id="b4625-137">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="b4625-138">È necessario un DockerFile per ogni immagine personalizzata da compilare e ogni contenitore da distribuire, pertanto, se l'app è costituita da un solo servizio personalizzato, sarà necessario un solo DockerFile.</span><span class="sxs-lookup"><span data-stu-id="b4625-138">You will need a DockerFile per custom image to be built and per container to be deployed, therefore, if your app is made up of a single custom service, you will need a single DockerFile.</span></span> <span data-ttu-id="b4625-139">Tuttavia, se l'app è costituita da più servizi (ad esempio un'architettura di microservizi), è necessario un Dockerfile per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="b4625-139">But, if your app is composed of multiple services (as in a microservices architecture), you'll need one Dockerfile per service.</span></span>

<span data-ttu-id="b4625-140">Il DockerFile viene in genere posizionato all'interno della cartella radice dell'app o del servizio e contiene i comandi necessari in modo che Docker sa come configurare ed eseguire tale applicazione o servizio.</span><span class="sxs-lookup"><span data-stu-id="b4625-140">The DockerFile is usually placed within the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="b4625-141">È possibile creare i DockerFile e aggiungerlo al progetto insieme a codice (Node. js, .NET Core, e così via), o, se si ha familiarità con l'ambiente, esaminiamo il suggerimento seguente.</span><span class="sxs-lookup"><span data-stu-id="b4625-141">You can create your DockerFile and add it to your project along with your code (node.js, .NET Core, etc.), or, if you are new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
> <span data-ttu-id="b4625-142">È possibile usare uno strumento da riga di comando denominato [yo docker](https://github.com/Microsoft/generator-docker), che esegue scaffolding delle file dal progetto nella lingua si sceglie e aggiunge i file di configurazione di Docker necessari.</span><span class="sxs-lookup"><span data-stu-id="b4625-142">You can use a command-line tool called [yo docker](https://github.com/Microsoft/generator-docker), which scaffolds files from your project in the language you choose and adds the required Docker configuration files.</span></span> <span data-ttu-id="b4625-143">In pratica, per assistere gli sviluppatori Guida introduttiva, viene creato il documento DockerFile appropriato, docker-Compose. yml e altri script associato per compilare ed eseguire i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="b4625-143">Basically, to assist developers getting started, it creates the appropriate DockerFile, docker-compose.yml, and other associated scripts to build and run your Docker containers.</span></span> <span data-ttu-id="b4625-144">Il generatore yeoman richiederà alcune domande, porre l'host del contenitore selezionato sviluppo language e di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b4625-144">This yeoman generator will prompt you with a few questions, asking your selected development language and destination container host.</span></span>

![yo docker](./media/image21.png)

<span data-ttu-id="b4625-146">Ad esempio, nella figura 4-17 due schermate dai terminali in Windows e in un computer Mac, in entrambi i casi, in esecuzione yo docker, che genera i codice progetti di esempio (attualmente .NET Core, Golang e Node. js come lingue supportate) già configurati per l'utilizzo in parte superiore di Docker.</span><span class="sxs-lookup"><span data-stu-id="b4625-146">For instance, Figure 4-17 shows two screenshots from the terminals in Windows and on a Mac, in both cases, running yo docker, which will generate the sample code projects (currently .NET Core, Golang, and Node.js as supported languages) already configured to work on top of Docker.</span></span>

![](./media/image22.PNG)  ![](./media/image23.png)

<span data-ttu-id="b4625-147">Figura 4-17: yo docker strumento di comando in Windows (left) e in un computer Mac</span><span class="sxs-lookup"><span data-stu-id="b4625-147">Figure 4-17: yo docker command tool in Windows (left) and on a Mac</span></span>

<span data-ttu-id="b4625-148">Figura 4-18 presenta un esempio di uso di yo docker dopo aver creato un progetto .NET Core esistente in grado di essere sottoposto a scaffolding.</span><span class="sxs-lookup"><span data-stu-id="b4625-148">Figure 4-18 presents an example using yo docker after you have an existing .NET Core project in place to be scaffolded.</span></span>

![](./media/image24.PNG)

<span data-ttu-id="b4625-149">Figura 4-18: yo docker con una versione esistente di .NET Core project posto</span><span class="sxs-lookup"><span data-stu-id="b4625-149">Figure 4-18: yo docker with an existing .NET Core project in place</span></span>

<span data-ttu-id="b4625-150">Da DockerFile, è specificare quale immagine Docker di base sarà possibile usare (ad esempio, tramite "da microsoft/dotnet:1.0.0-core").</span><span class="sxs-lookup"><span data-stu-id="b4625-150">From the DockerFile, you specify what base Docker image you'll be using (like using "FROM microsoft/dotnet:1.0.0-core").</span></span> <span data-ttu-id="b4625-151">È in genere compilerà l'immagine personalizzata all'inizio di un'immagine di base che è possibile ottenere da qualsiasi repository ufficiale nel [registro Docker Hub](https://hub.docker.com/) (ad esempio un [immagine per .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o uno [per Node. js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="b4625-151">You usually will build your custom image on top of a base image that you can get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="b4625-152">***Opzione a: Usare un'immagine Docker ufficiale esistente***</span><span class="sxs-lookup"><span data-stu-id="b4625-152">***Option A: Use an existing official Docker image***</span></span>

<span data-ttu-id="b4625-153">Uso di un repository ufficiale di uno stack di linguaggio con un numero di versione garantisce che le stesse funzionalità del linguaggio sono disponibili in tutti i computer (tra cui sviluppo, test e produzione).</span><span class="sxs-lookup"><span data-stu-id="b4625-153">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="b4625-154">Seguito è riportato un esempio di DockerFile per un contenitore di .NET Core:</span><span class="sxs-lookup"><span data-stu-id="b4625-154">Following is a sample DockerFile for a .NET Core container:</span></span>

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

<span data-ttu-id="b4625-155">In questo caso, Usa la versione 1.0.1 dell'immagine ASP.NET Core Docker ufficiale per Linux denominato microsoft/aspnetcore:1.0.1.</span><span class="sxs-lookup"><span data-stu-id="b4625-155">In this case, it is using the version 1.0.1 of the official ASP.NET Core Docker image for Linux named microsoft/aspnetcore:1.0.1.</span></span> <span data-ttu-id="b4625-156">Per altri dettagli, consultare il [pagina di ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) e il [pagina di .NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="b4625-156">For further details, consult the [ASP.NET Core Docker Image page](https://hub.docker.com/r/microsoft/aspnetcore/) and the [.NET Core Docker Image page](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="b4625-157">È anche possibile usare un'altra immagine confrontabile, ad esempio il nodo: 4-onbuild per Node. js o molte altre immagini preconfigurate per i linguaggi di sviluppo, sono disponibili all'indirizzo [Hub Docker](https://hub.docker.com/explore/).</span><span class="sxs-lookup"><span data-stu-id="b4625-157">You also could be using another comparable image like node:4-onbuild for Node.js, or many other preconfigured images for development languages, which are available at [Docker Hub](https://hub.docker.com/explore/).</span></span>

<span data-ttu-id="b4625-158">Nel DockerFile, è necessario anche indicare a Docker in ascolto sulla porta TCP si userà in fase di esecuzione (ad esempio la porta 80).</span><span class="sxs-lookup"><span data-stu-id="b4625-158">In the DockerFile, you also need to instruct Docker to listen to the TCP port that you will use at runtime (such as port 80).</span></span>

<span data-ttu-id="b4625-159">Sono presenti altre righe di configurazione che è possibile aggiungere nel DockerFile a seconda del linguaggio/framework in uso, in modo che Docker sa come eseguire l'app.</span><span class="sxs-lookup"><span data-stu-id="b4625-159">There are other lines of configuration that you can add in the DockerFile depending on the language/framework you are using, so Docker knows how to run the app.</span></span> <span data-ttu-id="b4625-160">Ad esempio, è necessario la riga ENTRYPOINT con \["dotnet", "MyCustomMicroservice.dll"\] per eseguire un'app .NET Core, anche se è possibile avere più varianti a seconda dell'approccio per compilare ed eseguire il servizio.</span><span class="sxs-lookup"><span data-stu-id="b4625-160">For instance, you need the ENTRYPOINT line with \["dotnet", "MyCustomMicroservice.dll"\] to run a .NET Core app, although you can have multiple variants depending on the approach to build and run your service.</span></span> <span data-ttu-id="b4625-161">Se si usa il SDK e una riga di comando dotnet per compilare ed eseguire l'app .NET, potrebbe essere leggermente diverso.</span><span class="sxs-lookup"><span data-stu-id="b4625-161">If you're using the SDK and dotnet CLI to build and run the .NET app, it would be slightly different.</span></span> <span data-ttu-id="b4625-162">La conclusione è che la riga ENTRYPOINT e altre righe saranno diverse a seconda del linguaggio o piattaforma che scelta per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b4625-162">The bottom line is that the ENTRYPOINT line plus additional lines will be different depending on the language/platform you choose for your application.</span></span>

<span data-ttu-id="b4625-163">**Altre informazioni** per informazioni sulla compilazione di immagini Docker per applicazioni .NET Core, vedere [ https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images ](../../../core/docker/building-net-docker-images.md).</span><span class="sxs-lookup"><span data-stu-id="b4625-163">**More info** For information about building Docker images for .NET Core applications, go to [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](../../../core/docker/building-net-docker-images.md).</span></span>

<span data-ttu-id="b4625-164">Per altre informazioni sulla creazione di immagini personalizzate, passare a [ https://docs.docker.com/engine/\ esercitazioni/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span><span class="sxs-lookup"><span data-stu-id="b4625-164">To learn more about building your own images, go to [https://docs.docker.com/engine/\ tutorials/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).</span></span>

<span data-ttu-id="b4625-165">**Repository di immagini multipiattaforma**</span><span class="sxs-lookup"><span data-stu-id="b4625-165">**Multiplatform image repositories**</span></span>

<span data-ttu-id="b4625-166">Man mano che diventano i contenitori di Windows più prevalenti, un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="b4625-166">As Windows containers become more prevalent, a single repository can contain platform variants, such as a Linux and Windows image.</span></span> <span data-ttu-id="b4625-167">Si tratta di una nuova funzionalità di Docker che rende possibile per i fornitori di usare un unico repository per coprire più piattaforme, quali [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, che sono disponibili nel Registro di sistema DockerHub.</span><span class="sxs-lookup"><span data-stu-id="b4625-167">This is a new feature coming in Docker that makes it possible for vendors to use a single repository to cover multiple platforms, such as [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, which is available at DockerHub registry.</span></span> <span data-ttu-id="b4625-168">Man mano che la funzionalità attiva, il pull di questa immagine da un host Windows richiamerà la variante di Windows, mentre il pull lo stesso nome di immagine da un host Linux richiamerà la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="b4625-168">As the feature comes alive, pulling this image from a Windows host will pull the Windows variant, whereas pulling the same image name from a Linux host will pull the Linux variant.</span></span>

<span data-ttu-id="b4625-169">***Opzione b: Creare l'immagine di base da zero***</span><span class="sxs-lookup"><span data-stu-id="b4625-169">***Option B: Create your base image from scratch***</span></span>

<span data-ttu-id="b4625-170">È possibile creare la propria immagine di base di Docker da zero, come illustrato in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) da Docker.</span><span class="sxs-lookup"><span data-stu-id="b4625-170">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="b4625-171">Questo è uno scenario che probabilmente non è adatto a te se si sta iniziando con Docker, ma se si desidera impostare i bit specifici della propria immagine di base, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="b4625-171">This is a scenario that is probably not best for you if you are just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="b4625-172">Passaggio 3: Creare le immagini Docker personalizzate in essa l'incorporamento del servizio</span><span class="sxs-lookup"><span data-stu-id="b4625-172">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="b4625-173">Per ogni servizio personalizzata che comprende l'app, è necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="b4625-173">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="b4625-174">Se l'app è costituito da un singolo servizio o un'app web, è necessario avere una sola immagine.</span><span class="sxs-lookup"><span data-stu-id="b4625-174">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
> <span data-ttu-id="b4625-175">Quando prendendo in considerazione il "ciclo esterno flusso di lavoro DevOps", le immagini verranno create da un processo di compilazione automatica ogni volta che si esegue il push del codice sorgente in un repository Git (Continuous Integration) in modo che le immagini verranno create in quell'ambiente globale dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="b4625-175">When taking into account the "outer-loop DevOps workflow," the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration) so the images will be created in that global environment from your source code.</span></span>

<span data-ttu-id="b4625-176">Tuttavia, prima che passa a tale route ciclo esterno, è necessario verificare che l'applicazione Docker in realtà funziona correttamente in modo che non sono push del codice che potrebbe non funzionare correttamente per il sistema di controllo sorgente (Git e così via).</span><span class="sxs-lookup"><span data-stu-id="b4625-176">But, before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>

<span data-ttu-id="b4625-177">Pertanto, ogni sviluppatore deve prima eseguire l'intero processo di ciclo interno per testare in locale e continuare a sviluppare fino a quando non desiderano eseguire il push di una funzionalità completa o modificare il sistema di controllo sorgente.</span><span class="sxs-lookup"><span data-stu-id="b4625-177">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="b4625-178">Per creare un'immagine nell'ambiente locale e Usa il DockerFile, è possibile usare il comando docker build, come illustrato nella figura 4-19 (è anche possibile eseguire docker-compose up-- compilazione per applicazioni composte da diversi contenitori/servizi).</span><span class="sxs-lookup"><span data-stu-id="b4625-178">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-19 (you also can run docker-compose up --build for applications composed by several containers/services).</span></span>

![](./media/image25.png)

<span data-ttu-id="b4625-179">Figura 4-19: Compilazione di docker in esecuzione</span><span class="sxs-lookup"><span data-stu-id="b4625-179">Figure 4-19: Running docker build</span></span>

<span data-ttu-id="b4625-180">Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è innanzitutto possibile generare una cartella distribuibile con le librerie di .NET necessarie tramite l'esecuzione di dotnet publish di e quindi eseguire la compilazione docker.</span><span class="sxs-lookup"><span data-stu-id="b4625-180">Optionally, instead of directly running docker build from the project's folder, you first can generate a deployable folder with the .NET libraries needed by using the run dotnet publish command, and then run docker build.</span></span>

<span data-ttu-id="b4625-181">In questo esempio verrà creata un'immagine Docker con il nome cesardl/netcore-webapi-microservizio-docker: first (: first è un tag, ad esempio una versione specifica).</span><span class="sxs-lookup"><span data-stu-id="b4625-181">In this example, this creates a Docker image with the name cesardl/netcore-webapi-microservice-docker:first (:first is a tag, like a specific version).</span></span> <span data-ttu-id="b4625-182">È possibile eseguire questo passaggio per ogni immagine personalizzata che è necessario creare per l'applicazione Docker composta con diversi contenitori.</span><span class="sxs-lookup"><span data-stu-id="b4625-182">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="b4625-183">È possibile trovare le immagini esistenti nel repository locale (computer di sviluppo) usando docker immagini comando, come illustrato nella figura 4-20.</span><span class="sxs-lookup"><span data-stu-id="b4625-183">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-20.</span></span>

![](./media/image26.png)

<span data-ttu-id="b4625-184">La figura 4-20: Visualizzazione immagini esistente con le immagini docker</span><span class="sxs-lookup"><span data-stu-id="b4625-184">Figure 4-20: Viewing existing images using docker images</span></span>

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="b4625-185">Passaggio 4: (Facoltativo) Definire i servizi in docker-Compose. yml quando si compila un'applicazione Docker composta con più servizi</span><span class="sxs-lookup"><span data-stu-id="b4625-185">Step 4: (Optional) Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="b4625-186">Con il file docker-Compose. yml è possibile definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione illustrati nella sezione Passaggio successiva.</span><span class="sxs-lookup"><span data-stu-id="b4625-186">With the docker-compose.yml file you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="b4625-187">È necessario creare file in principale o la cartella soluzione radice; deve avere un contenuto simile al file docker-Compose. yml seguente:</span><span class="sxs-lookup"><span data-stu-id="b4625-187">You need to create that file in your main or root solution folder; it should have a similar content to the following docker-compose.yml file:</span></span>

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

<span data-ttu-id="b4625-188">In questo caso particolare, questo file definisce due servizi: il servizio web (il servizio personalizzato) e il servizio redis (un servizio popolare cache).</span><span class="sxs-lookup"><span data-stu-id="b4625-188">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="b4625-189">Ogni servizio verrà distribuito come un contenitore, pertanto è necessario usare un'immagine Docker concreta per ognuno.</span><span class="sxs-lookup"><span data-stu-id="b4625-189">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="b4625-190">Per questo servizio web specifico, l'immagine dovrà eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b4625-190">For this particular web service, the image will need to do the following:</span></span>

-   <span data-ttu-id="b4625-191">Compilazione del dockerfile nella directory corrente</span><span class="sxs-lookup"><span data-stu-id="b4625-191">Build from the DockerFile in the current directory</span></span>

-   <span data-ttu-id="b4625-192">Inoltrare la porta 80 esposta sul contenitore alla porta 81 nel computer host</span><span class="sxs-lookup"><span data-stu-id="b4625-192">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

-   <span data-ttu-id="b4625-193">Montare la directory del progetto nell'host in cui /code all'interno del contenitore, rendendo possibile la modifica del codice senza dover ricompilare l'immagine</span><span class="sxs-lookup"><span data-stu-id="b4625-193">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

-   <span data-ttu-id="b4625-194">Collegare il servizio web al servizio redis</span><span class="sxs-lookup"><span data-stu-id="b4625-194">Link the web service to the redis service</span></span>

<span data-ttu-id="b4625-195">Il servizio redis Usa il [immagine redis pubblica più recente](https://hub.docker.com/_/redis/) estratto dal registro Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="b4625-195">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="b4625-196">[redis](https://redis.io/) è un sistema di cache molto diffusa per le applicazioni lato server.</span><span class="sxs-lookup"><span data-stu-id="b4625-196">[redis](https://redis.io/) is a very popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="b4625-197">Passaggio 5: Compilare ed eseguire l'app Docker</span><span class="sxs-lookup"><span data-stu-id="b4625-197">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="b4625-198">Se l'app ha solo un singolo contenitore, è sufficiente eseguirla distribuendola all'host Docker (macchina virtuale o server fisico).</span><span class="sxs-lookup"><span data-stu-id="b4625-198">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="b4625-199">Tuttavia, se l'app è costituita da più servizi, devi *comporlo*anche.</span><span class="sxs-lookup"><span data-stu-id="b4625-199">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="b4625-200">Esaminiamo le diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="b4625-200">Let's see the different options.</span></span>

<span data-ttu-id="b4625-201">***Opzione a: Eseguire un singolo contenitore o un servizio***</span><span class="sxs-lookup"><span data-stu-id="b4625-201">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="b4625-202">È possibile eseguire l'immagine Docker usando il comando docker run, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b4625-202">You can run the Docker image by using the docker run command, as shown here:</span></span>

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="b4625-203">Si noti che per questa distribuzione specifica, si saranno essere reindirizzando le richieste inviate alla porta 80 alla porta interna 5000.</span><span class="sxs-lookup"><span data-stu-id="b4625-203">Note that for this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="b4625-204">A questo punto, l'applicazione è in ascolto sulla porta esterna 80 a livello di host.</span><span class="sxs-lookup"><span data-stu-id="b4625-204">Now, the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="b4625-205">***Opzione b: Creare ed eseguire un'applicazione di più contenitori***</span><span class="sxs-lookup"><span data-stu-id="b4625-205">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="b4625-206">Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà essere composte da più servizi.</span><span class="sxs-lookup"><span data-stu-id="b4625-206">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="b4625-207">In questi casi, è possibile eseguire il comando docker-compose backup (figura 4-21), che userà il file docker-Compose. yml che è stato creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b4625-207">For these cases, you can run the command docker-compose up (Figure 4-21), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="b4625-208">Questo comando consente di distribuire un'applicazione composta con tutti i contenitori correlati.</span><span class="sxs-lookup"><span data-stu-id="b4625-208">Running this command deploys a composed application with all of its related containers.</span></span>

![](./media/image27.png)

<span data-ttu-id="b4625-209">Figura 4-21: Risultati dell'esecuzione del comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="b4625-209">Figure 4-21: Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="b4625-210">Dopo l'esecuzione di docker-compose backup, si distribuisce l'applicazione e i relativi contenitori correlati nell'Host Docker, come illustrato nella figura 4-22, la rappresentazione in forma di macchina virtuale.</span><span class="sxs-lookup"><span data-stu-id="b4625-210">After you run docker-compose up, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-22, in the VM representation.</span></span>

![](./media/image28.png)

<span data-ttu-id="b4625-211">Figura 4-22: VM con contenitori Docker distribuiti</span><span class="sxs-lookup"><span data-stu-id="b4625-211">Figure 4-22: VM with Docker containers deployed</span></span>

<span data-ttu-id="b4625-212">Nota comando docker-compose up e docker eseguire potrebbe essere sufficiente per il test dei contenitori nell'ambiente di sviluppo, ma non usarli affatto se si prevede di gestire i cluster Docker e gli agenti di orchestrazione come Docker Swarm, Mesosphere DC/OS o Kubernetes Per poter essere in grado di aumentare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b4625-212">Note docker-compose up and docker run might be enough for testing your containers in your development environment, but you might not use them at all if you are expecting to work with Docker clusters and orchestrators like Docker Swarm, Mesosphere DC/OS, or Kubernetes in order to be able to scale up.</span></span> <span data-ttu-id="b4625-213">Se si usa un cluster, ad esempio [modalità Docker Swarm](https://docs.docker.com/engine/swarm/) , disponibile in Docker per Windows e Mac dalla versione 1.12, è necessario distribuire e testare con comandi aggiuntivi, ad esempio per servizi singoli di creazione servizio docker, o quando si è distribuzione di un'app composte da diversi contenitori, usando docker compose bundle e distribuzione docker myBundleFile, distribuendo l'app composto come uno stack, come illustrato nell'articolo [bundle dell'applicazione distribuita](https://blog.docker.com/2016/06/docker-app-bundle/) da Docker.</span><span class="sxs-lookup"><span data-stu-id="b4625-213">If you're using a cluster like [Docker Swarm mode](https://docs.docker.com/engine/swarm/) (available in Docker for Windows and Mac since version 1.12), you need to deploy and test with additional commands such as docker service create for single services, or when you're deploying an app composed of several containers, using docker compose bundle and docker deploy myBundleFile, by deploying the composed app as a stack, as explained in the article [Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) from Docker.</span></span>

<span data-ttu-id="b4625-214">Per la [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) si usano i comandi di distribuzione diversi e gli script, nonché.</span><span class="sxs-lookup"><span data-stu-id="b4625-214">For [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) and [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) you would use different deployment commands and scripts, as well.</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="b4625-215">Passaggio 6: Testare l'applicazione Docker (in locale, nella macchina virtuale locale CD)</span><span class="sxs-lookup"><span data-stu-id="b4625-215">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="b4625-216">Questo passaggio varia a seconda di ciò che esegue l'app.</span><span class="sxs-lookup"><span data-stu-id="b4625-216">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="b4625-217">In un semplice .NET Core API Web "Hello World" distribuito come un singolo contenitore o un servizio, è sufficiente accedere al servizio, fornendo la porta TCP specificata nel DockerFile.</span><span class="sxs-lookup"><span data-stu-id="b4625-217">In a very simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="b4625-218">Se localhost non è attivata, per passare al servizio, trovare l'indirizzo IP per la macchina tramite questo comando:</span><span class="sxs-lookup"><span data-stu-id="b4625-218">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

<span data-ttu-id="b4625-219">docker machine ip *your-container-name*</span><span class="sxs-lookup"><span data-stu-id="b4625-219">docker-machine ip *your-container-name*</span></span>

<span data-ttu-id="b4625-220">Nell'host Docker, aprire un browser e passare a tale sito. il servizio app/in esecuzione, verrà visualizzato come illustrato nella figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="b4625-220">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-23.</span></span>

![](./media/image29.png)

<span data-ttu-id="b4625-221">Figura 4-23: Test dell'applicazione Docker in locale mediante localhost</span><span class="sxs-lookup"><span data-stu-id="b4625-221">Figure 4-23: Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="b4625-222">Si noti che utilizza la porta 80, ma internamente è stata viene reindirizzata alla porta 5000 perché si tratta di come è stata distribuita con docker run, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="b4625-222">Note that it is using port 80, but internally it was being redirected to port 5000, because that's how it was deployed with docker run, as explained earlier.</span></span>

<span data-ttu-id="b4625-223">È possibile verificarlo usando CURL dal terminale.</span><span class="sxs-lookup"><span data-stu-id="b4625-223">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="b4625-224">In un'installazione di Docker in Windows, l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4-24.</span><span class="sxs-lookup"><span data-stu-id="b4625-224">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-24.</span></span>

![](./media/image30.png)

<span data-ttu-id="b4625-225">La figura 4-24: Test di un'applicazione Docker in locale mediante CURL</span><span class="sxs-lookup"><span data-stu-id="b4625-225">Figure 4-24: Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="b4625-226">**Debug di un contenitore in esecuzione in Docker**</span><span class="sxs-lookup"><span data-stu-id="b4625-226">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="b4625-227">Visual Studio Code supporta debug Docker se si usa Node. js e altre piattaforme quali contenitori .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b4625-227">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="b4625-228">È anche possibile eseguire il debug dei contenitori di .NET Core in Docker quando si usa Visual Studio, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="b4625-228">You also can debug .NET Core containers in Docker when using Visual Studio, as described in the next section.</span></span>

<span data-ttu-id="b4625-229">**Altre informazioni:** per altre informazioni sul debug di contenitori Docker di Node. js, passare alla <https://blog.docker.com/2016/07/live-debugging-docker/> e [ https://blogs.msdn.microsoft.com/\ utente\_ed/2016/02/27 o Visual-Studio-code-New-Features-13-big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span><span class="sxs-lookup"><span data-stu-id="b4625-229">**More info:** To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and [https://blogs.msdn.microsoft.com/\ user\_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b4625-230">[Precedente](docker-apps-development-environment.md)
>[Successivo](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="b4625-230">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>