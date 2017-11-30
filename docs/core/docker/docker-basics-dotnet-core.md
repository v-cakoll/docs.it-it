---
title: Nozioni di Docker con .NET Core
description: Un Docker e l'esercitazione di base di .NET Core
keywords: .NET, .NET core, Docker, esercitazione
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a><span data-ttu-id="ce312-104">Nozioni di Docker con .NET Core</span><span class="sxs-lookup"><span data-stu-id="ce312-104">Learn Docker Basics with .NET Core</span></span>

<span data-ttu-id="ce312-105">In questa esercitazione Docker contenitore compilare e distribuire le attività per un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce312-105">This tutorial teaches the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="ce312-106">Nel corso di questa esercitazione, si apprenderà:</span><span class="sxs-lookup"><span data-stu-id="ce312-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="ce312-107">Come creare un Dockerfile</span><span class="sxs-lookup"><span data-stu-id="ce312-107">How to create a Dockerfile</span></span>
> * <span data-ttu-id="ce312-108">Come creare un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce312-108">How to create a .NET Core app.</span></span>
> * <span data-ttu-id="ce312-109">Come distribuire l'app in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="ce312-109">How to deploy your app into a Docker container.</span></span>

<span data-ttu-id="ce312-110">Il [piattaforma Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) utilizza il [motore Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) per compilare rapidamente e pacchetti di applicazioni di esempio [immagini Docker](https://docs.docker.com/glossary/?term=image).</span><span class="sxs-lookup"><span data-stu-id="ce312-110">The [Docker platform](https://docs.docker.com/engine/docker-overview/#the-docker-platform) uses the [Docker Engine](https://docs.docker.com/engine/docker-overview/#docker-engine) to quickly build and package apps as [Docker images](https://docs.docker.com/glossary/?term=image).</span></span> <span data-ttu-id="ce312-111">Queste immagini vengono scritti [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) formato per essere distribuito ed eseguito un [a più livelli contenitore](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span><span class="sxs-lookup"><span data-stu-id="ce312-111">These images are written in the [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) format to be deployed and run in a [layered container](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).</span></span>

## <a name="net-core-easiest-way-to-get-started"></a><span data-ttu-id="ce312-112">.NET core: Il modo più semplice per iniziare</span><span class="sxs-lookup"><span data-stu-id="ce312-112">.NET Core: Easiest way to get started</span></span>

<span data-ttu-id="ce312-113">Prima di creare l'immagine di Docker, è necessario disporre di un'applicazione a inserita in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="ce312-113">Before creating the Docker image, you need an application to containerize.</span></span> <span data-ttu-id="ce312-114">È possibile crearlo in Linux, MacOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="ce312-114">You can create it on Linux, MacOS, or Windows.</span></span> <span data-ttu-id="ce312-115">Il modo più rapido e semplice per eseguire questa operazione consiste nell'utilizzare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ce312-115">The quickest and easiest way to do that is to use .NET Core.</span></span>

<span data-ttu-id="ce312-116">Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="ce312-116">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

<span data-ttu-id="ce312-117">È possibile creare contenitori di Windows e Linux con [multi-arch basati su tag](https://github.com/dotnet/announcements/issues/14).</span><span class="sxs-lookup"><span data-stu-id="ce312-117">You can build both Windows and Linux containers with [multi-arch based tags](https://github.com/dotnet/announcements/issues/14).</span></span>

## <a name="your-first-net-core-docker-app"></a><span data-ttu-id="ce312-118">La prima app .NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="ce312-118">Your first .NET Core Docker app</span></span>

### <a name="prerequisites"></a><span data-ttu-id="ce312-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ce312-119">Prerequisites</span></span>

<span data-ttu-id="ce312-120">Per completare questa esercitazione:</span><span class="sxs-lookup"><span data-stu-id="ce312-120">To complete this tutorial:</span></span>

#### <a name="net-core-20-sdk"></a><span data-ttu-id="ce312-121">.NET core SDK 2.0</span><span class="sxs-lookup"><span data-stu-id="ce312-121">.NET Core 2.0 SDK</span></span>

* <span data-ttu-id="ce312-122">Installare [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="ce312-122">Install [.NET Core SDK 2.0](https://www.microsoft.com/net/core).</span></span>

<span data-ttu-id="ce312-123">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, le versioni di sistemi operativi non supportate e i criteri relativi al ciclo di vita, vedere [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="ce312-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

* <span data-ttu-id="ce312-124">Installare l'editor di codice preferito, se hai già fatto.</span><span class="sxs-lookup"><span data-stu-id="ce312-124">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="ce312-125">È necessario installare un editor di codice?</span><span class="sxs-lookup"><span data-stu-id="ce312-125">Need to install a code editor?</span></span> <span data-ttu-id="ce312-126">Provare a [Visual Studio](https://visualstudio.com/downloads)!</span><span class="sxs-lookup"><span data-stu-id="ce312-126">Try [Visual Studio](https://visualstudio.com/downloads)!</span></span>

#### <a name="installing-docker-client"></a><span data-ttu-id="ce312-127">L'installazione Client di Docker</span><span class="sxs-lookup"><span data-stu-id="ce312-127">Installing Docker Client</span></span>

<span data-ttu-id="ce312-128">Installare [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) o versione successiva del client Docker.</span><span class="sxs-lookup"><span data-stu-id="ce312-128">Install [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) or later of the Docker client.</span></span>

<span data-ttu-id="ce312-129">Il client Docker può essere installato in:</span><span class="sxs-lookup"><span data-stu-id="ce312-129">The Docker client can be installed in:</span></span>

* <span data-ttu-id="ce312-130">Distribuzioni di Linux</span><span class="sxs-lookup"><span data-stu-id="ce312-130">Linux distributions</span></span>

   * [<span data-ttu-id="ce312-131">CentOS</span><span class="sxs-lookup"><span data-stu-id="ce312-131">CentOS</span></span>](https://www.docker.com/docker-centos-distribution)

   * [<span data-ttu-id="ce312-132">Debian</span><span class="sxs-lookup"><span data-stu-id="ce312-132">Debian</span></span>](https://www.docker.com/docker-debian)

   * [<span data-ttu-id="ce312-133">Fedora</span><span class="sxs-lookup"><span data-stu-id="ce312-133">Fedora</span></span>](https://www.docker.com/docker-fedora)

   * [<span data-ttu-id="ce312-134">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="ce312-134">Ubuntu</span></span>](https://www.docker.com/docker-ubuntu)

* [<span data-ttu-id="ce312-135">macOS</span><span class="sxs-lookup"><span data-stu-id="ce312-135">macOS</span></span>](https://docs.docker.com/docker-for-mac/)

* <span data-ttu-id="ce312-136">[Windows](https://docs.docker.com/docker-for-windows/).</span><span class="sxs-lookup"><span data-stu-id="ce312-136">[Windows](https://docs.docker.com/docker-for-windows/).</span></span>

### <a name="create-a-net-core-20-console-app-for-dockerization"></a><span data-ttu-id="ce312-137">Creare un'applicazione console .NET Core 2.0 per Dockerization</span><span class="sxs-lookup"><span data-stu-id="ce312-137">Create a .NET Core 2.0 console app for Dockerization</span></span>

<span data-ttu-id="ce312-138">Aprire un prompt dei comandi e creare una cartella denominata *Hello*.</span><span class="sxs-lookup"><span data-stu-id="ce312-138">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="ce312-139">Passare alla cartella creata e digitare i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce312-139">Navigate to the folder you created and type the following commands:</span></span>

```console
dotnet new console
dotnet run
```

<span data-ttu-id="ce312-140">Ecco una descrizione rapida dei comandi digitati:</span><span class="sxs-lookup"><span data-stu-id="ce312-140">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="ce312-141">[`dotnet new`](../tools/dotnet-new.md) crea un file di progetto `Hello.csproj` aggiornato con le dipendenze necessarie per compilare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="ce312-141">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="ce312-142">Crea inoltre un file `Program.cs` di base contenente il punto di ingresso per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce312-142">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>
   
   <span data-ttu-id="ce312-143">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="ce312-143">`Hello.csproj`:</span></span>

   <span data-ttu-id="ce312-144">Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.</span><span class="sxs-lookup"><span data-stu-id="ce312-144">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="ce312-145">Il tag `OutputType` specifica che si sta compilando un file eseguibile, ovvero un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="ce312-145">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="ce312-146">Il tag `TargetFramework` specifica l'implementazione di .NET di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ce312-146">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="ce312-147">In uno scenario avanzato, è possibile specificare più Framework di destinazione e per i Framework specificati in una singola operazione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="ce312-147">In an advanced scenario, you can specify multiple target frameworks and build to the specified frameworks in a single operation.</span></span> <span data-ttu-id="ce312-148">In questa esercitazione, si compila per Core .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="ce312-148">In this tutorial, we build for .NET Core 2.0.</span></span>

   <span data-ttu-id="ce312-149">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="ce312-149">`Program.cs`:</span></span>

   <span data-ttu-id="ce312-150">Il programma viene avviato da `using System`.</span><span class="sxs-lookup"><span data-stu-id="ce312-150">The program starts by `using System`.</span></span> <span data-ttu-id="ce312-151">Questa istruzione indica, "importare tutti gli elementi il `System` dello spazio dei nomi nell'ambito di questo file."</span><span class="sxs-lookup"><span data-stu-id="ce312-151">This statement means, "Bring everything in the `System` namespace into scope for this file."</span></span> <span data-ttu-id="ce312-152">Lo spazio dei nomi `System` include costrutti di base come `string` o tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="ce312-152">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="ce312-153">Viene quindi definito uno spazio dei nomi denominato `Hello`.</span><span class="sxs-lookup"><span data-stu-id="ce312-153">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="ce312-154">È possibile modificare lo spazio dei nomi per immettere le informazioni desiderate.</span><span class="sxs-lookup"><span data-stu-id="ce312-154">You can change namespace to anything you want.</span></span> <span data-ttu-id="ce312-155">All'interno dello spazio dei nomi viene definita una classe denominata `Program` con un metodo `Main` che accetta come argomento una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="ce312-155">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="ce312-156">Tale matrice contiene l'elenco degli argomenti passati nel momento in cui viene chiamato il programma compilato.</span><span class="sxs-lookup"><span data-stu-id="ce312-156">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="ce312-157">In questo esempio, il programma scrive solo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="ce312-157">In our example, the program only writes "Hello World!"</span></span> <span data-ttu-id="ce312-158">nella console.</span><span class="sxs-lookup"><span data-stu-id="ce312-158">to the console.</span></span>

2. `$ dotnet restore`

   <span data-ttu-id="ce312-159">In .NET Core 2. x, **dotnet nuovo** viene eseguito il [ `dotnet restore` ](../tools/dotnet-restore.md) comando.</span><span class="sxs-lookup"><span data-stu-id="ce312-159">In .NET Core 2.x, **dotnet new** runs the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="ce312-160">**Ripristino dotnet** Ripristina l'albero delle dipendenze con un [NuGet](https://www.nuget.org/)chiamata (gestione di pacchetti .NET).</span><span class="sxs-lookup"><span data-stu-id="ce312-160">**Dotnet restore** restores the tree of dependencies with a [NuGet](https://www.nuget.org/)(.NET package manager) call.</span></span>
   <span data-ttu-id="ce312-161">NuGet esegue le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce312-161">NuGet performs the following tasks:</span></span>
   * <span data-ttu-id="ce312-162">Analizza il *Hello.csproj* file</span><span class="sxs-lookup"><span data-stu-id="ce312-162">analyzes the *Hello.csproj* file</span></span> 
   * <span data-ttu-id="ce312-163">Scarica il file delle dipendenze (o acrobazie dalla cache del computer)</span><span class="sxs-lookup"><span data-stu-id="ce312-163">downloads the file dependencies (or grabs from your machine cache)</span></span>
   * <span data-ttu-id="ce312-164">Scrive il *obj/project.assets.json* file</span><span class="sxs-lookup"><span data-stu-id="ce312-164">writes the *obj/project.assets.json* file</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   <span data-ttu-id="ce312-165">Il *project.assets.json* file è un set completo di grafico di dipendenze di NuGet, associazione risoluzioni e altri metadati dell'app.</span><span class="sxs-lookup"><span data-stu-id="ce312-165">The *project.assets.json* file is a complete set of the NuGet dependencies graph, binding resolutions, and other app metadata.</span></span> <span data-ttu-id="ce312-166">Questa richiesta di file è utilizzato da altri strumenti, ad esempio [ `dotnet build` ](../tools/dotnet-build.md) e [ `dotnet run` ](../tools/dotnet-run.md), elaborare correttamente il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="ce312-166">This required file is used by other tools, such as [`dotnet build`](../tools/dotnet-build.md) and [`dotnet run`](../tools/dotnet-run.md), to correctly process the source code.</span></span>
   
3. `$ dotnet run`

   <span data-ttu-id="ce312-167">[`dotnet run`](../tools/dotnet-run.md)chiamate [ `dotnet build` ](../tools/dotnet-build.md) per verificare una compilazione corretta, quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce312-167">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to confirm a successful build, and then calls `dotnet <assembly.dll>` to run the application.</span></span>
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    <span data-ttu-id="ce312-168">Per gli scenari avanzati, vedere [distribuzione dell'applicazione .NET Core](../deploying/index.md) per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="ce312-168">For advanced scenarios,  see [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

## <a name="dockerize-the-net-core-application"></a><span data-ttu-id="ce312-169">Dockerize l'applicazione .NET Core</span><span class="sxs-lookup"><span data-stu-id="ce312-169">Dockerize the .NET Core application</span></span>

<span data-ttu-id="ce312-170">L'applicazione console Hello .NET Core viene eseguito correttamente in locale.</span><span class="sxs-lookup"><span data-stu-id="ce312-170">The Hello .NET Core console app successfully runs locally.</span></span> <span data-ttu-id="ce312-171">Ora si fare un passo ulteriormente e di compilare ed eseguire l'app in Docker.</span><span class="sxs-lookup"><span data-stu-id="ce312-171">Now let's take it a step further and build and run the app in Docker.</span></span>

### <a name="your-first-dockerfile"></a><span data-ttu-id="ce312-172">Il primo Dockerfile</span><span class="sxs-lookup"><span data-stu-id="ce312-172">Your first Dockerfile</span></span>

<span data-ttu-id="ce312-173">Aprire l'editor di testo ed è possibile iniziare subito!</span><span class="sxs-lookup"><span data-stu-id="ce312-173">Open your text editor and let's get started!</span></span> <span data-ttu-id="ce312-174">Stiamo ancora lavorando dalla directory Hello in che è compilata l'app.</span><span class="sxs-lookup"><span data-stu-id="ce312-174">We're still working from the Hello directory we built the app in.</span></span>

<span data-ttu-id="ce312-175">Aggiungere le seguenti istruzioni di Docker per entrambi Linux o [contenitori di Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) in un nuovo file.</span><span class="sxs-lookup"><span data-stu-id="ce312-175">Add the following Docker instructions for either Linux or [Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) to a new file.</span></span> <span data-ttu-id="ce312-176">Al termine, salvarlo nella radice della directory Hello come **Dockerfile**, senza estensione (potrebbe essere necessario impostare il tipo di file `All types (*.*)` o simile).</span><span class="sxs-lookup"><span data-stu-id="ce312-176">When finished, save it in the root of your Hello directory as **Dockerfile**, with no extension (You may need to set your file type to `All types (*.*)` or something similar).</span></span>

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

<span data-ttu-id="ce312-177">Dockerfile contiene le istruzioni di compilazione Docker che vengono eseguiti in sequenza.</span><span class="sxs-lookup"><span data-stu-id="ce312-177">The Dockerfile contains Docker build instructions that run sequentially.</span></span>

<span data-ttu-id="ce312-178">La prima istruzione deve essere [ **FROM**](https://docs.docker.com/engine/reference/builder/#from).</span><span class="sxs-lookup"><span data-stu-id="ce312-178">The first instruction must be [**FROM**](https://docs.docker.com/engine/reference/builder/#from).</span></span> <span data-ttu-id="ce312-179">Questa istruzione consente di inizializzare una nuova fase di compilazione e imposta l'immagine di Base per le istruzioni rimanenti.</span><span class="sxs-lookup"><span data-stu-id="ce312-179">This instruction initializes a new build stage and sets the Base Image for the remaining instructions.</span></span> <span data-ttu-id="ce312-180">I tag più arch pull contenitori di Windows o Linux a seconda di Docker per Windows [modalità contenitore](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span><span class="sxs-lookup"><span data-stu-id="ce312-180">The multi-arch tags pull either Windows or Linux containers depending on the Docker for Windows [container mode](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers).</span></span> <span data-ttu-id="ce312-181">L'immagine di Base per l'esempio è l'immagine di 2.0 sdk dal repository, microsoft/dotnet</span><span class="sxs-lookup"><span data-stu-id="ce312-181">The Base Image for our sample is the 2.0-sdk image from the microsoft/dotnet repository,</span></span>

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

<span data-ttu-id="ce312-182">Il [ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) istruzione imposta la directory di lavoro per eseguire rimanenti, CMD, il punto di ingresso, copia e Aggiungi Dockerfile istruzioni.</span><span class="sxs-lookup"><span data-stu-id="ce312-182">The [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) instruction sets the working directory for any remaining RUN, CMD, ENTRYPOINT, COPY, and ADD Dockerfile instructions.</span></span> <span data-ttu-id="ce312-183">Se la directory non esiste, viene creato.</span><span class="sxs-lookup"><span data-stu-id="ce312-183">If the directory doesn't exist, it's created.</span></span> <span data-ttu-id="ce312-184">In questo caso, WORKDIR è impostata per la directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ce312-184">In this case, WORKDIR is set to the app directory.</span></span>

```Dockerfile
WORKDIR /app
```

<span data-ttu-id="ce312-185">Il [ **copia** ](https://docs.docker.com/engine/reference/builder/#copy) istruzione consente di copiare nuovi file o directory dal percorso di origine e li aggiunge al file System di contenitore di destinazione.</span><span class="sxs-lookup"><span data-stu-id="ce312-185">The [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) instruction copies new files or directories from the source path and adds them to the destination container filesystem.</span></span> <span data-ttu-id="ce312-186">Con questa istruzione, viene copiato il file di progetto c# per il contenitore.</span><span class="sxs-lookup"><span data-stu-id="ce312-186">With this instruction, we are copying the C# project file to the container.</span></span>

```Dockerfile
COPY *.csproj ./
```

<span data-ttu-id="ce312-187">Il [ **eseguire** ](https://docs.docker.com/engine/reference/builder/#run) istruzione esegue i comandi in un nuovo livello nella parte superiore dell'immagine corrente ed eseguire il commit dei risultati.</span><span class="sxs-lookup"><span data-stu-id="ce312-187">The [**RUN**](https://docs.docker.com/engine/reference/builder/#run) instruction executes any commands in a new layer on top of the current image and commit the results.</span></span> <span data-ttu-id="ce312-188">L'immagine di commit risultante viene utilizzato per il passaggio successivo nel documento Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="ce312-188">The resulting committed image is used for the next step in the Dockerfile.</span></span> <span data-ttu-id="ce312-189">È in esecuzione **dotnet ripristino** per acquisire le dipendenze necessarie del file di progetto c#.</span><span class="sxs-lookup"><span data-stu-id="ce312-189">We are running **dotnet restore** to get the needed dependencies of the C# project file.</span></span> 

```Dockerfile
RUN dotnet restore
```

<span data-ttu-id="ce312-190">Questo **copia** istruzione copia il resto dei file in questo contenitore in nuovi [livelli](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span><span class="sxs-lookup"><span data-stu-id="ce312-190">This **COPY** instruction copies the rest of the files into our container into new [layers](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).</span></span>

```Dockerfile
COPY . ./
```

<span data-ttu-id="ce312-191">Si sta pubblicando l'app con questo **eseguire** (istruzione).</span><span class="sxs-lookup"><span data-stu-id="ce312-191">We are publishing the app with this **RUN** instruction.</span></span> <span data-ttu-id="ce312-192">Il [ **dotnet pubblicare** ](../tools/dotnet-publish.md) comando compila l'applicazione, legge le dipendenze specificate nel file di progetto e pubblica il set di file in una directory.</span><span class="sxs-lookup"><span data-stu-id="ce312-192">The [**dotnet publish**](../tools/dotnet-publish.md) command compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="ce312-193">L'app viene pubblicato con un **versione** configurazione e l'output nella directory predefinita.</span><span class="sxs-lookup"><span data-stu-id="ce312-193">Our app is published with a **Release** configuration and output to the default directory.</span></span>

```Dockerfile
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="ce312-194">Il [ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) istruzione consente al contenitore per l'esecuzione come eseguibile.</span><span class="sxs-lookup"><span data-stu-id="ce312-194">The [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) instruction allows the container to run as an executable.</span></span>

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

<span data-ttu-id="ce312-195">Ora si dispone di un Dockerfile che:</span><span class="sxs-lookup"><span data-stu-id="ce312-195">Now you have a Dockerfile that:</span></span>

* <span data-ttu-id="ce312-196">Copia l'immagine dell'app</span><span class="sxs-lookup"><span data-stu-id="ce312-196">copies your app to the image</span></span>
* <span data-ttu-id="ce312-197">dipendenze dell'applicazione per l'immagine</span><span class="sxs-lookup"><span data-stu-id="ce312-197">your app's dependencies to the image</span></span>
* <span data-ttu-id="ce312-198">Compila l'app per l'esecuzione come eseguibile</span><span class="sxs-lookup"><span data-stu-id="ce312-198">builds the app to run as an executable</span></span>

### <a name="build-and-run-the-hello-net-core-20-app"></a><span data-ttu-id="ce312-199">Compilare ed eseguire l'applicazione Hello .NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ce312-199">Build and run the Hello .NET Core 2.0 app</span></span>

#### <a name="essential-docker-commands"></a><span data-ttu-id="ce312-200">Comandi di Docker essenziali</span><span class="sxs-lookup"><span data-stu-id="ce312-200">Essential Docker commands</span></span>

<span data-ttu-id="ce312-201">Questi comandi di Docker sono essenziali:</span><span class="sxs-lookup"><span data-stu-id="ce312-201">These Docker commands are essential:</span></span>

* [<span data-ttu-id="ce312-202">compilazione docker</span><span class="sxs-lookup"><span data-stu-id="ce312-202">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="ce312-203">esecuzione di docker</span><span class="sxs-lookup"><span data-stu-id="ce312-203">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="ce312-204">docker ps</span><span class="sxs-lookup"><span data-stu-id="ce312-204">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="ce312-205">arresto di docker</span><span class="sxs-lookup"><span data-stu-id="ce312-205">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="ce312-206">docker rm</span><span class="sxs-lookup"><span data-stu-id="ce312-206">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="ce312-207">rmi docker</span><span class="sxs-lookup"><span data-stu-id="ce312-207">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="ce312-208">immagine di docker</span><span class="sxs-lookup"><span data-stu-id="ce312-208">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a><span data-ttu-id="ce312-209">Compilare ed eseguire</span><span class="sxs-lookup"><span data-stu-id="ce312-209">Build and run</span></span>

<span data-ttu-id="ce312-210">È stato scritto il dockerfile; ora Docker compila l'app e quindi esegue il contenitore.</span><span class="sxs-lookup"><span data-stu-id="ce312-210">You wrote the dockerfile; now Docker builds your app and then runs the container.</span></span>

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

<span data-ttu-id="ce312-211">L'output di `docker build` comando dovrebbe essere simile al seguente output di console:</span><span class="sxs-lookup"><span data-stu-id="ce312-211">The output from the `docker build` command should be similar to the following console output:</span></span>

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

<span data-ttu-id="ce312-212">Come si vede dall'output, il motore Docker usati Dockerfile per creare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="ce312-212">As you can see from the output, the Docker Engine used the Dockerfile to build our container.</span></span>

<span data-ttu-id="ce312-213">L'output di `docker run` comando dovrebbe essere simile al seguente output di console:</span><span class="sxs-lookup"><span data-stu-id="ce312-213">The output from the `docker run` command should be similar to the following console output:</span></span>

```console
Hello World!
```

<span data-ttu-id="ce312-214">La procedura è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ce312-214">Congratulations!</span></span> <span data-ttu-id="ce312-215">sono disponibili solo:</span><span class="sxs-lookup"><span data-stu-id="ce312-215">you have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="ce312-216">Ha creato un'applicazione .NET Core locale</span><span class="sxs-lookup"><span data-stu-id="ce312-216">Created a local .NET Core app</span></span>
> * <span data-ttu-id="ce312-217">Creare un Dockerfile per creare il primo contenitore</span><span class="sxs-lookup"><span data-stu-id="ce312-217">Created a Dockerfile to build your first container</span></span>
> * <span data-ttu-id="ce312-218">Compilato ed eseguito l'app Dockerized</span><span class="sxs-lookup"><span data-stu-id="ce312-218">Built and ran your Dockerized app</span></span>



## <a name="next-steps"></a><span data-ttu-id="ce312-219">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ce312-219">Next Steps</span></span>

<span data-ttu-id="ce312-220">Ecco alcuni dei passaggi da eseguire:</span><span class="sxs-lookup"><span data-stu-id="ce312-220">Here are some next steps you can take:</span></span>

* [<span data-ttu-id="ce312-221">Introduzione a .NET Docker immagini Video</span><span class="sxs-lookup"><span data-stu-id="ce312-221">Introduction to .NET Docker Images Video</span></span>](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [<span data-ttu-id="ce312-222">Visual Studio, Docker e istanze di contenitori Azure meglio insieme!</span><span class="sxs-lookup"><span data-stu-id="ce312-222">Visual Studio, Docker & Azure Container Instances better together!</span></span>](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [<span data-ttu-id="ce312-223">Docker per la Guida introduttiva di Azure</span><span class="sxs-lookup"><span data-stu-id="ce312-223">Docker for Azure Quickstarts</span></span>](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [<span data-ttu-id="ce312-224">Distribuire l'app in Docker per Azure</span><span class="sxs-lookup"><span data-stu-id="ce312-224">Deploy your app on Docker for Azure</span></span>](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> <span data-ttu-id="ce312-225">Se non si dispone di una sottoscrizione di Azure, [Iscriviti oggi stesso](https://azure.microsoft.com/free/?b=16.48) per un account gratuito di 30 giorni e get 200 dollari di crediti di Azure per provare qualsiasi combinazione di servizi di Azure.</span><span class="sxs-lookup"><span data-stu-id="ce312-225">If you do not have an Azure subscription, [sign up today](https://azure.microsoft.com/free/?b=16.48) for a free 30-day account and get $200 in Azure Credits to try out any combination of Azure services.</span></span>

## <a name="docker-images-used-in-this-sample"></a><span data-ttu-id="ce312-226">Immagini docker usate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="ce312-226">Docker Images used in this sample</span></span>

<span data-ttu-id="ce312-227">Le immagini Docker seguenti vengono utilizzate in questo esempio</span><span class="sxs-lookup"><span data-stu-id="ce312-227">The following Docker images are used in this sample</span></span>

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a><span data-ttu-id="ce312-228">Risorse correlate</span><span class="sxs-lookup"><span data-stu-id="ce312-228">Related Resources</span></span>

* [<span data-ttu-id="ce312-229">Esempi di .NET core Docker</span><span class="sxs-lookup"><span data-stu-id="ce312-229">.NET Core Docker samples</span></span>](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [<span data-ttu-id="ce312-230">Dockerfile in contenitori di Windows</span><span class="sxs-lookup"><span data-stu-id="ce312-230">Dockerfile on Windows Containers</span></span>](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [<span data-ttu-id="ce312-231">Esempi di .NET framework Docker</span><span class="sxs-lookup"><span data-stu-id="ce312-231">.NET Framework Docker samples</span></span>](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [<span data-ttu-id="ce312-232">ASP.NET Core in cui DockerHub</span><span class="sxs-lookup"><span data-stu-id="ce312-232">ASP.NET Core on DockerHub</span></span>](https://hub.docker.com/r/microsoft/aspnetcore/)
* [<span data-ttu-id="ce312-233">Un'applicazione .NET Core - esercitazione Docker dockerize</span><span class="sxs-lookup"><span data-stu-id="ce312-233">Dockerize a .NET Core application - Docker Tutorial</span></span>](https://docs.docker.com/engine/examples/dotnetcore/)
* [<span data-ttu-id="ce312-234">Utilizzo degli strumenti di Visual Studio Docker</span><span class="sxs-lookup"><span data-stu-id="ce312-234">Working with Visual Studio Docker Tools</span></span>](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [<span data-ttu-id="ce312-235">Distribuzione di immagini Docker dal Registro di sistema contenitore di Azure per le istanze di contenitore di Azure</span><span class="sxs-lookup"><span data-stu-id="ce312-235">Deploying Docker Images from the Azure Container Registry to Azure Container Instances</span></span>](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)