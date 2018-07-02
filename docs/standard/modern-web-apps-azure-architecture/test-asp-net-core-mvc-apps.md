---
title: Testare app ASP.NET Core MVC
description: Progettare applicazioni Web moderne con ASP.NET Core e Azure | Testare app ASP.NET Core MVC
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.openlocfilehash: b22e0e109144b4abd04cd4199cfdec244d8fa7af
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106502"
---
# <a name="test-aspnet-core-mvc-apps"></a>Testare app ASP.NET Core MVC

> _"Non vi piace fare lo unit test dei vostri prodotti? Molto probabilmente non piacerà neanche ai vostri clienti."_
>  _- Anonimo-_

## <a name="summary"></a>Riepilogo

Qualsiasi software, indipendentemente dalla complessità, può generare errori imprevisti dopo che è stato modificato. È quindi assolutamente necessario sottoporre a test tutte le applicazioni che non siano banali o poco importanti. Il test manuale è il modo più lento, meno affidabile e più costoso per testare il software, ma sfortunatamente, se le applicazioni non sono progettate per l'esecuzione di test, è l'unico modo disponibile. Le applicazioni scritte secondo i principi architetturali descritti nel capitolo X devono supportare gli unit test. Le applicazioni ASP.NET Core supportano anche l'integrazione automatizzata e i test funzionali.

## <a name="kinds-of-automated-tests"></a>Tipi di test automatizzati

Esistono molti tipi di test automatizzati per le applicazioni software. Il test più semplice e di livello più basso è lo unit test. A un livello leggermente superiore si trovano i test di integrazione e i test funzionali. Altri tipi di test, come i test dell'interfaccia utente, i test di carico, test di stress e gli smoke test, non rientrano nell'ambito di questo documento.

### <a name="unit-tests"></a>Unit test

Uno unit test verifica una sola parte della logica dell'applicazione. Un modo per descrivere meglio questo tipo di test consiste nell'elencare alcune caratteristiche che non ha. Uno unit test non verifica il funzionamento del codice con le dipendenze e l'infrastruttura. Questo tipo di verifica viene effettuato dai test di integrazione. Uno unit test non verifica il framework in cui è scritto il codice: si presuppone infatti che funzioni. Se invece si rilevano problemi, è necessario segnalare un bug e scrivere codice per una soluzione alternativa. Uno unit test viene eseguito completamente in memoria e all'interno di un processo. Non comunica con il file system, con la rete o con un database. Gli unit test devono solo testare il codice.

Gli unit test interessano solo una singola unità di codice, senza dipendenze esterne. La loro esecuzione, quindi, deve essere estremamente rapida e consentire l'esecuzione di gruppi di centinaia di unit test in pochi secondi. È necessario eseguirli spesso, idealmente prima di ogni push a un repository di controllo del codice sorgente condiviso e sicuramente in corrispondenza di ogni compilazione automatizzata eseguita nel server di compilazione.

### <a name="integration-tests"></a>Test di integrazione

Incapsulare il codice che interagisce con l'infrastruttura, ad esempio con database e file system, è una buona idea, ma una parte di codice di questo tipo sarà comunque presente e sarà probabilmente necessario testarla. È anche necessario verificare che i livelli del codice interagiscano nel modo previsto quando le dipendenze dell'applicazione sono completamente risolte. Questo è compito dei test di integrazione. I test di integrazione tendono a essere più lenti e più difficili da configurare rispetto agli unit test, perché spesso dipendono da dipendenze esterne e dall'infrastruttura. Di conseguenza, è consigliabile evitare di testare all'interno di test di integrazione le parti di codice che possono essere testate tramite unit test. Se è possibile testare uno scenario specifico con uno unit test, è consigliabile usare uno unit test. Se non è possibile, è consigliabile prendere in considerazione l'uso di un test di integrazione.

Rispetto agli unit test, i test di integrazione prevedono una configurazione più complessa e procedure di disinstallazione più elaborate. Un test di integrazione eseguito a fronte un database, ad esempio, deve prevedere il modo di riportare il database a uno stato noto prima dell'esecuzione di ogni test. Man mano che vengono aggiunti nuovi test e lo schema del database cambia, questi script di test tendono ad aumentare di dimensioni e complessità. In molti sistemi di grandi dimensioni non è pratico eseguire gruppi completi di test di integrazione nelle workstation degli sviluppatori prima di archiviare le modifiche nel controllo del codice sorgente condiviso. In questi casi, è possibile eseguire i test di integrazione in un server di compilazione.

La classe di implementazione LocalFileImageService implementa la logica per il recupero e la restituzione dei byte di un file di immagine da una cartella specifica, dato un ID:

```csharp
public class LocalFileImageService : IImageService
{
    private readonly IHostingEnvironment _env;
    public LocalFileImageService(IHostingEnvironment env)
    {
        _env = env;
    }
    public byte[] GetImageBytesById(int id)
    {
        try
        {
            var contentRoot = _env.ContentRootPath + "//Pics";
            var path = Path.Combine(contentRoot, id + ".png");
            return File.ReadAllBytes(path);
        }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

### <a name="functional-tests"></a>Test funzionali

I test di integrazione vengono scritti dal punto di vista dello sviluppatore per verificare che alcuni componenti del sistema interagiscano correttamente. I test funzionali vengono scritti dal punto di vista dell'utente e verificano la correttezza del sistema in base ai relativi requisiti. Il brano seguente presenta un'analogia utile a chiarire il concetto di test funzionale rispetto agli unit test:

> "Spesso lo sviluppo di un sistema viene paragonato alla costruzione di una casa. Questa analogia non è completamente corretta, ma è possibile estenderla per consentire la comprensione delle differenze tra unit test e test funzionali. Uno unit test può essere paragonato a un ispettore che visita il cantiere di un'abitazione. L'ispettore concentra l'attenzione sulle varie parti interne della casa: le fondamenta, gli infissi, l'impianto elettrico, quello idraulico e così via, per assicurarsi (testare) che le parti della casa funzionino correttamente e in modo sicuro, ovvero soddisfino le normative edilizie (il codice di compilazione). In questo scenario, i test funzionali sono paragonabili al proprietario della casa che visita questo stesso cantiere. Il proprietario presuppone che gli impianti interni della casa funzionino come si deve, dato che di questo si occupa l'ispettore. Il proprietario concentra l'attenzione sulla qualità della vita in quella casa, preoccupandosi dell'aspetto della casa stessa, dell'adeguatezza delle dimensioni delle stanze, della capacità della casa di soddisfare le esigenze della famiglia e dell'orientamento delle finestre, che devono lasciar entrare il sole del mattino. Il proprietario esegue il test funzionale della casa. Il suo punto di vista è quello dell'utente finale. L'ispettore esegue gli unit test della casa. Il suo punto di vista è quello del compilatore."

Fonte: [Unit Testing versus Functional Tests](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html) (Unit test e test funzionali)

Gli sviluppatori possono sbagliare in due modi: creando una cosa nel modo sbagliato o creando la cosa sbagliata. Gli unit test consentono di verificare che si stia creando qualcosa nel modo corretto. I test funzionali consentono di verificare che si stia creando la cosa giusta.

Dato che i test funzionali operano a livello di sistema, possono richiedere un certo grado di automazione dell'interfaccia utente. Analogamente ai test di integrazione, in genere usano anche un certo tipo di infrastruttura di test. Ciò li rende più lenti e meno solidi degli unit test e dei test di integrazione. Per avere la certezza che il sistema funzioni come gli utenti si aspettano, è necessario avere solo il numero di test funzionali strettamente necessario.

### <a name="testing-pyramid"></a>Piramide dei test

La piramide dei test, un esempio della quale è illustrato nella Figura 9-1, è stato trattato da Martin Fowler.

![](./media/image9-1.png)

Figura 9-1 Piramide dei test

I diversi livelli della piramide e le dimensioni relative rappresentano i diversi tipi di test e il numero di test che è consigliabile scrivere per l'applicazione. Come si può notare, è consigliabile avere una base ampia di unit test, supportata da un livello di test di integrazione di dimensioni inferiori, con un livello di dimensioni ancora inferiori di test funzionali. Ogni livello in linea di principio deve contenere solo test che non possono essere eseguiti in modo adeguato a un livello inferiore. Tenere presente la piramide dei test quando si deve decidere il tipo di test necessario per uno scenario specifico.

### <a name="what-to-test"></a>Cosa testare

Un problema comune agli sviluppatori che non hanno dimestichezza con la scrittura di test automatizzati è decidere che cosa testare. Un buon punto di partenza è il test della logica condizionale. Ovunque sia presente un metodo il cui comportamento cambia in base a un'istruzione condizionale (if-else, switch e così via), è necessario creare almeno un paio di test che confermino la correttezza del comportamento per determinate condizioni. Se il codice prevede condizioni di errore, è consigliabile scrivere almeno un test per il percorso corretto attraverso il codice (senza errori) e almeno un test per il percorso non corretto (con errori o risultati atipici) per confermare che l'applicazione si comporti come previsto in caso di errori. Provare infine a concentrarsi sul test delle operazioni che possono non riuscire, piuttosto che su metriche quali il code coverage. Un code coverage maggiore è meglio di un code coverage minore, in genere, ma il tempo impiegato a scrivere qualche test in più per un metodo molto complesso e di importanza critica è di solito meglio impiegato rispetto al tempo speso a scrivere test per le proprietà automatiche per migliorare la metrica di code coverage.

## <a name="organizing-test-projects"></a>Organizzazione dei progetti di test

È possibile organizzare i progetti di test nel modo che si ritiene più efficiente per le proprie esigenze. È consigliabile suddividere i test per tipo (unit test, test di integrazione) e per oggetto del test (progetto, spazio dei nomi). Se questa suddivisione debba essere realizzata tramite cartelle all'interno di un unico progetto di test o tramite più progetti di test è una decisione che viene presa a livello di progettazione. Un solo progetto è la soluzione più semplice, ma per progetti di grandi dimensioni con molti test o per eseguire set diversi di test più facilmente, è consigliabile avere più progetti di test diversi. Molti team organizzano i progetti di test in base al progetto sottoposto a test. Per le applicazioni che non si limitano a un numero ridotto di progetti, questa soluzione può comportare un numero elevato di progetti di test, soprattutto se questi vengono ancora suddivisi in base al tipo di test che contengono. Un approccio di compromesso può essere di avere un progetto per tipo di test per applicazione, con cartelle all'interno dei progetti di test per indicare il progetto e la classe sottoposti a test.

Un approccio comune consiste nell'organizzare i progetti dell'applicazione in una cartella 'src' e i progetti di test dell'applicazione in una cartella 'tests' parallela. Nel caso si ritenga utile questo tipo di organizzazione, Visual Studio consente di creare cartelle della soluzione corrispondenti.

![](./media/image9-2.png)

Figura 9-2 Organizzazione dei test nella soluzione

È possibile usare qualsiasi framework di test si preferisca. Il framework xUnit, in cui sono scritti tutti i test di ASP.NET Core ed EF Core, funziona in modo efficiente. È possibile aggiungere un progetto di test xUnit in Visual Studio usando il modello illustrato nella figura 9-3 oppure usando il comando dotnet new xunit nell'interfaccia della riga di comando.

![](./media/image9-3.png)

Figura 9-3 aggiungere un progetto di test xUnit in Visual Studio

### <a name="test-naming"></a>Denominazione dei test

È consigliabile assegnare ai test nomi coerenti che indichino il tipo di test eseguito. Un approccio molto efficace è assegnare alle classi di test nomi basati sulla classe e sul metodo testato. Il risultato è un numero elevato di classi di test, ma la funzione di ogni test è estremamente chiara. Con il nome della classe di test impostato per identificare la classe e il metodo da sottoporre a test, è possibile usare il nome di ogni metodo di test per specificare il comportamento sottoposto a test. Deve essere incluso il comportamento previsto e l'eventuale input o gli eventuali presupposti che devono generare questo comportamento. Ecco alcuni esempi di nomi di test:

- CatalogControllerGetImage.CallsImageServiceWithId

- CatalogControllerGetImage.LogsWarningGivenImageMissingException

- CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess

- CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException

Una variante di questo approccio consiste nel terminare ogni nome di classe di test con "Should" e nel modificare leggermente i tempi verbali:

- CatalogControllerGetImage**Should**.**Call**ImageServiceWithId

- CatalogControllerGetImage**Should**.**Log**WarningGivenImageMissingException

Alcuni team trovano il secondo approccio più chiaro, anche se leggermente più prolisso. In ogni caso, è consigliabile usare una convenzione di denominazione che consenta di comprendere il comportamento del test. In questo modo, se uno o più test hanno esito negativo, risulta evidente dai nomi quali casi non sono riusciti. Evitare di denominare i test in modo generico, ad esempio ControllerTests.Test1, perché questi nomi non hanno alcun valore quando vengono visualizzati nei risultati dei test.

Se si segue una convenzione di denominazione simile a quella illustrata sopra, che genera molte classi di test di piccole dimensioni, è consigliabile organizzare ulteriormente i test tramite cartelle e spazi dei nomi. La figura 9-4 illustra un approccio di organizzazione dei test per cartella all'interno di diversi progetti di test.

![](./media/image9-4.png)

**Figura 9-4.** Organizzazione delle classi di test per cartella in base alla classe da testare.

È ovvio che, se per una classe di applicazione specifica vengono testati molti metodi (e quindi esistono molte classi di test), può essere utile inserirli in una cartella corrispondente alla classe stessa. Questo tipo di organizzazione è analogo all'organizzazione di file in cartelle in un altro contesto. Se si hanno più di tre o quattro file correlati in una cartella contenente molti altri file, è spesso utile spostare i primi in una sottocartella specifica.

## <a name="unit-testing-aspnet-core-apps"></a>Unit test di app ASP.NET Core

In un'applicazione ASP.NET Core ben progettata, la maggior parte della complessità e della logica di business viene incapsulata in entità di business e in una varietà di servizi. L'app ASP.NET Core MVC stessa, con i controller, i filtri, i ViewModel e le visualizzazioni, deve richiedere un numero molto ridotto di unit test. Buona parte delle funzionalità di un'azione specifica si trova all'esterno del metodo di azione stesso. Il test del funzionamento del routing o la gestione globale degli errori non può essere eseguita in modo efficiente con uno unit test. Analogamente, non è possibile eseguire unit test di filtri, inclusi i filtri di convalida di modelli, di autenticazione e di autorizzazione. Senza queste origini di comportamento, la maggior parte dei metodi di azione sarebbero incredibilmente piccoli e delegherebbero la maggior parte delle proprie funzioni a servizi che possono essere testati indipendentemente dal controller che li usa.

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

Lo unit test di questo metodo è reso difficile dalla dipendenza diretta da System.IO.File, usato per leggere dal file system. È possibile testare questo comportamento per assicurarsi che funzioni come previsto, ma facendo questo con file reali si esegue un test di integrazione. Vale la pena di notare che non è possibile testare la route di questo metodo. Fra poco si vedrà come eseguire questa operazione con un test funzionale.

Se non è possibile eseguire direttamente lo unit test del comportamento del file system e non è possibile testare la route, cosa è possibile testare? Dopo aver effettuato il refactoring per rendere possibile l'esecuzione di unit test, si possono individuare alcuni test case e comportamenti mancanti, ad esempio la gestione degli errori. Che cosa fa il metodo quando non trova un file? Cosa deve fare? In questo esempio, il metodo sottoposto a refactoring ha l'aspetto seguente:

```csharp
[HttpGet("[controller]/pic/{id}")\]
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

\_logger e \_imageService sono entrambi inseriti come dipendenze. È ora possibile verificare che lo stesso ID che viene passato al metodo di azione venga passato a \_imageService, e che i byte risultanti vengano restituiti come parte di FileResult. È anche possibile verificare che la registrazione degli errori venga eseguita come previsto e che venga restituito un risultato NotFound se l'immagine manca, presupponendo che questo rappresenti un comportamento importante dell'applicazione, in altre parole, che non sia solo codice temporaneo aggiunto dallo sviluppatore per diagnosticare un problema. La logica effettiva del file è stata spostata in un servizio di implementazione separato ed è stata migliorata perché venga restituita un'eccezione specifica dell'applicazione in caso di mancanza di un file. È possibile testare questa implementazione in modo indipendente, usando un test di integrazione.

## <a name="integration-testing-aspnet-core-apps"></a>Test di integrazione di app ASP.NET Core

Questo servizio usa IHostingEnvironment, così come faceva il codice CatalogController prima del refactoring in un servizio separato. Poiché questo era l'unica parte di codice nel controller che usava IHostingEnvironment, tale dipendenza è stata rimossa dal costruttore di CatalogController.

Per verificare il corretto funzionamento di questo servizio, è necessario creare un file di immagine di test noto e verificare che il servizio lo restituisca in risposta a un input specifico. È necessario prestare attenzione a non usare oggetti fittizi per il comportamento effettivamente da testare (in questo caso, la lettura dal file system). Gli oggetti fittizi, tuttavia, possono comunque rivelarsi utili per impostare i test di integrazione. In questo caso, è possibile simulare IHostingEnvironment in modo che il relativo ContentRootPath punti alla cartella che si intende usare per l'immagine di test. La classe di test di integrazione funzionante completa è illustrata di seguito:

```csharp
public class LocalFileImageServiceGetImageBytesById
{
    private byte[] _testBytes = new byte[] { 0x01, 0x02, 0x03 };
    private readonly Mock<IHostingEnvironment> _mockEnvironment = new Mock<IHostingEnvironment>();
    private int _testImageId = 123;
    private string _testFileName = "123.png";
    public LocalFileImageServiceGetImageBytesById()
    {
        // create folder if necessary
        Directory.CreateDirectory(Path.Combine(GetFileDirectory(), "Pics"));
        string filePath = GetFilePath(_testFileName);
        System.IO.File.WriteAllBytes(filePath, _testBytes);
        _mockEnvironment.SetupGet<string>(m => m.ContentRootPath).Returns(GetFileDirectory());
    }
    private string GetFilePath(string fileName)
    {
        return Path.Combine(GetFileDirectory(), "Pics", fileName);
        }
            private string GetFileDirectory()
        {
            var location = System.Reflection.Assembly.GetEntryAssembly().Location;
            return Path.GetDirectoryName(location);
        }

        [Fact]
        public void ReturnsFileContentResultGivenValidId()
        {
            var fileService = new LocalFileImageService(_mockEnvironment.Object);
            var result = fileService.GetImageBytesById(_testImageId);
            Assert.Equal(_testBytes, result);
        }
    }
```

> [!NOTE]
> Il test di per sé è molto semplice: la maggior parte del codice è necessaria per configurare il sistema e creare l'infrastruttura di test (in questo caso, un file effettivo da leggere dal disco). Questa è una situazione tipica per i test di integrazione, che spesso richiedono una configurazione più complessa rispetto agli unit test.

## <a name="functional-testing-aspnet-core-apps"></a>Test funzionale di app ASP.NET Core

Per applicazioni ASP.NET Core, la classe TestServer rende la scrittura di test funzionali piuttosto facile. Per configurare un TestServer è possibile usare un WebHostBuilder, esattamente come si fa normalmente per l'applicazione. Questo WebHostBuilder deve essere configurato come l'host reale dell'applicazione, ma è possibile modificarne qualsiasi aspetto per facilitare il test. Nella maggior parte dei casi, lo stesso TestServer viene riusato per molti test case. È quindi possibile incapsularlo in un metodo riutilizzabile (ad esempio in una classe di base):

```csharp
public abstract class BaseWebTest
{
    protected readonly HttpClient _client;
    protected string _contentRoot;

    public BaseWebTest()
    {
        _client = GetClient();
    }

    protected HttpClient GetClient()
    {
        var startupAssembly = typeof(Startup).GetTypeInfo().Assembly;
        _contentRoot = GetProjectPath("src", startupAssembly);
        var builder = new WebHostBuilder()
        .UseContentRoot(_contentRoot)
        .UseStartup<Startup>();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

Il metodo GetProjectPath restituisce semplicemente il percorso fisico del progetto Web (scaricare la soluzione di esempio). In questo caso WebHostBuilder specifica semplicemente dove si trova la radice del contenuto per l'applicazione Web e fa riferimento alla stessa classe Startup usata dall'applicazione Web reale. Per usare TestServer, inviare richieste a questo usando il tipo System.Net.HttpClient standard. TestServer espone un metodo CreateClient utile che offre un client preconfigurato pronto per effettuare richieste all'applicazione in esecuzione in TestServer. Usare questo client (impostato sul membro protected \_client del test di base precedente) nella scrittura di test funzionali dell'applicazione ASP.NET Core:

```csharp
public class CatalogControllerGetImage : BaseWebTest
{
    [Fact]
    public async Task ReturnsFileContentResultGivenValidId()
    {
        var testFilePath = Path.Combine(_contentRoot, "pics//1.png");
        var expectedFileBytes = File.ReadAllBytes(testFilePath);
        var response = await _client.GetAsync("/catalog/pic/1");
        response.EnsureSuccessStatusCode();
        var streamResponse = await response.Content.ReadAsStreamAsync();
        byte[] byteResult;
        using (var ms = new MemoryStream())
        {
            streamResponse.CopyTo(ms);
            byteResult = ms.ToArray();
        }
        Assert.Equal(expectedFileBytes, byteResult);
    }
}
```

Questo test funzionale interessa tutto lo stack dell'applicazione ASP.NET Core MVC, inclusi tutti i middleware, i filtri, i binder e così via eventualmente presenti. Verifica che una route specifica ("/catalog/pic/1") restituisca la matrice di byte prevista per un file in una posizione nota. Questa verifica viene eseguita senza la configurazione di un server Web reale ed è quindi possibile evitare gran parte degli inconvenienti che l'uso di un server Web reale può comportare (ad esempio, problemi con le impostazioni del firewall). I test funzionali eseguiti su TestServer sono in genere più lenti rispetto ai test di integrazione e agli unit test, ma sono molto più veloci rispetto a test eseguiti attraverso la rete per un server Web.

>[!div class="step-by-step"]
[Precedente](work-with-data-in-asp-net-core-apps.md)
[Successivo](development-process-for-azure.md)
