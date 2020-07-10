---
title: Gestione e accesso ai dati
description: Informazioni su come accedere e gestire i dati in ASP.NET Web Form e Blazor .
author: csharpfritz
ms.author: jefritz
no-loc:
- Blazor
ms.date: 04/26/2020
ms.openlocfilehash: 4bf9bee21ce1db828dbe0aeb156d5e15cae4f703
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173304"
---
# <a name="work-with-data"></a><span data-ttu-id="cb1e6-103">Usare i dati</span><span class="sxs-lookup"><span data-stu-id="cb1e6-103">Work with data</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="cb1e6-104">L'accesso ai dati è la spina principale di un'app Web Form ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-104">Data access is the backbone of an ASP.NET Web Forms app.</span></span> <span data-ttu-id="cb1e6-105">Se si stanno creando moduli per il Web, cosa accade ai dati?</span><span class="sxs-lookup"><span data-stu-id="cb1e6-105">If you're building forms for the web, what happens to that data?</span></span> <span data-ttu-id="cb1e6-106">Con i Web Form, era possibile usare più tecniche di accesso ai dati per interagire con un database:</span><span class="sxs-lookup"><span data-stu-id="cb1e6-106">With Web Forms, there were multiple data access techniques you could use to interact with a database:</span></span>

- <span data-ttu-id="cb1e6-107">Data Sources</span><span class="sxs-lookup"><span data-stu-id="cb1e6-107">Data Sources</span></span>
- <span data-ttu-id="cb1e6-108">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="cb1e6-108">ADO.NET</span></span>
- <span data-ttu-id="cb1e6-109">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="cb1e6-109">Entity Framework</span></span>

<span data-ttu-id="cb1e6-110">Le origini dati erano controlli che potevano essere posizionati in una pagina Web Form e configurati come altri controlli.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-110">Data Sources were controls that you could place on a Web Forms page and configure like other controls.</span></span> <span data-ttu-id="cb1e6-111">Visual Studio fornisce un set di finestre di dialogo descrittivo per configurare e associare i controlli alle pagine Web Form.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-111">Visual Studio provided a friendly set of dialogs to configure and bind the controls to your Web Forms pages.</span></span> <span data-ttu-id="cb1e6-112">Gli sviluppatori che si occupano di un approccio "low code" o "No Code" preferiscono questa tecnica quando Web Forms è stato rilasciato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-112">Developers who enjoy a "low code" or "no code" approach preferred this technique when Web Forms was first released.</span></span>

![Data Sources](media/data/datasources.png)

<span data-ttu-id="cb1e6-114">ADO.NET è l'approccio di basso livello per l'interazione con un database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-114">ADO.NET is the low-level approach to interacting with a database.</span></span> <span data-ttu-id="cb1e6-115">Le app possono creare una connessione al database con comandi, recordset e set di dati per interagire.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-115">Your apps could create a connection to the database with Commands, Recordsets, and Datasets for interacting.</span></span> <span data-ttu-id="cb1e6-116">I risultati possono quindi essere associati a campi sullo schermo senza molto codice.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-116">The results could then be bound to fields on screen without much code.</span></span> <span data-ttu-id="cb1e6-117">Lo svantaggio di questo approccio consiste nel fatto che ogni set di oggetti ADO.NET ( `Connection` , `Command` e `Recordset` ) è stato associato alle librerie fornite da un fornitore di database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-117">The drawback of this approach was that each set of ADO.NET objects (`Connection`, `Command`, and `Recordset`) was bound to libraries provided by a database vendor.</span></span> <span data-ttu-id="cb1e6-118">L'utilizzo di questi componenti rendeva il codice rigido e difficile da migrare a un database diverso.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-118">Use of these components made the code rigid and difficult to migrate to a different database.</span></span>

## <a name="entity-framework"></a><span data-ttu-id="cb1e6-119">Entity Framework</span><span class="sxs-lookup"><span data-stu-id="cb1e6-119">Entity Framework</span></span>

<span data-ttu-id="cb1e6-120">Entity Framework (EF) è il Framework di mapping relazionale a oggetti open source gestito da .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-120">Entity Framework (EF) is the open source object-relational mapping framework maintained by the .NET Foundation.</span></span> <span data-ttu-id="cb1e6-121">Rilasciato inizialmente con .NET Framework, EF consente la generazione di codice per le connessioni al database, gli schemi di archiviazione e le interazioni.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-121">Initially released with .NET Framework, EF allows for generating code for the database connections, storage schemas, and interactions.</span></span> <span data-ttu-id="cb1e6-122">Con questa astrazione, è possibile concentrarsi sulle regole business dell'app e consentire la gestione del database da parte di un amministratore di database attendibile.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-122">With this abstraction, you can focus on your app's business rules and allow the database to be managed by a trusted database administrator.</span></span> <span data-ttu-id="cb1e6-123">In .NET Core è possibile usare una versione aggiornata di EF denominata EF Core.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-123">In .NET Core, you can use an updated version of EF called EF Core.</span></span> <span data-ttu-id="cb1e6-124">EF Core consente di generare e gestire le interazioni tra il codice e il database con una serie di comandi disponibili mediante lo `dotnet ef` strumento da riga di comando.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-124">EF Core helps generate and maintain the interactions between your code and the database with a series of commands that are available for you using the `dotnet ef` command-line tool.</span></span> <span data-ttu-id="cb1e6-125">Verranno ora esaminati alcuni esempi per iniziare a utilizzare un database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-125">Let's take a look at a few samples to get you working with a database.</span></span>

### <a name="ef-code-first"></a><span data-ttu-id="cb1e6-126">Code First EF</span><span class="sxs-lookup"><span data-stu-id="cb1e6-126">EF Code First</span></span>

<span data-ttu-id="cb1e6-127">Un modo rapido per iniziare a creare le interazioni con il database consiste nell'iniziare con gli oggetti classe che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-127">A quick way to get started building your database interactions is to start with the class objects you want to work with.</span></span> <span data-ttu-id="cb1e6-128">EF fornisce uno strumento che consente di generare il codice di database appropriato per le classi.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-128">EF provides a tool to help generate the appropriate database code for your classes.</span></span> <span data-ttu-id="cb1e6-129">Questo approccio è denominato sviluppo "Code First".</span><span class="sxs-lookup"><span data-stu-id="cb1e6-129">This approach is called "Code First" development.</span></span> <span data-ttu-id="cb1e6-130">Si consideri la `Product` classe seguente per un'app storefront di esempio che si vuole archiviare in un database relazionale come Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-130">Consider the following `Product` class for a sample storefront app that we want to store in a relational database like Microsoft SQL Server.</span></span>

```csharp
public class Product
{
    public int Id { get; set; }

    [Required]
    public string Name { get; set; }

    [MaxLength(4000)]
    public string Description { get; set; }

    [Range(0, 99999,99)]
    [DataType(DataType.Currency)]
    public decimal Price { get; set; }
}
```

<span data-ttu-id="cb1e6-131">Il prodotto include una chiave primaria e tre campi aggiuntivi che verranno creati nel database:</span><span class="sxs-lookup"><span data-stu-id="cb1e6-131">Product has a primary key and three additional fields that would be created in our database:</span></span>  

- <span data-ttu-id="cb1e6-132">EF identificherà la `Id` proprietà come chiave primaria per convenzione.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-132">EF will identify the `Id` property as a primary key by convention.</span></span>
- <span data-ttu-id="cb1e6-133">`Name`verranno archiviati in una colonna configurata per l'archiviazione di testo.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-133">`Name` will be stored in a column configured for text storage.</span></span> <span data-ttu-id="cb1e6-134">L' `[Required]` attributo che decora questa proprietà aggiunge un `not null` vincolo per consentire l'applicazione di questo comportamento dichiarato della proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-134">The `[Required]` attribute decorating this property will add a `not null` constraint to help enforce this declared behavior of the property.</span></span>
- <span data-ttu-id="cb1e6-135">`Description`verranno archiviati in una colonna configurata per l'archiviazione di testo e hanno una lunghezza massima configurata di 4000 caratteri, come stabilito dall' `[MaxLength]` attributo.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-135">`Description` will be stored in a column configured for text storage, and have a maximum length configured of 4000 characters as dictated by the `[MaxLength]` attribute.</span></span> <span data-ttu-id="cb1e6-136">Lo schema del database verrà configurato con una colonna denominata `MaxLength` utilizzando il tipo di dati `varchar(4000)` .</span><span class="sxs-lookup"><span data-stu-id="cb1e6-136">The database schema will be configured with a column named `MaxLength` using data type `varchar(4000)`.</span></span>
- <span data-ttu-id="cb1e6-137">La `Price` proprietà verrà archiviata come valuta.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-137">The `Price` property will be stored as currency.</span></span> <span data-ttu-id="cb1e6-138">L' `[Range]` attributo genererà vincoli appropriati per impedire l'archiviazione dei dati al di fuori dei valori minimo e massimo dichiarati.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-138">The `[Range]` attribute will generate appropriate constraints to prevent data storage outside of the minimum and maximum values declared.</span></span>

<span data-ttu-id="cb1e6-139">È necessario aggiungere questa `Product` classe a una classe del contesto del database che definisce le operazioni di connessione e conversione con il database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-139">We need to add this `Product` class to a database context class that defines the connection and translation operations with our database.</span></span>

```csharp
public class MyDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
}
```

<span data-ttu-id="cb1e6-140">La `MyDbContext` classe fornisce l'unica proprietà che definisce l'accesso e la traduzione per la `Product` classe.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-140">The `MyDbContext` class provides the one property that defines the access and translation for the `Product` class.</span></span>  <span data-ttu-id="cb1e6-141">L'applicazione configura questa classe per l'interazione con il database usando le voci seguenti nel `Startup` metodo della classe `ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="cb1e6-141">Your application configures this class for interaction with the database using the following entries in the `Startup` class's `ConfigureServices` method:</span></span>

```csharp
services.AddDbContext<MyDbContext>(options =>
    options.UseSqlServer("MY DATABASE CONNECTION STRING"));
```

<span data-ttu-id="cb1e6-142">Il codice precedente si connetterà a un database SQL Server con la stringa di connessione specificata.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-142">The preceding code will connect to a SQL Server database with the specified connection string.</span></span> <span data-ttu-id="cb1e6-143">È possibile inserire la stringa di connessione nel *appsettings.jssu* file, variabili di ambiente o altri percorsi di archiviazione della configurazione e sostituire questa stringa incorporata in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-143">You can place the connection string in your *appsettings.json* file, environment variables, or other configuration storage locations and replace this embedded string appropriately.</span></span>

<span data-ttu-id="cb1e6-144">È quindi possibile generare la tabella di database appropriata per questa classe usando i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb1e6-144">You can then generate the database table appropriate for this class using the following commands:</span></span>

```dotnetcli
dotnet ef migrations add 'Create Product table'
dotnet ef database update
```

<span data-ttu-id="cb1e6-145">Il primo comando definisce le modifiche apportate allo schema del database come nuova migrazione di EF denominata `Create Product table` .</span><span class="sxs-lookup"><span data-stu-id="cb1e6-145">The first command defines the changes you're making to the database schema as a new EF Migration called `Create Product table`.</span></span>  <span data-ttu-id="cb1e6-146">Una migrazione definisce come applicare e rimuovere le nuove modifiche del database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-146">A Migration defines how to apply and remove your new database changes.</span></span>

<span data-ttu-id="cb1e6-147">Una volta applicato, è presente una semplice `Product` tabella nel database e alcune nuove classi sono state aggiunte al progetto che consentono di gestire lo schema del database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-147">Once applied, you have a simple `Product` table in your database and some new classes added to the project that help manage the database schema.</span></span>  <span data-ttu-id="cb1e6-148">È possibile trovare queste classi generate, per impostazione predefinita, in una nuova cartella denominata *Migrations*.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-148">You can find these generated classes, by default, in a new folder called *Migrations*.</span></span>  <span data-ttu-id="cb1e6-149">Quando si apportano modifiche alla `Product` classe o si aggiungono altre classi correlate che si desidera interagire con il database, è necessario eseguire di nuovo i comandi della riga di comando con un nuovo nome della migrazione.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-149">When you make changes to the `Product` class or add more related classes you would like interacting with your database, you need to run the command-line commands again with a new name of the migration.</span></span>  <span data-ttu-id="cb1e6-150">Questo comando genererà un altro set di classi di migrazione per aggiornare lo schema del database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-150">This command will generate another set of migration classes to update your database schema.</span></span>

### <a name="ef-database-first"></a><span data-ttu-id="cb1e6-151">Database First EF</span><span class="sxs-lookup"><span data-stu-id="cb1e6-151">EF Database First</span></span>

<span data-ttu-id="cb1e6-152">Per i database esistenti, è possibile generare le classi per EF Core usando gli strumenti da riga di comando .NET.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-152">For existing databases, you can generate the classes for EF Core by using the .NET command-line tools.</span></span> <span data-ttu-id="cb1e6-153">Per eseguire l'impalcatura delle classi, usare una variante del comando seguente:</span><span class="sxs-lookup"><span data-stu-id="cb1e6-153">To scaffold the classes, use a variation of the following command:</span></span>

```dotnetcli
dotnet ef dbcontext scaffold "CONNECTION STRING" Microsoft.EntityFrameworkCore.SqlServer -c MyDbContext -t Product -t Customer
```

<span data-ttu-id="cb1e6-154">Il comando precedente si connette al database usando la stringa di connessione specificata e il `Microsoft.EntityFrameworkCore.SqlServer` provider.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-154">The preceding command connects to the database using the specified connection string and the `Microsoft.EntityFrameworkCore.SqlServer` provider.</span></span> <span data-ttu-id="cb1e6-155">Una volta stabilita la connessione, viene creata una classe del contesto del database denominata `MyDbContext` .</span><span class="sxs-lookup"><span data-stu-id="cb1e6-155">Once connected, a database context class named `MyDbContext` is created.</span></span> <span data-ttu-id="cb1e6-156">Vengono inoltre create le classi di supporto per `Product` le `Customer` tabelle e specificate con le `-t` Opzioni.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-156">Additionally, supporting classes are created for the `Product` and `Customer` tables that were specified with the `-t` options.</span></span> <span data-ttu-id="cb1e6-157">Sono disponibili molte opzioni di configurazione per questo comando per generare la gerarchia di classi appropriata per il database.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-157">There are many configuration options for this command to generate the class hierarchy appropriate for your database.</span></span> <span data-ttu-id="cb1e6-158">Per informazioni di riferimento complete, vedere [la documentazione del comando](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).</span><span class="sxs-lookup"><span data-stu-id="cb1e6-158">For a complete reference, see [the command's documentation](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).</span></span>

<span data-ttu-id="cb1e6-159">Ulteriori informazioni su [EF Core](/ef/core/) sono reperibili nel sito Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-159">More information about [EF Core](/ef/core/) can be found on the Microsoft Docs site.</span></span>

## <a name="interact-with-web-services"></a><span data-ttu-id="cb1e6-160">Interagire con i servizi Web</span><span class="sxs-lookup"><span data-stu-id="cb1e6-160">Interact with web services</span></span>

<span data-ttu-id="cb1e6-161">Quando ASP.NET è stato rilasciato per la prima volta, i servizi SOAP erano il modo migliore per scambiare dati tra i server Web e i client.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-161">When ASP.NET was first released, SOAP services were the preferred way for web servers and clients to exchange data.</span></span> <span data-ttu-id="cb1e6-162">La maggior parte delle modifiche è cambiata da quel momento e le interazioni preferite con i servizi sono state spostate verso le interazioni dirette del client HTTP.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-162">Much has changed since that time, and the preferred interactions with services have shifted to direct HTTP client interactions.</span></span> <span data-ttu-id="cb1e6-163">Con ASP.NET Core e Blazor , è possibile registrare la configurazione di `HttpClient` nel metodo della `Startup` classe `ConfigureServices` .</span><span class="sxs-lookup"><span data-stu-id="cb1e6-163">With ASP.NET Core and Blazor, you can register the configuration of your `HttpClient` in the `Startup` class's `ConfigureServices` method.</span></span> <span data-ttu-id="cb1e6-164">Usare tale configurazione quando è necessario interagire con l'endpoint HTTP.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-164">Use that configuration when you need to interact with the HTTP endpoint.</span></span> <span data-ttu-id="cb1e6-165">Si consideri il codice di configurazione seguente:</span><span class="sxs-lookup"><span data-stu-id="cb1e6-165">Consider the following configuration code:</span></span>

```csharp
services.AddHttpClient("github", client =>
{
    client.BaseAddress = new Uri("http://api.github.com/");
    // Github API versioning
    client.DefaultRequestHeaders.Add("Accept", "application/vnd.github.v3+json");
    // Github requires a user-agent
    client.DefaultRequestHeaders.Add("User-Agent", "BlazorWebForms-Sample");
});
```

<span data-ttu-id="cb1e6-166">Quando è necessario accedere ai dati da GitHub, creare un client con un nome `github` .</span><span class="sxs-lookup"><span data-stu-id="cb1e6-166">Whenever you need to access data from GitHub, create a client with a name of `github`.</span></span> <span data-ttu-id="cb1e6-167">Il client viene configurato con l'indirizzo di base e le intestazioni della richiesta sono impostate in modo appropriato.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-167">The client is configured with the base address, and the request headers are set appropriately.</span></span> <span data-ttu-id="cb1e6-168">Inserire i `IHttpClientFactory` nei Blazor componenti con la `@inject` direttiva o un `[Inject]` attributo in una proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-168">Inject the `IHttpClientFactory` into your Blazor components with the `@inject` directive or an `[Inject]` attribute on a property.</span></span> <span data-ttu-id="cb1e6-169">Creare il client denominato e interagire con i servizi usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="cb1e6-169">Create your named client and interact with services using the following syntax:</span></span>

```razor
@inject IHttpClientFactory factory

...

@code {
    protected override async Task OnInitializedAsync()
    {
        var client = factory.CreateClient("github");
        var response = await client.GetAsync("repos/dotnet/docs/issues");
        response.EnsureStatusCode();
        var content = async response.Content.ReadAsStringAsync();
    }
}
```

<span data-ttu-id="cb1e6-170">Questo metodo restituisce la stringa che descrive la raccolta di problemi nel repository GitHub *DotNet/docs* .</span><span class="sxs-lookup"><span data-stu-id="cb1e6-170">This method returns the string describing the collection of issues in the *dotnet/docs* GitHub repository.</span></span> <span data-ttu-id="cb1e6-171">Restituisce il contenuto in formato JSON e viene deserializzato in oggetti del problema GitHub appropriati.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-171">It returns content in JSON format and is deserialized into appropriate GitHub issue objects.</span></span> <span data-ttu-id="cb1e6-172">È possibile configurare `HttpClientFactory` per il recapito di oggetti preconfigurati in diversi modi `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="cb1e6-172">There are many ways that you can configure the `HttpClientFactory` to deliver preconfigured `HttpClient` objects.</span></span> <span data-ttu-id="cb1e6-173">Provare a configurare più `HttpClient` istanze con nomi ed endpoint diversi per i vari servizi Web con cui si lavora.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-173">Try configuring multiple `HttpClient` instances with different names and endpoints for the various web services you work with.</span></span> <span data-ttu-id="cb1e6-174">Questo approccio renderà le interazioni con i servizi più facili da usare in ogni pagina.</span><span class="sxs-lookup"><span data-stu-id="cb1e6-174">This approach will make your interactions with those services easier to work with on each page.</span></span> <span data-ttu-id="cb1e6-175">Per ulteriori informazioni, leggere [la documentazione relativa a IHttpClientFactory](/aspnet/core/fundamentals/http-requests).</span><span class="sxs-lookup"><span data-stu-id="cb1e6-175">For more details, read [the documentation for the IHttpClientFactory](/aspnet/core/fundamentals/http-requests).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cb1e6-176">[Precedente](forms-validation.md) 
> [Avanti](middleware.md)</span><span class="sxs-lookup"><span data-stu-id="cb1e6-176">[Previous](forms-validation.md)
[Next](middleware.md)</span></span>
