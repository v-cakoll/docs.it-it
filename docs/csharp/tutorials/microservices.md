---
title: Microservizi ospitati in Docker - C#
description: Informazioni su come creare servizi ASP.NET Core in esecuzione in contenitori Docker
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: b1f7159a222ab4d68715844e9997ca922676bc80
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454486"
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="e1ddd-103">Microservizi ospitati in Docker</span><span class="sxs-lookup"><span data-stu-id="e1ddd-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="e1ddd-104">Questa esercitazione descrive nel dettaglio la procedura per creare e distribuire un microservizio ASP.NET Core in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="e1ddd-105">Nel corso di questa esercitazione verranno illustrate le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="e1ddd-106">Generazione di un'applicazione ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-106">How to generate an ASP.NET Core application.</span></span>
* <span data-ttu-id="e1ddd-107">Creazione di un ambiente di sviluppo Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-107">How to create a development Docker environment.</span></span>
* <span data-ttu-id="e1ddd-108">Creazione di un'immagine Docker basata su un'immagine esistente</span><span class="sxs-lookup"><span data-stu-id="e1ddd-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="e1ddd-109">Distribuzione del servizio in un ambiente Docker</span><span class="sxs-lookup"><span data-stu-id="e1ddd-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="e1ddd-110">Verranno inoltre illustrate alcune funzionalità del linguaggio C#:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="e1ddd-111">Conversione di oggetti C# in payload JSON</span><span class="sxs-lookup"><span data-stu-id="e1ddd-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="e1ddd-112">Creazione di oggetti di trasferimento dati non modificabili.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-112">How to build immutable Data Transfer Objects.</span></span>
* <span data-ttu-id="e1ddd-113">Elaborazione delle richieste HTTP in ingresso e generazione della risposta HTTP.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-113">How to process incoming HTTP Requests and generate the HTTP Response.</span></span>
* <span data-ttu-id="e1ddd-114">Uso dei tipi valore nullable.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-114">How to work with nullable value types.</span></span>

<span data-ttu-id="e1ddd-115">È possibile [visualizzare o scaricare l'app di esempio](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="e1ddd-116">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="e1ddd-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="why-docker"></a><span data-ttu-id="e1ddd-117">Vantaggi offerti dall'uso di Docker</span><span class="sxs-lookup"><span data-stu-id="e1ddd-117">Why Docker?</span></span>

<span data-ttu-id="e1ddd-118">Docker semplifica la creazione di immagini delle macchine standard per ospitare i servizi in un data center o nel cloud pubblico.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="e1ddd-119">Docker consente di configurare l'immagine e di eseguirne la replica in base alle necessità per scalare l'installazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="e1ddd-120">Tutto il codice riportato in questa esercitazione può essere eseguito in qualsiasi ambiente .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="e1ddd-121">Le attività aggiuntive per un'installazione Docker funzioneranno per un'applicazione ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e1ddd-122">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e1ddd-122">Prerequisites</span></span>

<span data-ttu-id="e1ddd-123">È necessario configurare il computer per l'esecuzione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-123">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="e1ddd-124">Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="e1ddd-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="e1ddd-125">Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-125">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="e1ddd-126">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="e1ddd-127">Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma,</span><span class="sxs-lookup"><span data-stu-id="e1ddd-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="e1ddd-128">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="e1ddd-129">È inoltre necessario installare il motore di Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="e1ddd-130">Per le istruzioni di installazione relative alla piattaforma in uso, vedere la pagina [Docker Installation](https://docs.docker.com/install/overview/) (Installazione di Docker).</span><span class="sxs-lookup"><span data-stu-id="e1ddd-130">See the [Docker Installation page](https://docs.docker.com/install/overview/) for instructions for your platform.</span></span>
<span data-ttu-id="e1ddd-131">È possibile installare Docker in diverse distribuzioni di Linux, macOS o Windows.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="e1ddd-132">La pagina citata sopra contiene sezioni per ciascuna delle installazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-132">The page referenced above contains sections to each of the available installations.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="e1ddd-133">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="e1ddd-133">Create the Application</span></span>

<span data-ttu-id="e1ddd-134">Una volta installati tutti gli strumenti, creare una nuova applicazione ASP.NET Core in una directory denominata "WeatherMicroservice" eseguendo il comando seguente nella shell preferita:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-134">Now that you've installed all the tools, create a new ASP.NET Core application in a directory called "WeatherMicroservice" by executing the following command in your favorite shell:</span></span>

```console
dotnet new web -o WeatherMicroservice
```

<span data-ttu-id="e1ddd-135">Il comando `dotnet` esegue gli strumenti necessari per lo sviluppo di .NET.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-135">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="e1ddd-136">Ogni verbo esegue un comando diverso.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-136">Each verb executes a different command.</span></span>

<span data-ttu-id="e1ddd-137">Il comando `dotnet new` viene usato per creare progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-137">The `dotnet new` command is used to create .Net Core projects.</span></span>

<span data-ttu-id="e1ddd-138">L'opzione `-o WeatherMicroservice` dopo il comando `dotnet new` viene usata per specificare la posizione in cui creare l'applicazione ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-138">The `-o WeatherMicroservice` option after the `dotnet new` command is used to give the location to create the ASP.NET Core application.</span></span>

<span data-ttu-id="e1ddd-139">Per questo microservizio si vuole creare l'applicazione Web più semplice e leggera possibile. Si userà quindi il modello "Progetto ASP.NET Core vuoto" specificandone il nome breve, `web`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-139">For this microservice, we want the simplest, most lightweight web application possible, so we used the "ASP.NET Core Empty" template, by specifying its short name, `web`.</span></span>

<span data-ttu-id="e1ddd-140">Il modello crea automaticamente quattro file:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-140">The template creates four files for you:</span></span>

* <span data-ttu-id="e1ddd-141">Un file Startup.cs,</span><span class="sxs-lookup"><span data-stu-id="e1ddd-141">A Startup.cs file.</span></span> <span data-ttu-id="e1ddd-142">contenente la base dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-142">This contains the basis of the application.</span></span>
* <span data-ttu-id="e1ddd-143">Un file Program.cs,</span><span class="sxs-lookup"><span data-stu-id="e1ddd-143">A Program.cs file.</span></span> <span data-ttu-id="e1ddd-144">contenente il punto di ingresso dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-144">This contains the entry point of the application.</span></span>
* <span data-ttu-id="e1ddd-145">Un file WeatherMicroservice.csproj,</span><span class="sxs-lookup"><span data-stu-id="e1ddd-145">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="e1ddd-146">ovvero il file di compilazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-146">This is the build file for the application.</span></span>
* <span data-ttu-id="e1ddd-147">Un file Properties/launchSettings.json.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-147">A Properties/launchSettings.json file.</span></span> <span data-ttu-id="e1ddd-148">contenente le impostazioni di debug degli IDE.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-148">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="e1ddd-149">È ora possibile eseguire l'applicazione generata dal modello:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-149">Now you can run the template generated application:</span></span>

```console
dotnet run
```

<span data-ttu-id="e1ddd-150">Questo comando prima ripristina le dipendenze necessarie per compilare l'applicazione e quindi compila l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-150">This command will first restore dependencies required to build the application and then it will build the application.</span></span>

<span data-ttu-id="e1ddd-151">La configurazione predefinita è in ascolto su `http://localhost:5000`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-151">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="e1ddd-152">È possibile aprire un browser e passare a tale pagina, dove viene visualizzato un messaggio "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="e1ddd-152">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="e1ddd-153">trovata.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-153">message.</span></span>

<span data-ttu-id="e1ddd-154">Al termine, è possibile arrestare l'applicazione premendo <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-154">When you're done, you can shut down the application by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="e1ddd-155">Composizione di un'applicazione ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e1ddd-155">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="e1ddd-156">Dopo aver compilato l'applicazione, è ora opportuno analizzare il modo in cui questa funzionalità viene implementata.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-156">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="e1ddd-157">A questo punto risultano particolarmente interessanti due dei file generati: WeatherMicroservice.json e Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-157">There are two of the generated files that are particularly interesting at this point: WeatherMicroservice.csproj and Startup.cs.</span></span> 

<span data-ttu-id="e1ddd-158">Il file con estensione csproj contiene informazioni sul progetto.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-158">The .csproj file contains information about the project.</span></span>
<span data-ttu-id="e1ddd-159">I due nodi più interessanti sono `<TargetFramework>` e `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-159">The two nodes that are most interesting are `<TargetFramework>` and `<PackageReference>`.</span></span>

<span data-ttu-id="e1ddd-160">Il nodo `<TargetFramework>` specifica la versione di .NET con cui questa applicazione verrà eseguita.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-160">The `<TargetFramework>` node specifies the version of .NET that will run this application.</span></span>

<span data-ttu-id="e1ddd-161">Ogni nodo `<PackageReference>` viene usato per specificare un pacchetto necessario per questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-161">Each `<PackageReference>` node is used to specify a package that is needed for this application.</span></span>

<span data-ttu-id="e1ddd-162">L'applicazione viene implementata nel file Startup.cs,</span><span class="sxs-lookup"><span data-stu-id="e1ddd-162">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="e1ddd-163">contenente la classe startup.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-163">This file contains the startup class.</span></span>

<span data-ttu-id="e1ddd-164">I due metodi vengono chiamati dall'infrastruttura ASP.NET Core per configurare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-164">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="e1ddd-165">Il metodo `ConfigureServices` descrive i servizi necessari per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-165">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="e1ddd-166">Poiché si sta creando un microservizio semplificato, non è necessario configurare alcuna dipendenza.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-166">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="e1ddd-167">Il metodo `Configure` consente di configurare i gestori per le richieste HTTP in ingresso.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-167">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="e1ddd-168">Il modello genera un semplice gestore che risponde a qualsiasi richiesta con il testo "Hello World!".</span><span class="sxs-lookup"><span data-stu-id="e1ddd-168">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="e1ddd-169">Creare un microservizio</span><span class="sxs-lookup"><span data-stu-id="e1ddd-169">Build a microservice</span></span>

<span data-ttu-id="e1ddd-170">Il servizio che si intende creare distribuirà report meteo da qualsiasi località.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-170">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="e1ddd-171">In un ambiente di produzione, per recuperare i dati meteo sarebbe necessario chiamare un qualche servizio.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-171">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="e1ddd-172">Ai fini di questo esempio, verrà generata una previsione meteo casuale.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-172">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="e1ddd-173">Per implementare il servizio meteo casuale, è necessario eseguire diverse attività:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-173">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="e1ddd-174">Analizzare la richiesta in ingresso per leggere la latitudine e la longitudine.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-174">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="e1ddd-175">Generare alcuni dati di previsione casuali.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-175">Generate some random forecast data.</span></span>
* <span data-ttu-id="e1ddd-176">Convertire i dati di previsione casuali da oggetti C# in pacchetti JSON.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-176">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="e1ddd-177">Impostare l'intestazione della risposta per indicare che il servizio reinvia JSON.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-177">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="e1ddd-178">Scrivere la risposta.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-178">Write the response.</span></span>

<span data-ttu-id="e1ddd-179">Ciascuno di questi passaggi è descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-179">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="e1ddd-180">Analisi della stringa di query</span><span class="sxs-lookup"><span data-stu-id="e1ddd-180">Parsing the Query String</span></span>

<span data-ttu-id="e1ddd-181">Per iniziare, viene eseguita l'analisi della stringa di query.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-181">You'll begin by parsing the query string.</span></span> <span data-ttu-id="e1ddd-182">Nella stringa di query il servizio accetterà argomenti 'lat' e 'long' nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-182">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

<span data-ttu-id="e1ddd-183">Tutte le modifiche che è necessario apportare sono presenti nell'espressione lambda definita come argomento per `app.Run` nella classe startup.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-183">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="e1ddd-184">L'argomento presente nell'espressione lambda è l'`HttpContext` della richiesta.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-184">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="e1ddd-185">Una delle sue proprietà è l'oggetto `Request`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-185">One of its properties is the `Request` object.</span></span> <span data-ttu-id="e1ddd-186">L'oggetto `Request` ha una proprietà `Query` contenente un dizionario di tutti i valori presenti nella stringa di query per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-186">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="e1ddd-187">La prima operazione consiste nell'individuare i valori relativi alla latitudine e alla longitudine:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-187">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="e1ddd-188">I valori del dizionario `Query` sono di tipo `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-188">The `Query` dictionary values are `StringValue` type.</span></span> <span data-ttu-id="e1ddd-189">Questo tipo può contenere una raccolta di stringhe.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-189">That type can contain a collection of strings.</span></span> <span data-ttu-id="e1ddd-190">Ai fini di questo servizio meteo, ogni valore è una singola stringa.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-190">For your weather service, each value is a single string.</span></span> <span data-ttu-id="e1ddd-191">Per questo motivo nel codice sopra riportato è presente una chiamata a `FirstOrDefault()`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-191">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="e1ddd-192">Come passaggio successivo, è necessario convertire le stringhe in valori double.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-192">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="e1ddd-193">Per convertire una stringa in un valore double verrà usato il metodo `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-193">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="e1ddd-194">Questo metodo utilizza parametri C# per indicare se la stringa di input può essere convertita in un valore double.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-194">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="e1ddd-195">Se la stringa costituisce una rappresentazione valida per un valore double, il metodo restituisce true e l'argomento `result` contiene il valore.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-195">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="e1ddd-196">Se la stringa non rappresenta un valore double valido, il metodo restituisce false.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-196">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="e1ddd-197">È possibile adattare tale API mediante l'uso di un *metodo di estensione* che restituisce un *valore double nullable*.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-197">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="e1ddd-198">Un *tipo valore nullable* rappresenta alcuni tipi valore e può includere anche un valore mancante o null.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-198">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="e1ddd-199">Per rappresentare un tipo nullable, aggiungere il carattere `?` alla dichiarazione del tipo.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-199">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="e1ddd-200">I metodi di estensione sono definiti come metodi statici. Se tuttavia si aggiunge il modificatore `this` al primo parametro di tali metodi, è possibile chiamarli come se fossero membri della classe.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-200">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="e1ddd-201">I metodi di estensione possono essere definiti soltanto in classi statiche.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-201">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="e1ddd-202">Di seguito è riportata la definizione della classe contenente il metodo di estensione per l'analisi:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-202">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="e1ddd-203">Prima di chiamare il metodo di estensione, modificare le impostazioni cultura correnti sulle impostazioni cultura inglese non dipendenti da paese/area geografica:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-203">Before calling the extension method, change the current culture to invariant:</span></span>

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

<span data-ttu-id="e1ddd-204">Ciò garantisce che l'applicazione analizzi i numeri allo stesso modo in qualsiasi server, indipendentemente dalle impostazioni cultura predefinite.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-204">This ensures that your application parses numbers the same on any server, regardless of its default culture.</span></span>

<span data-ttu-id="e1ddd-205">È ora possibile usare il metodo di estensione per convertire gli argomenti della stringa di query nel tipo double:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-205">Now you can use the extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="e1ddd-206">Per testare facilmente il codice di analisi, aggiornare la risposta in modo che includa i valori degli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-206">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="e1ddd-207">A questo punto, è possibile eseguire l'applicazione Web e verificare se il codice di analisi funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-207">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="e1ddd-208">Aggiungere valori alla richiesta Web in un browser. Verranno visualizzati i risultati aggiornati.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-208">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="e1ddd-209">Creare una previsione meteo casuale</span><span class="sxs-lookup"><span data-stu-id="e1ddd-209">Build a random weather forecast</span></span>

<span data-ttu-id="e1ddd-210">L'attività successiva consiste nella creazione di una previsione meteo casuale.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-210">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="e1ddd-211">Come prima operazione, creare un contenitore dati in cui siano presenti i valori necessari per una previsione meteo:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-211">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

<span data-ttu-id="e1ddd-212">Come passaggio successivo, aggiungere un costruttore che imposti tali valori in modo casuale.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-212">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="e1ddd-213">Il costruttore usa i valori relativi a latitudine e longitudine per inizializzare il generatore di numeri `Random`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-213">This constructor uses the values for the latitude and longitude to seed the `Random` number generator.</span></span> <span data-ttu-id="e1ddd-214">Questo significa che la previsione per la stessa località è la stessa.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-214">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="e1ddd-215">Se si modificano gli argomenti relativi alla latitudine e alla longitudine, si otterrà una previsione diversa, poiché si parte da un altro valore di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-215">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed).</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="e1ddd-216">Nel metodo di risposta è ora possibile generare una previsione a 5 giorni:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-216">You can now generate the 5-day forecast in your response method:</span></span>

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a><span data-ttu-id="e1ddd-217">Generare la risposta JSON</span><span class="sxs-lookup"><span data-stu-id="e1ddd-217">Build the JSON response</span></span>

<span data-ttu-id="e1ddd-218">L'attività finale del codice sul server consiste nel convertire l'elenco `WeatherReport` in un documento JSON e nel rinviarlo al client.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-218">The final code task on the server is to convert the `WeatherReport` list into JSON document, and send that back to the client.</span></span> <span data-ttu-id="e1ddd-219">Come prima operazione, creare il documento JSON.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-219">Let's start by creating the JSON document.</span></span> <span data-ttu-id="e1ddd-220">All'elenco delle dipendenze verrà aggiunto il serializzatore JSON Newtonsoft.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-220">You'll add the Newtonsoft JSON serializer to the list of dependencies.</span></span> <span data-ttu-id="e1ddd-221">A tale scopo, è possibile usare il comando `dotnet` seguente:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-221">You can do that using the following `dotnet` command:</span></span>

```console
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="e1ddd-222">È quindi possibile usare la classe `JsonConvert` per scrivere l'oggetto in una stringa:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-222">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="e1ddd-223">Il codice sopra riportato converte l'oggetto forecast (un elenco di oggetti `WeatherForecast`) in un documento JSON.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-223">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON document.</span></span> <span data-ttu-id="e1ddd-224">Dopo aver costruito il documento di risposta, impostare il tipo di contenuto su `application/json` e scrivere la stringa.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-224">After you've constructed the response document, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="e1ddd-225">L'applicazione viene eseguita e restituisce previsioni casuali.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-225">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="e1ddd-226">Creare un'immagine Docker</span><span class="sxs-lookup"><span data-stu-id="e1ddd-226">Build a Docker image</span></span>

<span data-ttu-id="e1ddd-227">L'attività finale consiste nell'esecuzione dell'applicazione in Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-227">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="e1ddd-228">Verrà creato un contenitore Docker per eseguire un'immagine Docker che rappresenta l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-228">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="e1ddd-229">Un'***immagine Docker*** è un file che definisce l'ambiente per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-229">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="e1ddd-230">Un ***contenitore Docker*** rappresenta un'istanza in esecuzione di un'immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-230">A ***Docker Container*** represents a running instance of a Docker Image.</span></span>

<span data-ttu-id="e1ddd-231">Per analogia, è possibile assimilare l'*immagine Docker* a una *classe* e il *contenitore Docker* a un oggetto o a un'istanza di tale classe.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-231">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="e1ddd-232">A questo scopo, verrà usato il Dockerfile seguente:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-232">The following Dockerfile will serve for our purposes:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="e1ddd-233">Di seguito viene descritto il contenuto di tale file.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-233">Let's go over its contents.</span></span>

<span data-ttu-id="e1ddd-234">La prima riga specifica l'immagine di origine usata per compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-234">The first line specifies the source image used for building the application:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
```

<span data-ttu-id="e1ddd-235">Docker consente di configurare un'immagine del computer basata su un modello di origine.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-235">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="e1ddd-236">Questo significa che, per iniziare, non è necessario specificare tutti i parametri del computer, ma soltanto le eventuali modifiche.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-236">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="e1ddd-237">Tali modifiche dovranno includere l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-237">The changes here will be to include our application.</span></span>

<span data-ttu-id="e1ddd-238">In questo esempio verrà usata la versione `2.1-sdk` dell'immagine `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-238">In this sample, we'll use the `2.1-sdk` version of the `dotnet` image.</span></span> <span data-ttu-id="e1ddd-239">Questo è il modo più semplice per creare un ambiente Docker funzionante.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-239">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="e1ddd-240">Questa immagine include il runtime di .NET Core e .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-240">This image includes the .NET Core runtime, and the .NET Core SDK.</span></span>
<span data-ttu-id="e1ddd-241">Ciò rende più semplice iniziare e compilare, ma crea un'immagine più grande. Questa immagine verrà pertanto usata per la compilazione dell'applicazione, mentre per l'esecuzione verrà usata un'immagine diversa.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-241">That makes it easier to get started and build, but does create a larger image, so we'll use this image for building the application and a different image to run it.</span></span>

<span data-ttu-id="e1ddd-242">Le prossime righe consentono di installare e compilare l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-242">The next lines setup and build your application:</span></span>

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="e1ddd-243">Il codice sopra riportato copia il file di progetto dalla directory corrente alla macchina virtuale Docker e ripristina tutti i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-243">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="e1ddd-244">Se si usa l'interfaccia della riga di comando, l'immagine Docker deve includere .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-244">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="e1ddd-245">Dopo ciò, viene copiata la parte rimanente dell'applicazione e il comando `dotnet
publish` compila l'applicazione e ne crea il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-245">After that, the rest of your application gets copied, and the `dotnet
publish` command builds and packages your application.</span></span>

<span data-ttu-id="e1ddd-246">Viene infine creata una seconda immagine Docker che esegue l'applicazione:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-246">Finally, we create a second Docker image that runs the application:</span></span>

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="e1ddd-247">Questa immagine usa la versione `2.1-aspnetcore-runtime` dell'immagine `dotnet`, che contiene tutto quando necessario per eseguire applicazioni ASP.NET Core, ma non include .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-247">This image uses the `2.1-aspnetcore-runtime` version of the `dotnet` image, which contains everything necessary to run ASP.NET Core applications, but does not include the .NET Core SDK.</span></span> <span data-ttu-id="e1ddd-248">Ciò significa che questa immagine non può essere usata per compilare applicazioni .NET Core, ma anche che l'immagine finale risultante è più piccola.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-248">This means this image can't be used to build .NET Core applications, but it also makes the final image smaller.</span></span>

<span data-ttu-id="e1ddd-249">Per ottenere questo risultato, copiare l'applicazione compilata dalla prima immagine alla seconda.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-249">To make this work, we copy the built application from the first image to the second one.</span></span>

<span data-ttu-id="e1ddd-250">Il comando `ENTRYPOINT` informa Docker del comando che avvia il servizio.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-250">The `ENTRYPOINT` command informs Docker what command starts the service.</span></span>

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="e1ddd-251">Compilazione ed esecuzione dell'immagine in un contenitore</span><span class="sxs-lookup"><span data-stu-id="e1ddd-251">Building and running the image in a container</span></span>

<span data-ttu-id="e1ddd-252">In questa sezione si eseguirà la compilazione di un'immagine e l'esecuzione di un servizio all'interno di un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-252">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="e1ddd-253">Non si vuole che tutti i file della directory locale vengano copiati nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-253">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="e1ddd-254">L'applicazione verrà invece compilata nel contenitore.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-254">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="e1ddd-255">Verrà creato un file `.dockerignore` per specificare le directory non copiate nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-255">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="e1ddd-256">Si vuole che non venga copiata alcuna risorsa di compilazione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-256">You don't want any of the build assets copied.</span></span> <span data-ttu-id="e1ddd-257">Specificare le directory di compilazione e pubblicazione nel file `.dockerignore`:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-257">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="e1ddd-258">L'immagine viene compilata usando il comando `docker build`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-258">You build the image using the `docker build` command.</span></span> <span data-ttu-id="e1ddd-259">Eseguire il comando seguente dalla directory contenente il codice.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-259">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="e1ddd-260">Questo comando compila l'immagine del contenitore sulla base di tutte le informazioni presenti nel file Docker.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-260">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="e1ddd-261">L'argomento `-t` specifica un tag, o un nome, per questa immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-261">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="e1ddd-262">Nella riga di comando precedente il tag usato per il contenitore Docker è `weather-microservice`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-262">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="e1ddd-263">Dopo l'esecuzione di questo comando, è disponibile un contenitore pronto per l'esecuzione del nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-263">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="e1ddd-264">Eseguire il comando seguente per avviare il contenitore e il servizio:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-264">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

<span data-ttu-id="e1ddd-265">L'opzione `-d` consente di eseguire il contenitore scollegato dal terminale corrente.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-265">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="e1ddd-266">Questo significa che nel terminale non verrà visualizzato l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-266">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="e1ddd-267">L'opzione `-p` indica il mapping delle porte tra il servizio e l'host.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-267">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="e1ddd-268">In base al codice sopra riportato, qualsiasi richiesta in ingresso sulla porta 80 verrà inoltrata alla porta 80 del contenitore.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-268">Here it says that any incoming request on port 80 should be forwarded to port 80 on the container.</span></span> <span data-ttu-id="e1ddd-269">La porta 80 corrisponde alla porta su cui il servizio è in ascolto, ovvero alla porta predefinita per le applicazioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-269">Using 80 matches the port your service is listening on, which is the default port for production applications.</span></span> <span data-ttu-id="e1ddd-270">L'argomento `--name` indica il nome del contenitore in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-270">The `--name` argument names your running container.</span></span> <span data-ttu-id="e1ddd-271">È un nome appropriato, che è possibile specificare per usare il contenitore.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-271">It's a convenient name you can use to work with that container.</span></span>

<span data-ttu-id="e1ddd-272">Per vedere se l'immagine è in esecuzione, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-272">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="e1ddd-273">Se il contenitore è in esecuzione, viene visualizzata una riga in cui sono elencati i processi in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-273">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="e1ddd-274">Questa riga potrebbe essere l'unica.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-274">(It may be the only one.)</span></span>

<span data-ttu-id="e1ddd-275">Per testare il servizio, è possibile aprire un browser, passare a localhost e specificare valori per la latitudine e la longitudine:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-275">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="e1ddd-276">Collegarsi a un contenitore in esecuzione</span><span class="sxs-lookup"><span data-stu-id="e1ddd-276">Attaching to a running container</span></span>

<span data-ttu-id="e1ddd-277">Quando si esegue il servizio in una finestra di comando, è possibile osservare le informazioni di diagnostica stampate per ogni richiesta.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-277">When you ran your service in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="e1ddd-278">Quando il contenitore è in esecuzione senza collegamento, tali informazioni non vengono visualizzate.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-278">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="e1ddd-279">Il comando attach di Docker consente di collegarsi a un contenitore in esecuzione in modo da visualizzare le informazioni di log.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-279">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="e1ddd-280">Eseguire questo comando da una finestra di comando:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-280">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="e1ddd-281">L'argomento `--sig-proxy=false` indica che i comandi <kbd>Ctrl</kbd>+<kbd>C</kbd> non vengono inviati al processo del contenitore, ma interrompono il comando `docker attach`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-281">The `--sig-proxy=false` argument means that <kbd>Ctrl</kbd>+<kbd>C</kbd> commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="e1ddd-282">L'argomento finale è il nome assegnato al contenitore nel comando `docker run`.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-282">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="e1ddd-283">È anche possibile usare l'ID del contenitore assegnato da Docker per fare riferimento a qualsiasi altro contenitore.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-283">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="e1ddd-284">Se in `docker run` non è stato specificato un nome per il contenitore, è necessario usare l'ID del contenitore.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-284">If you didn't specify a name for your container in `docker run` you must use the container ID.</span></span>

<span data-ttu-id="e1ddd-285">Aprire un browser e passare al servizio.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-285">Open a browser and navigate to your service.</span></span> <span data-ttu-id="e1ddd-286">Nelle finestre di comando verranno visualizzati messaggi di diagnostica provenienti dal contenitore collegato in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-286">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="e1ddd-287">Premere <kbd>Ctrl</kbd>+<kbd>C</kbd> per arrestare il processo del comando attach.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-287">Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop the attach process.</span></span>

<span data-ttu-id="e1ddd-288">Quando si è finito di usare il contenitore, è possibile arrestarlo:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-288">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="e1ddd-289">Il contenitore e l'immagine sono ancora disponibili per il riavvio.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-289">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="e1ddd-290">Per rimuovere il contenitore dal computer, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-290">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="e1ddd-291">Per rimuovere dal computer le immagini non utilizzate, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e1ddd-291">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="e1ddd-292">Conclusione</span><span class="sxs-lookup"><span data-stu-id="e1ddd-292">Conclusion</span></span> 

<span data-ttu-id="e1ddd-293">In questa esercitazione è stato creato un microservizio ASP.NET Core e sono state aggiunte alcune semplici funzionalità.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-293">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="e1ddd-294">È stata compilata un'immagine del contenitore Docker per il servizio e tale contenitore è stato eseguito nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-294">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="e1ddd-295">È stata collegata una finestra del terminale al servizio e sono stati visualizzati i messaggi di diagnostica provenienti dal servizio stesso.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-295">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="e1ddd-296">Nel corso dell'esercitazione è stato possibile osservare diverse funzionalità del linguaggio C# in azione.</span><span class="sxs-lookup"><span data-stu-id="e1ddd-296">Along the way, you saw several features of the C# language in action.</span></span>
