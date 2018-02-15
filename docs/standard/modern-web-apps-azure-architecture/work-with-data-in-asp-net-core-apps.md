---
title: Utilizzare i dati in app di ASP.NET Core
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | utilizzo dei dati in asp
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 648e0a4cdd388cf4a322f0fc049d5dcfca53d54b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="working-with-data-in-aspnet-core-apps"></a>Utilizzo dei dati nelle applicazioni ASP.NET Core

> "Dati un aspetto preziosi e durano più tempo rispetto a sistemi stessi".

Tim Berners-Lee

## <a name="summary"></a>Riepilogo

Accesso ai dati è una parte importante di quasi tutte le applicazioni software. ASP.NET Core supporta un'ampia gamma di opzioni di accesso a dati, tra cui Entity Framework Core (e anche Entity Framework 6) e può funzionare con qualsiasi accesso ai dati di .NET framework. La scelta dei quali accesso ai dati framework da utilizzare dipende dalle esigenze dell'applicazione. Fornire l'astrazione di tali scelte dai progetti ApplicationCore e l'interfaccia utente e incapsulare dettagli di implementazione nell'infrastruttura, consente di produrre verificabili regime di controllo software.

## <a name="entity-framework-core-for-relational-databases"></a>Entity Framework Core (per i database relazionali)

Se si sta scrivendo una nuova applicazione ASP.NET di base che deve essere utilizzato con dati relazionali, Entity Framework Core (Core EF) è il modo consigliato per l'applicazione di accedere ai relativi dati. EF Core è un mapping relazionale a oggetti (O/RM) che consente agli sviluppatori di .NET in modo permanente gli oggetti in e da un'origine dati. Elimina la necessità per la maggior parte degli sviluppatori in genere necessario scrivere il codice di accesso ai dati. Ad esempio ASP.NET Core, EF Core è stato riscritto da zero per le applicazioni multipiattaforma modulare di supporto. Aggiungerlo all'applicazione come pacchetto NuGet, configurarlo in avvio e richiesta tramite l'inserimento di dipendenze ovunque sia necessaria.

Per usare EF Core con un database di SQL Server, eseguire il comando CLI dotnet seguente:

dotnet aggiungere pacchetto Microsoft.EntityFrameworkCore.SqlServer

Per aggiungere il supporto per un'origine dati InMemory, per il test:

dotnet aggiungere pacchetto Microsoft.EntityFrameworkCore.InMemory

### <a name="the-dbcontext"></a>L'elemento DbContext

Per utilizzare i componenti di base di Entity Framework, è necessario una sottoclasse di DbContext. Questa classe contiene proprietà che rappresentano raccolte di entità a cui che l'applicazione funzionerà con. L'esempio eShopOnWeb include un CatalogContext con le raccolte per gli elementi, i marchi e i tipi:

```csharp
public class CatalogContext : DbContext
{
    public CatalogContext(DbContextOptions<CatalogContext> options) : base(options)
    {

    }

    public DbSet<CatalogItem> CatalogItems { get; set; }

    public DbSet<CatalogBrand> CatalogBrands { get; set; }

    public DbSet<CatalogType> CatalogTypes { get; set; }
}
```

Il DbContext deve avere un costruttore che accetta DbContextOptions e passare il costruttore DbContext base di questo argomento. Si noti che se si dispone di un solo elemento DbContext nell'applicazione, è possibile passare un'istanza di DbContextOptions, ma se dispone di più di un è necessario utilizzare il generico DbContextOptions<T> tipo, passando il tipo DbContext come parametro generico.

### <a name="configuring-ef-core"></a>Configurazione di Entity Framework Core

Nell'applicazione ASP.NET di base, si configurerà in genere EF Core nel metodo ConfigureServices. Componenti di base di Entity Framework Usa un DbContextOptionsBuilder, che supporta diversi metodi di estensione utili per semplificare la configurazione. Per configurare CatalogContext per utilizzare un database di SQL Server con una stringa di connessione definita nella configurazione, aggiungere il codice seguente per ConfigureServices:

```csharp
services.AddDbContext<CatalogContext>(options => options.UseSqlServer (Configuration.GetConnectionString("DefaultConnection")));
```

Per usare il database in memoria:

```csharp
services.AddDbContext<CatalogContext>(options =>
    options.UseInMemoryDatabase());
```

Dopo aver installato EF Core, un tipo figlio DbContext creato e configurato nel ConfigureServices, si è pronti per utilizzare componenti di base di Entity Framework. È possibile richiedere un'istanza del tipo DbContext in qualsiasi servizio che ha bisogno e iniziare a lavorare con le entità persistente utilizzando LINQ come se fossero semplicemente in una raccolta. Core EF esegue le operazioni di conversione di espressioni LINQ in query SQL per archiviare e recuperare i dati.

È possibile visualizzare le query è in esecuzione Core EF configurando un logger e garantire il livello è impostato su almeno informazioni, come illustrato nella figura 8-1.

![](./media/image8-1.png)

Figura 8-1 query di registrazione EF Core nella console

### <a name="fetching-and-storing-data"></a>Recupero e l'archiviazione dei dati

Per recuperare dati da Entity Framework Core, accedere alla proprietà appropriata e utilizzare LINQ per filtrare il risultato. È inoltre possibile utilizzare LINQ per eseguire proiezione, di trasformazione del risultato da un tipo a un altro. Nell'esempio seguente si recupererebbe CatalogBrands, ordinati per nome e filtrati per la proprietà Enabled proiettato su un tipo SelectListItem:

```csharp
var brandItems = await _context.CatalogBrands
    .Where(b => b.Enabled)
    .OrderBy(b => b.Name)
    .Select(b => new SelectListItem {
        Value = b.Id, Text = b.Name })
    .ToListAsync();
```

È importante nell'esempio precedente per aggiungere la chiamata a ToListAsync per eseguire immediatamente la query. In caso contrario, l'istruzione verrà assegnato un IQueryable<SelectListItem> a brandItems, che non verranno eseguiti finché viene enumerata. Esistono vantaggi e svantaggi nella restituzione di risultati IQueryable di metodi. Consente la query che verrà costruito EF Core per essere ulteriormente modificata, ma vengono anche restituiti errori che si verificano solo in fase di esecuzione, se le operazioni vengono aggiunti alla query che non è possibile convertire EF Core. È in genere preferibile passare tutti i filtri al metodo esegue l'accesso ai dati e restituire il backup di una raccolta in memoria (ad esempio, l'elenco<T>) come risultato.

Core EF tiene traccia delle modifiche alle entità che vengono recuperati dalla persistenza. Per salvare le modifiche a un'entità rilevata, chiamare semplicemente il metodo SaveChanges su DbContext, assicurandosi che è la stessa istanza di DbContext che è stata usata per recuperare l'entità. Aggiunta e rimozione di entità è direttamente sulla proprietà DbSet appropriata, con una chiamata al metodo SaveChanges per eseguire i comandi di database. Nell'esempio seguente viene aggiunta, aggiornamento e rimozione di entità dalla persistenza.

```csharp
// create
var newBrand = new CatalogBrand() { Brand = "Acme" };
_context.Add(newBrand);
await _context.SaveChangesAsync();

// read and update
var existingBrand = _context.CatalogBrands.Find(1);
existingBrand.Brand = "Updated Brand";
await _context.SaveChangesAsync();

// read and delete (alternate Find syntax)
var brandToDelete = _context.Find<CatalogBrand>(2);
_context.CatalogBrands.Remove(brandToDelete);
await _context.SaveChangesAsync();
```

Core EF supporta sia sincrono e i metodi asincroni per il recupero e il salvataggio. Nelle applicazioni web, si consiglia di utilizzare il modello async/await con i metodi asincroni, in modo che i thread del server web non vengono bloccati durante l'attesa di dati per completare le operazioni di accesso.

### <a name="fetching-related-data"></a>Recupero dei dati correlati

Quando EF Core recupera le entità, viene compilata tutte le proprietà che vengono archiviate direttamente con tale entità nel database. Le proprietà di navigazione, quali gli elenchi di entità correlate, non vengono popolate e può avere il valore impostato su null. In questo modo che core EF non recupera ulteriori dati superiore al necessario, che è particolarmente importante per applicazioni web, che rapidamente è necessario elaborare le richieste e restituire risposte in modo efficiente. Per includere le relazioni con un'entità mediante *caricamento eager*, per specificare la proprietà utilizzando il metodo di estensione di includere nella query, come illustrato:

```csharp
// .Include requires using Microsoft.EntityFrameworkCore
var brandsWithItems = await _context.CatalogBrands
    .Include(b => b.Items)
    .ToListAsync();
```

È possibile includere più relazioni, ed è anche possibile includere relazioni secondario utilizzando ThenInclude. Core EF eseguirà una singola query per recuperare il set di entità.

Per il caricamento dei dati correlati un'altra opzione consiste nell'utilizzare *caricamento esplicito*. Caricamento esplicito consente di caricare dati aggiuntivi in un'entità che è già stata recuperata. Poiché si prevede una richiesta separata al database, non è consigliabile per applicazioni web, che è consigliabile ridurre al minimo il numero di database eseguite per ogni richiesta di round trip.

*Caricamento lazy* è una funzionalità che consente di caricare automaticamente i dati correlati perché fa riferimento l'applicazione. Attualmente non è supportata da Entity Framework Core, ma come con il caricamento esplicito deve in genere essere disattivato per le applicazioni web.

### <a name="resilient-connections"></a>Connessioni resilienti

Risorse esterne quali database SQL in alcuni casi potrebbero essere disponibile. In caso di indisponibilità temporanea, le applicazioni è possono utilizzare logica di riesecuzione per evitare la generazione di un'eccezione. Questa tecnica è conosciuta come *resilienza delle connessioni*. È possibile implementare il [proprio tentativi con backoff esponenziale](https://docs.microsoft.com/azure/architecture/patterns/retry) tecnica mediante un tentativo di ripetizione con un tempo di attesa aumenta in modo esponenziale, fino a quando non è stato raggiunto un numero massimo di tentativi. Questa tecnica basata sul modello il fatto che le risorse cloud in modo intermittente siano disponibili per brevi periodi di tempo, causando un errore di alcune richieste.

Per il database di SQL Azure, Entity Framework Core fornisce già logica resilienza e tentativi di connessione database interno. Ma è necessario abilitare la strategia di esecuzione di Entity Framework per ogni connessione DbContext se si desidera disporre di connessioni Core EF resiliente.

Ad esempio, il codice seguente a livello di connessione Entity Framework Core consente connessioni SQL resilienti che vengono ripetute nel caso di connessione ha esito negativo.

```csharp
// Startup.cs from any ASP.NET Core Web API
public class Startup
{
    public IServiceProvider ConfigureServices(IServiceCollection services)
    {
        //...
        services.AddDbContext<OrderingContext>(options =>
        {
            options.UseSqlServer(Configuration["ConnectionString"],
            sqlServerOptionsAction: sqlOptions =>
        {
            sqlOptions.EnableRetryOnFailure(
            maxRetryCount: 5,
            maxRetryDelay: TimeSpan.FromSeconds(30), 
            errorNumbersToAdd: null); 
        });
    });
}
//...
```

  #### <a name="execution-strategies-and-explicit-transactions-using-begintransaction-and-multiple-dbcontexts"></a>Strategie di esecuzione e le transazioni esplicite utilizzando BeginTransaction e più DbContexts 
  
  Quando i tentativi sono abilitati nelle connessioni di Entity Framework Core, ogni operazione effettuata usando EF Core diventa il proprio possibilità di ritentare. Ogni query e ogni chiamata al metodo SaveChanges verrà ritentate come unità se si verifica un errore temporaneo.
  
  Tuttavia, se il codice avvia una transazione utilizzando BeginTransaction, si definisce un proprio gruppo di operazioni che devono essere trattati come un'unità, ovvero tutti gli elementi all'interno della transazione è essere sottoposta a rollback se si verifica un errore. Si verrà generata un'eccezione simile al seguente se si tenta di eseguire tale transazione quando si utilizza una strategia di esecuzione EF (criteri di ripetizione) e si includono più SaveChanges da più DbContexts in essa contenuti.

System. InvalidOperationException: La strategia di esecuzione configurata 'SqlServerRetryingExecutionStrategy' non supporta le transazioni avviate dall'utente. Utilizzare la strategia di esecuzione restituita da 'DbContext.Database.CreateExecutionStrategy()' per eseguire tutte le operazioni nella transazione come unità possibilità di ritentare.

La soluzione consiste nel richiamare manualmente la strategia di esecuzione EF con un delegato che rappresenta gli elementi che deve essere eseguito. Se si verifica un errore temporaneo, la strategia di esecuzione verrà nuovamente richiamare il delegato. Il codice seguente viene illustrato come implementare questo approccio:

```csharp
// Use of an EF Core resiliency strategy when using multiple DbContexts
// within an explicit transaction
// See:
// https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency
var strategy = _catalogContext.Database.CreateExecutionStrategy(); 
await strategy.ExecuteAsync(async () =>
{
    // Achieving atomicity between original Catalog database operation and the
    // IntegrationEventLog thanks to a local transaction
    using (var transaction = _catalogContext.Database.BeginTransaction())
    {
        _catalogContext.CatalogItems.Update(catalogItem);
        await _catalogContext.SaveChangesAsync();
        
        // Save to EventLog only if product price changed
        if (raiseProductPriceChangedEvent)
        await _integrationEventLogService.SaveEventAsync(priceChangedEvent);
        transaction.Commit();
    }
});
```

Il primo elemento DbContext è il \_catalogContext e il secondo elemento DbContext è all'interno di \_integrationEventLogService oggetto. Infine, il Commit di azione da eseguita più DbContexts e l'utilizzo di una strategia di esecuzione di Entity Framework.

> ### <a name="references--entity-framework-core"></a>Riferimenti: Entity Framework Core
> - **Documenti principali di Entity Framework**  
> <https://docs.microsoft.com/ef/>
> - **EF principale: Dati correlati**  
> <https://docs.microsoft.com/ef/core/querying/related-data>
> - **Evitare il caricamento Lazy entità nelle applicazioni ASP.NET**  
> <http://ardalis.com/avoid-lazy-loading-entities-in-asp-net-applications>

## <a name="ef-core-or-micro-orm"></a>Componenti di base EF o prodotto ORM micro?

EF Core è un'ottima scelta per la gestione di persistenza, mentre per la maggior parte incapsula i dettagli del database da parte degli sviluppatori dell'applicazione, non è l'unica scelta. È un'alternativa open source comuni [Dapper](https://github.com/StackExchange/Dapper), un cosiddetto prodotto ORM micro. Un prodotto ORM micro è un tipo semplice, meno strumento completo per il mapping di oggetti di strutture di dati. Nel caso di Dapper, la progettazione degli obiettivi di concentrarsi sulle prestazioni, anziché completamente incapsulamento sottostante sottoposto a query viene utilizzato per recuperare e aggiornare i dati. Poiché non astratto SQL da parte dello sviluppatore, Dapper "più vicino a metallo" e consente agli sviluppatori di scrivere la query da utilizzare per i dati di un determinata operazione di accedere.

Core EF dispone di due importanti funzionalità che fornisce che lo separano dal Dapper ma è aggiungere anche il relativo overhead delle prestazioni. Il primo è una conversione da LINQ. expressions in SQL. Queste conversioni vengono memorizzati nella cache, ma anche in questo caso è overhead durante la prima volta. Il secondo è rilevamento delle modifiche per le entità (in modo che le istruzioni update efficiente possono essere generate). Questo comportamento può essere disattivato per query specifiche tramite l'estensione AsNotTracking. Core EF genera anche le query SQL che in genere sono molto efficienti e in ogni caso è perfettamente accettabile dal punto di vista delle prestazioni, ma se è necessario maggiore controllo sulla query precisa deve essere eseguito, è possibile passare in SQL personalizzato (o eseguire una stored procedure) mediante EF Troppo Core. In questo caso, ancora Dapper supera EF Core, ma solo leggermente. Julie Lerman presenta alcuni dati sulle prestazioni nel proprio potrebbero articolo MSDN 2016 [Dapper, Entity Framework e App ibride](https://msdn.microsoft.com/magazine/mt703432.aspx). Dati aggiuntivi delle prestazioni benchmark per un'ampia gamma di metodi di accesso ai dati possono trovarsi in [il sito Dapper](https://github.com/StackExchange/Dapper).

Per vedere come la sintassi per Dapper varia da Entity Framework Core, tenere presenti queste due versioni dello stesso metodo per recuperare un elenco di elementi:

```csharp
// EF Core
private readonly CatalogContext _context;
public async Task<IEnumerable<CatalogType>> GetCatalogTypes()
{
    return await _context.CatalogTypes.ToListAsync();
}

// Dapper
private readonly SqlConnection _conn;
public async Task<IEnumerable<CatalogType>> GetCatalogTypesWithDapper()
{
    return await _conn.QueryAsync<CatalogType>("SELECT * FROM CatalogType");
}
```

Se è necessario compilare oggetti grafici più complessi con Dapper, è necessario scrivere la query associata (a differenza di aggiunta di un'inclusione esattamente come si farebbe Core EF). Questa è supportata tramite una varietà di sintassi, tra cui la funzione di Mapping che consente di eseguire il mapping di singole righe a più oggetti con mapping più. Ad esempio, specifica una classe Post con una proprietà del proprietario del tipo di utente, l'istruzione SQL seguente restituisce tutti i dati necessari:

```sql
select * from #Posts p
left join \#Users u on u.Id = p.OwnerId
Order by p.Id
```

Ogni riga restituita include dati utente e di Post. Poiché i dati utente dovrebbero essere collegati ai dati tramite la proprietà Owner Post, viene utilizzata la funzione seguente:

```csharp
(post, user) => { post.Owner = user; return post; }
```

Il listato di codice completo per restituire una raccolta di annunci con la proprietà Owner popolata con i dati utente associati sarebbe:

```csharp
var sql = @"select * from #Posts p
left join #Users u on u.Id = p.OwnerId
Order by p.Id";
var data = connection.Query<Post, User, Post>(sql,
(post, user) => { post.Owner = user; return post;});
```

In quanto offre meno incapsulamento, Dapper richiede gli sviluppatori saperne di più sull'archiviazione dei dati, come eseguire una query in modo efficiente e scrivere codice più per recuperarlo. Quando viene modificato il modello, anziché semplicemente la creazione di una nuova migrazione (un'altra funzionalità di base di Entity Framework) e/o l'aggiornamento delle informazioni di mapping in un'unica posizione in un elemento DbContext, è necessario aggiornare ogni query che è interessata. Queste query sono non compilazione ora garanzie, in modo che è possibile interrompere in runtime in risposta alle modifiche al modello o il database, rendendo più difficile rilevare rapidamente gli errori. In cambio di questi compromessi, Dapper offre prestazioni molto elevate.

Per la maggior parte delle applicazioni e la maggior parte delle parti di quasi tutte le applicazioni, componenti di base di Entity Framework offre prestazioni accettabili. Di conseguenza, i vantaggi di produttività per sviluppatori intendono genere superano il relativo overhead delle prestazioni. Per le query che possono trarre vantaggio dalla memorizzazione nella cache, l'effettiva query può essere eseguita solo una piccola percentuale di tempo, rendendo relativamente ridotto di query impostato HDR differenze di prestazioni.

## <a name="sql-or-nosql"></a>SQL o NoSQL

In genere, i database relazionali, ad esempio SQL Server sono dominato marketplace per l'archiviazione dei dati persistenti, ma non sono l'unica soluzione disponibile. Nei database NoSQL come [MongoDB](https://www.mongodb.com/what-is-mongodb) offrono un approccio diverso per l'archiviazione di oggetti. Anziché oggetti il mapping a tabelle e righe, un'altra opzione è per la serializzazione dell'intero oggetto grafico e memorizza il risultato. I vantaggi di questo approccio, almeno inizialmente, sono le prestazioni e alla semplicità. È certamente più semplice archiviare un singolo oggetto serializzato con una chiave rispetto al scomporre l'oggetto in molte tabelle con relazioni e aggiornamento e le righe che potrebbero essere modificate dall'ultima volta l'oggetto recupero dal database. Analogamente, il recupero e la deserializzazione di un singolo oggetto da un archivio basato su chiavi è in genere molto più veloce e più semplice che complesso join o più query di database necessarie per comporre completamente lo stesso oggetto da un database relazionale. La mancanza di blocchi o le transazioni o uno schema fisso rende inoltre database NoSQL molto adatti per la scalabilità su molti computer, che supporta i set di dati molto grandi.

D'altra parte, nei database NoSQL (come in genere vengono definite) hanno svantaggi. Database relazionali Usa la normalizzazione per garantire la coerenza ed evitare la duplicazione di dati. Ciò riduce le dimensioni totali del database e si assicura che gli aggiornamenti ai dati condivisi sono disponibili immediatamente in tutto il database. In un database relazionale, una tabella di indirizzi potrebbe fare riferimento una tabella paese dall'ID, in modo che se il nome di un paese sono stato modificato, i record degli indirizzi può costituire un vantaggio rispetto all'aggiornamento di non dover essere aggiornati. Tuttavia, in un database NoSQL, indirizzo e il paese associato potrebbe essere serializzato come parte di molti degli oggetti archiviati. Tali oggetti da aggiornare, anziché una singola riga richiede un aggiornamento di un nome di paese. Database relazionali possono inoltre garantire l'integrità relazionale tramite l'applicazione delle regole, come chiavi esterne. Nei database NoSQL non offrono in genere i vincoli per i propri dati.

Complessità di un altro NoSQL devono gestire i database è il controllo delle versioni. Quando modificare proprietà di un oggetto, potrebbe non essere in grado di deserializzare dalle versioni precedenti che sono state archiviate. Di conseguenza, è necessario aggiornare tutti gli oggetti esistenti con una versione (precedente) serializzata dell'oggetto per rispettare il nuovo schema. Questo non è concettualmente diverso da un database relazionale, in cui modifiche dello schema talvolta richiedono script di aggiornamento o il mapping degli aggiornamenti. Tuttavia, il numero di voci che deve essere modificato è spesso molto maggiore nell'approccio NoSQL, poiché non esiste più di duplicazione dei dati.

È possibile nei database NoSQL di archiviare più versioni di oggetti, database relazionali di uno schema fisso che non è in genere supportano. Tuttavia, in questo caso il codice dell'applicazione sarà necessario tenere conto per l'esistenza delle versioni precedenti di oggetti, l'aggiunta di complessità.

In genere nei database NoSQL non applicano [ACID](http://en.wikipedia.org/wiki/ACID), ovvero presentano vantaggi di prestazioni e scalabilità su database relazionali. Si tratta di ideale per grandi set di dati e gli oggetti che non sono particolarmente adatti per l'archiviazione nelle strutture tabella normalizzata. Non è necessario perché una singola applicazione non è possibile trarre vantaggio da entrambi relazionale e nei database NoSQL, con ogni in cui è preferibile adatto.

## <a name="azure-documentdb"></a>Azure DocumentDB

Azure DocumentDB è un servizio di database NoSQL completamente gestito che offre l'archiviazione di dati privi di schema basato su cloud. DocumentDB è stato compilato per prestazioni rapida e prevedibile, la disponibilità elevata, scalabilità elastica e distribuzione globale. Nonostante sia un database NoSQL, gli sviluppatori possono utilizzare rich e familiare funzionalità di query SQL sui dati JSON. Tutte le risorse in DocumentDB vengono archiviate come documenti JSON. Le risorse vengono gestite come *elementi*, che sono documenti che contengono i metadati, e *feed*, che sono raccolte di elementi. Figura 8-2 viene illustrata la relazione tra le diverse risorse di DocumentDB.


![La relazione gerarchica tra le risorse di DocumentDB, un database NoSQL JSON](./media/image8-2.png)

**Figura 8-2.** Organizzazione di risorse di DocumentDB.

Il linguaggio di query di DocumentDB è un'interfaccia semplice e potente per eseguire query sui documenti JSON. Il linguaggio supporta un sottoinsieme di grammatica SQL ANSI e aggiunge l'integrazione di oggetti, matrici, la costruzione di oggetti e chiamata di funzione JavaScript.

**Riferimenti: DocumentDB**

-   DocumentDB Introduction\
    <https://docs.microsoft.com/azure/documentdb/documentdb-introduction>

## <a name="other-persistence-options"></a>Altre opzioni di persistenza

Oltre ai dati relazionali e le opzioni di archiviazione di database NoSQL, applicazioni ASP.NET Core consente di archiviazione di Azure per archiviare una varietà di formati di dati e i file in modo scalabile e basate su cloud. Archiviazione di Azure è altamente scalabile, pertanto è possibile avviare out archiviare piccole quantità di dati e la scala fino a archiviazione centinaia di terabyte, se richiesto dall'applicazione. Archiviazione di Azure supporta quattro tipi di dati:

-   Archiviazione BLOB di testo non strutturato o archiviazione binario, detta anche archiviazione di oggetti.

-   Archiviazione tabelle per set di dati strutturati, accessibile tramite chiavi di riga.

-   Archiviazione delle code di messaggistica affidabile basata su coda.

-   L'archiviazione dei file per l'accesso a file condivisi tra macchine virtuali di Azure e applicazioni locali.

**Riferimenti: archiviazione di Azure**

-   Introduction\ di archiviazione di Azure
    <https://docs.microsoft.com/azure/storage/storage-introduction>

## <a name="caching"></a>Memorizzazione nella cache

Nelle applicazioni web, ogni richiesta web deve essere completata in minor tempo possibile. Un modo per ottenere questo risultato consiste nel limitare il numero di chiamate esterne, che il server è necessario apportare per completare la richiesta. La memorizzazione nella cache comporta l'archiviazione di una copia dei dati nel server o un altro archivio dati che è più facilmente sottoposti a query di origine dei dati. Applicazioni Web e soprattutto le applicazioni web tradizionali non SPA, necessario compilare l'intera interfaccia utente per ogni richiesta. Questo comporta spesso l'esecuzione di molte delle stesse query di database ripetutamente da una richiesta di un utente al successivo. Nella maggior parte dei casi, questo dati vengono modificati raramente, pertanto non c'è motivo di richiederla costantemente dal database. ASP.NET Core supporta la memorizzazione nella cache risposta, per la memorizzazione nella cache intere pagine e la memorizzazione nella cache di dati, che supporta il comportamento di memorizzazione nella cache più granulare.

Quando si implementa la memorizzazione nella cache, è importante tenere separazione presente delle problematiche. Evitare di implementazione della logica di memorizzazione nella cache della logica di accesso ai dati o in un'interfaccia utente. Incapsulare la memorizzazione nella cache nelle proprie classi e utilizzare una configurazione per gestire il comportamento. Si attiene ai aperto o chiuso e i principi unica responsabilità e renderà più facile per gestire l'utilizzo di memorizzazione nella cache nell'applicazione di si sviluppa.

### <a name="aspnet-core-response-caching"></a>La memorizzazione nella cache di ASP.NET Core risposta

ASP.NET Core supporta due livelli di memorizzazione nella cache di risposta. Il primo livello non memorizzare nella cache qualsiasi elemento nel server, ma aggiunge le intestazioni HTTP che indicano i client e server proxy per memorizzare risposte. Ciò viene implementato, aggiungere l'attributo ResponseCache ai singoli controller o azioni:

```csharp
    [ResponseCache(Duration = 60)]
    public IActionResult Contact()
    { }
    
    ViewData["Message"] = "Your contact page.";
    return View();
}

The above example will result in the following header being added to the response, instructing clients to cache the result for up to 60 seconds.

Cache-Control: public,max-age=60

In order to add server-side in-memory caching to the application, you must reference the Microsoft.AspNetCore.ResponseCaching NuGet package, and then add the Response Caching middleware. This middleware is configured in both ConfigureServices and Configure in Startup:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddResponseCaching();
}

public void Configure(IApplicationBuilder app)
{
    app.UseResponseCaching();
}
```

Il Middleware di memorizzazione nella cache della risposta verrà automaticamente nella cache le risposte in base a un set di condizioni, che è possibile personalizzare. Per impostazione predefinita, vengono memorizzati nella cache le risposte solo 200 (OK), richieste tramite i metodi GET o HEAD. Inoltre, le richieste devono avere una risposta con una Cache-Control: intestazione pubblica e non può includere le intestazioni per l'autorizzazione o Set-Cookie. Vedere un [elenco completo delle condizioni memorizzazione nella cache utilizzato dalla risposta la memorizzazione nella cache middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware#conditions-for-caching).

### <a name="data-caching"></a>Memorizzazione di dati

Anziché (o in aggiunta a) la memorizzazione nella cache le risposte dei web completo, è possibile memorizzare nella cache i risultati delle query di dati singoli. A tale scopo, è possibile utilizzare la memorizzazione nella cache sul server web o usare [una cache distribuita](https://docs.microsoft.com/aspnet/core/performance/caching/distributed). In questa sezione verrà illustrato come implementare in memoria la memorizzazione nella cache.

Aggiungere il supporto per la memoria (o distribuita) la memorizzazione nella cache in ConfigureServices:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMemoryCache();
    services.AddMvc();
}
```

Assicurarsi di aggiungere anche il pacchetto Microsoft.Extensions.Caching.Memory NuGet.

Dopo aver aggiunto il servizio, richiesta IMemoryCache tramite l'inserimento di dipendenze ogni volta che è necessario accedere alla cache. In questo esempio, il CachedCatalogService viene usato il modello di progettazione Proxy (o un elemento Decorator), fornendo un'implementazione alternativa del ICatalogService che controlla l'accesso a (o comportamento aggiunge) l'implementazione di CatalogService sottostante.

```csharp
public class CachedCatalogService : ICatalogService
{
    private readonly IMemoryCache _cache;
    private readonly CatalogService _catalogService;
    private static readonly string _brandsKey = "brands";
    private static readonly string _typesKey = "types";
    private static readonly string _itemsKeyTemplate = "items-{0}-{1}-{2}-{3}";
    private static readonly TimeSpan _defaultCacheDuration = TimeSpan.FromSeconds(30);
    public CachedCatalogService(IMemoryCache cache,
    CatalogService catalogService)
    {
        _cache = cache;
        _catalogService = catalogService;
    }
    
    public async Task<IEnumerable<SelectListItem>> GetBrands()
    {
        return await _cache.GetOrCreateAsync(_brandsKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetBrands();
        });
    }
    
    public async Task<Catalog> GetCatalogItems(int pageIndex, int itemsPage, int? brandID, int? typeId)
    {
        string cacheKey = String.Format(_itemsKeyTemplate, pageIndex, itemsPage, brandID, typeId);
        return await _cache.GetOrCreateAsync(cacheKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetCatalogItems(pageIndex, itemsPage, brandID, typeId);
        });
    }
    
    public async Task<IEnumerable<SelectListItem>> GetTypes()
    {
        return await _cache.GetOrCreateAsync(_typesKey, async entry =>
        {
            entry.SlidingExpiration = _defaultCacheDuration;
            return await _catalogService.GetTypes();
        });
    }
}
```

Per configurare l'applicazione di utilizzare la versione memorizzata nella cache del servizio, ma consentono ancora il servizio per l'istanza di CatalogService necessarie nel relativo costruttore, è necessario aggiungere quanto segue in ConfigureServices:

```csharp
services.AddMemoryCache();
services.AddScoped<ICatalogService, CachedCatalogService>();
services.AddScoped<CatalogService>();
```

A questo punto, le chiamate del database per recuperare i dati del catalogo verranno effettuate solo una volta al minuto, piuttosto che a ogni richiesta. In base al traffico al sito, questo può avere un impatto significativo sul numero di query eseguite per il database e il tempo medio di caricamento per la home page che attualmente dipende tutte e tre le query esposti da questo servizio.

È un problema che si verifica quando viene implementata la memorizzazione nella cache *dati non aggiornati* –, ovvero i dati modificati in una versione aggiornata, ma l'origine rimangono nella cache. Un modo semplice per risolvere questo problema è utilizzare la durata della cache piccola, poiché per un'applicazione occupata è limitato benefici per estendere la lunghezza dei dati viene memorizzato nella cache. Si consideri ad esempio una pagina che esegue una query di singolo database, e viene richiesto di 10 volte al secondo. Se questa pagina viene memorizzato nella cache per un minuto, si verificherà il numero di query di database eseguite al minuto per eliminare da 600 a una riduzione 99,8% 1. Se invece la durata della cache sono stata apportata a un'ora, la riduzione complessiva sarebbe 99.997%, ma ora l'età di probabilità e il potenziale di dati non aggiornati sono entrambi aumenta notevolmente.

Un altro approccio consiste nel rimuovere in modo proattivo le voci della cache quando vengono aggiornati i dati in che essi contenuti. Qualsiasi singola voce può essere rimossa se si conosce la chiave:

```csharp
_cache.Remove(cacheKey);
```

Se l'applicazione espone la funzionalità per l'aggiornamento delle voci che memorizza nella cache, è possibile rimuovere le voci della cache corrispondente nel codice che esegue gli aggiornamenti. In alcuni casi potrebbero essere presenti numerose voci diverse che dipendono da un particolare set di dati. In tal caso, può essere utile creare dipendenze tra le voci della cache, utilizzando un CancellationChangeToken. Con un CancellationChangeToken, è possibile far scadere più voci nella cache in una sola volta per il token di annullamento.

```csharp
// configure CancellationToken and add entry to cache
var cts = new CancellationTokenSource();
_cache.Set("cts", cts);
_cache.Set(cacheKey,
itemToCache,
new CancellationChangeToken(cts.Token));

// elsewhere, expire the cache by cancelling the token\
_cache.Get<CancellationTokenSource>("cts").Cancel();
```

>[!div class="step-by-step"]
[Precedente] [Avanti] (test-asp-net-core-mvc-apps.md) (develop-asp-net-core-mvc-apps.md)
