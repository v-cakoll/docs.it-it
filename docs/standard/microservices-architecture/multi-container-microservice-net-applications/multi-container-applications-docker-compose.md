---
title: Definizione dell'applicazione a più contenitori con docker-compose.yml
description: Architettura di microservizi .NET per le applicazioni nei contenitori .NET | Definizione dell'applicazione a più contenitori con docker-compose.yml
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.openlocfilehash: d1c4166129716ccbbc86855e38d631f493b82290
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2018
ms.locfileid: "46937605"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Definizione dell'applicazione a più contenitori con docker-compose.yml 

Il file [docker-compose.yml](https://docs.docker.com/compose/compose-file/) è stato introdotto nella sezione [Passaggio 4 di questa guida. Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori](#step4_define_svcs_in_docker_compose_yml). Tuttavia esistono altri modi per usare i file docker-compose che vale la pena di esplorare in maggiore dettaglio.

È possibile, ad esempio, descrivere in modo esplicito la modalità di distribuzione dell'applicazione a più contenitori nel file docker-compose.yml. Facoltativamente è possibile anche descrivere come si intende compilare le immagini Docker personalizzate. Le immagini Docker personalizzate possono essere compilate anche con l'interfaccia della riga di comando di Docker.

In pratica è possibile definire ciascun contenitore da distribuire, più determinate caratteristiche per ogni distribuzione di contenitore. Dopo aver creato un file di descrizione della distribuzione di più contenitori, è possibile distribuire l'intera soluzione con un'unica azione orchestrata dal comando dell'interfaccia della riga di comando [docker-compose up](https://docs.docker.com/compose/overview/) oppure in modo trasparente da Visual Studio. In caso contrario, sarebbe necessario usare l'interfaccia della riga di comando di Docker per eseguire la distribuzione contenitore per contenitore in più passaggi usando il comando docker run dalla riga di comando. Pertanto ogni servizio definito in docker-compose.yml deve specificare esattamente un'immagine o una build. Le altre chiavi sono facoltative e sono analoghe alle controparti della riga di comando docker run.

Il seguente codice YAML definisce un possibile file docker-compose.yml globale, ma unico per l'esempio eShopOnContainers. Non si tratta del file docker-compose reale di eShopOnContainers. È invece una versione semplificata e consolidata in un singolo file, ma non è il modo migliore per lavorare con i file docker-compose, come sarà illustrato in seguito.

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

La chiave radice in questo file sono i servizi. Sotto questa chiave si definiscono i servizi che si vuole distribuire ed eseguire quando si esegue il comando docker-compose up o quando si esegue la distribuzione da Visual Studio usando questo file docker-compose.yml. In questo caso, nel file docker compose.yml sono stati definiti più servizi, come descritto nell'elenco seguente.

-   webmvc Contenitore che include l'applicazione ASP.NET Core MVC che usa i microservizi da C\# sul lato server

-   catalog.api Contenitore che include il microservizio API Web ASP.NET Core che gestisce i cataloghi

-   ordering.api Contenitore che include il microservizio API Web ASP.NET Core che gestisce gli ordini

-   sql.data Contenitore che esegue SQL Server per Linux, contenente i database di microservizi

-   basket.API Contenitore con il microservizio API Web ASP.NET Core che gestisce i carrelli

-   basket.data Contenitore che esegue il servizio cache REDIS, con il database dei carrelli come cache REDIS

### <a name="a-simple-web-service-api-container"></a>Un semplice contenitore di API di servizi Web

Concentrandosi su un singolo contenitore, la definizione del microservizio contenitore catalog.api è semplice:

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

La configurazione base di questo servizio con contenitore è la seguente:

-   Si basa sull'immagine eshop/catalog.api personalizzata. Per semplicità non esiste un'impostazione chiave build: nel file. Ciò significa che l'immagine deve essere stata compilata in precedenza (con docker build) oppure è stata scaricata (con il comando docker pull) da un registro Docker.

-   Definisce una variabile di ambiente denominata ConnectionString con la stringa di connessione che Entity Framework deve usare per accedere all'istanza di SQL Server contenente il modello di dati di catalogo. In questo caso, lo stesso contenitore SQL Server contiene più database. Pertanto la memoria necessaria nel computer di sviluppo per Docker è inferiore. Tuttavia è possibile anche distribuire un contenitore SQL Server per ogni database di microservizi.

-   Il nome SQL Server è sql.data, ovvero lo stesso nome usato per il contenitore in cui è in esecuzione l'istanza di SQL Server per Linux. Questo approccio è vantaggioso perché la possibilità di usare questa risoluzione di nomi (interna all'host Docker) risolverà l'indirizzo di rete e non è quindi necessario conoscere l'IP interno per i contenitori a cui si sta accedendo da altri contenitori.

Poiché la stringa di connessione viene definita da una variabile di ambiente, è possibile impostare questa variabile tramite un meccanismo diverso e in un momento diverso. Ad esempio, è possibile impostare una stringa di connessione diversa durante la distribuzione in produzione negli host finali oppure dalle pipeline CI/CD in Azure DevOps Services o dal sistema DevOps preferito.

-   Espone la porta 80 per l'accesso interno al servizio catalog.api all'interno dell'host Docker. L'host è attualmente una VM Linux perché si basa su un'immagine Docker per Linux, ma è possibile configurare il contenitore per l'esecuzione su un'immagine per Windows.

-   Inoltra la porta 80 esposta sul contenitore alla porta esterna 5101 sul computer host Docker (la VM Linux).

-   Collega il servizio Web al servizio sql.data, ossia l'istanza di SQL Server per il database Linux in esecuzione in un contenitore. Quando si specifica questa dipendenza, il contenitore catalog.api verrà avviato solo dopo l'avvio del contenitore sql.data; questo aspetto è importante perché per catalog.api è necessario che prima sia in esecuzione il database SQL Server. Tuttavia, questo tipo di dipendenza di contenitore non è sufficiente in molti casi poiché Docker esegue il controllo solo a livello di contenitore. In alcuni casi il servizio, in questo caso SQL Server, potrebbe non essere ancora pronto ed è quindi consigliabile implementare la logica di ripetizione con il backoff esponenziale nei microservizi client. In questo modo, se un contenitore di dipendenza non è pronto per un breve periodo di tempo, l'applicazione sarà ancora resiliente.

-   Viene configurata per consentire l'accesso ai server esterni: l'impostazione extra\_hosts consente di accedere ai server esterni o ai computer all'esterno dell'host Docker (quindi all'esterno della VM predefinita che è un host Docker di sviluppo), ad esempio un'istanza locale di SQL Server sul PC di sviluppo.

Altre impostazioni più avanzate del file docker-compose.yml verranno illustrate nelle sezioni successive.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Utilizzo dei file docker-compose per usare più ambienti come destinazione

I file docker-compose.yml sono file di definizione e possono essere usati da più infrastrutture compatibili con questo formato. Lo strumento più semplice è il comando docker-compose, ma anche altri strumenti come gli agenti di orchestrazione, ad esempio Docker Swarm, sono compatibili con questo file.

Con il comando docker-compose è quindi possibile usare come destinazione i seguenti scenari principali.

#### <a name="development-environments"></a>Ambienti di sviluppo

Quando si sviluppano applicazioni, è importante poter eseguire un'applicazione in un ambiente di sviluppo isolato. È possibile usare il comando dell'interfaccia della riga di comando docker-compose per creare questo ambiente oppure usare Visual Studio che esegue docker-compose in background.

Il file docker-compose.yml consente di configurare e documentare tutte le dipendenze di servizio dell'applicazione,come altri servizi, cache, database, code e così via. Con il comando dell'interfaccia della riga di comando docker-compose è possibile creare e avviare uno o più contenitori per ogni dipendenza con un unico comando (docker-compose up).

I file docker-compose.yml sono file di configurazione interpretati dal motore Docker, ma servono anche come utili file di documentazione sulla composizione dell'applicazione a più contenitori.

#### <a name="testing-environments"></a>Ambienti di test

Un aspetto importante di qualsiasi processo di distribuzione continua (CD) o di integrazione continua (CI) sono gli unit test e i test di integrazione. Questi test automatizzati richiedono un ambiente isolato per evitare impatti da parte degli utenti o di eventuali altre modifiche nei dati dell'applicazione.

Con Docker Compose è possibile creare ed eliminare definitivamente l'ambiente isolato molto facilmente usando alcuni comandi al prompt dei comandi o script, come i comandi seguenti:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>Distribuzioni in produzione

È possibile anche usare Docker Compose per eseguire la distribuzione in un motore Docker remoto. Un caso tipico consiste nella distribuzione di una singola istanza dell'host Docker, ad esempio una macchina virtuale in produzione o un server di cui viene eseguito il provisioning con [Docker Machine](https://docs.docker.com/machine/overview/). Potrebbe anche essere un intero cluster [Docker Swarm](https://docs.docker.com/swarm/overview/) perché anche i cluster sono compatibili con i file docker-compose.yml.

Se si usa qualsiasi altro agente di orchestrazione (Microsoft Azure Service Fabric, Mesos DC/OS, Kubernetes, ecc.), potrebbe essere necessario aggiungere impostazioni di installazione e configurazione dei metadati, come quelle in docker-compose.yml, ma nel formato richiesto dall'altro agente di orchestrazione.

In ogni caso, docker-compose è un utile strumento e formato di metadati per lo sviluppo, i test e i flussi di lavoro di produzione, anche se il flusso di lavoro di produzione potrebbe variare in base all'agente di orchestrazione in uso.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Utilizzo di più file docker-compose per la gestione di ambienti diversi

Se si usano come destinazione ambienti diversi, è necessario usare più file compose. In questo modo è possibile creare più varianti di configurazione a seconda dell'ambiente.

#### <a name="overriding-the-base-docker-compose-file"></a>Override del file docker-compose base

È possibile usare un singolo file docker-compose.yml, come negli esempi semplificati illustrati nelle sezioni precedenti. Tuttavia questo approccio non è consigliabile per la maggior parte delle applicazioni.

Per impostazione predefinita, Compose legge due file: docker-compose.yml e un file docker-compose.override.yml facoltativo. Come illustrato nella figura 8-11, quando si usa Visual Studio e si abilita il supporto di Docker, Visual Studio crea anche un file docker-compose.ci.build.yml aggiuntivo da usare dalle pipeline CI/CD come in Azure DevOps Services.

![](./media/image12.png)

**Figura 8-11**. File docker-compose in Visual Studio 2017

È possibile modificare i file docker-compose con qualsiasi editor di codice di Visual Studio o Sublime ed eseguire l'applicazione con il comando docker-compose up.

Per convenzione, il file docker-compose.yml contiene la configurazione base e altre impostazioni statiche. Ciò significa che la configurazione del servizio non deve cambiare a seconda dell'ambiente di distribuzione di destinazione.

Il file docker-compose.override.yml, come suggerisce il nome, contiene le impostazioni di configurazione che eseguono l'override della configurazione base, ad esempio la configurazione che dipende dall'ambiente di distribuzione. È possibile anche avere più file di override con nomi diversi. I file di override in genere contengono informazioni aggiuntive necessarie per l'applicazione, ma specifiche per un ambiente o una distribuzione.

#### <a name="targeting-multiple-environments"></a>Utilizzo di più ambienti come destinazione

Un tipico caso d'uso è quello in cui si definiscono più file compose in modo da poter usare come destinazione più ambienti, ad esempio quello di produzione, staging, CI o sviluppo. Per supportare queste differenze, è possibile dividere la configurazione di Compose in più file, come illustrato nella figura 8-12.

![](./media/image13.png)

**Figura 8-12**. Più file docker-compose che eseguono l'override di valori del file docker-compose.yml base

Iniziare con il file docker-compose.yml base. Questo file base deve contenere le impostazioni di configurazione base o statiche, ossia che non cambiano in base all'ambiente. Ad esempio, il file base di eShopOnContainers è il file docker-compose.yml seguente.

```yml
#docker-compose.yml (Base)
version: '3'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: ./src/Services/Basket/Basket.API
      dockerfile: Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: ./src/Services/Catalog/Catalog.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: ./src/Services/Marketing/Marketing.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: ./src/Web/WebMVC
      dockerfile: Dockerfile    
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api
      - marketing.api

  sql.data:
    image: microsoft/mssql-server-linux:2017-latest

  nosql.data:
    image: mongo

  basket.data:
    image: redis
      
  rabbitmq:
    image: rabbitmq:3-management

```

I valori nel file docker-compose.yml base non devono essere modificati in base ai diversi ambienti di distribuzione di destinazione.

Se, ad esempio, si esamina con attenzione la definizione del servizio webmvc, si nota come queste informazioni sono più o meno le stesse indipendentemente dall'ambiente di destinazione. Sono disponibili le seguenti informazioni:

-   Il nome del servizio: webmvc.

-   L'immagine personalizzata del contenitore: eshop/webmvc.

-   Il comando per compilare l'immagine personalizzata di Docker, che indica il Dockerfile da usare.

-   Le dipendenze da altri servizi, per cui questo contenitore viene avviato solo dopo che sono stati avviati gli altri contenitori di dipendenza.

È possibile avere una configurazione aggiuntiva, ma il punto importante è che nel file docker-compose.yml base si impostano solo le informazioni comuni tra gli ambienti. Nel file docker-compose.override.yml o nei file simili per la produzione o lo staging si inserisce la configurazione specifica per ogni ambiente.

In genere, il file docker-compose.override.yml viene usato per l'ambiente di sviluppo, come nell'esempio seguente dall'applicazione eShopOnContainers:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3'

services: 
# Simplified number of services here: 
      
  basket.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basket.data}
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}      
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5101/api/v1/catalog/items/[0]/pic/}   
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}         
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}          
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
      - LocationsUrl=http://locations.api
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://marketing.api                                                    
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc     
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - MSSQL_SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
      - MSSQL_PID=Developer
    ports:
      - "5433:1433"
  nosql.data:
    ports:
      - "27017:27017"
  basket.data:
    ports:
      - "6379:6379"      
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

In questo esempio, la configurazione di override dello sviluppo espone alcune porte all'host, definisce le variabili di ambiente con gli URL di reindirizzamento e specifica le stringhe di connessione per l'ambiente di sviluppo. Queste impostazioni sono tutte relative solo all'ambiente di sviluppo.

Quando si esegue `docker-compose up` o lo si avvia da Visual Studio, il comando legge automaticamente le sostituzioni come se stesse unendo entrambi i file.

Si supponga di voler creare un altro file Compose per l'ambiente di produzione, con diversi valori di configurazione, porte o stringhe di connessione. È possibile creare un altro file di override, ad esempio un file denominato `docker-compose.prod.yml` con diverse impostazioni e variabili di ambiente.  Questo file potrebbe essere archiviato in un diverso repository Git oppure gestito e protetto da un team diverso.

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Come distribuire un file di override specifico

Per usare più file di override o un file di override con un nome diverso, è possibile usare l'opzione -f con il comando docker-compose e specificare i file. Compose unisce i file nell'ordine in che cui vengono specificati alla riga di comando. Nell'esempio seguente viene illustrato come eseguire la distribuzione con i file di override.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Utilizzo di variabili di ambiente nei file docker-compose

È utile, soprattutto negli ambienti di produzione, poter ottenere le informazioni di configurazione dalle variabili di ambiente, come mostrato negli esempi precedenti. Fare riferimento a una variabile di ambiente nei file docker-compose usando la sintassi \${MY\_VAR}. La riga seguente da un file docker compose.prod.yml mostra come fare riferimento al valore di una variabile di ambiente.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Le variabili di ambiente vengono create e inizializzate in modi diversi, a seconda dell'ambiente host (Linux, Windows, cluster basato su cloud e così via). Tuttavia, un approccio pratico consiste nell'usare un file con estensione env. I file docker-compose supportano la dichiarazione di variabili di ambiente predefinite nel file con estensione env. Questi valori per le variabili di ambiente sono i valori predefiniti. Possono tuttavia essere sostituiti dai valori eventualmente definiti in ciascun ambiente (variabili del sistema operativo host o di ambiente dal cluster). Inserire questo file con estensione env nella cartella da cui viene eseguito il comando docker-compose.

Nell'esempio seguente viene illustrato un file con estensione env, come il file [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) per l'applicazione eShopOnContainers.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Docker-compose prevede che il formato di ogni riga di un file con estensione env sia &lt;variabile&gt;=&lt;valore&gt;.

Si noti che i valori impostati nell'ambiente di runtime eseguono sempre l'override dei valori definiti all'interno del file con estensione env. Analogamente, anche i valori passati tramite gli argomenti del comando della riga di comando eseguono l'override dei valori predefiniti impostati nel file con estensione env.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Overview of Docker Compose**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/) (Panoramica di Docker Compose)

-   **Multiple Compose files**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files) (Più file Compose)

### <a name="building-optimized-aspnet-core-docker-images"></a>Creazione di immagini Docker ottimizzate con ASP.NET Core

Se si esplorano Docker e .NET Core sulle origini su Internet, si troveranno Dockerfile che illustrano la semplicità di creazione di un'immagine Docker copiando l'origine in un contenitore. Questi esempi suggeriscono che usando una configurazione semplice è possibile disporre di un'immagine Docker con l'ambiente fornito con l'applicazione. Nell'esempio seguente viene illustrato un Dockerfile semplice in questa ottica.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Un Dockerfile come questo funzionerà correttamente. Tuttavia è possibile ottimizzare in modo sostanziale le immagini, in particolare le immagini di produzione.

Nel modello basato su contenitori e microservizi si avviano costantemente contenitori. L'utilizzi tipico dei contenitori non comporta il riavvio di un contenitore in sospensione perché il contenitore è eliminabile. Gli agenti di orchestrazione, ad esempio Docker Swarm, Kubernetes, DCOS o Azure Service Fabric, creano semplicemente nuove istanze delle immagini. È quindi necessario ottimizzare precompilando l'applicazione quando viene compilata in modo che il processo di creazione dell'istanza sia più veloce. Quando viene avviato, il contenitore deve essere pronto per l'esecuzione. Non eseguire il ripristino e la compilazione in fase di esecuzione, usando i comandi dotnet restore e dotnet build dall'interfaccia della riga di comando dotnet, come indicato in molti post di blog su .NET Core e Docker.

Il team .NET sta lavorando intensamente per rendere .NET Core e ASP.NET Core un framework ottimizzato per i contenitori. .NET Core non è solo un framework leggero con un ingombro di memoria ridotto; il team si è concentrato sulle prestazioni di avvio e ha prodotto alcune immagini Docker ottimizzate, ad esempio [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) disponibile in [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), rispetto alle immagini regolari [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile). L'immagine [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) fornisce l'impostazione automatica di aspnetcore\_urls per la porta 80 e la cache pre-ngend degli assembly; entrambe le impostazioni consentono un avvio più rapido.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Building Optimized Docker Images with ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/) (Compilazione di immagini Docker ottimizzate con ASP.NET Core)

### <a name="building-the-application-from-a-build-ci-container"></a>Compilazione dell'applicazione da un contenitore (CI) di compilazione

Un altro vantaggio di Docker è che consente di compilare l'applicazione da un contenitore preconfigurato, come illustrato nella figura 8-13 senza la necessità di creare una VM o un computer di compilazione. È possibile usare o testare il contenitore di compilazione eseguendolo nel computer di sviluppo. L'aspetto ancora più interessante è tuttavia che è possibile usare lo stesso contenitore di compilazione dalla pipeline CI (Continuous Integration).

![](./media/image14.png)

**Figura 8-13**. Docker build-container per la compilazione di binari .NET 

Per questo scenario viene fornita l'immagine [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/), che è possibile usare per compilare e creare le app ASP.NET Core. L'output viene inserito in un'immagine basata sull'immagine [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), che è un'immagine di runtime ottimizzata, come indicato in precedenza.

L'immagine aspnetcore-build contiene tutto ciò che occorre per compilare un'applicazione ASP.NET Core, tra cui .NET Core, ASP.NET SDK, npm, Bower, Gulp e così via.

Queste dipendenze sono necessarie in fase di compilazione. Non si intende tuttavia mantenerle con l'applicazione in fase di esecuzione perché renderebbero l'immagine inutilmente grande. Nell'applicazione eShopOnContainers è possibile compilare l'applicazione da un contenitore semplicemente eseguendo il comando docker-compose seguente.

```
  docker-compose -f docker-compose.ci.build.yml up
```

La figura 8-14 mostra questo comando in esecuzione dalla riga di comando.

![](./media/image15.png)

**Figura 8-14.** Compilazione dell'applicazione .NET da un contenitore

Come si può notare, il contenitore in esecuzione è ci-build\_1. È basato sull'immagine aspnetcore-build ed è quindi possibile compilare e creare l'intera applicazione all'interno del contenitore, anziché dal PC. Questo è il motivo per cui in realtà si stanno creando e compilando i progetti .NET Core in Linux, perché quel contenitore è in esecuzione sull'host predefinito Linux Docker.

Il file [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) per questa immagine (parte di eShopOnContainers) contiene il codice seguente. Si noti che avvia un contenitore di compilazione usando l'immagine [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/).

```yml
version: '3'

services:

  ci-build:

    image: microsoft/aspnetcore-build:2.0

    volumes:
      - .:/src

    working_dir: /src

    command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && popd && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"

```

* A partire da **.NET Core 2.0**, il comando `dotnet restore` viene eseguito automaticamente quando viene eseguito il comando `dotnet publish`.

Dopo che il contenitore di compilazione è in esecuzione, vengono eseguiti i comandi dotnet restore e dotnet publish di .NET SDK su tutti i progetti nella soluzione per compilare i bit .NET. In questo caso, poiché eShopOnContainers include anche un'applicazione a pagina singola basata su TypeScript e Angular per il codice client, è necessario anche controllare le dipendenze JavaScript con npm, ma questa operazione non è correlata ai bit di .NET.

Il comando dotnet publish compila e pubblica l'output compilato all'interno della cartella di ogni progetto nella cartella ../obj/Docker/publish, come illustrato nella figura 8-15.

![](./media/image16.png)

**Figura 8-15.** File binari generati dal comando dotnet publish

#### <a name="creating-the-docker-images-from-the-cli"></a>Creazione di immagini Docker dall'interfaccia della riga di comando

Dopo che l'output dell'applicazione viene pubblicato nelle cartelle correlate (all'interno di ogni progetto), il passaggio successivo consiste nel creare effettivamente le immagini Docker. A tale scopo si usano i comandi docker-compose build e docker-compose up, come illustrato nella figura 8-16.

![](./media/image17.png)

**Figura 8-16.** Creazione di immagini Docker ed esecuzione di contenitori

Nella figura 8-17 è possibile esaminare come viene eseguito il comando docker-compose build.

![](./media/image18.png)

**Figura 8-17**. Creazione di immagini Docker con il comando docker-compose build

La differenza tra i comandi docker-compose build e docker-compose up è che il secondo crea e avvia le immagini.

Quando si usa Visual Studio, tutti questi passaggi vengono eseguiti dietro le quinte. Visual Studio compila l'applicazione .NET, crea le immagini Docker e distribuisce i contenitori nell'host Docker. Visual Studio offre funzionalità aggiuntive, come la possibilità di eseguire il debug dei contenitori in esecuzione in Docker direttamente da Visual Studio.

La conclusione generale è che è possibile compilare l'applicazione allo stesso modo in cui la compilerebbe la pipeline CI/CD, da un contenitore invece che da un computer locale. Dopo aver creato le immagini, è sufficiente eseguire le immagini Docker usando il comando docker-compose up.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)) (Compilazione di bit da un contenitore: impostazione della soluzione eShopOnContainers in un ambiente Windows CLI (dotnet CLI, Docker CLI e codice di Visual Studio), -Docker-CLI-e codice VS)


>[!div class="step-by-step"]
[Precedente](data-driven-crud-microservice.md)
[Successivo](database-server-container.md)
