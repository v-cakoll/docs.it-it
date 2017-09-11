---
title: Microservizi ospitati in Docker - C#
description: Informazioni su come creare servizi ASP.NET Core in esecuzione in contenitori Docker
keywords: .NET, .NET Core, Docker, C#, ASP.NET, microservizio
author: BillWagner
ms.author: wiwagn
ms.date: 02/03/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: csharp
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5585db33fb5020ed18c26f32ce0b63f97353d20f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="e2c68-104">Microservizi ospitati in Docker</span><span class="sxs-lookup"><span data-stu-id="e2c68-104">Microservices hosted in Docker</span></span>

## <a name="introduction"></a><span data-ttu-id="e2c68-105">Introduzione</span><span class="sxs-lookup"><span data-stu-id="e2c68-105">Introduction</span></span>

<span data-ttu-id="e2c68-106">Questa esercitazione descrive nel dettaglio la procedura per creare e distribuire un microservizio ASP.NET Core in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-106">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="e2c68-107">Nel corso di questa esercitazione verranno illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2c68-107">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="e2c68-108">Generazione di un'applicazione ASP.NET Core mediante Yeoman</span><span class="sxs-lookup"><span data-stu-id="e2c68-108">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="e2c68-109">Creazione di un ambiente di sviluppo Docker</span><span class="sxs-lookup"><span data-stu-id="e2c68-109">How to create a development Docker environment</span></span>
* <span data-ttu-id="e2c68-110">Creazione di un'immagine Docker basata su un'immagine esistente</span><span class="sxs-lookup"><span data-stu-id="e2c68-110">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="e2c68-111">Distribuzione del servizio in un ambiente Docker</span><span class="sxs-lookup"><span data-stu-id="e2c68-111">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="e2c68-112">Verranno inoltre illustrate alcune funzionalità del linguaggio C#:</span><span class="sxs-lookup"><span data-stu-id="e2c68-112">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="e2c68-113">Conversione di oggetti C# in payload JSON</span><span class="sxs-lookup"><span data-stu-id="e2c68-113">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="e2c68-114">Creazione di oggetti di trasferimento dati non modificabili</span><span class="sxs-lookup"><span data-stu-id="e2c68-114">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="e2c68-115">Elaborazione delle richieste HTTP in ingresso e generazione della risposta HTTP</span><span class="sxs-lookup"><span data-stu-id="e2c68-115">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="e2c68-116">Uso dei tipi valore nullable</span><span class="sxs-lookup"><span data-stu-id="e2c68-116">How to work with nullable value types</span></span>

<span data-ttu-id="e2c68-117">È possibile [visualizzare o scaricare l'app di esempio](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e2c68-117">You can [view or download the sample app](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="e2c68-118">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e2c68-118">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="e2c68-119">Vantaggi offerti dall'uso di Docker</span><span class="sxs-lookup"><span data-stu-id="e2c68-119">Why Docker?</span></span>

<span data-ttu-id="e2c68-120">Docker semplifica la creazione di immagini delle macchine standard per ospitare i servizi in un data center o nel cloud pubblico.</span><span class="sxs-lookup"><span data-stu-id="e2c68-120">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="e2c68-121">Docker consente di configurare l'immagine e di eseguirne la replica in base alle necessità per scalare l'installazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-121">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="e2c68-122">Tutto il codice riportato in questa esercitazione può essere eseguito in qualsiasi ambiente .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2c68-122">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="e2c68-123">Le attività aggiuntive per un'installazione Docker funzioneranno per un'applicazione ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2c68-123">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e2c68-124">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e2c68-124">Prerequisites</span></span>
<span data-ttu-id="e2c68-125">È necessario configurare il computer per l'esecuzione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2c68-125">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="e2c68-126">Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="e2c68-126">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="e2c68-127">Questa applicazione può essere eseguita in Windows, Ubuntu Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-127">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="e2c68-128">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="e2c68-128">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="e2c68-129">Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma,</span><span class="sxs-lookup"><span data-stu-id="e2c68-129">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="e2c68-130">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="e2c68-130">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="e2c68-131">È inoltre necessario installare il motore di Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-131">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="e2c68-132">Per le istruzioni di installazione relative alla piattaforma in uso, vedere la pagina [Docker Installation](http://www.docker.com/products/docker) (Installazione di Docker).</span><span class="sxs-lookup"><span data-stu-id="e2c68-132">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="e2c68-133">È possibile installare Docker in diverse distribuzioni di Linux, macOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="e2c68-133">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="e2c68-134">La pagina citata sopra contiene sezioni per ciascuna delle installazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="e2c68-134">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="e2c68-135">La maggior parte dei componenti da installare viene eseguita da uno strumento di gestione pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e2c68-135">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="e2c68-136">Se è già installato lo strumento di gestione pacchetti `npm` di Node.js, ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="e2c68-136">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="e2c68-137">In caso contrario, installare la versione più recente di Node.js, scaricabile da [nodejs.org](https://nodejs.org), che installerà lo strumento di gestione pacchetti npm.</span><span class="sxs-lookup"><span data-stu-id="e2c68-137">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="e2c68-138">A questo punto è necessario installare alcuni strumenti da riga di comando che supportano lo sviluppo di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2c68-138">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="e2c68-139">I modelli di riga di comando usano Yeoman, Bower, Grunt e Gulp.</span><span class="sxs-lookup"><span data-stu-id="e2c68-139">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="e2c68-140">Se tali strumenti sono già installati, è positivo. In caso contrario, digitare quanto segue nella shell preferita:</span><span class="sxs-lookup"><span data-stu-id="e2c68-140">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="e2c68-141">L'opzione `-g` indica che si tratta di un'installazione globale e che gli strumenti sono disponibili nell'intero sistema.</span><span class="sxs-lookup"><span data-stu-id="e2c68-141">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="e2c68-142">Un'installazione locale limita l'ambito del pacchetto a un singolo progetto.</span><span class="sxs-lookup"><span data-stu-id="e2c68-142">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="e2c68-143">Dopo avere installato gli strumenti di base, è necessario installare i generatori di modelli yeoman ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="e2c68-143">Once you've installed those core tools, you need to install the yeoman asp.net template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="e2c68-144">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="e2c68-144">Create the Application</span></span>

<span data-ttu-id="e2c68-145">Dopo avere installato tutti gli strumenti, creare una nuova applicazione ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2c68-145">Now that you've installed all the tools, create a new asp.net core application.</span></span> <span data-ttu-id="e2c68-146">Per usare il generatore da riga di comando, eseguire il comando yeoman seguente nella shell preferita:</span><span class="sxs-lookup"><span data-stu-id="e2c68-146">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="e2c68-147">Questo comando richiede di selezionare il tipo di applicazione che si vuole creare.</span><span class="sxs-lookup"><span data-stu-id="e2c68-147">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="e2c68-148">Per questo microservizio, è consigliabile selezionare l'applicazione Web più semplice e leggera possibile. A questo scopo, selezionare Applicazione Web ASP.NET vuota.</span><span class="sxs-lookup"><span data-stu-id="e2c68-148">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="e2c68-149">Il modello richiederà di specificare un nome.</span><span class="sxs-lookup"><span data-stu-id="e2c68-149">The template will prompt you for a name.</span></span> <span data-ttu-id="e2c68-150">Selezionare WeatherMicroservice.</span><span class="sxs-lookup"><span data-stu-id="e2c68-150">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="e2c68-151">Il modello crea automaticamente otto file:</span><span class="sxs-lookup"><span data-stu-id="e2c68-151">The template creates eight files for you:</span></span>

* <span data-ttu-id="e2c68-152">Un file con estensione gitignore, personalizzato per le applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2c68-152">A .gitignore, customized for asp.net core applications.</span></span>
* <span data-ttu-id="e2c68-153">Un file Startup.cs,</span><span class="sxs-lookup"><span data-stu-id="e2c68-153">A Startup.cs file.</span></span> <span data-ttu-id="e2c68-154">contenente la base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-154">This contains the basis of the application.</span></span>
* <span data-ttu-id="e2c68-155">Un file Program.cs,</span><span class="sxs-lookup"><span data-stu-id="e2c68-155">A Program.cs file.</span></span> <span data-ttu-id="e2c68-156">contenente il punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-156">This contains the entry point of the application.</span></span>
* <span data-ttu-id="e2c68-157">Un file WeatherMicroservice.csproj,</span><span class="sxs-lookup"><span data-stu-id="e2c68-157">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="e2c68-158">ovvero il file di compilazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-158">This is the build file for the application.</span></span>
* <span data-ttu-id="e2c68-159">Un file Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-159">A Dockerfile.</span></span> <span data-ttu-id="e2c68-160">Questo script crea un'immagine Docker per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-160">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="e2c68-161">Un file README.md,</span><span class="sxs-lookup"><span data-stu-id="e2c68-161">A README.md.</span></span> <span data-ttu-id="e2c68-162">contenente collegamenti ad altre risorse ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e2c68-162">This contains links to other asp.net core resources.</span></span>
* <span data-ttu-id="e2c68-163">Un file web.config,</span><span class="sxs-lookup"><span data-stu-id="e2c68-163">A web.config file.</span></span> <span data-ttu-id="e2c68-164">contenente informazioni di configurazione di base.</span><span class="sxs-lookup"><span data-stu-id="e2c68-164">This contains basic configuration information.</span></span>
* <span data-ttu-id="e2c68-165">Un file runtimeconfig.template.json,</span><span class="sxs-lookup"><span data-stu-id="e2c68-165">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="e2c68-166">contenente le impostazioni di debug degli IDE.</span><span class="sxs-lookup"><span data-stu-id="e2c68-166">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="e2c68-167">È ora possibile eseguire l'applicazione generata dal modello.</span><span class="sxs-lookup"><span data-stu-id="e2c68-167">Now you can run the template generated application.</span></span> <span data-ttu-id="e2c68-168">A questo scopo è possibile usare una serie di strumenti da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="e2c68-168">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="e2c68-169">Il comando `dotnet` esegue gli strumenti necessari per lo sviluppo di .NET.</span><span class="sxs-lookup"><span data-stu-id="e2c68-169">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="e2c68-170">Ogni verbo esegue un comando differente</span><span class="sxs-lookup"><span data-stu-id="e2c68-170">Each verb executes a different command</span></span>

<span data-ttu-id="e2c68-171">Il primo passaggio riguarda il ripristino di tutte le dipendenze:</span><span class="sxs-lookup"><span data-stu-id="e2c68-171">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="e2c68-172">Il comando dotnet restore usa lo strumento di gestione pacchetti di NuGet per installare tutti i pacchetti necessari nella directory dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-172">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="e2c68-173">Genera inoltre un file project.json.lock.</span><span class="sxs-lookup"><span data-stu-id="e2c68-173">It also generates a project.json.lock file.</span></span> <span data-ttu-id="e2c68-174">Questo file contiene informazioni su ciascun pacchetto a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e2c68-174">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="e2c68-175">Dopo aver ripristinato tutte le dipendenze, compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e2c68-175">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```

<span data-ttu-id="e2c68-176">Dopo aver compilato l'applicazione, eseguirla dalla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="e2c68-176">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="e2c68-177">La configurazione predefinita è in ascolto su http://localhost:5000.</span><span class="sxs-lookup"><span data-stu-id="e2c68-177">The default configuration listens to http://localhost:5000.</span></span> <span data-ttu-id="e2c68-178">È possibile aprire un browser e passare a tale pagina, dove viene visualizzato un messaggio "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="e2c68-178">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="e2c68-179">.</span><span class="sxs-lookup"><span data-stu-id="e2c68-179">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="e2c68-180">Composizione di un'applicazione ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e2c68-180">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="e2c68-181">Dopo aver compilato l'applicazione, è ora opportuno analizzare il modo in cui questa funzionalità viene implementata.</span><span class="sxs-lookup"><span data-stu-id="e2c68-181">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="e2c68-182">A questo punto risultano particolarmente interessanti due dei file generati: project.json e Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="e2c68-182">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="e2c68-183">Project.json contiene informazioni sul progetto.</span><span class="sxs-lookup"><span data-stu-id="e2c68-183">Project.json contains information about the project.</span></span> <span data-ttu-id="e2c68-184">I due nodi che verranno usati di frequente sono 'dependencies' e 'frameworks'.</span><span class="sxs-lookup"><span data-stu-id="e2c68-184">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="e2c68-185">Nel nodo 'dependencies' sono elencati tutti i pacchetti necessari per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-185">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="e2c68-186">Al momento, poiché sono necessario soltanto i pacchetti che eseguono un server Web, si tratta di un nodo di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e2c68-186">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="e2c68-187">Il nodo 'frameworks' specifica le versioni e le configurazioni del framework .NET che eseguirà l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-187">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="e2c68-188">L'applicazione viene implementata nel file Startup.cs,</span><span class="sxs-lookup"><span data-stu-id="e2c68-188">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="e2c68-189">contenente la classe startup.</span><span class="sxs-lookup"><span data-stu-id="e2c68-189">This file contains the startup class.</span></span>

<span data-ttu-id="e2c68-190">I due metodi vengono chiamati dall'infrastruttura ASP.NET Core per configurare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-190">The two methods are called by the asp.net core infrastructure to configure and run the application.</span></span> <span data-ttu-id="e2c68-191">Il metodo `ConfigureServices` descrive i servizi necessari per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-191">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="e2c68-192">Poiché si sta creando un microservizio semplificato, non è necessario configurare alcuna dipendenza.</span><span class="sxs-lookup"><span data-stu-id="e2c68-192">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="e2c68-193">Il metodo `Configure` consente di configurare i gestori per le richieste HTTP in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e2c68-193">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="e2c68-194">Il modello genera un semplice gestore che risponde a qualsiasi richiesta con il testo "Hello World!".</span><span class="sxs-lookup"><span data-stu-id="e2c68-194">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="e2c68-195">Creare un microservizio</span><span class="sxs-lookup"><span data-stu-id="e2c68-195">Build a microservice</span></span>

<span data-ttu-id="e2c68-196">Il servizio che si intende creare distribuirà report meteo da qualsiasi località.</span><span class="sxs-lookup"><span data-stu-id="e2c68-196">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="e2c68-197">In un ambiente di produzione, per recuperare i dati meteo sarebbe necessario chiamare un qualche servizio.</span><span class="sxs-lookup"><span data-stu-id="e2c68-197">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="e2c68-198">Ai fini di questo esempio, verrà generata una previsione meteo casuale.</span><span class="sxs-lookup"><span data-stu-id="e2c68-198">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="e2c68-199">Per implementare il servizio meteo casuale, è necessario eseguire diverse attività:</span><span class="sxs-lookup"><span data-stu-id="e2c68-199">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="e2c68-200">Analizzare la richiesta in ingresso per leggere la latitudine e la longitudine.</span><span class="sxs-lookup"><span data-stu-id="e2c68-200">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="e2c68-201">Generare alcuni dati di previsione casuali.</span><span class="sxs-lookup"><span data-stu-id="e2c68-201">Generate some random forecast data.</span></span>
* <span data-ttu-id="e2c68-202">Convertire i dati di previsione casuali da oggetti C# in pacchetti JSON.</span><span class="sxs-lookup"><span data-stu-id="e2c68-202">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="e2c68-203">Impostare l'intestazione della risposta per indicare che il servizio reinvia JSON.</span><span class="sxs-lookup"><span data-stu-id="e2c68-203">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="e2c68-204">Scrivere la risposta.</span><span class="sxs-lookup"><span data-stu-id="e2c68-204">Write the response.</span></span>

<span data-ttu-id="e2c68-205">Ciascuno di questi passaggi è descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e2c68-205">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="e2c68-206">Analizzare la stringa di query</span><span class="sxs-lookup"><span data-stu-id="e2c68-206">Parsing the Query String.</span></span>

<span data-ttu-id="e2c68-207">Per iniziare, viene eseguita l'analisi della stringa di query.</span><span class="sxs-lookup"><span data-stu-id="e2c68-207">You'll begin by parsing the query string.</span></span> <span data-ttu-id="e2c68-208">Nella stringa di query il servizio accetterà argomenti 'lat' e 'long' nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="e2c68-208">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="e2c68-209">Tutte le modifiche che è necessario apportare sono presenti nell'espressione lambda definita come argomento per `app.Run` nella classe startup.</span><span class="sxs-lookup"><span data-stu-id="e2c68-209">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="e2c68-210">L'argomento presente nell'espressione lambda è l'`HttpContext` della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e2c68-210">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="e2c68-211">Una delle sue proprietà è l'oggetto `Request`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-211">One of its properties is the `Request` object.</span></span> <span data-ttu-id="e2c68-212">L'oggetto `Request` ha una proprietà `Query` contenente un dizionario di tutti i valori presenti nella stringa di query per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="e2c68-212">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="e2c68-213">La prima operazione consiste nell'individuare i valori relativi alla latitudine e alla longitudine:</span><span class="sxs-lookup"><span data-stu-id="e2c68-213">The first addition is to find the latitude and longitude values:</span></span>

<span data-ttu-id="e2c68-214">[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "leggere le variabili dalla stringa di query")]</span><span class="sxs-lookup"><span data-stu-id="e2c68-214">[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]</span></span>

<span data-ttu-id="e2c68-215">Il valori del dizionario Query sono di tipo `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-215">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="e2c68-216">Questo tipo può contenere una raccolta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="e2c68-216">That type can contain a collection of strings.</span></span> <span data-ttu-id="e2c68-217">Ai fini di questo servizio meteo, ogni valore è una singola stringa.</span><span class="sxs-lookup"><span data-stu-id="e2c68-217">For your weather service, each value is a single string.</span></span> <span data-ttu-id="e2c68-218">Per questo motivo nel codice sopra riportato è presente una chiamata a `FirstOrDefault()`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-218">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="e2c68-219">Come passaggio successivo, è necessario convertire le stringhe in valori double.</span><span class="sxs-lookup"><span data-stu-id="e2c68-219">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="e2c68-220">Per convertire una stringa in un valore double verrà usato il metodo `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="e2c68-220">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="e2c68-221">Questo metodo utilizza parametri C# per indicare se la stringa di input può essere convertita in un valore double.</span><span class="sxs-lookup"><span data-stu-id="e2c68-221">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="e2c68-222">Se la stringa costituisce una rappresentazione valida per un valore double, il metodo restituisce true e l'argomento `result` contiene il valore.</span><span class="sxs-lookup"><span data-stu-id="e2c68-222">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="e2c68-223">Se la stringa non rappresenta un valore double valido, il metodo restituisce false.</span><span class="sxs-lookup"><span data-stu-id="e2c68-223">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="e2c68-224">È possibile adattare tale API mediante l'uso di un *metodo di estensione* che restituisce un *valore double nullable*.</span><span class="sxs-lookup"><span data-stu-id="e2c68-224">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="e2c68-225">Un *tipo valore nullable* rappresenta alcuni tipi valore e può includere anche un valore mancante o null.</span><span class="sxs-lookup"><span data-stu-id="e2c68-225">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="e2c68-226">Per rappresentare un tipo nullable, aggiungere il carattere `?` alla dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="e2c68-226">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="e2c68-227">I metodi di estensione sono definiti come metodi statici. Se tuttavia si aggiunge il modificatore `this` al primo parametro di tali metodi, è possibile chiamarli come se fossero membri della classe.</span><span class="sxs-lookup"><span data-stu-id="e2c68-227">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="e2c68-228">I metodi di estensione possono essere definiti soltanto in classi statiche.</span><span class="sxs-lookup"><span data-stu-id="e2c68-228">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="e2c68-229">Di seguito è riportata la definizione della classe contenente il metodo di estensione per l'analisi:</span><span class="sxs-lookup"><span data-stu-id="e2c68-229">Here's the definition of the class containing the extension method for parse:</span></span>

<span data-ttu-id="e2c68-230">[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "Tentare l'analisi per un valore nullable")]</span><span class="sxs-lookup"><span data-stu-id="e2c68-230">[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]</span></span>

<span data-ttu-id="e2c68-231">L'espressione `default(double?)` restituisce il valore predefinito per il tipo `double?`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-231">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="e2c68-232">Il valore predefinito è il valore null (o mancante).</span><span class="sxs-lookup"><span data-stu-id="e2c68-232">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="e2c68-233">È possibile usare questo metodo di estensione per convertire gli argomenti della stringa di query in un tipo double:</span><span class="sxs-lookup"><span data-stu-id="e2c68-233">You can use this extension method to convert the query string arguments into the double type:</span></span>

<span data-ttu-id="e2c68-234">[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Usare il metodo di estensione TryParse")]</span><span class="sxs-lookup"><span data-stu-id="e2c68-234">[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]</span></span>

<span data-ttu-id="e2c68-235">Per testare facilmente il codice di analisi, aggiornare la risposta in modo che includa i valori degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e2c68-235">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

<span data-ttu-id="e2c68-236">[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Scrivere la risposta di output")]</span><span class="sxs-lookup"><span data-stu-id="e2c68-236">[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]</span></span>

<span data-ttu-id="e2c68-237">A questo punto, è possibile eseguire l'applicazione Web e verificare se il codice di analisi funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="e2c68-237">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="e2c68-238">Aggiungere valori alla richiesta Web in un browser. Verranno visualizzati i risultati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="e2c68-238">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="e2c68-239">Creare una previsione meteo casuale</span><span class="sxs-lookup"><span data-stu-id="e2c68-239">Build a random weather forecast</span></span>

<span data-ttu-id="e2c68-240">L'attività successiva consiste nella creazione di una previsione meteo casuale.</span><span class="sxs-lookup"><span data-stu-id="e2c68-240">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="e2c68-241">Come prima operazione, creare un contenitore dati in cui siano presenti i valori necessari per una previsione meteo:</span><span class="sxs-lookup"><span data-stu-id="e2c68-241">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

<span data-ttu-id="e2c68-242">Come passaggio successivo, aggiungere un costruttore che imposti tali valori in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="e2c68-242">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="e2c68-243">Il costruttore usa i valori relativi a latitudine e longitudine per inizializzare il generatore di numeri Random.</span><span class="sxs-lookup"><span data-stu-id="e2c68-243">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="e2c68-244">Questo significa che la previsione per la stessa località è la stessa.</span><span class="sxs-lookup"><span data-stu-id="e2c68-244">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="e2c68-245">Se si modificano gli argomenti relativi alla latitudine e alla longitudine, si otterrà una previsione diversa, poiché si parte con un valore di inizializzazione differente.</span><span class="sxs-lookup"><span data-stu-id="e2c68-245">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

<span data-ttu-id="e2c68-246">[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Costruttore report meteo")]</span><span class="sxs-lookup"><span data-stu-id="e2c68-246">[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]</span></span>

<span data-ttu-id="e2c68-247">Nel metodo di risposta è ora possibile generare una previsione a 5 giorni:</span><span class="sxs-lookup"><span data-stu-id="e2c68-247">You can now generate the 5-day forecast in your response method:</span></span>

<span data-ttu-id="e2c68-248">[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generare un report meteo casuale")]</span><span class="sxs-lookup"><span data-stu-id="e2c68-248">[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]</span></span>

### <a name="build-the-json-response"></a><span data-ttu-id="e2c68-249">Generare la risposta JSON</span><span class="sxs-lookup"><span data-stu-id="e2c68-249">Build the JSON response.</span></span>

<span data-ttu-id="e2c68-250">L'attività finale del codice sul server consiste nel convertire la matrice WeatherReport in un pacchetto JSON e di rinviarlo al client.</span><span class="sxs-lookup"><span data-stu-id="e2c68-250">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="e2c68-251">Come prima operazione, creare il pacchetto JSON.</span><span class="sxs-lookup"><span data-stu-id="e2c68-251">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="e2c68-252">All'elenco delle dipendenze verrà aggiunto il serializzatore NewtonSoft JSON.</span><span class="sxs-lookup"><span data-stu-id="e2c68-252">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="e2c68-253">È possibile eseguire questa operazione usando l'interfaccia della riga di comando di `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="e2c68-253">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="e2c68-254">È quindi possibile usare la classe `JsonConvert` per scrivere l'oggetto in una stringa:</span><span class="sxs-lookup"><span data-stu-id="e2c68-254">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

<span data-ttu-id="e2c68-255">[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convertire gli oggetti in JSON")]</span><span class="sxs-lookup"><span data-stu-id="e2c68-255">[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]</span></span>

<span data-ttu-id="e2c68-256">Il codice sopra riportato converte l'oggetto forecast (un elenco di oggetti `WeatherForecast`) in un pacchetto JSON.</span><span class="sxs-lookup"><span data-stu-id="e2c68-256">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="e2c68-257">Dopo aver costruito il pacchetto di risposta, impostare il tipo di contenuto su `application/json` e scrivere la stringa.</span><span class="sxs-lookup"><span data-stu-id="e2c68-257">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="e2c68-258">L'applicazione viene eseguita e restituisce previsioni casuali.</span><span class="sxs-lookup"><span data-stu-id="e2c68-258">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="e2c68-259">Creare un'immagine Docker</span><span class="sxs-lookup"><span data-stu-id="e2c68-259">Build a Docker image</span></span>

<span data-ttu-id="e2c68-260">L'attività finale consiste nell'esecuzione dell'applicazione in Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-260">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="e2c68-261">Verrà creato un contenitore Docker per eseguire un'immagine Docker che rappresenta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-261">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="e2c68-262">Un'***immagine Docker*** è un file che definisce l'ambiente per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-262">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="e2c68-263">Un ***contenitore Docker*** rappresenta un'istanza in esecuzione di un'immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-263">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="e2c68-264">Per analogia, è possibile assimilare l'*immagine Docker* a una *classe* e il *contenitore Docker* a un oggetto o a un'istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="e2c68-264">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="e2c68-265">Ai fini di questa esercitazione, verrà usato il file Docker creato dal modello di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e2c68-265">The Dockerfile created by the asp.net template will serve for our purposes.</span></span> <span data-ttu-id="e2c68-266">Di seguito viene descritto il contenuto di tale file.</span><span class="sxs-lookup"><span data-stu-id="e2c68-266">Let's go over its contents.</span></span>

<span data-ttu-id="e2c68-267">La prima riga specifica l'immagine di origine:</span><span class="sxs-lookup"><span data-stu-id="e2c68-267">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="e2c68-268">Docker consente di configurare un'immagine del computer basata su un modello di origine.</span><span class="sxs-lookup"><span data-stu-id="e2c68-268">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="e2c68-269">Questo significa che, per iniziare, non è necessario specificare tutti i parametri del computer, ma soltanto le eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="e2c68-269">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="e2c68-270">Tali modifiche dovranno includere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-270">The changes here will be to include our application.</span></span>

<span data-ttu-id="e2c68-271">Nel primo esempio verrà usata la versione `1.1-sdk-msbuild` dell'immagine dotnet.</span><span class="sxs-lookup"><span data-stu-id="e2c68-271">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="e2c68-272">Questo è il modo più semplice per creare un ambiente Docker funzionante.</span><span class="sxs-lookup"><span data-stu-id="e2c68-272">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="e2c68-273">L'immagine include il runtime principale di dotnet e dotnet SDK.</span><span class="sxs-lookup"><span data-stu-id="e2c68-273">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="e2c68-274">Questo semplifica le operazioni iniziali e la compilazione, ma crea un'immagine di maggiori dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e2c68-274">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="e2c68-275">Le cinque righe successive consentono di installare e compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e2c68-275">The next five lines setup and build your application:</span></span>

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroservice.csproj .
RUN dotnet restore

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="e2c68-276">Il codice sopra riportato copia il file di progetto dalla directory corrente alla macchina virtuale Docker e ripristina tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e2c68-276">This will copy the project file from the  current directory to the docker VM, and restore all the packages.</span></span> <span data-ttu-id="e2c68-277">Se si usa l'interfaccia della riga di comando, l'immagine Docker deve includere .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e2c68-277">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="e2c68-278">In seguito la rimanente parte dell'applicazione viene copiata e il comando publish di dotnet compila l'applicazione e ne crea un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e2c68-278">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="e2c68-279">L'ultima riga del file esegue l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e2c68-279">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="e2c68-280">Viene fatto riferimento a questa porta configurata nell'ultima riga del file Docker, nell'argomento `--server.urls` di `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-280">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="e2c68-281">Il comando `ENTRYPOINT` comunica a Docker quale comando e quali opzioni della riga di comando avviano il servizio.</span><span class="sxs-lookup"><span data-stu-id="e2c68-281">The `ENTRYPOINT` command informs Docker  what command and command line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="e2c68-282">Compilare ed eseguire l'immagine in un contenitore</span><span class="sxs-lookup"><span data-stu-id="e2c68-282">Building and running the image in a container.</span></span>

<span data-ttu-id="e2c68-283">In questa sezione si eseguirà la compilazione di un'immagine e l'esecuzione di un servizio all'interno di un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-283">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="e2c68-284">Non si vuole che tutti i file della directory locale vengano copiati nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e2c68-284">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="e2c68-285">L'applicazione verrà invece compilata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="e2c68-285">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="e2c68-286">Verrà creato un file `.dockerignore` per specificare le directory non copiate nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e2c68-286">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="e2c68-287">Si vuole che non venga copiata alcuna risorsa di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-287">You don't want any of the build assets copied.</span></span> <span data-ttu-id="e2c68-288">Specificare le directory di compilazione e pubblicazione nel file `.dockerignore`:</span><span class="sxs-lookup"><span data-stu-id="e2c68-288">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="e2c68-289">L'immagine viene compilata usando il comando build di Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-289">You build the image using the docker build command.</span></span> <span data-ttu-id="e2c68-290">Eseguire il comando seguente dalla directory contenente il codice.</span><span class="sxs-lookup"><span data-stu-id="e2c68-290">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="e2c68-291">Questo comando compila l'immagine del contenitore sulla base di tutte le informazioni presenti nel file Docker.</span><span class="sxs-lookup"><span data-stu-id="e2c68-291">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="e2c68-292">L'argomento `-t` specifica un tag, o un nome, per questa immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="e2c68-292">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="e2c68-293">Nella riga di comando precedente il tag usato per il contenitore Docker è `weather-microservice`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-293">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="e2c68-294">Dopo l'esecuzione di questo comando, è disponibile un contenitore pronto per l'esecuzione del nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="e2c68-294">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="e2c68-295">Eseguire il comando seguente per avviare il contenitore e il servizio:</span><span class="sxs-lookup"><span data-stu-id="e2c68-295">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="e2c68-296">L'opzione `-d` consente di eseguire il contenitore scollegato dal terminale corrente.</span><span class="sxs-lookup"><span data-stu-id="e2c68-296">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="e2c68-297">Questo significa che nel terminale non verrà visualizzato l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="e2c68-297">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="e2c68-298">L'opzione `-p` indica il mapping delle porte tra il servizio e l'host.</span><span class="sxs-lookup"><span data-stu-id="e2c68-298">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="e2c68-299">In base al codice sopra riportato, qualsiasi richiesta in ingresso sulla porta 80 verrà inoltrata alla porta 5000 del contenitore.</span><span class="sxs-lookup"><span data-stu-id="e2c68-299">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="e2c68-300">La porta 5000 è la porta su cui è in ascolto il servizio secondo gli argomenti della riga di comando specificati nel file Docker sopra riportato.</span><span class="sxs-lookup"><span data-stu-id="e2c68-300">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="e2c68-301">L'argomento `--name` indica il nome del contenitore in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-301">The `--name` argument names your running container.</span></span> <span data-ttu-id="e2c68-302">È un nome appropriato, che è possibile specificare per usare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="e2c68-302">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="e2c68-303">Per vedere se l'immagine è in esecuzione, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e2c68-303">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="e2c68-304">Se il contenitore è in esecuzione, viene visualizzata una riga in cui sono elencati i processi in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-304">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="e2c68-305">Questa riga potrebbe essere l'unica.</span><span class="sxs-lookup"><span data-stu-id="e2c68-305">(It may be the only one).</span></span>

<span data-ttu-id="e2c68-306">Per testare il servizio, è possibile aprire un browser, passare a localhost e specificare valori per la latitudine e la longitudine:</span><span class="sxs-lookup"><span data-stu-id="e2c68-306">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="e2c68-307">Collegarsi a un contenitore in esecuzione</span><span class="sxs-lookup"><span data-stu-id="e2c68-307">Attaching to a running container</span></span>

<span data-ttu-id="e2c68-308">Quando si esegue il servizio in una finestra di comando, è possibile osservare le informazioni di diagnostica stampate per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="e2c68-308">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="e2c68-309">Quando il contenitore è in esecuzione senza collegamento, tali informazioni non vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="e2c68-309">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="e2c68-310">Il comando attach di Docker consente di collegarsi a un contenitore in esecuzione in modo da visualizzare le informazioni di log.</span><span class="sxs-lookup"><span data-stu-id="e2c68-310">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="e2c68-311">Eseguire questo comando da una finestra di comando:</span><span class="sxs-lookup"><span data-stu-id="e2c68-311">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="e2c68-312">L'argomento `--sig-proxy=false` indica che i comandi `Ctrl-C` non vengono inviati al processo del contenitore, ma che arrestano il comando `docker attach`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-312">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="e2c68-313">L'argomento finale è il nome assegnato al contenitore nel comando `docker run`.</span><span class="sxs-lookup"><span data-stu-id="e2c68-313">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="e2c68-314">È anche possibile usare l'ID del contenitore assegnato da Docker per fare riferimento a qualsiasi altro contenitore.</span><span class="sxs-lookup"><span data-stu-id="e2c68-314">You can also use the docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="e2c68-315">Se in `docker run` non è stato specificato un nome per il contenitore, è necessario usare l'ID del contenitore.</span><span class="sxs-lookup"><span data-stu-id="e2c68-315">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="e2c68-316">Aprire un browser e passare al servizio.</span><span class="sxs-lookup"><span data-stu-id="e2c68-316">Open a browser and navigate to your service.</span></span> <span data-ttu-id="e2c68-317">Nelle finestre di comando verranno visualizzati messaggi di diagnostica provenienti dal contenitore collegato in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-317">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="e2c68-318">Premere `Ctrl-C` per arrestare il processo di collegamento.</span><span class="sxs-lookup"><span data-stu-id="e2c68-318">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="e2c68-319">Quando si è finito di usare il contenitore, è possibile arrestarlo:</span><span class="sxs-lookup"><span data-stu-id="e2c68-319">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="e2c68-320">Il contenitore e l'immagine sono ancora disponibili per il riavvio.</span><span class="sxs-lookup"><span data-stu-id="e2c68-320">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="e2c68-321">Per rimuovere il contenitore dal computer, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e2c68-321">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="e2c68-322">Per rimuovere dal computer le immagini non utilizzate, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e2c68-322">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="e2c68-323">Conclusione</span><span class="sxs-lookup"><span data-stu-id="e2c68-323">Conclusion</span></span> 

<span data-ttu-id="e2c68-324">In questa esercitazione è stato creato un microservizio ASP.NET Core e sono state aggiunte alcune semplici funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e2c68-324">In this tutorial, you built an asp.net core microservice, and added a few simple features.</span></span>

<span data-ttu-id="e2c68-325">È stata compilata un'immagine Docker del contenitore e quest'ultimo è stato eseguito sul computer.</span><span class="sxs-lookup"><span data-stu-id="e2c68-325">You built a docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="e2c68-326">È stata collegata una finestra del terminale al servizio e sono stati visualizzati i messaggi di diagnostica provenienti dal servizio stesso.</span><span class="sxs-lookup"><span data-stu-id="e2c68-326">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="e2c68-327">Nel corso dell'esercitazione è stato possibile osservare diverse funzionalità del linguaggio C# in azione.</span><span class="sxs-lookup"><span data-stu-id="e2c68-327">Along the way, you saw several features of the C# language in action.</span></span>

