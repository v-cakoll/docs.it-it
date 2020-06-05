---
title: Gestione e accesso ai dati
description: Informazioni su come accedere e gestire i dati in ASP.NET Web Forms e blazer.
author: csharpfritz
ms.author: jefritz
ms.date: 04/26/2020
ms.openlocfilehash: b9805da60722de1b5d4f91107e856f647f7564a7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446476"
---
# <a name="work-with-data"></a>Usare i dati

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

L'accesso ai dati è la spina principale di un'app Web Form ASP.NET. Se si stanno creando moduli per il Web, cosa accade ai dati? Con i Web Form, era possibile usare più tecniche di accesso ai dati per interagire con un database:

- Data Sources
- ADO.NET
- Entity Framework

Le origini dati erano controlli che potevano essere posizionati in una pagina Web Form e configurati come altri controlli. Visual Studio fornisce un set di finestre di dialogo descrittivo per configurare e associare i controlli alle pagine Web Form. Gli sviluppatori che si occupano di un approccio "low code" o "No Code" preferiscono questa tecnica quando Web Forms è stato rilasciato per la prima volta.

![Data Sources](media/data/datasources.png)

ADO.NET è l'approccio di basso livello per l'interazione con un database. Le app possono creare una connessione al database con comandi, recordset e set di dati per interagire. I risultati possono quindi essere associati a campi sullo schermo senza molto codice. Lo svantaggio di questo approccio consiste nel fatto che ogni set di oggetti ADO.NET ( `Connection` , `Command` e `Recordset` ) è stato associato alle librerie fornite da un fornitore di database. L'utilizzo di questi componenti rendeva il codice rigido e difficile da migrare a un database diverso.

## <a name="entity-framework"></a>Entity Framework

Entity Framework (EF) è il Framework di mapping relazionale a oggetti open source gestito da .NET Foundation. Rilasciato inizialmente con .NET Framework, EF consente la generazione di codice per le connessioni al database, gli schemi di archiviazione e le interazioni. Con questa astrazione, è possibile concentrarsi sulle regole business dell'app e consentire la gestione del database da parte di un amministratore di database attendibile. In .NET Core è possibile usare una versione aggiornata di EF denominata EF Core. EF Core consente di generare e gestire le interazioni tra il codice e il database con una serie di comandi disponibili mediante lo `dotnet ef` strumento da riga di comando. Verranno ora esaminati alcuni esempi per iniziare a utilizzare un database.

### <a name="ef-code-first"></a>Code First EF

Un modo rapido per iniziare a creare le interazioni con il database consiste nell'iniziare con gli oggetti classe che si desidera utilizzare. EF fornisce uno strumento che consente di generare il codice di database appropriato per le classi. Questo approccio è denominato sviluppo "Code First". Si consideri la `Product` classe seguente per un'app storefront di esempio che si vuole archiviare in un database relazionale come Microsoft SQL Server.

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

Il prodotto include una chiave primaria e tre campi aggiuntivi che verranno creati nel database:  

- EF identificherà la `Id` proprietà come chiave primaria per convenzione.
- `Name`verranno archiviati in una colonna configurata per l'archiviazione di testo. L' `[Required]` attributo che decora questa proprietà aggiunge un `not null` vincolo per consentire l'applicazione di questo comportamento dichiarato della proprietà.
- `Description`verranno archiviati in una colonna configurata per l'archiviazione di testo e hanno una lunghezza massima configurata di 4000 caratteri, come stabilito dall' `[MaxLength]` attributo. Lo schema del database verrà configurato con una colonna denominata `MaxLength` utilizzando il tipo di dati `varchar(4000)` .
- La `Price` proprietà verrà archiviata come valuta. L' `[Range]` attributo genererà vincoli appropriati per impedire l'archiviazione dei dati al di fuori dei valori minimo e massimo dichiarati.

È necessario aggiungere questa `Product` classe a una classe del contesto del database che definisce le operazioni di connessione e conversione con il database.

```csharp
public class MyDbContext : DbContext
{
    public DbSet<Product> Products { get; set; }
}
```

La `MyDbContext` classe fornisce l'unica proprietà che definisce l'accesso e la traduzione per la `Product` classe.  L'applicazione configura questa classe per l'interazione con il database usando le voci seguenti nel `Startup` metodo della classe `ConfigureServices` :

```csharp
services.AddDbContext<MyDbContext>(options =>
    options.UseSqlServer("MY DATABASE CONNECTION STRING"));
```

Il codice precedente si connetterà a un database SQL Server con la stringa di connessione specificata. È possibile inserire la stringa di connessione nel file *appSettings. JSON* , nelle variabili di ambiente o in altri percorsi di archiviazione della configurazione e sostituire questa stringa incorporata in modo appropriato.

È quindi possibile generare la tabella di database appropriata per questa classe usando i comandi seguenti:

```dotnetcli
dotnet ef migrations add 'Create Product table'
dotnet ef database update
```

Il primo comando definisce le modifiche apportate allo schema del database come nuova migrazione di EF denominata `Create Product table` .  Una migrazione definisce come applicare e rimuovere le nuove modifiche del database.

Una volta applicato, è presente una semplice `Product` tabella nel database e alcune nuove classi sono state aggiunte al progetto che consentono di gestire lo schema del database.  È possibile trovare queste classi generate, per impostazione predefinita, in una nuova cartella denominata *Migrations*.  Quando si apportano modifiche alla `Product` classe o si aggiungono altre classi correlate che si desidera interagire con il database, è necessario eseguire di nuovo i comandi della riga di comando con un nuovo nome della migrazione.  Questo comando genererà un altro set di classi di migrazione per aggiornare lo schema del database.

### <a name="ef-database-first"></a>Database First EF

Per i database esistenti, è possibile generare le classi per EF Core usando gli strumenti da riga di comando .NET. Per eseguire l'impalcatura delle classi, usare una variante del comando seguente:

```dotnetcli
dotnet ef dbcontext scaffold "CONNECTION STRING" Microsoft.EntityFrameworkCore.SqlServer -c MyDbContext -t Product -t Customer
```

Il comando precedente si connette al database usando la stringa di connessione specificata e il `Microsoft.EntityFrameworkCore.SqlServer` provider. Una volta stabilita la connessione, viene creata una classe del contesto del database denominata `MyDbContext` . Vengono inoltre create le classi di supporto per `Product` le `Customer` tabelle e specificate con le `-t` Opzioni. Sono disponibili molte opzioni di configurazione per questo comando per generare la gerarchia di classi appropriata per il database. Per informazioni di riferimento complete, vedere [la documentazione del comando](/ef/core/miscellaneous/cli/dotnet#dotnet-ef-dbcontext-scaffold).

Ulteriori informazioni su [EF Core](/ef/core/) sono reperibili nel sito Microsoft docs.

## <a name="interact-with-web-services"></a>Interagire con i servizi Web

Quando ASP.NET è stato rilasciato per la prima volta, i servizi SOAP erano il modo migliore per scambiare dati tra i server Web e i client. La maggior parte delle modifiche è cambiata da quel momento e le interazioni preferite con i servizi sono state spostate verso le interazioni dirette del client HTTP. Con ASP.NET Core e blazer, è possibile registrare la configurazione di `HttpClient` nel metodo della `Startup` classe `ConfigureServices` . Usare tale configurazione quando è necessario interagire con l'endpoint HTTP. Si consideri il codice di configurazione seguente:

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

Quando è necessario accedere ai dati da GitHub, creare un client con un nome `github` . Il client viene configurato con l'indirizzo di base e le intestazioni della richiesta sono impostate in modo appropriato. Inserire l'oggetto `IHttpClientFactory` nei componenti di Blazer con la `@inject` direttiva o un `[Inject]` attributo in una proprietà. Creare il client denominato e interagire con i servizi usando la sintassi seguente:

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

Questo metodo restituisce la stringa che descrive la raccolta di problemi nel repository GitHub *DotNet/docs* . Restituisce il contenuto in formato JSON e viene deserializzato in oggetti del problema GitHub appropriati. È possibile configurare `HttpClientFactory` per il recapito di oggetti preconfigurati in diversi modi `HttpClient` . Provare a configurare più `HttpClient` istanze con nomi ed endpoint diversi per i vari servizi Web con cui si lavora. Questo approccio renderà le interazioni con i servizi più facili da usare in ogni pagina. Per ulteriori informazioni, leggere [la documentazione relativa a IHttpClientFactory](/aspnet/core/fundamentals/http-requests).

>[!div class="step-by-step"]
>[Precedente](forms-validation.md) 
> [Avanti](middleware.md)
