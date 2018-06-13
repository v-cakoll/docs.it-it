---
title: Apprendere le nozioni di base di Docker con .NET Core
description: Esercitazione di base su Docker e .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 02b6b3fc9e149f5d1d5d78e310c7df257be983c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218544"
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="2e26a-103">Apprendere le nozioni di base di Docker con .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e26a-103">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="2e26a-104">Questa esercitazione illustra le attività di compilazione e distribuzione di un contenitore Docker per un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e26a-104">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="2e26a-105">Nel corso di questa esercitazione verranno illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e26a-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="2e26a-106">Come creare un Dockerfile</span><span class="sxs-lookup"><span data-stu-id="2e26a-106">How to create a Dockerfile</span></span>
> * <span data-ttu-id="2e26a-107">Come creare un'app .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e26a-107">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="2e26a-108">Come distribuire l'app in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="2e26a-108">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="2e26a-109">La [piattaforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) usa il [motore Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) per compilare e creare pacchetti rapidamente per le app come [immagini Docker](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="2e26a-109">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="2e26a-110">Queste immagini vengono scritte nel formato [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) per la distribuzione e l'esecuzione in un [contenitore su più livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="2e26a-110">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="2e26a-111">.NET Core: il modo più semplice per iniziare</span><span class="sxs-lookup"><span data-stu-id="2e26a-111">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="2e26a-112">Prima di creare l'immagine Docker è necessaria un'applicazione da aggiungere a un contenitore.</span><span class="sxs-lookup"><span data-stu-id="2e26a-112">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="2e26a-113">È possibile crearla in Linux, MacOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="2e26a-113">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="2e26a-114">Il modo più veloce e semplice per farlo consiste nell'usare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e26a-114">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="2e26a-115">Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e26a-115">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="2e26a-116">È possibile compilare sia contenitori Windiws che Linux con [tag basati su più architetture](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="2e26a-116">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="2e26a-117">La prima app Docker .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e26a-117">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2e26a-118">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="2e26a-118">Prerequisites</span></span>

<span data-ttu-id="2e26a-119">Per completare questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="2e26a-119">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="2e26a-120">.NET Core 2.0 SDK</span><span class="sxs-lookup"><span data-stu-id="2e26a-120">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="2e26a-121">Installare [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="2e26a-121">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="2e26a-122">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="2e26a-122">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="2e26a-123">Installare l'editor del codice preferito, se non è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="2e26a-123">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="2e26a-124">È necessario installare un editor del codice?</span><span class="sxs-lookup"><span data-stu-id="2e26a-124">Need to install a code editor?</span></span> <span data-ttu-id="2e26a-125">Provare [Visual Studio](https://visualstudio.com/downloads).</span><span class="sxs-lookup"><span data-stu-id="2e26a-125">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="2e26a-126">Installazione del client di Docker</span><span class="sxs-lookup"><span data-stu-id="2e26a-126">Installing Docker Client</span></span>

<span data-ttu-id="2e26a-127">Installare [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) o una versione successiva del client di Docker.</span><span class="sxs-lookup"><span data-stu-id="2e26a-127">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="2e26a-128">Il client di Docker può essere installato in:</span><span class="sxs-lookup"><span data-stu-id="2e26a-128">The Docker client can be installed in:</span></span>

* <span data-ttu-id="2e26a-129">Distribuzioni di Linux</span><span class="sxs-lookup"><span data-stu-id="2e26a-129">Linux distributions</span></span>

   * [<span data-ttu-id="2e26a-130">CentOS</span><span class="sxs-lookup"><span data-stu-id="2e26a-130">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="2e26a-131">Debian</span><span class="sxs-lookup"><span data-stu-id="2e26a-131">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="2e26a-132">Fedora</span><span class="sxs-lookup"><span data-stu-id="2e26a-132">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="2e26a-133">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2e26a-133">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="2e26a-134">macOS</span><span class="sxs-lookup"><span data-stu-id="2e26a-134">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="2e26a-135">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="2e26a-135">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="2e26a-136">Creare un'app console .NET Core 2.0 per il contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="2e26a-136">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="2e26a-137">Aprire un prompt dei comandi e creare una cartella denominata *Hello*.</span><span class="sxs-lookup"><span data-stu-id="2e26a-137">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="2e26a-138">Passare alla cartella creata e digitare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e26a-138">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="2e26a-139">Ecco una descrizione rapida dei comandi digitati:</span><span class="sxs-lookup"><span data-stu-id="2e26a-139">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="2e26a-140">[`dotnet new`](../tools/dotnet-new.md) crea un file di progetto `Hello.csproj` aggiornato con le dipendenze necessarie per compilare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="2e26a-140">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="2e26a-141">Crea inoltre un file `Program.cs` di base contenente il punto di ingresso per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e26a-141">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="2e26a-142">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="2e26a-142">`Hello.csproj`:</span></span>

   <span data-ttu-id="2e26a-143">Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.</span><span class="sxs-lookup"><span data-stu-id="2e26a-143">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="2e26a-144">Il tag `OutputType` specifica che si sta compilando un file eseguibile, ovvero un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="2e26a-144">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="2e26a-145">Il tag `TargetFramework` specifica l'implementazione di .NET di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2e26a-145">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="2e26a-146">In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per i framework specificati in un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="2e26a-146">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="2e26a-147">In questa esercitazione, la destinazione di compilazione è .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="2e26a-147">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="2e26a-148">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="2e26a-148">`Program.cs`:</span></span>

   <span data-ttu-id="2e26a-149">Il programma inizia con `using System`.</span><span class="sxs-lookup"><span data-stu-id="2e26a-149">The program starts by `using System`.</span></span> <span data-ttu-id="2e26a-150">Questa istruzione significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file".</span><span class="sxs-lookup"><span data-stu-id="2e26a-150">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="2e26a-151">Lo spazio dei nomi `System` include costrutti di base come `string` o tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="2e26a-151">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="2e26a-152">Viene quindi definito uno spazio dei nomi denominato `Hello`.</span><span class="sxs-lookup"><span data-stu-id="2e26a-152">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="2e26a-153">È comunque possibile modificare lo spazio dei nomi secondo le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="2e26a-153">You can change namespace to anything you want.</span></span> <span data-ttu-id="2e26a-154">All'interno dello spazio dei nomi viene definita una classe denominata `Program` con un metodo `Main` che accetta come argomento una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="2e26a-154">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="2e26a-155">Tale matrice contiene l'elenco degli argomenti passati nel momento in cui viene chiamato il programma compilato.</span><span class="sxs-lookup"><span data-stu-id="2e26a-155">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="2e26a-156">In questo esempio, il programma scrive solo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="2e26a-156">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="2e26a-157">nella console.</span><span class="sxs-lookup"><span data-stu-id="2e26a-157">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="2e26a-158">In .NET Core 2.x, **dotnet new** esegue il comando [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="2e26a-158">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="2e26a-159">**Dotnet restore** ripristina l'albero delle dipendenze con una chiamata [NuGet](https://www.nuget.org/) (gestione pacchetti .NET).</span><span class="sxs-lookup"><span data-stu-id="2e26a-159">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="2e26a-160">NuGet esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e26a-160">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="2e26a-161">Analizza il file *Hello.csproj*</span><span class="sxs-lookup"><span data-stu-id="2e26a-161">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="2e26a-162">Scarica le dipendenze del file (o le recupera dalla cache del computer)</span><span class="sxs-lookup"><span data-stu-id="2e26a-162">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="2e26a-163">Scrive il file *obj/project.assets.json*</span><span class="sxs-lookup"><span data-stu-id="2e26a-163">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="2e26a-164">Il file *project.assets.json* è un set completo delle grafico delle dipendenze di NuGet, delle risoluzioni dei binding e di altri metadati dell'app.</span><span class="sxs-lookup"><span data-stu-id="2e26a-164">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="2e26a-165">Questo file obbligatorio viene usato da altri strumenti, ad esempio [`dotnet build`](../tools/dotnet-build.md) e [`dotnet run`](../tools/dotnet-run.md), per elaborare correttamente il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="2e26a-165">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="2e26a-166">[`dotnet run`](../tools/dotnet-run.md) chiama [`dotnet build`](../tools/dotnet-build.md) per verificare che la compilazione sia corretta e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e26a-166">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="2e26a-167">Per scenari avanzati, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md) per altri dettagli.</span><span class="sxs-lookup"><span data-stu-id="2e26a-167">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="2e26a-168">Usare i contenitori Docker per l'applicazione .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e26a-168">Dockerize the .NET Core application</span></span>

<span data-ttu-id="2e26a-169">L'app console .NET Core Hello viene eseguita correttamente in locale.</span><span class="sxs-lookup"><span data-stu-id="2e26a-169">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="2e26a-170">A questo punto è possibile procedere e compilare ed eseguire l'app in Docker.</span><span class="sxs-lookup"><span data-stu-id="2e26a-170">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="2e26a-171">Il primo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="2e26a-171">Your first Dockerfile</span></span>

<span data-ttu-id="2e26a-172">Per iniziare, aprire l'editor di testo.</span><span class="sxs-lookup"><span data-stu-id="2e26a-172">Open your text editor and let's get started!</span></span> <span data-ttu-id="2e26a-173">Si lavorerà ancora dalla directory Hello in cui è stata compilata l'app.</span><span class="sxs-lookup"><span data-stu-id="2e26a-173">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="2e26a-174">Aggiungere le istruzioni seguenti di Docker per i contenitori Linux o i [contenitori Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) in un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="2e26a-174">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="2e26a-175">Al termine, salvarlo nella radice della directory Hello come **Dockerfile**, senza estensione (potrebbe essere necessario impostare il tipo di file su `All types (*.*)` o un valore analogo).</span><span class="sxs-lookup"><span data-stu-id="2e26a-175">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="2e26a-176">Il Dockerfile contiene istruzioni per la compilazione di Docker eseguite in sequenza.</span><span class="sxs-lookup"><span data-stu-id="2e26a-176">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="2e26a-177">La prima istruzione deve essere [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="2e26a-177">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="2e26a-178">Questa istruzione inizializza una nuova fase di compilazione e imposta l'immagine di base per le istruzioni rimanenti.</span><span class="sxs-lookup"><span data-stu-id="2e26a-178">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="2e26a-179">I tag basati su più architetture eseguono il pull dei contenitori Windows o Linux a seconda della [modalità contenitore](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) di Docker per Windows.</span><span class="sxs-lookup"><span data-stu-id="2e26a-179">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="2e26a-180">L'immagine di base per l'esempio è l'immagine 2.0-sdk dal repository microsoft/dotnet:</span><span class="sxs-lookup"><span data-stu-id="2e26a-180">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="2e26a-181">L'istruzione [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) imposta la directory di lavoro per eventuali istruzioni Dockerfile RUN, CMD, ENTRYPOINT, COPY e ADD rimanenti.</span><span class="sxs-lookup"><span data-stu-id="2e26a-181">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="2e26a-182">Se la directory non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="2e26a-182">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="2e26a-183">In questo caso, WORKDIR viene impostata sulla directory dell'app.</span><span class="sxs-lookup"><span data-stu-id="2e26a-183">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="2e26a-184">L'istruzione [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) copia i nuovi file o le nuove directory dal percorso di origine e li aggiunge al file system del contenitore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2e26a-184">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="2e26a-185">Con questa istruzione, il file di progetto C# viene copiato nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="2e26a-185">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="2e26a-186">L'istruzione [**RUN**](https://docs.docker.com/engine/reference/builder/#run) esegue qualsiasi comando in un nuovo livello sopra l'immagine corrente ed esegue il commit dei risultati.</span><span class="sxs-lookup"><span data-stu-id="2e26a-186">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="2e26a-187">L'immagine risultante viene usata nel passaggio successivo nel Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="2e26a-187">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="2e26a-188">Viene eseguito il comando **dotnet restore** per ottenere le dipendenze necessarie del file di progetto C#.</span><span class="sxs-lookup"><span data-stu-id="2e26a-188">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="2e26a-189">L'istruzione **COPY** copia il resto dei file nel contenitore in nuovi [livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="2e26a-189">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="2e26a-190">L'app viene pubblicata con questa istruzione **RUN**.</span><span class="sxs-lookup"><span data-stu-id="2e26a-190">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="2e26a-191">Il comando [**dotnet publish**](../tools/dotnet-publish.md) compila l'applicazione, legge le relative dipendenze specificate nel file di progetto e pubblica il set di file risultante in una directory.</span><span class="sxs-lookup"><span data-stu-id="2e26a-191">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="2e26a-192">L'app viene pubblicata con la configurazione **Versione** e l'output collocato nella directory predefinita.</span><span class="sxs-lookup"><span data-stu-id="2e26a-192">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="2e26a-193">L'istruzione [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) consente di eseguire il contenitore come eseguibile.</span><span class="sxs-lookup"><span data-stu-id="2e26a-193">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="2e26a-194">È ora disponibile un Dockerfile che:</span><span class="sxs-lookup"><span data-stu-id="2e26a-194">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="2e26a-195">Copia l'app nell'immagine</span><span class="sxs-lookup"><span data-stu-id="2e26a-195">copies your app to the image</span></span>
* <span data-ttu-id="2e26a-196">Include le dipendenze dell'app nell'immagine</span><span class="sxs-lookup"><span data-stu-id="2e26a-196">your app's dependencies to the image</span></span>
* <span data-ttu-id="2e26a-197">Compila l'app per l'esecuzione come eseguibile</span><span class="sxs-lookup"><span data-stu-id="2e26a-197">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="2e26a-198">Compilare ed eseguire l'app .NET Core 2.0 Hello</span><span class="sxs-lookup"><span data-stu-id="2e26a-198">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="2e26a-199">Comandi Docker essenziali</span><span class="sxs-lookup"><span data-stu-id="2e26a-199">Essential Docker commands</span></span>

<span data-ttu-id="2e26a-200">Questi comandi Docker sono essenziali:</span><span class="sxs-lookup"><span data-stu-id="2e26a-200">These Docker commands are essential:</span></span>

* [<span data-ttu-id="2e26a-201">docker build</span><span class="sxs-lookup"><span data-stu-id="2e26a-201">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="2e26a-202">docker run</span><span class="sxs-lookup"><span data-stu-id="2e26a-202">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="2e26a-203">docker ps</span><span class="sxs-lookup"><span data-stu-id="2e26a-203">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="2e26a-204">docker stop</span><span class="sxs-lookup"><span data-stu-id="2e26a-204">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="2e26a-205">docker rm</span><span class="sxs-lookup"><span data-stu-id="2e26a-205">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="2e26a-206">docker rmi</span><span class="sxs-lookup"><span data-stu-id="2e26a-206">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="2e26a-207">docker image</span><span class="sxs-lookup"><span data-stu-id="2e26a-207">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="2e26a-208">Compilare ed eseguire</span><span class="sxs-lookup"><span data-stu-id="2e26a-208">Build and run</span></span>

<span data-ttu-id="2e26a-209">Dopo aver scritto il Dockerfile, Docker ora compila l'app e quindi esegue il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2e26a-209">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="2e26a-210">L'output del comando `docker build` dovrebbe essere simile all'output della console seguente:</span><span class="sxs-lookup"><span data-stu-id="2e26a-210">The output from the `docker build` command should be similar to the following console output:</span></span>

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
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
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

<span data-ttu-id="2e26a-211">Come si vede dall'output, il motore Docker ha usato il Dockerfile per creare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="2e26a-211">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="2e26a-212">L'output del comando `docker run` dovrebbe essere simile all'output della console seguente:</span><span class="sxs-lookup"><span data-stu-id="2e26a-212">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="2e26a-213">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="2e26a-213">Congratulations!</span></span> <span data-ttu-id="2e26a-214">Sono state eseguite le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e26a-214">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2e26a-215">Creazione di un'app .NET Core locale</span><span class="sxs-lookup"><span data-stu-id="2e26a-215">Created a local .NET Core app</span></span>
> * <span data-ttu-id="2e26a-216">Creazione di un Dockerfile per creare il primo contenitore</span><span class="sxs-lookup"><span data-stu-id="2e26a-216">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="2e26a-217">Compilazione ed esecuzione dell'app nel contenitore Docker</span><span class="sxs-lookup"><span data-stu-id="2e26a-217">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="2e26a-218">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2e26a-218">Next Steps</span></span>

<span data-ttu-id="2e26a-219">Ecco alcuni dei possibili argomenti con cui proseguire:</span><span class="sxs-lookup"><span data-stu-id="2e26a-219">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="2e26a-220">Video introduttivo alle immagini Docker .NET</span><span class="sxs-lookup"><span data-stu-id="2e26a-220">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* <span data-ttu-id="2e26a-221">[Visual Studio, Docker & Azure Container Instances better together!](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/) (I vantaggi dell'integrazione di Visual Studio, Docker e le istanze di contenitori di Azure)</span><span class="sxs-lookup"><span data-stu-id="2e26a-221">[Visual Studio, Docker & Azure Container Instances better together!](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)</span></span>
* [<span data-ttu-id="2e26a-222">Guide introduttive per Docker per Azure</span><span class="sxs-lookup"><span data-stu-id="2e26a-222">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* <span data-ttu-id="2e26a-223">[Deploy your app on Docker for Azure](https://docs.docker.com/docker-for-azure/deploy/) (Distribuire l'app in Docker per Azure)</span><span class="sxs-lookup"><span data-stu-id="2e26a-223">[Deploy your app on Docker for Azure](https://docs.docker.com/docker-for-azure/deploy/)</span></span>

> [!Note]
> <span data-ttu-id="2e26a-224">Se non si ha una sottoscrizione di Azure, [iscriversi subito](https://azure.microsoft.com/free/?b=16.48) per ottenere un account gratuito di 30 giorni e 200 dollari in crediti di Azure per poter provare una combinazione dei servizi di Azure.</span><span class="sxs-lookup"><span data-stu-id="2e26a-224">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="2e26a-225">Immagini Docker usate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="2e26a-225">Docker Images used in this sample</span></span>

<span data-ttu-id="2e26a-226">In questo esempio vengono usate le immagini Docker seguenti</span><span class="sxs-lookup"><span data-stu-id="2e26a-226">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="2e26a-227">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="2e26a-227">Related Resources</span></span>

* [<span data-ttu-id="2e26a-228">Esempi di Docker per .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e26a-228">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* <span data-ttu-id="2e26a-229">[Dockerfile on Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile) (Dockerfile in contenitori Windows)</span><span class="sxs-lookup"><span data-stu-id="2e26a-229">[Dockerfile on Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)</span></span>
* [<span data-ttu-id="2e26a-230">Esempi di Docker per .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2e26a-230">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* <span data-ttu-id="2e26a-231">[ASP.NET Core on DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/) (ASP.NET Core in DockerHub)</span><span class="sxs-lookup"><span data-stu-id="2e26a-231">[ASP.NET Core on DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)</span></span>
* <span data-ttu-id="2e26a-232">[Dockerize a .NET Core application](https://docs.docker.com/engine/examples/dotnetcore/) (Usare i contenitori Docker per un'applicazione .NET Core) - Esercitazione per Docker</span><span class="sxs-lookup"><span data-stu-id="2e26a-232">[Dockerize a .NET Core application - Docker Tutorial](https://docs.docker.com/engine/examples/dotnetcore/)</span></span>
* <span data-ttu-id="2e26a-233">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker) (Uso degli strumenti Docker per Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="2e26a-233">[Working with Visual Studio Docker Tools](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)</span></span>
* <span data-ttu-id="2e26a-234">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) (Distribuzione di immagini Docker dal Registro contenitori di Azure a Istanze di contenitore di Azure)</span><span class="sxs-lookup"><span data-stu-id="2e26a-234">[Deploying Docker Images from the Azure Container Registry to Azure Container Instances](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)</span></span>