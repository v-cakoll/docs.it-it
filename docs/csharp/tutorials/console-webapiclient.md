---
title: Creare un client REST usando .NET Core
description: Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.
ms.date: 03/06/2017
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 13466b717d0676c2db5edf4c98a4ead3e673b96c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397920"
---
# <a name="rest-client"></a><span data-ttu-id="04928-103">Client REST</span><span class="sxs-lookup"><span data-stu-id="04928-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="04928-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="04928-104">Introduction</span></span>
<span data-ttu-id="04928-105">Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="04928-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="04928-106">Verranno affrontati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="04928-106">You’ll learn:</span></span>
*   <span data-ttu-id="04928-107">Nozioni di base sull'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="04928-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="04928-108">Panoramica delle funzionalità del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="04928-108">An overview of C# Language features.</span></span>
*   <span data-ttu-id="04928-109">Gestione delle dipendenze con NuGet</span><span class="sxs-lookup"><span data-stu-id="04928-109">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="04928-110">Comunicazioni HTTP</span><span class="sxs-lookup"><span data-stu-id="04928-110">HTTP Communications</span></span>
*   <span data-ttu-id="04928-111">Elaborazione delle informazioni JSON</span><span class="sxs-lookup"><span data-stu-id="04928-111">Processing JSON information</span></span>
*   <span data-ttu-id="04928-112">Gestione della configurazione con attributi</span><span class="sxs-lookup"><span data-stu-id="04928-112">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="04928-113">Si creerà un'applicazione che invia richieste HTTP a un servizio REST su GitHub,</span><span class="sxs-lookup"><span data-stu-id="04928-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="04928-114">si leggeranno informazioni in formato JSON e si convertirà il pacchetto JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="04928-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="04928-115">Si imparerà infine a usare e gestire oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="04928-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="04928-116">In questa esercitazione verranno create anche</span><span class="sxs-lookup"><span data-stu-id="04928-116">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="04928-117">numerose funzionalità.</span><span class="sxs-lookup"><span data-stu-id="04928-117">Let’s build them one by one.</span></span>

<span data-ttu-id="04928-118">Se si vuole proseguire, è possibile scaricare l'[esempio finale](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="04928-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="04928-119">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="04928-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04928-120">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="04928-120">Prerequisites</span></span>
<span data-ttu-id="04928-121">È necessario configurare il computer per l'esecuzione di .NET core.</span><span class="sxs-lookup"><span data-stu-id="04928-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="04928-122">Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="04928-122">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="04928-123">Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="04928-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="04928-124">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="04928-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="04928-125">Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma,</span><span class="sxs-lookup"><span data-stu-id="04928-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="04928-126">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="04928-126">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="04928-127">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="04928-127">Create the Application</span></span>
<span data-ttu-id="04928-128">Il primo passaggio consiste nel creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="04928-128">The first step is to create a new application.</span></span> <span data-ttu-id="04928-129">Aprire un prompt dei comandi e creare una nuova directory per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="04928-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="04928-130">impostandola come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="04928-130">Make that the current directory.</span></span> <span data-ttu-id="04928-131">Digitare il comando `dotnet new console` al prompt dei comandi</span><span class="sxs-lookup"><span data-stu-id="04928-131">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="04928-132">Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="04928-132">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="04928-133">Prima di iniziare ad apportare modifiche, è opportuno ripercorrere i passaggi necessari per eseguire l'applicazione Hello World semplice.</span><span class="sxs-lookup"><span data-stu-id="04928-133">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="04928-134">Dopo aver creato l'applicazione, digitare `dotnet restore` ([vedere la nota](#dotnet-restore-note)) al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="04928-134">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="04928-135">Questo comando esegue il processo di ripristino dei pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="04928-135">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="04928-136">Lo strumento NuGet consente di gestire pacchetti .NET.</span><span class="sxs-lookup"><span data-stu-id="04928-136">NuGet is a .NET package manager.</span></span> <span data-ttu-id="04928-137">Questo comando scarica eventuali dipendenze mancanti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="04928-137">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="04928-138">Poiché si tratta di un nuovo progetto, non è ancora presente alcuna dipendenza e con la prima esecuzione verrà quindi scaricato .NET Core Framework.</span><span class="sxs-lookup"><span data-stu-id="04928-138">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="04928-139">Dopo questo passaggio iniziale, sarà sufficiente eseguire `dotnet restore` ([vedere la nota](#dotnet-restore-note)) quando si aggiungono nuovi pacchetti dipendenti o si aggiorna la versione di una delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="04928-139">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="04928-140">Dopo aver ripristinato i pacchetti, eseguire `dotnet build`</span><span class="sxs-lookup"><span data-stu-id="04928-140">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="04928-141">per avviare il motore di compilazione e creare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04928-141">This executes the build engine and creates your application.</span></span> <span data-ttu-id="04928-142">Eseguire infine `dotnet run` per avviare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04928-142">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="04928-143">Aggiunta di nuove dipendenze</span><span class="sxs-lookup"><span data-stu-id="04928-143">Adding New Dependencies</span></span>
<span data-ttu-id="04928-144">Uno degli obiettivi di progettazione principali di .NET Core è ridurre al minimo le dimensioni dell'installazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="04928-144">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="04928-145">Se per alcune delle funzionalità di un'applicazione sono necessarie altre librerie, è possibile aggiungere tali dipendenze al file di progetto C# (\*.csproj).</span><span class="sxs-lookup"><span data-stu-id="04928-145">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="04928-146">Per questo esempio sarà necessario aggiungere il pacchetto `System.Runtime.Serialization.Json` per consentire all'applicazione di elaborare le risposte JSON.</span><span class="sxs-lookup"><span data-stu-id="04928-146">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="04928-147">Aprire il file di progetto `csproj`.</span><span class="sxs-lookup"><span data-stu-id="04928-147">Open your `csproj` project file.</span></span> <span data-ttu-id="04928-148">La prima riga del file dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="04928-148">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="04928-149">Subito dopo la riga aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="04928-149">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="04928-150">La maggior parte degli editor di codice offre funzioni di completamento per le diverse versioni di queste librerie.</span><span class="sxs-lookup"><span data-stu-id="04928-150">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="04928-151">Si preferisce in genere usare la versione più recente dei pacchetti da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="04928-151">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="04928-152">È importante tuttavia verificare che le versioni di tutti i pacchetti corrispondano tra loro e con la versione del framework dell'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="04928-152">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="04928-153">Dopo aver apportato queste modifiche, eseguire nuovamente `dotnet restore` ([vedere la nota](#dotnet-restore-note)) per consentire l'installazione del pacchetto nel sistema.</span><span class="sxs-lookup"><span data-stu-id="04928-153">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="04928-154">Esecuzione di richieste Web</span><span class="sxs-lookup"><span data-stu-id="04928-154">Making Web Requests</span></span>
<span data-ttu-id="04928-155">Si è ora pronti per iniziare a recuperare dati dal Web.</span><span class="sxs-lookup"><span data-stu-id="04928-155">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="04928-156">In questa applicazione si leggeranno informazioni dall'[API GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="04928-156">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="04928-157">In particolare, si leggeranno informazioni sui progetti nell'ambito di [.NET Foundation](http://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="04928-157">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="04928-158">Si inizierà inviando all'API GitHub la richiesta di recuperare informazioni sui progetti.</span><span class="sxs-lookup"><span data-stu-id="04928-158">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="04928-159">L'endpoint che verrà usato è: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span><span class="sxs-lookup"><span data-stu-id="04928-159">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="04928-160">Poiché si vuole recuperare tutte le informazioni su questi progetti, si userà una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="04928-160">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="04928-161">Anche il browser usa richieste HTTP GET ed è quindi possibile incollare l'URL nel browser per visualizzare le informazioni che si riceveranno ed elaboreranno.</span><span class="sxs-lookup"><span data-stu-id="04928-161">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="04928-162">Per eseguire richieste Web, usare la classe <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="04928-162">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="04928-163">Come tutte le API .NET moderne, <xref:System.Net.Http.HttpClient> supporta solo metodi asincroni per le API a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="04928-163">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="04928-164">È quindi necessario iniziare creando un metodo asincrono,</span><span class="sxs-lookup"><span data-stu-id="04928-164">Start by making an async method.</span></span> <span data-ttu-id="04928-165">che verrà inserito nell'implementazione mentre si compila la funzionalità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="04928-165">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="04928-166">Iniziare aprendo il file `program.cs` nella directory del progetto e aggiungendo il metodo seguente alla classe `Program`:</span><span class="sxs-lookup"><span data-stu-id="04928-166">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="04928-167">Aggiungere quindi un'istruzione `using` all'inizio del metodo `Main`, in modo che il compilatore C# riconosca il tipo <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="04928-167">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="04928-168">Se si compila il progetto in questo momento, viene generato un avviso per indicare che il metodo non contiene alcun operatore `await` e verrà quindi eseguito in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="04928-168">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="04928-169">Ignorare temporaneamente il messaggio. Si aggiungeranno operatori `await` durante la compilazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="04928-169">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="04928-170">Rinominare quindi lo spazio dei nomi definito nell'istruzione `namespace` sostituendo `ConsoleApp` (nome predefinito) con `WebAPIClient`.</span><span class="sxs-lookup"><span data-stu-id="04928-170">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="04928-171">In questo spazio dei nomi si definirà in seguito una classe `repo`.</span><span class="sxs-lookup"><span data-stu-id="04928-171">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="04928-172">Aggiornare quindi il metodo `Main` per chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="04928-172">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="04928-173">Il metodo `ProcessRepositories` restituisce un'attività ed è necessario non uscire dal programma prima che questa sia completata.</span><span class="sxs-lookup"><span data-stu-id="04928-173">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="04928-174">Usare quindi il metodo `Wait` per bloccare il processo e attendere il completamento dell'attività:</span><span class="sxs-lookup"><span data-stu-id="04928-174">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="04928-175">Si dispone a questo punto di un programma che, pur non eseguendo alcuna operazione, opera in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="04928-175">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="04928-176">È ora possibile migliorarlo.</span><span class="sxs-lookup"><span data-stu-id="04928-176">Let's improve it.</span></span>

<span data-ttu-id="04928-177">È necessario innanzitutto un oggetto in grado di recuperare i dati dal Web; a tale scopo è possibile usare <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="04928-177">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="04928-178">per gestire la richiesta e le risposte.</span><span class="sxs-lookup"><span data-stu-id="04928-178">This object handles the request and the responses.</span></span> <span data-ttu-id="04928-179">Creare un'istanza di una singola istanza del tipo nella classe `Program` all'interno del file Program.cs.</span><span class="sxs-lookup"><span data-stu-id="04928-179">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
        {
            //...
        }
    }
}
```

 <span data-ttu-id="04928-180">Tornare quindi al metodo `ProcessRepositories` e compilarne una prima versione:</span><span class="sxs-lookup"><span data-stu-id="04928-180">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="04928-181">Sarà inoltre necessario aggiungere due nuove istruzioni using all'inizio del file per consentirne la compilazione:</span><span class="sxs-lookup"><span data-stu-id="04928-181">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="04928-182">Questa prima versione esegue una richiesta Web per leggere l'elenco di tutti i repository presenti nell'organizzazione DotNet Foundation.</span><span class="sxs-lookup"><span data-stu-id="04928-182">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="04928-183">L'ID di GitHub per .NET Foundation è 'dotnet'.</span><span class="sxs-lookup"><span data-stu-id="04928-183">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="04928-184">Nelle prime righe l'oggetto <xref:System.Net.Http.HttpClient> viene impostato per questa richiesta, ma</span><span class="sxs-lookup"><span data-stu-id="04928-184">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="04928-185">prima viene configurato per accettare le risposte JSON di GitHub.</span><span class="sxs-lookup"><span data-stu-id="04928-185">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="04928-186">Questo formato è semplicemente JSON.</span><span class="sxs-lookup"><span data-stu-id="04928-186">This format is simply JSON.</span></span> <span data-ttu-id="04928-187">Nella riga successiva viene aggiunta un'intestazione Agente utente a tutte le richieste provenienti da questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="04928-187">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="04928-188">Queste due intestazioni vengono controllate dal codice server di GitHub e sono necessarie per recuperare informazioni da GitHub.</span><span class="sxs-lookup"><span data-stu-id="04928-188">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="04928-189">Dopo aver configurato l'oggetto <xref:System.Net.Http.HttpClient>, si eseguirà una richiesta Web e si recupererà la risposta.</span><span class="sxs-lookup"><span data-stu-id="04928-189">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="04928-190">In questa prima versione viene usato il metodo pratico <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04928-190">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="04928-191">Questo metodo avvia un'attività che esegue la richiesta Web e, quando la richiesta viene restituita, legge il flusso di risposta e ne estrae il contenuto.</span><span class="sxs-lookup"><span data-stu-id="04928-191">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="04928-192">Il corpo della risposta viene restituito come <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="04928-192">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="04928-193">La stringa è disponibile quando l'attività viene completata.</span><span class="sxs-lookup"><span data-stu-id="04928-193">The string is available when the task completes.</span></span> 

<span data-ttu-id="04928-194">Le ultime due righe di questo metodo attendono che l'attività sia completata e visualizzano la risposta nella console.</span><span class="sxs-lookup"><span data-stu-id="04928-194">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="04928-195">Compilare l'app ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="04928-195">Build the app, and run it.</span></span> <span data-ttu-id="04928-196">Il messaggio di avviso non viene più visualizzato perché `ProcessRepositories` contiene ora un operatore `await`.</span><span class="sxs-lookup"><span data-stu-id="04928-196">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="04928-197">Verrà visualizzata una lunga schermata di testo JSON formattato.</span><span class="sxs-lookup"><span data-stu-id="04928-197">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="04928-198">Elaborazione del risultato JSON</span><span class="sxs-lookup"><span data-stu-id="04928-198">Processing the JSON Result</span></span>

<span data-ttu-id="04928-199">A questo punto è stato scritto il codice per recuperare una risposta da un server Web e visualizzare il testo contenuto nella risposta.</span><span class="sxs-lookup"><span data-stu-id="04928-199">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="04928-200">Si convertirà ora la risposta JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="04928-200">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="04928-201">Per convertire dati JSON in oggetti C# è possibile usare il serializzatore JSON.</span><span class="sxs-lookup"><span data-stu-id="04928-201">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="04928-202">La prima attività consisterà nel definire un tipo di classe C# in cui saranno contenute le informazioni usate dalla risposta.</span><span class="sxs-lookup"><span data-stu-id="04928-202">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="04928-203">Questa operazione verrà eseguita passo dopo passo e si inizierà con un tipo C# semplice contenente il nome del repository:</span><span class="sxs-lookup"><span data-stu-id="04928-203">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

<span data-ttu-id="04928-204">Inserire il codice precedente in un nuovo file denominato 'repo.cs'.</span><span class="sxs-lookup"><span data-stu-id="04928-204">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="04928-205">Questa versione della classe rappresenta il percorso più semplice per elaborare dati JSON.</span><span class="sxs-lookup"><span data-stu-id="04928-205">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="04928-206">Il nome della classe e il nome del membro corrispondono ai nomi usati nel pacchetto JSON, anziché alle convenzioni C# seguenti.</span><span class="sxs-lookup"><span data-stu-id="04928-206">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="04928-207">Questo errore verrà risolto in un secondo momento specificando alcuni attributi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="04928-207">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="04928-208">Questa classe dimostra un'altra caratteristica importante delle funzioni di serializzazione e deserializzazione JSON: non tutti i campi del pacchetto JSON fanno parte della classe.</span><span class="sxs-lookup"><span data-stu-id="04928-208">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="04928-209">Il serializzatore JSON ignorerà le informazioni non incluse nel tipo di classe in uso.</span><span class="sxs-lookup"><span data-stu-id="04928-209">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="04928-210">In questo modo sarà più semplice creare tipi compatibili con un solo subset dei campi presenti nel pacchetto JSON.</span><span class="sxs-lookup"><span data-stu-id="04928-210">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="04928-211">Dopo aver creato il tipo, è possibile deserializzarlo.</span><span class="sxs-lookup"><span data-stu-id="04928-211">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="04928-212">Sarà quindi necessario creare un oggetto <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>,</span><span class="sxs-lookup"><span data-stu-id="04928-212">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="04928-213">che deve conoscere il tipo CLR previsto per il pacchetto JSON che recupera.</span><span class="sxs-lookup"><span data-stu-id="04928-213">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="04928-214">Il pacchetto di GitHub contiene una sequenza di repository e quindi `List<repo>` è il tipo corretto.</span><span class="sxs-lookup"><span data-stu-id="04928-214">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="04928-215">Aggiungere la riga seguente al metodo `ProcessRepositories`:</span><span class="sxs-lookup"><span data-stu-id="04928-215">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="04928-216">Si useranno due nuovi spazi dei nomi e sarà quindi necessario aggiungere anche questi:</span><span class="sxs-lookup"><span data-stu-id="04928-216">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="04928-217">Si userà infine il serializzatore per convertire i dati JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="04928-217">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="04928-218">Sostituire la chiamata a <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> nel metodo `ProcessRepositories` con le due righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="04928-218">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="04928-219">Si noti che ora viene usato <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anziché <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="04928-219">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="04928-220">Il serializzatore usa un flusso anziché una stringa come origine.</span><span class="sxs-lookup"><span data-stu-id="04928-220">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="04928-221">Verranno ora illustrate alcune funzionalità del linguaggio C# usate nella seconda riga sopra riportata.</span><span class="sxs-lookup"><span data-stu-id="04928-221">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="04928-222">L'argomento per <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> è un'espressione `await`.</span><span class="sxs-lookup"><span data-stu-id="04928-222">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="04928-223">Le espressioni await possono essere presenti quasi ovunque nel codice, anche se finora sono apparse solo nell'ambito di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="04928-223">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="04928-224">Inoltre, l'operatore `as` esegue la conversione del tipo in fase di compilazione da `object` a `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="04928-224">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="04928-225">La dichiarazione di <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> indica che viene restituito un oggetto di tipo <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="04928-225">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="04928-226"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> restituirà il tipo specificato al momento della costruzione (`List<repo>` in questa esercitazione).</span><span class="sxs-lookup"><span data-stu-id="04928-226"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="04928-227">Se la conversione non riesce, l'operatore `as` restituisce `null` anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="04928-227">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="04928-228">Questa sezione è quasi completata.</span><span class="sxs-lookup"><span data-stu-id="04928-228">You're almost done with this section.</span></span> <span data-ttu-id="04928-229">Ora che i dati JSON sono stati convertiti in oggetti C#, verrà visualizzato il nome di ogni repository.</span><span class="sxs-lookup"><span data-stu-id="04928-229">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="04928-230">Sostituire le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="04928-230">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="04928-231">con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="04928-231">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="04928-232">Compilare l'applicazione ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="04928-232">Compile and run the application.</span></span> <span data-ttu-id="04928-233">Verranno stampati i nomi dei repository che fanno parte di .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="04928-233">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="04928-234">Controllo della serializzazione</span><span class="sxs-lookup"><span data-stu-id="04928-234">Controlling Serialization</span></span>

<span data-ttu-id="04928-235">Prima di aggiungere altre funzionalità, è necessario indirizzare il tipo `repo` e renderlo conforme ad altre convenzioni C# standard.</span><span class="sxs-lookup"><span data-stu-id="04928-235">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="04928-236">A questo scopo, è necessario annotare il tipo `repo` con *attributi* che controllano il funzionamento del serializzatore JSON.</span><span class="sxs-lookup"><span data-stu-id="04928-236">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="04928-237">In questo caso, si useranno questi attributi per definire un mapping tra i nomi di chiavi JSON e i nomi di membri e classi C#.</span><span class="sxs-lookup"><span data-stu-id="04928-237">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="04928-238">In particolare, verranno usati i due attributi `DataContract` e `DataMember`.</span><span class="sxs-lookup"><span data-stu-id="04928-238">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="04928-239">Per convenzione, tutte le classi di attributo terminano con il suffisso `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="04928-239">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="04928-240">Questo suffisso, tuttavia, non deve essere necessariamente usato quando si applica un attributo.</span><span class="sxs-lookup"><span data-stu-id="04928-240">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="04928-241">Gli attributi `DataContract` e `DataMember` si trovano in un'altra libreria che sarà necessario aggiungere al file di progetto C# come dipendenza.</span><span class="sxs-lookup"><span data-stu-id="04928-241">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="04928-242">Aggiungere la riga seguente alla sezione `<ItemGroup>` del file di progetto:</span><span class="sxs-lookup"><span data-stu-id="04928-242">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="04928-243">Dopo aver salvato il file, eseguire `dotnet restore` ([vedere la nota](#dotnet-restore-note)) per recuperare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="04928-243">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="04928-244">Aprire quindi il file `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="04928-244">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="04928-245">È possibile modificare il nome in modo da usare la convenzione Pascal e specificare il nome completo `Repository`.</span><span class="sxs-lookup"><span data-stu-id="04928-245">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="04928-246">Si vuole ora eseguire il mapping dei nodi 'repo' di JSON a questo tipo e sarà quindi necessario aggiungere l'attributo `DataContract` alla dichiarazione di classe.</span><span class="sxs-lookup"><span data-stu-id="04928-246">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="04928-247">Si imposterà la proprietà `Name` dell'attributo sul nome dei nodi JSON mappati a questo tipo:</span><span class="sxs-lookup"><span data-stu-id="04928-247">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="04928-248"><xref:System.Runtime.Serialization.DataContractAttribute> è un membro dello spazio dei nomi <xref:System.Runtime.Serialization> e sarà quindi necessario aggiungere l'istruzione `using` appropriata all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="04928-248">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="04928-249">Il nome della classe `repo` è stato modificato in `Repository` e sarà quindi necessario apportare la stessa modifica in Program.cs. È possibile che alcuni editor supportino un refactoring di ridenominazione in virtù del quale questa modifica verrebbe apportata in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="04928-249">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="04928-250">Si apporterà quindi la stessa modifica per il campo `name` usando la classe <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="04928-250">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="04928-251">A questo scopo, eseguire le modifiche seguenti alla dichiarazione del campo `name` in repo.cs:</span><span class="sxs-lookup"><span data-stu-id="04928-251">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="04928-252">Con questa operazione si modifica il codice che scrive il nome di ogni repository in program.cs:</span><span class="sxs-lookup"><span data-stu-id="04928-252">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="04928-253">Eseguire un comando `dotnet build` seguito da un comando `dotnet run` per assicurarsi che i mapping siano stati eseguiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="04928-253">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="04928-254">L'output ottenuto dovrebbe essere uguale a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="04928-254">You should see the same output as before.</span></span> <span data-ttu-id="04928-255">Prima di elaborare altre proprietà del server Web è necessario apportare un'altra modifica alla classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="04928-255">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="04928-256">Il membro `Name` è un campo accessibile pubblicamente.</span><span class="sxs-lookup"><span data-stu-id="04928-256">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="04928-257">Non essendo questa una prassi raccomandabile nella programmazione orientata agli oggetti, si trasformerà il membro in una proprietà.</span><span class="sxs-lookup"><span data-stu-id="04928-257">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="04928-258">Ai fini di questa esercitazione, non è necessario eseguire alcun codice specifico per ottenere o impostare la proprietà, ma la conversione in una proprietà consente di aggiungere più facilmente eventuali modifiche in un secondo momento, senza dover modificare il codice che usa la classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="04928-258">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="04928-259">Rimuovere la definizione di campo e sostituirla con una [proprietà implementata automaticamente](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span><span class="sxs-lookup"><span data-stu-id="04928-259">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="04928-260">Il compilatore genera il corpo delle funzioni di accesso `get` e `set`, oltre a un campo privato in cui archiviare il nome,</span><span class="sxs-lookup"><span data-stu-id="04928-260">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="04928-261">con un codice simile al seguente, che è possibile digitare anche manualmente:</span><span class="sxs-lookup"><span data-stu-id="04928-261">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="04928-262">Si apporterà di seguito un'ultima modifica prima di aggiungere nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="04928-262">Let's make one more change before adding new features.</span></span> <span data-ttu-id="04928-263">Il metodo `ProcessRepositories` può operare in modo asincrono e restituire una raccolta di repository.</span><span class="sxs-lookup"><span data-stu-id="04928-263">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="04928-264">È ora necessario fare in modo che il metodo restituisca `List<Repository>` e spostare il codice che scrive le informazioni nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="04928-264">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="04928-265">Modificare la firma di `ProcessRepositories` in modo da restituire un'attività il cui risultato sia un elenco di oggetti `Repository`:</span><span class="sxs-lookup"><span data-stu-id="04928-265">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="04928-266">Restituire quindi i repository dopo aver elaborato la risposta JSON:</span><span class="sxs-lookup"><span data-stu-id="04928-266">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="04928-267">Il compilatore genera l'oggetto `Task<T>` come elemento restituito perché il metodo è stato contrassegnato come `async`.</span><span class="sxs-lookup"><span data-stu-id="04928-267">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="04928-268">Si modificherà ora il metodo `Main` in modo che acquisisca i risultati e scriva ogni nome di repository nella console.</span><span class="sxs-lookup"><span data-stu-id="04928-268">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="04928-269">Il metodo `Main` avrà ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="04928-269">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="04928-270">L'accesso alla proprietà `Result` di un'attività è bloccato fino al completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="04928-270">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="04928-271">In genere, si preferisce attendere il completamento dell'attività con un'espressione `await`, come nel metodo `ProcessRepositories`, ma questa possibilità non è prevista nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="04928-271">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="04928-272">Lettura di altre informazioni</span><span class="sxs-lookup"><span data-stu-id="04928-272">Reading More Information</span></span>

<span data-ttu-id="04928-273">Per completare l'esercitazione si elaboreranno ora altre proprietà del pacchetto JSON inviato dall'API di GitHub.</span><span class="sxs-lookup"><span data-stu-id="04928-273">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="04928-274">Non si intende acquisire tutte le informazioni possibili ma, aggiungendo alcune proprietà, sarà possibile illustrare qualche altra funzionalità del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="04928-274">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="04928-275">Si inizierà aggiungendo altri tipi semplici alla definizione di classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="04928-275">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="04928-276">Aggiungere quindi alla classe le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="04928-276">Add these properties to that class:</span></span>

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="04928-277">In queste proprietà sono incorporate conversioni dal tipo stringa (il contenuto dei pacchetti JSON) al tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="04928-277">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="04928-278">Il tipo <xref:System.Uri>, che per alcuni utenti può essere nuovo,</span><span class="sxs-lookup"><span data-stu-id="04928-278">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="04928-279">rappresenta un URI o, come in questo caso, un URL.</span><span class="sxs-lookup"><span data-stu-id="04928-279">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="04928-280">Nel caso dei tipi `Uri` e `int`, se il pacchetto JSON contiene dati che non possono essere convertiti nel tipo di destinazione, l'azione di serializzazione genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="04928-280">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="04928-281">Dopo aver aggiunto queste proprietà, aggiornare il metodo `Main` per visualizzare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="04928-281">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```
<span data-ttu-id="04928-282">Come passaggio conclusivo si aggiungeranno le informazioni necessarie per l'ultima operazione push,</span><span class="sxs-lookup"><span data-stu-id="04928-282">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="04928-283">formattate nella risposta JSON come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="04928-283">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="04928-284">Questo formato non segue nessuno dei formati .NET <xref:System.DateTime> standard e,</span><span class="sxs-lookup"><span data-stu-id="04928-284">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="04928-285">pertanto, sarà necessario scrivere un metodo di conversione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="04928-285">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="04928-286">Probabilmente si vorrà evitare anche che la stringa non elaborata sia esposta agli utenti della classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="04928-286">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="04928-287">Gli attributi possono essere utili per controllare anche questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="04928-287">Attributes can help control that as well.</span></span> <span data-ttu-id="04928-288">È necessario prima definire una proprietà `private` che contenga la rappresentazione stringa del valore data/ora della classe `Repository`:</span><span class="sxs-lookup"><span data-stu-id="04928-288">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="04928-289">L'attributo `DataMember` informa il serializzatore che questo elemento deve essere elaborato, anche se non è un membro pubblico.</span><span class="sxs-lookup"><span data-stu-id="04928-289">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="04928-290">Sarà quindi necessario scrivere una proprietà pubblica di sola lettura che converta la stringa in un oggetto <xref:System.DateTime> valido e restituisca il valore <xref:System.DateTime> specificato:</span><span class="sxs-lookup"><span data-stu-id="04928-290">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

<span data-ttu-id="04928-291">Relativamente ai nuovi costrutti sopra riportati,</span><span class="sxs-lookup"><span data-stu-id="04928-291">Let's go over the new constructs above.</span></span> <span data-ttu-id="04928-292">l'attributo `IgnoreDataMember` informa il serializzatore che questo tipo non deve essere letto o scritto da qualsiasi oggetto JSON.</span><span class="sxs-lookup"><span data-stu-id="04928-292">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="04928-293">Questa proprietà contiene solo una funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="04928-293">This property contains only a `get` accessor.</span></span> <span data-ttu-id="04928-294">Non è presente alcuna funzione di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="04928-294">There is no `set` accessor.</span></span> <span data-ttu-id="04928-295">Ecco come definire una proprietà di *sola lettura* in C#.</span><span class="sxs-lookup"><span data-stu-id="04928-295">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="04928-296">È possibile creare anche proprietà di *sola scrittura* in C#, ma con un valore limitato. Il metodo <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> analizza una stringa e crea prima un oggetto <xref:System.DateTime> usando un formato di data specificato e quindi aggiunge altri metadati a `DateTime` usando un oggetto `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="04928-296">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="04928-297">Se l'operazione di analisi ha esito negativo, la funzione di accesso della proprietà genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="04928-297">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="04928-298">Per usare <xref:System.Globalization.CultureInfo.InvariantCulture> sarà necessario aggiungere lo spazio dei nomi <xref:System.Globalization> alle istruzioni `using` in `repo.cs`:</span><span class="sxs-lookup"><span data-stu-id="04928-298">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="04928-299">Dopo aver aggiunto un'altra istruzione di output alla console, sarà possibile compilare ed eseguire nuovamente l'app:</span><span class="sxs-lookup"><span data-stu-id="04928-299">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="04928-300">La versione dell'app dovrebbe ora corrispondere all'[esempio completo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="04928-300">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="04928-301">Conclusione</span><span class="sxs-lookup"><span data-stu-id="04928-301">Conclusion</span></span>

<span data-ttu-id="04928-302">In questa esercitazione sono state descritte le procedure necessarie per eseguire richieste Web, analizzare i risultati e visualizzare le proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="04928-302">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="04928-303">Sono stati inoltre aggiunti nuovi pacchetti come dipendenze del progetto</span><span class="sxs-lookup"><span data-stu-id="04928-303">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="04928-304">e sono state illustrate alcune delle funzionalità del linguaggio C# che supportano tecniche orientate agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="04928-304">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
