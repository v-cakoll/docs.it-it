---
title: Implementazione di gateway API con Ocelot
description: Informazioni su come implementare i gateway API con Ocelot e come usare Ocelot in un ambiente basato su contenitori.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: e6ffef646f860a07920c37d239ee7f2e379aac92
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143857"
---
# <a name="implement-api-gateways-with-ocelot"></a>Implementare gateway API con Ocelot

L'applicazione di microservizi di riferimento [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) usa [Ocelot](https://github.com/ThreeMammals/Ocelot), un gateway API semplice e leggero che è possibile distribuire ovunque insieme a microservizi/contenitori, ad esempio in uno degli ambienti seguenti usati da eShopOnContainers.

- Host Docker, nel PC di sviluppo locale, in locale o nel cloud.
- Cluster Kubernetes, in locale o nel servizio Azure Kubernetes gestito.
- Cluster Service Fabric, in locale o nel cloud.
- Mesh Service Fabric, come PaaS/Serverless in Azure.

## <a name="architect-and-design-your-api-gateways"></a>Creare l'architettura e progettare i propri gateway API

Il seguente diagramma dell'architettura illustra in che modo i gateway API vengono implementati con Ocelot in eShopOnContainers.

![Diagramma dell'architettura di eShopOnContainers con app client e microservizi separati dai gateway API](./media/image28.png)

**Figura 6-28**. Architettura di eShopOnContainers con gateway API

Questo diagramma illustra in che modo l'intera applicazione viene distribuita in un singolo host Docker o un computer di sviluppo con "Docker per Windows" o "Docker per Mac". La distribuzione in un qualsiasi agente di orchestrazione, tuttavia, sarebbe piuttosto simile ma qualsiasi contenitore nel diagramma potrebbe venire ridimensionato orizzontalmente nell'agente di orchestrazione. 

Le risorse dell'infrastruttura, inoltre, ad esempio i database, la cache e i broker dei messaggi, devono essere scaricate dall'agente di orchestrazione e distribuite in sistemi a disponibilità elevata per l'infrastruttura, ad esempio Database SQL di Azure, Azure Cosmos DB, Redis di Azure, bus di servizio di Azure o qualsiasi altra soluzione di clustering a disponibilità elevata locale.

Come si può notare nel diagramma, la presenza di più gateway API consente a più team di sviluppo di essere autonomi (in questo caso, le funzionalità di Marketing e le funzionalità di Shopping) nello sviluppo e nella distribuzione di microservizi con i propri gateway API correlati. 

Un unico gateway API monolitico significherebbe un unico punto che i vari team di sviluppo devono aggiornare, con conseguente rischio di duplicazione di tutti i microservizi con una singola parte dell'applicazione.

Analizzando il progetto più a fondo, un gateway API specifico può talvolta essere limitato anche a un singolo microservizio aziendale a seconda dell'architettura scelta. Se per il gateway API si usano limiti stabiliti dall'azienda o dal dominio, si avrà una progettazione migliore.

La granularità a livello di gateway API può essere particolarmente utile per le applicazioni con interfaccia utente composita più avanzate basate su microservizi, perché il concetto di gateway API specifico è analogo a quello di un servizio di composizione dell'interfaccia utente. 

Altri dettagli sono illustrati nella sezione precedente [Creazione dell'interfaccia utente composita basata su microservizi](../architect-microservice-container-applications/microservice-based-composite-ui-shape-layout.md).

Come riferimento chiave, per molte applicazioni di medie e grandi dimensioni, l'utilizzo di un prodotto gateway API personalizzato rappresenta in genere un buon approccio, ma non come unico aggregatore monolitico o unico gateway API centrale personalizzato, a meno che tale gateway API non consenta più aree di configurazione indipendenti per i diversi team di sviluppo che creano microservizi autonomi.

### <a name="sample-microservicescontainers-to-re-route-through-the-api-gateways"></a>Microservizi/contenitori di esempio per il reindirizzamento tramite i gateway API

Per fare un esempio, eShopOnContainers include circa sei tipi di microservizi interni che devono essere pubblicati attraverso i gateway API, come illustrato nell'immagine seguente.

![Solo i microservizi Basket, Catalog, Location, Marketing, Ordering e Payment sono pubblicati tramite il gateway API.](./media/image29.png)

**Figura 6-29**. Cartelle di microservizi nella soluzione eShopOnContainers in Visual Studio

Per quanto riguarda il servizio di gestione delle identità, nella progettazione viene omesso dal routing del gateway API in quanto è l'unico aspetto trasversale nel sistema, sebbene con Ocelot sia anche possibile includere questo servizio negli elenchi di reindirizzamento.

Tutti questi servizi vengono attualmente implementati come servizi API Web ASP.NET Core, come si può vedere dal codice. Concentriamoci su uno dei microservizi, ad esempio il codice del microservizio Catalog.

![Visualizzazione in Esplora soluzioni del progetto Catalog.API.](./media/image30.png)

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

Per quanto riguarda l'URL del microservizio, quando i contenitori vengono distribuiti nel PC di sviluppo locale (host Docker locale), ogni contenitore del microservizio ha sempre una porta interna, in genere la porta 80, specificata nel dockerfile, come illustrato di seguito:

```
FROM microsoft/aspnetcore:2.0.5 AS base
WORKDIR /app
EXPOSE 80
```

La porta 80 indicata nel codice è interna all'host Docker, quindi non può essere raggiunta dalle app client. 

Le app client possono accedere solo alle porte esterne (se presenti) pubblicate durante la distribuzione con `docker-compose`.

È consigliabile non pubblicare queste porte esterne durante la distribuzione in un ambiente di produzione. È proprio questo il motivo per cui si usa il gateway API, per evitare la comunicazione diretta tra le app client e i microservizi.

Quando si sviluppa, invece, è utile accedere direttamente al microservizio/contenitore ed eseguirlo tramite Swagger. Questo è il motivo per cui in eShopOnContainers le porte esterne sono ancora specificate anche se non verranno usate dal gateway API o dalle app client.

Ecco un esempio del file `docker-compose.override.yml` per il microservizio Catalog:

```
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

Si può vedere che nella configurazione di docker-compose.override.yml la porta interna per il contenitore Catalog è la porta 80, ma la porta per l'accesso esterno è la numero 5101. Questa porta tuttavia non dovrebbe essere usata dall'applicazione quando si usa un gateway API solo per eseguire il debug, eseguire e testare solo il microservizio Catalog.

In genere non si distribuisce con docker-compose in un ambiente di produzione perché l'ambiente di distribuzione di produzione giusto per i microservizi è un agente di orchestrazione come Kubernetes o Service Fabric. Quando si esegue la distribuzione in questi ambienti, si usano file di configurazione diversi laddove non si pubblicherà direttamente una porta esterna per i microservizi ma si userà sempre il proxy inverso del gateway API.

Eseguire il microservizio Catalog nell'host Docker locale eseguendo la soluzione eShopOnContainers completa da Visual Studio (eseguirà tutti i servizi nei file docker-compose) o semplicemente avviando il microservizio Catalog con il comando docker-compose in CMD o PowerShell posizionato nella cartella in cui si trovano `docker-compose.yml` e docker-compose.override.yml.

```
docker-compose run --service-ports catalog.api
```

Questo comando esegue solo il contenitore del servizio catalog.api, oltre alle dipendenze specificate in docker-compose.yml, in questo caso, i contenitori SQL Server e RabbitMQ.

È quindi possibile accedere direttamente al microservizio Catalog e vedere i relativi metodi tramite l'interfaccia utente di Swagger accedendo direttamente tramite la porta "esterna", in questo caso `http://localhost:5101/swagger`:

![Visualizzazione nel browser dell'interfaccia utente di Swagger per l'API REST Catalog.API.](./media/image31.png)

**Figura 6-31**. Esecuzione dei test sul microservizio Catalog con la relativa interfaccia utente di Swagger

Si può a questo punto impostare un punto di interruzione nel codice C# in Visual Studio, eseguire i test sul microservizio con i metodi esposti nell'interfaccia utente di Swagger e infine pulire tutto usando il comando `docker-compose down`.

La comunicazione ad accesso diretto al microservizio, in questo caso attraverso la porta esterna 5101, è tuttavia esattamente ciò che si vuole evitare nell'applicazione. Si può ovviare impostando il livello aggiuntivo di riferimento indiretto del gateway API (in questo caso, Ocelot). L'app client in questo modo non accederà direttamente al microservizio.

## <a name="implementing-your-api-gateways-with-ocelot"></a>Implementazione di gateway API con Ocelot

Ocelot è essenzialmente un set di middleware che è possibile applicare in un ordine specifico.

Ocelot è progettato per funzionare solo con ASP.NET Core. È destinato a netstandard2.0, quindi può essere usato ovunque sia supportato .NET Standard 2.0, inclusi i runtime di .NET Core 2.0 e di .NET Framework 4.6.1 e versioni successive.

È possibile installare Ocelot e le relative dipendenze nel progetto ASP.NET Core con il [pacchetto NuGet di Ocelot](https://www.nuget.org/packages/Ocelot/) da Visual Studio.

```
Install-Package Ocelot
```

In eShopOnContainers l'implementazione del gateway API è un semplice progetto WebHost ASP.NET Core e i middleware di Ocelot gestiscono tutte le funzionalità del gateway API, come illustrato nell'immagine seguente:

![Visualizzazione in Esplora soluzioni del progetto del gateway API Ocelot.](./media/image32.png)

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

```
{
    "ReRoutes": [],
    "GlobalConfiguration": {}
}
```

La configurazione prevede due sezioni. Una matrice di reindirizzamenti (ReRoutes) e una configurazione globale (GlobalConfiguration). I reindirizzamenti sono gli oggetti che indicano a Ocelot come gestire una richiesta upstream. La configurazione globale consente di eseguire l'override di impostazioni specifiche del reindirizzamento. È utile se non si vuole gestire un numero elevato di impostazioni specifiche del reindirizzamento.

Di seguito è riportato un esempio semplificato di [file di configurazione del reindirizzamento](https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/ApiGateways/Web.Bff.Shopping/apigw/configuration.json) di uno dei gateway API di eShopOnContainers.

```
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

La funzionalità principale di un gateway API Ocelot consiste nel ricevere le richieste HTTP in ingresso e di inoltrarle a un servizio downstream, come un'altra richiesta HTTP. Ocelot descrive il routing di una richiesta a un altro servizio come un reindirizzamento.

Si pensi ad esempio a uno dei reindirizzamenti nel file configuration.json precedente, la configurazione del microservizio Basket.

```
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

Gli oggetti DownstreamPathTemplate, Scheme e DownstreamHostAndPorts costituiscono l'URL del microservizio a cui sarà inoltrata questa richiesta. 

La porta è la porta interna usata dal servizio. Quando si usano i contenitori, è la porta specificata nel relativo dockerfile.

L'oggetto `Host` è un nome di servizio che dipende dalla risoluzione dei nomi dei servizi in uso. Quando si usa docker-compose, i nomi dei servizi vengono specificati dall'host Docker, che usa i nomi di servizio specificati nei file docker-compose. Se si usa un agente di orchestrazione, come Kubernetes o Service Fabric, tale nome deve essere risolto dal DNS o dalla risoluzione dei nomi indicata da ogni agente di orchestrazione.

DownstreamHostAndPorts è una matrice che contiene l'host e la porta di tutti i servizi downstream a cui si desidera inoltrare le richieste. Questo oggetto contiene di solito una sola voce ma talvolta si può voler bilanciare le richieste ai servizi downstream e Ocelot consente di aggiungere più voci e selezionare un servizio di bilanciamento del carico. Se tuttavia si usano Azure e un qualsiasi agente di orchestrazione, è probabilmente meglio bilanciare il carico con l'infrastruttura del cloud e dell'agente di orchestrazione.

L'oggetto UpstreamPathTemplate è l'URL che Ocelot userà per identificare quale oggetto DownstreamPathTemplate usare per una determinata richiesta del client. Viene infine usato l'oggetto UpstreamHttpMethod per consentire a Ocelot di distinguere tra le varie richieste (GET, POST, PUT) allo stesso URL.

È possibile a questo punto che si abbia un unico gateway API Ocelot (ASP.NET Core WebHost) che usa uno o [più file configuration.json uniti](https://ocelot.readthedocs.io/en/latest/features/configuration.html#merging-configuration-files) oppure è possibile archiviare la [configurazione in un archivio Consul KV](https://ocelot.readthedocs.io/en/latest/features/configuration.html#store-configuration-in-consul). 

Se tuttavia, come detto nelle sezioni sull'architettura e la progettazione, si intende veramente avere microservizi autonomi, potrebbe essere più opportuno suddividere il singolo gateway API monolitico in più gateway API e/o BFF (back-end per front-end). Vediamo a tale scopo come implementare questo approccio con i contenitori Docker.

### <a name="using-a-single-docker-container-image-to-run-multiple-different-api-gateway--bff-container-types"></a>Utilizzo di una singola immagine del contenitore Docker per eseguire più tipi di contenitore gateway API/BFF 

In eShopOnContainers viene usata una singola immagine del contenitore Docker con il gateway API Ocelot ma successivamente, in fase di esecuzione, vengono creati servizi/contenitori diversi per ogni tipo di API-Gateway/BFF specificando un file configuration.json diverso che usa un volume Docker per accedere a una cartella del PC diversa per ogni servizio.

![Viene usata una singola immagine Docker per gateway API Ocelot per tutti e quattro i gateway API](./media/image33.png)

**Figura 6-33**. Riuso di una singola immagine Docker per Ocelot su più tipi di gateway API

In eShopOnContainers l'"immagine generica del Docker del gateway API Ocelot" viene creata con il progetto denominato "OcelotApiGw" e il nome di immagine "eshop/ocelotapigw" specificato nel file docker-compose.yml. Durante la distribuzione in Docker, saranno presenti quattro contenitori API-Gateway creati dalla stessa immagine di Docker, come mostrato nel seguente estratto del file docker-compose.yml.

```

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

```
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

A causa del codice precedente e, come illustrato di seguito in Visual Studio Explorer, l'unico file necessario per definire ogni gateway API aziendale/BFF specifico è un file configuration.json, perché i quattro gateway API si basano sulla stessa immagine Docker.

![L'unica differenza tra tutti i gateway API è costituita da un file configuration.json presente in ognuno di essi.](./media/image34.png)

**Figura 6-34**. L'unico file necessario per definire ogni gateway API/BFF con Ocelot è un file di configurazione

Suddividendo il gateway API in più gateway API, i diversi team di sviluppo impegnati su subset diversi di microservizi possono gestire i propri gateway API usando file di configurazione Ocelot indipendenti. Possono inoltre usare contemporaneamente la stessa immagine Docker Ocelot. 

Se a questo punto si esegue eShopOnContainers con i gateway API (inclusi per impostazione predefinita in VS quando si apre la soluzione eShopOnContainers-ServicesAndWebApps.sln e si esegue "docker-compose up"), verranno eseguiti gli indirizzamenti di esempio indicati di seguito.

Quando ad esempio si visita l'URL upstream `http://localhost:5202/api/v1/c/catalog/items/2/` servito dal gateway API webshoppingapigw, si ottiene lo stesso risultato dall'URL downstream interno `http://catalog.api/api/v1/2` all'interno dell'host Docker, come nel browser seguente.

![Visualizzazione nel browser di una risposta di Catalog.api che passa attraverso il gateway API.](./media/image35.png)

**Figura 6-35**. Accesso a un microservizio tramite un URL specificato dal gateway API

Se, per motivi di test o di debug, si vuole accedere direttamente al contenitore Docker Catalog (solo nell'ambiente di sviluppo) senza passare attraverso il gateway API, poiché "catalog.api" è una risoluzione DNS interna all'host Docker (individuazione del servizio gestita da nomi di servizio di docker-compose), l'unico modo disponibile è attraverso la porta esterna pubblicata nel file docker-compose.override.yml, che viene fornita solo per i test di sviluppo, ad esempio `http://localhost:5101/api/v1/Catalog/items/1` nel browser seguente.

![Visualizzazione nel browser di una risposta di Catalog.api che passa direttamente al servizio Catalog.api, identica a quella che passa attraverso il gateway API.](./media/image36.png)

**Figura 6-36**. Accesso diretto a un microservizio per scopi di test

L'applicazione viene invece configurata in modo da accedere a tutti i microservizi tramite i gateway API, non tramite il "collegamento" alla porta diretta.

### <a name="the-gateway-aggregation-pattern-in-eshoponcontainers"></a>Modello di aggregazione del gateway in eShopOnContainers

Come illustrato in precedenza, un modo flessibile per implementare l'aggregazione di richieste è con i servizi personalizzati, tramite il codice. È possibile implementare l'aggregazione di richieste anche con la [funzione di aggregazione richieste in Ocelot](https://ocelot.readthedocs.io/en/latest/features/requestaggregation.html#request-aggregation) che tuttavia potrebbe non offrire la flessibilità necessaria. Il modo scelto per implementare l'aggregazione in eShopOnContainers è quindi con un servizio esplicito di API Web ASP.NET Core per ogni aggregatore.

In base a questo approccio, il diagramma della composizione del gateway API risulta in realtà un po' più esteso quando si prendono in considerazione i servizi di aggregazione non inclusi nel diagramma dell'architettura globale semplificato illustrato in precedenza.

Nel diagramma seguente è possibile vedere in che modo i servizi di aggregazione collaborano con i gateway API correlati.

![Architettura di eShopOnContainers con i servizi di aggregazione.](./media/image37.png)

**Figura 6-37**. Architettura di eShopOnContainers con servizi di aggregazione

Entrando maggiormente in dettaglio, nell'area di business "Shopping" nell'immagine seguente è possibile vedere che le comunicazioni frammentate tra le app client e i microservizi diminuiscono quando si usano i servizi di aggregazione nei gateway API.

 ![Architettura di eShopOnContainers ingrandita, con i servizi di aggregazione, che "assembla" una risposta "unendo" le risposte di diversi microservizi per ridurre le comunicazioni frammentate con il client finale.](./media/image38.png)

**Figura 6-38**. Visualizzazione in dettaglio dei servizi di aggregazione

È possibile notare come, quando vengono mostrate le possibili richieste provenienti dai gateway API, il diagramma diventi piuttosto complesso. Si può tuttavia notare come le frecce blu risultino semplificate, dalla prospettiva delle app client, quando si usa il modello di aggregatore riducendo il dialogo e la latenza nella comunicazione, finendo con il migliorare in modo significativo l'esperienza utente specialmente per le app remote (app SPA e per dispositivi mobili).

Nel caso dell'area di business e dei microservizi "Marketing" si tratta di un caso d'uso molto semplice pertanto non occorre usare aggregatori, ma, se necessario, sarebbe possibile farlo.

### <a name="authentication-and-authorization-in-ocelot-api-gateways"></a>Autenticazione e autorizzazione nei gateway API Ocelot

In un gateway API Ocelot è possibile inserire un servizio di autenticazione, ad esempio un servizio API Web ASP.NET Core che usa [IdentityServer](https://identityserver.io/) per generare il token di autorizzazione, all'interno o all'esterno del gateway API.

Poiché eShopOnContainers usa più gateway API con limiti basati su aree di business e BFF, il servizio di gestione delle identità/autenticazione viene lasciato al di fuori dei gateway API, come evidenziato in giallo nel diagramma seguente.

 ![Diagramma dell'architettura di eShopOnContainers con il microservizio di gestione delle identità nel gateway API.](./media/image39.png)

**Figura 6-39**. Posizione del servizio di gestione delle identità in eShopOnContainers

Ocelot supporta tuttavia anche il posizionamento del microservizio di gestione delle identità/autenticazione all'interno del limite del gateway API, come illustrato in questo altro diagramma.

 ![Autenticazione con il servizio di gestione delle identità nel gateway API (AG): 1) AG richiede un token di autenticazione al microservizio di gestione delle identità, 2) Il microservizio di gestione delle identità restituisce il token ad AG, 3-4) AG invia le richieste ai microservizi usando il token di autenticazione.](./media/image40.png)

**Figura 6-40**. Autenticazione in Ocelot

Poiché l'applicazione eShopOnContainers ha suddiviso il gateway API in più gateway API di BFF (back-end per front-end) e aree di business, un'altra opzione sarebbe stata quella di creare un gateway API aggiuntivo per gli aspetti trasversali. Tale scelta sarebbe lecita in un'architettura basata su microservizi più complessa con più microservizi con aspetti trasversali. Poiché in eShopOnContainers esiste un solo aspetto trasversale, è stato deciso di gestire semplicemente il servizio di sicurezza al di fuori dell'ambito del gateway API, per motivi di semplicità.

Se l'app è protetta a livello di gateway API, in ogni caso il modulo di autenticazione del gateway API Ocelot viene visitato per primo quando si tenta di usare un qualsiasi microservizio protetto. Tale operazione reindirizza la richiesta HTTP verso un microservizio di gestione delle identità o di autenticazione per ottenere il token di accesso e poter così visitare i servizi protetti con il token di accesso.

Per proteggere con autenticazione qualsiasi servizio a livello di gateway API, occorre impostare AuthenticationProviderKey nelle relative impostazioni nel file configuration.json.

```
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

In fase di esecuzione, Ocelot cerca nella sezione dei reindirizzamenti (ReRoutes) la voce AuthenticationOptions.AuthenticationProviderKey e verifica che sia stato registrato un provider di autenticazione con la chiave specificata. In caso negativo, Ocelot non viene avviato. In caso affermativo, invece, il reindirizzamento userà tale provider durante l'esecuzione.

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

Le voci ValidAudiences, ad esempio "basket", sono correlate al pubblico definito in ogni microservizio con `AddJwtBearer()` nel metodo ConfigureServices() della classe Startup, come nel codice riportato di seguito.

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

Se si prova ad accedere a qualsiasi microservizio protetto, ad esempio il microservizio Basket con un URL di reindirizzamento basato sul gateway API, quale `http://localhost:5202/api/v1/b/basket/1`, verrà restituito l'errore 401 di utente non autorizzato, a meno che non si specifichi un token valido. D'altra parte, se un URL di reindirizzamento viene autenticato, Ocelot richiamerà qualsiasi schema di downstream ad esso associato (l'URL interno del microservizio).

**Autorizzazione a livello di reindirizzamenti di Ocelot.**  Ocelot supporta l'autorizzazione basata su attestazioni valutata dopo l'autenticazione. L'autorizzazione viene impostata a livello di route aggiungendo le righe seguenti alla configurazione di reindirizzamento. 

```
"RouteClaimsRequirement": {
    "UserType": "employee"
}
```

In questo esempio, quando viene chiamato il middleware di autorizzazione, Ocelot cerca se l'utente dispone del tipo di attestazione "UserType" nel token e se il valore di tale attestazione è "employee". Se Ocelot non trova queste informazioni, l'utente non verrà autorizzato e la risposta sarà un messaggio 403 di accesso negato.

## <a name="using-kubernetes-ingress-plus-ocelot-api-gateways"></a>Utilizzo dell'oggetto Ingress di Kubernetes insieme ai gateway API Ocelot

Quando si usa Kubernetes (come in un cluster del servizio Azure Kubernetes), in genere si uniscono tutte le richieste HTTP attraverso il [livello di oggetto Ingress di Kubernetes](https://kubernetes.io/docs/concepts/services-networking/ingress/) basato su *Nginx*.

In Kubernetes, se non si usa un alcun approccio con oggetto Ingress, i servizi e i pod hanno indirizzi IP instradabili solo dalla rete di cluster. 

Se invece si usa un approccio con oggetto Ingress, si avrà un livello intermedio tra Internet e i servizi (inclusi i gateway API), che agisce come proxy inverso.

Come definizione, un oggetto Ingress è una raccolta di regole che consentono alle connessioni in ingresso di raggiungere i servizi del cluster. In genere si configura un oggetto Ingress per offrire ai servizi URL raggiungibili esternamente, bilanciare il traffico, consentire la terminazione SSL e altro ancora. Gli utenti richiedono l'ingresso eseguendo il comando POST sulla risorsa Ingress al server API.

In eShopOnContainers, quando lo sviluppo avviene in locale e si usa solo il computer di sviluppo come host Docker, non si usa alcun oggetto Ingress, ma solo più gateway API.

Quando invece la destinazione è un ambiente di "produzione" basato su Kubernetes, eShopOnContainers usa un oggetto Ingress davanti ai gateway API. I client, in questo modo, chiamano lo stesso URL di base, ma le richieste vengono instradate a più gateway API o BFF. 

I gateway API sono front-end o facciate che espongono solo i servizi, ma non le applicazioni Web che di solito non rientrano nel loro ambito. I gateway API possono inoltre nascondere determinati microservizi interni. 

L'oggetto Ingress, invece, si limita a reindirizzare le richieste HTTP ma non tenta di nascondere alcun microservizio o app Web.

La presenza di un livello Ingress Nginx in Kubernetes davanti alle applicazioni Web oltre ai diversi gateway API/BFF Ocelot rappresenta l'architettura ideale, come illustrato nel diagramma seguente.

 ![Un oggetto Ingress di Kubernetes funge da proxy inverso per tutto il traffico diretto all'app, incluse le applicazioni Web che di solito non rientrano nell'ambito del gateway API.](./media/image41.png)

**Figura 6-41**. Livello Ingress in eShopOnContainers quando distribuito in Kubernetes

Quando viene distribuito in Kubernetes, eShopOnContainers espone alcuni servizi o endpoint tramite _Ingress_, fondamentalmente l'elenco seguente di suffissi negli URL:

-   `/` per l'applicazione Web SPA client
-   `/webmvc` per l'applicazione Web MVC client
-   `/webstatus` per l'app Web client che mostra lo stato o i controlli di integrità
-   `/webshoppingapigw` per i processi aziendali Web di BFF e Shopping
-   `/webmarketingapigw` per i processi aziendali Web di BFF e Marketing
-   `/mobileshoppingapigw` per i processi aziendali per dispositivi mobili di BFF e Shopping
-   `/mobilemarketingapigw` per i processi aziendali per dispositivi mobili di BFF e Marketing

Durante la distribuzione in Kubernetes, ogni gateway API Ocelot usa un file "configuration.json" diverso per ogni _pod_ che esegue i gateway API. Questi file "configuration.json" vengono specificati montando (originariamente con lo script deploy.ps1) un volume creato in base a una _mappa di configurazione_ di Kubernetes denominata "ocelot". Ogni contenitore monta il file di configurazione correlato nella cartella del contenitore denominata `/app/configuration`.

Nel file del codice sorgente di eShopOnContainers i file "configuration.json" originali sono reperibili all'interno della cartella `k8s/ocelot/`. È disponibile un file per ogni gateway API/BFF.

## <a name="additional-cross-cutting-features-in-an-ocelot-api-gateway"></a>Altre funzionalità trasversali in un gateway API Ocelot

Esistono altre importanti funzionalità da cercare e usare quando si usa un gateway API Ocelot. Queste funzionalità sono descritte nei collegamenti seguenti.

- **Individuazione di servizi sul lato client che integra Ocelot con Consul o Eureka** \
  [*https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html*](https://ocelot.readthedocs.io/en/latest/features/servicediscovery.html)

- **Memorizzazione nella cache a livello di gateway API** \
  [*https://ocelot.readthedocs.io/en/latest/features/caching.html*](https://ocelot.readthedocs.io/en/latest/features/caching.html)

- **Registrazione a livello di gateway API** \
  [*https://ocelot.readthedocs.io/en/latest/features/logging.html*](https://ocelot.readthedocs.io/en/latest/features/logging.html)

- **Qualità del servizio (nuovi tentativi e interruttori) a livello di gateway API** \
  [*https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html*](https://ocelot.readthedocs.io/en/latest/features/qualityofservice.html)

- **Limite di frequenza** \
  [*https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html*](https://ocelot.readthedocs.io/en/latest/features/ratelimiting.html )

>[!div class="step-by-step"]
>[Precedente](background-tasks-with-ihostedservice.md)
>[Successivo](../microservice-ddd-cqrs-patterns/index.md)