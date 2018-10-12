---
title: Test delle app Web e dei servizi ASP.NET di base
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Test delle app Web e dei servizi ASP.NET di base
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 2702a273ade0e58ba93d556cfd1ecc5531027f93
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2018
ms.locfileid: "47232859"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="2f839-103">Test delle app Web e dei servizi ASP.NET di base</span><span class="sxs-lookup"><span data-stu-id="2f839-103">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="2f839-104">I controller sono un componente essenziale di qualsiasi servizio API ASP.NET Core e applicazione Web MVC ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2f839-104">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="2f839-105">Di conseguenza è importante verificare che funzionino correttamente nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f839-105">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="2f839-106">I test automatizzati eseguono questa verifica e rilevano gli errori dei controller prima che questi raggiungano la fase di produzione.</span><span class="sxs-lookup"><span data-stu-id="2f839-106">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="2f839-107">È necessario testare il comportamento del controller in base a input valido o non validi ed eseguire il test delle risposte del controller in base ai risultati dell'operazione di business effettuata.</span><span class="sxs-lookup"><span data-stu-id="2f839-107">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="2f839-108">Tuttavia, è necessario avere i seguenti tipi di test nei microservizi:</span><span class="sxs-lookup"><span data-stu-id="2f839-108">However, you should have these types of tests for your microservices:</span></span>

-   <span data-ttu-id="2f839-109">Unit test.</span><span class="sxs-lookup"><span data-stu-id="2f839-109">Unit tests.</span></span> <span data-ttu-id="2f839-110">Garantiscono il funzionamento previsto dei singoli componenti dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2f839-110">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="2f839-111">Le asserzioni testano l'API componente.</span><span class="sxs-lookup"><span data-stu-id="2f839-111">Assertions test the component API.</span></span>

-   <span data-ttu-id="2f839-112">Test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="2f839-112">Integration tests.</span></span> <span data-ttu-id="2f839-113">Garantiscono il funzionamento previsto delle interazioni tra componenti rispetto a elementi esterni, come i database.</span><span class="sxs-lookup"><span data-stu-id="2f839-113">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="2f839-114">Le asserzioni possono testare l'API componente, l'interfaccia utente o gli effetti collaterali di azioni come input/output nei database, registrazione e così via.</span><span class="sxs-lookup"><span data-stu-id="2f839-114">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="2f839-115">Test funzionali per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="2f839-115">Functional tests for each microservice.</span></span> <span data-ttu-id="2f839-116">Garantiscono il funzionamento previsto dell'applicazione dal punto di vista dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2f839-116">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="2f839-117">Test di servizio.</span><span class="sxs-lookup"><span data-stu-id="2f839-117">Service tests.</span></span> <span data-ttu-id="2f839-118">Garantiscono l'esecuzione del test dei casi d'uso dei servizi end-to-end, tra cui il test simultaneo di più servizi.</span><span class="sxs-lookup"><span data-stu-id="2f839-118">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="2f839-119">Per questo tipo di test, è necessario preparare prima l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2f839-119">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="2f839-120">In questo caso, ciò significa avviare i servizi (ad esempio, usando il comando docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="2f839-120">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="2f839-121">Implementazione di unit test per le API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="2f839-121">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="2f839-122">Lo unit test prevede l'esecuzione di test su una parte di un'applicazione isolandola dall'infrastruttura e dalle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="2f839-122">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="2f839-123">Quando si sottopone a unit test la logica del controller, si verifica solo il contenuto di una singola azione o metodo e non il comportamento delle relative dipendenze o del framework.</span><span class="sxs-lookup"><span data-stu-id="2f839-123">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="2f839-124">Gli unit test non rilevano i problemi dell'interazione tra componenti: a questo scopo esistono i test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="2f839-124">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="2f839-125">Quando si sottopongono a unit test le azioni del controller, è importante concentrarsi esclusivamente sul funzionamento del relativo controller.</span><span class="sxs-lookup"><span data-stu-id="2f839-125">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="2f839-126">Uno unit test del controller non prende in esame elementi come filtri, routing o associazione di modelli.</span><span class="sxs-lookup"><span data-stu-id="2f839-126">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="2f839-127">Gli unit test risultano in genere facili da creare e rapidi da eseguire, perché verificano un solo aspetto.</span><span class="sxs-lookup"><span data-stu-id="2f839-127">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="2f839-128">Un set di unit test ben organizzato può essere eseguito spesso senza sovraccarichi eccessivi.</span><span class="sxs-lookup"><span data-stu-id="2f839-128">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="2f839-129">Gli unit test vengono implementati in base ai framework di test come xUnit.net, MSTest, Moq o NUnit.</span><span class="sxs-lookup"><span data-stu-id="2f839-129">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="2f839-130">Per l'applicazione di esempio eShopOnContainers, useremo xUnit.</span><span class="sxs-lookup"><span data-stu-id="2f839-130">For the eShopOnContainers sample application, we are using xUnit.</span></span>

<span data-ttu-id="2f839-131">Quando si scrive uno unit test per un controller API Web, si crea direttamente un'istanza della classe controller usando la nuova parola chiave in C\#, in modo che il test venga eseguito il più velocemente possibile.</span><span class="sxs-lookup"><span data-stu-id="2f839-131">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="2f839-132">L'esempio seguente illustra come eseguire questa operazione usando [xUnit](https://xunit.github.io/) come framework di test.</span><span class="sxs-lookup"><span data-stu-id="2f839-132">The following example shows how to do this when using [xUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="2f839-133">Implementazione dei test funzionali e di integrazione per ogni microservizio</span><span class="sxs-lookup"><span data-stu-id="2f839-133">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="2f839-134">Come già indicato, i test di integrazione e i test funzionali hanno scopi e obiettivi diversi.</span><span class="sxs-lookup"><span data-stu-id="2f839-134">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="2f839-135">Tuttavia, la modalità di implementazione di entrambi durante il test dei controller ASP.NET Core è simile, dunque questa sezione è incentrata sui test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="2f839-135">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="2f839-136">Il test di integrazione garantisce che i componenti di un'applicazione funzionino correttamente quando assemblati.</span><span class="sxs-lookup"><span data-stu-id="2f839-136">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="2f839-137">ASP.NET Core supporta i test di integrazione con framework di unit test e un host Web di test predefinito che può essere usato per gestire le richieste senza sovraccarico di rete.</span><span class="sxs-lookup"><span data-stu-id="2f839-137">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="2f839-138">A differenza degli unit test, i test di integrazione comportano spesso preoccupazioni relative all'infrastruttura dell'applicazione, ad esempio il database, il file system, le risorse di rete o le richieste e risposte Web.</span><span class="sxs-lookup"><span data-stu-id="2f839-138">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="2f839-139">Gli unit test usano dati falsi o oggetti fittizi al posto di queste preoccupazioni,</span><span class="sxs-lookup"><span data-stu-id="2f839-139">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="2f839-140">ma lo scopo dei test di integrazione è confermare il funzionamento previsto del sistema, dunque è inutile usare dati falsi oppure oggetti fittizi.</span><span class="sxs-lookup"><span data-stu-id="2f839-140">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="2f839-141">Si includerà piuttosto l'infrastruttura, come l'accesso al database o la chiamata di un servizio da altri servizi.</span><span class="sxs-lookup"><span data-stu-id="2f839-141">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="2f839-142">Visto che esercitano segmenti di codice più grandi rispetto agli unit test e si basano sugli elementi dell'infrastruttura, i test di integrazione tendono a essere notevolmente più lenti rispetto agli unit test.</span><span class="sxs-lookup"><span data-stu-id="2f839-142">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="2f839-143">Di conseguenza, è consigliabile limitare il numero di test di integrazione da scrivere ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="2f839-143">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="2f839-144">ASP.NET Core include un host Web di test predefinito che può essere usato per gestire le richieste HTTP senza il sovraccarico di rete, vale a dire che è possibile eseguire più rapidamente i test quando si usa un host Web reale.</span><span class="sxs-lookup"><span data-stu-id="2f839-144">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="2f839-145">L'host Web di test è disponibile in un componente NuGet come Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="2f839-145">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="2f839-146">Può essere aggiunto ai progetti di test di integrazione e usato per ospitare le applicazioni ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2f839-146">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="2f839-147">Come si può notare nel codice seguente, quando si creano test di integrazione per i controller ASP.NET Core, si crea l'istanza dei controller attraverso l'host di test.</span><span class="sxs-lookup"><span data-stu-id="2f839-147">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="2f839-148">Ciò è paragonabile a una richiesta HTTP, ma viene eseguita più rapidamente.</span><span class="sxs-lookup"><span data-stu-id="2f839-148">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="2f839-149">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2f839-149">Additional resources</span></span>

-   <span data-ttu-id="2f839-150">**Steve Smith. Testing controllers** (Test dei controller) (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="2f839-150">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="2f839-151">**Steve Smith. Integration testing** (Test di integrazione) (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/test/integration-tests*](/aspnet/core/test/integration-tests)</span><span class="sxs-lookup"><span data-stu-id="2f839-151">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/test/integration-tests*](/aspnet/core/test/integration-tests)</span></span>

-   <span data-ttu-id="2f839-152">**Unit Testing in .NET Core using dotnet test**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md) (Testing unità in .NET Core con il test dotnet)</span><span class="sxs-lookup"><span data-stu-id="2f839-152">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)</span></span>

-   <span data-ttu-id="2f839-153">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="2f839-153">**xUnit.net**.</span></span> <span data-ttu-id="2f839-154">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="2f839-154">Official site.</span></span>
    [*https://xunit.github.io/*](https://xunit.github.io/)

-   <span data-ttu-id="2f839-155">**Nozioni di base sugli unit test.**
    [*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="2f839-155">**Unit Test Basics.**
[*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="2f839-156">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="2f839-156">**Moq**.</span></span> <span data-ttu-id="2f839-157">Repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="2f839-157">GitHub repo.</span></span>
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   <span data-ttu-id="2f839-158">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="2f839-158">**NUnit**.</span></span> <span data-ttu-id="2f839-159">Sito ufficiale.</span><span class="sxs-lookup"><span data-stu-id="2f839-159">Official site.</span></span>
    [*https://www.nunit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="2f839-160">Implementazione di test di servizio in un'applicazione a più contenitori</span><span class="sxs-lookup"><span data-stu-id="2f839-160">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="2f839-161">Come indicato in precedenza, quando si testano applicazioni a più contenitori, tutti i microservizi devono essere eseguiti all'interno dell'host Docker o del cluster di contenitori.</span><span class="sxs-lookup"><span data-stu-id="2f839-161">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="2f839-162">I test di servizio end-to-end che includono più operazioni che implicano diversi microservizi richiedono la distribuzione e l'avvio dell'intera applicazione nell'host Docker con l'esecuzione del comando docker-compose up (o un meccanismo analogo, se si usa un agente di orchestrazione).</span><span class="sxs-lookup"><span data-stu-id="2f839-162">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="2f839-163">Quando l'intera applicazione e tutti i relativi servizi saranno in esecuzione, sarà possibile eseguire i test funzionali e di integrazione end-to-end.</span><span class="sxs-lookup"><span data-stu-id="2f839-163">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="2f839-164">Sono possibili alcuni approcci.</span><span class="sxs-lookup"><span data-stu-id="2f839-164">There are a few approaches you can use.</span></span> <span data-ttu-id="2f839-165">Nel file docker-compose.yml usato per distribuire l'applicazione (o file simili, come docker-compose.ci.build.yml), a livello di soluzione è possibile espandere il punto di ingresso in modo da usare [dotnet test](../../../core/tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="2f839-165">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="2f839-166">È anche possibile usare un altro file Compose che esegua i test nell'immagine specificata come destinazione.</span><span class="sxs-lookup"><span data-stu-id="2f839-166">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="2f839-167">Se per i test di integrazione si usa un altro file Compose che include i microservizi e i database nei contenitori, ci si assicura di ripristinare sempre lo stato originale dei dati correlati prima di eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="2f839-167">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="2f839-168">Quando l'applicazione Compose è operativa, è possibile sfruttare i punti di interruzione e le eccezioni se si esegue Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2f839-168">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="2f839-169">In alternativa, è possibile eseguire i test di integrazione nella pipeline CI in Azure DevOps Services o qualsiasi altro sistema di integrazione continua/recapito continuo che supporti i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="2f839-169">Or you can run the integration tests automatically in your CI pipeline in Azure DevOps Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="2f839-170">[Precedente](subscribe-events.md)
[Successivo](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="2f839-170">[Previous](subscribe-events.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
