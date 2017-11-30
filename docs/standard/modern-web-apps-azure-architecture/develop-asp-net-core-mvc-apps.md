---
title: Sviluppo di applicazioni MVC ASP.NET Core
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | lo sviluppo di App di MVC ASP.NET Core
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 54e7ed6fff9ac709e411d0ac1e345c63fd753201
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a>Sviluppare applicazioni MVC ASP.NET Core

> "Non è importante capire la prima volta. È estremamente importante da capire l'ultima volta".  
> _-Andrew risposta e David Thomas_

## <a name="summary"></a>Riepilogo

ASP.NET Core è un framework multipiattaforma, open source per la compilazione di applicazioni web moderne ottimizzato su cloud. Le app di ASP.NET Core sono lightweight e modulari, con supporto incorporato per l'inserimento di dipendenze, consentendo maggiore testabilità e gestibilità. Combinata con MVC, che supporta la creazione di API web moderna oltre alle applicazioni basate su Vista, ASP.NET Core è un framework potente con il quale la creazione di applicazioni web aziendali.

## <a name="mapping-requests-to-responses"></a>Mapping tra le richieste e risposte

Essenzialmente, App ASP.NET Core mappare le richieste in ingresso per le risposte in uscita. Un livello basso, questa operazione viene eseguita con middleware e semplici applicazioni ASP.NET Core e microservizi possono essere costituito esclusivamente middleware personalizzato. Quando si utilizza ASP.NET MVC di base, è possibile utilizzare un livello leggermente più elevato, pensare in termini di *route*, *controller*, e *azioni*. Ogni richiesta in ingresso viene confrontato con la tabella di routing dell'applicazione e se viene trovata una route corrispondente, il metodo di azione associato (appartenente a un controller) viene chiamato per gestire la richiesta. Se non viene trovata alcuna route corrispondente, viene chiamato un gestore degli errori (in questo caso, restituire un risultato non trovato).

Le applicazioni MVC ASP.NET Core è possono utilizzare le route convenzionale, route di attributi o entrambi. Route convenzionale sono definite nel codice, che specifica il routing *convenzioni* utilizzando una sintassi come nell'esempio seguente:

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

In questo esempio, una route denominata "default" è stato aggiunto alla tabella di routing. Definisce un modello di route con segnaposto per *controller*, *azione*, e *id*. I segnaposto di azione e del controller sono predefinito specificato ("Home" e "Index", rispettivamente), e il segnaposto dell'id è facoltativo (in virtù di un "?" applicata). La convenzione definite qui gli Stati che la prima parte di una richiesta deve corrispondere al nome del controller, la seconda parte, all'azione e quindi se è necessaria una terza parte rappresenterà un parametro di tipo id. Le route convenzionale sono in genere definite in un'unica posizione per l'applicazione, come nel metodo configura la classe di avvio.

Route di attributi vengono applicate a controller e azioni direttamente, anziché specificate a livello globale. Questo ha il vantaggio di renderli risulta molto più facilmente individuabile quando si cerca un metodo specifico, ma significa che le informazioni di routing non viene mantenute in un'unica posizione nell'applicazione. Route di attributo, è facilmente possibile specificare più route per una determinata azione, nonché combinare le route tra i controller e azioni. Ad esempio:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

Le route possono essere specificate in [HttpGet] e separano attributi simili, evitando la necessità di aggiungere [Route\] attributi. Route di attributi possono inoltre utilizzare i token per ridurre la necessità di ripetere i nomi di controller o un'azione, come illustrato di seguito:

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

Una volta che una determinata richiesta è stata trovata per una route, ma prima dell'azione metodo viene chiamato, ASP.NET MVC Core eseguirà [associazione del modello](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) e [la convalida del modello](https://docs.microsoft.com/aspnet/core/mvc/models/validation) nella richiesta. Associazione di modelli è responsabile della conversione dei dati HTTP in ingresso nei tipi .NET specificati come parametri del metodo di azione da chiamare. Ad esempio, se il metodo di azione che prevede un parametro di id int, l'associazione di modelli tenterà di utilizzare questo parametro da un valore fornito come parte della richiesta. A tale scopo, l'associazione di modelli Cerca valori in un form pubblicato, i valori della route se stesso e i valori di stringa di query. Se che viene trovato un valore di id, verrà convertito in un intero prima di essere passata al metodo di azione.

Dopo l'associazione del modello, ma prima di chiamare il metodo di azione, si verifica la convalida del modello. Convalida del modello utilizza gli attributi facoltativi nel tipo di modello e contribuisce a garantire che l'oggetto modello fornito sia conforme ai requisiti determinati dati. Alcuni valori possono essere specificati come richiesto, o limitate a un determinato intervallo numerico o di lunghezza, e così via. Se vengono specificati gli attributi di convalida, ma il modello non è conforme ai relativi requisiti, la proprietà ModelState.IsValid è false e il set di regole di convalida non sarà disponibile per l'invio al client che effettua la richiesta.

Se si utilizza la convalida del modello, è necessario verificare sempre che il modello sia valido prima di eseguire i comandi di modifica dello stato, per garantire che l'applicazione non sia danneggiato da dati non validi. È possibile utilizzare un [filtro](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) per evitare la necessità di aggiungere il codice per questo oggetto per ogni azione. Filtri MVC ASP.NET Core offrono un metodo di intercettazione delle richieste, i gruppi in modo che i criteri comuni e i problemi di montaggio incrociato possono essere applicati in base a una destinazione. Filtri possono essere applicati alle singole azioni, intero controller, o a livello globale per un'applicazione.

Per le API web, ASP.NET MVC di base supporta [ *negoziazione del contenuto*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), che consente le richieste specificare la modalità di formattazione di risposte. In base alle intestazioni fornite nella richiesta, la restituzione di dati di azioni formatterà la risposta in XML, JSON o un altro formato supportato. Questa funzionalità consente la stessa API utilizzabile da più client con i requisiti per il formato dati diverso.

> ### <a name="references--mapping-requests-to-responses"></a>Riferimenti: mapping tra le richieste e risposte
> - **Routing per Controller azioni**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **Associazione del modello** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding
> - **La convalida del modello**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **I filtri** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters

## <a name="working-with-dependencies"></a>Utilizzo di dipendenze

ASP.NET di base include il supporto incorporato per e utilizza internamente una tecnica nota come [inserimento di dipendenze](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection). Inserimento di dipendenze è una tecnica che abilitato accoppiamento debole tra parti diverse di un'applicazione. Rigida è consigliabile, perché rende più semplice isolare le parti dell'applicazione, consentendo di test o di sostituzione. Rende inoltre meno probabile che una modifica in una parte dell'applicazione avrà un impatto imprevisto in un'altra posizione nell'applicazione. Inserimento di dipendenze si basa sul principio di inversione della dipendenza e viene spesso chiave per ottenere il principio di apertura/chiusura. Prestare attenzione quando si valuta il funzionamento dell'applicazione con le relative dipendenze, di [adesive statico](http://deviq.com/static-cling/) codice odore e memorizza il aphorism "[nuovo è glue](http://ardalis.com/new-is-glue)."

Adesive statico si verifica quando le classi di effettuano chiamate ai metodi statici o accedere a proprietà statiche, che presentano effetti collaterali o dipendenze dall'infrastruttura. Ad esempio, se si dispone di un metodo che chiama un metodo statico, che a sua volta scrive in un database, il metodo è strettamente al database. Tutto ciò che si interrompe la chiamata al database interromperà il metodo. Tali metodi di test è notoriamente difficile, poiché tali test richiedono commerciale librerie di simulazione per simulare le chiamate statiche oppure può essere testato solo con un database di prova sul posto. Chiamate statiche che non dispongono di qualsiasi dipendenza infrastruttura, specialmente quelle che sono completamente indipendenti dallo stato, sono supportate chiamare e avere alcun impatto su accoppiamento o testabilità (oltre l'accoppiamento tra codice per la chiamata statica).

Molti sviluppatori comprenderne i rischi di adesive statico e stato globale, ma verranno comunque stretta tra il codice per le implementazioni specifiche tramite la creazione di istanze diretto. "Nuovo è glue" deve essere un promemoria di questo tipo di controllo e non un condanna generale utilizza la parola chiave new. Come con chiamate al metodo statico, nuove istanze dei tipi che non hanno dipendenze esterne in genere non è strettamente accoppiato codice per i dettagli di implementazione o rendere più difficile il test. Ma ogni volta che viene creata un'istanza di una classe, richiedere solo un breve istante da considerare se è consigliabile codificare quell ' istanza specifica in quella determinata posizione o se ne fosse una progettazione migliore per richiedere tale istanza come dipendenza.

### <a name="declare-your-dependencies"></a>Dichiarare le dipendenze

ASP.NET Core si basa su metodi e classi dichiarano le relative dipendenze, che ne fanno richiesta come argomenti. Applicazioni ASP.NET vengono in genere impostate in una classe di avvio, che a sua volta è configurato per supportare l'inserimento di dipendenze in diversi momenti. Se la classe di avvio ha un costruttore, può richiedere dipendenze mediante il costruttore, come illustrato di seguito:

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
        .AddJsonFile(\$"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

La classe di avvio è interessante in quanto non esistono requisiti per il tipo esplicito. Non eredita da una classe di base di avvio speciale, né implementa alcuna interfaccia specifico. È possibile assegnare un costruttore o non ed è possibile specificare tutti i parametri del costruttore desiderato. Quando l'host web configurati per l'applicazione viene avviata, chiama la classe di avvio che si è indicato l'utilizzo e utilizzerà l'inserimento di dipendenze per popolare le dipendenze che richiede la classe di avvio. Naturalmente, se si richiedono parametri che non sono configurati nel contenitore di servizi utilizzato da ASP.NET Core, si otterrà un'eccezione, ma come soffermeremo dipendenze il contenitore viene a conoscenza, è possibile richiedere desiderato.

Inserimento di dipendenze è incorporata nelle applicazioni ASP.NET Core sin dall'inizio, quando si crea l'istanza di avvio. Non solo per la classe di avvio. È inoltre possibile richiedere le dipendenze del metodo di configurazione:

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

Il metodo ConfigureServices è l'eccezione a questo comportamento. è necessario eseguire un solo parametro di tipo IServiceCollection. Non debba necessariamente supportano l'inserimento di dipendenze, poiché da un lato è responsabile dell'aggiunta di oggetti per il contenitore dei servizi e l'altro ha accesso a tutti i servizi configurati tramite il parametro IServiceCollection. Di conseguenza, è possibile utilizzare con le dipendenze definite nella raccolta in ogni parte della classe di avvio, che richiede il servizio necessario come parametro oppure quando si lavora con IServiceCollection in ConfigureServices servizi ASP.NET Core.

> [!NOTE]
> Se si desidera verificare alcuni servizi siano disponibili per la classe di avvio, è possibile configurarli tramite WebHostBuilder e il relativo metodo ConfigureServices.

La classe di avvio è un modello di struttura altre parti dell'applicazione ASP.NET di base, dal controller al Middleware ai filtri per i propri servizi. In ogni caso, è necessario seguire il [principio dipendenze esplicite](http://deviq.com/explicit-dependencies-principle/), che richiede le dipendenze anziché direttamente la loro creazione e sfruttando l'inserimento di dipendenze in tutta l'applicazione. Prestare attenzione a dove e come creare direttamente le implementazioni, in particolare i servizi e gli oggetti che utilizzano infrastruttura o avere effetti collaterali. Preferire l'utilizzo di astrazioni definite in base l'applicazione e passati come argomenti a riferimenti hardcoded per tipi specifici di implementazione.

## <a name="structuring-the-application"></a>Strutturare l'applicazione

Applicazioni monolitiche in genere presente un solo punto di ingresso. Nel caso di un'applicazione web ASP.NET Core, il punto di ingresso sarà il progetto web ASP.NET Core. Tuttavia, non implica che la soluzione deve essere costituito solo un singolo progetto. È utile suddividere l'applicazione in livelli diversi per seguire la separazione dei compiti. Dopo aver suddiviso in livelli, è utile superare le cartelle per separare i progetti, che consentono di ottenere una migliore incapsulamento. L'approccio migliore per raggiungere questi obiettivi con un'applicazione ASP.NET Core è una variante dell'architettura pulita descritte nel capitolo 5. Seguendo questo approccio, la soluzione dell'applicazione verrà essere costituita da librerie separate per l'interfaccia utente, l'infrastruttura e ApplicationCore.

Oltre a questi progetti, i progetti di test separato sono inclusi anche (test sono descritto nel capitolo 9).

Modello a oggetti e le interfacce dell'applicazione devono trovarsi nel progetto ApplicationCore. Questo progetto verrà dipendenze con il minor numero possibile, e gli altri progetti nella soluzione verranno farvi riferimento. Entità di business che devono essere mantenute sono definite nel progetto ApplicationCore, sono servizi che non dipendono direttamente da infrastruttura.

Dettagli di implementazione, ad esempio la modalità di esecuzione di persistenza o come è possibile inviare notifiche a un utente, vengono mantenuti nel progetto di infrastruttura. Il progetto farà riferimento specifico dell'implementazione di pacchetti, ad esempio Entity Framework Core, ma non deve esporre informazioni dettagliate su queste implementazioni all'esterno del progetto. Repository e servizi dell'infrastruttura deve implementare le interfacce che sono definite nel progetto ApplicationCore, e le relative implementazioni di persistenza sono responsabili per recuperare e archiviare le entità definite in ApplicationCore.

Il progetto ASP.NET Core stesso è responsabile di eventuali problemi a livello dell'interfaccia utente, ma non deve includere i dettagli di infrastruttura o logica di business. In realtà, in teoria non deve anche presentano una dipendenza nel progetto di infrastruttura, che non è stato introdotto accidentalmente alcuna dipendenza tra i due progetti in modo. Questo può essere ottenuto utilizzando un contenitore DI terze parti come StructureMap, che consente di definire le regole DI nelle classi del Registro di sistema in ogni progetto.

Un altro approccio per l'applicazione dai dettagli di implementazione di separazione è che microservizi la chiamata dell'applicazione, probabilmente distribuiti in singoli contenitori Docker. Offre anche maggiore separazione delle problematiche e separazione di utilizzo DI tra due progetti, ma presenta una complessità aggiuntiva.

### <a name="feature-organization"></a>Organizzazione di funzionalità

Per impostazione predefinita, le applicazioni ASP.NET Core organizzano relativa struttura di cartelle da includere controller e visualizzazioni e spesso ViewModel. Il codice lato client per supportare queste strutture sul lato server è in genere archiviato separatamente nella cartella wwwroot. Tuttavia, applicazioni di grandi dimensioni possono verificarsi problemi con l'organizzazione, poiché spesso l'utilizzo su qualsiasi funzionalità specificata richiede il passaggio tra queste cartelle. Questo metodo ottiene più difficile man mano che aumenta il numero di file e le sottocartelle in ogni cartella, comportando una notevole di scorrimento in Esplora soluzioni. Per risolvere questo problema consiste nell'organizzare il codice dell'applicazione da *funzionalità* anziché mediante il tipo di file. Questo stile azienda viene generalmente indicato come cartelle delle funzionalità o sezioni di funzionalità (vedere anche: [sezioni verticale](http://deviq.com/vertical-slices/)).

Componenti di base di ASP.NET MVC supporta aree a questo scopo. Utilizzo delle aree, è possibile creare set distinti di controller e visualizzazioni cartelle (nonché tutti i modelli associati) in ogni cartella di Area. Figura 7-1 mostra una struttura di cartelle di esempio, utilizzando le aree.

![](./media/image7-1.png)

Organizzazione di Area di esempio nella figura 7-1

Quando si usano le aree, è necessario utilizzare gli attributi per decorare i controller con il nome dell'area a cui appartengono:

```csharp
[Area("Catalog")]
public class HomeController
{}
```

È inoltre necessario aggiungere il supporto di area per la route:

```csharp
app.UseMvc(routes =>
{
    // Areas support
    routes.MapRoute(
    name: "areaRoute",
    template: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    routes.MapRoute(
    name: "default",
    template: "{controller=Home}/{action=Index}/{id?}");
});
```

Oltre al supporto incorporato per le aree, è possibile utilizzare la propria struttura di cartelle e le convenzioni al posto di attributi e le route personalizzate. Ciò consentirebbe a cartelle di funzionalità che non includono cartelle separate per le visualizzazioni, controller e così via, mantenendo più piana della gerarchia e rendendo più semplice visualizzare che tutti i relativi file in un'unica posizione per ogni funzionalità.

ASP.NET Core utilizza tipi incorporati convenzione per controllarne il comportamento. È possibile modificare o sostituire queste convenzioni. Ad esempio, è possibile creare una convenzione che verrà assegnato automaticamente il nome della funzionalità per un controller specifico in base al relativo spazio dei nomi (che in genere è correlato alla cartella in cui si trova il controller):

```csharp
FeatureConvention : IControllerModelConvention
{
    public void Apply(ControllerModel controller)
    {
        controller.Properties.Add("feature",
        GetFeatureName(controller.ControllerType));
    }

    private string GetFeatureName(TypeInfo controllerType)
    {
        string[] tokens = controllerType.FullName.Split('.');
        if (!tokens.Any(t => t == "Features")) return "";
        string featureName = tokens
        .SkipWhile(t => !t.Equals("features",
        StringComparison.CurrentCultureIgnoreCase))
        .Skip(1)
        .Take(1)
        .FirstOrDefault();
        return featureName;
    }
}
```

Specificare quindi questa convenzione come opzione quando si aggiunge il supporto per MVC per l'applicazione in ConfigureServices:

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

Componenti di base di ASP.NET MVC utilizza anche una convenzione di trovare le viste. È possibile eseguirne l'override con una convenzione personalizzata in modo che le visualizzazioni si trovino nelle cartelle di funzionalità (utilizzando il nome della funzionalità fornito da FeatureConvention, sopra). È possibile approfondire la conoscenza di questo approccio e scaricare un esempio reale dall'articolo MSDN, [gli intervalli di funzionalità per ASP.NET MVC Core](https://msdn.microsoft.com/magazine/mt763233.aspx).

### <a name="cross-cutting-concerns"></a>Problemi di montaggio incrociato

Applicazioni di aumento delle dimensioni, diventa sempre più importante tenere in considerazione le problematiche a montaggio incrociato per eliminare i duplicati e mantenere la coerenza. Alcuni esempi di problemi di montaggio incrociato nelle applicazioni ASP.NET Core sono l'autenticazione, le regole di convalida del modello, la memorizzazione nella cache di output e gestione degli errori, anche se esistono molti altri. Componenti di base di ASP.NET MVC [filtri](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) consentono di eseguire codice prima o dopo alcuni passaggi nella pipeline di elaborazione della richiesta. Ad esempio, un filtro è possibile eseguire prima e dopo l'associazione di modelli, prima e dopo un'azione, o prima e dopo il risultato di un'azione. È inoltre possibile utilizzare un filtro di autorizzazione per controllare l'accesso al resto della pipeline. Viene illustrato nelle figure 7-2 richiesta come flussi di esecuzione tramite i filtri, se configurato.

![La richiesta viene elaborata tramite filtri di autorizzazione, filtri delle risorse, associazione di modelli, filtri azione, esecuzione azione e azione di conversione di risultati, i filtri eccezioni, filtri dei risultati e risultati esecuzione. La modalità di timeout, la richiesta viene elaborata solo mediante filtri dei risultati e i filtri di risorsa prima di diventare una risposta inviata al client.](./media/image7-2.png)

Figura 7-2 l'esecuzione della richiesta tramite pipeline di richieste e di filtri.

I filtri vengono in genere implementati come attributi, pertanto è possibile applicare azioni o controller. Quando aggiunta in questo modo, i filtri specificati all'override del livello di azione o di compilazione al momento i filtri specificati a livello di controller, che a loro volta eseguire l'override di filtri globali. Ad esempio, il \[Route\] attributo può essere utilizzato per creare le route tra i controller e azioni. Analogamente, autorizzazione può essere configurata a livello di controller e sottoposta a override da singole azioni, come illustrato nell'esempio seguente:

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

Il primo metodo, l'account di accesso, utilizza il filtro di AllowAnonymous (attributo) per eseguire l'override di filtro autorizza impostato a livello di controller. L'azione ForgotPassword (e qualsiasi altra azione nella classe che non dispone di un attributo AllowAnonymous) richiederà una richiesta autenticata.

Per eliminare i duplicati nel modulo comuni di gestione degli errori criteri per le API, è possono utilizzare i filtri. Ad esempio, un criterio di API tipico è per restituire una risposta non trovato per le richieste che fanno riferimento a chiavi che non esistono e una risposta richiesta non valida se si verifica un errore di convalida del modello. L'esempio seguente illustra queste due criteri in azione:

```csharp
[HttpPut("{id}")]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    if ((await _authorRepository.ListAsync()).All(a => a.Id != id))
    {
        return NotFound(id);
    }
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    author.Id = id;
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

Non consentire i metodi di azione accumularsi condizionale codice simile al seguente. In alternativa, estrarre i criteri in filtri che possono essere applicati in base alle esigenze. In questo esempio, il controllo di convalida del modello, deve verificarsi ogni volta che viene inviato un comando all'API, può essere sostituito dall'attributo seguente:

```csharp
public class ValidateModelAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (!context.ModelState.IsValid)
        {
            context.Result = new BadRequestObjectResult(context.ModelState);
        }
    }
}
```

Analogamente, un filtro consente di verificare se un record di restituire un errore 404 prima che l'azione viene eseguita, eliminando la necessità di eseguire questi controlli nell'azione. Dopo avere estratta convenzioni comuni e organizzati la soluzione di separare la logica di business e di codice di infrastruttura dall'interfaccia utente, i metodi di azione MVC devono essere estremamente sottili:

```csharp
// PUT api/authors/2/5
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

È possibile leggere informazioni circa l'implementazione di filtri e scaricare un esempio reale dall'articolo MSDN, [reale World ASP.NET Core MVC filtri](https://msdn.microsoft.com/magazine/mt767699.aspx).

> ### <a name="references--structuring-applications"></a>Riferimenti: strutturare applicazioni
> - **Aree**  
> <https://docs.microsoft.com/ASPNET/core/MVC/Controllers/Areas>
> - **MSDN: gli intervalli di funzionalità per i componenti di base di ASP.NET MVC**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx>
> - **Filtri**  
> <https://docs.microsoft.com/ASPNET/core/MVC/Controllers/Filters>
> - **MSDN-filtri MVC ASP.NET Core mondo reale**  
> <https://msdn.microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a>Sicurezza

Protezione delle applicazioni web è un argomento di grandi dimensioni, con in considerazione numerosi fattori. Al livello più elementare di protezione prevede che sapere chi provenienti da una determinata richiesta e quindi garantire che la richiesta ha accesso solo a risorse che dovrebbe essere. L'autenticazione è il processo di confronto tra le credenziali fornite con una richiesta a quelli di un archivio dati attendibile, per vedere se la richiesta deve essere trattata come proveniente da un'entità nota. L'autorizzazione è il processo di limitare l'accesso a determinate risorse in base all'identità utente. Problemi di sicurezza terzo protegge le richieste di intercettazione di terze parti, per cui è necessario almeno [assicurarsi che SSL viene utilizzato dall'applicazione](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).

### <a name="authentication"></a>Autenticazione

Identità di ASP.NET Core è un sistema di appartenenze, che è possibile utilizzare per supportare la funzionalità di accesso per l'applicazione. Include supporto per gli account utente locale oltre al supporto di provider di accesso esterno dal provider come Account Microsoft, Twitter, Facebook, Google e altro ancora. Oltre a ASP.NET Identity Core, è possibile utilizzare l'autenticazione di windows o un provider di identità di terze parti come [Identity Server](https://github.com/IdentityServer/IdentityServer4).

Identità di ASP.NET Core è incluso in nuovi modelli di progetto se è selezionata l'opzione di account utente. Questo modello include il supporto per la registrazione, account di accesso, account di accesso esterni, password dimenticate e funzionalità aggiuntive.

![](./media/image7-3.png)

Figura 7-3 selezionare singoli account utente di disporre di identità preconfigurato.

Nella finestra di avvio, sia in ConfigureServices e configura viene configurato il supporto di identità:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
    services.AddMvc();
}

public void Configure(IApplicationBuilder app)
{
    app.UseStaticFiles();
    app.UseIdentity();
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

È importante che UseIdentity precedere UseMvc nel metodo di configurazione. Quando si configura l'identità in ConfigureServices, si noterà una chiamata a AddDefaultTokenProviders. Questo non ha nulla a che fare con i token che possono essere utilizzati per proteggere le comunicazioni web, ma invece fa riferimento ai provider di creazione di richieste che possono essere inviate agli utenti tramite SMS o posta elettronica per consentire di confermare la propria identità.

Altre informazioni, vedere [la configurazione dell'autenticazione a due fattori](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) e [abilitazione di provider di accesso esterno](https://docs.microsoft.com/aspnet/core/security/authentication/social/) dalla documentazione ufficiale ASP.NET Core.

### <a name="authorization"></a>Autorizzazione

La forma più semplice di autorizzazione è necessario limitare l'accesso a utenti anonimi. Questo può essere ottenuto applicando semplicemente il \[Authorize\] attributo determinati controller o azioni. Se vengono utilizzati i ruoli, l'attributo può essere esteso ulteriormente per limitare l'accesso agli utenti che appartengono a determinati ruoli, come illustrato:

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

In questo caso, gli utenti che appartengono ai ruoli HRManager o Finance (oppure entrambe) deve disporre dell'accesso per il SalaryController. Per richiedere che un utente appartiene a più ruoli (non solo uno di diversi), è possibile applicare l'attributo più volte, specificando un ruolo necessario ogni ora.

Specificare alcuni set di ruoli come stringhe in numerosi diversi controller e azioni possono causare la ripetizione indesiderata. È possibile configurare criteri di autorizzazione, che incapsulano le regole di autorizzazione, e quindi specificare i criteri anziché singoli ruoli quando si applica il \[Authorize\] attributo:

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

Usando i criteri in questo modo, è possibile separare i tipi di azioni vengano limitate dal ruoli specifici o regole da applicare a esso. In un secondo momento, se si crea un nuovo ruolo che deve avere accesso a determinate risorse, è possibile aggiornare solo un criterio, anziché aggiornare ogni elenco di ruoli in ogni \[Authorize\] attributo.

#### <a name="claims"></a>Attestazioni

Le attestazioni sono coppie nome / valore che rappresentano le proprietà di un utente autenticato. Ad esempio, è possibile archiviare il numero di dipendenti degli utenti come attestazione. Attestazioni possono quindi essere utilizzate come parte di criteri di autorizzazione. È possibile creare un criterio denominato "EmployeeOnly" che richiede l'esistenza di un'attestazione denominata "EmployeeNumber", come illustrato in questo esempio:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}
```

Questo criterio può essere utilizzato con la \[Authorize\] attributo per proteggere qualsiasi controller e/o l'azione, come descritto in precedenza.

#### <a name="securing-web-apis"></a>Protezione delle API Web

La maggior parte dei web API deve implementare un sistema di autenticazione basata su token. L'autenticazione del token è progettato per essere scalabile e senza stato. In un sistema basato su token di autenticazione, il client deve prima autenticarsi con il provider di autenticazione. Se ha esito positivo, il client ha emesso un token, che è semplicemente una stringa significativa crittograficamente di caratteri. Quando il client deve quindi eseguire una richiesta a un'API, questo token viene aggiunto un'intestazione nella richiesta. Il server di convalida quindi il token nell'intestazione della richiesta prima di completare la richiesta. Figura 7-4 viene illustrato questo processo.

![TokenAuth](./media/image7-4.png)

**Figura 7-4.** Autenticazione basata su token per le API Web.

> ### <a name="references--security"></a>Riferimenti: sicurezza
> - **Panoramica della sicurezza documenti**  
> https://docs.microsoft.com/ASPNET/Core/Security/
> - **Applicazione di SSL in un'applicazione ASP.NET di base**  
> <https://docs.microsoft.com/ASPNET/Core/Security/Enforcing-SSL>
> - **Introduzione a Identity**  
> <https://docs.microsoft.com/ASPNET/Core/Security/Authentication/Identity>
> - **Introduzione alle autorizzazioni**  
> <https://docs.microsoft.com/ASPNET/Core/Security/Authorization/Introduction>
> - **Autenticazione e autorizzazione per App per le API nel servizio App di Azure**  
> <https://docs.microsoft.com/Azure/App-Service-API/App-Service-API-Authentication>

## <a name="client-communication"></a>Comunicazione client

Oltre a servire le pagine e risponde alle richieste di dati tramite l'API web, le applicazioni ASP.NET Core possono comunicare direttamente con i client connessi. Le comunicazioni in uscita è possono utilizzare un'ampia gamma di tecnologie di trasporto, l'oggetto da più comune di WebSocket. Componenti di base di ASP.NET SignalR è una libreria che semplifica il tipo di funzionalità di comunicazione client-server in tempo reale alle applicazioni. SignalR supporta un'ampia gamma di tecnologie di trasporto, incluse WebSocket e astrae stoccaggi molti dettagli dell'implementazione da parte dello sviluppatore.

Componenti di base di ASP.NET SignalR è attualmente in fase di sviluppo e saranno disponibili nella prossima versione di ASP.NET Core. Tuttavia, altri [aprire librerie WebSocket origine](https://github.com/radu-matei/websocket-manager) sono attualmente disponibili.

Comunicazione client in tempo reale, se tramite WebSockets direttamente o altre tecniche, sono utili per un'ampia gamma di scenari di applicazioni. Di seguito sono riportati alcuni esempi:

-   Applicazioni di chat in tempo reale

-   Monitoraggio delle applicazioni

-   Aggiornamenti dello stato di processo

-   Notifiche

-   Applicazioni interattive form

Quando si compila la comunicazione client nelle applicazioni, in genere due componenti sono:

-   Gestione di connessione sul lato server (SignalR Hub, WebSocketManager WebSocketHandler)

-   Libreria lato client

I client non sono limitati ai browser-App per dispositivi mobili, applicazioni console, e altre App native possono inoltre in grado di comunicare utilizzando/WebSocket SignalR. Il programma semplice seguente restituisce tutto il contenuto inviato a un'applicazione di chat alla console, come parte di un'applicazione di esempio WebSocketManager:

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>;
        {
            Console.WriteLine(\$"{arguments\[0\]} said: {arguments\[1\]}");
        });
        Console.ReadLine();
        StopConnectionAsync();
    }
    
    public static async Task StartConnectionAsync()
    {
        _connection = new Connection();
        await _connection.StartConnectionAsync("ws://localhost:65110/chat");
    }
    
    public static async Task StopConnectionAsync()
    {
        await _connection.StopConnectionAsync();
    }
```

Considerare l'esperienza di modi in cui le applicazioni comunicano direttamente con le applicazioni client e considerare se la comunicazione in tempo reale migliorerebbe utente dell'applicazione.

> ### <a name="references--client-communication"></a>Riferimenti: la comunicazione Client
> - **Componenti di base di ASP.NET SignalR**  
> <https://github.com/ASPNET/SignalR>
> - **Gestione di WebSocket**  
> https://github.com/Radu-matei/WebSocket-Manager

## <a name="domain-driven-design--should-you-apply-it"></a>Progettazione – basati su dominio deve viene applicato?

Progettazione basati su dominio (DDD) è un approccio agile per la creazione di software che punta a concentrarsi sul *dominio aziendale*. Inserisce l'importanza di comunicazione e l'interazione con expert(s) di dominio di business che può essere correlata per gli sviluppatori di funzionamento del sistema del mondo reale. Ad esempio, se si sta creando un sistema di transazioni azionarie, l'esperto di dominio potrebbe essere un'esperto broker predefinite. DDD è progettato per risolvere problemi aziendali complessi e spesso non è appropriato per le applicazioni più piccole e più semplice, come l'investimento della comprensione e modellazione del dominio non è accettabile.

Quando si compila software adotta un approccio DDD, il team (incluso per le persone interessate e i collaboratori) è necessario sviluppare un *linguaggio universale* per lo spazio dei problemi. Vale a dire la stessa terminologia da utilizzare per il concetto di scenari reali in fase di modellazione, l'equivalente di software e le strutture che potrebbero esistere per mantenere il concetto (ad esempio, le tabelle di database). Di conseguenza, i concetti illustrati in linguaggio universale devono costituiscono la base per il *modello di dominio*.

Modello di dominio è costituito da oggetti che interagiscono tra loro per rappresentare il comportamento del sistema. Questi oggetti possono rientrano nelle categorie seguenti:

-   [Entità](http://deviq.com/entity/), che rappresentano gli oggetti con un thread di identità. Le entità vengono in genere archiviate nella persistenza con una chiave con cui essi possono essere recuperate successivamente.

-   [Funzioni di aggregazione](http://deviq.com/aggregate-pattern/), che rappresentano gruppi di oggetti che devono essere mantenuti come un'unità.

-   [Valore oggetti](http://deviq.com/value-object/), che rappresentano i concetti che possono essere confrontati mediante la somma dei valori delle relative proprietà. Ad esempio, DateRange costituito da una data di inizio e di fine.

-   [Eventi del dominio](https://martinfowler.com/eaaDev/DomainEvent.html), che rappresentano operazioni eseguite all'interno del sistema di interesse ad altre parti del sistema.

Si noti che un modello di dominio DDD deve incapsulare un comportamento complesso all'interno del modello. Le entità, in particolare, non devono semplicemente essere raccolte di proprietà. Quando il modello di dominio non dispone di comportamento e semplicemente rappresenta lo stato del sistema, viene definito un [anemic modello](http://deviq.com/anemic-model/), questo non è auspicabile in DDD.

Oltre a questi tipi di modello, DDD utilizza in genere un'ampia gamma di modelli:

-   [Repository](http://deviq.com/repository-pattern/), per fornire l'astrazione di dettagli di persistenza.

-   [Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), per incapsulare la creazione di oggetti complessi.

-   Eventi di dominio, per la separazione di comportamento dipende dal comportamento di trigger.

-   [Servizi](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), per un comportamento complesso incapsulamento e/o i dettagli di implementazione dell'infrastruttura.

-   [Comando](https://en.wikipedia.org/wiki/Command_pattern), inviare i comandi per la separazione e l'esecuzione del comando stesso.

-   [Specifica](http://deviq.com/specification-pattern/), per incapsulare dettagli di query.

DDD inoltre consiglia l'uso dell'architettura pulita illustrato in precedenza, consentendo un regime di controllo, incapsulamento e codice che può essere verificato facilmente con unit test.

### <a name="when-should-you-apply-ddd"></a>Quando si deve applicare DDD

DDD è ideale per applicazioni di grandi dimensioni con una complessità di business significativo (non solo tecnico). L'applicazione deve richiedere le informazioni di esperti di dominio. Dovrebbe esserci un comportamento significativo nel modello di dominio, che rappresenta le regole di business e interazioni oltre sufficiente archiviare e recuperare lo stato corrente di vari record dagli archivi dati.

### <a name="when-shouldnt-you-apply-ddd"></a>Quando non si applicano DDD

DDD prevede gli investimenti nella comunicazione che non può essere garantita per piccole applicazioni o le applicazioni che sono essenzialmente solo CRUD (creazione/lettura/aggiornamento/eliminazione), l'architettura e modellazione. Se si sceglie di approccio l'applicazione seguente DDD, ma che il dominio è disponibile un modello anemic con alcun comportamento di trovare, devi riprogettare l'approccio. L'applicazione potrebbe non essere necessario DDD oppure potrebbe essere necessaria assistenza refactoring dell'applicazione per incapsulare la logica di business nel modello di dominio, anziché nell'interfaccia utente o di database.

Un approccio ibrido può essere usata solo DDD per le aree transazionale o di più complesse dell'applicazione, ma non per CRUD più semplice o di sola lettura di parti dell'applicazione. È necessario che ad esempio, includere i vincoli di un'aggregazione se si sta eseguendo la query di dati per visualizzare un report o per visualizzare i dati per un dashboard. È perfettamente accettabile disporre di un modello per la letto separato e più semplice per tali requisiti.

> ### <a name="references--domain-driven-design"></a>Riferimenti: progettazione basati su dominio
> - **DDD in lingua inglese (StackOverflow risposta)**  
> <https://StackOverflow.com/Questions/1222392/CAN-someone-Explain-Domain-Driven-Design-ddd-in-Plain-English-Please/1222488#1222488>

## <a name="deployment"></a>Distribuzione

Esistono alcuni passaggi coinvolti nel processo di distribuzione dell'applicazione ASP.NET di base, indipendentemente dal fatto in cui verrà ospitato. Il primo passaggio consiste nel pubblicare l'applicazione, che può essere eseguita con il dotnet pubblicare comando CLI. Verrà compilato l'applicazione e inserire tutti i file necessari per eseguire l'applicazione in una cartella designata. Quando si distribuisce da Visual Studio, questo passaggio viene eseguito automaticamente. Cartella di pubblicazione contiene file .exe e DLL per l'applicazione e le relative dipendenze. Un'applicazione indipendente includerà inoltre una versione del runtime .NET. Le applicazioni ASP.NET Core includerà anche i file di configurazione, asset client statico e le visualizzazioni MVC.

Applicazioni ASP.NET sono applicazioni console che devono essere avviate quando il server viene avviato e riavviato in caso di arresto anomalo dell'applicazione (o server). Un gestore di processi è utilizzabile per automatizzare il processo. I responsabili di processo più comuni per ASP.NET Core sono Nginx e Apache su Linux e IIS o il servizio di Windows in Windows.

Oltre a un gestore di processi, le applicazioni ASP.NET Core ospitate nel server web Kestrel devono utilizzare un server proxy inverso. Un server proxy inverso riceve le richieste HTTP da internet e li inoltra a Kestrel dopo alcune operazioni di gestione preliminare. Server proxy inverso forniscono un livello di sicurezza per l'applicazione e sono necessari per le distribuzioni di edge (esposte per il traffico da Internet). Kestrel è relativamente nuovo e non dispone ancora di difese contro alcuni attacchi. Kestrel inoltre non supporta l'hosting di più applicazioni sulla stessa porta, in modo tecniche come intestazioni host non possono essere utilizzate per abilitare l'hosting di più applicazioni sulla stessa porta e indirizzo IP.

![Kestrel a Internet](./media/image7-5.png)

Figura 7-5 ASP.NET ospitati in Kestrel dietro un server proxy inverso

Un altro scenario in cui un proxy inverso può risultare utile consiste nel proteggere più applicazioni che usano SSL e HTTPS. In questo caso, sarebbe necessario solo il proxy inverso di avere configurato SSL. La comunicazione tra il server proxy inverso Kestrel potrebbe avvenire su HTTP, come illustrato nella figura 7-6.

![](./media/image7-6.png)

Figura 7-6 ASP.NET ospitato da un server proxy inverso HTTPS protetta

Un approccio sempre più diffuso consiste nell'ospitare l'applicazione ASP.NET Core in un contenitore Docker, che può essere ospitato in locale o distribuito in Azure per l'hosting basato su cloud. Il contenitore Docker potrebbe contenere codice dell'applicazione in esecuzione su Kestrel e sarà distribuito con un server proxy inverso, come illustrato in precedenza.

Se si ospita l'applicazione in Azure, è possibile utilizzare il Gateway di applicazione di Microsoft Azure come appliance virtuale dedicato per fornire servizi diversi. Oltre a funge da proxy inverso per le singole applicazioni, Gateway applicazione possono inoltre offrire le funzionalità seguenti:

-   Bilanciamento del carico HTTP

-   Offload SSL (SSL solo per Internet)

-   SSL end-to-End

-   Routing multisito (consolidare fino a 20 siti su un singolo Gateway applicazione)

-   Firewall applicazione Web

-   Supporto di WebSocket

-   Diagnostica avanzata

*Per ulteriori informazioni sulle opzioni di distribuzione di Azure nel capitolo 10.*

> ### <a name="references--deployment"></a>Riferimenti: distribuzione
> - **Cenni preliminari sulla distribuzione e hosting**  
> <https://docs.microsoft.com/ASPNET/core/Publishing/>
> - **Quando utilizzare Kestrel con un proxy inverso**  
> <https://docs.microsoft.com/ASPNET/core/Fundamentals/Servers/kestrel#When-to-Use-kestrel-with-a-reverse-proxy>
> - **Host di applicazioni ASP.NET Core in Docker**  
> <https://docs.microsoft.com/ASPNET/core/Publishing/docker>
> - **Introduzione di Gateway applicazione Azure**  
> <https://docs.microsoft.com/Azure/Application-Gateway/Application-Gateway-Introduction>

>[!div class="step-by-step"]
[Precedente] (comuni-client-side-web-technologies.md) [Avanti] (work-with-data-in-asp-net-core-apps.md)
