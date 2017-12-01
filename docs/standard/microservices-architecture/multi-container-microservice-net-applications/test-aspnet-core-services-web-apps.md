---
title: Test dei servizi principali di ASP.NET e applicazioni web
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Test dei servizi principali di ASP.NET e applicazioni web
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f756a679befee676db2bf6d402fd7e34b1621b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="testing-aspnet-core-services-and-web-apps"></a>Test dei servizi principali di ASP.NET e applicazioni web

I controller sono una parte essenziale di qualsiasi servizio ASP.NET Core API e l'applicazione Web ASP.NET MVC. Di conseguenza, è necessario confidenza che si comportano come previsto per l'applicazione. Test automatizzati possono fornire questo confidenza e consente di rilevare errori prima che raggiungano di produzione.

È necessario il comportamento di input valido o non valido in base al controller di test e test in base al risultato dell'operazione di business che esegue le risposte di controller. Tuttavia, è necessario disporre questi tipi di test del microservizi:

-   Unit test. Ciò assicura che i singoli componenti dell'applicazione funzionino come previsto. Le asserzioni di testare l'API del componente.

-   Test di integrazione. Ciò assicura che interazioni tra i componenti funzionino come previsto rispetto a elementi esterni come i database. Le asserzioni possono testare componente API, dell'interfaccia utente o gli effetti collaterali delle azioni come i/o database, la registrazione e così via.

-   Test funzionale per ogni microservizio. Ciò assicura che l'applicazione funzioni come previsto dal punto di vista dell'utente.

-   Verifica del servizio. Ciò assicura che i casi di utilizzo del servizio end-to-end, tra cui il test più servizi nello stesso momento, verranno testati. Per questo tipo di test, è necessario preparare l'ambiente prima. In questo caso, significa che i servizi di avvio (ad esempio, tramite docker-costituiscono backup).

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a>Implementazione di unit test per le API Web di ASP.NET Core

Unit test prevede una parte di un'applicazione di test in isolamento dalle relative dipendenze e l'infrastruttura. Quando si esegue uno unit test logica del controller, solo il contenuto di una singola azione o metodo è stato testato, non il comportamento delle dipendenze o di framework stesso. Unit test non vengono rilevati problemi nell'interazione tra componenti, ovvero lo scopo di test di integrazione.

Come si esegue uno unit test le azioni del controller, assicurarsi di che concentrarsi solo sul relativo comportamento. Uno unit test controller consente di evitare operazioni come filtri, di routing o di associazione del modello. Poiché sono concentrarsi su un solo elemento di test, unit test sono in genere semplici da scrivere e rapido per l'esecuzione. È possibile eseguire un set ben scritto di unit test spesso senza quantità di overhead.

Unit test vengono implementati basati su Framework di test come NUnit, MSTest, Moq o xUnit.net. Per l'applicazione di esempio eShopOnContainers, utilizziamo XUnit.

Quando si scrive uno unit test per un controller API Web, si crea un'istanza della classe di controller direttamente utilizzando la parola chiave new in C\#, in modo che il test verrà eseguito più velocemente possibile. Nell'esempio seguente viene illustrato come eseguire questa operazione quando si utilizza [XUnit](https://xunit.github.io/) come framework di Test.

```csharp
[Fact]
public void Add_new_Order_raises_new_event()
{
    // Arrange
    var street = " FakeStreet ";
    var city = "FakeCity";
    // Other variables omitted for brevity ...
    // Act
    var fakeOrder = new Order(new Address(street, city, state, country, zipcode),
        cardTypeId, cardNumber,
        cardSecurityNumber, cardHolderName,
        cardExpiration);
    // Assert
    Assert.Equal(fakeOrder.DomainEvents.Count, expectedResult);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a>Implementazione di integrazione e test funzionale per ogni microservizio

Come già indicato, test di integrazione test funzionali e di disporre gli obiettivi e scopi diversi. Tuttavia, la modalità di implementazione sia durante il test controller ASP.NET Core è simile, pertanto in questa sezione esaminate in test di integrazione.

Test di integrazione garantisce che i componenti di un'applicazione funzionano correttamente quando assemblato. ASP.NET Core supporta l'integrazione test con Framework di unit test e un host web test predefinite che può essere utilizzato per gestire le richieste senza l'overhead di rete.

A differenza di unit test, test di integrazione comportano spesso problemi di infrastruttura dell'applicazione, ad esempio un database, file system, risorse di rete, o le richieste web e le risposte. Unit test usare fakes o simulare oggetti al posto di questi problemi. Ma è lo scopo di test di integrazione per assicurarsi che il sistema funzioni come previsto con questi sistemi, per il test di integrazione per non utilizzare fakes o simulare oggetti. Invece, si include l'infrastruttura, ad esempio di chiamata di accesso o un servizio di database da altri servizi.

Poiché i test di integrazione esercitare maggiore segmenti di codice rispetto agli unit test e test di integrazione si basano sugli elementi dell'infrastruttura, tendono a essere notevolmente più lenti rispetto agli unit test. Pertanto, è consigliabile limitare il numero di test di integrazione scrivere ed eseguire.

ASP.NET Core include un host di web test incorporati che può essere usato per gestire le richieste HTTP senza l'overhead di rete, vale a dire che è possibile eseguire più rapidamente i test quando si utilizza un host web reale. L'host del test web è disponibile in un componente NuGet Microsoft.AspNetCore.TestHost. Viene utilizzato per l'host ASP.NET Core applicazioni possono essere aggiunti ai progetti di test di integrazione.

Come si può notare nel codice seguente, quando si creano test di integrazione per ASP.NET Core controller, l'istanza di un controller di tramite l'host di test. Ciò è paragonabile a una richiesta HTTP, ma viene eseguita più rapidamente.

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

-   **Steve Smith. Test controller** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)

-   **Steve Smith. Test di integrazione** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)

-   **Unit test in .NET Core utilizzando test dotnet**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)

-   **xUnit.net**. Sito ufficiale.
    [*https://xUnit.github.IO/*](https://xunit.github.io/)

-   **Nozioni di base di Unit Test. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)

-   **Moq**. Repository di GitHub.
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   **NUnit**. Sito ufficiale.
    [*https://www.NUnit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a>Implementazione del servizio test in un'applicazione multi-contenitore 

Come notato in precedenza, quando si testano applicazioni multi-contenitore, tutte le microservizi necessario sia in esecuzione all'interno del cluster di host o un contenitore Docker. Test di servizio end-to-end che includono più operazioni che coinvolgono diversi microservizi richiesto per distribuire e avviare l'intera applicazione nell'host Docker mediante l'esecuzione di docker-comporre remota (o un meccanismo analogo se si utilizza l'agente di orchestrazione). L'intera applicazione e tutti i servizi in esecuzione, è possibile eseguire test funzionali e integrazione end-to-end.

Esistono due approcci, che è possibile utilizzare. Nel file docker compose.yml che consente di distribuire l'applicazione (o quelle simili, ad esempio docker compose.ci.build.yml), a livello di soluzione è possibile espandere il punto di ingresso da utilizzare [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test). È inoltre possibile utilizzare un altro file di contenuto che si esecuzione i test nell'immagine di destinazione. Utilizzando un altro file di contenuto per i test di integrazione che include i database sui contenitori e microservizi, è possibile assicurarsi che i dati correlati sono sempre reimpostare lo stato originale prima di eseguire i test.

Dopo l'applicazione di composizione sia in esecuzione, è possibile sfruttare i punti di interruzione e le eccezioni se si esegue Visual Studio. Oppure è possibile eseguire il test di integrazione automaticamente nella pipeline elemento di configurazione in Visual Studio Team Services o qualsiasi altro sistema CI/CD che supporta i contenitori di Docker.

>[!div class="step-by-step"]
[Precedente] (sottoscrizione-events.md) [Avanti] (... /microservice-ddd-CQRS-Patterns/index.MD)
