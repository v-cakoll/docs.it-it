---
title: Flusso di lavoro di sviluppo a ciclo interno per le app Docker
description: Descrive il flusso di lavoro "ciclo interno" per lo sviluppo di applicazioni Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 1ed0feeec682f5a79bc38db6a101b751ea4dbc3a
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676668"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a><span data-ttu-id="865ab-103">Flusso di lavoro di sviluppo a ciclo interno per le app Docker</span><span class="sxs-lookup"><span data-stu-id="865ab-103">Inner-loop development workflow for Docker apps</span></span>

<span data-ttu-id="865ab-104">Prima di attivare il flusso di lavoro ciclo esterno che si estende l'intera DevOps del ciclo, tutto ha inizio in ogni computer dello sviluppatore, scrittura di codice dell'app stessa, usando i propri linguaggi Preferiti o piattaforme e testarla in locale (figura 4-21).</span><span class="sxs-lookup"><span data-stu-id="865ab-104">Before triggering the outer-loop workflow spanning the entire DevOps cycle, it all begins on each developer's machine, coding the app itself, using their preferred languages or platforms, and testing it locally (Figure 4-21).</span></span> <span data-ttu-id="865ab-105">Ma in ogni caso, sarà necessario un punto importante in comune, indipendentemente da quale linguaggio, framework o piattaforme scelto.</span><span class="sxs-lookup"><span data-stu-id="865ab-105">But in every case, you'll have an important point in common, no matter what language, framework, or platforms you choose.</span></span> <span data-ttu-id="865ab-106">In questo flusso di lavoro specifico, vengono sempre lo sviluppo, test sui contenitori di Docker, ma in locale.</span><span class="sxs-lookup"><span data-stu-id="865ab-106">In this specific workflow, you're always developing and testing Docker containers, but locally.</span></span>

![Passaggio 1: codice/esecuzione/Debug](./media/image18.png)

<span data-ttu-id="865ab-108">**Figura 4-21**.</span><span class="sxs-lookup"><span data-stu-id="865ab-108">**Figure 4-21**.</span></span> <span data-ttu-id="865ab-109">Contesto di sviluppo a ciclo interno</span><span class="sxs-lookup"><span data-stu-id="865ab-109">Inner-loop development context</span></span>

<span data-ttu-id="865ab-110">Il contenitore o l'istanza di un'immagine Docker conterrà questi componenti:</span><span class="sxs-lookup"><span data-stu-id="865ab-110">The container or instance of a Docker image will contain these components:</span></span>

-   <span data-ttu-id="865ab-111">Una selezione del sistema operativo (ad esempio, una distribuzione Linux o Windows)</span><span class="sxs-lookup"><span data-stu-id="865ab-111">An operating system selection (for example, a Linux distribution or Windows)</span></span>

- <span data-ttu-id="865ab-112">File aggiunti dallo sviluppatore (ad esempio, file binari dell'app)</span><span class="sxs-lookup"><span data-stu-id="865ab-112">Files added by the developer (for example, app binaries)</span></span>

-   <span data-ttu-id="865ab-113">Configurazione (ad esempio, le impostazioni di ambiente e le dipendenze)</span><span class="sxs-lookup"><span data-stu-id="865ab-113">Configuration (for example, environment settings and dependencies)</span></span>

- <span data-ttu-id="865ab-114">Istruzioni per i processi eseguiti da Docker</span><span class="sxs-lookup"><span data-stu-id="865ab-114">Instructions for what processes to run by Docker</span></span>

<span data-ttu-id="865ab-115">È possibile impostare il flusso di lavoro di sviluppo a ciclo interno che prevede l'utilizzo di Docker come il processo (descritto nella sezione successiva).</span><span class="sxs-lookup"><span data-stu-id="865ab-115">You can set up the inner-loop development workflow that utilizes Docker as the process (described in the next section).</span></span> <span data-ttu-id="865ab-116">È consigliabile che i passaggi iniziali per configurare l'ambiente non sono inclusi, perché è sufficiente eseguire una volta.</span><span class="sxs-lookup"><span data-stu-id="865ab-116">Consider that the initial steps to set up the environment are not included, because you only need to do it once.</span></span>

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a><span data-ttu-id="865ab-117">Creazione di una singola app all'interno di un contenitore Docker usando Visual Studio Code e CLI di Docker</span><span class="sxs-lookup"><span data-stu-id="865ab-117">Building a single app within a Docker container using Visual Studio Code and Docker CLI</span></span>

<span data-ttu-id="865ab-118">Le app sono composti da servizi e librerie aggiuntive (dipendenze).</span><span class="sxs-lookup"><span data-stu-id="865ab-118">Apps are made up from your own services plus additional libraries (dependencies).</span></span>

<span data-ttu-id="865ab-119">Figura 4-22 illustra i passaggi di base che è in genere necessario eseguire durante la creazione di un'app Docker, seguita da una descrizione dettagliata di ogni passaggio.</span><span class="sxs-lookup"><span data-stu-id="865ab-119">Figure 4-22 shows the basic steps that you usually need to carry out when building a Docker app, followed by detailed descriptions of each step.</span></span>

![Panoramica del flusso di lavoro: Passaggio 1: codice, passaggio 2: scrittura di Dockerfile, passaggio 3: creare immagini definite con i Dockerfile, passaggio 4: definire i servizi con file docker-Compose, passaggio 5: eseguire contenitori o App composte, passaggio 6 - Test App, passaggio 7: eseguire il Push per iniziare il ciclo esterno (pipeline CI/CD) oppure continuare de veloping.](./media/image19.png)

<span data-ttu-id="865ab-121">**Figura 4-22**.</span><span class="sxs-lookup"><span data-stu-id="865ab-121">**Figure 4-22**.</span></span> <span data-ttu-id="865ab-122">Flusso di lavoro generale per il ciclo di vita per applicazioni Docker in contenitori usando l'interfaccia CLI di Docker</span><span class="sxs-lookup"><span data-stu-id="865ab-122">High-level workflow for the life cycle for Docker containerized applications using Docker CLI</span></span>

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a><span data-ttu-id="865ab-123">Passaggio 1: Iniziare a scrivere codice in Visual Studio Code e creare la linea di base di app/servizio iniziale</span><span class="sxs-lookup"><span data-stu-id="865ab-123">Step 1: Start coding in Visual Studio Code and create your initial app/service baseline</span></span>

<span data-ttu-id="865ab-124">Il modo in cui si sviluppa l'applicazione è simile al modo in che cui avviene senza Docker.</span><span class="sxs-lookup"><span data-stu-id="865ab-124">The way you develop your application is similar to the way you do it without Docker.</span></span> <span data-ttu-id="865ab-125">La differenza è che durante lo sviluppo, si ha la distribuzione e test di applicazioni o servizi in esecuzione all'interno di contenitori Docker inseriti nell'ambiente locale (ad esempio, una VM Linux o Windows).</span><span class="sxs-lookup"><span data-stu-id="865ab-125">The difference is that while developing, you're deploying and testing your application or services running within Docker containers placed in your local environment (like a Linux VM or Windows).</span></span>

<span data-ttu-id="865ab-126">**Configurazione dell'ambiente locale**</span><span class="sxs-lookup"><span data-stu-id="865ab-126">**Setting up your local environment**</span></span>

<span data-ttu-id="865ab-127">Con le versioni più recenti di Docker per Mac e Windows, è più facile che mai per lo sviluppo di applicazioni di Docker, e il programma di installazione è semplice.</span><span class="sxs-lookup"><span data-stu-id="865ab-127">With the latest versions of Docker for Mac and Windows, it's easier than ever to develop Docker applications, and the setup is straightforward.</span></span>

> [! INFORMAZIONI]
>
> <span data-ttu-id="865ab-129">Per istruzioni sulla configurazione di Docker per Windows, passare a <https://docs.docker.com/docker-for-windows/>.</span><span class="sxs-lookup"><span data-stu-id="865ab-129">For instructions on setting up Docker for Windows, go to <https://docs.docker.com/docker-for-windows/>.</span></span>
>
><span data-ttu-id="865ab-130">Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="865ab-130">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="865ab-131">Inoltre, è necessario un editor di codice in modo che è effettivamente possibile sviluppare l'applicazione quando si usa l'interfaccia CLI di Docker.</span><span class="sxs-lookup"><span data-stu-id="865ab-131">In addition, you'll need a code editor so that you can actually develop your application while using Docker CLI.</span></span>

<span data-ttu-id="865ab-132">Microsoft fornisce Visual Studio Code, ovvero un editor di codice leggero che è supportato in Mac, Windows e Linux e offre il supporto IntelliSense con [supporto per molti linguaggi](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python e la maggior parte moderni linguaggi), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [supporto delle estensioni](https://code.visualstudio.com/docs/extensions/overview).</span><span class="sxs-lookup"><span data-stu-id="865ab-132">Microsoft provides Visual Studio Code, which is a lightweight code editor that's supported on Mac, Windows, and Linux, and provides IntelliSense with [support for many languages](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python, and most modern languages), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integration with Git](https://code.visualstudio.com/Docs/editor/versioncontrol) and [extensions support](https://code.visualstudio.com/docs/extensions/overview).</span></span> <span data-ttu-id="865ab-133">Questo editor è un candidato ideale per sviluppatori Mac e Linux.</span><span class="sxs-lookup"><span data-stu-id="865ab-133">This editor is a great fit for Mac and Linux developers.</span></span> <span data-ttu-id="865ab-134">In Windows, è anche possibile usare l'applicazione completa di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="865ab-134">In Windows, you also can use the full Visual Studio application.</span></span>

> [! INFORMAZIONI]
>
> <span data-ttu-id="865ab-136">Per istruzioni sull'installazione di Visual Studio Code per Windows, Mac o Linux, vedere <https://code.visualstudio.com/docs/setup/setup-overview/>.</span><span class="sxs-lookup"><span data-stu-id="865ab-136">For instructions on installing Visual Studio Code for Windows, Mac, or Linux, go to <https://code.visualstudio.com/docs/setup/setup-overview/>.</span></span>
>
> <span data-ttu-id="865ab-137">Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.</span><span class="sxs-lookup"><span data-stu-id="865ab-137">For instructions on setting up Docker for Mac, go to <https://docs.docker.com/docker-for-mac/>.</span></span>

<span data-ttu-id="865ab-138">È possibile lavorare con CLI di Docker e scrivere il codice usando qualsiasi editor di codice, ma con Visual Studio Code con l'estensione Docker semplifica all'autore `Dockerfile` e `docker-compose.yml` file nell'area di lavoro.</span><span class="sxs-lookup"><span data-stu-id="865ab-138">You can work with Docker CLI and write your code using any code editor, but using Visual Studio Code with the Docker extension makes it easy to author `Dockerfile` and `docker-compose.yml` files in your workspace.</span></span> <span data-ttu-id="865ab-139">È anche possibile eseguire le attività e gli script dall'IDE di Visual Studio Code per eseguire i comandi di Docker tramite la CLI di Docker di sotto.</span><span class="sxs-lookup"><span data-stu-id="865ab-139">You can also run tasks and scripts from the Visual Studio Code IDE to execute Docker commands using the Docker CLI underneath.</span></span>

<span data-ttu-id="865ab-140">L'estensione Docker per Visual Studio Code offre le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="865ab-140">The Docker extension for VS Code provides the following features:</span></span>

- <span data-ttu-id="865ab-141">Automatic `Dockerfile` e `docker-compose.yml` generazione di file</span><span class="sxs-lookup"><span data-stu-id="865ab-141">Automatic `Dockerfile` and `docker-compose.yml` file generation</span></span>

- <span data-ttu-id="865ab-142">Suggerimenti per la sintassi di evidenziazione e passare il mouse per `docker-compose.yml` e `Dockerfile` file</span><span class="sxs-lookup"><span data-stu-id="865ab-142">Syntax highlighting and hover tips for `docker-compose.yml` and `Dockerfile` files</span></span>

- <span data-ttu-id="865ab-143">IntelliSense (completamento) per `Dockerfile` e `docker-compose.yml` file</span><span class="sxs-lookup"><span data-stu-id="865ab-143">IntelliSense (completions) for `Dockerfile` and `docker-compose.yml` files</span></span>

- <span data-ttu-id="865ab-144">Il Lint (errori e avvisi) per `Dockerfile` file</span><span class="sxs-lookup"><span data-stu-id="865ab-144">Linting (errors and warnings) for `Dockerfile` files</span></span>

- <span data-ttu-id="865ab-145">Comando dell'integrazione tavolozza (F1) per i comandi di Docker più comuni</span><span class="sxs-lookup"><span data-stu-id="865ab-145">Command Palette (F1) integration for the most common Docker commands</span></span>

- <span data-ttu-id="865ab-146">Integrazione di soluzioni per la gestione delle immagini e contenitori</span><span class="sxs-lookup"><span data-stu-id="865ab-146">Explorer integration for managing Images and Containers</span></span>

- <span data-ttu-id="865ab-147">Distribuire le immagini da DockerHub e registri contenitori di Azure del servizio App di Azure</span><span class="sxs-lookup"><span data-stu-id="865ab-147">Deploy images from DockerHub and Azure Container Registries to Azure App Service</span></span>

<span data-ttu-id="865ab-148">Per installare l'estensione Docker, premere Ctrl + MAIUSC + P, digitare `ext install`, quindi eseguire il comando per l'estensione installa per visualizzare l'elenco di estensioni di Marketplace.</span><span class="sxs-lookup"><span data-stu-id="865ab-148">To install the Docker extension, press Ctrl+Shift+P, type `ext install`, and then run the Install Extension command to bring up the Marketplace extension list.</span></span> <span data-ttu-id="865ab-149">Successivamente, digitare **docker** per filtrare i risultati e quindi selezionare l'estensione del supporto per Docker, come illustrato nella figura 4-23.</span><span class="sxs-lookup"><span data-stu-id="865ab-149">Next, type **docker** to filter the results, and then select the Docker Support extension, as depicted in Figure 4-23.</span></span>

![Visualizzazione dell'estensione Docker per Visual Studio Code.](./media/image20.png)

<span data-ttu-id="865ab-151">**Figura 4-23**.</span><span class="sxs-lookup"><span data-stu-id="865ab-151">**Figure 4-23**.</span></span> <span data-ttu-id="865ab-152">Installazione dell'estensione Docker in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="865ab-152">Installing the Docker Extension in Visual Studio Code</span></span>

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a><span data-ttu-id="865ab-153">Passaggio 2: Creare un DockerFile correlato a un'immagine esistente (normale del sistema operativo o ambienti di sviluppo, come Ruby, Node. js e .NET Core)</span><span class="sxs-lookup"><span data-stu-id="865ab-153">Step 2: Create a DockerFile related to an existing image (plain OS or dev environments like .NET Core, Node.js, and Ruby)</span></span>

<span data-ttu-id="865ab-154">È necessario un `DockerFile` per ogni immagine personalizzata da compilare e ogni contenitore da distribuire.</span><span class="sxs-lookup"><span data-stu-id="865ab-154">You'll need a `DockerFile` per custom image to be built and per container to be deployed.</span></span> <span data-ttu-id="865ab-155">Se l'app è costituita da un solo servizio personalizzato, è necessario un singolo `DockerFile`.</span><span class="sxs-lookup"><span data-stu-id="865ab-155">If your app is made up of a single custom service, you'll need a single `DockerFile`.</span></span> <span data-ttu-id="865ab-156">Ma se l'app è costituita da più servizi (ad esempio un'architettura di microservizi), è necessario uno `Dockerfile` per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="865ab-156">But if your app is composed of multiple services (as in a microservices architecture), you'll need one `Dockerfile` per service.</span></span>

<span data-ttu-id="865ab-157">Il `DockerFile` comunemente viene inserito nella cartella radice dell'app o del servizio e contiene i comandi necessari in modo che Docker sa come configurare ed eseguire tale applicazione o servizio.</span><span class="sxs-lookup"><span data-stu-id="865ab-157">The `DockerFile` is commonly placed in the root folder of your app or service and contains the required commands so that Docker knows how to set up and run that app or service.</span></span> <span data-ttu-id="865ab-158">È possibile creare il `DockerFile` e aggiungerlo al progetto insieme al codice (Node. js, .NET Core, e così via), o, se si ha familiarità con l'ambiente, esaminiamo il suggerimento seguente.</span><span class="sxs-lookup"><span data-stu-id="865ab-158">You can create your `DockerFile` and add it to your project along with your code (node.js, .NET Core, etc.), or, if you're new to the environment, take a look at the following Tip.</span></span>

> [!TIP]
>
> <span data-ttu-id="865ab-159">È possibile usare l'estensione Docker per ottenere istruzioni utili quando si usa la `Dockerfile` e `docker-compose.yml` file correlati per i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="865ab-159">You can use the Docker extension to guide you when using the `Dockerfile` and `docker-compose.yml` files related to your Docker containers.</span></span> <span data-ttu-id="865ab-160">Alla fine, è probabilmente necessario scrivere questi tipi di file senza questo strumento, ma tramite l'estensione Docker è un buon punto di partenza che consente di accelerare la curva di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="865ab-160">Eventually, you'll probably write these kinds of files without this tool, but using the Docker extension is a good starting point that will accelerate your learning curve.</span></span>

<span data-ttu-id="865ab-161">Nella figura 4-24, è possibile visualizzare come un comando docker-compose file viene aggiunto tramite l'estensione Docker per Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="865ab-161">In Figure 4-24, you can see how a docker-compose file is added by using the Docker Extension for VS Code.</span></span>

![Visualizzazione della console dell'estensione Docker per Visual Studio Code.](./media/image24.png)

<span data-ttu-id="865ab-163">**Figura 4-24**.</span><span class="sxs-lookup"><span data-stu-id="865ab-163">**Figure 4-24**.</span></span> <span data-ttu-id="865ab-164">File docker aggiunti usando il **file Docker aggiungere al comando dell'area di lavoro**</span><span class="sxs-lookup"><span data-stu-id="865ab-164">Docker files added using the **Add Docker files to Workspace command**</span></span>

<span data-ttu-id="865ab-165">Quando si aggiunge un DockerFile, è specificare quale immagine Docker di base che verranno utilizzati (come l'uso di `FROM microsoft/aspnetcore`).</span><span class="sxs-lookup"><span data-stu-id="865ab-165">When you add a DockerFile, you specify what base Docker image you’ll be using (like using `FROM microsoft/aspnetcore`).</span></span> <span data-ttu-id="865ab-166">In genere si creerà un'immagine personalizzata all'inizio di un'immagine di base che si ottiene da qualsiasi repository ufficiale nel [registro Docker Hub](https://hub.docker.com/) (ad esempio un [immagine per .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o quello [per Node. js](https://hub.docker.com/_/node/)).</span><span class="sxs-lookup"><span data-stu-id="865ab-166">You'll usually build your custom image on top of a base image that you get from any official repository at the [Docker Hub registry](https://hub.docker.com/) (like an [image for .NET Core](https://hub.docker.com/r/microsoft/dotnet/) or the one [for Node.js](https://hub.docker.com/_/node/)).</span></span>

<span data-ttu-id="865ab-167">***Usare un'immagine Docker ufficiale esistente***</span><span class="sxs-lookup"><span data-stu-id="865ab-167">***Use an existing official Docker image***</span></span>

<span data-ttu-id="865ab-168">Uso di un repository ufficiale di uno stack di linguaggio con un numero di versione garantisce che le stesse funzionalità del linguaggio sono disponibili in tutti i computer (tra cui sviluppo, test e produzione).</span><span class="sxs-lookup"><span data-stu-id="865ab-168">Using an official repository of a language stack with a version number ensures that the same language features are available on all machines (including development, testing, and production).</span></span>

<span data-ttu-id="865ab-169">Di seguito è riportato un esempio di DockerFile per un contenitore di .NET Core:</span><span class="sxs-lookup"><span data-stu-id="865ab-169">The following is a sample DockerFile for a .NET Core container:</span></span>

```Dockerfile
# Base Docker image to use  
FROM microsoft/dotnet:2.1-aspnetcore-runtime
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

<span data-ttu-id="865ab-170">In questo caso, l'immagine si basa sulla versione 2.1 dell'immagine ASP.NET Core Docker ufficiale (multi-arch per Linux e Windows), in base alla riga `FROM microsoft/dotnet:2.1-aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="865ab-170">In this case, the image is based on version 2.1 of the official ASP.NET Core Docker image (multi-arch for Linux and Windows), as per the line `FROM microsoft/dotnet:2.1-aspnetcore-runtime`.</span></span> <span data-ttu-id="865ab-171">(Per altre informazioni su questo argomento, vedere la [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) pagina e il [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) pagina).</span><span class="sxs-lookup"><span data-stu-id="865ab-171">(For more information about this topic, see the [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) page and the [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) page).</span></span>

<span data-ttu-id="865ab-172">Nel DockerFile, è possibile indicare anche Docker per l'ascolto della porta TCP che verrà usato in fase di esecuzione (ad esempio la porta 80).</span><span class="sxs-lookup"><span data-stu-id="865ab-172">In the DockerFile, you can also instruct Docker to listen to the TCP port that you'll use at runtime (such as port 80).</span></span>

<span data-ttu-id="865ab-173">Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso.</span><span class="sxs-lookup"><span data-stu-id="865ab-173">You can specify additional configuration settings in the Dockerfile, depending on the language and framework you're using.</span></span> <span data-ttu-id="865ab-174">Ad esempio, il `ENTRYPOINT` linea con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker per eseguire un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="865ab-174">For instance, the `ENTRYPOINT` line with `["dotnet", "MySingleContainerWebApp.dll"]` tells Docker to run a .NET Core application.</span></span> <span data-ttu-id="865ab-175">Se si usa il SDK e .NET Core CLI (`dotnet CLI`) per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa.</span><span class="sxs-lookup"><span data-stu-id="865ab-175">If you're using the SDK and the .NET Core CLI (`dotnet CLI`) to build and run the .NET application, this setting would be different.</span></span> <span data-ttu-id="865ab-176">L'aspetto essenziale qui è che la riga ENTRYPOINT e altre impostazioni dipendono dal linguaggio e piattaforma che scelta per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="865ab-176">The key point here is that the ENTRYPOINT line and other settings depend on the language and platform you choose for your application.</span></span>

> [! INFORMAZIONI]
>
> <span data-ttu-id="865ab-178">Per altre informazioni sulla creazione di immagini Docker per applicazioni .NET Core, passare a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span><span class="sxs-lookup"><span data-stu-id="865ab-178">For more information about building Docker images for .NET Core applications, go to <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.</span></span>
>
> <span data-ttu-id="865ab-179">Per altre informazioni sulla creazione di immagini personalizzate, passare a <https://docs.docker.com/engine/tutorials/dockerimages/>.</span><span class="sxs-lookup"><span data-stu-id="865ab-179">To learn more about building your own images, go to <https://docs.docker.com/engine/tutorials/dockerimages/>.</span></span>

<span data-ttu-id="865ab-180">**Usare i repository di immagini multi-arch**</span><span class="sxs-lookup"><span data-stu-id="865ab-180">**Use multi-arch image repositories**</span></span>

<span data-ttu-id="865ab-181">Il nome di un'immagine singola in un repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine di Windows.</span><span class="sxs-lookup"><span data-stu-id="865ab-181">A single image name in a repo can contain platform variants, such as a Linux image and a Windows image.</span></span> <span data-ttu-id="865ab-182">Questa funzionalità consente a fornitori come Microsoft (creatori di immagini di base) creare un unico repository per più piattaforme (vale a dire, Linux e Windows).</span><span class="sxs-lookup"><span data-stu-id="865ab-182">This feature allows vendors like Microsoft (base image creators) to create a single repo to cover multiple platforms (that is, Linux and Windows).</span></span> <span data-ttu-id="865ab-183">Ad esempio, il [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository disponibili nel Registro di sistema dell'Hub Docker fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di immagine.</span><span class="sxs-lookup"><span data-stu-id="865ab-183">For example, the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository available in the Docker Hub registry provides support for Linux and Windows Nano Server by using the same image name.</span></span>

<span data-ttu-id="865ab-184">Eseguire il pull il [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) pull di immagini da un host Windows la variante di Windows, mentre il pull lo stesso nome di immagine da un host Linux estrae la variante Linux.</span><span class="sxs-lookup"><span data-stu-id="865ab-184">Pulling the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image from a Windows host pulls the Windows variant, whereas pulling the same image name from a Linux host pulls the Linux variant.</span></span>

<span data-ttu-id="865ab-185">***Creare l'immagine di base da zero***</span><span class="sxs-lookup"><span data-stu-id="865ab-185">***Create your base image from scratch***</span></span>

<span data-ttu-id="865ab-186">È possibile creare la propria immagine di base di Docker da zero, come illustrato in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) da Docker.</span><span class="sxs-lookup"><span data-stu-id="865ab-186">You can create your own Docker base image from scratch as explained in this [article](https://docs.docker.com/engine/userguide/eng-image/baseimages/) from Docker.</span></span> <span data-ttu-id="865ab-187">Questo scenario è probabile che non la migliore se stai iniziando con Docker, ma se si desidera impostare i bit specifici della propria immagine di base, è possibile farlo.</span><span class="sxs-lookup"><span data-stu-id="865ab-187">This scenario is probably not the best for you if you're just starting with Docker, but if you want to set the specific bits of your own base image, you can do it.</span></span>

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a><span data-ttu-id="865ab-188">Passaggio 3: Creare le immagini Docker personalizzate in essa l'incorporamento del servizio</span><span class="sxs-lookup"><span data-stu-id="865ab-188">Step 3: Create your custom Docker images embedding your service in it</span></span>

<span data-ttu-id="865ab-189">Per ogni servizio personalizzata che comprende l'app, è necessario creare un'immagine correlata.</span><span class="sxs-lookup"><span data-stu-id="865ab-189">For each custom service that comprises your app, you'll need to create a related image.</span></span> <span data-ttu-id="865ab-190">Se l'app è costituito da un singolo servizio o un'app web, è necessario avere una sola immagine.</span><span class="sxs-lookup"><span data-stu-id="865ab-190">If your app is made up of a single service or web app, you'll need just a single image.</span></span>

> [!NOTE]
>
> <span data-ttu-id="865ab-191">Quando prendendo in considerazione il "ciclo esterno flusso di lavoro DevOps", verranno create le immagini da un processo di compilazione automatica ogni volta che eseguire il push del codice sorgente in un repository Git (Continuous Integration), in modo che le immagini verranno create in quell'ambiente globale dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="865ab-191">When taking into account the "outer-loop DevOps workflow", the images will be created by an automated build process whenever you push your source code to a Git repository (Continuous Integration), so the images will be created in that global environment from your source code.</span></span>
>
> <span data-ttu-id="865ab-192">Ma prima che passa a tale route ciclo esterno, è necessario verificare che l'applicazione Docker in realtà funziona correttamente in modo che non sono push del codice che potrebbe non funzionare correttamente per il sistema di controllo sorgente (Git e così via).</span><span class="sxs-lookup"><span data-stu-id="865ab-192">But before we consider going to that outer-loop route, we need to ensure that the Docker application is actually working properly so that they don't push code that might not work properly to the source control system (Git, etc.).</span></span>
>
> <span data-ttu-id="865ab-193">Pertanto, ogni sviluppatore deve prima eseguire l'intero processo di ciclo interno per testare in locale e continuare a sviluppare fino a quando non desiderano eseguire il push di una funzionalità completa o modificare il sistema di controllo sorgente.</span><span class="sxs-lookup"><span data-stu-id="865ab-193">Therefore, each developer first needs to do the entire inner-loop process to test locally and continue developing until they want to push a complete feature or change to the source control system.</span></span>

<span data-ttu-id="865ab-194">Per creare un'immagine nell'ambiente locale e Usa il DockerFile, è possibile usare il comando docker build, come illustrato nella figura 4-25 (è anche possibile eseguire `docker-compose up --build` per applicazioni composte da diversi contenitori/servizi).</span><span class="sxs-lookup"><span data-stu-id="865ab-194">To create an image in your local environment and using the DockerFile, you can use the docker build command, as demonstrated in Figure 4-25 (you also can run `docker-compose up --build` for applications composed by several containers/services).</span></span>

![Output della console per la compilazione di docker-Compose, che mostra le immagini di avanzamento del download.](./media/image25.png)

<span data-ttu-id="865ab-196">**Figura 4-25**.</span><span class="sxs-lookup"><span data-stu-id="865ab-196">**Figure 4-25**.</span></span> <span data-ttu-id="865ab-197">Compilazione di docker in esecuzione</span><span class="sxs-lookup"><span data-stu-id="865ab-197">Running docker build</span></span>

<span data-ttu-id="865ab-198">Facoltativamente, anziché eseguire direttamente `docker build` dalla cartella del progetto, è innanzitutto possibile generare una cartella distribuibile con le librerie di .NET necessarie tramite l'esecuzione `dotnet publish` comandi e quindi eseguire `docker build`.</span><span class="sxs-lookup"><span data-stu-id="865ab-198">Optionally, instead of directly running `docker build` from the project folder, you first can generate a deployable folder with the .NET libraries needed by using the run `dotnet publish` command, and then run `docker build`.</span></span>

<span data-ttu-id="865ab-199">In questo esempio crea un'immagine Docker con il nome `cesardl/netcore-webapi-microservice-docker:first` (`:first` è un tag, ad esempio una versione specifica).</span><span class="sxs-lookup"><span data-stu-id="865ab-199">This example creates a Docker image with the name `cesardl/netcore-webapi-microservice-docker:first` (`:first` is a tag, like a specific version).</span></span> <span data-ttu-id="865ab-200">È possibile eseguire questo passaggio per ogni immagine personalizzata che è necessario creare per l'applicazione Docker composta con diversi contenitori.</span><span class="sxs-lookup"><span data-stu-id="865ab-200">You can take this step for each custom image you need to create for your composed Docker application with several containers.</span></span>

<span data-ttu-id="865ab-201">È possibile trovare le immagini esistenti nel repository locale (computer di sviluppo) usando docker immagini comando, come illustrato nella figura 4-26.</span><span class="sxs-lookup"><span data-stu-id="865ab-201">You can find the existing images in your local repository (your development machine) by using the docker images command, as illustrated in Figure 4-26.</span></span>

![Output della console da immagini docker di comando, che mostra le immagini esistenti.](./media/image26.png)

<span data-ttu-id="865ab-203">**Figura 4-26**.</span><span class="sxs-lookup"><span data-stu-id="865ab-203">**Figure 4-26**.</span></span> <span data-ttu-id="865ab-204">Visualizzazione immagini esistente con le immagini docker</span><span class="sxs-lookup"><span data-stu-id="865ab-204">Viewing existing images using docker images</span></span>

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a><span data-ttu-id="865ab-205">Passaggio 4: Definire i servizi in docker-Compose. yml quando si compila un'applicazione Docker composta con più servizi</span><span class="sxs-lookup"><span data-stu-id="865ab-205">Step 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services</span></span>

<span data-ttu-id="865ab-206">Con la `docker-compose.yml` file, è possibile definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione illustrati nella sezione Passaggio successiva.</span><span class="sxs-lookup"><span data-stu-id="865ab-206">With the `docker-compose.yml` file, you can define a set of related services to be deployed as a composed application with the deployment commands explained in the next step section.</span></span>

<span data-ttu-id="865ab-207">Creare file in principale o la cartella soluzione radice; deve essere contenuto simile a quello illustrato in questo `docker-compose.yml` file:</span><span class="sxs-lookup"><span data-stu-id="865ab-207">Create that file in your main or root solution folder; it should have content similar to that shown in this `docker-compose.yml` file:</span></span>

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

<span data-ttu-id="865ab-208">In questo caso particolare, questo file definisce due servizi: il servizio web (il servizio personalizzato) e il servizio redis (un servizio popolare cache).</span><span class="sxs-lookup"><span data-stu-id="865ab-208">In this particular case, this file defines two services: the web service (your custom service) and the redis service (a popular cache service).</span></span> <span data-ttu-id="865ab-209">Ogni servizio verrà distribuito come un contenitore, pertanto è necessario usare un'immagine Docker concreta per ognuno.</span><span class="sxs-lookup"><span data-stu-id="865ab-209">Each service will be deployed as a container, so we need to use a concrete Docker image for each.</span></span> <span data-ttu-id="865ab-210">Per questo servizio web specifico, l'immagine dovrà eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="865ab-210">For this particular web service, the image will need to do the following:</span></span>

- <span data-ttu-id="865ab-211">Compilazione del dockerfile nella directory corrente</span><span class="sxs-lookup"><span data-stu-id="865ab-211">Build from the DockerFile in the current directory</span></span>

- <span data-ttu-id="865ab-212">Inoltrare la porta 80 esposta sul contenitore alla porta 81 nel computer host</span><span class="sxs-lookup"><span data-stu-id="865ab-212">Forward the exposed port 80 on the container to port 81 on the host machine</span></span>

- <span data-ttu-id="865ab-213">Montare la directory del progetto nell'host in cui /code all'interno del contenitore, rendendo possibile la modifica del codice senza dover ricompilare l'immagine</span><span class="sxs-lookup"><span data-stu-id="865ab-213">Mount the project directory on the host to /code within the container, making it possible for you to modify the code without having to rebuild the image</span></span>

- <span data-ttu-id="865ab-214">Collegare il servizio web al servizio redis</span><span class="sxs-lookup"><span data-stu-id="865ab-214">Link the web service to the redis service</span></span>

<span data-ttu-id="865ab-215">Il servizio redis Usa il [immagine redis pubblica più recente](https://hub.docker.com/_/redis/) estratto dal registro Docker Hub.</span><span class="sxs-lookup"><span data-stu-id="865ab-215">The redis service uses the [latest public redis image](https://hub.docker.com/_/redis/) pulled from the Docker Hub registry.</span></span> <span data-ttu-id="865ab-216">[redis](https://redis.io/) è un sistema di cache più diffusi per le applicazioni lato server.</span><span class="sxs-lookup"><span data-stu-id="865ab-216">[redis](https://redis.io/) is a popular cache system for server-side applications.</span></span>

### <a name="step-5-build-and-run-your-docker-app"></a><span data-ttu-id="865ab-217">Passaggio 5: Compilare ed eseguire l'app Docker</span><span class="sxs-lookup"><span data-stu-id="865ab-217">Step 5: Build and run your Docker app</span></span>

<span data-ttu-id="865ab-218">Se l'app ha solo un singolo contenitore, è sufficiente eseguirla distribuendola all'host Docker (macchina virtuale o server fisico).</span><span class="sxs-lookup"><span data-stu-id="865ab-218">If your app has only a single container, you just need to run it by deploying it to your Docker Host (VM or physical server).</span></span> <span data-ttu-id="865ab-219">Tuttavia, se l'app è costituita da più servizi, devi *comporlo*anche.</span><span class="sxs-lookup"><span data-stu-id="865ab-219">However, if your app is made up of multiple services, you need to *compose it*, too.</span></span> <span data-ttu-id="865ab-220">Esaminiamo le diverse opzioni.</span><span class="sxs-lookup"><span data-stu-id="865ab-220">Let's see the different options.</span></span>

<span data-ttu-id="865ab-221">***Opzione a: Eseguire un singolo contenitore o un servizio***</span><span class="sxs-lookup"><span data-stu-id="865ab-221">***Option A: Run a single container or service***</span></span>

<span data-ttu-id="865ab-222">È possibile eseguire l'immagine Docker usando il comando docker run, come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="865ab-222">You can run the Docker image by using the docker run command, as shown here:</span></span>

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

<span data-ttu-id="865ab-223">Per questa distribuzione specifica, si saranno reindirizzando le richieste inviate alla porta 80 alla porta interna 5000.</span><span class="sxs-lookup"><span data-stu-id="865ab-223">For this particular deployment, we'll be redirecting requests sent to port 80 to the internal port 5000.</span></span> <span data-ttu-id="865ab-224">A questo punto l'applicazione è in ascolto sulla porta esterna 80 a livello di host.</span><span class="sxs-lookup"><span data-stu-id="865ab-224">Now the application is listening on the external port 80 at the host level.</span></span>

<span data-ttu-id="865ab-225">***Opzione b: Creare ed eseguire un'applicazione di più contenitori***</span><span class="sxs-lookup"><span data-stu-id="865ab-225">***Option B: Compose and run a multiple-container application***</span></span>

<span data-ttu-id="865ab-226">Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà essere composte da più servizi.</span><span class="sxs-lookup"><span data-stu-id="865ab-226">In most enterprise scenarios, a Docker application will be composed of multiple services.</span></span> <span data-ttu-id="865ab-227">In questi casi, è possibile eseguire il `docker-compose up` comando (figura 4-27), che userà il file docker-Compose. yml che è stato creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="865ab-227">For these cases, you can run the `docker-compose up` command (Figure 4-27), which will use the docker-compose.yml file that you might have created previously.</span></span> <span data-ttu-id="865ab-228">Questo comando consente di distribuire un'applicazione composta con tutti i contenitori correlati.</span><span class="sxs-lookup"><span data-stu-id="865ab-228">Running this command deploys a composed application with all of its related containers.</span></span>

![Output di console il comando docker-compose up comando.](./media/image27.png)

<span data-ttu-id="865ab-230">**Figura 4-27**.</span><span class="sxs-lookup"><span data-stu-id="865ab-230">**Figure 4-27**.</span></span> <span data-ttu-id="865ab-231">Risultati dell'esecuzione del comando "docker-compose up"</span><span class="sxs-lookup"><span data-stu-id="865ab-231">Results of running the "docker-compose up" command</span></span>

<span data-ttu-id="865ab-232">Dopo aver eseguito `docker-compose up`, si distribuisce l'applicazione e i relativi contenitori correlati nell'Host Docker, come illustrato nella figura 4-28, nella rappresentazione di VM.</span><span class="sxs-lookup"><span data-stu-id="865ab-232">After you run `docker-compose up`, you deploy your application and its related container(s) into your Docker Host, as illustrated in Figure 4-28, in the VM representation.</span></span>

![La macchina virtuale in esecuzione applicazioni multicontenitore.](./media/image28.png)

<span data-ttu-id="865ab-234">**Figura 4-28**.</span><span class="sxs-lookup"><span data-stu-id="865ab-234">**Figure 4-28**.</span></span> <span data-ttu-id="865ab-235">VM con contenitori Docker distribuiti</span><span class="sxs-lookup"><span data-stu-id="865ab-235">VM with Docker containers deployed</span></span>

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a><span data-ttu-id="865ab-236">Passaggio 6: Testare l'applicazione Docker (in locale, nella macchina virtuale locale CD)</span><span class="sxs-lookup"><span data-stu-id="865ab-236">Step 6: Test your Docker application (locally, in your local CD VM)</span></span>

<span data-ttu-id="865ab-237">Questo passaggio varia a seconda di ciò che esegue l'app.</span><span class="sxs-lookup"><span data-stu-id="865ab-237">This step will vary depending on what your app is doing.</span></span>

<span data-ttu-id="865ab-238">In un semplice API .NET Core Web "Hello World" distribuito come un singolo contenitore o un servizio, è sufficiente accedere al servizio, fornendo la porta TCP specificata nel DockerFile.</span><span class="sxs-lookup"><span data-stu-id="865ab-238">In a simple .NET Core Web API "Hello World" deployed as a single container or service, you'd just need to access the service by providing the TCP port specified in the DockerFile.</span></span>

<span data-ttu-id="865ab-239">Se localhost non è attivata, per passare al servizio, trovare l'indirizzo IP per la macchina tramite questo comando:</span><span class="sxs-lookup"><span data-stu-id="865ab-239">If localhost is not turned on, to navigate to your service, find the IP address for the machine by using this command:</span></span>

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

<span data-ttu-id="865ab-240">Nell'host Docker, aprire un browser e passare a tale sito. il servizio app/in esecuzione, verrà visualizzato come illustrato nella figura 4-29.</span><span class="sxs-lookup"><span data-stu-id="865ab-240">On the Docker host, open a browser and navigate to that site; you should see your app/service running, as demonstrated in Figure 4-29.</span></span>

![Visualizzazione di esplorazione della risposta da localhost/API/values.](./media/image29.png)

<span data-ttu-id="865ab-242">**Figura 4-29**.</span><span class="sxs-lookup"><span data-stu-id="865ab-242">**Figure 4-29**.</span></span> <span data-ttu-id="865ab-243">Test dell'applicazione Docker in locale mediante localhost</span><span class="sxs-lookup"><span data-stu-id="865ab-243">Testing your Docker application locally using localhost</span></span>

<span data-ttu-id="865ab-244">Si noti che utilizza la porta 80, ma internamente viene reindirizzata alla porta 5000 perché si tratta di come è stato distribuito con `docker run`, come illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="865ab-244">Note that it's using port 80, but internally it's being redirected to port 5000, because that's how it was deployed with `docker run`, as explained earlier.</span></span>

<span data-ttu-id="865ab-245">È possibile verificarlo usando CURL dal terminale.</span><span class="sxs-lookup"><span data-stu-id="865ab-245">You can test this by using CURL from the terminal.</span></span> <span data-ttu-id="865ab-246">In un'installazione di Docker in Windows, l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4-30.</span><span class="sxs-lookup"><span data-stu-id="865ab-246">In a Docker installation on Windows, the default IP is 10.0.75.1, as depicted in Figure 4-30.</span></span>

![Output dall'introduzione della console di http://10.0.75.1/API/values con curl](./media/image30.png)

<span data-ttu-id="865ab-248">**Figura 4-30**.</span><span class="sxs-lookup"><span data-stu-id="865ab-248">**Figure 4-30**.</span></span> <span data-ttu-id="865ab-249">Test di un'applicazione Docker in locale mediante CURL</span><span class="sxs-lookup"><span data-stu-id="865ab-249">Testing a Docker application locally by using CURL</span></span>

<span data-ttu-id="865ab-250">**Debug di un contenitore in esecuzione in Docker**</span><span class="sxs-lookup"><span data-stu-id="865ab-250">**Debugging a container running on Docker**</span></span>

<span data-ttu-id="865ab-251">Visual Studio Code supporta debug Docker se si usa Node. js e altre piattaforme quali contenitori .NET Core.</span><span class="sxs-lookup"><span data-stu-id="865ab-251">Visual Studio Code supports debugging Docker if you're using Node.js and other platforms like .NET Core containers.</span></span>

<span data-ttu-id="865ab-252">È anche possibile eseguire il debug dei contenitori di .NET Framework o .NET Core in Docker quando si usa Visual Studio per Windows o Mac, come descritto nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="865ab-252">You also can debug .NET Core or .NET Framework containers in Docker when using Visual Studio for Windows or Mac, as described in the next section.</span></span>

> [! INFORMAZIONI]
>
> <span data-ttu-id="865ab-254">Per altre informazioni sul debug di contenitori Docker di Node. js, passare a <https://blog.docker.com/2016/07/live-debugging-docker/> e <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span><span class="sxs-lookup"><span data-stu-id="865ab-254">To learn more about debugging Node.js Docker containers, go to <https://blog.docker.com/2016/07/live-debugging-docker/> and <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="865ab-255">[Precedente](docker-apps-development-environment.md)
>[Successivo](visual-studio-tools-for-docker.md)</span><span class="sxs-lookup"><span data-stu-id="865ab-255">[Previous](docker-apps-development-environment.md)
[Next](visual-studio-tools-for-docker.md)</span></span>
