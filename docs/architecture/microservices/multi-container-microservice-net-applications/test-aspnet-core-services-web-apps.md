---
title: Test delle app Web e dei servizi ASP.NET di base
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Esplorare un'architettura per il test delle app Web e dei servizi ASP.NET di base all'interno di contenitori.
ms.date: 01/30/2020
ms.openlocfilehash: f66d6184d913405c9372904f8072dda1dbfbe6ac
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988232"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Test delle app Web e dei servizi ASP.NET di base

I controller sono un componente essenziale di qualsiasi servizio API ASP.NET Core e applicazione Web MVC ASP.NET. Di conseguenza è importante verificare che funzionino correttamente nell'applicazione. I test automatizzati eseguono questa verifica e rilevano gli errori dei controller prima che questi raggiungano la fase di produzione.

È necessario testare il comportamento del controller in base a input valido o non validi ed eseguire il test delle risposte del controller in base ai risultati dell'operazione di business effettuata. Tuttavia, è necessario avere i seguenti tipi di test nei microservizi:

- Unit test. Garantiscono il funzionamento previsto dei singoli componenti dell'applicazione. Le asserzioni testano l'API componente.

- Test di integrazione. Garantiscono il funzionamento previsto delle interazioni tra componenti rispetto a elementi esterni, come i database. Le asserzioni possono testare l'API componente, l'interfaccia utente o gli effetti collaterali di azioni come input/output nei database, registrazione e così via.

- Test funzionali per ogni microservizio. Questi assicurano che l'applicazione funzioni come previsto dal punto di vista dell'utente.

- Test di servizio. Garantiscono l'esecuzione del test dei casi d'uso dei servizi end-to-end, tra cui il test simultaneo di più servizi. Per questo tipo di test, è necessario preparare prima l'ambiente. In questo caso, ciò significa avviare i servizi, ad esempio usando il comando docker-compose up.

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementazione di unit test per le API Web ASP.NET Core

Lo unit test prevede l'esecuzione di test su una parte di un'applicazione isolandola dall'infrastruttura e dalle dipendenze. Quando si sottopone a unit test la logica del controller, si verifica solo il contenuto di una singola azione o metodo e non il comportamento delle relative dipendenze o del framework. Gli unit test non rilevano i problemi dell'interazione tra componenti: a questo scopo esistono i test di integrazione.

Quando si sottopongono a unit test le azioni del controller, è importante concentrarsi esclusivamente sul funzionamento del relativo controller. Uno unit test del controller consente di evitare, ad esempio, filtri, routing o associazione di modelli (il mapping dei dati di richiesta a un elemento ViewModel o DTO). Gli unit test risultano in genere facili da creare e rapidi da eseguire, perché verificano un solo aspetto. Un set di unit test ben organizzato può essere eseguito spesso senza sovraccarichi eccessivi.

Gli unit test vengono implementati in base ai framework di test come xUnit.net, MSTest, Moq o NUnit. Per l'applicazione di esempio eShopOnContainers, useremo xUnit.

Quando si scrive uno unit test per un controller API Web, si crea direttamente un'istanza della classe controller usando la nuova parola chiave in C\#, in modo che il test venga eseguito il più velocemente possibile. L'esempio seguente illustra come eseguire questa operazione usando [xUnit](https://xunit.github.io/) come framework di test.

```csharp
[Fact]
public async Task Get_order_detail_success()
{
    //Arrange
    var fakeOrderId = "12";
    var fakeOrder = GetFakeOrder();

    //...

    //Act
    var orderController = new OrderController(
        _orderServiceMock.Object,
        _basketServiceMock.Object,
        _identityParserMock.Object);

    orderController.ControllerContext.HttpContext = _contextMock.Object;
    var actionResult = await orderController.Detail(fakeOrderId);

    //Assert
    var viewResult = Assert.IsType<ViewResult>(actionResult);
    Assert.IsAssignableFrom<Order>(viewResult.ViewData.Model);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementazione dei test funzionali e di integrazione per ogni microservizio

Come già indicato, i test di integrazione e i test funzionali hanno scopi e obiettivi diversi. Tuttavia, la modalità di implementazione di entrambi durante il test dei controller ASP.NET Core è simile, dunque questa sezione è incentrata sui test di integrazione.

Il test di integrazione garantisce che i componenti di un'applicazione funzionino correttamente quando assemblati. ASP.NET Core supporta i test di integrazione con framework di unit test e un host Web di test predefinito che può essere usato per gestire le richieste senza sovraccarico di rete.

A differenza degli unit test, i test di integrazione comportano spesso preoccupazioni relative all'infrastruttura dell'applicazione, ad esempio il database, il file system, le risorse di rete o le richieste e risposte Web. Gli unit test usano dati falsi o oggetti fittizi al posto di queste preoccupazioni, ma lo scopo dei test di integrazione è confermare il funzionamento previsto del sistema, dunque è inutile usare dati falsi oppure oggetti fittizi. Si includerà piuttosto l'infrastruttura, come l'accesso al database o la chiamata di un servizio da altri servizi.

Visto che esercitano segmenti di codice più grandi rispetto agli unit test e si basano sugli elementi dell'infrastruttura, i test di integrazione tendono a essere notevolmente più lenti rispetto agli unit test. Di conseguenza, è consigliabile limitare il numero di test di integrazione da scrivere ed eseguire.

ASP.NET Core include un host Web di test incorporato che può essere utilizzato per gestire le richieste HTTP senza sovraccarico di rete, il che significa che è possibile eseguire tali test più velocemente rispetto a quando si utilizza un host Web reale. L'host Web di test (TestServer) è disponibile in un componente NuGet come Microsoft.AspNetCore.TestHost. Può essere aggiunto ai progetti di test di integrazione e usato per ospitare le applicazioni ASP.NET Core.

Come si può notare nel codice seguente, quando si creano test di integrazione per i controller ASP.NET Core, si crea l'istanza dei controller attraverso l'host di test. Ciò è paragonabile a una richiesta HTTP, ma viene eseguita più rapidamente.

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a>Risorse aggiuntive

- **Steve Smith. Controller di test** (ASP.NET Core)
    [https://docs.microsoft.com/aspnet/core/mvc/controllers/testing](/aspnet/core/mvc/controllers/testing)

- **Steve Smith. Test di integrazione** (ASP.NET Core)
    [https://docs.microsoft.com/aspnet/core/test/integration-tests](/aspnet/core/test/integration-tests)

- **Unit test in .NET Core con dotnet test** \
    [https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test](../../../core/testing/unit-testing-with-dotnet-test.md)

- **xUnit.net**. Sito ufficiale. \
    <https://xunit.github.io/>

- **Nozioni di base sui unit test.** \
    [https://docs.microsoft.com/visualstudio/test/unit-test-basics](/visualstudio/test/unit-test-basics)

- **Moq**. Repository GitHub. \
    <https://github.com/moq/moq>

- **NUnit**. Sito ufficiale. \
    <https://www.nunit.org/>

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Implementazione di test di servizio in un'applicazione a più contenitori

Come indicato in precedenza, quando si testano applicazioni a più contenitori, tutti i microservizi devono essere eseguiti all'interno dell'host Docker o del cluster di contenitori. I test di servizio end-to-end che includono più operazioni che coinvolgono diversi microservizi richiedono la distribuzione e l'avvio dell'intera applicazione nell'host Docker con l'esecuzione del comando docker-compose up (o con un meccanismo analogo, se si usa un agente di orchestrazione). Quando l'intera applicazione e tutti i relativi servizi saranno in esecuzione, sarà possibile eseguire i test funzionali e di integrazione end-to-end.

Sono possibili alcuni approcci. Nel file docker-compose.yml usato per distribuire l'applicazione, a livello di soluzione è possibile espandere il punto di ingresso e usare [dotnet test](../../../core/tools/dotnet-test.md). È anche possibile usare un altro file Compose che esegua i test nell'immagine specificata come destinazione. Se per i test di integrazione si usa un altro file Compose che include i microservizi e i database nei contenitori, ci si assicura di ripristinare sempre lo stato originale dei dati correlati prima di eseguire i test.

Quando l'applicazione Compose è operativa, è possibile sfruttare i punti di interruzione e le eccezioni se si esegue Visual Studio. In alternativa, è possibile eseguire i test di integrazione nella pipeline CI in Azure DevOps Services o qualsiasi altro sistema di integrazione continua/recapito continuo che supporti i contenitori Docker.

## <a name="testing-in-eshoponcontainers"></a>Test in eShopOnContainers

I test dell'applicazione di riferimento (eShopOnContainers) sono stati ristrutturati di recente. Sono ora disponibili quattro categorie:

1. **Unit** test, normali, presenti all'interno dei progetti **{MicroserviceName}.UnitTests**

2. **Test funzionali o di integrazione dei microservizi**, con test case che coinvolgono l'infrastruttura di ogni microservizio, ma sono isolati dagli altri e sono presenti all'interno dei progetti **{MicroserviceName}.FunctionalTests**.

3. **Test di integrazione/funzionalità dell'applicazione,** incentrati sull'integrazione dei microservizi, con test case che esercitano diversi microservizi. Questi test si trovano nel progetto **Application.FunctionalTests**.

Il test di integrazione e lo unit test per ogni microservizio si trovano nella cartella dei test del rispettivo microservizio. I test di carico delle applicazioni si trovano nella cartella dei test all'interno della cartella della soluzione, come illustrato nella figura 6-25.

![Screenshot di VS che indica alcuni dei progetti di test nella soluzione.](./media/test-aspnet-core-services-web-apps/eshoponcontainers-test-folder-structure.png)

**Figura 6-25**. Struttura delle cartelle di test in eShopOnContainers

I test funzionali e di integrazione delle applicazioni e dei microservizi vengono eseguiti da Visual Studio tramite lo strumento di esecuzione di test normale. Prima, tuttavia, è necessario avviare i servizi dell'infrastruttura necessari tramite un set di file docker-compose presenti nella cartella dei test della soluzione:

**docker-compose-test.yml**

```yml
version: '3.4'

services:
  redis.data:
    image: redis:alpine
  rabbitmq:
    image: rabbitmq:3-management-alpine
  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest
  nosqldata:
    image: mongo
```

**docker-compose-test.override.yml**

```yml
version: '3.4'

services:
  redis.data:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
```

Per eseguire i test funzionali e di integrazione, è pertanto necessario eseguire prima questo comando dalla cartella dei test della soluzione:

```console
docker-compose -f docker-compose-test.yml -f docker-compose-test.override.yml up
```

Come si può notare, questi file docker-compose avviano solo i microservizi di Redis, RabbitMQ, SQL Server e MongoDB.

### <a name="additional-resources"></a>Risorse aggiuntive

- **File LEGGIMI dei test** nel repository di eShopOnContainers in GitHub \
    <https://github.com/dotnet-architecture/eShopOnContainers/tree/dev/test>

- **File LEGGIMI dei test di carico** nel repository di eShopOnContainers in GitHub \
    <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/test/ServicesTests/LoadTest/>

> [!div class="step-by-step"]
> [Successivo](subscribe-events.md)
> [precedente](background-tasks-with-ihostedservice.md)
