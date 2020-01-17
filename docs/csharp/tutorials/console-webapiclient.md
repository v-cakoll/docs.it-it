---
title: Creare un client REST usando .NET Core
description: Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 85a3c8e17e14db86786950380ba745ae286dccca
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115866"
---
# <a name="rest-client"></a><span data-ttu-id="80d38-103">Client REST</span><span class="sxs-lookup"><span data-stu-id="80d38-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="80d38-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="80d38-104">Introduction</span></span>

<span data-ttu-id="80d38-105">Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="80d38-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="80d38-106">Verranno affrontati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="80d38-106">You’ll learn:</span></span>

* <span data-ttu-id="80d38-107">Nozioni di base sull'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="80d38-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="80d38-108">Panoramica delle funzionalità del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="80d38-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="80d38-109">Gestione delle dipendenze con NuGet</span><span class="sxs-lookup"><span data-stu-id="80d38-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="80d38-110">Comunicazioni HTTP</span><span class="sxs-lookup"><span data-stu-id="80d38-110">HTTP Communications</span></span>
* <span data-ttu-id="80d38-111">Elaborazione delle informazioni JSON</span><span class="sxs-lookup"><span data-stu-id="80d38-111">Processing JSON information</span></span>
* <span data-ttu-id="80d38-112">Gestione della configurazione con attributi</span><span class="sxs-lookup"><span data-stu-id="80d38-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="80d38-113">Si creerà un'applicazione che invia richieste HTTP a un servizio REST su GitHub,</span><span class="sxs-lookup"><span data-stu-id="80d38-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="80d38-114">si leggeranno informazioni in formato JSON e si convertirà il pacchetto JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="80d38-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="80d38-115">Si imparerà infine a usare e gestire oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="80d38-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="80d38-116">Questa esercitazione include molte funzionalità.</span><span class="sxs-lookup"><span data-stu-id="80d38-116">There are many features in this tutorial.</span></span> <span data-ttu-id="80d38-117">numerose funzionalità.</span><span class="sxs-lookup"><span data-stu-id="80d38-117">Let’s build them one by one.</span></span>

<span data-ttu-id="80d38-118">Se si vuole proseguire, è possibile scaricare l'[esempio finale](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="80d38-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="80d38-119">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="80d38-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80d38-120">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="80d38-120">Prerequisites</span></span>

<span data-ttu-id="80d38-121">È necessario configurare il computer per l'esecuzione di .NET core.</span><span class="sxs-lookup"><span data-stu-id="80d38-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="80d38-122">È possibile trovare le istruzioni di installazione nella pagina di [download di .NET Core](https://dotnet.microsoft.com/download) .</span><span class="sxs-lookup"><span data-stu-id="80d38-122">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="80d38-123">Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="80d38-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="80d38-124">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="80d38-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="80d38-125">Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma,</span><span class="sxs-lookup"><span data-stu-id="80d38-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="80d38-126">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="80d38-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="80d38-127">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="80d38-127">Create the Application</span></span>

<span data-ttu-id="80d38-128">Il primo passaggio consiste nel creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="80d38-128">The first step is to create a new application.</span></span> <span data-ttu-id="80d38-129">Aprire un prompt dei comandi e creare una nuova directory per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="80d38-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="80d38-130">impostandola come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="80d38-130">Make that the current directory.</span></span> <span data-ttu-id="80d38-131">Immettere il comando seguente in una finestra della console:</span><span class="sxs-lookup"><span data-stu-id="80d38-131">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="80d38-132">Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="80d38-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="80d38-133">Il nome del progetto è "WebApiClient".</span><span class="sxs-lookup"><span data-stu-id="80d38-133">The project name is "WebApiClient".</span></span> <span data-ttu-id="80d38-134">Poiché si tratta di un nuovo progetto, non è presente alcuna dipendenza.</span><span class="sxs-lookup"><span data-stu-id="80d38-134">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="80d38-135">La prima esecuzione consente di scaricare il Framework .NET Core, installare un certificato di sviluppo ed eseguire Gestione pacchetti NuGet per ripristinare le dipendenze mancanti.</span><span class="sxs-lookup"><span data-stu-id="80d38-135">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="80d38-136">Prima di iniziare ad apportare modifiche, digitare `dotnet run` ([vedere la nota](#dotnet-restore-note)) al prompt dei comandi per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="80d38-136">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="80d38-137">`dotnet run` esegue automaticamente `dotnet restore` se nell'ambiente mancano dipendenze.</span><span class="sxs-lookup"><span data-stu-id="80d38-137">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="80d38-138">Esegue anche `dotnet build` se l'applicazione deve essere ricompilata.</span><span class="sxs-lookup"><span data-stu-id="80d38-138">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="80d38-139">Dopo l'installazione iniziale, sarà necessario solo eseguire `dotnet restore` o `dotnet build` quando ha senso per il progetto.</span><span class="sxs-lookup"><span data-stu-id="80d38-139">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="80d38-140">Aggiunta di nuove dipendenze</span><span class="sxs-lookup"><span data-stu-id="80d38-140">Adding New Dependencies</span></span>

<span data-ttu-id="80d38-141">Uno degli obiettivi di progettazione principali di .NET Core è ridurre al minimo le dimensioni dell'installazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="80d38-141">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="80d38-142">Se per alcune delle funzionalità di un'applicazione sono necessarie altre librerie, è possibile aggiungere tali dipendenze al file di progetto C# (\*.csproj).</span><span class="sxs-lookup"><span data-stu-id="80d38-142">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="80d38-143">Per questo esempio, è necessario aggiungere il pacchetto di `System.Runtime.Serialization.Json`, in modo che l'applicazione possa elaborare le risposte JSON.</span><span class="sxs-lookup"><span data-stu-id="80d38-143">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="80d38-144">È necessario il pacchetto di `System.Runtime.Serialization.Json` per questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="80d38-144">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="80d38-145">Aggiungerlo al progetto eseguendo il comando seguente dell' [interfaccia](../../core/tools/dotnet-add-package.md) della riga di comando di .NET:</span><span class="sxs-lookup"><span data-stu-id="80d38-145">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```console
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="80d38-146">Esecuzione di richieste Web</span><span class="sxs-lookup"><span data-stu-id="80d38-146">Making Web Requests</span></span>

<span data-ttu-id="80d38-147">Si è ora pronti per iniziare a recuperare dati dal Web.</span><span class="sxs-lookup"><span data-stu-id="80d38-147">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="80d38-148">In questa applicazione si leggeranno informazioni dall'[API GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="80d38-148">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="80d38-149">In particolare, si leggeranno informazioni sui progetti nell'ambito di [.NET Foundation](https://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="80d38-149">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="80d38-150">Si inizierà inviando all'API GitHub la richiesta di recuperare informazioni sui progetti.</span><span class="sxs-lookup"><span data-stu-id="80d38-150">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="80d38-151">L'endpoint che verrà usato è: <https://api.github.com/orgs/dotnet/repos>.</span><span class="sxs-lookup"><span data-stu-id="80d38-151">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="80d38-152">Poiché si vuole recuperare tutte le informazioni su questi progetti, si userà una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="80d38-152">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="80d38-153">Anche il browser usa richieste HTTP GET ed è quindi possibile incollare l'URL nel browser per visualizzare le informazioni che si riceveranno ed elaboreranno.</span><span class="sxs-lookup"><span data-stu-id="80d38-153">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="80d38-154">Per eseguire richieste Web, usare la classe <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="80d38-154">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="80d38-155">Come tutte le API .NET moderne, <xref:System.Net.Http.HttpClient> supporta solo metodi asincroni per le API a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="80d38-155">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="80d38-156">È quindi necessario iniziare creando un metodo asincrono,</span><span class="sxs-lookup"><span data-stu-id="80d38-156">Start by making an async method.</span></span> <span data-ttu-id="80d38-157">che verrà inserito nell'implementazione mentre si compila la funzionalità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="80d38-157">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="80d38-158">Iniziare aprendo il file `program.cs` nella directory del progetto e aggiungendo il metodo seguente alla classe `Program`:</span><span class="sxs-lookup"><span data-stu-id="80d38-158">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="80d38-159">Aggiungere quindi un'istruzione `using` all'inizio del metodo `Main`, in modo che il compilatore C# riconosca il tipo <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="80d38-159">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="80d38-160">Se si compila il progetto in questo momento, viene generato un avviso per indicare che il metodo non contiene alcun operatore `await` e verrà quindi eseguito in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="80d38-160">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="80d38-161">Ignorare temporaneamente il messaggio. Si aggiungeranno operatori `await` durante la compilazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="80d38-161">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="80d38-162">Rinominare quindi lo spazio dei nomi definito nell'istruzione `namespace` sostituendo `ConsoleApp` (nome predefinito) con `WebAPIClient`.</span><span class="sxs-lookup"><span data-stu-id="80d38-162">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="80d38-163">In questo spazio dei nomi si definirà in seguito una classe `repo`.</span><span class="sxs-lookup"><span data-stu-id="80d38-163">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="80d38-164">Aggiornare quindi il metodo `Main` per chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="80d38-164">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="80d38-165">Il metodo `ProcessRepositories` restituisce un'attività ed è necessario non uscire dal programma prima che questa sia completata.</span><span class="sxs-lookup"><span data-stu-id="80d38-165">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="80d38-166">È pertanto necessario modificare la firma del `Main`.</span><span class="sxs-lookup"><span data-stu-id="80d38-166">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="80d38-167">Aggiungere il modificatore `async` e modificare il tipo restituito in `Task`.</span><span class="sxs-lookup"><span data-stu-id="80d38-167">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="80d38-168">Quindi, nel corpo del metodo, aggiungere una chiamata a `ProcessRepositories`.</span><span class="sxs-lookup"><span data-stu-id="80d38-168">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="80d38-169">Aggiungere la parola chiave `await` quando alla chiamata al metodo:</span><span class="sxs-lookup"><span data-stu-id="80d38-169">Add the `await` keyword when to that method call:</span></span>

```csharp
static Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="80d38-170">Si dispone a questo punto di un programma che, pur non eseguendo alcuna operazione, opera in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="80d38-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="80d38-171">È ora possibile migliorarlo.</span><span class="sxs-lookup"><span data-stu-id="80d38-171">Let's improve it.</span></span>

<span data-ttu-id="80d38-172">È necessario innanzitutto un oggetto in grado di recuperare i dati dal Web; a tale scopo è possibile usare <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="80d38-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="80d38-173">per gestire la richiesta e le risposte.</span><span class="sxs-lookup"><span data-stu-id="80d38-173">This object handles the request and the responses.</span></span> <span data-ttu-id="80d38-174">Creare un'istanza di una singola istanza del tipo nella classe `Program` all'interno del file Program.cs.</span><span class="sxs-lookup"><span data-stu-id="80d38-174">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="80d38-175">Tornare quindi al metodo `ProcessRepositories` e compilarne una prima versione:</span><span class="sxs-lookup"><span data-stu-id="80d38-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="80d38-176">Sarà inoltre necessario aggiungere due nuove istruzioni using all'inizio del file per consentirne la compilazione:</span><span class="sxs-lookup"><span data-stu-id="80d38-176">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="80d38-177">Questa prima versione esegue una richiesta Web per leggere l'elenco di tutti i repository presenti nell'organizzazione DotNet Foundation.</span><span class="sxs-lookup"><span data-stu-id="80d38-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="80d38-178">L'ID di GitHub per .NET Foundation è 'dotnet'.</span><span class="sxs-lookup"><span data-stu-id="80d38-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="80d38-179">Nelle prime righe l'oggetto <xref:System.Net.Http.HttpClient> viene impostato per questa richiesta, ma</span><span class="sxs-lookup"><span data-stu-id="80d38-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="80d38-180">prima viene configurato per accettare le risposte JSON di GitHub.</span><span class="sxs-lookup"><span data-stu-id="80d38-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="80d38-181">Questo formato è semplicemente JSON.</span><span class="sxs-lookup"><span data-stu-id="80d38-181">This format is simply JSON.</span></span> <span data-ttu-id="80d38-182">Nella riga successiva viene aggiunta un'intestazione Agente utente a tutte le richieste provenienti da questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="80d38-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="80d38-183">Queste due intestazioni vengono controllate dal codice server di GitHub e sono necessarie per recuperare informazioni da GitHub.</span><span class="sxs-lookup"><span data-stu-id="80d38-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="80d38-184">Dopo aver configurato l'oggetto <xref:System.Net.Http.HttpClient>, si eseguirà una richiesta Web e si recupererà la risposta.</span><span class="sxs-lookup"><span data-stu-id="80d38-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="80d38-185">In questa prima versione viene usato il metodo pratico <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80d38-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="80d38-186">Questo metodo avvia un'attività che esegue la richiesta Web e, quando la richiesta viene restituita, legge il flusso di risposta e ne estrae il contenuto.</span><span class="sxs-lookup"><span data-stu-id="80d38-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="80d38-187">Il corpo della risposta viene restituito come <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="80d38-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="80d38-188">La stringa è disponibile quando l'attività viene completata.</span><span class="sxs-lookup"><span data-stu-id="80d38-188">The string is available when the task completes.</span></span>

<span data-ttu-id="80d38-189">Le ultime due righe di questo metodo attendono che l'attività sia completata e visualizzano la risposta nella console.</span><span class="sxs-lookup"><span data-stu-id="80d38-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="80d38-190">Compilare l'app ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="80d38-190">Build the app, and run it.</span></span> <span data-ttu-id="80d38-191">Il messaggio di avviso non viene più visualizzato perché `ProcessRepositories` contiene ora un operatore `await`.</span><span class="sxs-lookup"><span data-stu-id="80d38-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="80d38-192">Verrà visualizzata una lunga schermata di testo JSON formattato.</span><span class="sxs-lookup"><span data-stu-id="80d38-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="80d38-193">Elaborazione del risultato JSON</span><span class="sxs-lookup"><span data-stu-id="80d38-193">Processing the JSON Result</span></span>

<span data-ttu-id="80d38-194">A questo punto è stato scritto il codice per recuperare una risposta da un server Web e visualizzare il testo contenuto nella risposta.</span><span class="sxs-lookup"><span data-stu-id="80d38-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="80d38-195">Si convertirà ora la risposta JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="80d38-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="80d38-196">La classe <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> serializza gli oggetti in JSON e deserializza JSON negli oggetti.</span><span class="sxs-lookup"><span data-stu-id="80d38-196">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="80d38-197">Iniziare definendo una classe per rappresentare il `repo` oggetto JSON restituito dall'API GitHub:</span><span class="sxs-lookup"><span data-stu-id="80d38-197">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; };
    }
}
```

<span data-ttu-id="80d38-198">Inserire il codice precedente in un nuovo file denominato 'repo.cs'.</span><span class="sxs-lookup"><span data-stu-id="80d38-198">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="80d38-199">Questa versione della classe rappresenta il percorso più semplice per elaborare dati JSON.</span><span class="sxs-lookup"><span data-stu-id="80d38-199">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="80d38-200">Il nome della classe e il nome del membro corrispondono ai nomi usati nel pacchetto JSON, anziché alle convenzioni C# seguenti.</span><span class="sxs-lookup"><span data-stu-id="80d38-200">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="80d38-201">Questo errore verrà risolto in un secondo momento specificando alcuni attributi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="80d38-201">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="80d38-202">Questa classe dimostra un'altra caratteristica importante delle funzioni di serializzazione e deserializzazione JSON: non tutti i campi del pacchetto JSON fanno parte della classe.</span><span class="sxs-lookup"><span data-stu-id="80d38-202">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="80d38-203">Il serializzatore JSON ignorerà le informazioni non incluse nel tipo di classe in uso.</span><span class="sxs-lookup"><span data-stu-id="80d38-203">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="80d38-204">In questo modo sarà più semplice creare tipi compatibili con un solo subset dei campi presenti nel pacchetto JSON.</span><span class="sxs-lookup"><span data-stu-id="80d38-204">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="80d38-205">Dopo aver creato il tipo, è possibile deserializzarlo.</span><span class="sxs-lookup"><span data-stu-id="80d38-205">Now that you've created the type, let's deserialize it.</span></span> 

<span data-ttu-id="80d38-206">Si userà infine il serializzatore per convertire i dati JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="80d38-206">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="80d38-207">Sostituire la chiamata a <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> nel metodo `ProcessRepositories` con le tre righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="80d38-207">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following three lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="80d38-208">Si sta usando un nuovo spazio dei nomi, quindi è necessario aggiungerlo anche all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="80d38-208">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="80d38-209">Si noti che ora viene usato <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anziché <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="80d38-209">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="80d38-210">Il serializzatore usa un flusso anziché una stringa come origine.</span><span class="sxs-lookup"><span data-stu-id="80d38-210">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="80d38-211">Verranno ora illustrate alcune funzionalità del C# linguaggio utilizzate nella seconda riga del frammento di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="80d38-211">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="80d38-212">Il primo argomento per <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> è un'espressione `await`.</span><span class="sxs-lookup"><span data-stu-id="80d38-212">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="80d38-213">Gli altri due parametri sono facoltativi e vengono omessi nel frammento di codice. Le espressioni await possono apparire praticamente in qualsiasi punto del codice, anche se fino a questo momento sono state viste solo come parte di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="80d38-213">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="80d38-214">Il metodo `Deserialize` è *generico*, pertanto è necessario fornire gli argomenti di tipo per il tipo di oggetti che devono essere creati dal testo JSON.</span><span class="sxs-lookup"><span data-stu-id="80d38-214">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="80d38-215">In questo esempio si esegue la deserializzazione in un `List<Repository>`, ovvero un altro oggetto generico, l'<xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80d38-215">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="80d38-216">La classe `List<>` archivia una raccolta di oggetti.</span><span class="sxs-lookup"><span data-stu-id="80d38-216">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="80d38-217">L'argomento tipo dichiara il tipo di oggetti archiviati nel `List<>`.</span><span class="sxs-lookup"><span data-stu-id="80d38-217">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="80d38-218">Il testo JSON rappresenta una raccolta di oggetti repository, quindi l'argomento di tipo viene `Repository`.</span><span class="sxs-lookup"><span data-stu-id="80d38-218">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="80d38-219">Questa sezione è quasi completata.</span><span class="sxs-lookup"><span data-stu-id="80d38-219">You're almost done with this section.</span></span> <span data-ttu-id="80d38-220">Ora che i dati JSON sono stati convertiti in oggetti C#, verrà visualizzato il nome di ogni repository.</span><span class="sxs-lookup"><span data-stu-id="80d38-220">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="80d38-221">Sostituire le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="80d38-221">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="80d38-222">con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="80d38-222">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="80d38-223">Compilare l'applicazione ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="80d38-223">Compile and run the application.</span></span> <span data-ttu-id="80d38-224">Verranno stampati i nomi dei repository che fanno parte di .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="80d38-224">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="80d38-225">Controllo della serializzazione</span><span class="sxs-lookup"><span data-stu-id="80d38-225">Controlling Serialization</span></span>

<span data-ttu-id="80d38-226">Prima di aggiungere altre funzionalità, è possibile indirizzare la proprietà `name` usando l'attributo `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="80d38-226">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="80d38-227">A questo scopo, eseguire le modifiche seguenti alla dichiarazione del campo `name` in repo.cs:</span><span class="sxs-lookup"><span data-stu-id="80d38-227">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="80d38-228">Con questa operazione si modifica il codice che scrive il nome di ogni repository in program.cs:</span><span class="sxs-lookup"><span data-stu-id="80d38-228">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="80d38-229">Eseguire `dotnet run` per assicurarsi che i mapping siano corretti.</span><span class="sxs-lookup"><span data-stu-id="80d38-229">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="80d38-230">L'output ottenuto dovrebbe essere uguale a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="80d38-230">You should see the same output as before.</span></span>

<span data-ttu-id="80d38-231">Si apporterà di seguito un'ultima modifica prima di aggiungere nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="80d38-231">Let's make one more change before adding new features.</span></span> <span data-ttu-id="80d38-232">Il metodo `ProcessRepositories` può operare in modo asincrono e restituire una raccolta di repository.</span><span class="sxs-lookup"><span data-stu-id="80d38-232">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="80d38-233">È ora necessario fare in modo che il metodo restituisca `List<Repository>` e spostare il codice che scrive le informazioni nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="80d38-233">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="80d38-234">Modificare la firma di `ProcessRepositories` in modo da restituire un'attività il cui risultato sia un elenco di oggetti `Repository`:</span><span class="sxs-lookup"><span data-stu-id="80d38-234">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="80d38-235">Restituire quindi i repository dopo aver elaborato la risposta JSON:</span><span class="sxs-lookup"><span data-stu-id="80d38-235">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="80d38-236">Il compilatore genera l'oggetto `Task<T>` come elemento restituito perché il metodo è stato contrassegnato come `async`.</span><span class="sxs-lookup"><span data-stu-id="80d38-236">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="80d38-237">Si modificherà ora il metodo `Main` in modo che acquisisca i risultati e scriva ogni nome di repository nella console.</span><span class="sxs-lookup"><span data-stu-id="80d38-237">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="80d38-238">Il metodo `Main` avrà ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="80d38-238">Your `Main` method now looks like this:</span></span>

```csharp
public static Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="80d38-239">Lettura di altre informazioni</span><span class="sxs-lookup"><span data-stu-id="80d38-239">Reading More Information</span></span>

<span data-ttu-id="80d38-240">Per completare l'esercitazione si elaboreranno ora altre proprietà del pacchetto JSON inviato dall'API di GitHub.</span><span class="sxs-lookup"><span data-stu-id="80d38-240">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="80d38-241">Non si intende acquisire tutte le informazioni possibili ma, aggiungendo alcune proprietà, sarà possibile illustrare qualche altra funzionalità del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="80d38-241">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="80d38-242">Si inizierà aggiungendo altri tipi semplici alla definizione di classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="80d38-242">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="80d38-243">Aggiungere quindi alla classe le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="80d38-243">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName(Name="description")]
public string Description { get; set; }

[JsonPropertyName(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName(Name="homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="80d38-244">In queste proprietà sono incorporate conversioni dal tipo stringa (il contenuto dei pacchetti JSON) al tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="80d38-244">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="80d38-245">Il tipo <xref:System.Uri>, che per alcuni utenti può essere nuovo,</span><span class="sxs-lookup"><span data-stu-id="80d38-245">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="80d38-246">rappresenta un URI o, come in questo caso, un URL.</span><span class="sxs-lookup"><span data-stu-id="80d38-246">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="80d38-247">Nel caso dei tipi `Uri` e `int`, se il pacchetto JSON contiene dati che non possono essere convertiti nel tipo di destinazione, l'azione di serializzazione genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="80d38-247">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="80d38-248">Dopo aver aggiunto queste proprietà, aggiornare il metodo `Main` per visualizzare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="80d38-248">Once you've added these, update the `Main` method to display those elements:</span></span>

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

<span data-ttu-id="80d38-249">Come passaggio conclusivo si aggiungeranno le informazioni necessarie per l'ultima operazione push,</span><span class="sxs-lookup"><span data-stu-id="80d38-249">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="80d38-250">formattate nella risposta JSON come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="80d38-250">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="80d38-251">Questo formato non segue nessuno dei formati .NET <xref:System.DateTime> standard e,</span><span class="sxs-lookup"><span data-stu-id="80d38-251">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="80d38-252">pertanto, sarà necessario scrivere un metodo di conversione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="80d38-252">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="80d38-253">Probabilmente si vorrà evitare anche che la stringa non elaborata sia esposta agli utenti della classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="80d38-253">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="80d38-254">Gli attributi possono essere utili per controllare anche questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="80d38-254">Attributes can help control that as well.</span></span> <span data-ttu-id="80d38-255">Definire innanzitutto una proprietà di `public` che conterrà la rappresentazione di stringa della data e dell'ora nella classe `Repository` e una proprietà `readonly` `LastPush` che restituisca una stringa formattata che rappresenta la data restituita:</span><span class="sxs-lookup"><span data-stu-id="80d38-255">First, define a `public` property that will hold the string representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns a formatted string that represents the returned date:</span></span>

```csharp
[JsonPropertyName(Name="pushed_at")]
public string JsonDate { get; set; }

public DateTime LastPush =>
    DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
```

<span data-ttu-id="80d38-256">Verranno ora esaminati i nuovi costrutti appena definiti.</span><span class="sxs-lookup"><span data-stu-id="80d38-256">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="80d38-257">La proprietà `LastPush` viene definita utilizzando un *membro con corpo di espressione* per la funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="80d38-257">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="80d38-258">Non è presente alcuna funzione di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="80d38-258">There is no `set` accessor.</span></span> <span data-ttu-id="80d38-259">L'omissione della funzione di accesso `set` è la modalità di definizione di una proprietà C#di *sola lettura* in.</span><span class="sxs-lookup"><span data-stu-id="80d38-259">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="80d38-260">(Sì, è possibile creare proprietà di *sola scrittura* in C#, ma il relativo valore è limitato). Il metodo <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> analizza una stringa e crea un oggetto <xref:System.DateTime> usando un formato di data specificato e aggiunge metadati aggiuntivi al `DateTime` usando un oggetto `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="80d38-260">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="80d38-261">Se l'operazione di analisi ha esito negativo, la funzione di accesso della proprietà genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="80d38-261">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="80d38-262">Per usare <xref:System.Globalization.CultureInfo.InvariantCulture> sarà necessario aggiungere lo spazio dei nomi <xref:System.Globalization> alle istruzioni `using` in `repo.cs`:</span><span class="sxs-lookup"><span data-stu-id="80d38-262">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="80d38-263">Dopo aver aggiunto un'altra istruzione di output alla console, sarà possibile compilare ed eseguire nuovamente l'app:</span><span class="sxs-lookup"><span data-stu-id="80d38-263">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="80d38-264">La versione dell'app dovrebbe ora corrispondere all'[esempio completo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="80d38-264">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="80d38-265">Conclusione</span><span class="sxs-lookup"><span data-stu-id="80d38-265">Conclusion</span></span>

<span data-ttu-id="80d38-266">In questa esercitazione sono state descritte le procedure necessarie per eseguire richieste Web, analizzare i risultati e visualizzare le proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="80d38-266">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="80d38-267">Sono stati inoltre aggiunti nuovi pacchetti come dipendenze del progetto</span><span class="sxs-lookup"><span data-stu-id="80d38-267">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="80d38-268">e sono state illustrate alcune delle funzionalità del linguaggio C# che supportano tecniche orientate agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="80d38-268">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
