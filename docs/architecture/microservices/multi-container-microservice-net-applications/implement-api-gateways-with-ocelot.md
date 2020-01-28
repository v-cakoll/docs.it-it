---
title: Implementazione di gateway API con Ocelot
description: Informazioni su come implementare i gateway API con Ocelot e come usare Ocelot in un ambiente basato su contenitori.
ms.date: 10/02/2018
ms.openlocfilehash: 1ade05cc6935ce6a1bc74e6d6e4cdd5ef9fc6873
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734603"
---
# <a name="implement-api-gateways-with-ocelot"></a><span data-ttu-id="f394a-103">Implementare gateway API con Ocelot</span><span class="sxs-lookup"><span data-stu-id="f394a-103">Implement API Gateways with Ocelot</span></span>

<span data-ttu-id="f394a-104">L'applicazione di microservizio di riferimento [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) USA [Ocelot](https://github.com/ThreeMammals/Ocelot), un gateway API semplice e leggero che è possibile distribuire ovunque insieme ai microservizi/contenitori, ad esempio in uno degli ambienti seguenti usati da eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="f394a-104">The reference microservice application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) is using [Ocelot](https://github.com/ThreeMammals/Ocelot), a simple and lightweight API Gateway that you can deploy anywhere along with your microservices/containers, such as in any of the following environments used by eShopOnContainers:</span></span>

- <span data-ttu-id="f394a-105">Host Docker, nel PC di sviluppo locale, in locale o nel cloud.</span><span class="sxs-lookup"><span data-stu-id="f394a-105">Docker host, in your local dev PC, on-premises or in the cloud.</span></span>
- <span data-ttu-id="f394a-106">Cluster Kubernetes, in locale o nel servizio Azure Kubernetes gestito.</span><span class="sxs-lookup"><span data-stu-id="f394a-106">Kubernetes cluster, on-premises or in managed cloud such as Azure Kubernetes Service (AKS).</span></span>
- <span data-ttu-id="f394a-107">Cluster Service Fabric, in locale o nel cloud.</span><span class="sxs-lookup"><span data-stu-id="f394a-107">Service Fabric cluster, on-premises or in the cloud.</span></span>
- <span data-ttu-id="f394a-108">Mesh Service Fabric, come PaaS/Serverless in Azure.</span><span class="sxs-lookup"><span data-stu-id="f394a-108">Service Fabric mesh, as PaaS/Serverless in Azure.</span></span>

## <a name="architect-and-design-your-api-gateways"></a><span data-ttu-id="f394a-109">Creare l'architettura e progettare i propri gateway API</span><span class="sxs-lookup"><span data-stu-id="f394a-109">Architect and design your API Gateways</span></span>

<span data-ttu-id="f394a-110">Il seguente diagramma dell'architettura illustra in che modo i gateway API vengono implementati con Ocelot in eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f394a-110">The following architecture diagram shows how API Gateways are implemented with Ocelot in eShopOnContainers.</span></span>

![Diagramma che mostra l'architettura eShopOnContainers.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

<span data-ttu-id="f394a-112">**Figura 6-28**.</span><span class="sxs-lookup"><span data-stu-id="f394a-112">**Figure 6-28**.</span></span> <span data-ttu-id="f394a-113">Architettura di eShopOnContainers con gateway API</span><span class="sxs-lookup"><span data-stu-id="f394a-113">eShopOnContainers architecture with API Gateways</span></span>

<span data-ttu-id="f394a-114">Il diagramma mostra il modo in cui l'intera applicazione viene distribuita in un singolo host Docker o in un computer di sviluppo con "Docker per Windows" o "Docker per Mac".</span><span class="sxs-lookup"><span data-stu-id="f394a-114">That diagram shows how the whole application is deployed into a single Docker host or development PC with "Docker for Windows" or "Docker for Mac".</span></span> <span data-ttu-id="f394a-115">Tuttavia, la distribuzione in qualsiasi agente di orchestrazione è simile, ma qualsiasi contenitore nel diagramma può essere scalato orizzontalmente nell'agente di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-115">However, deploying into any orchestrator would be similar, but any container in the diagram could be scaled out in the orchestrator.</span></span>

<span data-ttu-id="f394a-116">Le risorse dell'infrastruttura, inoltre, ad esempio i database, la cache e i broker dei messaggi, devono essere scaricate dall'agente di orchestrazione e distribuite in sistemi a disponibilità elevata per l'infrastruttura, ad esempio Database SQL di Azure, Azure Cosmos DB, Redis di Azure, bus di servizio di Azure o qualsiasi altra soluzione di clustering a disponibilità elevata locale.</span><span class="sxs-lookup"><span data-stu-id="f394a-116">In addition, the infrastructure assets such as databases, cache, and message brokers should be offloaded from the orchestrator and deployed into high available systems for infrastructure, like Azure SQL Database, Azure Cosmos DB, Azure Redis, Azure Service Bus, or any HA clustering solution on-premises.</span></span>

<span data-ttu-id="f394a-117">Come si può notare anche nel diagramma, avere più gateway API consente a più team di sviluppo di essere autonomi (in questo caso funzionalità di marketing e funzionalità di acquisto) quando sviluppa e distribuisce i microservizi e i relativi gateway API correlati.</span><span class="sxs-lookup"><span data-stu-id="f394a-117">As you can also notice in the diagram, having several API Gateways allows multiple development teams to be autonomous (in this case Marketing features vs. Shopping features) when developing and deploying their microservices plus their own related API Gateways.</span></span>

<span data-ttu-id="f394a-118">Un unico gateway API monolitico significherebbe un unico punto che i vari team di sviluppo devono aggiornare, con conseguente rischio di duplicazione di tutti i microservizi con una singola parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-118">If you had a single monolithic API Gateway that would mean a single point to be updated by several development teams, which could couple all the microservices with a single part of the application.</span></span>

<span data-ttu-id="f394a-119">Analizzando il progetto più a fondo, un gateway API specifico può talvolta essere limitato anche a un singolo microservizio aziendale a seconda dell'architettura scelta.</span><span class="sxs-lookup"><span data-stu-id="f394a-119">Going much further in the design, sometimes a fine-grained API Gateway can also be limited to a single business microservice depending on the chosen architecture.</span></span> <span data-ttu-id="f394a-120">La presenza di limiti del gateway API dettati dall'azienda o dal dominio consentirà di ottenere una progettazione migliore.</span><span class="sxs-lookup"><span data-stu-id="f394a-120">Having the API Gateway's boundaries dictated by the business or domain will help you to get a better design.</span></span>

<span data-ttu-id="f394a-121">La granularità a livello di gateway API può essere particolarmente utile per le applicazioni con interfaccia utente composita più avanzate basate su microservizi, perché il concetto di gateway API specifico è analogo a quello di un servizio di composizione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="f394a-121">For instance, fine granularity in the API Gateway tier can be especially useful for more advanced composite UI applications that are based on microservices, because the concept of a fine-grained API Gateway is similar to a UI composition service.</span></span>

<span data-ttu-id="f394a-122">Altri dettagli sono illustrati nella sezione precedente [Creazione dell'interfaccia utente composita basata su microservizi](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span><span class="sxs-lookup"><span data-stu-id="f394a-122">We delve into more details in the previous section [Creating composite UI based on microservices](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).</span></span>

<span data-ttu-id="f394a-123">Come riferimento chiave, per molte applicazioni di medie e grandi dimensioni, l'utilizzo di un prodotto gateway API personalizzato rappresenta in genere un buon approccio, ma non come unico aggregatore monolitico o unico gateway API centrale personalizzato, a meno che tale gateway API non consenta più aree di configurazione indipendenti per i diversi team di sviluppo che creano microservizi autonomi.</span><span class="sxs-lookup"><span data-stu-id="f394a-123">As key takeaway, for many medium- and large-size applications, using a custom-built API Gateway product is usually a good approach, but not as a single monolithic aggregator or unique central custom API Gateway unless that API Gateway allows multiple independent configuration areas for the several development teams creating autonomous microservices.</span></span>

### <a name="sample-microservicescontainers-to-reroute-through-the-api-gateways"></a><span data-ttu-id="f394a-124">Microservizi/contenitori di esempio per il reindirizzamento tramite i gateway API</span><span class="sxs-lookup"><span data-stu-id="f394a-124">Sample microservices/containers to reroute through the API Gateways</span></span>

<span data-ttu-id="f394a-125">Per fare un esempio, eShopOnContainers include circa sei tipi di microservizi interni che devono essere pubblicati attraverso i gateway API, come illustrato nell'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="f394a-125">As an example, eShopOnContainers has around six internal microservice-types that have to be published through the API Gateways, as shown in the following image.</span></span>

![Screenshot della cartella dei servizi che mostra le relative sottocartelle.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

<span data-ttu-id="f394a-127">**Figura 6-29**.</span><span class="sxs-lookup"><span data-stu-id="f394a-127">**Figure 6-29**.</span></span> <span data-ttu-id="f394a-128">Cartelle di microservizi nella soluzione eShopOnContainers in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f394a-128">Microservice folders in eShopOnContainers solution in Visual Studio</span></span>

<span data-ttu-id="f394a-129">Per quanto riguarda il servizio di gestione delle identità, nella progettazione viene omesso dal routing del gateway API in quanto è l'unico aspetto trasversale nel sistema, sebbene con Ocelot sia anche possibile includere questo servizio negli elenchi di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f394a-129">About the Identity service, in the design it's left out of the API Gateway routing because it's the only cross-cutting concern in the system, although with Ocelot it's also possible to include it as part of the rerouting lists.</span></span>

<span data-ttu-id="f394a-130">Tutti questi servizi vengono attualmente implementati come servizi API Web ASP.NET Core, come si può vedere dal codice.</span><span class="sxs-lookup"><span data-stu-id="f394a-130">All those services are currently implemented as ASP.NET Core Web API services, as you can tell from the code.</span></span> <span data-ttu-id="f394a-131">Concentriamoci su uno dei microservizi, ad esempio il codice del microservizio Catalog.</span><span class="sxs-lookup"><span data-stu-id="f394a-131">Let's focus on one of the microservices like the Catalog microservice code.</span></span>

![Screenshot di Esplora soluzioni che mostra il contenuto del progetto Catalog. API.](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

<span data-ttu-id="f394a-133">**Figura 6-30**.</span><span class="sxs-lookup"><span data-stu-id="f394a-133">**Figure 6-30**.</span></span> <span data-ttu-id="f394a-134">Microservizio API Web di esempio (microservizio Catalog)</span><span class="sxs-lookup"><span data-stu-id="f394a-134">Sample Web API microservice (Catalog microservice)</span></span>

<span data-ttu-id="f394a-135">Il microservizio Catalog è un tipico progetto API Web ASP.NET Core con diversi controller e metodi, come si può vedere nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f394a-135">You can see that the Catalog microservice is a typical ASP.NET Core Web API project with several controllers and methods like in the following code.</span></span>

```csharp
[HttpGet]
[Route("items/{id:int}")]
[ProducesResponseType((int)HttpStatusCode.BadRequest)]
[ProducesResponseType((int)HttpStatusCode.NotFound)]
[ProducesResponseType(typeof(CatalogItem),(int)HttpStatusCode.OK)]
public async Task<IActionResult> GetItemById(int id)
{
    if (id <= 0)
    {
        return BadRequest();
    }
    var item = await _catalogContext.CatalogItems.
                                          SingleOrDefaultAsync(ci => ci.Id == id);
    //…

    if (item != null)
    {
        return Ok(item);
    }
    return NotFound();
}
```

<span data-ttu-id="f394a-136">La richiesta HTTP eseguirà quel genere di codice C# durante l'accesso al database del microservizio e a qualsiasi altra azione necessaria.</span><span class="sxs-lookup"><span data-stu-id="f394a-136">The HTTP request will end up running that kind of C# code accessing the microservice database and any additional required action.</span></span>

<span data-ttu-id="f394a-137">Per quanto riguarda l'URL del microservizio, quando i contenitori vengono distribuiti nel PC di sviluppo locale (host Docker locale), ogni contenitore del microservizio ha sempre una porta interna, in genere la porta 80, specificata nella relativa dockerfile, come nel dockerfile seguente:</span><span class="sxs-lookup"><span data-stu-id="f394a-137">Regarding the microservice URL, when the containers are deployed in your local development PC (local Docker host), each microservice's container has always an internal port (usually port 80) specified in its dockerfile, as in the following dockerfile:</span></span>

```Dockerfile
FROM microsoft/aspnetcore:2.0.5 AS base
WORKDIR /app
EXPOSE 80
```

<span data-ttu-id="f394a-138">La porta 80 indicata nel codice è interna all'host Docker, quindi non può essere raggiunta dalle app client.</span><span class="sxs-lookup"><span data-stu-id="f394a-138">The port 80 shown in the code is internal within the Docker host, so it can't be reached by client apps.</span></span>

<span data-ttu-id="f394a-139">Le app client possono accedere solo alle porte esterne (se presenti) pubblicate durante la distribuzione con `docker-compose`.</span><span class="sxs-lookup"><span data-stu-id="f394a-139">Client apps can access only the external ports (if any) published when deploying with `docker-compose`.</span></span>

<span data-ttu-id="f394a-140">È consigliabile non pubblicare queste porte esterne durante la distribuzione in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f394a-140">Those external ports shouldn't be published when deploying to a production environment.</span></span> <span data-ttu-id="f394a-141">È proprio questo il motivo per cui si usa il gateway API, per evitare la comunicazione diretta tra le app client e i microservizi.</span><span class="sxs-lookup"><span data-stu-id="f394a-141">This is precisely why you want to use the API Gateway, to avoid the direct communication between the client apps and the microservices.</span></span>

<span data-ttu-id="f394a-142">Quando si sviluppa, invece, è utile accedere direttamente al microservizio/contenitore ed eseguirlo tramite Swagger.</span><span class="sxs-lookup"><span data-stu-id="f394a-142">However, when developing, you want to access the microservice/container directly and run it through Swagger.</span></span> <span data-ttu-id="f394a-143">Per questo motivo, in eShopOnContainers, le porte esterne vengono comunque specificate anche quando non verranno usate dal gateway API o dalle app client.</span><span class="sxs-lookup"><span data-stu-id="f394a-143">That's why in eShopOnContainers, the external ports are still specified even when they won't be used by the API Gateway or the client apps.</span></span>

<span data-ttu-id="f394a-144">Di seguito è riportato un esempio del file di `docker-compose.override.yml` per il microservizio Catalog:</span><span class="sxs-lookup"><span data-stu-id="f394a-144">Here's an example of the `docker-compose.override.yml` file for the Catalog microservice:</span></span>

```yml
catalog.api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

<span data-ttu-id="f394a-145">Si può vedere che nella configurazione di docker-compose.override.yml la porta interna per il contenitore Catalog è la porta 80, ma la porta per l'accesso esterno è la numero 5101.</span><span class="sxs-lookup"><span data-stu-id="f394a-145">You can see how in the docker-compose.override.yml configuration the internal port for the Catalog container is port 80, but the port for external access is 5101.</span></span> <span data-ttu-id="f394a-146">Questa porta, tuttavia, non deve essere usata dall'applicazione quando si usa un gateway API, ma solo per eseguire il debug, eseguire e testare solo il microservizio Catalog.</span><span class="sxs-lookup"><span data-stu-id="f394a-146">But this port shouldn't be used by the application when using an API Gateway, only to debug, run, and test just the Catalog microservice.</span></span>

<span data-ttu-id="f394a-147">In genere, non verrà distribuita con Docker-compose in un ambiente di produzione perché l'ambiente di distribuzione di produzione appropriato per i microservizi è un agente di orchestrazione come Kubernetes o Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="f394a-147">Normally, you won't be deploying with docker-compose into a production environment because the right production deployment environment for microservices is an orchestrator like Kubernetes or Service Fabric.</span></span> <span data-ttu-id="f394a-148">Quando si esegue la distribuzione in questi ambienti si usano file di configurazione diversi, in cui non verrà pubblicata direttamente alcuna porta esterna per i microservizi, ma si userà sempre il proxy inverso dal gateway API.</span><span class="sxs-lookup"><span data-stu-id="f394a-148">When deploying to those environments you use different configuration files where you won't publish directly any external port for the microservices but, you'll always use the reverse proxy from the API Gateway.</span></span>

<span data-ttu-id="f394a-149">Eseguire il microservizio Catalog nell'host Docker locale.</span><span class="sxs-lookup"><span data-stu-id="f394a-149">Run the catalog microservice in your local Docker host.</span></span> <span data-ttu-id="f394a-150">Eseguire la soluzione eShopOnContainers completa da Visual Studio (esegue tutti i servizi nei file Docker-compose) o avviare il microservizio Catalog con il comando Docker-compose seguente in CMD o PowerShell posizionato nella cartella in cui si trovano i `docker-compose.yml` e `docker-compose.override.yml`.</span><span class="sxs-lookup"><span data-stu-id="f394a-150">Either run the full eShopOnContainers solution from Visual Studio (it runs all the services in the docker-compose files), or start the Catalog microservice with the following docker-compose command in CMD or PowerShell positioned at the folder where the `docker-compose.yml` and `docker-compose.override.yml` are placed.</span></span>

```console
docker-compose run --service-ports catalog.api
```

<span data-ttu-id="f394a-151">Questo comando esegue solo il contenitore del servizio catalog.api, oltre alle dipendenze specificate in docker-compose.yml,</span><span class="sxs-lookup"><span data-stu-id="f394a-151">This command only runs the catalog.api service container plus dependencies that are specified in the docker-compose.yml.</span></span> <span data-ttu-id="f394a-152">in questo caso, i contenitori SQL Server e RabbitMQ.</span><span class="sxs-lookup"><span data-stu-id="f394a-152">In this case, the SQL Server container and RabbitMQ container.</span></span>

<span data-ttu-id="f394a-153">Quindi, è possibile accedere direttamente al microservizio Catalog e visualizzare i relativi metodi tramite l'interfaccia utente di spavalderia che accede direttamente tramite la porta "External", in questo caso `http://localhost:5101/swagger`:</span><span class="sxs-lookup"><span data-stu-id="f394a-153">Then, you can directly access the Catalog microservice and see its methods through the Swagger UI accessing directly through that "external" port, in this case `http://localhost:5101/swagger`:</span></span>

![Screenshot dell'interfaccia utente di spavalderia che mostra l'API REST Catalog. API.](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

<span data-ttu-id="f394a-155">**Figura 6-31**.</span><span class="sxs-lookup"><span data-stu-id="f394a-155">**Figure 6-31**.</span></span> <span data-ttu-id="f394a-156">Esecuzione dei test sul microservizio Catalog con la relativa interfaccia utente di Swagger</span><span class="sxs-lookup"><span data-stu-id="f394a-156">Testing the Catalog microservice with its Swagger UI</span></span>

<span data-ttu-id="f394a-157">Si può a questo punto impostare un punto di interruzione nel codice C# in Visual Studio, eseguire i test sul microservizio con i metodi esposti nell'interfaccia utente di Swagger e infine pulire tutto usando il comando `docker-compose down`.</span><span class="sxs-lookup"><span data-stu-id="f394a-157">At this point, you could set a breakpoint in C# code in Visual Studio, test the microservice with the methods exposed in Swagger UI, and finally clean-up everything with the `docker-compose down` command.</span></span>

<span data-ttu-id="f394a-158">La comunicazione ad accesso diretto al microservizio, in questo caso attraverso la porta esterna 5101, è tuttavia esattamente ciò che si vuole evitare nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-158">However, direct-access communication to the microservice, in this case through the external port 5101, is precisely what you want to avoid in your application.</span></span> <span data-ttu-id="f394a-159">Si può ovviare impostando il livello aggiuntivo di riferimento indiretto del gateway API (in questo caso, Ocelot).</span><span class="sxs-lookup"><span data-stu-id="f394a-159">And you can avoid that by setting the additional level of indirection of the API Gateway (Ocelot, in this case).</span></span> <span data-ttu-id="f394a-160">In questo modo, l'app client non accederà direttamente al microservizio.</span><span class="sxs-lookup"><span data-stu-id="f394a-160">That way, the client app won't directly access the microservice.</span></span>

## <a name="implementing-your-api-gateways-with-ocelot"></a><span data-ttu-id="f394a-161">Implementazione di gateway API con Ocelot</span><span class="sxs-lookup"><span data-stu-id="f394a-161">Implementing your API Gateways with Ocelot</span></span>

<span data-ttu-id="f394a-162">Ocelot è essenzialmente un set di middleware che è possibile applicare in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="f394a-162">Ocelot is basically a set of middlewares that you can apply in a specific order.</span></span>

<span data-ttu-id="f394a-163">Ocelot è progettato per funzionare solo con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f394a-163">Ocelot is designed to work with ASP.NET Core only.</span></span> <span data-ttu-id="f394a-164">È destinato a netstandard2.0, quindi può essere usato ovunque sia supportato .NET Standard 2.0, inclusi i runtime di .NET Core 2.0 e di .NET Framework 4.6.1 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f394a-164">It targets netstandard2.0 so it can be used anywhere .NET Standard 2.0 is supported, including .NET Core 2.0 runtime and .NET Framework 4.6.1 runtime and up.</span></span>

<span data-ttu-id="f394a-165">È possibile installare Ocelot e le relative dipendenze nel progetto ASP.NET Core con il [pacchetto NuGet di Ocelot](https://www.nuget.org/packages/Ocelot/) da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f394a-165">You install Ocelot and its dependencies in your ASP.NET Core project with [Ocelot's NuGet package](https://www.nuget.org/packages/Ocelot/), from Visual Studio.</span></span>

```powershell
Install-Package Ocelot
```

<span data-ttu-id="f394a-166">In eShopOnContainers, l'implementazione del gateway API è un semplice progetto ASP.NET Core provider e i middleware di Ocelot gestiscono tutte le funzionalità del gateway API, come illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="f394a-166">In eShopOnContainers, its API Gateway implementation is a simple ASP.NET Core WebHost project, and Ocelot's middlewares handle all the API Gateway features, as shown in the following image:</span></span>

![Screenshot del Esplora soluzioni che mostra il progetto del gateway dell'API Ocelot.](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

<span data-ttu-id="f394a-168">**Figura 6-32**.</span><span class="sxs-lookup"><span data-stu-id="f394a-168">**Figure 6-32**.</span></span> <span data-ttu-id="f394a-169">Progetto di base OcelotApiGw in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f394a-169">The OcelotApiGw base project in eShopOnContainers</span></span>

<span data-ttu-id="f394a-170">Il progetto WebHost ASP.NET Core viene praticamente creato con due semplici file: `Program.cs` e `Startup.cs`.</span><span class="sxs-lookup"><span data-stu-id="f394a-170">This ASP.NET Core WebHost project is basically built with two simple files:  `Program.cs` and `Startup.cs`.</span></span>

<span data-ttu-id="f394a-171">Il file Program.cs serve solo a creare e configurare il tipico BuildWebHost ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f394a-171">The Program.cs just needs to create and configure the typical ASP.NET Core BuildWebHost.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Program
    {
        public static void Main(string[] args)
        {
            BuildWebHost(args).Run();
        }

        public static IWebHost BuildWebHost(string[] args)
        {
            var builder = WebHost.CreateDefaultBuilder(args);

            builder.ConfigureServices(s => s.AddSingleton(builder))
                    .ConfigureAppConfiguration(
                          ic => ic.AddJsonFile(Path.Combine("configuration",
                                                            "configuration.json")))
                    .UseStartup<Startup>();
            var host = builder.Build();
            return host;
        }
    }
}
```

<span data-ttu-id="f394a-172">Il punto importante qui per Ocelot è il file `configuration.json` che è necessario indicare al compilatore tramite il metodo `AddJsonFile()`.</span><span class="sxs-lookup"><span data-stu-id="f394a-172">The important point here for Ocelot is the `configuration.json` file that you must provide to the builder through the `AddJsonFile()` method.</span></span> <span data-ttu-id="f394a-173">Nel file `configuration.json` si specificano tutti i reindirizzamenti del gateway API, vale a dire gli endpoint esterni con porte specifiche e gli endpoint interni correlati, che in genere usano porte diverse.</span><span class="sxs-lookup"><span data-stu-id="f394a-173">That `configuration.json` is where you specify all the API Gateway ReRoutes, meaning the external endpoints with specific ports and the correlated internal endpoints, usually using different ports.</span></span>

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

<span data-ttu-id="f394a-174">La configurazione prevede due sezioni.</span><span class="sxs-lookup"><span data-stu-id="f394a-174">There are two sections to the configuration.</span></span> <span data-ttu-id="f394a-175">Una matrice di Reroute e un GlobalConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f394a-175">An array of ReRoutes and a GlobalConfiguration.</span></span> <span data-ttu-id="f394a-176">I reindirizzamenti sono gli oggetti che indicano a Ocelot come trattare una richiesta upstream.</span><span class="sxs-lookup"><span data-stu-id="f394a-176">The ReRoutes are the objects that tell Ocelot how to treat an upstream request.</span></span> <span data-ttu-id="f394a-177">La configurazione globale consente le sostituzioni delle impostazioni specifiche di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f394a-177">The Global configuration allows overrides of ReRoute specific settings.</span></span> <span data-ttu-id="f394a-178">È utile se non si vuole gestire un numero elevato di impostazioni specifiche di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f394a-178">It's useful if you don't want to manage lots of ReRoute specific settings.</span></span>

<span data-ttu-id="f394a-179">Ecco un esempio semplificato di [Reindirizzamento del file di configurazione](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) da uno dei gateway API da eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f394a-179">Here's a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.</span></span>

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/c/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ]
    },
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }

  ],
    "GlobalConfiguration": {
      "RequestIdKey": "OcRequestId",
      "AdministrationPath": "/administration"
    }
  }
```

<span data-ttu-id="f394a-180">La funzionalità principale di un gateway API Ocelot consiste nel ricevere le richieste HTTP in ingresso e di inoltrarle a un servizio downstream, come un'altra richiesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="f394a-180">The main functionality of an Ocelot API Gateway is to take incoming HTTP requests and forward them on to a downstream service, currently as another HTTP request.</span></span> <span data-ttu-id="f394a-181">Ocelot descrive il routing di una richiesta a un'altra come reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f394a-181">Ocelot's describes the routing of one request to another as a ReRoute.</span></span>

<span data-ttu-id="f394a-182">Ad esempio, concentriamoci su uno dei reindirizzamenti nel file Configuration. JSON riportato sopra, la configurazione per il microservizio basket.</span><span class="sxs-lookup"><span data-stu-id="f394a-182">For instance, let's focus on one of the ReRoutes in the configuration.json from above, the configuration for the Basket microservice.</span></span>

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [ "POST", "PUT", "GET" ],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
}
```

<span data-ttu-id="f394a-183">Gli oggetti DownstreamPathTemplate, Scheme e DownstreamHostAndPorts costituiscono l'URL del microservizio a cui sarà inoltrata questa richiesta.</span><span class="sxs-lookup"><span data-stu-id="f394a-183">The DownstreamPathTemplate, Scheme, and DownstreamHostAndPorts make the internal microservice URL that this request will be forwarded to.</span></span>

<span data-ttu-id="f394a-184">La porta è la porta interna usata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="f394a-184">The port is the internal port used by the service.</span></span> <span data-ttu-id="f394a-185">Quando si usano i contenitori, è la porta specificata nel relativo dockerfile.</span><span class="sxs-lookup"><span data-stu-id="f394a-185">When using containers, the port specified at its dockerfile.</span></span>

<span data-ttu-id="f394a-186">L'oggetto `Host` è un nome di servizio che dipende dalla risoluzione dei nomi dei servizi in uso.</span><span class="sxs-lookup"><span data-stu-id="f394a-186">The `Host` is a service name that depends on the service name resolution you are using.</span></span> <span data-ttu-id="f394a-187">Quando si usa docker-compose, i nomi dei servizi vengono specificati dall'host Docker, che usa i nomi di servizio specificati nei file docker-compose.</span><span class="sxs-lookup"><span data-stu-id="f394a-187">When using docker-compose, the services names are provided by the Docker Host, which is using the service names provided in the docker-compose files.</span></span> <span data-ttu-id="f394a-188">Se si usa un agente di orchestrazione, come Kubernetes o Service Fabric, tale nome deve essere risolto dal DNS o dalla risoluzione dei nomi indicata da ogni agente di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-188">If using an orchestrator like Kubernetes or Service Fabric, that name should be resolved by the DNS or name resolution provided by each orchestrator.</span></span>

<span data-ttu-id="f394a-189">DownstreamHostAndPorts è una matrice che contiene l'host e la porta di tutti i servizi downstream a cui si desidera inoltrare le richieste.</span><span class="sxs-lookup"><span data-stu-id="f394a-189">DownstreamHostAndPorts is an array that contains the host and port of any downstream services that you wish to forward requests to.</span></span> <span data-ttu-id="f394a-190">Questo oggetto contiene di solito una sola voce ma talvolta si può voler bilanciare le richieste ai servizi downstream e Ocelot consente di aggiungere più voci e selezionare un servizio di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="f394a-190">Usually this will just contain one entry but sometimes you might want to load balance requests to your downstream services and Ocelot lets you add more than one entry and then select a load balancer.</span></span> <span data-ttu-id="f394a-191">Se tuttavia si usano Azure e un qualsiasi agente di orchestrazione, è probabilmente meglio bilanciare il carico con l'infrastruttura del cloud e dell'agente di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-191">But if using Azure and any orchestrator it is probably a better idea to load balance with the cloud and orchestrator infrastructure.</span></span>

<span data-ttu-id="f394a-192">L'oggetto UpstreamPathTemplate è l'URL che Ocelot userà per identificare quale oggetto DownstreamPathTemplate usare per una determinata richiesta del client.</span><span class="sxs-lookup"><span data-stu-id="f394a-192">The UpstreamPathTemplate is the URL that Ocelot will use to identify which DownstreamPathTemplate to use for a given request from the client.</span></span> <span data-ttu-id="f394a-193">Viene infine usato l'oggetto UpstreamHttpMethod per consentire a Ocelot di distinguere tra le varie richieste (GET, POST, PUT) allo stesso URL.</span><span class="sxs-lookup"><span data-stu-id="f394a-193">Finally, the UpstreamHttpMethod is used so Ocelot can distinguish between different requests (GET, POST, PUT) to the same URL.</span></span>

<span data-ttu-id="f394a-194">È possibile a questo punto che si abbia un unico gateway API Ocelot (ASP.NET Core WebHost) che usa uno o [più file configuration.json uniti](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) oppure è possibile archiviare la [configurazione in un archivio Consul KV](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span><span class="sxs-lookup"><span data-stu-id="f394a-194">At this point, you could have a single Ocelot API Gateway (ASP.NET Core WebHost) using one or [multiple merged configuration.json files](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) or you can also store the [configuration in a Consul KV store](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).</span></span>

<span data-ttu-id="f394a-195">Se tuttavia, come detto nelle sezioni sull'architettura e la progettazione, si intende veramente avere microservizi autonomi, potrebbe essere più opportuno suddividere il singolo gateway API monolitico in più gateway API e/o BFF (back-end per front-end).</span><span class="sxs-lookup"><span data-stu-id="f394a-195">But as introduced in the architecture and design sections, if you really want to have autonomous microservices, it might be better to split that single monolithic API Gateway into multiple API Gateways and/or BFF (Backend for Frontend).</span></span> <span data-ttu-id="f394a-196">A tale scopo, si vedrà come implementare questo approccio con i contenitori docker.</span><span class="sxs-lookup"><span data-stu-id="f394a-196">For that purpose, let's see how to implement that approach with Docker containers.</span></span>

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a><span data-ttu-id="f394a-197">Utilizzo di una singola immagine del contenitore Docker per eseguire più tipi di contenitore gateway API/BFF</span><span class="sxs-lookup"><span data-stu-id="f394a-197">Using a single Docker container image to run multiple different API Gateway / BFF container types</span></span>

<span data-ttu-id="f394a-198">In eShopOnContainers si sta usando una singola immagine del contenitore Docker con il gateway dell'API Ocelot, ma in fase di esecuzione vengono creati diversi servizi/contenitori per ogni tipo di API-gateway/BFF fornendo un file Configuration. JSON diverso, usando un volume Docker per accedere a una cartella del PC diversa per ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="f394a-198">In eShopOnContainers, we're using a single Docker container image with the Ocelot API Gateway but then, at run time, we create different services/containers for each type of API-Gateway/BFF by providing a different configuration.json file, using a docker volume to access a different PC folder for each service.</span></span>

![Diagramma di una singola immagine docker del gateway Ocelot per tutti i gateway API.](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

<span data-ttu-id="f394a-200">**Figura 6-33**.</span><span class="sxs-lookup"><span data-stu-id="f394a-200">**Figure 6-33**.</span></span> <span data-ttu-id="f394a-201">Utilizzo di una singola immagine di Docker di Ocelot in più tipi di gateway API</span><span class="sxs-lookup"><span data-stu-id="f394a-201">Reusing a single Ocelot Docker image across multiple API Gateway types</span></span>

<span data-ttu-id="f394a-202">In eShopOnContainers viene creata l'immagine docker del gateway dell'API Ocelot generica con il progetto denominato ' OcelotApiGw ' e il nome dell'immagine "eShop/OcelotApiGw" specificato nel file Docker-compose. yml.</span><span class="sxs-lookup"><span data-stu-id="f394a-202">In eShopOnContainers, the "Generic Ocelot API Gateway Docker Image" is created with the project named 'OcelotApiGw' and the image name "eshop/ocelotapigw" that is specified in the docker-compose.yml file.</span></span> <span data-ttu-id="f394a-203">Durante la distribuzione in Docker, saranno presenti quattro contenitori API-Gateway creati dalla stessa immagine di Docker, come mostrato nel seguente estratto del file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="f394a-203">Then, when deploying to Docker, there will be four API-Gateway containers created from that same Docker image, as shown in the following extract from the docker-compose.yml file.</span></span>

```yml
  mobileshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  mobilemarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webshoppingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile

  webmarketingapigw:
    image: eshop/ocelotapigw:${TAG:-latest}
    build:
      context: .
      dockerfile: src/ApiGateways/ApiGw-Base/Dockerfile
```

<span data-ttu-id="f394a-204">Inoltre, come si può notare nel file docker-compose.override.yml, l'unica differenza tra questi contenitori API-Gateway è il file di configurazione Ocelot, che è diverso per ogni contenitore di servizi e viene specificato in fase di esecuzione tramite un volume Docker.</span><span class="sxs-lookup"><span data-stu-id="f394a-204">Additionally, as you can see in the following docker-compose.override.yml file, the only difference between those API Gateway containers is the Ocelot configuration file, which is different for each service container and it's specified at runtime through a Docker volume.</span></span>

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity.api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

<span data-ttu-id="f394a-205">A causa del codice precedente e, come illustrato di seguito in Visual Studio Explorer, l'unico file necessario per definire ogni gateway API aziendale/BFF specifico è un file configuration.json, perché i quattro gateway API si basano sulla stessa immagine Docker.</span><span class="sxs-lookup"><span data-stu-id="f394a-205">Because of that previous code, and as shown in the Visual Studio Explorer below, the only file needed to define each specific business/BFF API Gateway is just a configuration.json file, because the four API Gateways are based on the same Docker image.</span></span>

![Screenshot che Mostra tutti i gateway API con i file Configuration. JSON.](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

<span data-ttu-id="f394a-207">**Figura 6-34**.</span><span class="sxs-lookup"><span data-stu-id="f394a-207">**Figure 6-34**.</span></span> <span data-ttu-id="f394a-208">L'unico file necessario per definire ogni gateway API/BFF con Ocelot è un file di configurazione</span><span class="sxs-lookup"><span data-stu-id="f394a-208">The only file needed to define each API Gateway / BFF with Ocelot is a configuration file</span></span>

<span data-ttu-id="f394a-209">Suddividendo il gateway API in più gateway API, i diversi team di sviluppo impegnati su subset diversi di microservizi possono gestire i propri gateway API usando file di configurazione Ocelot indipendenti.</span><span class="sxs-lookup"><span data-stu-id="f394a-209">By splitting the API Gateway into multiple API Gateways, different development teams focusing on different subsets of microservices can manage their own API Gateways by using independent Ocelot configuration files.</span></span> <span data-ttu-id="f394a-210">Possono inoltre usare contemporaneamente la stessa immagine Docker Ocelot.</span><span class="sxs-lookup"><span data-stu-id="f394a-210">Plus, at the same time they can reuse the same Ocelot Docker image.</span></span>

<span data-ttu-id="f394a-211">A questo punto, se si esegue eShopOnContainers con i gateway API (incluso per impostazione predefinita in Visual Studio quando si apre la soluzione eShopOnContainers-ServicesAndWebApps. sln o se si esegue "Docker-compose up"), verranno eseguite le route di esempio seguenti.</span><span class="sxs-lookup"><span data-stu-id="f394a-211">Now, if you run eShopOnContainers with the API Gateways (included by default in VS when opening eShopOnContainers-ServicesAndWebApps.sln solution or if running "docker-compose up"), the following sample routes will be performed.</span></span>

<span data-ttu-id="f394a-212">Quando ad esempio si visita l'URL upstream `http://localhost:5202/api/v1/c/catalog/items/2/` servito dal gateway API webshoppingapigw, si ottiene lo stesso risultato dall'URL downstream interno `http://catalog.api/api/v1/2` all'interno dell'host Docker, come nel browser seguente.</span><span class="sxs-lookup"><span data-stu-id="f394a-212">For instance, when visiting the upstream URL `http://localhost:5202/api/v1/c/catalog/items/2/` served by the webshoppingapigw API Gateway, you get the same result from the internal Downstream URL `http://catalog.api/api/v1/2` within the Docker host, as in the following browser.</span></span>

![Screenshot di un browser che mostra una risposta che passa attraverso il gateway API.](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

<span data-ttu-id="f394a-214">**Figura 6-35**.</span><span class="sxs-lookup"><span data-stu-id="f394a-214">**Figure 6-35**.</span></span> <span data-ttu-id="f394a-215">Accesso a un microservizio tramite un URL specificato dal gateway API</span><span class="sxs-lookup"><span data-stu-id="f394a-215">Accessing a microservice through a URL provided by the API Gateway</span></span>

<span data-ttu-id="f394a-216">Se, per motivi di test o di debug, si vuole accedere direttamente al contenitore Docker Catalog (solo nell'ambiente di sviluppo) senza passare attraverso il gateway API, poiché "catalog.api" è una risoluzione DNS interna all'host Docker (individuazione del servizio gestita da nomi di servizio di docker-compose), l'unico modo disponibile è attraverso la porta esterna pubblicata nel file docker-compose.override.yml, che viene fornita solo per i test di sviluppo, ad esempio `http://localhost:5101/api/v1/Catalog/items/1` nel browser seguente.</span><span class="sxs-lookup"><span data-stu-id="f394a-216">Because of testing or debugging reasons, if you wanted to directly access to the Catalog Docker container (only at the development environment) without passing through the API Gateway, since 'catalog.api' is a DNS resolution internal to the Docker host (service discovery handled by docker-compose service names), the only way to directly access the container is through the external port published in the docker-compose.override.yml, which is provided only for development tests, such as `http://localhost:5101/api/v1/Catalog/items/1` in the following browser.</span></span>

![Screenshot di un browser che mostra una risposta diretta a Catalog. API.](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

<span data-ttu-id="f394a-218">**Figura 6-36**.</span><span class="sxs-lookup"><span data-stu-id="f394a-218">**Figure 6-36**.</span></span> <span data-ttu-id="f394a-219">Accesso diretto a un microservizio per scopi di test</span><span class="sxs-lookup"><span data-stu-id="f394a-219">Direct access to a microservice for testing purposes</span></span>

<span data-ttu-id="f394a-220">Tuttavia, l'applicazione è configurata in modo che acceda a tutti i microservizi tramite i gateway API, non tramite la porta diretta "Shortcuts".</span><span class="sxs-lookup"><span data-stu-id="f394a-220">But the application is configured so it accesses all the microservices through the API Gateways, not though the direct port "shortcuts".</span></span>

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a><span data-ttu-id="f394a-221">Modello di aggregazione del gateway in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f394a-221">The Gateway aggregation pattern in eShopOnContainers</span></span>

<span data-ttu-id="f394a-222">Come illustrato in precedenza, un modo flessibile per implementare l'aggregazione di richieste è con i servizi personalizzati, tramite il codice.</span><span class="sxs-lookup"><span data-stu-id="f394a-222">As introduced previously, a flexible way to implement requests aggregation is with custom services, by code.</span></span> <span data-ttu-id="f394a-223">È possibile implementare l'aggregazione di richieste anche con la [funzione di aggregazione richieste in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation) che tuttavia potrebbe non offrire la flessibilità necessaria.</span><span class="sxs-lookup"><span data-stu-id="f394a-223">You could also implement request aggregation with the [Request Aggregation feature in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation), but it might not be as flexible as you need.</span></span> <span data-ttu-id="f394a-224">Pertanto, il modo selezionato per implementare l'aggregazione in eShopOnContainers è con un servizio API Web esplicito ASP.NET Core per ogni aggregatore.</span><span class="sxs-lookup"><span data-stu-id="f394a-224">Therefore, the selected way to implement aggregation in eShopOnContainers is with an explicit ASP.NET Core Web API service for each aggregator.</span></span>

<span data-ttu-id="f394a-225">In base a questo approccio, il diagramma della composizione del gateway API risulta in realtà un po' più esteso quando si prendono in considerazione i servizi di aggregazione non inclusi nel diagramma dell'architettura globale semplificato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f394a-225">According to that approach, the API Gateway composition diagram is in reality a bit more extended when considering the aggregator services that are not shown in the simplified global architecture diagram shown previously.</span></span>

<span data-ttu-id="f394a-226">Nel diagramma seguente è possibile vedere in che modo i servizi di aggregazione collaborano con i gateway API correlati.</span><span class="sxs-lookup"><span data-stu-id="f394a-226">In the following diagram, you can also see how the aggregator services work with their related API Gateways.</span></span>

![Diagramma dell'architettura eShopOnContainers che mostra i servizi Aggregator.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

<span data-ttu-id="f394a-228">**Figura 6-37**.</span><span class="sxs-lookup"><span data-stu-id="f394a-228">**Figure 6-37**.</span></span> <span data-ttu-id="f394a-229">Architettura di eShopOnContainers con servizi di aggregazione</span><span class="sxs-lookup"><span data-stu-id="f394a-229">eShopOnContainers architecture with aggregator services</span></span>

<span data-ttu-id="f394a-230">Zoom avanti, nell'area di lavoro "acquisti" nell'immagine seguente, è possibile notare che chattiness tra le app client e i microservizi viene ridotto quando si usano i servizi aggregator nei gateway API.</span><span class="sxs-lookup"><span data-stu-id="f394a-230">Zooming in further, on the "Shopping" business area in the following image, you can see that chattiness between the client apps and the microservices is reduced when using the aggregator services in the API Gateways.</span></span>

![Diagramma che mostra l'architettura di eShopOnContainers zoom avanti.](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

<span data-ttu-id="f394a-232">**Figura 6-38**.</span><span class="sxs-lookup"><span data-stu-id="f394a-232">**Figure 6-38**.</span></span> <span data-ttu-id="f394a-233">Visualizzazione in dettaglio dei servizi di aggregazione</span><span class="sxs-lookup"><span data-stu-id="f394a-233">Zoom in vision of the Aggregator services</span></span>

<span data-ttu-id="f394a-234">È possibile notare come, quando il diagramma mostra le possibili richieste provenienti dai gateway API, può diventare complesso.</span><span class="sxs-lookup"><span data-stu-id="f394a-234">You can notice how when the diagram shows the possible requests coming from the API Gateways it can get complex.</span></span> <span data-ttu-id="f394a-235">Si può tuttavia notare come le frecce blu risultino semplificate, dalla prospettiva delle app client, quando si usa il modello di aggregatore riducendo il dialogo e la latenza nella comunicazione, finendo con il migliorare in modo significativo l'esperienza utente specialmente per le app remote (app SPA e per dispositivi mobili).</span><span class="sxs-lookup"><span data-stu-id="f394a-235">Although you can see how the arrows in blue would be simplified, from a client apps perspective, when using the aggregator pattern by reducing chattiness and latency in the communication, ultimately significantly improving the user experience for the remote apps (mobile and SPA apps), especially.</span></span>

<span data-ttu-id="f394a-236">Nel caso dell'area di lavoro "marketing" e dei microservizi, si tratta di un caso d'uso semplice, quindi non è necessario usare gli aggregatori, ma potrebbe anche essere possibile, se necessario.</span><span class="sxs-lookup"><span data-stu-id="f394a-236">In the case of the "Marketing" business area and microservices, it is a simple use case so there was no need to use aggregators, but it could also be possible, if needed.</span></span>

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a><span data-ttu-id="f394a-237">Autenticazione e autorizzazione nei gateway API Ocelot</span><span class="sxs-lookup"><span data-stu-id="f394a-237">Authentication and authorization in Ocelot API Gateways</span></span>

<span data-ttu-id="f394a-238">In un gateway API Ocelot è possibile inserire un servizio di autenticazione, ad esempio un servizio API Web ASP.NET Core che usa [IdentityServer](https://identityserver.io/) per generare il token di autorizzazione, all'interno o all'esterno del gateway API.</span><span class="sxs-lookup"><span data-stu-id="f394a-238">In an Ocelot API Gateway you can sit the authentication service, such as an ASP.NET Core Web API service using [IdentityServer](https://identityserver.io/) providing the auth token, either out or inside the API Gateway.</span></span>

<span data-ttu-id="f394a-239">Poiché eShopOnContainers usa più gateway API con limiti basati su aree di business e BFF, il servizio di gestione delle identità/autenticazione viene lasciato al di fuori dei gateway API, come evidenziato in giallo nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="f394a-239">Since eShopOnContainers is using multiple API Gateways with boundaries based on BFF and business areas, the Identity/Auth service is left out of the API Gateways, as highlighted in yellow in the following diagram.</span></span>

![Diagramma che mostra il microservizio di identità sotto il gateway API.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

<span data-ttu-id="f394a-241">**Figura 6-39**.</span><span class="sxs-lookup"><span data-stu-id="f394a-241">**Figure 6-39**.</span></span> <span data-ttu-id="f394a-242">Posizione del servizio di gestione delle identità in eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f394a-242">Position of the Identity service in eShopOnContainers</span></span>

<span data-ttu-id="f394a-243">Ocelot supporta tuttavia anche il posizionamento del microservizio di gestione delle identità/autenticazione all'interno del limite del gateway API, come illustrato in questo altro diagramma.</span><span class="sxs-lookup"><span data-stu-id="f394a-243">However, Ocelot also supports sitting the Identity/Auth microservice within the API Gateway boundary, as in this other diagram.</span></span>

![Diagramma che illustra l'autenticazione in un gateway API Ocelot.](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

<span data-ttu-id="f394a-245">**Figura 6-40**.</span><span class="sxs-lookup"><span data-stu-id="f394a-245">**Figure 6-40**.</span></span> <span data-ttu-id="f394a-246">Autenticazione in Ocelot</span><span class="sxs-lookup"><span data-stu-id="f394a-246">Authentication in Ocelot</span></span>

<span data-ttu-id="f394a-247">Come illustrato nel diagramma precedente, quando il microservizio di identità è sotto il gateway API (AG): 1) il gruppo di disponibilità richiede un token di autenticazione dal microservizio di identità, 2) il microservizio Identity restituisce il token alle richieste AG, 3-4) dai microservizi usando il token di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-247">As the previous diagram shows, when the Identity microservice is beneath the API gateway (AG): 1) AG requests an auth token from identity microservice, 2) The identity microservice returns token to AG, 3-4) AG requests from microservices using the auth token.</span></span> <span data-ttu-id="f394a-248">Poiché l'applicazione eShopOnContainers ha suddiviso il gateway API in più gateway API di BFF (back-end per front-end) e aree di business, un'altra opzione sarebbe stata quella di creare un gateway API aggiuntivo per gli aspetti trasversali.</span><span class="sxs-lookup"><span data-stu-id="f394a-248">Because eShopOnContainers application has split the API Gateway into multiple BFF (Backend for Frontend) and business areas API Gateways, another option would had been to create an additional API Gateway for cross-cutting concerns.</span></span> <span data-ttu-id="f394a-249">Tale scelta sarebbe lecita in un'architettura basata su microservizi più complessa con più microservizi con aspetti trasversali.</span><span class="sxs-lookup"><span data-stu-id="f394a-249">That choice would be fair in a more complex microservice based architecture with multiple cross-cutting concerns microservices.</span></span> <span data-ttu-id="f394a-250">Poiché si tratta solo di un problema trasversale in eShopOnContainers, si è deciso di gestire solo il servizio di sicurezza dall'area di autenticazione del gateway API, per semplicità.</span><span class="sxs-lookup"><span data-stu-id="f394a-250">Since there's only one cross-cutting concern in eShopOnContainers, it was decided to just handle the security service out of the API Gateway realm, for simplicity's sake.</span></span>

<span data-ttu-id="f394a-251">Se l'app è protetta a livello di gateway API, in ogni caso il modulo di autenticazione del gateway API Ocelot viene visitato per primo quando si tenta di usare un qualsiasi microservizio protetto.</span><span class="sxs-lookup"><span data-stu-id="f394a-251">In any case, if the app is secured at the API Gateway level, the authentication module of the Ocelot API Gateway is visited at first when trying to use any secured microservice.</span></span> <span data-ttu-id="f394a-252">Che reindirizza la richiesta HTTP per visitare il microservizio di identità o autenticazione per ottenere il token di accesso in modo che sia possibile visitare i servizi protetti con la access_token.</span><span class="sxs-lookup"><span data-stu-id="f394a-252">That redirects the HTTP request to visit the Identity or auth microservice to get the access token so you can visit the protected services with the access_token.</span></span>

<span data-ttu-id="f394a-253">Per proteggere con autenticazione qualsiasi servizio a livello di gateway API, occorre impostare AuthenticationProviderKey nelle relative impostazioni nel file configuration.json.</span><span class="sxs-lookup"><span data-stu-id="f394a-253">The way you secure with authentication any service at the API Gateway level is by setting the AuthenticationProviderKey in its related settings at the configuration.json.</span></span>

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket.api",
          "Port": 80
        }
      ],
      "UpstreamPathTemplate": "/api/{version}/b/{everything}",
      "UpstreamHttpMethod": [],
      "AuthenticationOptions": {
        "AuthenticationProviderKey": "IdentityApiKey",
        "AllowedScopes": []
      }
    }
```

<span data-ttu-id="f394a-254">Quando si esegue Ocelot, viene esaminato il reindirizzamento AuthenticationOptions. AuthenticationProviderKey e viene verificato che sia presente un provider di autenticazione registrato con la chiave specificata.</span><span class="sxs-lookup"><span data-stu-id="f394a-254">When Ocelot runs, it will look at the ReRoutes AuthenticationOptions.AuthenticationProviderKey and check that there is an Authentication Provider registered with the given key.</span></span> <span data-ttu-id="f394a-255">In caso negativo, Ocelot non viene avviato.</span><span class="sxs-lookup"><span data-stu-id="f394a-255">If there isn't, then Ocelot will not start up.</span></span> <span data-ttu-id="f394a-256">In caso affermativo, invece, il reindirizzamento userà tale provider durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f394a-256">If there is, then the ReRoute will use that provider when it executes.</span></span>

<span data-ttu-id="f394a-257">Poiché il WebHost Ocelot è configurato con `authenticationProviderKey = "IdentityApiKey"`, sarà necessaria l'autenticazione ogni volta che il servizio riceverà richieste senza token di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-257">Because the Ocelot WebHost is configured with the `authenticationProviderKey = "IdentityApiKey"`, that will require authentication whenever that service has any requests without any auth token.</span></span>

```csharp
namespace OcelotApiGw
{
    public class Startup
    {
        private readonly IConfiguration _cfg;

        public Startup(IConfiguration configuration) => _cfg = configuration;

        public void ConfigureServices(IServiceCollection services)
        {
            var identityUrl = _cfg.GetValue<string>("IdentityUrl");
            var authenticationProviderKey = "IdentityApiKey";
                         //…
            services.AddAuthentication()
                .AddJwtBearer(authenticationProviderKey, x =>
                {
                    x.Authority = identityUrl;
                    x.RequireHttpsMetadata = false;
                    x.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters()
                    {
                        ValidAudiences = new[] { "orders", "basket", "locations", "marketing", "mobileshoppingagg", "webshoppingagg" }
                    };
                });
            //...
        }
    }
}
```

<span data-ttu-id="f394a-258">È quindi necessario impostare l'autorizzazione con l'attributo [Authorize] in qualsiasi risorsa a cui si deve accedere, ad esempio i microservizi. Un esempio è il seguente controller del microservizio Basket.</span><span class="sxs-lookup"><span data-stu-id="f394a-258">Then, you also need to set authorization with the [Authorize] attribute on any resource to be accessed like the microservices, such as in the following Basket microservice controller.</span></span>

```csharp
namespace Microsoft.eShopOnContainers.Services.Basket.API.Controllers
{
    [Route("api/v1/[controller]")]
    [Authorize]
    public class BasketController : Controller
    {
      //...
    }
}
```

<span data-ttu-id="f394a-259">ValidAudiences, ad esempio "basket", sono correlati con i destinatari definiti in ogni microservizio con `AddJwtBearer()` al ConfigureServices () della classe di avvio, ad esempio nel codice riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f394a-259">The ValidAudiences such as "basket" are correlated with the audience defined in each microservice with `AddJwtBearer()` at the ConfigureServices() of the Startup class, such as in the code below.</span></span>

```csharp
// prevent from mapping "sub" claim to nameidentifier.
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();

var identityUrl = Configuration.GetValue<string>("IdentityUrl");

services.AddAuthentication(options =>
{
    options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
    options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

}).AddJwtBearer(options =>
{
    options.Authority = identityUrl;
    options.RequireHttpsMetadata = false;
    options.Audience = "basket";
});
```

<span data-ttu-id="f394a-260">Se si prova ad accedere a un microservizio protetto, ad esempio il microservizio basket con un URL di reindirizzamento basato sul gateway API, ad esempio `http://localhost:5202/api/v1/b/basket/1`, si otterrà un 401 non autorizzato, a meno che non si fornisca un token valido.</span><span class="sxs-lookup"><span data-stu-id="f394a-260">If you try to access any secured microservice, like the Basket microservice with a ReRoute URL based on the API Gateway like `http://localhost:5202/api/v1/b/basket/1`, then you'll get a 401 Unauthorized unless you provide a valid token.</span></span> <span data-ttu-id="f394a-261">D'altra parte, se viene autenticato un URL di reinstradamento, Ocelot richiama qualsiasi schema downstream associato (l'URL del microservizio interno).</span><span class="sxs-lookup"><span data-stu-id="f394a-261">On the other hand, if a ReRoute URL is authenticated, Ocelot will invoke whatever downstream scheme is associated with it (the internal microservice URL).</span></span>

<span data-ttu-id="f394a-262">**Autorizzazione al livello di reindirizzamento di Ocelot.**</span><span class="sxs-lookup"><span data-stu-id="f394a-262">**Authorization at Ocelot's ReRoutes tier.**</span></span>  <span data-ttu-id="f394a-263">Ocelot supporta l'autorizzazione basata su attestazioni valutata dopo l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f394a-263">Ocelot supports claims-based authorization evaluated after the authentication.</span></span> <span data-ttu-id="f394a-264">L'autorizzazione viene impostata a livello di route aggiungendo le righe seguenti alla configurazione di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f394a-264">You set the authorization at a route level by adding the following lines to the ReRoute configuration.</span></span>

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

<span data-ttu-id="f394a-265">In questo esempio, quando viene chiamato il middleware di autorizzazione, Ocelot cerca se l'utente dispone del tipo di attestazione "UserType" nel token e se il valore di tale attestazione è "employee".</span><span class="sxs-lookup"><span data-stu-id="f394a-265">In that example, when the authorization middleware is called, Ocelot will find if the user has the claim type 'UserType' in the token and if the value of that claim is 'employee'.</span></span> <span data-ttu-id="f394a-266">In caso contrario, l'utente non sarà autorizzato e la risposta sarà 403 non consentito.</span><span class="sxs-lookup"><span data-stu-id="f394a-266">If it isn't, then the user will not be authorized and the response will be 403 forbidden.</span></span>

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a><span data-ttu-id="f394a-267">Utilizzo dell'oggetto Ingress di Kubernetes insieme ai gateway API Ocelot</span><span class="sxs-lookup"><span data-stu-id="f394a-267">Using Kubernetes Ingress plus Ocelot API Gateways</span></span>

<span data-ttu-id="f394a-268">Quando si usa Kubernetes (come in un cluster del servizio Azure Kubernetes), in genere si uniscono tutte le richieste HTTP attraverso il [livello di oggetto Ingress di Kubernetes](https://kubernetes.io/docs/concepts/services-networking/ingress/) basato su *Nginx*.</span><span class="sxs-lookup"><span data-stu-id="f394a-268">When using Kubernetes (like in an Azure Kubernetes Service cluster), you usually unify all the HTTP requests through the [Kubernetes Ingress tier](https://kubernetes.io/docs/concepts/services-networking/ingress/) based on *Nginx*.</span></span>

<span data-ttu-id="f394a-269">In Kubernetes, se non si usa un approccio in ingresso, i servizi e i pod hanno indirizzi IP instradabili solo dalla rete cluster.</span><span class="sxs-lookup"><span data-stu-id="f394a-269">In Kubernetes, if you don't use any ingress approach, then your services and pods have IPs only routable by the cluster network.</span></span>

<span data-ttu-id="f394a-270">Se invece si usa un approccio con oggetto Ingress, si avrà un livello intermedio tra Internet e i servizi (inclusi i gateway API), che agisce come proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="f394a-270">But if you use an ingress approach, you'll have a middle tier between the Internet and your services (including your API Gateways), acting as a reverse proxy.</span></span>

<span data-ttu-id="f394a-271">Come definizione, un oggetto Ingress è una raccolta di regole che consentono alle connessioni in ingresso di raggiungere i servizi del cluster.</span><span class="sxs-lookup"><span data-stu-id="f394a-271">As a definition, an Ingress is a collection of rules that allow inbound connections to reach the cluster services.</span></span> <span data-ttu-id="f394a-272">In genere si configura un oggetto Ingress per offrire ai servizi URL raggiungibili esternamente, bilanciare il traffico, consentire la terminazione SSL e altro ancora.</span><span class="sxs-lookup"><span data-stu-id="f394a-272">An ingress is usually configured to provide services externally reachable URLs, load balance traffic, SSL termination and more.</span></span> <span data-ttu-id="f394a-273">Gli utenti richiedono l'ingresso eseguendo il comando POST sulla risorsa Ingress al server API.</span><span class="sxs-lookup"><span data-stu-id="f394a-273">Users request ingress by POSTing the Ingress resource to the API server.</span></span>

<span data-ttu-id="f394a-274">In eShopOnContainers, quando lo sviluppo avviene in locale e si usa solo il computer di sviluppo come host Docker, non si usa alcun oggetto Ingress, ma solo più gateway API.</span><span class="sxs-lookup"><span data-stu-id="f394a-274">In eShopOnContainers, when developing locally and using just your development machine as the Docker host, you are not using any ingress but only the multiple API Gateways.</span></span>

<span data-ttu-id="f394a-275">Tuttavia, quando la destinazione è un ambiente di "produzione" basato su Kubernetes, eShopOnContainers usa un ingresso davanti ai gateway API.</span><span class="sxs-lookup"><span data-stu-id="f394a-275">However, when targeting a "production" environment based on Kubernetes, eShopOnContainers is using an ingress in front of the API gateways.</span></span> <span data-ttu-id="f394a-276">I client, in questo modo, chiamano lo stesso URL di base, ma le richieste vengono instradate a più gateway API o BFF.</span><span class="sxs-lookup"><span data-stu-id="f394a-276">That way, the clients still call the same base URL but the requests are routed to multiple API Gateways or BFF.</span></span>

<span data-ttu-id="f394a-277">I gateway API sono front-end o le facet che escono solo i servizi, ma non le applicazioni Web che in genere non rientrano nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="f394a-277">API Gateways are front-ends or façades surfacing only the services but not the web applications that are usually out of their scope.</span></span> <span data-ttu-id="f394a-278">I gateway API possono inoltre nascondere determinati microservizi interni.</span><span class="sxs-lookup"><span data-stu-id="f394a-278">In addition, the API Gateways might hide certain internal microservices.</span></span>

<span data-ttu-id="f394a-279">L'oggetto Ingress, invece, si limita a reindirizzare le richieste HTTP ma non tenta di nascondere alcun microservizio o app Web.</span><span class="sxs-lookup"><span data-stu-id="f394a-279">The ingress, however, is just redirecting HTTP requests but not trying to hide any microservice or web app.</span></span>

<span data-ttu-id="f394a-280">La presenza di un livello Ingress Nginx in Kubernetes davanti alle applicazioni Web oltre ai diversi gateway API/BFF Ocelot rappresenta l'architettura ideale, come illustrato nel diagramma seguente.</span><span class="sxs-lookup"><span data-stu-id="f394a-280">Having an ingress Nginx tier in Kubernetes in front of the web applications plus the several Ocelot API Gateways / BFF is the ideal architecture, as shown in the following diagram.</span></span>

![Diagramma che Mostra come un livello di ingresso si inserisce nell'ambiente AKS.](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

<span data-ttu-id="f394a-282">**Figura 6-41**.</span><span class="sxs-lookup"><span data-stu-id="f394a-282">**Figure 6-41**.</span></span> <span data-ttu-id="f394a-283">Livello Ingress in eShopOnContainers quando distribuito in Kubernetes</span><span class="sxs-lookup"><span data-stu-id="f394a-283">The ingress tier in eShopOnContainers when deployed into Kubernetes</span></span>

<span data-ttu-id="f394a-284">Un oggetto Ingress di Kubernetes funge da proxy inverso per tutto il traffico diretto all'app, incluse le applicazioni Web che di solito non rientrano nell'ambito del gateway API.</span><span class="sxs-lookup"><span data-stu-id="f394a-284">A Kubernetes Ingress acts as a reverse proxy for all traffic to the app, including the web applications, that are usually out of the Api gateway scope.</span></span> <span data-ttu-id="f394a-285">Quando viene distribuito in Kubernetes, eShopOnContainers espone alcuni servizi o endpoint tramite _Ingress_, fondamentalmente l'elenco seguente di suffissi negli URL:</span><span class="sxs-lookup"><span data-stu-id="f394a-285">When you deploy eShopOnContainers into Kubernetes, it exposes just a few services or endpoints via _ingress_, basically the following list of postfixes on the URLs:</span></span>

- <span data-ttu-id="f394a-286">`/` per l'applicazione Web SPA client</span><span class="sxs-lookup"><span data-stu-id="f394a-286">`/` for the client SPA web application</span></span>
- <span data-ttu-id="f394a-287">`/webmvc` per l'applicazione Web MVC client</span><span class="sxs-lookup"><span data-stu-id="f394a-287">`/webmvc` for the client MVC web application</span></span>
- <span data-ttu-id="f394a-288">`/webstatus` per l'app Web client che mostra lo stato o i controlli di integrità</span><span class="sxs-lookup"><span data-stu-id="f394a-288">`/webstatus` for the client web app showing the status/healthchecks</span></span>
- <span data-ttu-id="f394a-289">`/webshoppingapigw` per i processi aziendali Web di BFF e Shopping</span><span class="sxs-lookup"><span data-stu-id="f394a-289">`/webshoppingapigw` for the web BFF and shopping business processes</span></span>
- <span data-ttu-id="f394a-290">`/webmarketingapigw` per i processi aziendali Web di BFF e Marketing</span><span class="sxs-lookup"><span data-stu-id="f394a-290">`/webmarketingapigw` for the web BFF and marketing business processes</span></span>
- <span data-ttu-id="f394a-291">`/mobileshoppingapigw` per i processi aziendali per dispositivi mobili di BFF e Shopping</span><span class="sxs-lookup"><span data-stu-id="f394a-291">`/mobileshoppingapigw` for the mobile BFF and shopping business processes</span></span>
- <span data-ttu-id="f394a-292">`/mobilemarketingapigw` per i processi aziendali per dispositivi mobili di BFF e Marketing</span><span class="sxs-lookup"><span data-stu-id="f394a-292">`/mobilemarketingapigw` for the mobile BFF and marketing business processes</span></span>

<span data-ttu-id="f394a-293">Quando si esegue la distribuzione in Kubernetes, ogni gateway dell'API Ocelot usa un file "Configuration. JSON" diverso per ogni _Pod_ che esegue i gateway API.</span><span class="sxs-lookup"><span data-stu-id="f394a-293">When deploying to Kubernetes, each Ocelot API Gateway is using a different "configuration.json" file for each _pod_ running the API Gateways.</span></span> <span data-ttu-id="f394a-294">I file "Configuration. JSON" vengono forniti montando (originariamente con lo script Deploy. ps1) un volume creato in base a una _mappa di configurazione_ Kubernetes denominata "Ocelot".</span><span class="sxs-lookup"><span data-stu-id="f394a-294">Those "configuration.json" files are provided by mounting (originally with the deploy.ps1 script) a volume created based on a Kubernetes _config map_ named ‘ocelot'.</span></span> <span data-ttu-id="f394a-295">Ogni contenitore monta il file di configurazione correlato nella cartella del contenitore denominata `/app/configuration`.</span><span class="sxs-lookup"><span data-stu-id="f394a-295">Each container mounts its related configuration file in the container's folder named `/app/configuration`.</span></span>

<span data-ttu-id="f394a-296">Nei file di codice sorgente di eShopOnContainers, i file "Configuration. JSON" originali si trovano nella cartella `k8s/ocelot/`.</span><span class="sxs-lookup"><span data-stu-id="f394a-296">In the source code files of eShopOnContainers, the original "configuration.json" files can be found within the `k8s/ocelot/` folder.</span></span> <span data-ttu-id="f394a-297">È presente un file per ogni BFF/APIGateway.</span><span class="sxs-lookup"><span data-stu-id="f394a-297">There's one file for each BFF/APIGateway.</span></span>

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a><span data-ttu-id="f394a-298">Altre funzionalità trasversali in un gateway API Ocelot</span><span class="sxs-lookup"><span data-stu-id="f394a-298">Additional cross-cutting features in an Ocelot API Gateway</span></span>

<span data-ttu-id="f394a-299">Esistono altre importanti funzionalità da cercare e usare quando si usa un gateway API Ocelot. Queste funzionalità sono descritte nei collegamenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="f394a-299">There are other important features to research and use, when using an Ocelot API Gateway, described in the following links.</span></span>

- <span data-ttu-id="f394a-300">**Individuazione di servizi sul lato client che integra Ocelot con Consul o Eureka** </span><span class="sxs-lookup"><span data-stu-id="f394a-300">**Service discovery in the client side integrating Ocelot with Consul or Eureka** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- <span data-ttu-id="f394a-301">**Memorizzazione nella cache a livello di gateway API** </span><span class="sxs-lookup"><span data-stu-id="f394a-301">**Caching at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- <span data-ttu-id="f394a-302">**Registrazione a livello di gateway API** </span><span class="sxs-lookup"><span data-stu-id="f394a-302">**Logging at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- <span data-ttu-id="f394a-303">**Qualità del servizio (nuovi tentativi e interruttori) a livello di gateway API** </span><span class="sxs-lookup"><span data-stu-id="f394a-303">**Quality of Service (Retries and Circuit breakers) at the API Gateway tier** </span></span>\
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- <span data-ttu-id="f394a-304">**Limite di frequenza** </span><span class="sxs-lookup"><span data-stu-id="f394a-304">**Rate limiting** </span></span>\
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> <span data-ttu-id="f394a-305">[Precedente](background-tasks-with-ihostedservice.md)
> [Successivo](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="f394a-305">[Previous](background-tasks-with-ihostedservice.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
