---
title: Implementazione di gateway API con Ocelot
description: Informazioni su come implementare i gateway API con Ocelot e come usare Ocelot in un ambiente basato su contenitori.
ms.date: 03/02/2020
ms.openlocfilehash: 28b9ca22d232baf3545d71b876cecf72fea05c92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846946"
---
# <a name="implement-api-gateways-with-ocelot"></a>Implementare gateway API con Ocelot

> [!IMPORTANT]
> L'applicazione di microservizio di riferimento [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) utilizza attualmente le funzionalità fornite da [Envoy](https://www.envoyproxy.io/) per implementare il gateway API anziché l'Ocelot a cui si fa riferimento in precedenza. [Ocelot](https://github.com/ThreeMammals/Ocelot)
> Abbiamo fatto questa scelta di progettazione a causa del supporto integrato di Envoy per il protocollo WebSocket, richiesto dalle nuove comunicazioni interservizi gRPC implementate in eShopOnContainers.
> Tuttavia, abbiamo mantenuto questa sezione nella guida in modo da poter considerare Ocelot come un gateway API semplice, capace e leggero adatto per scenari di livello di produzione.

## <a name="architect-and-design-your-api-gateways"></a>Creare l'architettura e progettare i propri gateway API

Il diagramma dell'architettura seguente mostra come sono stati implementati i gateway API con Ocelot in eShopOnContainers.The following architecture diagram shows how API Gateways were implemented with Ocelot in eShopOnContainers.

![Diagramma che mostra l'architettura eShopOnContainers.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture.png)

**Figura 6-28**. Architettura di eShopOnContainers con gateway API

Questo diagramma mostra come l'intera applicazione viene distribuita in un singolo host Docker o PC di sviluppo con "Docker per Windows" o "Docker per Mac". Tuttavia, la distribuzione in qualsiasi agente di orchestrazione sarebbe simile, ma qualsiasi contenitore nel diagramma potrebbe essere scalato orizzontalmente nell'agente di orchestrazione.

Le risorse dell'infrastruttura, inoltre, ad esempio i database, la cache e i broker dei messaggi, devono essere scaricate dall'agente di orchestrazione e distribuite in sistemi a disponibilità elevata per l'infrastruttura, ad esempio Database SQL di Azure, Azure Cosmos DB, Redis di Azure, bus di servizio di Azure o qualsiasi altra soluzione di clustering a disponibilità elevata locale.

Come si può notare anche nel diagramma, la presenza di diversi gateway API consente a più team di sviluppo di essere autonomi (in questo caso le funzionalità Di marketing e Shopping) durante lo sviluppo e la distribuzione dei microservizi più i propri gateway API correlati.

Un unico gateway API monolitico significherebbe un unico punto che i vari team di sviluppo devono aggiornare, con conseguente rischio di duplicazione di tutti i microservizi con una singola parte dell'applicazione.

Analizzando il progetto più a fondo, un gateway API specifico può talvolta essere limitato anche a un singolo microservizio aziendale a seconda dell'architettura scelta. Avere i limiti del gateway API dettati dall'azienda o dal dominio ti aiuterà a ottenere una progettazione migliore.

La granularità a livello di gateway API può essere particolarmente utile per le applicazioni con interfaccia utente composita più avanzate basate su microservizi, perché il concetto di gateway API specifico è analogo a quello di un servizio di composizione dell'interfaccia utente.

Altri dettagli sono illustrati nella sezione precedente [Creazione dell'interfaccia utente composita basata su microservizi](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).

Come riferimento chiave, per molte applicazioni di medie e grandi dimensioni, l'utilizzo di un prodotto gateway API personalizzato rappresenta in genere un buon approccio, ma non come unico aggregatore monolitico o unico gateway API centrale personalizzato, a meno che tale gateway API non consenta più aree di configurazione indipendenti per i diversi team di sviluppo che creano microservizi autonomi.

### <a name="sample-microservicescontainers-to-reroute-through-the-api-gateways"></a>Microservizi/contenitori di esempio per il reindirizzamento tramite i gateway API

Per fare un esempio, eShopOnContainers include circa sei tipi di microservizi interni che devono essere pubblicati attraverso i gateway API, come illustrato nell'immagine seguente.

![Screenshot della cartella Servizi che mostra le relative sottocartelle.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-microservice-folders.png)

**Figura 6-29**. Cartelle di microservizi nella soluzione eShopOnContainers in Visual Studio

Per quanto riguarda il servizio di gestione delle identità, nella progettazione viene omesso dal routing del gateway API in quanto è l'unico aspetto trasversale nel sistema, sebbene con Ocelot sia anche possibile includere questo servizio negli elenchi di reindirizzamento.

Tutti questi servizi vengono attualmente implementati come servizi API Web ASP.NET Core, come si può vedere dal codice. Concentriamoci su uno dei microservizi come il codice del microservizio del catalogo.

![Screenshot di Esplora soluzioni che mostra il contenuto del progetto Catalog.API.](./media/implement-api-gateways-with-ocelot/catalog-api-microservice-folders.png)

**Figura 6-30**. Microservizio API Web di esempio (microservizio Catalog)

Il microservizio Catalog è un tipico progetto API Web ASP.NET Core con diversi controller e metodi, come si può vedere nel codice seguente.

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

La richiesta HTTP eseguirà quel genere di codice C# durante l'accesso al database del microservizio e a qualsiasi altra azione necessaria.

Per quanto riguarda l'URL del microservizio, quando i contenitori vengono distribuiti nel PC di sviluppo locale (host Docker locale), il contenitore di ogni microservizio ha sempre una porta interna (in genere la porta 80) specificata nel relativo dockerfile, come nel file dockerfile seguente:

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1 AS base
WORKDIR /app
EXPOSE 80
```

La porta 80 indicata nel codice è interna all'host Docker, quindi non può essere raggiunta dalle app client.

Le app client possono accedere solo alle porte esterne (se presenti) pubblicate durante la distribuzione con `docker-compose`.

È consigliabile non pubblicare queste porte esterne durante la distribuzione in un ambiente di produzione. È proprio questo il motivo per cui si usa il gateway API, per evitare la comunicazione diretta tra le app client e i microservizi.

Quando si sviluppa, invece, è utile accedere direttamente al microservizio/contenitore ed eseguirlo tramite Swagger. Ecco perché in eShopOnContainers, le porte esterne sono ancora specificate anche quando non verranno utilizzate dal gateway API o dalle app client.

Di seguito è riportato un esempio del `docker-compose.override.yml` file per il microservizio catalogo:Here's an example of the file for the Catalog microservice:

```yml
catalog-api:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:80
    - ConnectionString=YOUR_VALUE
    - ... Other Environment Variables
  ports:
    - "5101:80"   # Important: In a production environment you should remove the external port (5101) kept here for microservice debugging purposes.
                  # The API Gateway redirects and access through the internal port (80).
```

Si può vedere che nella configurazione di docker-compose.override.yml la porta interna per il contenitore Catalog è la porta 80, ma la porta per l'accesso esterno è la numero 5101. Ma questa porta non deve essere utilizzata dall'applicazione quando si usa un gateway API, solo per eseguire il debug, eseguire e testare solo il microservizio del catalogo.

In genere, non si esegue la distribuzione con docker-compose in un ambiente di produzione perché l'ambiente di distribuzione di produzione corretto per i microservizi è un orchestratore come Kubernetes o Service Fabric. Quando si esegue la distribuzione in tali ambienti si usano file di configurazione diversi in cui non si pubblica direttamente alcuna porta esterna per i microservizi, ma si utilizzerà sempre il proxy inverso dal gateway API.

Eseguire il microservizio del catalogo nell'host Docker locale. Eseguire la soluzione eShopOnContainers completa da Visual Studio (esegue tutti i servizi nei file docker-compose) oppure avviare il microservizio del catalogo `docker-compose.yml` con `docker-compose.override.yml` il comando docker-compose seguente in CMD o PowerShell posizionato nella cartella in cui sono posizionati gli oggetti.

```console
docker-compose run --service-ports catalog-api
```

Questo comando esegue solo il contenitore del servizio api catalogo e le dipendenze specificate in docker-compose.yml. in questo caso, i contenitori SQL Server e RabbitMQ.

Quindi, è possibile accedere direttamente al microservizio Catalogo e visualizzarne i metodi tramite l'interfaccia `http://localhost:5101/swagger`utente Swagger che accede direttamente tramite tale porta "esterna", in questo caso:

![Screenshot dell'interfaccia utente di Swagger che mostra l'API REST Catalog.API.](./media/implement-api-gateways-with-ocelot/test-catalog-microservice.png)

**Figura 6-31**. Esecuzione dei test sul microservizio Catalog con la relativa interfaccia utente di Swagger

Si può a questo punto impostare un punto di interruzione nel codice C# in Visual Studio, eseguire i test sul microservizio con i metodi esposti nell'interfaccia utente di Swagger e infine pulire tutto usando il comando `docker-compose down`.

La comunicazione ad accesso diretto al microservizio, in questo caso attraverso la porta esterna 5101, è tuttavia esattamente ciò che si vuole evitare nell'applicazione. Si può ovviare impostando il livello aggiuntivo di riferimento indiretto del gateway API (in questo caso, Ocelot). In questo modo, l'app client non accederà direttamente al microservizio.

## <a name="implementing-your-api-gateways-with-ocelot"></a>Implementazione di gateway API con Ocelot

Ocelot è essenzialmente un set di middleware che è possibile applicare in un ordine specifico.

Ocelot è progettato per funzionare solo con ASP.NET Core. La versione più recente `.NETCoreApp 3.1` del pacchetto è destinata e pertanto non è adatta per le applicazioni .NET Framework.

È possibile installare Ocelot e le relative dipendenze nel progetto ASP.NET Core con il [pacchetto NuGet di Ocelot](https://www.nuget.org/packages/Ocelot/) da Visual Studio.

```powershell
Install-Package Ocelot
```

In eShopOnContainers, l'implementazione del gateway API è un semplice ASP.NET progetto Core WebHost e il middleware di Ocelot gestisce tutte le funzionalità di Gateway API, come illustrato nell'immagine seguente:

![Screenshot di Esplora soluzioni che mostra il progetto gateway API Ocelot.](./media/implement-api-gateways-with-ocelot/ocelotapigw-base-project.png)

**Figura 6-32**. Progetto di base OcelotApiGw in eShopOnContainers

Il progetto WebHost ASP.NET Core viene praticamente creato con due semplici file: `Program.cs` e `Startup.cs`.

Il file Program.cs serve solo a creare e configurare il tipico BuildWebHost ASP.NET Core.

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

Il punto importante qui per Ocelot è il file `configuration.json` che è necessario indicare al compilatore tramite il metodo `AddJsonFile()`. Nel file `configuration.json` si specificano tutti i reindirizzamenti del gateway API, vale a dire gli endpoint esterni con porte specifiche e gli endpoint interni correlati, che in genere usano porte diverse.

```json
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

La configurazione prevede due sezioni. Matrice di ReRoutes e GlobalConfiguration. I reRoutes sono gli oggetti che indicano a Ocelot come trattare una richiesta a monte. La configurazione globale consente l'override delle impostazioni specifiche di ReRoute.The Global configuration allows overrides of ReRoute specific settings. È utile se non si desidera gestire molte impostazioni specifiche di ReRoute.It's useful if you don't want to manage lots of ReRoute specific settings.

Ecco un esempio semplificato di file di configurazione ReRoute da uno dei gateway API da eShopOnContainers.Here's a simplified example of [ReRoute configuration file](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) from one of the API Gateways from eShopOnContainers.

```json
{
  "ReRoutes": [
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "catalog-api",
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
          "Host": "basket-api",
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

La funzionalità principale di un gateway API Ocelot consiste nel ricevere le richieste HTTP in ingresso e di inoltrarle a un servizio downstream, come un'altra richiesta HTTP. Ocelot's descrive il routing di una richiesta a un'altra come ReRoute.

Ad esempio, concentriamoci su uno dei ReRoutes in configuration.json dall'alto, la configurazione per il microservizio Basket.

```json
{
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
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

Gli oggetti DownstreamPathTemplate, Scheme e DownstreamHostAndPorts costituiscono l'URL del microservizio a cui sarà inoltrata questa richiesta.

La porta è la porta interna usata dal servizio. Quando si usano i contenitori, è la porta specificata nel relativo dockerfile.

L'oggetto `Host` è un nome di servizio che dipende dalla risoluzione dei nomi dei servizi in uso. Quando si usa docker-compose, i nomi dei servizi vengono specificati dall'host Docker, che usa i nomi di servizio specificati nei file docker-compose. Se si usa un agente di orchestrazione, come Kubernetes o Service Fabric, tale nome deve essere risolto dal DNS o dalla risoluzione dei nomi indicata da ogni agente di orchestrazione.

DownstreamHostAndPorts è una matrice che contiene l'host e la porta di tutti i servizi downstream a cui si desidera inoltrare le richieste. Questo oggetto contiene di solito una sola voce ma talvolta si può voler bilanciare le richieste ai servizi downstream e Ocelot consente di aggiungere più voci e selezionare un servizio di bilanciamento del carico. Se tuttavia si usano Azure e un qualsiasi agente di orchestrazione, è probabilmente meglio bilanciare il carico con l'infrastruttura del cloud e dell'agente di orchestrazione.

L'oggetto UpstreamPathTemplate è l'URL che Ocelot userà per identificare quale oggetto DownstreamPathTemplate usare per una determinata richiesta del client. Viene infine usato l'oggetto UpstreamHttpMethod per consentire a Ocelot di distinguere tra le varie richieste (GET, POST, PUT) allo stesso URL.

È possibile a questo punto che si abbia un unico gateway API Ocelot (ASP.NET Core WebHost) che usa uno o [più file configuration.json uniti](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) oppure è possibile archiviare la [configurazione in un archivio Consul KV](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul).

Se tuttavia, come detto nelle sezioni sull'architettura e la progettazione, si intende veramente avere microservizi autonomi, potrebbe essere più opportuno suddividere il singolo gateway API monolitico in più gateway API e/o BFF (back-end per front-end). A tale scopo, vediamo come implementare tale approccio con i contenitori Docker.For that purpose, let's see how to implement that approach with Docker containers.

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a>Utilizzo di una singola immagine del contenitore Docker per eseguire più tipi di contenitore gateway API/BFF

In eShopOnContainers, stiamo usando una singola immagine del contenitore Docker con il gateway API Ocelot, ma poi, in fase di esecuzione, creiamo servizi/contenitori diversi per ogni tipo di API-Gateway/BFF fornendo un file configuration.json diverso, usando un volume docker per accedere a una cartella PC diversa per ogni servizio.

![Diagramma di una singola immagine Docker del gateway Ocelot per tutti i gateway API.](./media/implement-api-gateways-with-ocelot/reusing-single-ocelot-docker-image.png)

**Figura 6-33**. Utilizzo di una singola immagine di Docker di Ocelot in più tipi di gateway API

In eShopOnContainers, l'immagine "Generic Ocelot API Gateway Docker Image" viene creata con il progetto denominato "OcelotApiGw" e il nome dell'immagine "eshop/ocelotapigw" specificato nel file docker-compose.yml. Durante la distribuzione in Docker, saranno presenti quattro contenitori API-Gateway creati dalla stessa immagine di Docker, come mostrato nel seguente estratto del file docker-compose.yml.

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

Inoltre, come si può notare nel file docker-compose.override.yml, l'unica differenza tra questi contenitori API-Gateway è il file di configurazione Ocelot, che è diverso per ogni contenitore di servizi e viene specificato in fase di esecuzione tramite un volume Docker.

```yml
mobileshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5200:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Shopping/apigw:/app/configuration

mobilemarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5201:80"
  volumes:
    - ./src/ApiGateways/Mobile.Bff.Marketing/apigw:/app/configuration

webshoppingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5202:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Shopping/apigw:/app/configuration

webmarketingapigw:
  environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - IdentityUrl=http://identity-api
  ports:
    - "5203:80"
  volumes:
    - ./src/ApiGateways/Web.Bff.Marketing/apigw:/app/configuration
```

A causa del codice precedente e, come illustrato di seguito in Visual Studio Explorer, l'unico file necessario per definire ogni gateway API aziendale/BFF specifico è un file configuration.json, perché i quattro gateway API si basano sulla stessa immagine Docker.

![Screenshot che mostra tutti i gateway API con file configuration.json.](./media/implement-api-gateways-with-ocelot/ocelot-configuration-files.png)

**Figura 6-34**. L'unico file necessario per definire ogni gateway API/BFF con Ocelot è un file di configurazione

Suddividendo il gateway API in più gateway API, i diversi team di sviluppo impegnati su subset diversi di microservizi possono gestire i propri gateway API usando file di configurazione Ocelot indipendenti. Possono inoltre usare contemporaneamente la stessa immagine Docker Ocelot.

A questo punto, se si esegue eShopOnContainers con i gateway API (incluso per impostazione predefinita in VS quando si apre la soluzione eShopOnContainers-ServicesAndWebApps.sln o se si esegue "docker-compose up"), verranno eseguite le route di esempio seguenti.

Quando ad esempio si visita l'URL upstream `http://localhost:5202/api/v1/c/catalog/items/2/` servito dal gateway API webshoppingapigw, si ottiene lo stesso risultato dall'URL downstream interno `http://catalog-api/api/v1/2` all'interno dell'host Docker, come nel browser seguente.

![Screenshot di un browser che mostra una risposta che passa attraverso il gateway API.](./media/implement-api-gateways-with-ocelot/access-microservice-through-url.png)

**Figura 6-35**. Accesso a un microservizio tramite un URL specificato dal gateway API

A causa di motivi di test o debug, se si desidera accedere direttamente al contenitore Catalog Docker (solo nell'ambiente di sviluppo) senza passare attraverso il gateway API, poiché 'catalog-api' è una risoluzione DNS interna all'host Docker (individuazione dei servizi gestita dai `http://localhost:5101/api/v1/Catalog/items/1` nomi dei servizi docker-compose), l'unico modo per accedere direttamente al contenitore è tramite la porta esterna pubblicata in do-compose.override.yml, che viene fornito solo per i test di sviluppo, ad esempio nel browser seguente.

![Screenshot di un browser che mostra una risposta diretta a Catalog.api.](./media/implement-api-gateways-with-ocelot/direct-access-microservice-testing.png)

**Figura 6-36**. Accesso diretto a un microservizio per scopi di test

Ma l'applicazione è configurata in modo che acceda a tutti i microservizi attraverso i gateway API, non attraverso la porta diretta "scorciatoie".

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a>Modello di aggregazione del gateway in eShopOnContainers

Come illustrato in precedenza, un modo flessibile per implementare l'aggregazione di richieste è con i servizi personalizzati, tramite il codice. È possibile implementare l'aggregazione di richieste anche con la [funzione di aggregazione richieste in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation) che tuttavia potrebbe non offrire la flessibilità necessaria. Pertanto, il modo selezionato per implementare l'aggregazione in eShopOnContainers è con un servizio API Web core ASP.NET esplicito per ogni aggregatore.

In base a questo approccio, il diagramma della composizione del gateway API risulta in realtà un po' più esteso quando si prendono in considerazione i servizi di aggregazione non inclusi nel diagramma dell'architettura globale semplificato illustrato in precedenza.

Nel diagramma seguente è possibile vedere in che modo i servizi di aggregazione collaborano con i gateway API correlati.

![Diagramma dell'architettura di eShopOnContainers che mostra i servizi di aggregatore.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-architecture-aggregator-services.png)

**Figura 6-37**. Architettura di eShopOnContainers con servizi di aggregazione

Ingrandire ulteriormente, nell'area di business "Shopping" nell'immagine seguente, è possibile vedere che la chiacchiere tra le app client e i microservizi si riduce quando si usano i servizi di aggregatore nei gateway API.

![Diagramma che mostra l'architettura di eShopOnContainers ingrandisci.](./media/implement-api-gateways-with-ocelot/zoom-in-vision-aggregator-services.png)

**Figura 6-38**. Visualizzazione in dettaglio dei servizi di aggregazione

È possibile notare come quando il diagramma mostra le possibili richieste provenienti dai gateway API può diventare complesso. Si può tuttavia notare come le frecce blu risultino semplificate, dalla prospettiva delle app client, quando si usa il modello di aggregatore riducendo il dialogo e la latenza nella comunicazione, finendo con il migliorare in modo significativo l'esperienza utente specialmente per le app remote (app SPA e per dispositivi mobili).

Nel caso dell'area di business "Marketing" e dei microservizi, si tratta di un semplice caso d'uso, quindi non è stato necessario utilizzare aggregatori, ma potrebbe anche essere possibile, se necessario.

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a>Autenticazione e autorizzazione nei gateway API Ocelot

In un gateway API Ocelot è possibile inserire un servizio di autenticazione, ad esempio un servizio API Web ASP.NET Core che usa [IdentityServer](https://identityserver.io/) per generare il token di autorizzazione, all'interno o all'esterno del gateway API.

Poiché eShopOnContainers usa più gateway API con limiti basati su aree di business e BFF, il servizio di gestione delle identità/autenticazione viene lasciato al di fuori dei gateway API, come evidenziato in giallo nel diagramma seguente.

![Diagramma che mostra il microservizio Identity sotto il gateway API.](./media/implement-api-gateways-with-ocelot/eshoponcontainers-identity-service-position.png)

**Figura 6-39**. Posizione del servizio di gestione delle identità in eShopOnContainers

Ocelot supporta tuttavia anche il posizionamento del microservizio di gestione delle identità/autenticazione all'interno del limite del gateway API, come illustrato in questo altro diagramma.

![Diagramma che mostra l'autenticazione in un gateway API Ocelot.Diagram showing authentication in an Ocelot API Gateway.](./media/implement-api-gateways-with-ocelot/ocelot-authentication.png)

**Figura 6-40**. Autenticazione in Ocelot

Come illustrato nel diagramma precedente, quando il microservizio Identity è sotto il gateway API (AG): 1) AG richiede un token di autenticazione dal microservizio di identità, 2) Il microservizio di identità restituisce il token a AG, 3-4) richieste di disponibilità dai microservizi usando il token di autenticazione. Poiché l'applicazione eShopOnContainers ha suddiviso il gateway API in più gateway API BFF (Backend per front-end) e aree di business, un'altra opzione sarebbe stata quella di creare un gateway API aggiuntivo per i problemi trasversali. Tale scelta sarebbe lecita in un'architettura basata su microservizi più complessa con più microservizi con aspetti trasversali. Poiché c'è solo una preoccupazione trasversale in eShopOnContainers, si è deciso di gestire solo il servizio di sicurezza fuori dall'area di autenticazione gateway API, per motivi di semplicità.

Se l'app è protetta a livello di gateway API, in ogni caso il modulo di autenticazione del gateway API Ocelot viene visitato per primo quando si tenta di usare un qualsiasi microservizio protetto. Che reindirizza la richiesta HTTP per visitare il microservizio di identità o autenticazione per ottenere il token di accesso in modo da poter visitare i servizi protetti con il access_token.

Per proteggere con autenticazione qualsiasi servizio a livello di gateway API, occorre impostare AuthenticationProviderKey nelle relative impostazioni nel file configuration.json.

```json
    {
      "DownstreamPathTemplate": "/api/{version}/{everything}",
      "DownstreamScheme": "http",
      "DownstreamHostAndPorts": [
        {
          "Host": "basket-api",
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

Quando Ocelot viene eseguito, esaminerà ReRoutes AuthenticationOptions.AuthenticationProviderKey e controllerà che sia presente un provider di autenticazione registrato con la chiave specificata. In caso negativo, Ocelot non viene avviato. In caso affermativo, invece, il reindirizzamento userà tale provider durante l'esecuzione.

Poiché il WebHost Ocelot è configurato con `authenticationProviderKey = "IdentityApiKey"`, sarà necessaria l'autenticazione ogni volta che il servizio riceverà richieste senza token di autenticazione.

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

È quindi necessario impostare l'autorizzazione con l'attributo [Authorize] in qualsiasi risorsa a cui si deve accedere, ad esempio i microservizi. Un esempio è il seguente controller del microservizio Basket.

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

I ValidAudience, ad esempio "basket", sono correlati al `AddJwtBearer()` gruppo di destinatari definito in ogni microservizio con il Metodo ConfigureServices() della classe Startup, ad esempio nel codice seguente.

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

Se si tenta di accedere a qualsiasi microservizio protetto, ad esempio il `http://localhost:5202/api/v1/b/basket/1`microservizio Basket con un URL ReRoute basato sul gateway API come , si otterrà un 401 Non autorizzato a meno che non si fornisca un token valido. D'altra parte, se un URL ReRoute è autenticato, Ocelot richiamerà qualsiasi schema downstream associato (l'URL del microservizio interno).

**Autorizzazione al livello ReRoutes di Ocelot.**  Ocelot supporta l'autorizzazione basata su attestazioni valutata dopo l'autenticazione. L'autorizzazione viene impostata a livello di route aggiungendo le righe seguenti alla configurazione di reindirizzamento.

```json
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

In questo esempio, quando viene chiamato il middleware di autorizzazione, Ocelot cerca se l'utente dispone del tipo di attestazione "UserType" nel token e se il valore di tale attestazione è "employee". In caso contrario, l'utente non sarà autorizzato e la risposta sarà 403 vietata.

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a>Utilizzo dell'oggetto Ingress di Kubernetes insieme ai gateway API Ocelot

Quando si usano Kubernetes (come in un cluster di servizi Azure Kubernetes), in genere si unificano tutte le richieste HTTP tramite il [livello Kubernetes Ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) basato su *Nginx*.

In Kubernetes, se non si utilizza alcun approccio in ingresso, i servizi e i pod dispongono di indirizzi IP instradabili solo dalla rete del cluster.

Se invece si usa un approccio con oggetto Ingress, si avrà un livello intermedio tra Internet e i servizi (inclusi i gateway API), che agisce come proxy inverso.

Come definizione, un oggetto Ingress è una raccolta di regole che consentono alle connessioni in ingresso di raggiungere i servizi del cluster. In genere si configura un oggetto Ingress per offrire ai servizi URL raggiungibili esternamente, bilanciare il traffico, consentire la terminazione SSL e altro ancora. Gli utenti richiedono l'ingresso eseguendo il comando POST sulla risorsa Ingress al server API.

In eShopOnContainers, quando lo sviluppo avviene in locale e si usa solo il computer di sviluppo come host Docker, non si usa alcun oggetto Ingress, ma solo più gateway API.

Tuttavia, quando si utilizza come destinazione un ambiente di "produzione" basato su Kubernetes, eShopOnContainers usa un ingresso davanti ai gateway API. I client, in questo modo, chiamano lo stesso URL di base, ma le richieste vengono instradate a più gateway API o BFF.

I gateway API sono front-end o facciate che visualizzano solo i servizi, ma non le applicazioni Web che in genere non sono escluse dall'ambito. I gateway API possono inoltre nascondere determinati microservizi interni.

L'oggetto Ingress, invece, si limita a reindirizzare le richieste HTTP ma non tenta di nascondere alcun microservizio o app Web.

La presenza di un livello Ingress Nginx in Kubernetes davanti alle applicazioni Web oltre ai diversi gateway API/BFF Ocelot rappresenta l'architettura ideale, come illustrato nel diagramma seguente.

![Diagramma che illustra come un livello in ingresso si inserisce nell'ambiente AKS.](./media/implement-api-gateways-with-ocelot/eshoponcontainer-ingress-tier.png)

**Figura 6-41**. Livello Ingress in eShopOnContainers quando distribuito in Kubernetes

Un oggetto Ingress di Kubernetes funge da proxy inverso per tutto il traffico diretto all'app, incluse le applicazioni Web che di solito non rientrano nell'ambito del gateway API. Quando viene distribuito in Kubernetes, eShopOnContainers espone alcuni servizi o endpoint tramite _Ingress_, fondamentalmente l'elenco seguente di suffissi negli URL:

- `/` per l'applicazione Web SPA client
- `/webmvc` per l'applicazione Web MVC client
- `/webstatus` per l'app Web client che mostra lo stato o i controlli di integrità
- `/webshoppingapigw` per i processi aziendali Web di BFF e Shopping
- `/webmarketingapigw` per i processi aziendali Web di BFF e Marketing
- `/mobileshoppingapigw` per i processi aziendali per dispositivi mobili di BFF e Shopping
- `/mobilemarketingapigw` per i processi aziendali per dispositivi mobili di BFF e Marketing

Quando si esegue la distribuzione in Kubernetes, ogni gateway API Ocelot utilizza un file "configuration.json" diverso per ogni _pod_ che esegue i gateway API. Questi file "configuration.json" vengono forniti montando (originariamente con lo script deploy.ps1) un volume creato in base a una mappa di _configurazione_ Kubernetes denominata 'ocelot'. Ogni contenitore monta il file di configurazione `/app/configuration`correlato nella cartella del contenitore denominata .

Nei file di codice sorgente di eShopOnContainers, i file "configuration.json" originali si trovano all'interno della `k8s/ocelot/` cartella. Esiste un file per ogni BFF/APIGateway.

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a>Altre funzionalità trasversali in un gateway API Ocelot

Esistono altre importanti funzionalità da cercare e usare quando si usa un gateway API Ocelot. Queste funzionalità sono descritte nei collegamenti seguenti.

- **Individuazione dei servizi sul lato client che integra Ocelot con Console o EurekaService discovery in the client side integrating Ocelot with Consul or Eureka** \
  <https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html>

- **Memorizzazione nella cache al livello Gateway APICaching at the API Gateway tier** \
  <https://ocelot.readthedocs.io/en/latest/features/caching.html>

- **Registrazione nel livello Gateway APILogging at the API Gateway tier** \
  <https://ocelot.readthedocs.io/en/latest/features/logging.html>

- **Qualità del servizio (tentativi e interruttori di circuito) al livello gateway API** \
  <https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html>

- **Limitazione della tariffa** \
  [https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

> [!div class="step-by-step"]
> [Successivo](background-tasks-with-ihostedservice.md)
> [precedente](../microservice-ddd-cqrs-patterns/index.md)
