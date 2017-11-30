---
title: Il monitoraggio dello stato
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Il monitoraggio dello stato
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a><span data-ttu-id="2b7eb-104">Il monitoraggio dello stato</span><span class="sxs-lookup"><span data-stu-id="2b7eb-104">Health monitoring</span></span>

<span data-ttu-id="2b7eb-105">Monitoraggio dell'integrità, è possibile consentire tempo quasi reale informazioni sullo stato dei contenitori e microservizi.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-105">Health monitoring can allow near-real-time information about the state of your containers and microservices.</span></span> <span data-ttu-id="2b7eb-106">Il monitoraggio dello stato è fondamentale per vari aspetti di microservizi operativo ed è particolarmente importante quando orchestrators eseguire gli aggiornamenti dell'applicazione parziale in fasi, come illustrato in seguito.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-106">Health monitoring is critical to multiple aspects of operating microservices and is especially important when orchestrators perform partial application upgrades in phases, as explained later.</span></span>

<span data-ttu-id="2b7eb-107">Applicazioni basate su Microservizi utilizzano spesso gli heartbeat o controlli di integrità per abilitare i monitoraggi delle prestazioni, le utilità di pianificazione e orchestrators tenere traccia della grande varietà di servizi.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-107">Microservices-based applications often use heartbeats or health checks to enable their performance monitors, schedulers, and orchestrators to keep track of the multitude of services.</span></span> <span data-ttu-id="2b7eb-108">Se i servizi non è possibile inviare una qualche forma di segnale "Sto alive", su richiesta o in una pianificazione, l'applicazione potrebbe essere esposti i rischi quando si distribuiscono gli aggiornamenti o potrebbe semplicemente rilevare più errori e non essere in grado di arrestare gli errori CSS che possono finire in interruzioni significative.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-108">If services cannot send some sort of “I’m alive” signal, either on demand or on a schedule, your application might face risks when you deploy updates, or it might simply detect failures too late and not be able to stop cascading failures that can end up in major outages.</span></span>

<span data-ttu-id="2b7eb-109">Nel tipico modello di servizi di inviare report sullo stato e tali informazioni vengono aggregate per fornire una visualizzazione complessiva dello stato di integrità dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-109">In the typical model, services send reports about their status, and that information is aggregated to provide an overall view of the state of health of your application.</span></span> <span data-ttu-id="2b7eb-110">Se si utilizza l'agente di orchestrazione, è possibile fornire informazioni di integrità al cluster di orchestrator, in modo che il cluster può agire di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-110">If you are using an orchestrator, you can provide health information to your orchestrator’s cluster, so that the cluster can act accordingly.</span></span> <span data-ttu-id="2b7eb-111">Se investire in report di integrità di alta qualità personalizzato per l'applicazione, è possibile rilevare e risolvere i problemi dell'applicazione in esecuzione molto più facilmente.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-111">If you invest in high-quality health reporting that is customized for your application, you can detect and fix issues for your running application much more easily.</span></span>

## <a name="implementing-health-checks-in-aspnet-core-services"></a><span data-ttu-id="2b7eb-112">Implementazione di integrità controlla in servizi di base di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2b7eb-112">Implementing health checks in ASP.NET Core services</span></span>

<span data-ttu-id="2b7eb-113">Quando si sviluppa un'applicazione web o microservizio di ASP.NET Core, è possibile utilizzare una libreria denominata HealthChecks dal team di ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-113">When developing an ASP.NET Core microservice or web application, you can use a library named HealthChecks from the ASP.NET team.</span></span> <span data-ttu-id="2b7eb-114">(A partire da maggio 2017, una versione preliminare è disponibile su GitHub).</span><span class="sxs-lookup"><span data-stu-id="2b7eb-114">(As of May 2017, an early release is available on GitHub).</span></span>

<span data-ttu-id="2b7eb-115">Questa libreria è facile da usare e offre funzionalità che consentono che convalidare il corretto funzionamento qualsiasi risorsa esterna specifico necessario per l'applicazione (ad esempio un database di SQL Server o l'API remota).</span><span class="sxs-lookup"><span data-stu-id="2b7eb-115">This library is easy to use and provides features that let you validate that any specific external resource needed for your application (like a SQL Server database or remote API) is working properly.</span></span> <span data-ttu-id="2b7eb-116">Quando si usa questa libreria, è possibile decidere cosa significa che la risorsa sia integra, come viene descritto più avanti.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-116">When you use this library, you can also decide what it means that the resource is healthy, as we explain later.</span></span>

<span data-ttu-id="2b7eb-117">Per utilizzare questa raccolta, è necessario utilizzare prima la libreria nel microservizi.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-117">In order to use this library, you need to first use the library in your microservices.</span></span> <span data-ttu-id="2b7eb-118">In secondo luogo, è necessaria un'applicazione front-end che esegue una query per i report sull'integrità.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-118">Second, you need a front-end application that queries for the health reports.</span></span> <span data-ttu-id="2b7eb-119">Applicazione front-end potrebbe essere un'applicazione di creazione di report personalizzata oppure può trattarsi di un agente di orchestrazione stessa che possa agire di conseguenza per gli stati di integrità.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-119">That front end application could be a custom reporting application, or it could be an orchestrator itself that can react accordingly to the health states.</span></span>

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a><span data-ttu-id="2b7eb-120">Utilizza la libreria HealthChecks nel back end del microservizi ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2b7eb-120">Using the HealthChecks library in your back end ASP.NET microservices</span></span>

<span data-ttu-id="2b7eb-121">È possibile visualizzare l'utilizzo nell'applicazione di esempio eShopOnContainers HealthChecks libreria.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-121">You can see how the HealthChecks library is used in the eShopOnContainers sample application.</span></span> <span data-ttu-id="2b7eb-122">Per iniziare, è necessario definire gli elementi che costituiscono uno stato integro per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-122">To begin, you need to define what constitutes a healthy status for each microservice.</span></span> <span data-ttu-id="2b7eb-123">Nell'applicazione di esempio, di microservizi sono integri se microservizio API accessibile mediante HTTP e se è disponibile anche il database di SQL Server correlato.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-123">In the sample application, the microservices are healthy if the microservice API is accessible via HTTP and if its related SQL Server database is also available.</span></span>

<span data-ttu-id="2b7eb-124">In futuro, sarà in grado di installare la libreria HealthChecks come pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-124">In the future, you will be able to install the HealthChecks library as a NuGet package.</span></span> <span data-ttu-id="2b7eb-125">Ma redazione del presente documento, è necessario scaricare e compilare il codice come parte della soluzione.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-125">But as of this writing, you need to download and compile the code as part of your solution.</span></span> <span data-ttu-id="2b7eb-126">Clonare il codice disponibile all'indirizzo https://github.com/aspnet/HealthChecks e copiare le cartelle seguenti per la soluzione.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-126">Clone the code available at https://github.com/aspnet/HealthChecks and copy the following folders to your solution.</span></span>

  - <span data-ttu-id="2b7eb-127">src o comune</span><span class="sxs-lookup"><span data-stu-id="2b7eb-127">src/common</span></span>
  - <span data-ttu-id="2b7eb-128">src/Microsoft.AspNetCore.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="2b7eb-128">src/Microsoft.AspNetCore.HealthChecks</span></span>
  - <span data-ttu-id="2b7eb-129">src/Microsoft.Extensions.HealthChecks</span><span class="sxs-lookup"><span data-stu-id="2b7eb-129">src/Microsoft.Extensions.HealthChecks</span></span>
  - <span data-ttu-id="2b7eb-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span><span class="sxs-lookup"><span data-stu-id="2b7eb-130">src/Microsoft.Extensions.HealthChecks.SqlServer</span></span>

<span data-ttu-id="2b7eb-131">È anche possibile usare i controlli aggiuntivi, come quelle per Azure (Microsoft.Extensions.HealthChecks.AzureStorage), ma poiché questa versione di eShopOnContainers non dispone di tutte le dipendenze in Azure, non è necessario.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-131">You could also use additional checks like the ones for Azure (Microsoft.Extensions.HealthChecks.AzureStorage), but since this version of eShopOnContainers does not have any dependency on Azure, you do not need it.</span></span> <span data-ttu-id="2b7eb-132">I controlli di integrità ASP.NET, non è necessario poiché eShopOnContainers è basato su ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-132">You do not need the ASP.NET health checks, because eShopOnContainers is based on ASP.NET Core.</span></span>

<span data-ttu-id="2b7eb-133">Figura 10-6 è illustrata la libreria HealthChecks in Visual Studio, pronto per essere utilizzato come un blocco di compilazione da qualsiasi microservizi.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-133">Figure 10-6 shows the HealthChecks library in Visual Studio, ready to be used as a building block by any microservices.</span></span>

![](./media/image6.png)

<span data-ttu-id="2b7eb-134">**Figura 10-6**.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-134">**Figure 10-6**.</span></span> <span data-ttu-id="2b7eb-135">Codice sorgente della libreria ASP.NET Core HealthChecks in una soluzione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2b7eb-135">ASP.NET Core HealthChecks library source code in a Visual Studio solution</span></span>

<span data-ttu-id="2b7eb-136">Come descritto in precedenza, la prima cosa da eseguire in ogni progetto microservizio consiste nell'aggiungere un riferimento alle librerie HealthChecks tre.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-136">As introduced earlier, the first thing to do in each microservice project is to add a reference to the three HealthChecks libraries.</span></span> <span data-ttu-id="2b7eb-137">Successivamente, aggiungere le azioni di controllo di integrità che si desidera eseguire in tale microservizio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-137">After that, you add the health check actions that you want to perform in that microservice.</span></span> <span data-ttu-id="2b7eb-138">Queste azioni sono fondamentalmente dipendenze da altri microservizi (HttpUrlCheck) o un database (attualmente SqlCheck\* per i database di SQL Server).</span><span class="sxs-lookup"><span data-stu-id="2b7eb-138">These actions are basically dependencies on other microservices (HttpUrlCheck) or databases (currently SqlCheck\* for SQL Server databases).</span></span> <span data-ttu-id="2b7eb-139">Aggiungere l'azione all'interno della classe di avvio di ogni microservizio ASP.NET o applicazione web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-139">You add the action within the Startup class of each ASP.NET microservice or ASP.NET web application.</span></span>

<span data-ttu-id="2b7eb-140">Ogni servizio o un'applicazione web deve essere configurata tramite l'aggiunta di tutte le dipendenze HTTP o un database come un metodo AddHealthCheck.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-140">Each service or web application should be configured by adding all its HTTP or database dependencies as one AddHealthCheck method.</span></span> <span data-ttu-id="2b7eb-141">Ad esempio, l'applicazione web MVC da eShopOnContainers dipende da molti servizi, pertanto dispone di diversi metodi AddCheck aggiunti per i controlli di integrità.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-141">For example, the MVC web application from eShopOnContainers depends on many services, therefore has several AddCheck methods added to the health checks.</span></span>

<span data-ttu-id="2b7eb-142">Ad esempio, nel codice seguente è possibile visualizzare come microservizio il catalogo aggiunge una dipendenza sul proprio database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-142">For instance, in the following code you can see how the catalog microservice adds a dependency on its SQL Server database.</span></span>

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

<span data-ttu-id="2b7eb-143">Tuttavia, l'applicazione web MVC di eShopOnContainers presenta più dipendenze nelle restanti di microservizi.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-143">However, the MVC web application of eShopOnContainers has multiple dependencies on the rest of the microservices.</span></span> <span data-ttu-id="2b7eb-144">Pertanto, viene chiamato un metodo di AddUrlCheck per ogni microservizio, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2b7eb-144">Therefore, it calls one AddUrlCheck method for each microservice, as shown in the following example:</span></span>

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

<span data-ttu-id="2b7eb-145">Di conseguenza, un microservizio non fornisce uno stato "Integro" fino a quando tutti i controlli sono anche integro.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-145">Thus, a microservice will not provide a “healthy” status until all its checks are healthy as well.</span></span>

<span data-ttu-id="2b7eb-146">Se il microservizio non ha una dipendenza su un servizio o in SQL Server, è consigliabile aggiungere solo un controllo Healthy("Ok").</span><span class="sxs-lookup"><span data-stu-id="2b7eb-146">If the microservice does not have a dependency on a service or on SQL Server, you should just add a Healthy("Ok") check.</span></span> <span data-ttu-id="2b7eb-147">Il codice seguente è tratto dal microservizio basket.api eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-147">The following code is from the eShopOnContainers basket.api microservice.</span></span> <span data-ttu-id="2b7eb-148">(Il microservizio basket utilizza la cache Redis, ma la libreria non è ancora incluso un provider di controllo di integrità di Redis).</span><span class="sxs-lookup"><span data-stu-id="2b7eb-148">(The basket microservice uses the Redis cache, but the library does not yet include a Redis health check provider.)</span></span>

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

<span data-ttu-id="2b7eb-149">Per un'applicazione web o di servizio per esporre l'endpoint di controllo di integrità, deve abilitare l'UseHealthChecks (\[*url\_per\_integrità\_controlla*\]) estensione metodo.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-149">For a service or web application to expose the health check endpoint, it has to enable the UseHealthChecks(\[*url\_for\_health\_checks*\]) extension method.</span></span> <span data-ttu-id="2b7eb-150">Questo metodo passa a di WebHostBuilder livello nel metodo main della classe di programma dell'applicazione web o servizio di ASP.NET Core, subito dopo UseKestrel come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-150">This method goes at the WebHostBuilder level in the main method of the Program class of your ASP.NET Core service or web application, right after UseKestrel as shown in the code below.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

<span data-ttu-id="2b7eb-151">Il processo è simile al seguente: ogni microservizio espone /hc l'endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-151">The process works like this: each microservice exposes the endpoint /hc.</span></span> <span data-ttu-id="2b7eb-152">Tale endpoint viene creato dalla libreria HealthChecks middleware ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-152">That endpoint is created by the HealthChecks library ASP.NET Core middleware.</span></span> <span data-ttu-id="2b7eb-153">Quando tale endpoint viene richiamato, viene eseguito tutti i controlli di integrità configurati nel metodo AddHealthChecks nella classe di avvio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-153">When that endpoint is invoked, it runs all the health checks that are configured in the AddHealthChecks method in the Startup class.</span></span>

<span data-ttu-id="2b7eb-154">Il metodo UseHealthChecks prevede una porta o un percorso.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-154">The UseHealthChecks method expects a port or a path.</span></span> <span data-ttu-id="2b7eb-155">Porta o un percorso è l'endpoint da utilizzare per controllare lo stato di integrità del servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-155">That port or path is the endpoint to use to check the health state of the service.</span></span> <span data-ttu-id="2b7eb-156">Ad esempio, il catalogo di microservizio utilizza /hc il percorso.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-156">For instance, the catalog microservice uses the path /hc.</span></span>

### <a name="caching-health-check-responses"></a><span data-ttu-id="2b7eb-157">La memorizzazione nella cache le risposte di controllo di integrità</span><span class="sxs-lookup"><span data-stu-id="2b7eb-157">Caching health check responses</span></span>

<span data-ttu-id="2b7eb-158">Poiché non si desidera causare un attacco Denial of Service (DoS) nei servizi, o semplicemente non desidera abbiano un impatto sulle prestazioni del servizio mediante il controllo delle risorse troppo di frequente, è possibile memorizzare nella cache restituisce e configurare una durata della cache per ogni controllo di integrità.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-158">Since you do not want to cause a Denial of Service (DoS) in your services, or you simply do not want to impact service performance by checking resources too frequently, you can cache the returns and configure a cache duration for each health check.</span></span>

<span data-ttu-id="2b7eb-159">Per impostazione predefinita, la durata della cache internamente è impostata su 5 minuti, ma è possibile modificare la durata della cache in ogni controllo di integrità, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="2b7eb-159">By default, the cache duration is internally set to 5 minutes, but you can change that cache duration on each health check, as in the following code:</span></span>

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a><span data-ttu-id="2b7eb-160">L'esecuzione di query del microservizi report sul loro stato di integrità</span><span class="sxs-lookup"><span data-stu-id="2b7eb-160">Querying your microservices to report about their health status</span></span>

<span data-ttu-id="2b7eb-161">Dopo aver configurato i controlli di integrità, come descritto in questo caso, quando il microservizio è in esecuzione in Docker, è possibile direttamente verificare da un browser se è integro.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-161">When you have configured health checks as described here, once the microservice is running in Docker, you can directly check from a browser if it is healthy.</span></span> <span data-ttu-id="2b7eb-162">Per questo è necessario che si sta pubblicando la porta del contenitore tramite l'host Docker, pertanto è possibile accedere al contenitore tramite localhost o l'indirizzo IP esterno host Docker. Nella figura 10-7 mostra una richiesta in un browser e la risposta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-162">(This does require that you are publishing the container port out of the Docker host, so you can access the container through localhost or through the external Docker host IP.) Figure 10-7 shows a request in a browser and the corresponding response.</span></span>

![](./media/image7.png)

<span data-ttu-id="2b7eb-163">**Nella figura 10-7**.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-163">**Figure 10-7**.</span></span> <span data-ttu-id="2b7eb-164">Verifica dello stato di integrità di un singolo servizio da un browser</span><span class="sxs-lookup"><span data-stu-id="2b7eb-164">Checking health status of a single service from a browser</span></span>

<span data-ttu-id="2b7eb-165">In test, si noterà che il microservizio catalog.api (in esecuzione sulla porta 5101) sia integro, la restituzione di informazioni sullo stato e stato HTTP 200 in JSON.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-165">In that test, you can see that the catalog.api microservice (running on port 5101) is healthy, returning HTTP status 200 and status information in JSON.</span></span> <span data-ttu-id="2b7eb-166">Significa anche che il servizio internamente l'integrità della relativa dipendenza di database di SQL Server anche selezionata e che il controllo di integrità è stato rilevato come integro.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-166">It also means that internally the service also checked the health of its SQL Server database dependency and that health check was reported itself as healthy.</span></span>

## <a name="using-watchdogs"></a><span data-ttu-id="2b7eb-167">Utilizzo di watchdog</span><span class="sxs-lookup"><span data-stu-id="2b7eb-167">Using watchdogs</span></span>

<span data-ttu-id="2b7eb-168">Un controllo è un servizio separato che può controllare l'integrità e il carico tra servizi e segnalare l'integrità sul microservizi eseguendo una query con la libreria HealthChecks introdotta in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-168">A watchdog is a separate service that can watch health and load across services, and report health about the microservices by querying with the HealthChecks library introduced earlier.</span></span> <span data-ttu-id="2b7eb-169">Ciò consente di evitare gli errori che non verrebbero rilevati in base alla visualizzazione di un singolo servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-169">This can help prevent errors that would not be detected based on the view of a single service.</span></span> <span data-ttu-id="2b7eb-170">Inoltre, watchdog sono un ottimo strumento per il codice host che è possibile eseguire azioni correttive per condizioni note senza interazione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-170">Watchdogs also are a good place to host code that can perform remediation actions for known conditions without user interaction.</span></span>

<span data-ttu-id="2b7eb-171">L'esempio eShopOnContainers contiene una pagina web che consente di visualizzare report di controllo dell'integrità di esempio, come illustrato nella figura 10-8.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-171">The eShopOnContainers sample contains a web page that displays sample health check reports, as shown in Figure 10-8.</span></span> <span data-ttu-id="2b7eb-172">Questo è il più semplice watchdog potrebbe aver, poiché tutto avviene è illustrato lo stato delle applicazioni web e microservizi in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-172">This is the simplest watchdog you could have, since all it does is shows the state of the microservices and web applications in eShopOnContainers.</span></span> <span data-ttu-id="2b7eb-173">In genere un watchdog accetta anche azioni quando viene rilevato stati non integri.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-173">Usually a watchdog also takes actions when it detects unhealthy states.</span></span>

![](./media/image8.png)

<span data-ttu-id="2b7eb-174">**Figura 10-8**.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-174">**Figure 10-8**.</span></span> <span data-ttu-id="2b7eb-175">Report di controllo di integrità di esempio in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="2b7eb-175">Sample health check report in eShopOnContainers</span></span>

<span data-ttu-id="2b7eb-176">In breve, il middleware ASP.NET della libreria ASP.NET Core HealthChecks fornisce un endpoint di controllo di integrità singolo per ogni microservizio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-176">In summary, the ASP.NET middleware of the ASP.NET Core HealthChecks library provides a single health check endpoint for each microservice.</span></span> <span data-ttu-id="2b7eb-177">Eseguire tutti i controlli di integrità definiti al suo interno, verrà restituito uno stato di integrità globale a seconda di tutti i controlli.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-177">This will execute all the health checks defined within it and return an overall health state depending on all those checks.</span></span>

<span data-ttu-id="2b7eb-178">La libreria HealthChecks è estensibile tramite nuovi controlli di integrità delle risorse esterne future.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-178">The HealthChecks library is extensible through new health checks of future external resources.</span></span> <span data-ttu-id="2b7eb-179">Ad esempio, si prevede che in futuro la libreria avrà controlli di integrità per cache Redis e per altri database.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-179">For example, we expect that in the future the library will have health checks for Redis cache and for other databases.</span></span> <span data-ttu-id="2b7eb-180">La libreria consente integrità segnalazione più dipendenze di servizio o applicazione e si possono intraprendere le azioni in base a tali controlli di integrità.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-180">The library allows health reporting by multiple service or application dependencies, and you can then take actions based on those health checks.</span></span>

## <a name="health-checks-when-using-orchestrators"></a><span data-ttu-id="2b7eb-181">Controlli di integrità quando si utilizza orchestrators</span><span class="sxs-lookup"><span data-stu-id="2b7eb-181">Health checks when using orchestrators</span></span>

<span data-ttu-id="2b7eb-182">Per monitorare la disponibilità del microservizi, orchestrators come Docker Swarm Kubernetes e Service Fabric periodicamente esegue controlli di integrità inviando richieste per eseguire il test di microservizi.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-182">To monitor the availability of your microservices, orchestrators like Docker Swarm, Kubernetes, and Service Fabric periodically perform health checks by sending requests to test the microservices.</span></span> <span data-ttu-id="2b7eb-183">Quando un agente di orchestrazione determina che un servizio o del contenitore non è integro, che si arresta il routing delle richieste a tale istanza.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-183">When an orchestrator determines that a service/container is unhealthy, it stops routing requests to that instance.</span></span> <span data-ttu-id="2b7eb-184">In genere anche crea una nuova istanza di tale contenitore.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-184">It also usually creates a new instance of that container.</span></span>

<span data-ttu-id="2b7eb-185">Ad esempio, orchestrators la maggior parte possibile utilizzare controlli di integrità per gestire le distribuzioni senza tempi di inattività.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-185">For instance, most orchestrators can use health checks to manage zero-downtime deployments.</span></span> <span data-ttu-id="2b7eb-186">Solo quando lo stato di un servizio o del contenitore diventa integro sarà l'agente di orchestrazione avviare routing del traffico per le istanze di servizio o del contenitore.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-186">Only when the status of a service/container changes to healthy will the orchestrator start routing traffic to service/container instances.</span></span>

<span data-ttu-id="2b7eb-187">Il monitoraggio dello stato è particolarmente importante quando un agente di orchestrazione esegue l'aggiornamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-187">Health monitoring is especially important when an orchestrator performs an application upgrade.</span></span> <span data-ttu-id="2b7eb-188">Alcuni orchestrators (ad esempio Azure Service Fabric) aggiornare i servizi in fasi, ad esempio, aggiornano un quinto della superficie di cluster per ogni aggiornamento dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-188">Some orchestrators (like Azure Service Fabric) update services in phases—for example, they might update one-fifth of the cluster surface for each application upgrade.</span></span> <span data-ttu-id="2b7eb-189">Il set di nodi che viene aggiornato allo stesso tempo viene considerato un *dominio di aggiornamento*.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-189">The set of nodes that is upgraded at the same time is referred to as an *upgrade domain*.</span></span> <span data-ttu-id="2b7eb-190">Dopo ogni dominio di aggiornamento è stato aggiornato ed è disponibile agli utenti, tale dominio di aggiornamento deve superare controlli di integrità prima di sposta la distribuzione per il dominio di aggiornamento successivo.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-190">After each upgrade domain has been upgraded and is available to users, that upgrade domain must pass health checks before the deployment moves to the next upgrade domain.</span></span>

<span data-ttu-id="2b7eb-191">Un altro aspetto dell'integrità del servizio segnala le metriche dal servizio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-191">Another aspect of service health is reporting metrics from the service.</span></span> <span data-ttu-id="2b7eb-192">Si tratta di una funzionalità avanzata del modello di integrità di alcuni orchestrators, ad esempio Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-192">This is an advanced capability of the health model of some orchestrators, like Service Fabric.</span></span> <span data-ttu-id="2b7eb-193">Le metriche sono importanti quando si usa l'agente di orchestrazione perché vengono usate per bilanciare l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-193">Metrics are important when using an orchestrator because they are used to balance resource usage.</span></span> <span data-ttu-id="2b7eb-194">Le metriche, inoltre, possono essere un indicatore dello stato del sistema.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-194">Metrics also can be an indicator of system health.</span></span> <span data-ttu-id="2b7eb-195">Ad esempio, potrebbe essere un'applicazione che dispone di molti microservizi e ogni istanza segnala una metrica di richieste al secondo (RPS).</span><span class="sxs-lookup"><span data-stu-id="2b7eb-195">For example, you might have an application that has many microservices, and each instance reports a requests-per-second (RPS) metric.</span></span> <span data-ttu-id="2b7eb-196">Se un servizio utilizza più risorse (memoria, processore, e così via) rispetto a un altro servizio, l'agente di orchestrazione potrebbe spostare le istanze del servizio all'interno del cluster per tentare di gestire anche l'utilizzo delle risorse.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-196">If one service is using more resources (memory, processor, etc.) than another service, the orchestrator could move service instances around in the cluster to try to maintain even resource utilization.</span></span>

<span data-ttu-id="2b7eb-197">Si noti che se si utilizza Azure Service Fabric, fornisce il proprio [modello monitoraggio dell'integrità](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), ovvero più avanzata rispetto a controlli di integrità semplice.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-197">Note that if you are using Azure Service Fabric, it provides its own [Health Monitoring model](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), which is more advanced than simple health checks.</span></span>

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a><span data-ttu-id="2b7eb-198">Monitoraggio avanzate: visualizzazione e analisi degli avvisi</span><span class="sxs-lookup"><span data-stu-id="2b7eb-198">Advanced monitoring: visualization, analysis, and alerts</span></span>

<span data-ttu-id="2b7eb-199">La parte finale del monitoraggio Visualizza flusso di eventi, generazione di report sulle prestazioni del servizio e di avviso quando viene rilevato un problema.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-199">The final part of monitoring is visualizing the event stream, reporting on service performance, and alerting when an issue is detected.</span></span> <span data-ttu-id="2b7eb-200">È possibile utilizzare diverse soluzioni per questo aspetto del monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-200">You can use different solutions for this aspect of monitoring.</span></span>

<span data-ttu-id="2b7eb-201">È possibile utilizzare semplici applicazioni personalizzate che mostra lo stato dei servizi, ad esempio la pagina personalizzata abbiamo anche mostrato quando spiegare [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span><span class="sxs-lookup"><span data-stu-id="2b7eb-201">You can use simple custom applications showing the state of your services, like the custom page we showed when we explained [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks).</span></span> <span data-ttu-id="2b7eb-202">In alternativa, è possibile usare gli strumenti più avanzati come Azure Application Insights e Operations Management Suite per la generazione di avvisi in base al flusso di eventi.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-202">Or you could use more advanced tools like Azure Application Insights and Operations Management Suite to raise alerts based on the stream of events.</span></span>

<span data-ttu-id="2b7eb-203">Infine, se sono stati archiviati tutti i flussi di eventi, è possibile utilizzare Microsoft Power BI o una soluzione di terze parti, ad esempio Kibana o Splunk per visualizzare i dati.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-203">Finally, if you were storing all the event streams, you can use Microsoft Power BI or a third-party solution like Kibana or Splunk to visualize the data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b7eb-204">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2b7eb-204">Additional resources</span></span>

-   <span data-ttu-id="2b7eb-205">**ASP.NET Core HealthChecks** (versione preliminare) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span><span class="sxs-lookup"><span data-stu-id="2b7eb-205">**ASP.NET Core HealthChecks** (early release) [*https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)</span></span>

-   <span data-ttu-id="2b7eb-206">**Introduzione al monitoraggio dell'integrità dell'infrastruttura a servizio**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span><span class="sxs-lookup"><span data-stu-id="2b7eb-206">**Introduction to Service Fabric health monitoring**
[*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)</span></span>

-   <span data-ttu-id="2b7eb-207">**Applicazione Azure Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span><span class="sxs-lookup"><span data-stu-id="2b7eb-207">**Azure Application Insights**
[*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)</span></span>

-   <span data-ttu-id="2b7eb-208">**Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span><span class="sxs-lookup"><span data-stu-id="2b7eb-208">**Microsoft Operations Management Suite**
[*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="2b7eb-209">[Precedente] (implementa-circuito-breaker-pattern.md) [Avanti] (... /Secure-NET-microservices-Web-Applications/index.MD)</span><span class="sxs-lookup"><span data-stu-id="2b7eb-209">[Previous] (implement-circuit-breaker-pattern.md) [Next] (../secure-net-microservices-web-applications/index.md)</span></span>
