---
title: Sviluppo di app ASP.NET Core MVC
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Sviluppo di app ASP.NET Core MVC
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 3de70af23206b0ae0525541b3d2cb480dc5bb882
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987907"
---
# <a name="develop-aspnet-core-mvc-apps"></a>Sviluppare app ASP.NET Core MVC

> "Non è importante ottenere il risultato desiderato al primo tentativo. L'importante è ottenerlo all'ultimo".  
> _- Andrew Hunt e David Thomas_

ASP.NET Core è un framework multipiattaforma open source per la compilazione di moderne applicazioni Web ottimizzate per il cloud. Le app ASP.NET Core sono leggere e modulari, con supporto incorporato per l'inserimento di dipendenze, e offrono maggiore testabilità e gestibilità. In associazione a MVC, che supporta la compilazione di API Web moderne oltre che di app basate su visualizzazione, ASP.NET Core è un framework potente per la compilazione di applicazioni Web aziendali.

## <a name="mvc-and-razor-pages"></a>MVC e Razor Pages

ASP.NET Core MVC offre molte funzionalità utili per la compilazione di API e app basate sul Web. Il termine MVC è l'acronimo di "Model-View-Controller", un modello UI che suddivide le responsabilità della risposta alle richieste degli utenti in più sezioni. Oltre a seguire questo modello è possibile implementare funzionalità nelle app ASP.NET Core come Razor Pages. Le pagine Razor sono incorporate in ASP.NET Core MVC e usano le stesse funzionalità per il routing, l'associazione di modelli e così via. Tuttavia, anziché disporre di cartelle e file separati per controller, visualizzazioni e così via e utilizzando il routing basato su attributi, le pagine Razor vengono inserite in un'unica cartella ("/Pages"), instradare in base alla posizione relativa in questa cartella e gestire le richieste con i gestori anziché le azioni del controller.

Quando si crea una nuova app ASP.NET Core è importante avere determinato il tipo di app che si vuole creare. In Visual Studio è possibile scegliere tra diversi modelli. I tre modelli di progetto più comuni sono API Web, Applicazione Web e Applicazione Web (MVC). Anche se è possibile prendere questa decisione solo quando si crea un progetto per la prima volta, non è una decisione irrevocabile. Il progetto API Web usa controller MVC standard, ma per impostazione predefinita non dispone di una cartella Views. Allo stesso modo il modello Applicazione Web predefinito usa Razor Pages e pertanto non dispone di una cartella Views. È possibile aggiungere una cartella Views a questi progetti in un secondo momento per supportare il comportamento basato sulle visualizzazioni. I progetti API Web e MVC non includono una cartella Pages per impostazione predefinita, ma è possibile aggiungerne una in un secondo momento per supportare i comportamenti basati su Razor Pages. Considerare questi tre modelli come origini del supporto per tre tipi diversi di interazione dell'utente predefinita: dati (API Web), basata sulle pagine e basata sulle visualizzazioni. Se si vuole è tuttavia possibile combinare e associare alcuni o tutti questi modelli in un singolo progetto.

### <a name="why-razor-pages"></a>Perché Razor Pages?

Razor Pages è l'approccio predefinito per le nuove applicazioni Web in Visual Studio. Razor Pages offre una modalità più semplice per la creazione di funzionalità dell'applicazione basate sulle pagine, ad esempio moduli non SPA. Con i controller e le visualizzazioni capitava spesso di avere applicazioni con controller molto grandi, che funzionavano con molte dipendenze e modelli di visualizzazione diversi e restituivano molte visualizzazioni diverse. Ciò ha comportato una maggiore complessità e spesso ha portato a controller che non hanno seguito il principio di responsabilità singola o principi aperti/chiusi in modo efficace. Razor Pages risolve questo problema incapsulando la logica lato server di una determinata "pagina" logica in un'applicazione Web con markup Razor. Una pagina Razor che non include logica lato server può essere costituita semplicemente da un file Razor (ad esempio "Index.cshtml"). Tuttavia la maggior parte delle pagine Razor non elementari include una classe modello pagina associata, che per convenzione ha lo stesso nome del file Razor seguito dall'estensione "cs", ad esempio "Index.cshtml.cs".

Modello di pagina di una pagina Razor combina le responsabilità di un controller MVC e un modello di visualizzazione. Anziché gestire le richieste con metodi di azione del controller, vengono eseguiti gestori modello di pagina come "OnGet()" che eseguono il rendering della pagina associata per impostazione predefinita. Razor Pages semplifica il processo di creazione di pagine singole in un'app ASP.NET Core, pur garantendo tutte le funzionalità architettoniche di ASP.NET Core MVC. Si tratta di una scelta predefinita ottimale per nuove funzionalità basate sulle pagine.

### <a name="when-to-use-mvc"></a>Quando usare MVC

Se si creano API Web, il modello MVC ha più senso che provare a usare pagine Razor.If you're building web APIs, the MVC pattern makes more sense than trying to use Razor Pages. Se il progetto esporrà solo gli endpoint API Web, è consigliabile iniziare dal modello di progetto API Web. In caso contrario, è facile aggiungere controller ed endpoint API associati a qualsiasi app ASP.NET Core.Otherwise, it's easy to add controllers and associated API endpoints to any ASP.NET Core app. Utilizzare l'approccio MVC basato sulla visualizzazione se si esegue la migrazione di un'applicazione esistente da ASP.NET MVC 5 o versioni precedenti per ASP.NET MVC di base e si desidera eseguire questa operazione con il minimo sforzo. Dopo aver effettuato la migrazione iniziale, è possibile valutare se ha senso adottare pagine Razor per nuove funzionalità o anche come migrazione all'ingrosso.

Se scegli di compilare l'app Web usando le pagine Razor o le visualizzazioni MVC, l'app avrà prestazioni simili e includerà il supporto per l'inserimento di dipendenze, i filtri, l'associazione di modelli, la convalida e così via.

## <a name="mapping-requests-to-responses"></a>Mapping delle richieste alle risposte

Fondamentalmente, le app ASP.NET Core mappano le richieste in ingresso alle risposte in uscita. Questa operazione viene eseguita tramite middleware e le semplici app ASP.NET Core e i microservizi possono essere costituiti esclusivamente da middleware personalizzato. Quando si usa ASP.NET Core MVC, è possibile lavorare a un livello avanzato con _route_, _controller_ e _azioni_. Ogni richiesta in ingresso viene confrontata con la tabella di routing dell'applicazione e se viene trovata una route corrispondente, viene chiamato il metodo di azione associato (appartenente a un controller) per gestire la richiesta. Se non viene trovata alcuna route corrispondente, viene chiamato un gestore degli errori (in questo caso, viene restituito un risultato NotFound).

Le app ASP.NET Core MVC possono usare route convenzionali, route di attributi o entrambi i tipi di route. Le route convenzionali sono definite nel codice tramite la specifica delle _convenzioni_ di routing usando una sintassi simile a quella dell'esempio seguente:

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

In questo esempio è stata aggiunta una route denominata "default" alla tabella di routing. Definisce un modello di route con segnaposto per _controller_, _action_e _id_. I segnaposto del controller e dell'azione sono specificati per impostazione predefinita ("Home" e "Index", rispettivamente) e il segnaposto id è facoltativo (in virtù di un "?" applicato ad esso). La convenzione definita in questo caso stabilisce che la prima parte di una richiesta deve corrispondere al nome del controller, la seconda parte all'azione e, se necessaria, una terza parte al parametro dell'ID. Le route convenzionali vengono in genere definite in un'unica posizione per l'applicazione, ad esempio nel metodo Configure della classe Startup.

Le route di attributi vengono applicate a controller e azioni direttamente anziché essere specificate a livello globale. Ciò offre il vantaggio di renderle più facilmente individuabili durante la ricerca di un metodo specifico, ma significa che le informazioni di routing non vengono mantenute in un'unica posizione nell'applicazione. Con le route di attributi, è possibile specificare in modo semplice più route per una determinata azione nonché combinare le route tra i controller e le azioni. Ad esempio:

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
}
```

Le route possono essere specificate in [HttpGet] e attributi simili, evitando la necessità di aggiungere attributi [Route] separati. Le route di attributi possono anche usare i token per ridurre la necessità di ripetere i nomi di controller o azioni, come illustrato di seguito:

```csharp
[Route("[controller]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index() {}
}
```

Le pagine Razor non utilizzano il routing degli attributi. È possibile specificare informazioni aggiuntive sul modello di route per una pagina Razor nel contesto della direttiva `@page` corrispondente:

```csharp
@page "{id:int}"
```

Nell'esempio precedente, la pagina in questione corrisponderà a una route con un parametro `id` intero. Ad esempio la pagina *Products.cshtml* nel percorso radice di `/Pages` ha la route seguente:

```csharp
"/Products/123"
```

Dopo aver individuato una determinata richiesta corrispondente a una route e prima della chiamata al metodo di azione, ASP.NET Core MVC eseguirà l'[associazione del modello](/aspnet/core/mvc/models/model-binding) e la [convalida del modello](/aspnet/core/mvc/models/validation) nella richiesta. L'associazione del modello converte i dati HTTP in ingresso nei tipi .NET specificati come parametri del metodo di azione da chiamare. Ad esempio, se il metodo di azione prevede un parametro ID di tipo int, l'associazione del modello tenterà di usare questo parametro in base a un valore specificato come parte della richiesta. A tale scopo, l'associazione del modello cerca i valori in un form pubblicato, i valori nella route e i valori di stringa di query. Se viene trovato un valore ID, il valore viene convertito in un intero prima di essere passato nel metodo di azione.

Dopo l'associazione del modello ma prima della chiamata al metodo di azione, viene eseguita la convalida del modello. La convalida del modello usa gli attributi facoltativi del tipo di modello e contribuisce a garantire che l'oggetto di modello specificato sia conforme a determinati requisiti dei dati. Alcuni valori possono essere specificati come richiesto, o limitati a una certa lunghezza o intervallo numerico, ecc. Se vengono specificati attributi di convalida ma il modello non è conforme ai requisiti, la proprietà ModelState.IsValid sarà false e il set di regole di convalida non riuscite sarà disponibile per l'invio al client che effettua la richiesta.

Se viene usata la convalida del modello, è necessario verificare sempre che il modello sia valido prima di eseguire i comandi di modifica dello stato per garantire che l'app non sia danneggiata da dati non validi. È possibile usare un [filtro](/aspnet/core/mvc/controllers/filters) per evitare di aggiungere il codice necessario in ogni azione. I filtri di ASP.NET Core MVC consentono di intercettare i gruppi di richieste in modo che sia possibile applicare alla base di destinazione i criteri e gli aspetti comuni. I filtri possono essere applicati alle singole azioni, a interi controller o a livello globale per un'applicazione.

Per le API Web, ASP.NET Core MVC supporta la [_negoziazione del contenuto_](/aspnet/core/mvc/models/formatting) consentendo alle richieste di specificare la formattazione delle risposte. In base alle intestazioni specificate nella richiesta, le azioni che restituiscono dati formattano la risposta nel formato XML, JSON o un altro formato supportato. Questa funzionalità consente a più client con requisiti diversi di formattazione dei dati di usare la stessa API.

Per i progetti API Web può essere utile usare l'attributo `[ApiController]`, applicabile a singoli controller, a una classe controller di base o all'intero assembly. Questo attributo aggiunge il controllo di convalida modello automatico e qualsiasi azione con un modello non valido restituisce BadRequest con i dettagli degli errori di convalida. L'attributo richiede anche che tutte le azioni abbiano una route di attributo (anziché usare una route convenzionale) e restituisce informazioni ProblemDetails più dettagliate in caso di errori.

> ### <a name="references--mapping-requests-to-responses"></a>Riferimenti - Mapping delle richieste alle risposte
>
> - **Routing alle azioni del controller**
 > <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing>
> - **Associazione del modello**
 > <https://docs.microsoft.com/aspnet/core/mvc/models/model-binding>
> - **Convalida del modello**
 > <https://docs.microsoft.com/aspnet/core/mvc/models/validation>
> - **Filtri**
 > <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **Attributo ApiController**
 > <https://docs.microsoft.com/aspnet/core/web-api/>

## <a name="working-with-dependencies"></a>Uso delle dipendenze

ASP.NET Core include il supporto incorporato e usa internamente una tecnica chiamata [inserimento di dipendenze](/aspnet/core/fundamentals/dependency-injection). L'inserimento di dipendenze è una tecnica che abilita l'accoppiamento libero tra parti diverse di un'applicazione. L'accoppiamento libero può essere utile perché rende più semplice isolare le parti dell'applicazione per il test o la sostituzione. Rende anche meno probabile che una modifica in una parte dell'applicazione abbia un impatto imprevisto in un'altra posizione nell'applicazione. L'inserimento di dipendenze si basa sul principio di inversione della dipendenza e rappresenta spesso la chiave per ottenere il principio di apertura/chiusura. Quando si valuta il funzionamento dell'applicazione con le dipendenze, prestare attenzione al codice [static cling](https://deviq.com/static-cling/) e ricordare la frase "[New is Glue](https://ardalis.com/new-is-glue)".

Lo static cling si verifica quando le classi chiamano metodi statici o accedono a proprietà statiche, un'operazione che comporta effetti collaterali o dipendenze nell'infrastruttura. Ad esempio, se è presente un metodo che chiama un metodo statico che a sua volta scrive in un database, il metodo è strettamente accoppiato al database. Qualsiasi elemento che interrompe la chiamata al database interromperà il metodo. Eseguire i test di questi tipi di metodi è notoriamente difficile poiché i test richiedono librerie di simulazione commerciali per simulare le chiamate statiche oppure possono essere eseguiti solo con un database di prova. Le chiamate statiche che non hanno alcuna dipendenza nell'infrastruttura, in particolare quelle che sono completamente senza stato, possono essere eseguite senza problemi e non hanno alcun effetto sull'accoppiamento o la testabilità (oltre all'accoppiamento del codice alla chiamata statica).

Sebbene conoscano i rischi dello static cling e dello stato globale, molti sviluppatori eseguono comunque uno stretto accoppiamento del codice a implementazioni specifiche attraverso la creazione diretta delle istanze. "New is glue" vuole essere un promemoria di questo accoppiamento e non una condanna generale dell'uso della parola chiave `new`. Come con le chiamate a metodi statici, le nuove istanze dei tipi che non hanno dipendenze esterne in genere non accoppiano strettamente il codice ai dettagli di implementazione o rendono più difficile il test. Tuttavia, ogni volta che viene creata un'istanza di una classe, fermarsi a considerare se è consigliabile impostare come hardcoded l'istanza specifica in quella determinata posizione oppure richiedere l'istanza come dipendenza.

### <a name="declare-your-dependencies"></a>Dichiarare le dipendenze

ASP.NET Core si basa su metodi e classi che dichiarano le relative dipendenze richiedendole come argomenti. Le applicazioni ASP.NET sono in genere configurate in una classe Startup che è a sua volta configurata per supportare l'inserimento di dipendenze in punti diversi. Se la classe Startup ha un costruttore, può richiedere le dipendenze mediante il costruttore, come illustrato di seguito:

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
            .SetBasePath(env.ContentRootPath)
            .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
            .AddJsonFile($"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

La classe Startup è particolare perché non include requisiti di tipo espliciti per la classe. Non eredita da una classe di base Startup, né implementa alcuna interfaccia specifica. È possibile assegnare o meno alla classe un costruttore ed è possibile specificare il numero di parametri desiderato nel costruttore. Quando viene avviato l'host Web configurato per l'applicazione, l'host chiama la classe Startup specificata e usa l'inserimento di dipendenze per popolare le dipendenze richieste dalla classe Startup. Naturalmente, se si richiedono parametri che non sono configurati nel contenitore dei servizi usato da ASP.NET Core, viene generata un'eccezione, ma se le richieste si limitano alle dipendenze riconosciute dal contenitore, sarà possibile richiedere qualsiasi elemento.

L'inserimento di dipendenze è incorporato nelle app ASP.NET Core sin dall'inizio, ovvero dalla creazione dell'istanza di Startup. Non viene interrotto per la classe Startup. È possibile richiedere le dipendenze anche nel metodo Configure:

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

Il metodo ConfigureServices rappresenta l'eccezione a questo comportamento. Il metodo deve ricevere un solo parametro di tipo IServiceCollection. Non necessita del supporto dell'inserimento delle dipendenze poiché da un lato è responsabile dell'aggiunta degli oggetti al contenitore dei servizi e dall'altro ha accesso a tutti i servizi correntemente configurati tramite il parametro IServiceCollection. Per questa ragione, è possibile usare le dipendenze definite nella raccolta di servizi di ASP.NET Core in ogni parte della classe Startup, richiedendo il servizi necessario come parametro o usando IServiceCollection in ConfigureServices.

> [!NOTE]
> Se è necessario assicurarsi che determinati servizi siano disponibili per la classe Startup, è possibile configurarli utilizzando un IWebHostBuilder e il relativo metodo ConfigureServices all'interno della chiamata CreateDefaultBuilder.

La classe Startup costituisce un modello per la struttura delle altre parti dell'applicazione ASP.NET Core, dai controller al middleware e dai filtri ai servizi. In ogni caso, è necessario seguire il [principio delle dipendenze esplicite](https://deviq.com/explicit-dependencies-principle/) richiedendo le dipendenze anziché crearle direttamente e usando l'inserimento di dipendenze in tutta l'applicazione. Prestare attenzione alla posizione e alla modalità di creazione diretta delle istanze delle implementazioni, in particolare dei servizi e degli oggetti che usano l'infrastruttura o presentano effetti collaterali. Preferire l'uso di astrazioni definite nell'applicazione e passate come argomenti anziché l'uso di riferimenti hardcoded a tipi di implementazione specifici.

## <a name="structuring-the-application"></a>Creazione della struttura dell'applicazione

Le applicazioni monolitiche hanno in genere un singolo punto di ingresso. In un'applicazione Web ASP.NET Core il punto di ingresso sarà il progetto Web ASP.NET Core. Tuttavia, ciò non significa che la soluzione deve essere costituita da un singolo progetto. È utile suddividere l'applicazione in livelli diversi per riflettere la separazione delle competenze. Dopo la suddivisione in livelli, è utile andare oltre le cartelle per separare i progetti per ottenere un miglior incapsulamento. L'approccio migliore per raggiungere questi obiettivi con un'applicazione ASP.NET Core è una variante dell'architettura "pulita" descritta nel capitolo 5. Seguendo questo approccio, la soluzione dell'applicazione sarà costituita da librerie separate per interfaccia utente, infrastruttura e ApplicationCore.

Oltre a questi progetti, sono inclusi anche i progetti di test separati (i test sono descritti nel capitolo 9).

Il modello a oggetti e le interfacce dell'applicazione devono trovarsi nel progetto ApplicationCore. Questo progetto avrà il minor numero possibile di dipendenze e gli altri progetti nella soluzione faranno riferimento ad esso. Le entità di business che devono essere mantenute sono definite nel progetto ApplicationCore, analogamente ai servizi che non dipendono direttamente dall'infrastruttura.

I dettagli di implementazione, ad esempio la modalità di persistenza o di invio delle notifiche a un utente, si trovano nel progetto Infrastructure. Il progetto farà riferimento a pacchetti specifici dell'implementazione, ad esempio Entity Framework Core, ma non deve esporre informazioni dettagliate su queste implementazioni all'esterno del progetto. I servizi e i repository dell'infrastruttura devono implementare interfacce definite nel progetto ApplicationCore e le relative implementazioni della persistenza sono responsabili del recupero e dell'archiviazione delle entità definite in ApplicationCore.

Il progetto dell'interfaccia utente ASP.NET Core è responsabile di tutte le competenze a livello dell'interfaccia utente, ma non deve includere la logica di business o i dettagli dell'infrastruttura. Di fatto, il progetto non deve includere alcuna dipendenza nel progetto Infrastructure in modo che non venga inserita accidentalmente alcuna dipendenza tra i due progetti. Questo obiettivo può essere raggiunto usando un contenitore DI di terze parti come Autofac, che consente di definire le regole DI nelle classi Module in ogni progetto.

Un altro approccio per disaccoppiare l'applicazione dai dettagli di implementazione consiste nel fare in modo che l'applicazione chiami i microservizi, forse distribuiti in singoli contenitori Docker. Ciò offre una separazione delle competenze e un disaccoppiamento maggiori rispetto all'utilizzo di DI tra due progetti ma comporta una maggiore complessità.

### <a name="feature-organization"></a>Organizzazione basata sulle funzionalità

Per impostazione predefinita, le applicazioni ASP.NET Core organizzano la struttura delle cartelle in modo da includere controller e visualizzazioni e spesso modelli di visualizzazione. Il codice lato client per supportare queste strutture lato server è in genere archiviato separatamente nella cartella wwwroot. Questa organizzazione, tuttavia, può creare problemi nelle applicazioni di grandi dimensioni poiché l'utilizzo di qualsiasi funzionalità specificata richiede spesso il passaggio da una cartella all'altra. Questa operazione diventa ancora più complessa con un numero più elevato di file e sottocartelle in ogni cartella richiedendo un maggior esplorazione in Esplora soluzioni. Per risolvere questo problema è possibile organizzare il codice dell'applicazione per _funzionalità_ anziché per tipo di file. Questo stile organizzativo viene in genere definito cartelle di entità geografiche o sezioni di [entità geografiche](https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc) (vedere anche: [Sezioni verticali).](https://deviq.com/vertical-slices/)

A tale scopo, ASP.NET Core MVC supporta le aree. Usando le aree è possibile creare set separati di cartelle di controller e visualizzazioni, inclusi i modelli associati, in ogni cartella Area. La figure 7-1 illustra un esempio di struttura di cartelle con aree.

![Organizzazione dell'area di esempio](./media/image7-1.png)

**Figura 7-1**. Organizzazione dell'area di esempio

Quando si usano le aree, è necessario usare gli attributi per decorare i controller con il nome dell'area a cui appartengono:

```csharp
[Area("Catalog")]
public class HomeController
{}
```

È anche necessario aggiungere il supporto delle aree alle route:

```csharp
app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(name: "areaRoute", pattern: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
});
```

Oltre al supporto incorporato per le aree, è possibile usare anche la propria struttura di cartelle e le convenzioni al posto di attributi e route personalizzate. Ciò consentirebbe di avere cartelle di funzionalità che non includano cartelle separate per le visualizzazioni, i controller e così via, creando in questo modo una gerarchia più piana e rendendo più semplice visualizzare tutti i file correlati in un'unica posizione per ogni funzionalità.

ASP.NET Core usa tipi convenzione predefiniti per controllare il comportamento. È possibile modificare o sostituire queste convenzioni. Ad esempio, è possibile creare una convenzione che ottiene automaticamente il nome della funzionalità per un controller specifico in base al relativo spazio dei nomi (che in genere è correlato alla cartella in cui si trova il controller):

```csharp
public class FeatureConvention : IControllerModelConvention
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

Specificare quindi questa convenzione come opzione quando si aggiunge il supporto per MVC all'applicazione in ConfigureServices:

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

ASP.NET Core MVC usa una convenzione anche per individuare le visualizzazioni. Questa convenzione può essere sostituita con una convenzione personalizzata in modo che le visualizzazioni vengano inserite nelle cartelle delle funzionalità (usando il nome della funzionalità specificato da FeatureConvention). È possibile ottenere ulteriori informazioni su questo approccio e scaricare un esempio funzionante dall'articolo di MSDN Magazine, [Feature Slices for ASP.NET Core MVC](https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc).

### <a name="cross-cutting-concerns"></a>Problematiche trasversali

Con l'aumento delle dimensioni delle applicazioni, diventa sempre più importante evitare i problemi di cross-cutting per eliminare la duplicazione e mantenere la coerenza. Alcuni esempi di problemi di cross-cutting nelle applicazioni ASP.NET Core sono, tra gli altri, l'autenticazione, le regole di convalida del modello, la memorizzazione nella cache dell'output e la gestione degli errori. I [filtri](/aspnet/core/mvc/controllers/filters) di ASP.NET Core MVC consentono di eseguire codice prima o dopo determinate fasi della pipeline di elaborazione della richiesta. Ad esempio, un filtro può essere eseguito prima e dopo l'associazione di modelli, prima e dopo un'azione o prima e dopo il risultato di un'azione. È anche possibile usare un filtro di autorizzazione per controllare l'accesso alla parte rimanente della pipeline. La figura 7-2 mostra l'esecuzione della richiesta attraverso i filtri, se configurati.

![La richiesta passa attraverso i filtri autorizzazione, i filtri risorse, l'associazione di modelli, i filtri azione, l'esecuzione dell'azione e la conversione del risultato dell'azione, i filtri eccezioni, i filtri risultato e l'esecuzione del risultato. All'uscita della pipeline, la richiesta viene elaborata solo dai filtri risultato e dai filtri risorse prima di diventare una risposta inviata al client.](./media/image7-2.png)

**Figura 7-2**. Richiedere l'esecuzione tramite filtri e pipeline di richieste.

I filtri vengono in genere implementati come attributi, quindi è possibile applicarli a controller o azioni (o persino a livello globale). Quando vengono aggiunti in questo modo, i filtri specificati a livello di azione sostituiscono o sono basati sui filtri specificati a livello di controller che a loro volta sostituiscono i filtri globali. È possibile ad esempio usare l'attributo \[Route\] per creare route tra i controller e le azioni. Analogamente, l'autorizzazione può essere configurata a livello di controller e quindi sostituita da singole azioni, come illustrato nell'esempio seguente:

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous] // overrides the Authorize attribute
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

Il primo metodo, Login, usa il filtro AllowAnonymous (attributo) per sostituire il filtro Authorize impostato a livello di controller. L'azione ForgotPassword (e qualsiasi altra azione nella classe che non ha un attributo AllowAnonymous) richiederà una richiesta autenticata.

È possibile usare i filtri per eliminare la duplicazione come criteri di gestione degli errori comuni delle API. Ad esempio, un criterio di API tipico consiste nel restituire una risposta NotFound alle richieste che fanno riferimento a chiavi non esistenti e una risposta BadRequest nei casi in cui la convalida del modello ha esito negativo. L'esempio seguente illustrate questi due criteri:

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

Evitare che i metodi di azione diventino troppo pieni con codice condizionale di questo tipo. Eseguire invece il pull dei criteri nei filtri che possono essere applicati quando necessario. In questo esempio, il controllo di convalida del modello, che deve essere eseguito ogni volta che un comando viene inviato all'API, può essere sostituito dall'attributo seguente:In this example, the model validation check, which should occur anytime a command is sent to the API, can be replaced by the following attribute:

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

È possibile aggiungere `ValidateModelAttribute` al progetto come dipendenza NuGet includendo il pacchetto [Ardalis.ValidateModel](https://www.nuget.org/packages/Ardalis.ValidateModel). Per le API è possibile usare l'attributo `ApiController` per applicare questo comportamento senza la necessità di un filtro `ValidateModel` separato.

Analogamente, è possibile usare un filtro per verificare l'esistenza di un record e restituire un errore 404 prima che venga eseguita l'azione, eliminando la necessità di eseguire questi controlli nell'azione. Dopo aver estratto le convenzioni comuni e aver organizzato la soluzione per separare il codice dell'infrastruttura e la logica di business dall'interfaccia utente, i metodi delle azioni MVC dovrebbero essere estremamente snelli:

```csharp
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

Per ulteriori informazioni sull'implementazione dei filtri e sul download di un esempio funzionante, vedere l'articolo di MSDN Magazine [Real-World ASP.NET Core MVC](https://docs.microsoft.com/archive/msdn-magazine/2016/august/asp-net-core-real-world-asp-net-core-mvc-filters).

> ### <a name="references--structuring-applications"></a>Riferimenti - Creazione della struttura delle applicazioni
>
> - **Aree**  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - **MSDN Magazine - Funzionalità Feature Slices per ASP.NET Core MVC**  
>   <https://docs.microsoft.com/archive/msdn-magazine/2016/september/asp-net-core-feature-slices-for-asp-net-core-mvc>
> - **Filtri**  
>   <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - **MSDN Magazine – Filtri MVC di base ASP.NET del mondo reale**  
>   <https://docs.microsoft.com/archive/msdn-magazine/2016/august/asp-net-core-real-world-asp-net-core-mvc-filters>

## <a name="security"></a>Sicurezza

La protezione delle applicazioni Web è un argomento molto ampio con numerose considerazioni. A un livello di base, per garantire la sicurezza è necessario conoscere l'identità dell'utente da cui proviene una determinata richiesta e assicurarsi che la richiesta abbia accesso solo alle risorse necessarie. L'autenticazione è il processo di confronto delle credenziali specificate con una richiesta con quelle di un archivio di dati attendibili per verificare se la richiesta deve essere trattata come proveniente da un'entità nota. L'autorizzazione è il processo di limitazione dell'accesso a determinate risorse in base all'identità utente. Un terzo aspetto relativo alla sicurezza è la protezione delle richieste dall'intercettazione da terze parti per cui è necessario [assicurarsi che l'applicazione usi SSL](/aspnet/core/security/enforcing-ssl).

### <a name="authentication"></a>Authentication

ASP.NET Core Identity è un sistema di appartenenza che è possibile usare per supportare la funzionalità di accesso per l'applicazione. Include il supporto degli account utente locali e il supporto dei provider di accesso esterni come l'account Microsoft, Twitter, Facebook, Google e altri ancora. Oltre a ASP.NET Core Identity, l'applicazione può usare l'autenticazione di Windows o un provider di identità di terze parti come [Identity Server](https://github.com/IdentityServer/IdentityServer4).

ASP.NET Core Identity è incluso nei nuovi modelli di progetto se l'opzione Account utente individuali è selezionata. Questo modello include il supporto per la registrazione, l'accesso, gli accessi esterni, le password dimenticate e funzionalità aggiuntive.

![Selezionare Singoli account utente per avere l'identità preconfigurata](./media/image7-3.png)

**Figura 7-3**. Selezionare Singoli account utente per avere Identity preconfigurata.

Il supporto di Identity è configurato in Startup, sia in ConfigureServices che in Configure:

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
    app.UseEndpoints(endpoints =>
    {
        endpoints.MapControllerRoute(name: "default", pattern: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

È importante che UseIdentity si trovi prima di UseMvc nel metodo Configure. Quando si configura Identity in ConfigureServices, è possibile notare una chiamata ad AddDefaultTokenProviders. La chiamata non è correlata ai token che possono essere usati per proteggere le connessioni Web, ma fa riferimento ai provider che creano prompt che è possibile inviare agli utenti tramite SMS o posta elettronica per la conferma dell'identità.

Per altre informazioni sulla [configurazione dell'autenticazione a due fattori](/aspnet/core/security/authentication/2fa) e l'[abilitazione di provider di accesso esterni](/aspnet/core/security/authentication/social/), vedere la documentazione ufficiale di ASP.NET Core.

### <a name="authorization"></a>Autorizzazione

La forma di autorizzazione più semplice prevede la limitazione dell'accesso per gli utenti anonimi. La limitazione può essere ottenuta semplicemente applicando l'attributo \[Authorize\] a determinati controller o azioni. Se vengono usati i ruoli, è possibile estendere ulteriormente l'attributo per limitare l'accesso agli utenti che appartengono a determinati ruoli, come illustrato di seguito:

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

In questo caso gli utenti che appartengono al ruolo HRManager o Finance o a entrambi i ruoli hanno accesso a SalaryController. Per richiedere l'appartenenza di un utente a più ruoli e non a un solo ruolo, è possibile applicare l'attributo più volte specificando ogni volta il ruolo richiesto.

La specifica di determinati set di ruoli come stringhe in diversi controller e azioni può causare una ripetizione indesiderata. È possibile configurare criteri di autorizzazione che incapsulano regole di autorizzazione e quindi specificare i criteri anziché i singoli ruoli durante l'applicazione dell'attributo \[Authorize\]:

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

Questa modalità di utilizzo dei criteri consente di suddividere i tipi di azione limitati dai ruoli o dalle regole specifiche applicate. In seguito, se si crea un nuovo ruolo che necessita dell'accesso a determinate risorse, sarà sufficiente aggiornare i criteri anziché aggiornare ogni elenco di ruoli in ogni attributo \[Authorize\].

#### <a name="claims"></a>Claims

Le attestazioni sono coppie nome-valore che rappresentano le proprietà di un utente autenticato. Ad esempio, è possibile archiviare il numero di dipendente degli utenti come attestazione. Le attestazioni possono quindi essere usate come parte dei criteri di autorizzazione. È possibile creare un criterio denominato "EmployeeOnly" che richiede l'esistenza di un'attestazione denominata "EmployeeNumber", come illustrato nell'esempio seguente:

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

Questo criterio può quindi essere usato con l'attributo \[Authorize\] per proteggere qualsiasi controller e/o azione, come descritto in precedenza.

#### <a name="securing-web-apis"></a>Protezione delle API Web

La maggior parte delle API Web deve implementare un sistema di autenticazione basato su token. L'autenticazione del token è progettata per essere scalabile e senza stato. In un sistema di autenticazione basato su token, è necessario che il client esegua prima l'autenticazione nel provider di autenticazione. Se l'autenticazione ha esito positivo, per il client viene emesso un token che è costituito semplicemente da una stringa di caratteri crittograficamente significativa. Per inviare una richiesta a un'API, il client aggiunge il token come intestazione della richiesta. Il server convalida il token individuato nell'intestazione della richiesta prima di eseguire la richiesta. La figura 7-4 illustra questo processo.

![TokenAuth](./media/image7-4.png)

**Figura 7-4.** Autenticazione basata su token per le API Web.

È possibile creare il proprio servizio di autenticazione, integrarsi con Azure AD e OAuth o implementare un servizio usando uno strumento open source come [IdentityServer](https://github.com/IdentityServer).

#### <a name="custom-security"></a>Sicurezza personalizzata

Prestare particolare attenzione alle implementazioni personalizzate della crittografia, dell'appartenenza degli utenti o del sistema di generazione di token. Esistono molte alternative commerciali e open source che nella maggior parte dei casi offrono una sicurezza migliore rispetto a quella di un'implementazione personalizzata.

> ### <a name="references--security"></a>Riferimenti - Sicurezza
>
> - **Panoramica della documentazione sulla sicurezza**  
>   https://docs.microsoft.com/aspnet/core/security/
> - **Applicazione di SSL in un'app ASP.NET Core**  
>   <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - **Introduzione a Identity**  
>   <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - **Introduzione alle autorizzazioni**  
>   <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - **Autenticazione e autorizzazione per app per le API nel servizio app di Azure**  
>   <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>
> - **Identity Server**  
>   <https://github.com/IdentityServer>

## <a name="client-communication"></a>Comunicazione con i client

Oltre a visualizzare le pagine e a rispondere alle richieste di dati tramite le API Web, le app ASP.NET Core possono comunicare direttamente con i client connessi. Questa comunicazione in uscita può usare diverse tecnologie di trasporto, tra cui la più comune sono i WebSocket. ASP.NET ASP.NET Core SignalR è una libreria che semplifica l'aggiunta della funzionalità di comunicazione da server a client in tempo reale alle applicazioni. SignalR supporta diverse tecnologie di trasporto, inclusi i WebSocket, ed elimina molti dei dettagli di implementazione specificati dallo sviluppatore.

La comunicazione con il client in tempo reale, con l'utilizzo diretto di WebSocket o altre tecniche, è utile in diversi scenari di applicazioni. Di seguito sono riportati alcuni esempi:

- Applicazioni live chat room

- Applicazioni di monitoraggio

- Aggiornamenti dello stato di processo

- Notifiche

- Applicazioni di moduli interattivi

Quando si definisce la comunicazione con i client nelle applicazioni, vengono in genere usati due componenti:

- Gestione della connessione sul lato server (hub SignalR, WebSocketManager, WebSocketHandler)

- Libreria lato client

I client non sono costituiti solo da browser. Anche le app per dispositivi mobili, le app della console e altre app native possono comunicare tramite SignalR/WebSocket. Il semplice programma seguente ripete tutto il contenuto inviato a un'applicazione chat alla console, come parte di un'applicazione di esempio WebSocketManager:

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>
        {
            Console.WriteLine($"{arguments[0]} said: {arguments[1]}");
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
}
```

Esaminare i modi in cui le applicazioni comunicano direttamente con le applicazioni client e considerare se la comunicazione in tempo reale migliorerebbe l'esperienza utente dell'app.

> ### <a name="references--client-communication"></a>Riferimenti - Comunicazione con i client
>
> - **ASP.NET Core SignalR**  
>   <https://github.com/dotnet/aspnetcore/tree/master/src/SignalR>
> - **WebSocket Manager**  
>   https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a>Quando usare la progettazione basata su domini

La progettazione basata su domini (Domain-Driven Design, DDD) è un approccio semplice alla creazione di software che pone l'attenzione sul _dominio aziendale_. Evidenzia in particolare la comunicazione e l'interazione con gli esperti dei domini aziendali che possono indicare agli sviluppatori come funziona il sistema nel mondo reale. Ad esempio, se si crea un sistema per la gestione dei titoli azionari, l'esperto del dominio potrebbe essere un agente di cambio. La progettazione basata su domini (DDD) è indirizzata alla soluzione di problemi aziendali estesi e complessi e spesso non è adatta ad applicazioni più semplici e di piccole dimensioni poiché l'investimento nella conoscenza e nella modellazione del dominio potrebbe essere eccessivo.

Quando si compila un software seguendo un approccio DDD, è necessario che il team, inclusi gli utenti e i collaboratori non tecnici, sviluppi un _linguaggio universale_ per l'area dei problemi. Ciò significa che è necessario usare la stessa terminologia per il concetto del mondo reale modellato, l'equivalente software ed eventuali strutture esistenti per il mantenimento del concetto, ad esempio le tabelle di database. Di conseguenza, i concetti descritti in linguaggio universale devono costituire la base del _modello di dominio_.

Il modello di dominio è costituito da oggetti che interagiscono tra loro per rappresentare il comportamento del sistema. Gli oggetti sono suddivisi nelle categorie seguenti:

- [Entità](https://deviq.com/entity/) che rappresentano gli oggetti con un thread di identità. Le entità sono in genere salvate in modo permanente con una chiave con cui possono essere recuperate in seguito.

- [Aggregazioni](https://deviq.com/aggregate-pattern/) che rappresentano gruppi di oggetti che devono essere salvati in modo permanente come unità.

- [Oggetti valore](https://deviq.com/value-object/) che rappresentano i concetti che possono essere confrontati mediante la somma dei valori delle relative proprietà. Ad esempio, DateRange costituito da una data di inizio e di fine.

- [Eventi del dominio](https://martinfowler.com/eaaDev/DomainEvent.html) che rappresentano operazioni eseguite all'interno del sistema di interesse ad altre parti del sistema.

Un modello di dominio DDD deve incapsulare un comportamento complesso all'interno del modello. Le entità, in particolare, non devono essere semplici raccolte di proprietà. Quando il modello di dominio non include il comportamento e rappresenta solo lo stato del sistema viene definito un [modello anemico](https://deviq.com/anemic-model/) non adatto per la progettazione DDD.

Oltre a questi tipi di modello, la progettazione DDD usa in genere un'ampia gamma di modelli:

- [Repository](https://deviq.com/repository-pattern/), per fornire l'astrazione dei dettagli di persistenza.

- [Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), per incapsulare la creazione di oggetti complessi.

- Eventi di dominio, per separare il comportamento dipendente dal comportamento di attivazione.

- [Servizi](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), per incapsulare un comportamento complesso e/o i dettagli di implementazione dell'infrastruttura.

- [Comando](https://en.wikipedia.org/wiki/Command_pattern), per separare l'invio dei comandi e l'esecuzione del comando.

- [Specifica](https://deviq.com/specification-pattern/), per incapsulare i dettagli di query.

Con la progettazione DDD è inoltre consigliabile usare l'architettura "pulita" descritta in precedenza che offre l'accoppiamento libero, l'incapsulamento e un codice che può essere facilmente verificato tramite unit test.

### <a name="when-should-you-apply-ddd"></a>Quando applicare la progettazione basata su domini (DDD)

DDD è adatto ad applicazioni di grandi dimensioni con una complessità aziendale significativa (non solo tecnica). L'applicazione deve richiedere la competenza degli esperti di dominio. Deve inoltre essere presente un comportamento significativo nel modello di dominio stesso, che rappresenta le regole business e le interazioni e non si limita all'archiviazione e al recupero dello stato corrente dei diversi record dagli archivi dati.

### <a name="when-shouldnt-you-apply-ddd"></a>Quando non applicare la progettazione basata su domini (DDD)

La progettazione DDD prevede investimenti nella modellazione, nell'architettura e nella comunicazione non sempre garantiti per le applicazioni di piccole dimensioni o le applicazioni CRUD (Create/Read/Update/Delete). Se si sceglie un approccio basato sulla progettazione DDD per l'applicazione e si scopre che il dominio ha un modello anemico senza comportamento, potrebbe essere necessario cambiare approccio. È possibile che l'applicazione non richieda la progettazione DDD oppure potrebbe essere necessario ricevere assistenza per effettuare il refactoring dell'applicazione in modo da incapsulare la logica di business nel modello di dominio anziché nel database o nell'interfaccia utente.

Un approccio ibrido potrebbe essere quello di usare la progettazione DDD solo per le aree transazionali o più complesse dell'applicazione e di non usarla per le parti più semplici CRUD o di sola lettura dell'applicazione. Ad esempio, non sono necessari i vincoli di un'aggregazione quando si eseguono query sui dati per visualizzare un report o i dati di un dashboard. Per questo tipo di requisiti è possibile avere un modello di lettura più semplice separato.

> ### <a name="references--domain-driven-design"></a>Riferimenti - Progettazione basata su domini (DDD)
>
> - **DDD in Plain English (StackOverflow Answer)** (Progettazione basata su domini (risposta StackOverflow))  
>   <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a>Distribuzione

Il processo di distribuzione di un'applicazione ASP.NET Core prevede alcuni passaggi, indipendentemente dalla posizione in cui verrà ospitata. Il primo passaggio consiste nel pubblicare l'applicazione, che può essere eseguita utilizzando il `dotnet publish` comando CLI. Viene compilata l'applicazione e tutti i file necessari per eseguire l'applicazione vengono inseriti in una cartella specificata. Per le distribuzioni da Visual Studio, questo passaggio viene eseguito automaticamente. La cartella di publish contiene i file con estensione exe e dll dell'applicazione e le relative dipendenze. Un'applicazione indipendente includerà anche una versione del runtime .NET. Le applicazioni ASP.NET Core includeranno anche i file di configurazione, gli asset client statici e le visualizzazioni MVC.

Le applicazioni ASP.NET Core sono applicazioni console che devono essere avviate all'avvio del server e riavviate in caso di arresto anomalo dell'applicazione o del server. È possibile usare un'utilità di gestione dei processi per automatizzare questo processo. Le utilità di gestione dei processi più comuni per ASP.NET Core sono Nginx e Apache in Linux e IIS o Windows Service in Windows.

Oltre a un gestore di processi, ASP.NET applicazioni Core possono utilizzare un server proxy inverso. Un server proxy inverso riceve le richieste HTTP da Internet e le inoltra a Kestrel dopo alcune operazioni di gestione preliminari. I server proxy inversi forniscono un livello di sicurezza per l'applicazione. Inoltre, poiché Kestrel non supporta l'hosting di più applicazioni sulla stessa porta, non è possibile usare tecniche come le intestazioni host per abilitare l'hosting di più applicazioni sulla stessa porta e sullo stesso indirizzo IP.

![Kestrel in Internet](./media/image7-5.png)

**Figura 7-5.** ASP.NET ospitati in Kestrel dietro un server proxy inverso

Un proxy inverso può risultare utile anche in uno scenario in cui è necessario proteggere più applicazioni con SSL e HTTPS. In questo caso è necessario configurare SSL solo per il proxy inverso. La comunicazione tra il server proxy inverso e Kestrel può avvenire su HTTP, come illustrato nella figura 7-6.

![ASP.NET ospitato dietro un server proxy inverso protetto da HTTPS](./media/image7-6.png)

**Figura 7-6**. ASP.NET ospitato dietro un server proxy inverso protetto da HTTPS

Un approccio sempre più diffuso consiste nell'ospitare l'applicazione ASP.NET Core in un contenitore Docker che può essere ospitato in locale o distribuito in Azure per l'hosting basato su cloud. Il contenitore Docker può contenere il codice dell'applicazione in esecuzione su Kestrel e può essere distribuito in un server proxy inverso, come illustrato in precedenza.

Se l'applicazione è ospitata in Azure, è possibile usare il gateway applicazione di Microsoft Azure come appliance virtuale dedicata per offrire servizi diversi. Oltre a svolgere la funzione di proxy inverso per le singole applicazioni, il gateway applicazione può offrire anche le funzionalità seguenti:

- Bilanciamento del carico HTTP

- Ripartizione del carico di lavoro SSL (SSL sono in Internet)

- SSL end-to-end

- Routing multisito (consolidare fino a 20 siti in un unico gateway applicazione)

- Web application firewall

- Supporto di WebSocket

- Diagnostica avanzata

_Altre informazioni sulle opzioni di distribuzione di Azure sono disponibili nel [capitolo 10](development-process-for-azure.md)._

> ### <a name="references--deployment"></a>Riferimenti - Distribuzione
>
> - **Panoramica sull'hosting e la distribuzione**  
>   <https://docs.microsoft.com/aspnet/core/publishing/>
> - **Quando usare Kestrel con un proxy inverso**  
>   <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - **Ospitare app ASP.NET Core in Docker**  
>   <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - **Introduzione al gateway applicazione di Azure**  
>   <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
>[Successivo](common-client-side-web-technologies.md)
>[precedente](work-with-data-in-asp-net-core-apps.md)
