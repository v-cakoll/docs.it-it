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
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="898a7-103">Test delle app Web e dei servizi ASP.NET di base</span><span class="sxs-lookup"><span data-stu-id="898a7-103">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="898a7-104">I controller sono un componente essenziale di qualsiasi servizio API ASP.NET Core e applicazione Web MVC ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="898a7-104">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="898a7-105">Di conseguenza è importante verificare che funzionino correttamente nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="898a7-105">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="898a7-106">I test automatizzati eseguono questa verifica e rilevano gli errori dei controller prima che questi raggiungano la fase di produzione.</span><span class="sxs-lookup"><span data-stu-id="898a7-106">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="898a7-107">È necessario testare il comportamento del controller in base a input valido o non validi ed eseguire il test delle risposte del controller in base ai risultati dell'operazione di business effettuata.</span><span class="sxs-lookup"><span data-stu-id="898a7-107">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="898a7-108">Tuttavia, è necessario avere i seguenti tipi di test nei microservizi:</span><span class="sxs-lookup"><span data-stu-id="898a7-108">However, you should have these types of tests for your microservices:</span></span>

- <span data-ttu-id="898a7-109">Unit test.</span><span class="sxs-lookup"><span data-stu-id="898a7-109">Unit tests.</span></span> <span data-ttu-id="898a7-110">Garantiscono il funzionamento previsto dei singoli componenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="898a7-110">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="898a7-111">Le asserzioni testano l'API componente.</span><span class="sxs-lookup"><span data-stu-id="898a7-111">Assertions test the component API.</span></span>

- <span data-ttu-id="898a7-112">Test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="898a7-112">Integration tests.</span></span> <span data-ttu-id="898a7-113">Garantiscono il funzionamento previsto delle interazioni tra componenti rispetto a elementi esterni, come i database.</span><span class="sxs-lookup"><span data-stu-id="898a7-113">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="898a7-114">Le asserzioni possono testare l'API componente, l'interfaccia utente o gli effetti collaterali di azioni come input/output nei database, registrazione e così via.</span><span class="sxs-lookup"><span data-stu-id="898a7-114">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

- <span data-ttu-id="898a7-115">Test funzionali per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="898a7-115">Functional tests for each microservice.</span></span> <span data-ttu-id="898a7-116">Questi assicurano che l'applicazione funzioni come previsto dal punto di vista dell'utente.</span><span class="sxs-lookup"><span data-stu-id="898a7-116">These ensure that the application works as expected from the user's perspective.</span></span>

- <span data-ttu-id="898a7-117">Test di servizio.</span><span class="sxs-lookup"><span data-stu-id="898a7-117">Service tests.</span></span> <span data-ttu-id="898a7-118">Garantiscono l'esecuzione del test dei casi d'uso dei servizi end-to-end, tra cui il test simultaneo di più servizi.</span><span class="sxs-lookup"><span data-stu-id="898a7-118">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="898a7-119">Per questo tipo di test, è necessario preparare prima l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="898a7-119">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="898a7-120">In questo caso, ciò significa avviare i servizi, ad esempio usando il comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="898a7-120">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="898a7-121">Implementazione di unit test per le API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="898a7-121">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="898a7-122">Lo unit test prevede l'esecuzione di test su una parte di un'applicazione isolandola dall'infrastruttura e dalle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="898a7-122">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="898a7-123">Quando si sottopone a unit test la logica del controller, si verifica solo il contenuto di una singola azione o metodo e non il comportamento delle relative dipendenze o del framework.</span><span class="sxs-lookup"><span data-stu-id="898a7-123">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="898a7-124">Gli unit test non rilevano i problemi dell'interazione tra componenti: a questo scopo esistono i test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="898a7-124">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="898a7-125">Quando si sottopongono a unit test le azioni del controller, è importante concentrarsi esclusivamente sul funzionamento del relativo controller.</span><span class="sxs-lookup"><span data-stu-id="898a7-125">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="898a7-126">Uno unit test del controller consente di evitare, ad esempio, filtri, routing o associazione di modelli (il mapping dei dati di richiesta a un elemento ViewModel o DTO).</span><span class="sxs-lookup"><span data-stu-id="898a7-126">A controller unit test avoids things like filters, routing, or model binding (the mapping of request data to a ViewModel or DTO).</span></span> <span data-ttu-id="898a7-127">Gli unit test risultano in genere facili da creare e rapidi da eseguire, perché verificano un solo aspetto.</span><span class="sxs-lookup"><span data-stu-id="898a7-127">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="898a7-128">Un set di unit test ben organizzato può essere eseguito spesso senza sovraccarichi eccessivi.</span><span class="sxs-lookup"><span data-stu-id="898a7-128">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="898a7-129">Gli unit test vengono implementati in base ai framework di test come xUnit.net, MSTest, Moq o NUnit.</span><span class="sxs-lookup"><span data-stu-id="898a7-129">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="898a7-130">Per l'applicazione di esempio eShopOnContainers, useremo xUnit.</span><span class="sxs-lookup"><span data-stu-id="898a7-130">For the eShopOnContainers sample application, we are using xUnit.</span></span>

<span data-ttu-id="898a7-131">Quando si scrive uno unit test per un controller API Web, si crea direttamente un'istanza della classe controller usando la nuova parola chiave in C\#, in modo che il test venga eseguito il più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="898a7-131">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="898a7-132">L'esempio seguente illustra come eseguire questa operazione usando [xUnit](https://xunit.github.io/) come framework di test.</span><span class="sxs-lookup"><span data-stu-id="898a7-132">The following example shows how to do this when using [xUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="898a7-133">Implementazione dei test funzionali e di integrazione per ogni microservizio</span><span class="sxs-lookup"><span data-stu-id="898a7-133">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="898a7-134">Come già indicato, i test di integrazione e i test funzionali hanno scopi e obiettivi diversi.</span><span class="sxs-lookup"><span data-stu-id="898a7-134">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="898a7-135">Tuttavia, la modalità di implementazione di entrambi durante il test dei controller ASP.NET Core è simile, dunque questa sezione è incentrata sui test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="898a7-135">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="898a7-136">Il test di integrazione garantisce che i componenti di un'applicazione funzionino correttamente quando assemblati.</span><span class="sxs-lookup"><span data-stu-id="898a7-136">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="898a7-137">ASP.NET Core supporta i test di integrazione con framework di unit test e un host Web di test predefinito che può essere usato per gestire le richieste senza sovraccarico di rete.</span><span class="sxs-lookup"><span data-stu-id="898a7-137">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="898a7-138">A differenza degli unit test, i test di integrazione comportano spesso preoccupazioni relative all'infrastruttura dell'applicazione, ad esempio il database, il file system, le risorse di rete o le richieste e risposte Web.</span><span class="sxs-lookup"><span data-stu-id="898a7-138">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="898a7-139">Gli unit test usano dati falsi o oggetti fittizi al posto di queste preoccupazioni,</span><span class="sxs-lookup"><span data-stu-id="898a7-139">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="898a7-140">ma lo scopo dei test di integrazione è confermare il funzionamento previsto del sistema, dunque è inutile usare dati falsi oppure oggetti fittizi.</span><span class="sxs-lookup"><span data-stu-id="898a7-140">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="898a7-141">Si includerà piuttosto l'infrastruttura, come l'accesso al database o la chiamata di un servizio da altri servizi.</span><span class="sxs-lookup"><span data-stu-id="898a7-141">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="898a7-142">Visto che esercitano segmenti di codice più grandi rispetto agli unit test e si basano sugli elementi dell'infrastruttura, i test di integrazione tendono a essere notevolmente più lenti rispetto agli unit test.</span><span class="sxs-lookup"><span data-stu-id="898a7-142">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="898a7-143">Di conseguenza, è consigliabile limitare il numero di test di integrazione da scrivere ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="898a7-143">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="898a7-144">ASP.NET Core include un host Web di test incorporato che può essere utilizzato per gestire le richieste HTTP senza sovraccarico di rete, il che significa che è possibile eseguire tali test più velocemente rispetto a quando si utilizza un host Web reale.</span><span class="sxs-lookup"><span data-stu-id="898a7-144">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster than when using a real web host.</span></span> <span data-ttu-id="898a7-145">L'host Web di test (TestServer) è disponibile in un componente NuGet come Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="898a7-145">The test web host (TestServer) is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="898a7-146">Può essere aggiunto ai progetti di test di integrazione e usato per ospitare le applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="898a7-146">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="898a7-147">Come si può notare nel codice seguente, quando si creano test di integrazione per i controller ASP.NET Core, si crea l'istanza dei controller attraverso l'host di test.</span><span class="sxs-lookup"><span data-stu-id="898a7-147">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="898a7-148">Ciò è paragonabile a una richiesta HTTP, ma viene eseguita più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="898a7-148">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="898a7-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="898a7-149">Additional resources</span></span>

- <span data-ttu-id="898a7-150">**Steve Smith. Controller di test** (ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="898a7-150">**Steve Smith. Testing controllers** (ASP.NET Core) \</span></span>
    [https://docs.microsoft.com/aspnet/core/mvc/controllers/testing](/aspnet/core/mvc/controllers/testing)

- <span data-ttu-id="898a7-151">**Steve Smith. Test di integrazione** (ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="898a7-151">**Steve Smith. Integration testing** (ASP.NET Core) \</span></span>
    [https://docs.microsoft.com/aspnet/core/test/integration-tests](/aspnet/core/test/integration-tests)

- <span data-ttu-id="898a7-152">**Unit test in .NET Core con dotnet test** </span><span class="sxs-lookup"><span data-stu-id="898a7-152">**Unit testing in .NET Core using dotnet test** </span></span>\
    [https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test](../../../core/testing/unit-testing-with-dotnet-test.md)

- <span data-ttu-id="898a7-153">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="898a7-153">**xUnit.net**.</span></span> <span data-ttu-id="898a7-154">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="898a7-154">Official site.</span></span> \
    <https://xunit.github.io/>

- <span data-ttu-id="898a7-155">**Nozioni di base sui unit test.**</span><span class="sxs-lookup"><span data-stu-id="898a7-155">**Unit Test Basics.**</span></span> \
    [https://docs.microsoft.com/visualstudio/test/unit-test-basics](/visualstudio/test/unit-test-basics)

- <span data-ttu-id="898a7-156">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="898a7-156">**Moq**.</span></span> <span data-ttu-id="898a7-157">Repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="898a7-157">GitHub repo.</span></span> \
    <https://github.com/moq/moq>

- <span data-ttu-id="898a7-158">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="898a7-158">**NUnit**.</span></span> <span data-ttu-id="898a7-159">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="898a7-159">Official site.</span></span> \
    <https://www.nunit.org/>

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="898a7-160">Implementazione di test di servizio in un'applicazione a più contenitori</span><span class="sxs-lookup"><span data-stu-id="898a7-160">Implementing service tests on a multi-container application</span></span>

<span data-ttu-id="898a7-161">Come indicato in precedenza, quando si testano applicazioni a più contenitori, tutti i microservizi devono essere eseguiti all'interno dell'host Docker o del cluster di contenitori.</span><span class="sxs-lookup"><span data-stu-id="898a7-161">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="898a7-162">I test di servizio end-to-end che includono più operazioni che coinvolgono diversi microservizi richiedono la distribuzione e l'avvio dell'intera applicazione nell'host Docker con l'esecuzione del comando docker-compose up (o con un meccanismo analogo, se si usa un agente di orchestrazione).</span><span class="sxs-lookup"><span data-stu-id="898a7-162">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="898a7-163">Quando l'intera applicazione e tutti i relativi servizi saranno in esecuzione, sarà possibile eseguire i test funzionali e di integrazione end-to-end.</span><span class="sxs-lookup"><span data-stu-id="898a7-163">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="898a7-164">Sono possibili alcuni approcci.</span><span class="sxs-lookup"><span data-stu-id="898a7-164">There are a few approaches you can use.</span></span> <span data-ttu-id="898a7-165">Nel file docker-compose.yml usato per distribuire l'applicazione, a livello di soluzione è possibile espandere il punto di ingresso e usare [dotnet test](../../../core/tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="898a7-165">In the docker-compose.yml file that you use to deploy the application at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="898a7-166">È anche possibile usare un altro file Compose che esegua i test nell'immagine specificata come destinazione.</span><span class="sxs-lookup"><span data-stu-id="898a7-166">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="898a7-167">Se per i test di integrazione si usa un altro file Compose che include i microservizi e i database nei contenitori, ci si assicura di ripristinare sempre lo stato originale dei dati correlati prima di eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="898a7-167">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="898a7-168">Quando l'applicazione Compose è operativa, è possibile sfruttare i punti di interruzione e le eccezioni se si esegue Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="898a7-168">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="898a7-169">In alternativa, è possibile eseguire i test di integrazione nella pipeline CI in Azure DevOps Services o qualsiasi altro sistema di integrazione continua/recapito continuo che supporti i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="898a7-169">Or you can run the integration tests automatically in your CI pipeline in Azure DevOps Services or any other CI/CD system that supports Docker containers.</span></span>

## <a name="testing-in-eshoponcontainers"></a><span data-ttu-id="898a7-170">Test in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="898a7-170">Testing in eShopOnContainers</span></span>

<span data-ttu-id="898a7-171">I test dell'applicazione di riferimento (eShopOnContainers) sono stati ristrutturati di recente. Sono ora disponibili quattro categorie:</span><span class="sxs-lookup"><span data-stu-id="898a7-171">The reference application (eShopOnContainers) tests were recently restructured and now there are four categories:</span></span>

1. <span data-ttu-id="898a7-172">**Unit** test, normali, presenti all'interno dei progetti **{MicroserviceName}.UnitTests**</span><span class="sxs-lookup"><span data-stu-id="898a7-172">**Unit** tests, just plain old regular unit tests, contained in the **{MicroserviceName}.UnitTests** projects</span></span>

2. <span data-ttu-id="898a7-173">**Test funzionali o di integrazione dei microservizi**, con test case che coinvolgono l'infrastruttura di ogni microservizio, ma sono isolati dagli altri e sono presenti all'interno dei progetti **{MicroserviceName}.FunctionalTests**.</span><span class="sxs-lookup"><span data-stu-id="898a7-173">**Microservice functional/integration tests**, with test cases involving the infrastructure for each microservice but isolated from the others and are contained in the **{MicroserviceName}.FunctionalTests** projects.</span></span>

3. <span data-ttu-id="898a7-174">**Test di integrazione/funzionalità dell'applicazione,** incentrati sull'integrazione dei microservizi, con test case che esercitano diversi microservizi.</span><span class="sxs-lookup"><span data-stu-id="898a7-174">**Application functional/integration tests**, which focus on microservices integration, with test cases that exert several microservices.</span></span> <span data-ttu-id="898a7-175">Questi test si trovano nel progetto **Application.FunctionalTests**.</span><span class="sxs-lookup"><span data-stu-id="898a7-175">These tests are located in project **Application.FunctionalTests**.</span></span>

<span data-ttu-id="898a7-176">Il test di integrazione e lo unit test per ogni microservizio si trovano nella cartella dei test del rispettivo microservizio. I test di carico delle applicazioni si trovano nella cartella dei test all'interno della cartella della soluzione, come illustrato nella figura 6-25.</span><span class="sxs-lookup"><span data-stu-id="898a7-176">Unit and integration test per microservice are contained in a test folder in each microservice and Application a Load tests are contained under the test folder in the solution folder, as shown in Figure 6-25.</span></span>

![Screenshot di VS che indica alcuni dei progetti di test nella soluzione.](./media/test-aspnet-core-services-web-apps/eshoponcontainers-test-folder-structure.png)

<span data-ttu-id="898a7-178">**Figura 6-25**.</span><span class="sxs-lookup"><span data-stu-id="898a7-178">**Figure 6-25**.</span></span> <span data-ttu-id="898a7-179">Struttura delle cartelle di test in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="898a7-179">Test folder structure in eShopOnContainers</span></span>

<span data-ttu-id="898a7-180">I test funzionali e di integrazione delle applicazioni e dei microservizi vengono eseguiti da Visual Studio tramite lo strumento di esecuzione di test normale. Prima, tuttavia, è necessario avviare i servizi dell'infrastruttura necessari tramite un set di file docker-compose presenti nella cartella dei test della soluzione:</span><span class="sxs-lookup"><span data-stu-id="898a7-180">Microservice and Application functional/integration tests are run from Visual Studio, using the regular tests runner, but first you need to start the required infrastructure services, by means of a set of docker-compose files contained in the solution test folder:</span></span>

<span data-ttu-id="898a7-181">**docker-compose-test.yml**</span><span class="sxs-lookup"><span data-stu-id="898a7-181">**docker-compose-test.yml**</span></span>

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

<span data-ttu-id="898a7-182">**docker-compose-test.override.yml**</span><span class="sxs-lookup"><span data-stu-id="898a7-182">**docker-compose-test.override.yml**</span></span>

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

<span data-ttu-id="898a7-183">Per eseguire i test funzionali e di integrazione, è pertanto necessario eseguire prima questo comando dalla cartella dei test della soluzione:</span><span class="sxs-lookup"><span data-stu-id="898a7-183">So, to run the functional/integration tests you must first run this command, from the solution test folder:</span></span>

```console
docker-compose -f docker-compose-test.yml -f docker-compose-test.override.yml up
```

<span data-ttu-id="898a7-184">Come si può notare, questi file docker-compose avviano solo i microservizi di Redis, RabbitMQ, SQL Server e MongoDB.</span><span class="sxs-lookup"><span data-stu-id="898a7-184">As you can see, these docker-compose files only start the Redis, RabbitMQ, SQL Server and MongoDB microservices.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="898a7-185">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="898a7-185">Additional resources</span></span>

- <span data-ttu-id="898a7-186">**File LEGGIMI dei test** nel repository di eShopOnContainers in GitHub </span><span class="sxs-lookup"><span data-stu-id="898a7-186">**Tests README file** on the eShopOnContainers repo on GitHub </span></span>\
    <https://github.com/dotnet-architecture/eShopOnContainers/tree/dev/test>

- <span data-ttu-id="898a7-187">**File LEGGIMI dei test di carico** nel repository di eShopOnContainers in GitHub </span><span class="sxs-lookup"><span data-stu-id="898a7-187">**Load tests README file** on the eShopOnContainers repo on GitHub </span></span>\
    <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/test/ServicesTests/LoadTest/>

> [!div class="step-by-step"]
> <span data-ttu-id="898a7-188">[Successivo](subscribe-events.md)
> [precedente](background-tasks-with-ihostedservice.md)</span><span class="sxs-lookup"><span data-stu-id="898a7-188">[Previous](subscribe-events.md)
[Next](background-tasks-with-ihostedservice.md)</span></span>
