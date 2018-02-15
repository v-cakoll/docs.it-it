---
title: Test ASP.NET Core applicazioni MVC
description: Architettura di moderne applicazioni Web con ASP.NET Core e Azure | Test ASP.NET Core applicazioni MVC
author: ardalis
ms.author: wiwagn
ms.date: 10/08/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d23d0accc33fb8335dff602d6e1d6c8689972906
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="test-aspnet-core-mvc-apps"></a>Test ASP.NET Core applicazioni MVC

> _"Se non si desidera che gli unit test del prodotto, molto probabilmente i clienti non desiderano eseguire il test, sia."_
> _ - Anonimo:

## <a name="summary"></a>Riepilogo

Software di qualsiasi complessità può non riuscire in modo imprevisto in risposta alle modifiche. Di conseguenza, è necessario per tutte le applicazioni più comuni (o meno critiche) eseguire test dopo aver apportato modifiche. Il test manuale è il più lento, modo meno affidabile e più costoso per testare il software. Sfortunatamente, se le applicazioni non sono progettate per essere sottoposti a test, può essere l'unico mezzo disponibile. Le applicazioni scritte seguenti principi architetturali disposti nel capitolo X devono essere unità testabili e delle applicazioni ASP.NET Core supportano automatizzate e anche eseguire test funzionali.

## <a name="kinds-of-automated-tests"></a>Tipi di test automatizzati

Esistono molti tipi di test automatizzati per le applicazioni software. La più semplice, test di livello più basso è lo unit test. A un livello leggermente superiore sono presenti test funzionali e test di integrazione. Altri tipi di test, come i test dell'interfaccia utente, test di carico, test di stress e smoke test, non rientrano nell'ambito di questo documento.

### <a name="unit-tests"></a>Unit test

Uno unit test di verifica di una singola parte della logica dell'applicazione. Una possibile descrivere ulteriormente elencando alcune delle operazioni che non lo è. Non testare uno unit test come i codice funziona correttamente con dipendenze o infrastruttura, quali integration test sono per. Uno unit test non verifica il framework per scrivere il codice in: è necessario presupporre che funziona o, se si ritiene non, inviare un bug e code di una soluzione alternativa. Uno unit test viene eseguito completamente in memoria e nel processo. Comunica con il file system, la rete o un database. Unit test solo i test del codice.

Unit test, grazie al fatto che solo una singola unità di codice, senza dipendenze esterne, eseguono il test deve essere eseguita molto rapidamente. Pertanto, deve essere in grado di eseguire gruppi di test di centinaia di unit test in pochi secondi. È necessario eseguirli frequentemente, idealmente prima di ogni push a un repository del controllo del codice sorgente condiviso e certamente con ogni compilazione automatica nel server di compilazione.

### <a name="integration-tests"></a>Test di integrazione

Sebbene sia consigliabile per incapsulare il codice che interagisce con infrastruttura come ad esempio database e file System, sarà comunque possibile parte del codice e si desidera eseguire il test probabilmente. Inoltre, è necessario verificare che i livelli del codice interagiscono nel modo previsto quando sono completamente risolte le dipendenze dell'applicazione. Questa è la responsabilità di test di integrazione. Test di integrazione tendono a essere più lenta e più difficili da configurare rispetto agli unit test, perché spesso dipendono dell'infrastruttura e le dipendenze esterne. Di conseguenza, è consigliabile evitare di operazioni che potrebbero essere test con unit test in test di integrazione di test. Se è possibile testare uno scenario specifico con uno unit test, è necessario eseguirne il test con uno unit test. Se non è possibile, utilizzare un test di integrazione.

Test di integrazione sono spesso contenuti più complessi e disinstallazione procedure di configurazione di unit test. Ad esempio, un test di integrazione che va inserito in un database effettivo sarà necessario un modo per riportare il database in uno stato noto prima di ciascuna esecuzione dei test. Come vengono aggiunti nuovi test e lo schema del database di produzione si evolve, questi test script verrà tendono ad aumentare le dimensioni e complessità. In molti sistemi di grandi dimensioni, non è pratico eseguire completi gruppi di test di integrazione sulle workstation degli sviluppatori prima di archiviare le modifiche apportate al controllo del codice sorgente condiviso. In questi casi, è possibile eseguire test di integrazione in un server di compilazione.

La classe di implementazione LocalFileImageService implementa la logica per il recupero e restituisce i byte di un file di immagine da una cartella particolare assegnata un id:

```cs
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
```

### <a name="functional-tests"></a>Test funzionali

Test di integrazione vengono scritti dal punto di vista dello sviluppatore, verificare che alcuni componenti del sistema interagiscano correttamente. Test funzionali vengono scritte dal punto di vista dell'utente e verificare la correttezza del sistema in base ai relativi requisiti. L'estratto seguente offre un'utile analogia come preoccuparsi di test funzionali, rispetto agli unit test:

> "È paragonato più volte lo sviluppo di un sistema per la compilazione di una casa. Durante questa analogia non è abbastanza corretta, è possibile estenderlo per quanto riguarda le differenze tra unit test e test funzionale. Unit test è analogo a un controllo di compilazione, visitare il sito di costruzione di un'abitazione. Giorgio è incentrato sui vari sistemi interni dell'abitazione, foundation, frame, elettrica, plumbing e così via. Verificare che (test), che le parti della casa verranno correttamente e in modo sicuro, vale a dire, soddisfare il codice di compilazione. Test funzionali in questo scenario sono analoghe al proprietario di immobile citato visitare il sito stesso di costruzione. Si presuppone che i sistemi interni si comporterà in modo appropriato, che il controllo di compilazione sta eseguendo un'operazione. Il proprietario di immobile citato è incentrata su cosa sarà simile a live questa casa. Egli si riferisce l'aspetto della casa, sono i vari room dimensioni familiarità, la casa esigenze della famiglia, sono windows in un luogo ideale per rilevare il sole mattina. Il proprietario di immobile citato esegue test funzionali in casa. Ha un punto di vista dell'utente. Il controllo di compilazione esegue unit test in casa. Ha prospettiva del generatore."

Origine: [Unit test e test funzionali](http://www.softwaretestingtricks.com/2007/01/unit-testing-versus-functional-tests.html)

Sto carattere indicando "usate dagli sviluppatori, di errore in due modi: creiamo la cosa errata o è compilare l'elemento corretto." Verificare che si sta compilando il diritto di cosa; unit test test funzionali verificare che si sta compilando il giusto.

Poiché i test funzionali operano a livello di sistema, richiedere un certo grado di automazione interfaccia utente. Ad esempio test di integrazione, e in genere funzionano con un tipo di infrastruttura di test anche. Questo li rende più lenta e più fragile di unit test e integrazione test. È necessario solo come molti test funzionali che è necessario avere la certezza che il sistema funzioni come gli utenti.

### <a name="testing-pyramid"></a>Test a piramide

Martin Fowler è parlato della piramide test, un esempio di cui è illustrato nella figura 9-1.

![](./media/image9-1.png)

Figura 9-1 test a piramide

I diversi livelli di piramide e le dimensioni relative, rappresentano i diversi tipi di test e il numero è consigliabile scrivere per l'applicazione. Come si può notare, l'indicazione è che una grande quantità di unit test, supportato da un livello inferiore di test di integrazione, con un livello ancora più piccolo di test funzionali. Ogni livello idealmente può contenere solo test che non è possibile eseguire in modo adeguato a un livello inferiore. Tenere presente della piramide test quando si sta tentando di decidere quale tipo di test è necessario per un determinato scenario.

### <a name="what-to-test"></a>Cosa accade a Test

Con il contenuto eseguire il test è a presentarsi un problema comune per gli sviluppatori che non hanno dimestichezza con la scrittura di test automatizzati. Un buon punto di partenza è per testare la logica condizionale. In qualsiasi punto si dispone di un metodo con un comportamento che le modifiche in base a un'istruzione condizionale (if-else, cambiare, e così via), è possibile richiamare almeno un paio di test che confermano il comportamento corretto per determinate condizioni. Se il codice contiene le condizioni di errore, è consigliabile scrivere almeno un test per il percorso"i" tramite il codice (con nessun errore) e almeno un test per il percorso"sad" (con errori o risultati atipici) per confermare che l'applicazione si comporta come previsto in caso di errori. Infine, provare a concentrarsi sulle operazioni che è possono eseguire il test, piuttosto che sulla metrica relativa a come il code coverage. Altre code coverage è migliore di minore, in genere. Tuttavia, la scrittura di un numero limitato di test più di un metodo molto complesso e business-critical è in genere un migliore utilizzo di tempo rispetto alla scrittura di test per le proprietà automatiche solo migliorare la metrica di code coverage dei test.

## <a name="organizing-test-projects"></a>Organizzazione dei progetti di Test

Tuttavia i risultati migliori per l'utente, è possono organizzare i progetti di test. È consigliabile separare i test per tipo (unit test di, test di integrazione) e per cui il test (dal progetto, dallo spazio dei nomi). Se questa separazione costituita da cartelle all'interno di un progetto di test singolo o più progetti di test, è una decisione di progettazione. Un progetto è più semplice, ma per progetti di grandi dimensioni con molti test, o per eseguire più facilmente diversi set di test, è consigliabile disporre di più progetti di test diversi. Molti team per organizzare i progetti di test basati sul progetto sottoposto a test, che per le applicazioni con più progetti può comportare un numero elevato di progetti di test, soprattutto se è ancora suddividere questi in base alle quali sono di tipo di test in ogni progetto. Un compromesso è che un progetto per ogni tipo di test, per ogni applicazione, con le cartelle all'interno di progetti di test per indicare il progetto e classe, sottoposto a test.

Un approccio comune consiste nell'organizzare i progetti di applicazione in una cartella 'src' e i progetti di test dell'applicazione in una cartella parallel 'test'. È possibile creare cartelle della soluzione corrispondente in Visual Studio, se utile questa organizzazione.

![](./media/image9-2.png)

Figura 9-2 di organizzazione dei Test nella soluzione

È possibile utilizzare qualsiasi framework di test desiderato. Il framework xUnit funziona e cosa è scritte in tutti i test di ASP.NET Core e componenti di base di Entity Framework. È possibile aggiungere un progetto di test xUnit in Visual Studio usando il modello illustrato nella figura 9-3, oppure da CLI utilizzando dotnet nuovo xunit.

![](./media/image9-3.png)

Nella figura 9-3 aggiungere un progetto di Test xUnit in Visual Studio

### <a name="test-naming"></a>Denominazione di test

I test in modo coerente, è necessario assegnare un nome con nomi che indicano lo scopo di ogni test. Un approccio che ho avuto successo con è alle classi di test di nome in base di classe e metodo che sottoposto a test. Di conseguenza, molte classi di test di piccole dimensioni, ma rende inoltre estremamente deselezionare che cos'è responsabili per ogni test. Con il nome di classe di test impostato per identificare la classe e il metodo da sottoporre a test, è possibile utilizzare il nome del metodo di test per specificare il comportamento sottoposto a test. Deve includere il comportamento previsto e alcun input o i presupposti che devono produrre questo comportamento. Alcuni esempi di nomi di test:

-   CatalogControllerGetImage.CallsImageServiceWithId

-   CatalogControllerGetImage.LogsWarningGivenImageMissingException

-   CatalogControllerGetImage.ReturnsFileResultWithBytesGivenSuccess

-   CatalogControllerGetImage.ReturnsNotFoundResultGivenImageMissingException

Una variante di questo approccio termina con "Deve" nome di ogni classe di test e modifica i tempi verbali leggermente:

-   CatalogControllerGetImage**deve**. **Chiamare**ImageServiceWithId

-   CatalogControllerGetImage**deve**. **Log**WarningGivenImageMissingException

Alcuni team di trovare il secondo approccio più chiaro, denominazione tuttavia leggermente più dettagliata. In ogni caso, provare a utilizzare una convenzione di denominazione che consente di comprendere il comportamento di test, in modo che quando uno o più test hanno esito negativo, è evidente dai nomi dei quali casi non sono riuscita. Evitare di denominare è test massima, ad esempio ControllerTests.Test1, perché queste offrono alcun valore, quando vengono visualizzate nei risultati del test.

Se si segue una convenzione di denominazione come quella illustrata sopra che produce molte classi di test di piccole dimensioni, è consigliabile organizzare ulteriormente i test utilizzando le cartelle e spazi dei nomi. Nella figura 9-4 viene illustrato un approccio per l'organizzazione dei test dalla cartella all'interno dei progetti di test diversi.

![](./media/image9-4.png)

**Nella figura 9-4.** Organizzazione delle classi di test dalla cartella basato sulla classe da testare.

Naturalmente, se una classe particolare applicazione dispone di molti metodi testati e pertanto molte classi di test, può essere utile inserire in una cartella corrispondente alla classe dell'applicazione. Questa organizzazione non è diversa rispetto a come è possibile organizzare i file in cartelle in un' posizione. Se si dispone di più di tre o quattro i file in una cartella che contiene molti altri file correlati, è spesso utile per spostarli nella rispettiva sottocartella.

## <a name="unit-testing-aspnet-core-apps"></a>Unit test ASP.NET Core App

In un'applicazione ASP.NET di base ben progettata, la maggior parte delle complessità e della logica di business verrà incapsulata in entità aziendali e una varietà di servizi. L'app ASP.NET MVC di base, con il controller, i filtri, ViewModel e viste, deve richiedere un numero esiguo di unit test. La maggior parte delle funzionalità di un'azione specificata si trova all'esterno del metodo di azione stessa. Verificare se il routing funziona correttamente, o la gestione degli errori globale non può essere eseguita in modo efficace con uno unit test. Analogamente, eventuali filtri, compresa l'autenticazione e la convalida del modello e i filtri di autorizzazione non può essere sottoposta a unit test. Senza queste origini di comportamento, la maggior parte dei metodi di azione devono essere facilmente piccoli, delega la maggior parte delle attività di servizi che possono essere testati indipendente del controller in cui vengono utilizzati.

In alcuni casi è necessario eseguire il refactoring del codice in ordine a unit test. Spesso ciò comporta l'identificazione astrazioni e mediante l'inserimento di dipendenza per accedere l'astrazione nel codice di cui che si desidera testare, anziché scrivere codice direttamente per l'infrastruttura. Si consideri, ad esempio, questo metodo di azione semplice per la visualizzazione di immagini:

```cs
[HttpGet("[controller]/pic/{id}")]
public IActionResult GetImage(int id)
{
    var contentRoot = _env.ContentRootPath + "//Pics";
    var path = Path.Combine(contentRoot, id + ".png");
    Byte[] b = System.IO.File.ReadAllBytes(path);
    return File(b, "image/png");
}
```

Unit test di questo metodo è difficile da relativa dipendenza diretta su System.IO, che verrà utilizzato per leggere dal file system. È possibile verificare questo comportamento per assicurarsi che funzioni come previsto, ma in questo modo i file reali è un test di integrazione. Vale la pena notare route di questo metodo non è possibile testare, si vedrà come eseguire questa operazione con un test funzionale a breve.

Se non è possibile unit test del comportamento del file system direttamente e non è possibile testare la route, cosa è per eseguire il test? Anche dopo il refactoring per rendere possibile l'esecuzione di unit test, si potrebbe scoprire che alcuni test case e il comportamento mancano, ad esempio la gestione degli errori. Quali è il metodo? quando non viene trovato un file Cosa è necessario fare? In questo esempio, il metodo sottoposto a refactoring simile al seguente:

```cs
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

Il \_logger e \_entrambi imageService vengono inseriti come dipendenze. Ora è possibile verificare che lo stesso id che viene passato al metodo di azione viene passato per il \_imageService, e restituite come parte di FileResult i byte risultanti. È possibile verificare anche che la registrazione degli errori è in corso come previsto e che viene restituito un risultato di NotFound se l'immagine è manca, presupponendo che il comportamento di importanti dell'applicazione (ovvero, non solo codice temporaneo lo sviluppatore aggiunto per diagnosticare un problema). La logica effettiva del file è stato spostato in un servizio separato di implementazione ed è stata migliorata per restituire un'eccezione specifiche dell'applicazione per il caso di un file mancante. È possibile testare questa implementazione in modo indipendente, utilizzando un test di integrazione.

## <a name="integration-testing-aspnet-core-apps"></a>Integrazione di applicazioni ASP.NET Core test

```cs
    }
        catch (FileNotFoundException ex)
        {
            throw new CatalogImageMissingException(ex);
        }
    }
}
```

Questo servizio utilizza IHostingEnvironment, come il CatalogController codice ha prima del refactoring in un servizio separato. Poiché questo è l'unico codice nel controller utilizzato IHostingEnvironment, tale dipendenza è stata rimossa dal costruttore del CatalogController.

Per verificare il corretto funzionamento di questo servizio, è necessario creare un file di immagine test nota e verificare che il servizio restituisce viene fornito un input specifico. È necessario prestare attenzione per non utilizzare gli oggetti fittizi al comportamento effettivamente da testare (in questo caso, la lettura dal file system). Oggetti fittizi, tuttavia, possono rivelarsi utili per impostare i test di integrazione. In questo caso, è possibile simulare IHostingEnvironment in modo che il relativo ContentRootPath punta alla cartella che si intende utilizzare per l'immagine di test. La classe di test di integrazione funzionante completo è illustrata di seguito:

```cs
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
> la maggior parte del codice che il test è molto semplice: è necessaria configurare il sistema e creare l'infrastruttura di test (in questo caso, un file da leggere dal disco). È tipico per i test di integrazione, che spesso richiedono operazioni di configurazione più complessa rispetto agli unit test.

## <a name="functional-testing-aspnet-core-apps"></a>Applicazioni ASP.NET Core test funzionali

Per le applicazioni ASP.NET Core, la classe TestServer consente test funzionale piuttosto facili da scrivere. Configurare un TestServer utilizzando un WebHostBuilder, esattamente come si farebbe per l'applicazione. Questo WebHostBuilder deve essere configurato come host reale dell'applicazione, ma è possibile modificare tutti gli aspetti che facilitare il testing. La maggior parte dei casi, riutilizzare la stessa TestServer per molti test case, in modo possibile incapsulare un metodo riutilizzabili (ad esempio in una classe di base):

```cs
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
        .UseStartup&lt;Startup&gt;();
        var server = new TestServer(builder);
        var client = server.CreateClient();
        return client;
    }
}
```

GetProjectPath (metodo) restituisce semplicemente il percorso fisico per il progetto web (download soluzione di esempio). Il WebHostBuilder in questo caso semplicemente specifica dove è la radice del contenuto per l'applicazione web e fa riferimento alla stessa classe di avvio che viene utilizzata l'applicazione web reale. Per utilizzare il TestServer, utilizzare il tipo System.Net.HttpClient standard per effettuare richieste a esso. TestServer espone un metodo CreateClient utile che fornisce un client configurato in precedenza che è pronto per effettuare richieste per l'applicazione in esecuzione sul TestServer. Si utilizza questo client (impostato su protetto \_membro di client del test di base precedente) durante la scrittura di test funzionali dell'applicazione ASP.NET di base:

```cs
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

Questo test funzionale esercita lo stack dell'applicazione ASP.NET MVC di base completo, inclusi tutti i middleware, filtri, gestori di associazione e così via che possono essere presenti. Verifica che un dato route ("/ pic/catalogo/1") restituisce la matrice di byte previsto per un file in un percorso noto. A tale scopo senza dover configurare un server web reale e pertanto consente di evitare gran parte del vulnerabilità che possono verificarsi (ad esempio, problemi con le impostazioni del firewall) del server per il test con un web reale. Test funzionali eseguite su TestServer sono in genere più lento rispetto all'integrazione e unit test, ma sono molto più veloci rispetto ai test che verrebbe eseguito in rete per un server web.

>[!div class="step-by-step"]
[Precedente] [Avanti] (sviluppo-processo-per-azure.md) (work-with-data-in-asp-net-core-apps.md)
