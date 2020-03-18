---
title: Testare app ASP.NET Core MVC
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Testare app ASP.NET Core MVC
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: 2b347442c4a9b7b6cf912ec461248f901dc45417
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147491"
---
# <a name="test-aspnet-core-mvc-apps"></a>Testare app ASP.NET Core MVC

> *"Non vi piace fare lo unit test dei vostri prodotti? Molto probabilmente non piacerà neanche ai vostri clienti."*
 > \_- Anonimo-

Qualsiasi software, indipendentemente dalla complessità, può generare errori imprevisti dopo che è stato modificato. È quindi assolutamente necessario sottoporre a test tutte le applicazioni che non siano banali o poco importanti. Il test manuale è il modo più lento, meno affidabile e più costoso per testare il software, ma se le applicazioni non sono progettate per essere testabili, è l'unico modo disponibile. Le applicazioni scritte per seguire i principi architettonici delineati nel [capitolo 4](architectural-principles.md) devono essere unit testable. ASP.NET applicazioni core supportano l'integrazione automatizzata e i test funzionali.

## <a name="kinds-of-automated-tests"></a>Tipi di test automatizzati

Esistono molti tipi di test automatizzati per le applicazioni software. Il test più semplice e di livello più basso è lo unit test. A un livello leggermente superiore, sono disponibili test di integrazione e test funzionali. Altri tipi di test, ad esempio test dell'interfaccia utente, test di carico, test di stress e test di fumo, non rientrano nell'ambito di questo documento.

### <a name="unit-tests"></a>Unit test

Uno unit test verifica una sola parte della logica dell'applicazione. Un modo per descrivere meglio questo tipo di test consiste nell'elencare alcune caratteristiche che non ha. Uno unit test non verifica il funzionamento del codice con le dipendenze e l'infrastruttura. Questo tipo di verifica viene effettuato dai test di integrazione. Uno unit test non verifica il framework in cui è scritto il codice: si presuppone infatti che funzioni. Se invece si rilevano problemi, è necessario segnalare un bug e scrivere codice per una soluzione alternativa. Uno unit test viene eseguito completamente in memoria e all'interno di un processo. Non comunica con il file system, con la rete o con un database. Gli unit test devono solo testare il codice.

Gli unit test interessano solo una singola unità di codice, senza dipendenze esterne. La loro esecuzione, quindi, deve essere estremamente rapida e consentire l'esecuzione di gruppi di centinaia di unit test in pochi secondi. È necessario eseguirli spesso, idealmente prima di ogni push a un repository di controllo del codice sorgente condiviso e sicuramente in corrispondenza di ogni compilazione automatizzata eseguita nel server di compilazione.

### <a name="integration-tests"></a>Test di integrazione

Incapsulare il codice che interagisce con l'infrastruttura, ad esempio con database e file system, è una buona idea, ma una parte di codice di questo tipo sarà comunque presente e sarà probabilmente necessario testarla. È anche necessario verificare che i livelli del codice interagiscano nel modo previsto quando le dipendenze dell'applicazione sono completamente risolte. Questo è compito dei test di integrazione. I test di integrazione tendono a essere più lenti e più difficili da configurare rispetto agli unit test, perché spesso dipendono da dipendenze esterne e dall'infrastruttura. Di conseguenza, è consigliabile evitare di testare all'interno di test di integrazione le parti di codice che possono essere testate tramite unit test. Se è possibile testare uno scenario specifico con uno unit test, è consigliabile usare uno unit test. Se non è possibile, è consigliabile prendere in considerazione l'uso di un test di integrazione.

Rispetto agli unit test, i test di integrazione prevedono una configurazione più complessa e procedure di disinstallazione più elaborate. Un test di integrazione eseguito a fronte un database, ad esempio, deve prevedere il modo di riportare il database a uno stato noto prima dell'esecuzione di ogni test. Man mano che vengono aggiunti nuovi test e lo schema del database cambia, questi script di test tendono ad aumentare di dimensioni e complessità. In molti sistemi di grandi dimensioni non è pratico eseguire gruppi completi di test di integrazione nelle workstation degli sviluppatori prima di archiviare le modifiche nel controllo del codice sorgente condiviso. In questi casi, è possibile eseguire i test di integrazione in un server di compilazione.

### <a name="functional-tests"></a>Test funzionali

I test di integrazione vengono scritti dal punto di vista dello sviluppatore per verificare che alcuni componenti del sistema interagiscano correttamente. I test funzionali vengono scritti dal punto di vista dell'utente e verificano la correttezza del sistema in base ai relativi requisiti. Il brano seguente presenta un'analogia utile a chiarire il concetto di test funzionale rispetto agli unit test:

> "Spesso lo sviluppo di un sistema viene paragonato alla costruzione di una casa. Questa analogia non è completamente corretta, ma è possibile estenderla per consentire la comprensione delle differenze tra unit test e test funzionali. Uno unit test può essere paragonato a un ispettore che visita il cantiere di un'abitazione. L'ispettore concentra l'attenzione sulle varie parti interne della casa: le fondamenta, gli infissi, l'impianto elettrico, quello idraulico e così via, per assicurarsi (testare) che le parti della casa funzionino correttamente e in modo sicuro, ovvero soddisfino le normative edilizie (il codice di compilazione). In questo scenario, i test funzionali sono paragonabili al proprietario della casa che visita questo stesso cantiere. Il proprietario presuppone che gli impianti interni della casa funzionino come si deve, dato che di questo si occupa l'ispettore. Il proprietario concentra l'attenzione sulla qualità della vita in quella casa, preoccupandosi dell'aspetto della casa stessa, dell'adeguatezza delle dimensioni delle stanze, della capacità della casa di soddisfare le esigenze della famiglia e dell'orientamento delle finestre, che devono lasciar entrare il sole del mattino. Il proprietario esegue il test funzionale della casa. Il suo punto di vista è quello dell'utente finale. L'ispettore esegue gli unit test della casa. Il suo punto di vista è quello del compilatore."

Fonte: [Unit Testing versus Functional Tests](https://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html) (Unit test e test funzionali)

Gli sviluppatori possono sbagliare in due modi: creando una cosa nel modo sbagliato o creando la cosa sbagliata. Gli unit test consentono di verificare che si stia creando qualcosa nel modo corretto. I test funzionali consentono di verificare che si stia creando la cosa giusta.

Dato che i test funzionali operano a livello di sistema, possono richiedere un certo grado di automazione dell'interfaccia utente. Analogamente ai test di integrazione, in genere usano anche un certo tipo di infrastruttura di test. Ciò li rende più lenti e meno solidi degli unit test e dei test di integrazione. Per avere la certezza che il sistema funzioni come gli utenti si aspettano, è necessario avere solo il numero di test funzionali strettamente necessario.

### <a name="testing-pyramid"></a>Piramide dei test

La piramide dei test, un esempio della quale è illustrato nella Figura 9-1, è stato trattato da Martin Fowler.

![Piramide dei test](./media/image9-1.png)

**Figura 9-1**. Piramide dei test

I diversi livelli della piramide e le dimensioni relative rappresentano i diversi tipi di test e il numero di test che è consigliabile scrivere per l'applicazione. Come si può notare, è consigliabile avere una base ampia di unit test, supportata da un livello di test di integrazione di dimensioni inferiori, con un livello di dimensioni ancora inferiori di test funzionali. Ogni livello in linea di principio deve contenere solo test che non possono essere eseguiti in modo adeguato a un livello inferiore. Tenere presente la piramide dei test quando si deve decidere il tipo di test necessario per uno scenario specifico.

### <a name="what-to-test"></a>Cosa testare

Un problema comune agli sviluppatori che non hanno dimestichezza con la scrittura di test automatizzati è decidere che cosa testare. Un buon punto di partenza è il test della logica condizionale. Ovunque si disponga di un metodo con un comportamento che cambia in base a un'istruzione condizionale (if-else, switch e così via), si dovrebbe essere in grado di venire con almeno un paio di test che confermano il comportamento corretto per determinate condizioni. Se il codice prevede condizioni di errore, è consigliabile scrivere almeno un test per il percorso corretto attraverso il codice (senza errori) e almeno un test per il percorso non corretto (con errori o risultati atipici) per confermare che l'applicazione si comporti come previsto in caso di errori. Provare infine a concentrarsi sul test delle operazioni che possono non riuscire, piuttosto che su metriche quali il code coverage. Un code coverage maggiore è meglio di un code coverage minore, in genere, Tuttavia, la scrittura di alcuni altri test di un metodo complesso e business-critical è in genere un uso migliore del tempo rispetto alla scrittura di test per le proprietà automatiche solo per migliorare le metriche di code coverage di test.

## <a name="organizing-test-projects"></a>Organizzazione dei progetti di test

È possibile organizzare i progetti di test nel modo che si ritiene più efficiente per le proprie esigenze. È consigliabile suddividere i test per tipo (unit test, test di integrazione) e per oggetto del test (progetto, spazio dei nomi). Se questa suddivisione debba essere realizzata tramite cartelle all'interno di un unico progetto di test o tramite più progetti di test è una decisione che viene presa a livello di progettazione. Un solo progetto è la soluzione più semplice, ma per progetti di grandi dimensioni con molti test o per eseguire set diversi di test più facilmente, è consigliabile avere più progetti di test diversi. Molti team organizzano i progetti di test in base al progetto sottoposto a test. Per le applicazioni che non si limitano a un numero ridotto di progetti, questa soluzione può comportare un numero elevato di progetti di test, soprattutto se questi vengono ancora suddivisi in base al tipo di test che contengono. Un approccio di compromesso può essere di avere un progetto per tipo di test per applicazione, con cartelle all'interno dei progetti di test per indicare il progetto e la classe sottoposti a test.

Un approccio comune consiste nell'organizzare i progetti dell'applicazione in una cartella 'src' e i progetti di test dell'applicazione in una cartella 'tests' parallela. Nel caso si ritenga utile questo tipo di organizzazione, Visual Studio consente di creare cartelle della soluzione corrispondenti.

![Testare l'organizzazione nella soluzioneTest organization in your solution](./media/image9-2.png)

**Figura 9-2**. Testare l'organizzazione nella soluzioneTest organization in your solution

È possibile usare qualsiasi framework di test si preferisca. Il framework xUnit, in cui sono scritti tutti i test di ASP.NET Core ed EF Core, funziona in modo efficiente. È possibile aggiungere un progetto di test xUnit in Visual Studio utilizzando il `dotnet new xunit`modello illustrato nella Figura 9-3 o dalla riga di comando utilizzando .

![Aggiungere un progetto xUnit Test in Visual StudioAdd an xUnit Test Project in Visual Studio](./media/image9-3.png)

**Figura 9-3**. Aggiungere un progetto xUnit Test in Visual StudioAdd an xUnit Test Project in Visual Studio

### <a name="test-naming"></a>Denominazione dei test

Assegnare un nome ai test in modo coerente, con nomi che indicano le operazioni eseguite da ogni test. Un approccio molto efficace è assegnare alle classi di test nomi basati sulla classe e sul metodo testato. Il risultato è un numero elevato di classi di test, ma la funzione di ogni test è estremamente chiara. Con il nome della classe di test impostato per identificare la classe e il metodo da sottoporre a test, è possibile usare il nome di ogni metodo di test per specificare il comportamento sottoposto a test. Deve essere incluso il comportamento previsto e l'eventuale input o gli eventuali presupposti che devono generare questo comportamento. Ecco alcuni esempi di nomi di test:

- `CatalogControllerGetImage.CallsImageServiceWithId`

- `CatalogControllerGetImage.LogsWarningGivenImageMissingException`

- `CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess`

- `CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException`

Una variante di questo approccio consiste nel terminare ogni nome di classe di test con "Should" e nel modificare leggermente i tempi verbali:

- `CatalogControllerGetImage`**Dovrebbe**`.`**chiamare**`ImageServiceWithId`

- `CatalogControllerGetImage`**Dovrebbe**`.`**Log**`WarningGivenImageMissingException`

Alcuni team trovano il secondo approccio più chiaro, anche se leggermente più prolisso. In ogni caso, è consigliabile usare una convenzione di denominazione che consenta di comprendere il comportamento del test. In questo modo, se uno o più test hanno esito negativo, risulta evidente dai nomi quali casi non sono riusciti. Evitare di denominare i test in modo vago, ad esempio ControllerTests.Test1, in quanto non offrono alcun valore quando vengono visualizzati nei risultati dei test.

Se si segue una convenzione di denominazione simile a quella illustrata sopra, che genera molte classi di test di piccole dimensioni, è consigliabile organizzare ulteriormente i test tramite cartelle e spazi dei nomi. La figura 9-4 illustra un approccio di organizzazione dei test per cartella all'interno di diversi progetti di test.

![Organizzazione delle classi di test per cartella in base alla classe testata](./media/image9-4.png)

**Figura 9-4.** Organizzazione delle classi di test per cartella in base alla classe da testare.

Se una particolare classe di applicazione dispone di molti metodi sottoposti a test (e quindi molte classi di test), può essere opportuno inserirli in una cartella corrispondente alla classe dell'applicazione. Questo tipo di organizzazione è analogo all'organizzazione di file in cartelle in un altro contesto. Se si hanno più di tre o quattro file correlati in una cartella contenente molti altri file, è spesso utile spostare i primi in una sottocartella specifica.

## <a name="unit-testing-aspnet-core-apps"></a>Unit test di app ASP.NET Core

In un'applicazione ASP.NET Core ben progettata, la maggior parte della complessità e della logica di business viene incapsulata in entità di business e in una varietà di servizi. L'app ASP.NET Core MVC stessa, con i controller, i filtri, i ViewModel e le visualizzazioni, deve richiedere un numero molto ridotto di unit test. Buona parte delle funzionalità di un'azione specifica si trova all'esterno del metodo di azione stesso. Il test del funzionamento del routing o la gestione globale degli errori non può essere eseguita in modo efficiente con uno unit test. Analogamente, tutti i filtri, inclusi i filtri di convalida e autenticazione e autorizzazione del modello, non possono essere sottoposti a unit test con un metodo di azione di destinazione di test. Senza queste origini di comportamento, la maggior parte dei metodi di azione sarebbero incredibilmente piccoli e delegherebbero la maggior parte delle proprie funzioni a servizi che possono essere testati indipendentemente dal controller che li usa.

In alcuni casi, per eseguire lo unit test del codice è necessario effettuare il refactoring di quest'ultimo. Spesso ciò comporta l'identificazione di astrazioni e l'uso dell'inserimento di dipendenze per accedere all'astrazione nel codice che si vuole testare, anziché la scrittura di codice direttamente a fronte dell'infrastruttura. Si consideri ad esempio, questo semplice metodo di azione per la visualizzazione di immagini:

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

Il testing unità di questo metodo è reso difficile dalla dipendenza diretta da `System.IO.File`, usato per leggere dal file system. È possibile testare questo comportamento per assicurarsi che funzioni come previsto, ma facendo questo con file reali si esegue un test di integrazione. Si noti che non è possibile applicare uno unit test alla route di questo metodo. Più avanti si vedrà come eseguire questa operazione con un test funzionale.

Se non è possibile eseguire direttamente lo unit test del comportamento del file system e non è possibile testare la route, cosa è possibile testare? Dopo aver effettuato il refactoring per rendere possibile l'esecuzione di unit test, si possono individuare alcuni test case e comportamenti mancanti, ad esempio la gestione degli errori. Che cosa fa il metodo quando non trova un file? Cosa deve fare? In questo esempio, il metodo sottoposto a refactoring ha l'aspetto seguente:

```csharp
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    byte[] imageBytes;
    try
    {
        imageBytes = _imageService.GetImageBytesById(id);
    }
    catch (CatalogImageMissingException ex)
    {
        _logger.LogWarning($"No image found for id: {id}");
        return NotFound();
    }
    return File(imageBytes, "image/png");
}
```

`_logger`e `_imageService` sono entrambi iniettati come dipendenze. A questo punto è possibile verificare che lo stesso `_imageService`ID passato al metodo di azione venga passato a e che i byte risultanti vengano restituiti come parte di FileResult. È anche possibile verificare che la registrazione `NotFound` degli errori si verifichi come previsto e che venga restituito un risultato se l'immagine non è presente, presupponendo che si tratti di un comportamento importante dell'applicazione, ovvero non solo del codice temporaneo aggiunto dallo sviluppatore per diagnosticare un problema. La logica effettiva del file è stata spostata in un servizio di implementazione separato ed è stata migliorata perché venga restituita un'eccezione specifica dell'applicazione in caso di mancanza di un file. È possibile testare questa implementazione in modo indipendente, usando un test di integrazione.

Nella maggior parte dei casi è opportuno usare i gestori di eccezioni globali nei controller, per ridurre al minimo la quantità di codice e di conseguenza la necessità di esecuzione di unit test. È consigliabile eseguire la maggior parte dei test di azioni dei controller mediante i test funzionali e la classe `TestServer` descritta di seguito.

## <a name="integration-testing-aspnet-core-apps"></a>Test di integrazione di app ASP.NET Core

La maggior parte dei test di integrazione nelle app ASP.NET Core dovrebbe riguardare test dei servizi e degli altri tipi di implementazione definiti nel progetto di infrastruttura. Ad esempio, è possibile [verificare che EF Core abbia completato l'aggiornamento e il recupero dei dati previsti](https://docs.microsoft.com/ef/core/miscellaneous/testing/) da classi di accesso di dati che si trovano nel progetto Infrastructure. Il modo migliore per verificare che il progetto ASP.NET Core MVC funzioni correttamente è l'esecuzione di test funzionali sull'app in esecuzione in un host di test.

## <a name="functional-testing-aspnet-core-apps"></a>Test funzionale di app ASP.NET Core

Per le applicazioni ASP.NET Core, la classe `TestServer` semplifica notevolmente la scrittura di test funzionali. È possibile `TestServer` configurare un utilizzando un `WebHostBuilder` (o `HostBuilder`) direttamente (come si fa normalmente per l'applicazione) o con il `WebApplicationFactory` tipo (disponibile dalla versione 2.1). È consigliabile cercare la corrispondenza più esatta possibile tra l'host di test e l'host di produzione, in modo che i test abbiano un comportamento simile a quello dell'app in produzione. La classe `WebApplicationFactory` è utile per configurare ContentRoot di TestServer, che viene usata da ASP.NET Core per trovare una risorsa statica come Views.

È possibile generare test funzionali semplici creando una classe di test che implementa IClassFixture \<WebApplicationFactoryTEntry\<>>, dove TEntry è la classe Startup dell'applicazione Web. In questo modo, la fixture di test può creare un client usando il metodo CreateClient della factory:

```cs
public class BasicWebTests : IClassFixture<WebApplicationFactory<Startup>>
{
    protected readonly HttpClient _client;

    public BaseWebTest(WebApplicationFactory<Startup> factory)
    {
        _client = factory.CreateClient();
    }

    // write tests that use _client
}
```

Spesso, prima dell'esecuzione di ogni test è necessario eseguire un'ulteriore configurazione del sito, ad esempio la configurazione dell'applicazione per l'uso di un archivio dati in memoria e il seeding dell'applicazione con i dati di test. A tale scopo, è necessario creare una sottoclasse di WebApplicationFactory\<TEntry> ed eseguire l'override del metodo ConfigureWebHost. L'esempio seguente è tratto dal progetto FunctionalTests di eShopOnWeb e viene usato come parte dei test sull'applicazione Web principale.

```cs
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Identity;
using Microsoft.AspNetCore.Mvc.Testing;
using Microsoft.EntityFrameworkCore;
using Microsoft.eShopWeb.Infrastructure.Data;
using Microsoft.eShopWeb.Infrastructure.Identity;
using Microsoft.eShopWeb.Web;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Logging;
using System;

namespace Microsoft.eShopWeb.FunctionalTests.Web
{
    public class WebTestFixture : WebApplicationFactory<Startup>
    {
        protected override void ConfigureWebHost(IWebHostBuilder builder)
        {
            builder.UseEnvironment("Testing");

            builder.ConfigureServices(services =>
            {
                 services.AddEntityFrameworkInMemoryDatabase();

                // Create a new service provider.
                var provider = services
                    .AddEntityFrameworkInMemoryDatabase()
                    .BuildServiceProvider();

                // Add a database context (ApplicationDbContext) using an in-memory
                // database for testing.
                services.AddDbContext<CatalogContext>(options =>
                {
                    options.UseInMemoryDatabase("InMemoryDbForTesting");
                    options.UseInternalServiceProvider(provider);
                });

                services.AddDbContext<AppIdentityDbContext>(options =>
                {
                    options.UseInMemoryDatabase("Identity");
                    options.UseInternalServiceProvider(provider);
                });

                // Build the service provider.
                var sp = services.BuildServiceProvider();

                // Create a scope to obtain a reference to the database
                // context (ApplicationDbContext).
                using (var scope = sp.CreateScope())
                {
                    var scopedServices = scope.ServiceProvider;
                    var db = scopedServices.GetRequiredService<CatalogContext>();
                    var loggerFactory = scopedServices.GetRequiredService<ILoggerFactory>();

                    var logger = scopedServices
                        .GetRequiredService<ILogger<WebTestFixture>>();

                    // Ensure the database is created.
                    db.Database.EnsureCreated();

                    try
                    {
                        // Seed the database with test data.
                        CatalogContextSeed.SeedAsync(db, loggerFactory).Wait();

                        // seed sample user data
                        var userManager = scopedServices.GetRequiredService<UserManager<ApplicationUser>>();
                        var roleManager = scopedServices.GetRequiredService<RoleManager<IdentityRole>>();
                        AppIdentityDbContextSeed.SeedAsync(userManager, roleManager).Wait();
                    }
                    catch (Exception ex)
                    {
                        logger.LogError(ex, $"An error occurred seeding the " +
                            "database with test messages. Error: {ex.Message}");
                    }
                }
            });
        }
    }
}
```

I test possono usare questa WebApplicationFactory personalizzata per creare un client e formulare quindi le richieste all'applicazione usando questa istanza del client. L'applicazione avrà effettuato il seeding dei dati utilizzabili come parte delle asserzioni del test. Il test seguente verifica che la home page dell'applicazione eShopOnWeb si carichi correttamente e includa un elenco di prodotti già aggiunto all'applicazione come parte dei dati iniziali.

```cs
using Microsoft.eShopWeb.FunctionalTests.Web;
using System.Net.Http;
using System.Threading.Tasks;
using Xunit;

namespace Microsoft.eShopWeb.FunctionalTests.WebRazorPages
{
    [Collection("Sequential")]
    public class HomePageOnGet : IClassFixture<WebTestFixture>
    {
        public HomePageOnGet(WebTestFixture factory)
        {
            Client = factory.CreateClient();
        }

        public HttpClient Client { get; }

        [Fact]
        public async Task ReturnsHomePageWithProductListing()
        {
            // Arrange & Act
            var response = await Client.GetAsync("/");
            response.EnsureSuccessStatusCode();
            var stringResponse = await response.Content.ReadAsStringAsync();

            // Assert
            Assert.Contains(".NET Bot Black Sweatshirt", stringResponse);
        }
    }
}
```

Questo test funzionale interessa tutto lo stack dell'applicazione ASP.NET Core MVC / Razor Pages, inclusi tutti i middleware, i filtri, i binder e così via eventualmente presenti. Verifica che una determinata route ("/") restituisca il codice di stato riuscito e l'output HTML previsti. Questa verifica viene eseguita senza la configurazione di un server Web reale ed è quindi possibile evitare gran parte degli inconvenienti che l'uso di un server Web reale può comportare (ad esempio, problemi con le impostazioni del firewall). I test funzionali eseguiti su TestServer sono in genere più lenti rispetto ai test di integrazione e agli unit test, ma sono molto più veloci rispetto a test eseguiti attraverso la rete per un server Web. È consigliabile usare test funzionali per garantire che lo stack front-end dell'applicazione funzioni come previsto. Questi test sono particolarmente utili quando si trova la duplicazione nei controller o nelle pagine e la si risolve aggiungendo filtri. In teoria questo refactoring non modifica il comportamento dell'applicazione e ciò sarà verificabile tramite un gruppo di test funzionali.

> ### <a name="references--test-aspnet-core-mvc-apps"></a>Riferimenti: testare app ASP.NET Core MVC
>
> - **Test in ASP.NET CoreTesting in ASP.NET Core** \
>   <https://docs.microsoft.com/aspnet/core/testing/>
> - **Convenzione di denominazione degli unit test** \
>   <https://ardalis.com/unit-test-naming-convention>
> - **Test di EF Core** \
>   <https://docs.microsoft.com/ef/core/miscellaneous/testing/>
> - **Test di integrazione in ASP.NET Core** \
>   <https://docs.microsoft.com/aspnet/core/test/integration-tests>

>[!div class="step-by-step"]
>[Successivo](work-with-data-in-asp-net-core-apps.md)
>[precedente](development-process-for-azure.md)
