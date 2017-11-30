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
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="e7e2b-104">Test dei servizi principali di ASP.NET e applicazioni web</span><span class="sxs-lookup"><span data-stu-id="e7e2b-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="e7e2b-105">I controller sono una parte essenziale di qualsiasi servizio ASP.NET Core API e l'applicazione Web ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="e7e2b-106">Di conseguenza, è necessario confidenza che si comportano come previsto per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="e7e2b-107">Test automatizzati possono fornire questo confidenza e consente di rilevare errori prima che raggiungano di produzione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="e7e2b-108">È necessario il comportamento di input valido o non valido in base al controller di test e test in base al risultato dell'operazione di business che esegue le risposte di controller.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="e7e2b-109">Tuttavia, è necessario disporre questi tipi di test del microservizi:</span><span class="sxs-lookup"><span data-stu-id="e7e2b-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="e7e2b-110">Unit test.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-110">Unit tests.</span></span> <span data-ttu-id="e7e2b-111">Ciò assicura che i singoli componenti dell'applicazione funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="e7e2b-112">Le asserzioni di testare l'API del componente.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="e7e2b-113">Test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-113">Integration tests.</span></span> <span data-ttu-id="e7e2b-114">Ciò assicura che interazioni tra i componenti funzionino come previsto rispetto a elementi esterni come i database.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="e7e2b-115">Le asserzioni possono testare componente API, dell'interfaccia utente o gli effetti collaterali delle azioni come i/o database, la registrazione e così via.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="e7e2b-116">Test funzionale per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-116">Functional tests for each microservice.</span></span> <span data-ttu-id="e7e2b-117">Ciò assicura che l'applicazione funzioni come previsto dal punto di vista dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="e7e2b-118">Verifica del servizio.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-118">Service tests.</span></span> <span data-ttu-id="e7e2b-119">Ciò assicura che i casi di utilizzo del servizio end-to-end, tra cui il test più servizi nello stesso momento, verranno testati.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="e7e2b-120">Per questo tipo di test, è necessario preparare l'ambiente prima.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="e7e2b-121">In questo caso, significa che i servizi di avvio (ad esempio, tramite docker-costituiscono backup).</span><span class="sxs-lookup"><span data-stu-id="e7e2b-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="e7e2b-122">Implementazione di unit test per le API Web di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e7e2b-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="e7e2b-123">Unit test prevede una parte di un'applicazione di test in isolamento dalle relative dipendenze e l'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="e7e2b-124">Quando si esegue uno unit test logica del controller, solo il contenuto di una singola azione o metodo è stato testato, non il comportamento delle dipendenze o di framework stesso.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="e7e2b-125">Unit test non vengono rilevati problemi nell'interazione tra componenti, ovvero lo scopo di test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="e7e2b-126">Come si esegue uno unit test le azioni del controller, assicurarsi di che concentrarsi solo sul relativo comportamento.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="e7e2b-127">Uno unit test controller consente di evitare operazioni come filtri, di routing o di associazione del modello.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="e7e2b-128">Poiché sono concentrarsi su un solo elemento di test, unit test sono in genere semplici da scrivere e rapido per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="e7e2b-129">È possibile eseguire un set ben scritto di unit test spesso senza quantità di overhead.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="e7e2b-130">Unit test vengono implementati basati su Framework di test come NUnit, MSTest, Moq o xUnit.net.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="e7e2b-131">Per l'applicazione di esempio eShopOnContainers, utilizziamo XUnit.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="e7e2b-132">Quando si scrive uno unit test per un controller API Web, si crea un'istanza della classe di controller direttamente utilizzando la parola chiave new in C\#, in modo che il test verrà eseguito più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="e7e2b-133">Nell'esempio seguente viene illustrato come eseguire questa operazione quando si utilizza [XUnit](https://xunit.github.io/) come framework di Test.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="e7e2b-134">Implementazione di integrazione e test funzionale per ogni microservizio</span><span class="sxs-lookup"><span data-stu-id="e7e2b-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="e7e2b-135">Come già indicato, test di integrazione test funzionali e di disporre gli obiettivi e scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="e7e2b-136">Tuttavia, la modalità di implementazione sia durante il test controller ASP.NET Core è simile, pertanto in questa sezione esaminate in test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="e7e2b-137">Test di integrazione garantisce che i componenti di un'applicazione funzionano correttamente quando assemblato.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="e7e2b-138">ASP.NET Core supporta l'integrazione test con Framework di unit test e un host web test predefinite che può essere utilizzato per gestire le richieste senza l'overhead di rete.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="e7e2b-139">A differenza di unit test, test di integrazione comportano spesso problemi di infrastruttura dell'applicazione, ad esempio un database, file system, risorse di rete, o le richieste web e le risposte.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="e7e2b-140">Unit test usare fakes o simulare oggetti al posto di questi problemi.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="e7e2b-141">Ma è lo scopo di test di integrazione per assicurarsi che il sistema funzioni come previsto con questi sistemi, per il test di integrazione per non utilizzare fakes o simulare oggetti.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="e7e2b-142">Invece, si include l'infrastruttura, ad esempio di chiamata di accesso o un servizio di database da altri servizi.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="e7e2b-143">Poiché i test di integrazione esercitare maggiore segmenti di codice rispetto agli unit test e test di integrazione si basano sugli elementi dell'infrastruttura, tendono a essere notevolmente più lenti rispetto agli unit test.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="e7e2b-144">Pertanto, è consigliabile limitare il numero di test di integrazione scrivere ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="e7e2b-145">ASP.NET Core include un host di web test incorporati che può essere usato per gestire le richieste HTTP senza l'overhead di rete, vale a dire che è possibile eseguire più rapidamente i test quando si utilizza un host web reale.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="e7e2b-146">L'host del test web è disponibile in un componente NuGet Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="e7e2b-147">Viene utilizzato per l'host ASP.NET Core applicazioni possono essere aggiunti ai progetti di test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="e7e2b-148">Come si può notare nel codice seguente, quando si creano test di integrazione per ASP.NET Core controller, l'istanza di un controller di tramite l'host di test.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="e7e2b-149">Ciò è paragonabile a una richiesta HTTP, ma viene eseguita più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-149">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="e7e2b-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e7e2b-150">Additional resources</span></span>

-   <span data-ttu-id="e7e2b-151">**Steve Smith. Test controller** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="e7e2b-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="e7e2b-152">**Steve Smith. Test di integrazione** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="e7e2b-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="e7e2b-153">**Unit test in .NET Core utilizzando test dotnet**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span><span class="sxs-lookup"><span data-stu-id="e7e2b-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span></span>

-   <span data-ttu-id="e7e2b-154">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-154">**xUnit.net**.</span></span> <span data-ttu-id="e7e2b-155">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-155">Official site.</span></span>
    [<span data-ttu-id="e7e2b-156">*https://xUnit.github.IO/*</span><span class="sxs-lookup"><span data-stu-id="e7e2b-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="e7e2b-157">**Nozioni di base di Unit Test. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="e7e2b-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="e7e2b-158">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-158">**Moq**.</span></span> <span data-ttu-id="e7e2b-159">Repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-159">GitHub repo.</span></span>
    [<span data-ttu-id="e7e2b-160">*https://github.com/moq/moq*</span><span class="sxs-lookup"><span data-stu-id="e7e2b-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="e7e2b-161">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-161">**NUnit**.</span></span> <span data-ttu-id="e7e2b-162">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-162">Official site.</span></span>
    [<span data-ttu-id="e7e2b-163">*https://www.NUnit.org/*</span><span class="sxs-lookup"><span data-stu-id="e7e2b-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="e7e2b-164">Implementazione del servizio test in un'applicazione multi-contenitore</span><span class="sxs-lookup"><span data-stu-id="e7e2b-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="e7e2b-165">Come notato in precedenza, quando si testano applicazioni multi-contenitore, tutte le microservizi necessario sia in esecuzione all'interno del cluster di host o un contenitore Docker.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="e7e2b-166">Test di servizio end-to-end che includono più operazioni che coinvolgono diversi microservizi richiesto per distribuire e avviare l'intera applicazione nell'host Docker mediante l'esecuzione di docker-comporre remota (o un meccanismo analogo se si utilizza l'agente di orchestrazione).</span><span class="sxs-lookup"><span data-stu-id="e7e2b-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="e7e2b-167">L'intera applicazione e tutti i servizi in esecuzione, è possibile eseguire test funzionali e integrazione end-to-end.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="e7e2b-168">Esistono due approcci, che è possibile utilizzare.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-168">There are a few approaches you can use.</span></span> <span data-ttu-id="e7e2b-169">Nel file docker compose.yml che consente di distribuire l'applicazione (o quelle simili, ad esempio docker compose.ci.build.yml), a livello di soluzione è possibile espandere il punto di ingresso da utilizzare [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span><span class="sxs-lookup"><span data-stu-id="e7e2b-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span></span> <span data-ttu-id="e7e2b-170">È inoltre possibile utilizzare un altro file di contenuto che si esecuzione i test nell'immagine di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="e7e2b-171">Utilizzando un altro file di contenuto per i test di integrazione che include i database sui contenitori e microservizi, è possibile assicurarsi che i dati correlati sono sempre reimpostare lo stato originale prima di eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="e7e2b-172">Dopo l'applicazione di composizione sia in esecuzione, è possibile sfruttare i punti di interruzione e le eccezioni se si esegue Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="e7e2b-173">Oppure è possibile eseguire il test di integrazione automaticamente nella pipeline elemento di configurazione in Visual Studio Team Services o qualsiasi altro sistema CI/CD che supporta i contenitori di Docker.</span><span class="sxs-lookup"><span data-stu-id="e7e2b-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e7e2b-174">[Precedente] (sottoscrizione-events.md) [Avanti] (... /microservice-ddd-CQRS-Patterns/index.MD)</span><span class="sxs-lookup"><span data-stu-id="e7e2b-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>
