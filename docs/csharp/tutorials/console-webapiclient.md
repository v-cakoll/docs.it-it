---
title: Creare un client REST usando .NET Core
description: Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 0105db519f7accec6bf8bfbafdc6a67a444b1074
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249168"
---
# <a name="rest-client"></a><span data-ttu-id="b2bc0-103">Client REST</span><span class="sxs-lookup"><span data-stu-id="b2bc0-103">REST client</span></span>

<span data-ttu-id="b2bc0-104">Questa esercitazione illustra alcune funzionalità disponibili in .NET Core e nel linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-104">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="b2bc0-105">Verranno affrontati gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-105">You’ll learn:</span></span>

* <span data-ttu-id="b2bc0-106">Nozioni di base sull'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-106">The basics of the .NET Core CLI.</span></span>
* <span data-ttu-id="b2bc0-107">Panoramica delle funzionalità del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b2bc0-107">An overview of C# Language features.</span></span>
* <span data-ttu-id="b2bc0-108">Gestione delle dipendenze con NuGet</span><span class="sxs-lookup"><span data-stu-id="b2bc0-108">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="b2bc0-109">Comunicazioni HTTP</span><span class="sxs-lookup"><span data-stu-id="b2bc0-109">HTTP Communications</span></span>
* <span data-ttu-id="b2bc0-110">Elaborazione delle informazioni JSON</span><span class="sxs-lookup"><span data-stu-id="b2bc0-110">Processing JSON information</span></span>
* <span data-ttu-id="b2bc0-111">Gestione della configurazione con attributi</span><span class="sxs-lookup"><span data-stu-id="b2bc0-111">Managing configuration with Attributes.</span></span>

<span data-ttu-id="b2bc0-112">Si creerà un'applicazione che invia richieste HTTP a un servizio REST su GitHub,</span><span class="sxs-lookup"><span data-stu-id="b2bc0-112">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="b2bc0-113">si leggeranno informazioni in formato JSON e si convertirà il pacchetto JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-113">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="b2bc0-114">Si imparerà infine a usare e gestire oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-114">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="b2bc0-115">Ci sono molte caratteristiche in questo tutorial.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-115">There are many features in this tutorial.</span></span> <span data-ttu-id="b2bc0-116">numerose funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-116">Let’s build them one by one.</span></span>

<span data-ttu-id="b2bc0-117">Se si vuole proseguire, è possibile scaricare l'[esempio finale](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-117">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="b2bc0-118">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="b2bc0-118">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2bc0-119">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b2bc0-119">Prerequisites</span></span>

<span data-ttu-id="b2bc0-120">È necessario configurare il computer per l'esecuzione di .NET core.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-120">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="b2bc0-121">Le istruzioni di installazione sono disponibili nella pagina Download di .NET Core.You can find the installation instructions on the [.NET Core Downloads page.](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="b2bc0-121">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="b2bc0-122">Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-122">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="b2bc0-123">È necessario installare l'editor di codice preferito.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-123">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="b2bc0-124">Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma,</span><span class="sxs-lookup"><span data-stu-id="b2bc0-124">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="b2bc0-125">ma è possibile usare gli strumenti con cui si ha maggiore familiarità.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-125">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="b2bc0-126">Creare l'applicazione</span><span class="sxs-lookup"><span data-stu-id="b2bc0-126">Create the Application</span></span>

<span data-ttu-id="b2bc0-127">Il primo passaggio consiste nel creare una nuova applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-127">The first step is to create a new application.</span></span> <span data-ttu-id="b2bc0-128">Aprire un prompt dei comandi e creare una nuova directory per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="b2bc0-128">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="b2bc0-129">impostandola come directory corrente.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-129">Make that the current directory.</span></span> <span data-ttu-id="b2bc0-130">Immettere il comando seguente in una finestra della console:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-130">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="b2bc0-131">Questa operazione crea i file iniziali per un'applicazione "Hello World" di base.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-131">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="b2bc0-132">Il nome del progetto è "WebApiClient".</span><span class="sxs-lookup"><span data-stu-id="b2bc0-132">The project name is "WebApiClient".</span></span> <span data-ttu-id="b2bc0-133">Poiché si tratta di un nuovo progetto, nessuna delle dipendenze è presente.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-133">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="b2bc0-134">La prima esecuzione scaricherà il framework .NET Core, installerà un certificato di sviluppo ed eseguirà Gestione pacchetti NuGet per ripristinare le dipendenze mancanti.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-134">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="b2bc0-135">Prima di iniziare ad apportare modifiche, digitare `dotnet run` ([vedere la nota](#dotnet-restore-note)) al prompt dei comandi per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-135">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="b2bc0-136">`dotnet run` esegue automaticamente `dotnet restore` se nell'ambiente mancano dipendenze.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-136">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="b2bc0-137">Esegue anche `dotnet build` se l'applicazione deve essere ricompilata.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-137">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="b2bc0-138">Dopo l'installazione iniziale, sarà necessario solo eseguire `dotnet restore` o `dotnet build` quando ha senso per il progetto.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-138">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="b2bc0-139">Aggiunta di nuove dipendenze</span><span class="sxs-lookup"><span data-stu-id="b2bc0-139">Adding New Dependencies</span></span>

<span data-ttu-id="b2bc0-140">Uno degli obiettivi di progettazione principali di .NET Core è ridurre al minimo le dimensioni dell'installazione di .NET.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-140">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="b2bc0-141">Se per alcune delle funzionalità di un'applicazione sono necessarie altre librerie, è possibile aggiungere tali dipendenze al file di progetto C# (\*.csproj).</span><span class="sxs-lookup"><span data-stu-id="b2bc0-141">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="b2bc0-142">Per questo esempio, è necessario `System.Runtime.Serialization.Json` aggiungere il pacchetto, in modo che l'applicazione può elaborare le risposte JSON.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-142">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="b2bc0-143">Avrai bisogno del `System.Runtime.Serialization.Json` pacchetto per questa applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-143">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="b2bc0-144">Aggiungerlo al progetto eseguendo il comando [CLI .NET](../../core/tools/dotnet-add-package.md) seguente:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-144">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```dotnetcli
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="b2bc0-145">Esecuzione di richieste Web</span><span class="sxs-lookup"><span data-stu-id="b2bc0-145">Making Web Requests</span></span>

<span data-ttu-id="b2bc0-146">Si è ora pronti per iniziare a recuperare dati dal Web.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-146">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="b2bc0-147">In questa applicazione si leggeranno informazioni dall'[API GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="b2bc0-147">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="b2bc0-148">In particolare, si leggeranno informazioni sui progetti nell'ambito di [.NET Foundation](https://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="b2bc0-148">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="b2bc0-149">Si inizierà inviando all'API GitHub la richiesta di recuperare informazioni sui progetti.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-149">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="b2bc0-150">L'endpoint che verrà usato è: <https://api.github.com/orgs/dotnet/repos>.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-150">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="b2bc0-151">Poiché si vuole recuperare tutte le informazioni su questi progetti, si userà una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-151">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="b2bc0-152">Anche il browser usa richieste HTTP GET ed è quindi possibile incollare l'URL nel browser per visualizzare le informazioni che si riceveranno ed elaboreranno.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-152">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="b2bc0-153">Per eseguire richieste Web, usare la classe <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-153">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="b2bc0-154">Come tutte le API .NET moderne, <xref:System.Net.Http.HttpClient> supporta solo metodi asincroni per le API a esecuzione prolungata.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-154">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="b2bc0-155">È quindi necessario iniziare creando un metodo asincrono,</span><span class="sxs-lookup"><span data-stu-id="b2bc0-155">Start by making an async method.</span></span> <span data-ttu-id="b2bc0-156">che verrà inserito nell'implementazione mentre si compila la funzionalità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-156">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="b2bc0-157">Iniziare aprendo il file `program.cs` nella directory del progetto e aggiungendo il metodo seguente alla classe `Program`:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-157">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="b2bc0-158">È necessario aggiungere una `using` direttiva all'inizio del `Main` metodo in modo <xref:System.Threading.Tasks.Task> che il compilatore C ' riconosce il tipo:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-158">You'll need to add a `using` directive at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="b2bc0-159">Se si compila il progetto in questo momento, viene generato un avviso per indicare che il metodo non contiene alcun operatore `await` e verrà quindi eseguito in modo sincrono.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-159">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="b2bc0-160">Ignorare temporaneamente il messaggio. Si aggiungeranno operatori `await` durante la compilazione del metodo.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-160">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="b2bc0-161">Rinominare quindi lo spazio dei nomi definito nell'istruzione `namespace` sostituendo `ConsoleApp` (nome predefinito) con `WebAPIClient`.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-161">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="b2bc0-162">In questo spazio dei nomi si definirà in seguito una classe `repo`.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-162">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="b2bc0-163">Aggiornare quindi il metodo `Main` per chiamare questo metodo.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-163">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="b2bc0-164">Il `ProcessRepositories` metodo restituisce un'attività e non è necessario uscire dal programma prima del completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-164">The `ProcessRepositories` method returns a task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="b2bc0-165">Pertanto, è necessario `Main`modificare la firma di .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-165">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="b2bc0-166">Aggiungere `async` il modificatore e modificare `Task`il tipo restituito in .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-166">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="b2bc0-167">Quindi, nel corpo del metodo, aggiungere `ProcessRepositories`una chiamata a .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-167">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="b2bc0-168">Aggiungere `await` la parola chiave alla chiamata al metodo:Add the keyword to that method call:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-168">Add the `await` keyword to that method call:</span></span>

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="b2bc0-169">Si dispone a questo punto di un programma che, pur non eseguendo alcuna operazione, opera in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-169">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="b2bc0-170">È ora possibile migliorarlo.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-170">Let's improve it.</span></span>

<span data-ttu-id="b2bc0-171">È necessario innanzitutto un oggetto in grado di recuperare i dati dal Web; a tale scopo è possibile usare <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-171">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="b2bc0-172">per gestire la richiesta e le risposte.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-172">This object handles the request and the responses.</span></span> <span data-ttu-id="b2bc0-173">Creare un'istanza singola di `Program` tale tipo nella classe all'interno del *file di Program.cs.*</span><span class="sxs-lookup"><span data-stu-id="b2bc0-173">Instantiate a single instance of that type in the `Program` class inside the *Program.cs* file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="b2bc0-174">Tornare quindi al metodo `ProcessRepositories` e compilarne una prima versione:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-174">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="b2bc0-175">Sarà inoltre necessario aggiungere due `using` nuove direttive all'inizio del file per compilare:You'll need to also add two new directives at the top of the file for this to compile:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-175">You'll need to also add two new `using` directives at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="b2bc0-176">Questa prima versione esegue una richiesta Web per leggere l'elenco di tutti i repository presenti nell'organizzazione DotNet Foundation.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-176">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="b2bc0-177">L'ID di GitHub per .NET Foundation è 'dotnet'.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-177">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="b2bc0-178">Nelle prime righe l'oggetto <xref:System.Net.Http.HttpClient> viene impostato per questa richiesta, ma</span><span class="sxs-lookup"><span data-stu-id="b2bc0-178">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="b2bc0-179">prima viene configurato per accettare le risposte JSON di GitHub.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-179">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="b2bc0-180">Questo formato è semplicemente JSON.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-180">This format is simply JSON.</span></span> <span data-ttu-id="b2bc0-181">Nella riga successiva viene aggiunta un'intestazione Agente utente a tutte le richieste provenienti da questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-181">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="b2bc0-182">Queste due intestazioni vengono controllate dal codice server di GitHub e sono necessarie per recuperare informazioni da GitHub.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-182">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="b2bc0-183">Dopo aver configurato l'oggetto <xref:System.Net.Http.HttpClient>, si eseguirà una richiesta Web e si recupererà la risposta.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-183">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="b2bc0-184">In questa prima versione viene usato il metodo pratico <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-184">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="b2bc0-185">Questo metodo avvia un'attività che esegue la richiesta Web e, quando la richiesta viene restituita, legge il flusso di risposta e ne estrae il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-185">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="b2bc0-186">Il corpo della risposta viene restituito come <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-186">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="b2bc0-187">La stringa è disponibile quando l'attività viene completata.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-187">The string is available when the task completes.</span></span>

<span data-ttu-id="b2bc0-188">Le ultime due righe di questo metodo attendono che l'attività sia completata e visualizzano la risposta nella console.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-188">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="b2bc0-189">Compilare l'app ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-189">Build the app, and run it.</span></span> <span data-ttu-id="b2bc0-190">Il messaggio di avviso non viene più visualizzato perché `ProcessRepositories` contiene ora un operatore `await`.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-190">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="b2bc0-191">Verrà visualizzata una lunga schermata di testo JSON formattato.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-191">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="b2bc0-192">Elaborazione del risultato JSON</span><span class="sxs-lookup"><span data-stu-id="b2bc0-192">Processing the JSON Result</span></span>

<span data-ttu-id="b2bc0-193">A questo punto è stato scritto il codice per recuperare una risposta da un server Web e visualizzare il testo contenuto nella risposta.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-193">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="b2bc0-194">Si convertirà ora la risposta JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-194">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="b2bc0-195">La <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> classe serializza gli oggetti in JSON e deserializza JSON in oggetti.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-195">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="b2bc0-196">Iniziare definendo una classe `repo` per rappresentare l'oggetto JSON restituito dall'API GitHub:Start by defining a class to represent the JSON object returned from the GitHub API:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-196">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; }
    }
}
```

<span data-ttu-id="b2bc0-197">Inserire il codice precedente in un nuovo file denominato 'repo.cs'.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-197">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="b2bc0-198">Questa versione della classe rappresenta il percorso più semplice per elaborare dati JSON.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-198">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="b2bc0-199">Il nome della classe e il nome del membro corrispondono ai nomi usati nel pacchetto JSON, anziché alle convenzioni C# seguenti.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-199">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="b2bc0-200">Questo errore verrà risolto in un secondo momento specificando alcuni attributi di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-200">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="b2bc0-201">Questa classe dimostra un'altra caratteristica importante delle funzioni di serializzazione e deserializzazione JSON: non tutti i campi del pacchetto JSON fanno parte della classe.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-201">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="b2bc0-202">Il serializzatore JSON ignorerà le informazioni non incluse nel tipo di classe in uso.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-202">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="b2bc0-203">In questo modo sarà più semplice creare tipi compatibili con un solo subset dei campi presenti nel pacchetto JSON.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-203">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="b2bc0-204">Dopo aver creato il tipo, è possibile deserializzarlo.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-204">Now that you've created the type, let's deserialize it.</span></span>

<span data-ttu-id="b2bc0-205">Si userà infine il serializzatore per convertire i dati JSON in oggetti C#.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-205">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="b2bc0-206">Sostituire la <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> chiamata `ProcessRepositories` a nel metodo con le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-206">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
```

<span data-ttu-id="b2bc0-207">Si sta utilizzando un nuovo spazio dei nomi, quindi è necessario aggiungerlo anche all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-207">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="b2bc0-208">Si noti che ora viene usato <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> anziché <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-208">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="b2bc0-209">Il serializzatore usa un flusso anziché una stringa come origine.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-209">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="b2bc0-210">Diamo un'illustrazione di un paio di funzionalità del linguaggio C , che vengono utilizzati nella seconda riga del frammento di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-210">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="b2bc0-211">Il primo <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> argomento `await` di è un'espressione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-211">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="b2bc0-212">Gli altri due parametri sono facoltativi e vengono omessi nel frammento di codice. Le espressioni Await possono essere visualizzate quasi ovunque nel codice, anche se fino ad ora, sono state visualizzate solo come parte di un'istruzione di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-212">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="b2bc0-213">Il `Deserialize` metodo è *generico,* ovvero è necessario fornire argomenti di tipo per il tipo di oggetti da creare dal testo JSON.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-213">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="b2bc0-214">In questo esempio si esegue la `List<Repository>`deserializzazione in un <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>oggetto , che è un altro oggetto generico, il metodo .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-214">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2bc0-215">La `List<>` classe archivia un insieme di oggetti.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-215">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="b2bc0-216">L'argomento type dichiara il tipo `List<>`di oggetti archiviati nell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-216">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="b2bc0-217">Il testo JSON rappresenta una raccolta di oggetti `Repository`repo, pertanto l'argomento type è .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-217">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="b2bc0-218">Questa sezione è quasi completata.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-218">You're almost done with this section.</span></span> <span data-ttu-id="b2bc0-219">Ora che i dati JSON sono stati convertiti in oggetti C#, verrà visualizzato il nome di ogni repository.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-219">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="b2bc0-220">Sostituire le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-220">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="b2bc0-221">con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-221">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="b2bc0-222">Compilare l'applicazione ed eseguirla.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-222">Compile and run the application.</span></span> <span data-ttu-id="b2bc0-223">Verranno stampati i nomi dei repository che fanno parte di .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-223">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="b2bc0-224">Controllo della serializzazione</span><span class="sxs-lookup"><span data-stu-id="b2bc0-224">Controlling Serialization</span></span>

<span data-ttu-id="b2bc0-225">Prima di aggiungere altre funzionalità, `name` affrontiamo la `[JsonPropertyName]` proprietà utilizzando l'attributo .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-225">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="b2bc0-226">A questo scopo, eseguire le modifiche seguenti alla dichiarazione del campo `name` in repo.cs:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-226">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="b2bc0-227">Per `[JsonPropertyName]` usare l'attributo, <xref:System.Text.Json.Serialization> è necessario `using` aggiungere lo spazio dei nomi alle direttive:To use attribute, you need to add the namespace to the directives:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-227">To use `[JsonPropertyName]` attribute, you will need to add the <xref:System.Text.Json.Serialization> namespace to the `using` directives:</span></span>

```csharp
using System.Text.Json.Serialization;
```

<span data-ttu-id="b2bc0-228">Con questa operazione si modifica il codice che scrive il nome di ogni repository in program.cs:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-228">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="b2bc0-229">Eseguire `dotnet run` per assicurarsi di avere i mapping corretti.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-229">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="b2bc0-230">L'output ottenuto dovrebbe essere uguale a quello precedente.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-230">You should see the same output as before.</span></span>

<span data-ttu-id="b2bc0-231">Si apporterà di seguito un'ultima modifica prima di aggiungere nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-231">Let's make one more change before adding new features.</span></span> <span data-ttu-id="b2bc0-232">Il metodo `ProcessRepositories` può operare in modo asincrono e restituire una raccolta di repository.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-232">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="b2bc0-233">È ora necessario fare in modo che il metodo restituisca `List<Repository>` e spostare il codice che scrive le informazioni nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-233">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="b2bc0-234">Modificare la firma di `ProcessRepositories` in modo da restituire un'attività il cui risultato sia un elenco di oggetti `Repository`:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-234">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="b2bc0-235">Restituire quindi i repository dopo aver elaborato la risposta JSON:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-235">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="b2bc0-236">Il compilatore genera l'oggetto `Task<T>` come elemento restituito perché il metodo è stato contrassegnato come `async`.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-236">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="b2bc0-237">Si modificherà ora il metodo `Main` in modo che acquisisca i risultati e scriva ogni nome di repository nella console.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-237">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="b2bc0-238">Il metodo `Main` avrà ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-238">Your `Main` method now looks like this:</span></span>

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="b2bc0-239">Lettura di altre informazioni</span><span class="sxs-lookup"><span data-stu-id="b2bc0-239">Reading More Information</span></span>

<span data-ttu-id="b2bc0-240">Per completare l'esercitazione si elaboreranno ora altre proprietà del pacchetto JSON inviato dall'API di GitHub.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-240">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="b2bc0-241">Non si intende acquisire tutte le informazioni possibili ma, aggiungendo alcune proprietà, sarà possibile illustrare qualche altra funzionalità del linguaggio C#.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-241">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="b2bc0-242">Si inizierà aggiungendo altri tipi semplici alla definizione di classe `Repository`.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-242">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="b2bc0-243">Aggiungere quindi alla classe le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-243">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName("description")]
public string Description { get; set; }

[JsonPropertyName("html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName("homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName("watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="b2bc0-244">In queste proprietà sono incorporate conversioni dal tipo stringa (il contenuto dei pacchetti JSON) al tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-244">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="b2bc0-245">Il tipo <xref:System.Uri>, che per alcuni utenti può essere nuovo,</span><span class="sxs-lookup"><span data-stu-id="b2bc0-245">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="b2bc0-246">rappresenta un URI o, come in questo caso, un URL.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-246">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="b2bc0-247">Nel caso dei tipi `Uri` e `int`, se il pacchetto JSON contiene dati che non possono essere convertiti nel tipo di destinazione, l'azione di serializzazione genererà un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-247">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="b2bc0-248">Dopo aver aggiunto queste proprietà, aggiornare il metodo `Main` per visualizzare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-248">Once you've added these, update the `Main` method to display those elements:</span></span>

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

<span data-ttu-id="b2bc0-249">Come passaggio conclusivo si aggiungeranno le informazioni necessarie per l'ultima operazione push,</span><span class="sxs-lookup"><span data-stu-id="b2bc0-249">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="b2bc0-250">formattate nella risposta JSON come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-250">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="b2bc0-251">Tale formato è in formato UTC (Coordinated Universal <xref:System.DateTime> Time), pertanto si otterrà un valore la cui <xref:System.DateTime.Kind%2A> proprietà è <xref:System.DateTimeKind.Utc>.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-251">That format is in Coordinated Universal Time (UTC) so you'll get a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc>.</span></span> <span data-ttu-id="b2bc0-252">Se preferisci una data rappresentata nel tuo fuso orario, dovrai scrivere un metodo di conversione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-252">If you prefer a date represented in your time zone, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="b2bc0-253">Definire innanzitutto `public` una proprietà che conterrà la rappresentazione `Repository` UTC `LastPush` `readonly` della data e dell'ora nella classe e una proprietà che restituisce la data convertita nell'ora locale:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-253">First, define a `public` property that will hold the UTC representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns the date converted to local time:</span></span>

```csharp
[JsonPropertyName("pushed_at")]
public DateTime LastPushUtc { get; set; }

public DateTime LastPush => LastPushUtc.ToLocalTime();
```

<span data-ttu-id="b2bc0-254">Esaminiamo i nuovi costrutti che abbiamo appena definito.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-254">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="b2bc0-255">La `LastPush` proprietà viene definita utilizzando un membro `get` con corpo di *espressione* per la funzione di accesso.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-255">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="b2bc0-256">Non è presente alcuna funzione di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-256">There is no `set` accessor.</span></span> <span data-ttu-id="b2bc0-257">Omettendo `set` la funzione di accesso è come si definisce una proprietà di *sola lettura* in C .</span><span class="sxs-lookup"><span data-stu-id="b2bc0-257">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="b2bc0-258">È possibile creare anche proprietà di *sola scrittura* in C#, ma con un valore limitato.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-258">(Yes, you can create *write-only* properties in C#, but their value is limited.)</span></span>

<span data-ttu-id="b2bc0-259">Dopo aver aggiunto un'altra istruzione di output alla console, sarà possibile compilare ed eseguire nuovamente l'app:</span><span class="sxs-lookup"><span data-stu-id="b2bc0-259">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="b2bc0-260">La versione dell'app dovrebbe ora corrispondere all'[esempio completo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="b2bc0-260">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="b2bc0-261">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="b2bc0-261">Conclusion</span></span>

<span data-ttu-id="b2bc0-262">In questa esercitazione sono state descritte le procedure necessarie per eseguire richieste Web, analizzare i risultati e visualizzare le proprietà dei risultati.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-262">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="b2bc0-263">Sono stati inoltre aggiunti nuovi pacchetti come dipendenze del progetto</span><span class="sxs-lookup"><span data-stu-id="b2bc0-263">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="b2bc0-264">e sono state illustrate alcune delle funzionalità del linguaggio C# che supportano tecniche orientate agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="b2bc0-264">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
