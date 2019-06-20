---
title: Flusso di lavoro di sviluppo del ciclo interno per le app Docker
description: Informazioni sul flusso di lavoro del ciclo interno per lo sviluppo di applicazioni Docker.
ms.date: 02/15/2019
ms.openlocfilehash: ce573546f61b98c2f93e998203497fa949e9efe8
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644848"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="bed9d-103">Flusso di lavoro di sviluppo del ciclo interno per le app Docker</span><span class="sxs-lookup"><span data-stu-id="bed9d-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="bed9d-104">Prima di attivare il flusso di lavoro del ciclo esterno che coinvolge l'intero ciclo DevOps, è necessario che tutto abbia inizio nel computer dello sviluppatore. Si scrive il codice dell'app stessa usando i linguaggi o le piattaforme preferiti, e la si testa in locale (figura 4-21).</span><span class="sxs-lookup"><span data-stu-id="bed9d-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="bed9d-105">In ogni caso, la questione importante è una. Indipendentemente dal linguaggio, dal framework o dalle piattaforme scelti,</span><span class="sxs-lookup"><span data-stu-id="bed9d-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="bed9d-106">in questo flusso di lavoro specifico si sviluppano e testano sempre contenitori Docker, ma a livello locale.</span><span class="sxs-lookup"><span data-stu-id="bed9d-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Passaggio 1: Codice, esecuzione, debug](./media/image18.png)

<span data-ttu-id="bed9d-108">**Figura 4-21**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-108">**Figure 4-21**.</span></span> <span data-ttu-id="bed9d-109">Contesto di sviluppo del ciclo interno</span><span class="sxs-lookup"><span data-stu-id="bed9d-109">Inner-loop development context</span></span>

<span data-ttu-id="bed9d-110">Il contenitore o l'istanza di un'immagine Docker conterrà i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="bed9d-110">The container or instance of a Docker image will contain these components:</span></span>

- <span data-ttu-id="bed9d-111">Un sistema operativo a scelta, ad esempio una distribuzione Linux o Windows</span><span class="sxs-lookup"><span data-stu-id="bed9d-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="bed9d-112">File aggiunti dallo sviluppatore, ad esempio file binari dell'app</span><span class="sxs-lookup"><span data-stu-id="bed9d-112">Files added by the developer (for example, app binaries)</span></span>

- <span data-ttu-id="bed9d-113">Informazioni di configurazione, ad esempio impostazioni di ambiente e dipendenze</span><span class="sxs-lookup"><span data-stu-id="bed9d-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="bed9d-114">Istruzioni per i processi che Docker dovrà eseguire</span><span class="sxs-lookup"><span data-stu-id="bed9d-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="bed9d-115">È possibile configurare il flusso di lavoro di sviluppo del ciclo interno che prevede l'uso di Docker come processo. Questo processo viene descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="bed9d-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="bed9d-116">Tenere presente che i passaggi iniziali per configurare l'ambiente non sono inclusi, perché è sufficiente eseguire la configurazione una sola volta.</span><span class="sxs-lookup"><span data-stu-id="bed9d-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="bed9d-117">Compilazione di una singola app all'interno di un contenitore Docker usando Visual Studio Code e l'interfaccia della riga di comando di Docker</span><span class="sxs-lookup"><span data-stu-id="bed9d-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="bed9d-118">Le app sono costituite da servizi personalizzati e raccolte aggiuntive, vale a dire dipendenze.</span><span class="sxs-lookup"><span data-stu-id="bed9d-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="bed9d-119">La figura 4-22 illustra i passaggi di base che devono essere generalmente eseguiti per compilare un'app Docker e le descrizioni dettagliate di ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="bed9d-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Panoramica del flusso di lavoro: Passaggio 1: scrivere il codice dell'app, Passaggio 2: scrivere Dockerfile, Passaggio 3: creare immagini definite con Dockerfile, Passaggio 4: definire servizi con il file docker-compose, Passaggio 5: eseguire contenitori o app composte, Passaggio 6: testare app, Passaggio 7: eseguire il push per iniziare il ciclo esterno (pipeline CI/CD ) oppure continuare a sviluppare.](./media/image19.png)

<span data-ttu-id="bed9d-121">**Figura 4-22**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-121">**Figure 4-22**.</span></span> <span data-ttu-id="bed9d-122">Flusso di lavoro generale del ciclo di vita di applicazioni Docker in contenitori tramite l'interfaccia della riga di comando di Docker</span><span class="sxs-lookup"><span data-stu-id="bed9d-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="bed9d-123">Passaggio 1: Iniziare a scrivere codice in Visual Studio Code e creare l'app o il servizio iniziale</span><span class="sxs-lookup"><span data-stu-id="bed9d-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="bed9d-124">Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza l'uso di Docker.</span><span class="sxs-lookup"><span data-stu-id="bed9d-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="bed9d-125">La differenza consiste nel fatto che, durante lo sviluppo, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale, ad esempio una macchina virtuale Linux o Windows.</span><span class="sxs-lookup"><span data-stu-id="bed9d-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="bed9d-126">**Configurare l'ambiente locale**</span><span class="sxs-lookup"><span data-stu-id="bed9d-126">**Setting up your local environment**</span></span>

<span data-ttu-id="bed9d-127">Con le versioni più recenti di Docker per Mac e Windows, sviluppare applicazioni Docker non è mai stato tanto semplice e la configurazione è molto facile.</span><span class="sxs-lookup"><span data-stu-id="bed9d-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [!INFORMAZIONI]
>
> <span data-ttu-id="bed9d-129">Per istruzioni sulla configurazione di Docker per Windows, passare a <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="bed9d-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="bed9d-130">Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="bed9d-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="bed9d-131">Sarà anche necessario un editor di codice, con il quale sarà effettivamente possibile sviluppare l'applicazione usando al tempo stesso l'interfaccia della riga di comando di Docker.</span><span class="sxs-lookup"><span data-stu-id="bed9d-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="bed9d-132">Microsoft offre Visual Studio Code, un semplice editor di codice supportato in Mac, Windows e Linux, nonché IntelliSense con il [supporto per molti linguaggi](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python e la maggior parte dei linguaggi moderni), [debug](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [supporto per estensioni](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="bed9d-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="bed9d-133">Questo editor è la soluzione ideale per sviluppatori Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="bed9d-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="bed9d-134">In Windows è anche possibile usare l'intera suite di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bed9d-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [!INFORMAZIONI]
>
> <span data-ttu-id="bed9d-136">Per istruzioni sull'installazione di Visual Studio Code per Windows, Mac o Linux, passare a <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="bed9d-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="bed9d-137">Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="bed9d-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="bed9d-138">È possibile usare l'interfaccia della riga di comando di Docker e scrivere il codice usando qualsiasi editor di codice. L'uso di Visual Studio Code con l'estensione Docker consente però di creare facilmente file `Dockerfile` e `docker-compose.yml` nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bed9d-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="bed9d-139">Usando l'interfaccia della riga di comando di Docker riportata di seguito, è anche possibile eseguire attività e script dall'IDE di Visual Studio Code per eseguire comandi di Docker.</span><span class="sxs-lookup"><span data-stu-id="bed9d-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="bed9d-140">L'estensione Docker per Visual Studio Code offre le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="bed9d-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="bed9d-141">Generazione automatica dei file `Dockerfile` e `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="bed9d-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="bed9d-142">Evidenziazione della sintassi e suggerimenti al passaggio del mouse sui file `docker-compose.yml` e `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="bed9d-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="bed9d-143">IntelliSense (completamenti) per i file `Dockerfile` e `docker-compose.yml`</span><span class="sxs-lookup"><span data-stu-id="bed9d-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="bed9d-144">Analisi (errori e avvisi) per i file `Dockerfile`</span><span class="sxs-lookup"><span data-stu-id="bed9d-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="bed9d-145">Integrazione del riquadro comandi (F1) per la maggior parte dei comuni comandi di Docker</span><span class="sxs-lookup"><span data-stu-id="bed9d-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="bed9d-146">Integrazione dell'utilità di esplorazione per la gestione di immagini e contenitori</span><span class="sxs-lookup"><span data-stu-id="bed9d-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="bed9d-147">Distribuzione di immagini da Docker Hub e da registri contenitori Azure in Servizio app di Azure</span><span class="sxs-lookup"><span data-stu-id="bed9d-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="bed9d-148">Per installare l'estensione Docker, premere CTRL + MAIUSC + P, digitare `ext install`, quindi eseguire il comando Installa estensione per visualizzare l'elenco delle estensioni del Marketplace.</span><span class="sxs-lookup"><span data-stu-id="bed9d-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="bed9d-149">Successivamente, digitare **docker** per filtrare i risultati, quindi selezionare l'estensione del supporto per Docker come illustrato nella figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="bed9d-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Visualizzazione dell'estensione Docker per Visual Studio Code.](./media/image20.png)

<span data-ttu-id="bed9d-151">**Figura 4-23**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-151">**Figure 4-23**.</span></span> <span data-ttu-id="bed9d-152">Installazione dell'estensione Docker in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bed9d-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="bed9d-153">Passaggio 2: Creare un Dockerfile correlato a un'immagine esistente (normale sistema operativo o ambienti di sviluppo come NET Core, Node.js e Ruby)</span><span class="sxs-lookup"><span data-stu-id="bed9d-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="bed9d-154">Per ogni immagine da creare e per ogni contenitore da implementare è necessario un `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="bed9d-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="bed9d-155">Se l'app è costituita da un solo servizio personalizzato, sarà necessario un singolo `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="bed9d-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="bed9d-156">Se invece l'app è costituita da più servizi, come nel caso di un'architettura di microservizi, sarà necessario un `Dockerfile` per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="bed9d-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="bed9d-157">Il `DockerFile` viene comunemente inserito nella cartella radice dell'app o del servizio e contiene i comandi necessari che indicano a Docker come configurare ed eseguire l'app o il servizio.</span><span class="sxs-lookup"><span data-stu-id="bed9d-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="bed9d-158">È possibile creare il `DockerFile` e aggiungerlo al progetto insieme al codice (Node.js, .NET Core e così via), oppure se non si ha familiarità con l'ambiente, è consigliabile leggere il suggerimento seguente.</span><span class="sxs-lookup"><span data-stu-id="bed9d-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="bed9d-159">È possibile usare l'estensione Docker per avere indicazioni sull'uso dei file `Dockerfile` e `docker-compose.yml` correlati ai contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="bed9d-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="bed9d-160">Probabilmente alla fine non si userà questo strumento per scrivere questi tipi di file. L'estensione Docker resta comunque un buon punto di partenza che consente di accelerare la curva di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="bed9d-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="bed9d-161">La figura 4-24 visualizza come il file docker-compose viene aggiunto usando l'estensione Docker per Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="bed9d-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Visualizzazione della console dell'estensione Docker per Visual Studio Code.](./media/image24.png)

<span data-ttu-id="bed9d-163">**Figura 4-24**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-163">**Figure 4-24**.</span></span> <span data-ttu-id="bed9d-164">File Docker aggiunti usando il **comando Add Docker files to Workspace** (Aggiungi file Docker all'area di lavoro)</span><span class="sxs-lookup"><span data-stu-id="bed9d-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="bed9d-165">Quando si aggiunge un Dockerfile, specificare l'immagine Docker di base che si userà, ad esempio `FROM mcr.microsoft.com/dotnet/core/aspnet`.</span><span class="sxs-lookup"><span data-stu-id="bed9d-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM mcr.microsoft.com/dotnet/core/aspnet`).</span></span> <span data-ttu-id="bed9d-166">Si creerà generalmente l'immagine personalizzata sulla base di un'immagine disponibile in un qualsiasi repository ufficiale nel [registro Docker Hub](https://hub.docker.com/), ad esempio un'[immagine per .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) o una [per Node.js](https://hub.docker.com/_/node/).</span><span class="sxs-lookup"><span data-stu-id="bed9d-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="bed9d-167">***Usare un'immagine Docker ufficiale esistente***</span><span class="sxs-lookup"><span data-stu-id="bed9d-167">***Use an existing official Docker image***</span></span>

<span data-ttu-id="bed9d-168">L'uso di un repository ufficiale di uno stack di linguaggio con un numero di versione assicura che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.</span><span class="sxs-lookup"><span data-stu-id="bed9d-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="bed9d-169">Di seguito viene riportato un esempio di Dockerfile per un contenitore .NET Core:</span><span class="sxs-lookup"><span data-stu-id="bed9d-169">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="bed9d-170">In questo caso l'immagine si basa sulla versione 2.2 dell'immagine Docker ufficiale di ASP.NET Core (multiarchitettura per Linux e Windows), come indicato dalla riga `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span><span class="sxs-lookup"><span data-stu-id="bed9d-170">In this case, the image is based on version 2.2 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`.</span></span> <span data-ttu-id="bed9d-171">Per altre informazioni su questo argomento, vedere la pagina [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) (Immagine Docker di ASP.NET Core) e la pagina [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) (Immagine Docker di .NET Core).</span><span class="sxs-lookup"><span data-stu-id="bed9d-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) page and the [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) page).</span></span>

<span data-ttu-id="bed9d-172">Nel Dockerfile è possibile indicare a Docker la porta TCP di ascolto che si userà in fase di esecuzione, ad esempio la porta 80.</span><span class="sxs-lookup"><span data-stu-id="bed9d-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="bed9d-173">Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso.</span><span class="sxs-lookup"><span data-stu-id="bed9d-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="bed9d-174">Ad esempio la riga `ENTRYPOINT` con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker di eseguire un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bed9d-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="bed9d-175">Se si usa l'SDK e l'interfaccia della riga di comando di .NET Core(`dotnet CLI`) per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa.</span><span class="sxs-lookup"><span data-stu-id="bed9d-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="bed9d-176">In sostanza la riga ENTRYPOINT e altre impostazioni dipendono dal linguaggio e della piattaforma scelti per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="bed9d-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [!INFORMAZIONI]
>
> <span data-ttu-id="bed9d-178">Per altre informazioni sulla creazione di immagini Docker per applicazioni .NET Core, passare a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="bed9d-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="bed9d-179">Per altre informazioni sulla creazione di immagini personalizzate, passare a <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="bed9d-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="bed9d-180">**Usare repository di immagini multiarchitettura**</span><span class="sxs-lookup"><span data-stu-id="bed9d-180">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="bed9d-181">Un singolo nome di un'immagine in un repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows.</span><span class="sxs-lookup"><span data-stu-id="bed9d-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="bed9d-182">Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows.</span><span class="sxs-lookup"><span data-stu-id="bed9d-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="bed9d-183">Il repository [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) disponibile nel registro Docker Hub offre ad esempio supporto per Linux e Windows Nano Server usando lo stesso nome immagine.</span><span class="sxs-lookup"><span data-stu-id="bed9d-183">For example, the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="bed9d-184">Eseguendo il pull dell'immagine [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome immagine da un host Linux si ottiene la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="bed9d-184">Pulling the [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="bed9d-185">***Creare l'immagine di base da zero***</span><span class="sxs-lookup"><span data-stu-id="bed9d-185">***Create your base image from scratch***</span></span>

<span data-ttu-id="bed9d-186">È possibile creare l'immagine Docker di base personalizzata da zero, come descritto in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) usando Docker.</span><span class="sxs-lookup"><span data-stu-id="bed9d-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="bed9d-187">Non si tratta probabilmente dello scenario più adatto se non si ha ancora familiarità con Docker. È tuttavia possibile adottare questo approccio se si vogliono impostare i bit specifici dell'immagine di base personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bed9d-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="bed9d-188">Passaggio 3: Creare le immagini Docker personalizzate incorporandone il servizio</span><span class="sxs-lookup"><span data-stu-id="bed9d-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="bed9d-189">Per ogni servizio personalizzato comprensivo dell'app sarà necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="bed9d-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="bed9d-190">Se l'app è costituita da un singolo servizio o una singola app Web, sarà sufficiente una sola immagine.</span><span class="sxs-lookup"><span data-stu-id="bed9d-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="bed9d-191">Se si prende in considerazione il "flusso di lavoro del ciclo esterno di DevOps", le immagini saranno create da un processo di compilazione automatico ogni volta che si esegue il push del codice sorgente in un repository Git (integrazione continua). In questo modo le immagini saranno create in quell'ambiente globale partendo dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bed9d-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="bed9d-192">Prima di poter considerare il ciclo esterno, è necessario verificare effettivamente che l'applicazione Docker funzioni correttamente in modo che non venga eseguito il push di codice che potrebbe non funzionare nel sistema di controllo del codice sorgente (Git e così via).</span><span class="sxs-lookup"><span data-stu-id="bed9d-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="bed9d-193">Gli sviluppatori devono quindi prima di tutto eseguire l'intero processo del ciclo interno per testarlo in locale e continuare lo sviluppo finché vogliono eseguire il push di una funzionalità completa oppure passare al sistema di controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="bed9d-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="bed9d-194">Per creare un'immagine nell'ambiente locale e usare il Dockerfile, è possibile usare il comando docker build, come illustrato nella figura 4-25. È anche possibile eseguire `docker-compose up --build` per applicazioni composte da diversi contenitori/servizi.</span><span class="sxs-lookup"><span data-stu-id="bed9d-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Output della console per la compilazione di docker-compose che illustra lo stato di avanzamento del download delle immagini.](./media/image25.png)

<span data-ttu-id="bed9d-196">**Figura 4-25**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-196">**Figure 4-25**.</span></span> <span data-ttu-id="bed9d-197">Esecuzione del comando docker build</span><span class="sxs-lookup"><span data-stu-id="bed9d-197">Running docker build</span></span>

<span data-ttu-id="bed9d-198">Oppure, anziché eseguire direttamente `docker build` dalla cartella di progetto, è possibile prima generare una cartella distribuibile con le librerie di .NET necessarie usando il comando di esecuzione `dotnet publish`, poi eseguire `docker build`.</span><span class="sxs-lookup"><span data-stu-id="bed9d-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="bed9d-199">Questo esempio crea un'immagine Docker denominata `cesardl/netcore-webapi-microservice-docker:first`. `:first` è un tag, ad esempio una versione specifica.</span><span class="sxs-lookup"><span data-stu-id="bed9d-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="bed9d-200">È possibile eseguire questo passaggio per ogni immagine personalizzata che si vuole creare per l'applicazione Docker composta con diversi contenitori.</span><span class="sxs-lookup"><span data-stu-id="bed9d-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="bed9d-201">È possibile trovare le immagini esistenti nel repository locale del computer di sviluppo usando il comando docker images, come illustrato nella figura 4-26.</span><span class="sxs-lookup"><span data-stu-id="bed9d-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Output della console del comando docker images che illustra le immagini esistenti.](./media/image26.png)

<span data-ttu-id="bed9d-203">**Figura 4-26**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-203">**Figure 4-26**.</span></span> <span data-ttu-id="bed9d-204">Visualizzazione delle immagini esistenti usando il comando docker images</span><span class="sxs-lookup"><span data-stu-id="bed9d-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="bed9d-205">Passaggio 4: Definire i servizi in docker-compose.yml quando si compila un'app Docker composta con più servizi</span><span class="sxs-lookup"><span data-stu-id="bed9d-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="bed9d-206">Il file `docker-compose.yml` consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione illustrati nel passaggio della sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="bed9d-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="bed9d-207">Creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello illustrato nel file `docker-compose.yml`:</span><span class="sxs-lookup"><span data-stu-id="bed9d-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

```yml
version: '3.4'
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

<span data-ttu-id="bed9d-208">In questo caso particolare il file definisce due servizi: il servizio Web, vale a dire il servizio personalizzato, e il servizio Redis, un comune servizio cache.</span><span class="sxs-lookup"><span data-stu-id="bed9d-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="bed9d-209">Ogni servizio verrà distribuito come contenitore, quindi è necessaria un'immagine Docker concreta per ognuno.</span><span class="sxs-lookup"><span data-stu-id="bed9d-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="bed9d-210">Per questo servizio Web specifico, l'immagine dovrà eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bed9d-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="bed9d-211">Eseguire la compilazione dal Dockerfile nella directory corrente</span><span class="sxs-lookup"><span data-stu-id="bed9d-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="bed9d-212">Inoltrare la porta 80 esposta nel contenitore alla porta 81 nel computer host</span><span class="sxs-lookup"><span data-stu-id="bed9d-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="bed9d-213">Montare la directory del progetto nell'host/nel codice all'interno del contenitore, in modo che sia possibile modificare il codice senza dover creare nuovamente l'immagine</span><span class="sxs-lookup"><span data-stu-id="bed9d-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="bed9d-214">Collegare il servizio Web al servizio Redis</span><span class="sxs-lookup"><span data-stu-id="bed9d-214">Link the web service to the redis service</span></span>

<span data-ttu-id="bed9d-215">Il servizio Redis usa l'[immagine Redis pubblica più recente](https://hub.docker.com/_/redis/) di cui si esegue il pull dal registro Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="bed9d-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="bed9d-216">[Redis](https://redis.io/) è un sistema comune di cache per applicazioni lato server.</span><span class="sxs-lookup"><span data-stu-id="bed9d-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="bed9d-217">Passaggio 5: Compilare ed eseguire l'app Docker</span><span class="sxs-lookup"><span data-stu-id="bed9d-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="bed9d-218">Se l'app ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, vale a dire una macchina virtuale o un server fisico.</span><span class="sxs-lookup"><span data-stu-id="bed9d-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="bed9d-219">Se invece l'app è costituita da più servizi, è anche necessario *comporla*.</span><span class="sxs-lookup"><span data-stu-id="bed9d-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="bed9d-220">Esistono opzioni diverse.</span><span class="sxs-lookup"><span data-stu-id="bed9d-220">Let's see the different options.</span></span>

<span data-ttu-id="bed9d-221">***Opzione A: Eseguire un contenitore o servizio singolo***</span><span class="sxs-lookup"><span data-stu-id="bed9d-221">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="bed9d-222">È possibile eseguire l'immagine Docker usando il comando docker run, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bed9d-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="bed9d-223">Per questo tipo specifico di distribuzione, le richieste inviate alla porta 80 saranno reindirizzate alla porta interna 5000.</span><span class="sxs-lookup"><span data-stu-id="bed9d-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="bed9d-224">A questo punto l'applicazione si trova in ascolto sulla porta esterna 80 a livello di host.</span><span class="sxs-lookup"><span data-stu-id="bed9d-224">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="bed9d-225">***Opzione B: Comporre ed eseguire un'applicazione con più contenitori***</span><span class="sxs-lookup"><span data-stu-id="bed9d-225">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="bed9d-226">Nella maggior parte degli scenari aziendali un'applicazione Docker sarà composta da più servizi.</span><span class="sxs-lookup"><span data-stu-id="bed9d-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="bed9d-227">In questi casi è possibile eseguire il comando `docker-compose up` (figura 4-27), che userà il file docker-compose.yml che probabilmente è stato creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bed9d-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="bed9d-228">Se eseguito, questo comando distribuisce un'applicazione composta con tutti i relativi contenitori correlati.</span><span class="sxs-lookup"><span data-stu-id="bed9d-228">Running this command deploys a composed application with all of its related containers.</span></span>

![Output della console del comando docker-compose up.](./media/image27.png)

<span data-ttu-id="bed9d-230">**Figura 4-27**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-230">**Figure 4-27**.</span></span> <span data-ttu-id="bed9d-231">Risultati ottenuti eseguendo il comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="bed9d-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="bed9d-232">Dopo aver eseguito il comando `docker-compose up`, l'applicazione e i relativi contenitori correlati vengono distribuiti nell'host Docker, come illustrato nella figura 4-28 (rappresentazione delle macchina virtuale).</span><span class="sxs-lookup"><span data-stu-id="bed9d-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![Macchina virtuale che esegue applicazioni con più contenitori.](./media/image28.png)

<span data-ttu-id="bed9d-234">**Figura 4-28**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-234">**Figure 4-28**.</span></span> <span data-ttu-id="bed9d-235">VM con contenitori Docker distribuiti</span><span class="sxs-lookup"><span data-stu-id="bed9d-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="bed9d-236">Passaggio 6: Testare l'applicazione Docker (in locale, nella macchina virtuale CD locale)</span><span class="sxs-lookup"><span data-stu-id="bed9d-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="bed9d-237">Questo passaggio varia in base all'ambito dell'app.</span><span class="sxs-lookup"><span data-stu-id="bed9d-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="bed9d-238">In una semplice API Web .NET Core "Hello World" distribuita come un contenitore o servizio singolo sarà sufficiente accedere al servizio specificando la porta TCP indicata nel Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="bed9d-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="bed9d-239">Per passare al servizio quando il localhost non è attivo, trovare l'indirizzo IP del computer usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="bed9d-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="bed9d-240">Nell'host Docker aprire un browser e passare al sito. Verrà visualizzato il servizio o l'app in esecuzione, come illustrato nella figura 4-29.</span><span class="sxs-lookup"><span data-stu-id="bed9d-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Visualizzazione del browser con la risposta da localhost/API/values.](./media/image29.png)

<span data-ttu-id="bed9d-242">**Figura 4-29**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-242">**Figure 4-29**.</span></span> <span data-ttu-id="bed9d-243">Test dell'applicazione Docker in locale tramite localhost</span><span class="sxs-lookup"><span data-stu-id="bed9d-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="bed9d-244">Si noti che si sta usando la porta 80, ma internamente si viene reindirizzati alla porta 5000, in base alla distribuzione eseguita con `docker run`, che è stata illustrata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bed9d-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="bed9d-245">È possibile testare l'app usando CURL dal terminale.</span><span class="sxs-lookup"><span data-stu-id="bed9d-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="bed9d-246">In un'installazione Docker in Windows l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4-30.</span><span class="sxs-lookup"><span data-stu-id="bed9d-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Output della console con http://10.0.75.1/API/values ottenuto tramite CURL](./media/image30.png)

<span data-ttu-id="bed9d-248">**Figura 4-30**.</span><span class="sxs-lookup"><span data-stu-id="bed9d-248">**Figure 4-30**.</span></span> <span data-ttu-id="bed9d-249">Test di un'applicazione Docker in locale tramite CURL</span><span class="sxs-lookup"><span data-stu-id="bed9d-249">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="bed9d-250">**Debug di un contenitore in esecuzione in Docker**</span><span class="sxs-lookup"><span data-stu-id="bed9d-250">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="bed9d-251">Visual Studio Code supporta il debug Docker se si usa Node.js e altre piattaforme, ad esempio contenitori di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bed9d-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="bed9d-252">È anche possibile eseguire il debug di contenitori di .NET Framework o .NET Core in Docker quando si usa Visual Studio per Windows o Mac, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="bed9d-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [!INFORMAZIONI]
>
> <span data-ttu-id="bed9d-254">Per altre informazioni sul debug di contenitori Node.js in Docker, passare a <https://blog.docker.com/2016/07/live-debugging-docker/> e <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span><span class="sxs-lookup"><span data-stu-id="bed9d-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bed9d-255">[Precedente](docker-apps-development-environment.md)
>[Successivo](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="bed9d-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
