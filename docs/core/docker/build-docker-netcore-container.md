---
title: Distribuire un'app in un contenitore con Docker - Esercitazione
description: In questa esercitazione si apprenderà come distribuire un'applicazione .NET Core in un contenitore con Docker.
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 8255a901c706e55e143cdf23dda0eb9bc79d245d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58844964"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="e0c38-103">Esercitazione: Distribuire un'app .NET Core in un contenitore</span><span class="sxs-lookup"><span data-stu-id="e0c38-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="e0c38-104">Questa esercitazione illustra come compilare un'immagine Docker che contiene un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0c38-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="e0c38-105">L'immagine può essere usata per creare contenitori per l'ambiente di sviluppo locale, il cloud privato o il cloud pubblico.</span><span class="sxs-lookup"><span data-stu-id="e0c38-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="e0c38-106">In questa esercitazione si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="e0c38-106">In this tutorial you will learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="e0c38-107">Creare un Dockerfile</span><span class="sxs-lookup"><span data-stu-id="e0c38-107">Create a Dockerfile</span></span>
> * <span data-ttu-id="e0c38-108">Eseguire il pull di un'immagine Docker di Microsoft .NET Core</span><span class="sxs-lookup"><span data-stu-id="e0c38-108">Pull a Microsoft .NET Core Docker base image</span></span>
> * <span data-ttu-id="e0c38-109">Personalizzare e distribuire l'app nell'immagine</span><span class="sxs-lookup"><span data-stu-id="e0c38-109">Customize and deploy your app to the image</span></span>
> * <span data-ttu-id="e0c38-110">Creare ed eseguire un contenitore</span><span class="sxs-lookup"><span data-stu-id="e0c38-110">Create and run a container</span></span>
> * <span data-ttu-id="e0c38-111">Distribuire in Azure</span><span class="sxs-lookup"><span data-stu-id="e0c38-111">Deploy to Azure</span></span>

<span data-ttu-id="e0c38-112">Questa esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0c38-112">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="e0c38-113">La [piattaforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) usa il [motore Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) per compilare e creare pacchetti rapidamente per le app come [immagini Docker](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="e0c38-113">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="e0c38-114">Queste immagini vengono scritte nel formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) per la distribuzione e l'esecuzione in un [contenitore su più livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="e0c38-114">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>



## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="e0c38-115">.NET Core: il modo più semplice per iniziare</span><span class="sxs-lookup"><span data-stu-id="e0c38-115">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="e0c38-116">Prima di creare l'immagine Docker è necessaria un'applicazione da aggiungere a un contenitore.</span><span class="sxs-lookup"><span data-stu-id="e0c38-116">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="e0c38-117">È possibile crearla in Linux, MacOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="e0c38-117">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="e0c38-118">Il modo più veloce e semplice per farlo consiste nell'usare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e0c38-118">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="e0c38-119">Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="e0c38-119">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="e0c38-120">È possibile compilare sia contenitori Windiws che Linux con [tag basati su più architetture](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="e0c38-120">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="e0c38-121">La prima app Docker .NET Core</span><span class="sxs-lookup"><span data-stu-id="e0c38-121">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="e0c38-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e0c38-122">Prerequisites</span></span>

<span data-ttu-id="e0c38-123">Per completare questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="e0c38-123">To complete this tutorial:</span></span>

#### <a name="net-core-sdk"></a><span data-ttu-id="e0c38-124">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="e0c38-124">.NET Core SDK</span></span>

* <span data-ttu-id="e0c38-125">Installare [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="e0c38-125">Install [.NET Core 2.1 SDK](https://www.microsoft.com/net/download) or later.</span></span>

<span data-ttu-id="e0c38-126">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.1., le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.1. Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1 - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="e0c38-126">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) for the complete list of .NET Core 2.1 supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="e0c38-127">Installare l'editor del codice preferito, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="e0c38-127">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="e0c38-128">È necessario installare un editor del codice?</span><span class="sxs-lookup"><span data-stu-id="e0c38-128">Need to install a code editor?</span></span> <span data-ttu-id="e0c38-129">Provare [Visual Studio Code](https://code.visualstudio.com/download).</span><span class="sxs-lookup"><span data-stu-id="e0c38-129">Try [Visual Studio Code](https://code.visualstudio.com/download)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="e0c38-130">Installazione del client di Docker</span><span class="sxs-lookup"><span data-stu-id="e0c38-130">Installing Docker Client</span></span>

<span data-ttu-id="e0c38-131">Installare [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) o una versione successiva del client di Docker.</span><span class="sxs-lookup"><span data-stu-id="e0c38-131">Install [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="e0c38-132">Il client di Docker può essere installato in:</span><span class="sxs-lookup"><span data-stu-id="e0c38-132">The Docker client can be installed in:</span></span>

* <span data-ttu-id="e0c38-133">Distribuzioni di Linux</span><span class="sxs-lookup"><span data-stu-id="e0c38-133">Linux distributions</span></span>

   * [<span data-ttu-id="e0c38-134">CentOS</span><span class="sxs-lookup"><span data-stu-id="e0c38-134">CentOS</span></span>](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [<span data-ttu-id="e0c38-135">Debian</span><span class="sxs-lookup"><span data-stu-id="e0c38-135">Debian</span></span>](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [<span data-ttu-id="e0c38-136">Fedora</span><span class="sxs-lookup"><span data-stu-id="e0c38-136">Fedora</span></span>](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [<span data-ttu-id="e0c38-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e0c38-137">Ubuntu</span></span>](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [<span data-ttu-id="e0c38-138">macOS</span><span class="sxs-lookup"><span data-stu-id="e0c38-138">macOS</span></span>](https://docs.docker.com/docker-for-mac/install/)

* <span data-ttu-id="e0c38-139">[Windows](https://docs.docker.com/docker-for-windows/install/).</span><span class="sxs-lookup"><span data-stu-id="e0c38-139">[Windows](https://docs.docker.com/docker-for-windows/install/).</span></span>

### <a name="create-a-net-core-21-console-app-for-dockerization"></a><span data-ttu-id="e0c38-140">Creare un'app console .NET Core 2.1 per il contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="e0c38-140">Create a .NET Core 2.1 console app for Dockerization</span></span>

<span data-ttu-id="e0c38-141">Aprire un prompt dei comandi e creare una cartella denominata *Hello*.</span><span class="sxs-lookup"><span data-stu-id="e0c38-141">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="e0c38-142">Passare alla cartella creata e digitare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0c38-142">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="e0c38-143">Ecco una descrizione rapida dei comandi digitati:</span><span class="sxs-lookup"><span data-stu-id="e0c38-143">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="e0c38-144">[`dotnet new`](../tools/dotnet-new.md) crea un file di progetto `Hello.csproj` aggiornato con le dipendenze necessarie per compilare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="e0c38-144">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="e0c38-145">Crea inoltre un file `Program.cs` di base contenente il punto di ingresso per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e0c38-145">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="e0c38-146">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="e0c38-146">`Hello.csproj`:</span></span>

   <span data-ttu-id="e0c38-147">Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.</span><span class="sxs-lookup"><span data-stu-id="e0c38-147">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="e0c38-148">Il tag `OutputType` specifica che si sta compilando un file eseguibile, ovvero un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="e0c38-148">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="e0c38-149">Il tag `TargetFramework` specifica l'implementazione di .NET di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e0c38-149">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="e0c38-150">In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per i framework specificati in un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="e0c38-150">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="e0c38-151">In questa esercitazione, la destinazione di compilazione è .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="e0c38-151">In this tutorial, we build for .NET Core 2.1.</span></span>

   <span data-ttu-id="e0c38-152">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="e0c38-152">`Program.cs`:</span></span>

   <span data-ttu-id="e0c38-153">Il programma inizia con `using System`.</span><span class="sxs-lookup"><span data-stu-id="e0c38-153">The program starts by `using System`.</span></span> <span data-ttu-id="e0c38-154">Questa istruzione significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file".</span><span class="sxs-lookup"><span data-stu-id="e0c38-154">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="e0c38-155">Lo spazio dei nomi `System` include costrutti di base come `string` o tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="e0c38-155">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="e0c38-156">Viene quindi definito uno spazio dei nomi denominato `Hello`.</span><span class="sxs-lookup"><span data-stu-id="e0c38-156">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="e0c38-157">È comunque possibile modificare lo spazio dei nomi secondo le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="e0c38-157">You can change namespace to anything you want.</span></span> <span data-ttu-id="e0c38-158">All'interno dello spazio dei nomi viene definita una classe denominata `Program` con un metodo `Main` che accetta come argomento una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="e0c38-158">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="e0c38-159">Tale matrice contiene l'elenco degli argomenti passati nel momento in cui viene chiamato il programma compilato.</span><span class="sxs-lookup"><span data-stu-id="e0c38-159">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="e0c38-160">In questo esempio, il programma scrive solo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="e0c38-160">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="e0c38-161">nella console.</span><span class="sxs-lookup"><span data-stu-id="e0c38-161">to the console.</span></span>

   <span data-ttu-id="e0c38-162">**dotnet new** esegue il comando [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="e0c38-162">**dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="e0c38-163">**Dotnet restore** ripristina l'albero delle dipendenze con una chiamata [NuGet](https://www.nuget.org/) (gestione pacchetti .NET).</span><span class="sxs-lookup"><span data-stu-id="e0c38-163">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="e0c38-164">NuGet esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0c38-164">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="e0c38-165">Analizza il file *Hello.csproj*.</span><span class="sxs-lookup"><span data-stu-id="e0c38-165">analyzes the *Hello.csproj* file.</span></span>
   * <span data-ttu-id="e0c38-166">Scarica le dipendenze del file (o le recupera dalla cache del computer).</span><span class="sxs-lookup"><span data-stu-id="e0c38-166">downloads the file dependencies (or grabs from your machine cache).</span></span>
   * <span data-ttu-id="e0c38-167">Scrive il file *obj/project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e0c38-167">writes the *obj/project.assets.json* file.</span></span>

   <span data-ttu-id="e0c38-168">Il file *project.assets.json* è un set completo delle grafico delle dipendenze di NuGet, delle risoluzioni dei binding e di altri metadati dell'app.</span><span class="sxs-lookup"><span data-stu-id="e0c38-168">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="e0c38-169">Questo file obbligatorio viene usato da altri strumenti, ad esempio [`dotnet build`](../tools/dotnet-build.md) e [`dotnet run`](../tools/dotnet-run.md), per elaborare correttamente il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="e0c38-169">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>

2. `$ dotnet run`

   <span data-ttu-id="e0c38-170">[`dotnet run`](../tools/dotnet-run.md) chiama [`dotnet build`](../tools/dotnet-build.md) per verificare che la compilazione sia corretta e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e0c38-170">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>

    ```console
    $ dotnet run

    Hello World!
    ```

    <span data-ttu-id="e0c38-171">Per scenari avanzati, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md) per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="e0c38-171">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="e0c38-172">Usare i contenitori Docker per l'applicazione .NET Core</span><span class="sxs-lookup"><span data-stu-id="e0c38-172">Dockerize the .NET Core application</span></span>

<span data-ttu-id="e0c38-173">L'app console .NET Core Hello viene eseguita correttamente in locale.</span><span class="sxs-lookup"><span data-stu-id="e0c38-173">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="e0c38-174">A questo punto è possibile procedere e compilare ed eseguire l'app in Docker.</span><span class="sxs-lookup"><span data-stu-id="e0c38-174">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="e0c38-175">Il primo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="e0c38-175">Your first Dockerfile</span></span>

<span data-ttu-id="e0c38-176">Per iniziare, aprire l'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="e0c38-176">Open your text editor and let's get started!</span></span> <span data-ttu-id="e0c38-177">Si lavorerà ancora dalla directory Hello in cui è stata compilata l'app.</span><span class="sxs-lookup"><span data-stu-id="e0c38-177">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="e0c38-178">Aggiungere le istruzioni seguenti di Docker per i contenitori Linux o i [contenitori Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) in un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="e0c38-178">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="e0c38-179">Al termine, salvarlo nella radice della directory Hello come **Dockerfile**, senza estensione (potrebbe essere necessario impostare il tipo di file su `All types (*.*)` o un valore analogo).</span><span class="sxs-lookup"><span data-stu-id="e0c38-179">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="e0c38-180">Il Dockerfile contiene istruzioni per la compilazione di Docker eseguite in sequenza.</span><span class="sxs-lookup"><span data-stu-id="e0c38-180">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="e0c38-181">La prima istruzione deve essere [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="e0c38-181">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="e0c38-182">Questa istruzione inizializza una nuova fase di compilazione e imposta l'immagine di base per le istruzioni rimanenti.</span><span class="sxs-lookup"><span data-stu-id="e0c38-182">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="e0c38-183">I tag basati su più architetture eseguono il pull dei contenitori Windows o Linux a seconda della [modalità contenitore](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) di Docker per Windows.</span><span class="sxs-lookup"><span data-stu-id="e0c38-183">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="e0c38-184">L'immagine di base per l'esempio è l'immagine 2.1-sdk dal repository microsoft/dotnet:</span><span class="sxs-lookup"><span data-stu-id="e0c38-184">The Base Image for our sample is the 2.1-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

<span data-ttu-id="e0c38-185">L'istruzione [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) imposta la directory di lavoro per eventuali istruzioni Dockerfile RUN, CMD, ENTRYPOINT, COPY e ADD rimanenti.</span><span class="sxs-lookup"><span data-stu-id="e0c38-185">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="e0c38-186">Se la directory non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="e0c38-186">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="e0c38-187">In questo caso, WORKDIR viene impostata sulla directory dell'app.</span><span class="sxs-lookup"><span data-stu-id="e0c38-187">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="e0c38-188">L'istruzione [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) copia i nuovi file o le nuove directory dal percorso di origine e li aggiunge al file system del contenitore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e0c38-188">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="e0c38-189">Con questa istruzione, il file di progetto C# viene copiato nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="e0c38-189">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="e0c38-190">L'istruzione [**RUN**](https://docs.docker.com/engine/reference/builder/#run) esegue qualsiasi comando in un nuovo livello sopra l'immagine corrente ed esegue il commit dei risultati.</span><span class="sxs-lookup"><span data-stu-id="e0c38-190">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="e0c38-191">L'immagine risultante viene usata nel passaggio successivo nel Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e0c38-191">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="e0c38-192">Viene eseguito il comando **dotnet restore** per ottenere le dipendenze necessarie del file di progetto C#.</span><span class="sxs-lookup"><span data-stu-id="e0c38-192">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span>

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="e0c38-193">L'istruzione **COPY** copia il resto dei file nel contenitore in nuovi [livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="e0c38-193">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="e0c38-194">L'app viene pubblicata con questa istruzione **RUN**.</span><span class="sxs-lookup"><span data-stu-id="e0c38-194">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="e0c38-195">Il comando [**dotnet publish**](../tools/dotnet-publish.md) compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="e0c38-195">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="e0c38-196">L'app viene pubblicata con la configurazione **Versione** e l'output collocato nella directory predefinita.</span><span class="sxs-lookup"><span data-stu-id="e0c38-196">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="e0c38-197">L'istruzione [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) consente di eseguire il contenitore come eseguibile.</span><span class="sxs-lookup"><span data-stu-id="e0c38-197">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="e0c38-198">È ora disponibile un Dockerfile che:</span><span class="sxs-lookup"><span data-stu-id="e0c38-198">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="e0c38-199">Copia l'app nell'immagine</span><span class="sxs-lookup"><span data-stu-id="e0c38-199">copies your app to the image</span></span>
* <span data-ttu-id="e0c38-200">Include le dipendenze dell'app nell'immagine</span><span class="sxs-lookup"><span data-stu-id="e0c38-200">your app's dependencies to the image</span></span>
* <span data-ttu-id="e0c38-201">Compila l'app per l'esecuzione come eseguibile</span><span class="sxs-lookup"><span data-stu-id="e0c38-201">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-app"></a><span data-ttu-id="e0c38-202">Compilare ed eseguire l'app .NET Core Hello</span><span class="sxs-lookup"><span data-stu-id="e0c38-202">Build and run the Hello .NET Core app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="e0c38-203">Comandi Docker essenziali</span><span class="sxs-lookup"><span data-stu-id="e0c38-203">Essential Docker commands</span></span>

<span data-ttu-id="e0c38-204">Questi comandi Docker sono essenziali:</span><span class="sxs-lookup"><span data-stu-id="e0c38-204">These Docker commands are essential:</span></span>

* [<span data-ttu-id="e0c38-205">docker build</span><span class="sxs-lookup"><span data-stu-id="e0c38-205">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="e0c38-206">docker run</span><span class="sxs-lookup"><span data-stu-id="e0c38-206">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="e0c38-207">docker ps</span><span class="sxs-lookup"><span data-stu-id="e0c38-207">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="e0c38-208">docker stop</span><span class="sxs-lookup"><span data-stu-id="e0c38-208">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="e0c38-209">docker rm</span><span class="sxs-lookup"><span data-stu-id="e0c38-209">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="e0c38-210">docker rmi</span><span class="sxs-lookup"><span data-stu-id="e0c38-210">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="e0c38-211">docker image</span><span class="sxs-lookup"><span data-stu-id="e0c38-211">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="e0c38-212">Compilare ed eseguire</span><span class="sxs-lookup"><span data-stu-id="e0c38-212">Build and run</span></span>

<span data-ttu-id="e0c38-213">Dopo aver scritto il Dockerfile, Docker ora compila l'app e quindi esegue il contenitore.</span><span class="sxs-lookup"><span data-stu-id="e0c38-213">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="e0c38-214">L'output del comando `docker build` dovrebbe essere simile all'output della console seguente:</span><span class="sxs-lookup"><span data-stu-id="e0c38-214">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="e0c38-215">Come si vede dall'output, il motore Docker ha usato il Dockerfile per creare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="e0c38-215">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="e0c38-216">L'output del comando `docker run` dovrebbe essere simile all'output della console seguente:</span><span class="sxs-lookup"><span data-stu-id="e0c38-216">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="e0c38-217">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e0c38-217">Congratulations!</span></span> <span data-ttu-id="e0c38-218">Sono state eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0c38-218">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="e0c38-219">Creazione di un'app .NET Core locale</span><span class="sxs-lookup"><span data-stu-id="e0c38-219">Created a local .NET Core app</span></span>
> * <span data-ttu-id="e0c38-220">Creazione di un Dockerfile per creare il primo contenitore</span><span class="sxs-lookup"><span data-stu-id="e0c38-220">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="e0c38-221">Compilazione ed esecuzione dell'app nel contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="e0c38-221">Built and ran your Dockerized app</span></span>

## <a name="next-steps"></a><span data-ttu-id="e0c38-222">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e0c38-222">Next steps</span></span>

<span data-ttu-id="e0c38-223">Ecco alcuni dei possibili argomenti con cui proseguire:</span><span class="sxs-lookup"><span data-stu-id="e0c38-223">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="e0c38-224">Video introduttivo alle immagini Docker .NET</span><span class="sxs-lookup"><span data-stu-id="e0c38-224">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* <span data-ttu-id="e0c38-225">[Visual Studio, Docker &amp; Azure Container Instances better together!](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae) (I vantaggi dell'integrazione di Visual Studio, Docker e Istanze di Azure Container)</span><span class="sxs-lookup"><span data-stu-id="e0c38-225">[Visual Studio, Docker & Azure Container Instances better together!](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)</span></span>
* [<span data-ttu-id="e0c38-226">Guide introduttive per Docker per Azure</span><span class="sxs-lookup"><span data-stu-id="e0c38-226">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* <span data-ttu-id="e0c38-227">[Deploy your app on Docker for Azure](https://docs.docker.com/docker-for-azure/deploy/) (Distribuire l'app in Docker per Azure)</span><span class="sxs-lookup"><span data-stu-id="e0c38-227">[Deploy your app on Docker for Azure](https://docs.docker.com/docker-for-azure/deploy/)</span></span>

> [!NOTE]
> <span data-ttu-id="e0c38-228">Se non si ha una sottoscrizione di Azure, [iscriversi subito](https://azure.microsoft.com/free/?b=16.48) per ottenere un account gratuito di 30 giorni e 200 dollari in crediti di Azure per poter provare una combinazione dei servizi di Azure.</span><span class="sxs-lookup"><span data-stu-id="e0c38-228">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="e0c38-229">Immagini Docker usate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="e0c38-229">Docker Images used in this sample</span></span>

<span data-ttu-id="e0c38-230">In questo esempio vengono usate le immagini Docker seguenti</span><span class="sxs-lookup"><span data-stu-id="e0c38-230">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="e0c38-231">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="e0c38-231">Related resources</span></span>

* [<span data-ttu-id="e0c38-232">Esempi di Docker per .NET Core</span><span class="sxs-lookup"><span data-stu-id="e0c38-232">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* <span data-ttu-id="e0c38-233">[Dockerfile on Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile) (Dockerfile in contenitori Windows)</span><span class="sxs-lookup"><span data-stu-id="e0c38-233">[Dockerfile on Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)</span></span>
* [<span data-ttu-id="e0c38-234">Esempi di Docker per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e0c38-234">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* <span data-ttu-id="e0c38-235">[ASP.NET Core on DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/) (ASP.NET Core in DockerHub)</span><span class="sxs-lookup"><span data-stu-id="e0c38-235">[ASP.NET Core on DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)</span></span>
* <span data-ttu-id="e0c38-236">[Dockerize a .NET Core application](https://docs.docker.com/engine/examples/dotnetcore/) (Usare i contenitori Docker per un'applicazione .NET Core) - Esercitazione per Docker</span><span class="sxs-lookup"><span data-stu-id="e0c38-236">[Dockerize a .NET Core application - Docker Tutorial](https://docs.docker.com/engine/examples/dotnetcore/)</span></span>
* <span data-ttu-id="e0c38-237">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Uso degli strumenti Docker per Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e0c38-237">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>
* <span data-ttu-id="e0c38-238">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Distribuzione di immagini Docker dal Registro Azure Container a Istanze di Azure Container)</span><span class="sxs-lookup"><span data-stu-id="e0c38-238">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>