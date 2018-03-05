---
title: Test delle app Web e dei servizi ASP.NET di base
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Test delle app Web e dei servizi ASP.NET di base
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 596f588aae8c0814e5b40d29c4bf5723f944c5ac
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2018
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="d49a0-104">Test delle app Web e dei servizi ASP.NET di base</span><span class="sxs-lookup"><span data-stu-id="d49a0-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="d49a0-105">I controller sono un componente essenziale di qualsiasi servizio API ASP.NET Core e applicazione Web MVC ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="d49a0-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="d49a0-106">Di conseguenza è importante verificare che funzionino correttamente nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d49a0-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="d49a0-107">I test automatizzati eseguono questa verifica e rilevano gli errori dei controller prima che questi raggiungano la fase di produzione.</span><span class="sxs-lookup"><span data-stu-id="d49a0-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="d49a0-108">È necessario testare il comportamento del controller in base a input valido o non validi ed eseguire il test delle risposte del controller in base ai risultati dell'operazione di business effettuata.</span><span class="sxs-lookup"><span data-stu-id="d49a0-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="d49a0-109">Tuttavia, è necessario avere i seguenti tipi di test nei microservizi:</span><span class="sxs-lookup"><span data-stu-id="d49a0-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="d49a0-110">Unit test.</span><span class="sxs-lookup"><span data-stu-id="d49a0-110">Unit tests.</span></span> <span data-ttu-id="d49a0-111">Garantiscono il funzionamento previsto dei singoli componenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d49a0-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="d49a0-112">Le asserzioni testano l'API componente.</span><span class="sxs-lookup"><span data-stu-id="d49a0-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="d49a0-113">Test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="d49a0-113">Integration tests.</span></span> <span data-ttu-id="d49a0-114">Garantiscono il funzionamento previsto delle interazioni tra componenti rispetto a elementi esterni, come i database.</span><span class="sxs-lookup"><span data-stu-id="d49a0-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="d49a0-115">Le asserzioni possono testare l'API componente, l'interfaccia utente o gli effetti collaterali di azioni come input/output nei database, registrazione e così via.</span><span class="sxs-lookup"><span data-stu-id="d49a0-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="d49a0-116">Test funzionali per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="d49a0-116">Functional tests for each microservice.</span></span> <span data-ttu-id="d49a0-117">Garantiscono il funzionamento previsto dell'applicazione dal punto di vista dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d49a0-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="d49a0-118">Test di servizio.</span><span class="sxs-lookup"><span data-stu-id="d49a0-118">Service tests.</span></span> <span data-ttu-id="d49a0-119">Garantiscono l'esecuzione del test dei casi d'uso dei servizi end-to-end, tra cui il test simultaneo di più servizi.</span><span class="sxs-lookup"><span data-stu-id="d49a0-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="d49a0-120">Per questo tipo di test, è necessario preparare prima l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="d49a0-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="d49a0-121">In questo caso, ciò significa avviare i servizi (ad esempio, usando il comando docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="d49a0-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="d49a0-122">Implementazione di unit test per le API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d49a0-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="d49a0-123">Lo unit test prevede l'esecuzione di test su una parte di un'applicazione isolandola dall'infrastruttura e dalle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="d49a0-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="d49a0-124">Quando si sottopone a unit test la logica del controller, si verifica solo il contenuto di una singola azione o metodo e non il comportamento delle relative dipendenze o del framework.</span><span class="sxs-lookup"><span data-stu-id="d49a0-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="d49a0-125">Gli unit test non rilevano i problemi dell'interazione tra componenti: a questo scopo esistono i test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="d49a0-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="d49a0-126">Quando si sottopongono a unit test le azioni del controller, è importante concentrarsi esclusivamente sul funzionamento del relativo controller.</span><span class="sxs-lookup"><span data-stu-id="d49a0-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="d49a0-127">Uno unit test del controller non prende in esame elementi come filtri, routing o associazione di modelli.</span><span class="sxs-lookup"><span data-stu-id="d49a0-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="d49a0-128">Gli unit test risultano in genere facili da creare e rapidi da eseguire, perché verificano un solo aspetto.</span><span class="sxs-lookup"><span data-stu-id="d49a0-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="d49a0-129">Un set di unit test ben organizzato può essere eseguito spesso senza sovraccarichi eccessivi.</span><span class="sxs-lookup"><span data-stu-id="d49a0-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="d49a0-130">Gli unit test vengono implementati in base ai framework di test come xUnit.net, MSTest, Moq o NUnit.</span><span class="sxs-lookup"><span data-stu-id="d49a0-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="d49a0-131">Per l'applicazione di esempio eShopOnContainers, useremo XUnit.</span><span class="sxs-lookup"><span data-stu-id="d49a0-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="d49a0-132">Quando si scrive uno unit test per un controller API Web, si crea direttamente un'istanza della classe controller usando la nuova parola chiave in C\#, in modo che il test venga eseguito il più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="d49a0-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="d49a0-133">L'esempio seguente illustra come eseguire questa operazione usando [XUnit](https://xunit.github.io/) come framework di test.</span><span class="sxs-lookup"><span data-stu-id="d49a0-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="d49a0-134">Implementazione dei test funzionali e di integrazione per ogni microservizio</span><span class="sxs-lookup"><span data-stu-id="d49a0-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="d49a0-135">Come già indicato, i test di integrazione e i test funzionali hanno scopi e obiettivi diversi.</span><span class="sxs-lookup"><span data-stu-id="d49a0-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="d49a0-136">Tuttavia, la modalità di implementazione di entrambi durante il test dei controller ASP.NET Core è simile, dunque questa sezione è incentrata sui test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="d49a0-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="d49a0-137">Il test di integrazione garantisce che i componenti di un'applicazione funzionino correttamente quando assemblati.</span><span class="sxs-lookup"><span data-stu-id="d49a0-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="d49a0-138">ASP.NET Core supporta i test di integrazione con framework di unit test e un host Web di test predefinito che può essere usato per gestire le richieste senza sovraccarico di rete.</span><span class="sxs-lookup"><span data-stu-id="d49a0-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="d49a0-139">A differenza degli unit test, i test di integrazione comportano spesso preoccupazioni relative all'infrastruttura dell'applicazione, ad esempio il database, il file system, le risorse di rete o le richieste e risposte Web.</span><span class="sxs-lookup"><span data-stu-id="d49a0-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="d49a0-140">Gli unit test usano dati falsi o oggetti fittizi al posto di queste preoccupazioni,</span><span class="sxs-lookup"><span data-stu-id="d49a0-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="d49a0-141">ma lo scopo dei test di integrazione è confermare il funzionamento previsto del sistema, dunque è inutile usare dati falsi oppure oggetti fittizi.</span><span class="sxs-lookup"><span data-stu-id="d49a0-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="d49a0-142">Si includerà piuttosto l'infrastruttura, come l'accesso al database o la chiamata di un servizio da altri servizi.</span><span class="sxs-lookup"><span data-stu-id="d49a0-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="d49a0-143">Visto che esercitano segmenti di codice più grandi rispetto agli unit test e si basano sugli elementi dell'infrastruttura, i test di integrazione tendono a essere notevolmente più lenti rispetto agli unit test.</span><span class="sxs-lookup"><span data-stu-id="d49a0-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="d49a0-144">Di conseguenza, è consigliabile limitare il numero di test di integrazione da scrivere ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="d49a0-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="d49a0-145">ASP.NET Core include un host Web di test predefinito che può essere usato per gestire le richieste HTTP senza il sovraccarico di rete, vale a dire che è possibile eseguire più rapidamente i test quando si usa un host Web reale.</span><span class="sxs-lookup"><span data-stu-id="d49a0-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="d49a0-146">L'host Web di test è disponibile in un componente NuGet come Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="d49a0-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="d49a0-147">Può essere aggiunto ai progetti di test di integrazione e usato per ospitare le applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="d49a0-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="d49a0-148">Come si può notare nel codice seguente, quando si creano test di integrazione per i controller ASP.NET Core, si crea l'istanza dei controller attraverso l'host di test.</span><span class="sxs-lookup"><span data-stu-id="d49a0-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="d49a0-149">Ciò è paragonabile a una richiesta HTTP, ma viene eseguita più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="d49a0-149">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="d49a0-150">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d49a0-150">Additional resources</span></span>

-   <span data-ttu-id="d49a0-151">**Steve Smith. Test della logica dei controller in ASP.NET Core** [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="d49a0-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="d49a0-152">**Steve Smith. Integrazione di test in ASP.NET Core** [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="d49a0-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="d49a0-153">**Testing unità di C# in .NET Core usando il test dotnet e xUnit**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)</span><span class="sxs-lookup"><span data-stu-id="d49a0-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)</span></span>

-   <span data-ttu-id="d49a0-154">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="d49a0-154">**xUnit.net**.</span></span> <span data-ttu-id="d49a0-155">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="d49a0-155">Official site.</span></span>
    [<span data-ttu-id="d49a0-156">*https://xunit.github.io/*</span><span class="sxs-lookup"><span data-stu-id="d49a0-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="d49a0-157">**Nozioni fondamentali sugli unit test.**
    [*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="d49a0-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="d49a0-158">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="d49a0-158">**Moq**.</span></span> <span data-ttu-id="d49a0-159">Repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="d49a0-159">GitHub repo.</span></span>
    [<span data-ttu-id="d49a0-160">*https://github.com/moq/moq*</span><span class="sxs-lookup"><span data-stu-id="d49a0-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="d49a0-161">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="d49a0-161">**NUnit**.</span></span> <span data-ttu-id="d49a0-162">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="d49a0-162">Official site.</span></span>
    [<span data-ttu-id="d49a0-163">*https://www.nunit.org/*</span><span class="sxs-lookup"><span data-stu-id="d49a0-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="d49a0-164">Implementazione di test di servizio in un'applicazione a più contenitori</span><span class="sxs-lookup"><span data-stu-id="d49a0-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="d49a0-165">Come indicato in precedenza, quando si testano applicazioni a più contenitori, tutti i microservizi devono essere eseguiti all'interno dell'host Docker o del cluster di contenitori.</span><span class="sxs-lookup"><span data-stu-id="d49a0-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="d49a0-166">I test di servizio end-to-end che includono più operazioni che implicano diversi microservizi richiedono la distribuzione e l'avvio dell'intera applicazione nell'host Docker con l'esecuzione del comando docker-compose up (o un meccanismo analogo, se si usa un agente di orchestrazione).</span><span class="sxs-lookup"><span data-stu-id="d49a0-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="d49a0-167">Quando l'intera applicazione e tutti i relativi servizi saranno in esecuzione, sarà possibile eseguire i test funzionali e di integrazione end-to-end.</span><span class="sxs-lookup"><span data-stu-id="d49a0-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="d49a0-168">Sono possibili alcuni approcci.</span><span class="sxs-lookup"><span data-stu-id="d49a0-168">There are a few approaches you can use.</span></span> <span data-ttu-id="d49a0-169">Nel file docker-compose.yml usato per distribuire l'applicazione (o file simili, come docker-compose.ci.build.yml), a livello di soluzione è possibile espandere il punto di ingresso in modo da usare [dotnet test](../../../core/tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="d49a0-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="d49a0-170">È anche possibile usare un altro file Compose che esegua i test nell'immagine specificata come destinazione.</span><span class="sxs-lookup"><span data-stu-id="d49a0-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="d49a0-171">Se per i test di integrazione si usa un altro file Compose che include i microservizi e i database nei contenitori, ci si assicura di ripristinare sempre lo stato originale dei dati correlati prima di eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="d49a0-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="d49a0-172">Quando l'applicazione Compose è operativa, è possibile sfruttare i punti di interruzione e le eccezioni se si esegue Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d49a0-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="d49a0-173">In alternativa, è possibile eseguire i test di integrazione nella pipeline CI in Visual Studio Team Services o qualsiasi altro sistema di integrazione continua/recapito continuo che supporti i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="d49a0-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="d49a0-174">[Indietro] (subscribe-events.md) [Avanti] (../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="d49a0-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>
