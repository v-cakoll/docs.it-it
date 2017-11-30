---
title: Definizione dell'applicazione multi-contenitore con docker compose.yml
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Definizione dell'applicazione multi-contenitore con docker compose.yml
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Definizione dell'applicazione multi-contenitore con docker compose.yml 

In questa Guida, il [docker compose.yml](https://docs.docker.com/compose/compose-file/) file è stato introdotto nella sezione [passaggio 4. Definire i servizi in docker compose.yml quando si compila un'applicazione di multi-contenitore Docker](#step4_define_svcs_in_docker_compose_yml). Tuttavia, esistono altri modi per usare i file docker-compose sono è opportuno considerare in modo dettagliato.

Ad esempio, è possibile descrivere in modo esplicito come si desidera distribuire l'applicazione a più contenitori nel file compose.yml di docker. Facoltativamente, è possibile descrivere come si intende compilare le immagini Docker personalizzate. (Le immagini Docker personalizzato possono anche essere compilate con l'interfaccia CLI di Docker.)

In pratica, è possibile definire ognuno dei contenitori di cui che si desidera distribuire più determinate caratteristiche per la distribuzione di ogni contenitore. Dopo aver creato un file di descrizione del multi-contenitore di distribuzione, è possibile distribuire l'intera soluzione in un'unica azione orchestrata dal [docker comporre backup](https://docs.docker.com/compose/overview/) comando CLI, oppure è possibile distribuirlo in modo trasparente da Visual Studio. In caso contrario, è necessario utilizzare l'interfaccia CLI di Docker per distribuire dal contenitore in più passaggi tramite il comando docker run dalla riga di comando. Pertanto, ogni servizio definito in docker compose.yml deve specificare esattamente un'immagine o di compilazione. Le altre chiavi sono facoltativi e sono analoghi alle loro controparti della riga di comando di esecuzione di docker.

Il seguente codice YAML è la definizione di un file di possibili globale ma singolo docker-compose.yml per l'esempio eShopOnContainers. Questa operazione è il file effettivo docker-compose da eShopOnContainers. In alternativa, è una versione semplificata e consolidata in un singolo file, non è il miglior modo di lavorare con docker-comporre i file, come spiegato più avanti.

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

La chiave radice in questo file è di servizi. In tale chiave è definire i servizi che si desidera distribuire ed eseguire quando si esegue la composizione docker di comando oppure quando si distribuiscono da Visual Studio usando il file compose.yml di docker. In questo caso, il file di docker compose.yml ha più servizi definiti, come descritto nell'elenco seguente.

-   webmvc contenitore che include l'applicazione ASP.NET MVC di base che utilizza il microservizi dal lato server C\#

-   Catalog.API contenitore che include il microservizio catalogo ASP.NET Core Web API

-   Contenitore che include il microservizio ordinamento API Web di ASP.NET Core Ordering.API

-   Contenitore che esegue SQL Server per Linux, che contiene i database di microservizi SQL.Data

-   Basket.API contenitore con il microservizio Basket ASP.NET Core Web API

-   Basket.Data contenitore in esecuzione il servizio cache REDIS, con il database di acquisti come cache REDIS

### <a name="a-simple-web-service-api-container"></a>Un contenitore di API del servizio Web semplice

Porre l'attenzione su un singolo contenitore, il contenitore catalog.api-microservizio presenta una semplice definizione:

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
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

Questo servizio nei contenitori con la configurazione di base seguente:

-   È basato sull'immagine eshop/catalog.api personalizzato. Per semplicità, non è disponibile alcuna compilazione: l'impostazione nel file di chiave. Ciò significa che l'immagine devono essere stati creati in precedenza (con la compilazione docker) o sono stati scaricati (con il comando di docker pull) dal Registro di sistema qualsiasi Docker.

-   Definisce una variabile di ambiente denominata ConnectionString con la stringa di connessione da utilizzare da Entity Framework per accedere all'istanza di SQL Server che contiene il modello di dati del catalogo. In questo caso, lo stesso contenitore di SQL Server contiene più database. Pertanto, è necessario minore quantità di memoria nel computer di sviluppo per Docker. Tuttavia, è inoltre possibile distribuire un contenitore di SQL Server per ogni database microservizio.

-   Il nome di SQL Server è sql.data, ovvero lo stesso nome utilizzato per il contenitore in cui è in esecuzione l'istanza di SQL Server per Linux. Questa operazione è utile; è possibile utilizzare la risoluzione dei nomi (interna per l'host Docker) verrà risolto l'indirizzo di rete in modo che non è necessario conoscere l'indirizzo IP interno per i contenitori che si accede da altri contenitori.

Poiché la stringa di connessione è definita da una variabile di ambiente, è possibile impostare tale variabile tramite un meccanismo diverso e in un altro momento. Ad esempio, è possibile impostare una stringa di connessione diversi durante la distribuzione nell'ambiente di produzione in host finale, oppure dalle pipeline CI/CD-ROM in Visual Studio Team Services o il sistema DevOps preferito.

-   Espone la porta 80 per l'accesso interno per il servizio catalog.api all'interno dell'host Docker. L'host è attualmente una VM Linux perché si basa su un'immagine di Docker per Linux, ma è possibile configurare il contenitore eseguire su un'immagine di Windows.

-   Inoltra la porta 80 del contenitore su porta 5101 nel computer host Docker (la VM Linux) esposta.

-   Il servizio web fornisca un collegamento al servizio sql.data (l'istanza di SQL Server per il database di Linux in esecuzione in un contenitore). Quando si specifica questa dipendenza, il contenitore catalog.api non verrà avviato fino a quando non è già avviato il contenitore sql.data; prima di tutto questo è importante perché catalog.api deve contenere il database di SQL Server e in esecuzione. Tuttavia, questo tipo di contenitore dipendenza non è sufficiente in molti casi, perché Docker controlla solo a livello di contenitore. In alcuni casi il servizio (in questo caso SQL Server) potrebbe comunque non essere pronto, pertanto è consigliabile implementare la logica di ripetizione tentativi con backoff esponenziale in microservizi il client. In questo modo, se un contenitore di dipendenza non è pronto per un breve periodo di tempo, l'applicazione sarà comunque resiliente.

-   Si è configurato per consentire l'accesso a server esterni: aggiuntivo\_host impostazione consente di accedere a server esterni o i computer all'esterno dell'host Docker (vale a dire, compreso il valore predefinito di VM Linux che rappresenta uno sviluppo Docker host), ad esempio un database SQL locale Istanza del server del computer di sviluppo.

Esistono inoltre altre impostazioni di docker compose.yml più avanzate che verranno illustrati nelle sezioni seguenti.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Tramite docker-creare file in più ambienti di destinazione

I file di docker compose.yml sono file di definizione e possono essere utilizzati da più infrastrutture che utilizzano tale formato. Lo strumento più semplice è docker-comporre comando, ma altri strumenti come orchestrators (ad esempio, Docker Swarm) inoltre comprendere tale file.

Pertanto, tramite il comando è possibile utilizzare i seguenti scenari principali di docker-comporre.

#### <a name="development-environments"></a>Ambienti di sviluppo

Quando si sviluppano applicazioni, è importante essere in grado di eseguire un'applicazione in un ambiente di sviluppo isolato. È possibile utilizzare il comando CLI per creare tale ambiente oppure utilizzare Visual Studio che usa docker-comporre dietro le quinte docker-comporre.

Il file docker compose.yml consente di configurare e tutte le dipendenze dell'applicazione del servizio (altri servizi, cache, i database, code e così via) del documento. Utilizzando il comando CLI di docker-comporre, è possibile creare e avviare uno o più contenitori per ogni dipendenza con un unico comando (docker-costituiscono backup).

I file di docker compose.yml sono interpretati dal motore Docker i file di configurazione, ma anche fungere da file di documentazione pratico sulla composizione di un'applicazione multi-contenitore.

#### <a name="testing-environments"></a>Ambienti di test

Una parte importante di qualsiasi distribuzione continua (CD) o un processo di integrazione continua (CI) sono unit test e test di integrazione. Questi test automatizzati richiedono un ambiente isolato in modo che non sono interessate dagli utenti o qualsiasi altra differenza nei dati dell'applicazione.

Tramite Docker Compose si possono creare ed eliminare tale ambiente isolato in modo molto semplice in alcuni comandi dal prompt dei comandi o script, ad esempio i comandi seguenti:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>Distribuzioni di produzione

Per distribuire in un motore Docker remota, è possibile utilizzare anche Compose. Un caso tipico consiste nella distribuzione di una singola istanza di host Docker (ad esempio una macchina virtuale di produzione o di un server eseguito il provisioning con [Docker macchina](https://docs.docker.com/machine/overview/)). Ma potrebbe anche essere un intero [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, a causa di cluster sono inoltre compatibili con i file di docker compose.yml.

Se si utilizza orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes e così via), si potrebbe essere necessario aggiungere le impostazioni di configurazione di installazione e i metadati come quelle in docker compose.yml, ma nel formato richiesto da altro agente di orchestrazione.

In ogni caso, creare docker è un formato di metadati e lo strumento ideale per flussi di lavoro di sviluppo, test e produzione, anche se il flusso di lavoro di produzione può variare all'agente di orchestrazione in uso.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Utilizzo di più docker-comporre i file per la gestione di ambienti diversi

Se la destinazione ambienti diversi, è necessario utilizzare più comporre i file. Ciò consente di creare più varianti di configurazione a seconda dell'ambiente.

#### <a name="overriding-the-base-docker-compose-file"></a>Si esegue l'override del file base docker-compose

È possibile utilizzare un file singolo docker-compose.yml come illustrato negli esempi semplificati illustrato nelle sezioni precedenti. Tuttavia, non è consigliabile per la maggior parte delle applicazioni.

Per impostazione predefinita, composizione legge due file, un compose.yml di docker e un file docker-compose.override.yml facoltativo. Come illustrato nella figura 8-11, quando si utilizza Visual Studio e attivazione del supporto di Docker, Visual Studio crea anche i file e alcuni file aggiuntivi utilizzati per il debug.

![](./media/image12.png)

**Figura 8-11**. file in Visual Studio 2017 docker-comporre

È possibile modificare i file docker-compose con qualsiasi editor di codice di Visual Studio o Sublime ed eseguire l'applicazione con la composizione di docker comando di backup.

Per convenzione, il file di docker compose.yml contiene la configurazione di base e altre impostazioni statiche. Ciò significa che la configurazione del servizio non è necessario cambiare a seconda dell'ambiente di distribuzione di destinazione.

Il file di docker compose.override.yml, come suggerisce il nome, contiene le impostazioni di configurazione che eseguono l'override di configurazione di base, ad esempio di configurazione che varia a seconda dell'ambiente di distribuzione. Inoltre, è possibile avere più file di sostituzione con nomi diversi. I file di sostituzione in genere contengono informazioni aggiuntive necessarie per l'applicazione ma specifico in un ambiente o a una distribuzione.

#### <a name="targeting-multiple-environments"></a>Più ambienti di destinazione

Un caso di utilizzo tipico è quando si definiscono più costituiscono i file in modo è possibile associare più ambienti, ad esempio produzione, gestione temporanea, l'elemento di configurazione o di sviluppo. Per supportare queste differenze, è possibile suddividere la configurazione di composizione in più file, come illustrato nella figura 8-12.

![](./media/image13.png)

**Figura 8-12**. Docker-creare più file di override dei valori nel file di base di docker-compose.yml

Iniziare con il file di base-compose.yml di docker. Questo file di base deve contenere le impostazioni di configurazione di base o statico che non cambiano a seconda dell'ambiente. Ad esempio, il eShopOnContainers ha il seguente file docker compose.yml del file base.

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

Non modificare i valori nel file di base di docker-compose.yml a causa di ambienti di distribuzione di destinazione diverso.

Se si sta lavorando la definizione del servizio webmvc, ad esempio, è possibile visualizzare come tali informazioni sono molto simile all'indipendentemente da quale ambiente potrebbe essere destinando l'app. Sono le seguenti informazioni:

-   Il nome del servizio: webmvc.

-   Immagine personalizzata del contenitore: eshop/webmvc.

-   Il comando per compilare l'immagine personalizzata di Docker, che indica quale Dockerfile da utilizzare.

-   Dipendenze da altri servizi, in modo da questo contenitore non viene avviato fino a quando non sono stati avviati i contenitori di dipendenza.

È possibile avere una configurazione aggiuntiva, ma l'aspetto importante è che nel file di base-compose.yml di docker, si desidera impostare le informazioni che sono comuni a tutti gli ambienti. Docker compose.override.yml i file analoghi per la produzione o gestione temporanea, quindi è consigliabile inserire configurazione specifiche per ogni ambiente.

In genere, il compose.override.yml di docker viene usato per l'ambiente di sviluppo, come nell'esempio seguente da eShopOnContainers:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

In questo esempio, la configurazione della sostituzione sviluppo espone alcune porte all'host, definisce le variabili di ambiente con gli URL di reindirizzamento e specifica le stringhe di connessione per l'ambiente di sviluppo. Queste impostazioni sono tutte solo per l'ambiente di sviluppo.

Quando si esegue comporre docker backup oppure avviarlo da Visual Studio, il comando legge le sostituzioni automaticamente come se sono stati l'unione di entrambi i file.

Si supponga che un altro file di composizione per l'ambiente di produzione, con valori di configurazione diverso. È possibile creare un altro file di sostituzione, simile al seguente. (Questo file potrebbe essere archiviato in un repository Git diversi o gestito e protetto da un team diverso.)

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Come distribuire un file di override specifico

Per usare più file di sostituzione o di un file di sostituzione con un nome diverso, è possibile utilizzare l'opzione -f con il comando di docker-comporre e specificare i file. Comporre unisce i file nell'ordine in che cui vengono specificati nella riga di comando. Nell'esempio seguente viene illustrato come distribuire i file di sostituzione.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Utilizzo di variabili di ambiente in docker-composizione file

È utile, soprattutto in ambienti di produzione, per essere in grado di ottenere informazioni di configurazione dalle variabili di ambiente, come negli esempi precedenti è stato illustrato. Una variabile di ambiente si fa riferimento nei file docker-compose utilizzando la sintassi \${MY\_VAR}. La riga seguente da un file docker compose.prod.yml viene illustrato come fare riferimento al valore di una variabile di ambiente.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Le variabili di ambiente vengono create e inizializzate in modi diversi, a seconda dell'ambiente host (Linux, Windows, il cluster di Cloud, ecc.). Tuttavia, un approccio pratico consiste nell'utilizzare un file .env. I file docker-compose supportano la dichiarazione di variabili di ambiente predefinite nel file .env. Questi valori per le variabili di ambiente sono i valori predefiniti. Ma possono essere sostituite dai valori che sia stata definita in ognuno degli ambienti (sistema operativo host o le variabili di ambiente dal cluster). Inserire questo file .env nella cartella in cui la composizione docker comando viene eseguito da.

Nell'esempio seguente viene illustrato un file di .env come il [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file per l'applicazione eShopOnContainers.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Comporre docker prevede che ogni riga in un file nel formato .env &lt;variabile&gt;=&lt;valore&gt;.

Si noti che i valori impostati nell'ambiente di runtime sempre eseguire l'override di valori definiti all'interno del file .env. In modo analogo, i valori passati tramite gli argomenti della riga di comando comando inoltre sostituiscano i valori predefiniti impostati nel file .env.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Panoramica di Docker comporre**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **Più file di composizione**
    [*https://docs.docker.com/compose/extends/\#file comporre più*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Creazione di immagini di ASP.NET Core Docker ottimizzate

Se si Esplora Docker e .NET Core su origini su Internet, si noterà Dockerfile che illustrano la semplicità di creazione di un'immagine Docker copiando l'origine in un contenitore. Questi esempi è consigliabile che utilizza una configurazione semplice, è possibile creare un'immagine di Docker con l'ambiente incluso nel pacchetto dell'applicazione. Nell'esempio seguente viene illustrato un semplice Dockerfile in questo vein.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Un Dockerfile questo funzionerà. Tuttavia, è possibile ottimizzare sostanzialmente le immagini, in particolare le immagini di produzione.

In un contenitore e il modello di microservizi, viene avviato costantemente contenitori. L'utilizzo tipico di contenitori non viene riavviato un contenitore di sospensione, perché il contenitore è eliminabile. Orchestrators (ad esempio, Docker Swarm, Kubernetes, DCOS o Azure Service Fabric) è sufficiente creare nuove istanze delle immagini. Ciò significa che è necessario ottimizzare la precompilazione dell'applicazione quando viene generata in modo che il processo di creazione dell'istanza sia più veloce. Quando viene avviato il contenitore, deve essere pronto per l'esecuzione. Non ripristinare e compilare in fase di esecuzione, utilizzando dotnet dotnet e ripristino compilare comandi dotnet CLI che, come illustrato nella molti post di blog su .NET Core e Docker.

Il team di .NET è stato operazioni importanti per rendere un framework ottimizzato per il contenitore di .NET Core e ASP.NET Core. Non solo è .NET Core un framework semplice con un footprint di memoria di piccole dimensioni; il team ha con stato attivo sulle prestazioni di avvio e prodotti alcune immagini Docker ottimizzati, ad esempio il [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) immagine disponibile all'indirizzo [Hub Docker](https://hub.docker.com/r/microsoft/aspnetcore/), rispetto alle normali [ Microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) immagini. Il [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) immagine fornisce l'impostazione automatica di aspnetcore\_URL per la porta 80 e la cache di pre-ngend degli assembly; entrambe le impostazioni comportare un avvio più rapido.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Creazione di immagini di Docker con ASP.NET Core ottimizzate**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>Compilazione dell'applicazione da un contenitore di compilazione (CI)

Un altro vantaggio di Docker è possibile compilare l'applicazione da un contenitore preconfigurato, come illustrato nella figura 8-13, pertanto non è necessario creare un computer di compilazione o di una macchina virtuale per compilare l'applicazione. È possibile utilizzare o di test compilazione contenitore eseguendolo in computer di sviluppo. Ma l'aspetto ancora più interessante è che è possibile utilizzare lo stesso contenitore di compilazione da pipeline dell'elemento di configurazione (integrazione continua).

![](./media/image14.png)

**Figura 8-13**. Compilazione di bit di .NET da un contenitore di componenti

Per questo scenario, si forniscono le [aspnetcore/microsoft-compilazione](https://hub.docker.com/r/microsoft/aspnetcore-build/) immagine, è possibile utilizzare per compilare e ottenere il ASP.NET Core app. In un'immagine in base a cui viene inserito l'output di [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) immagine, che è un'immagine ottimizzata di runtime, come evidenziata in precedenza.

L'immagine aspnetcore compilazione contiene tutto ciò che occorre per compilare un'applicazione ASP.NET di base, tra cui .NET Core, il SDK di ASP.NET, npm, Bower, Gulp e così via.

Abbiamo bisogno di queste dipendenze in fase di compilazione. Ma si desidera eseguire con l'applicazione in fase di esecuzione perché renderebbe l'immagine inutilmente grandi. Nell'applicazione eShopOnContainers, è possibile compilare l'applicazione da un contenitore solo eseguendo le operazioni seguenti docker-compongono comando.

```
  docker-compose -f docker-compose.ci.build.yml up
```

Figura 8-14 mostra questo comando in esecuzione dalla riga di comando.

![](./media/image15.png)

**Figura 8-14.** Compilazione dell'applicazione .NET da un contenitore

Come si può notare, il contenitore in cui è in esecuzione è la compilazione di ci\_1 contenitore. Questa è basata sull'immagine di aspnetcore compilazione in modo che è possibile compilare e ottenere l'intera applicazione all'interno del contenitore invece che dal PC. Vale a dire perché in realtà è la creazione e la compilazione di progetti .NET Core in Linux, perché tale contenitore è in esecuzione nell'host Docker Linux predefinito.

Il [docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file di immagine (parte di eShopOnContainers) contiene il codice seguente. Si noterà che avvia un contenitore di compilazione usando il [aspnetcore/microsoft-compilazione](https://hub.docker.com/r/microsoft/aspnetcore-build/) immagine.

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* A partire da **2.0 di .NET Core**, `dotnet restore` comando viene eseguita automaticamente quando il `dotnet publish` comando viene eseguito.

Una volta installato e in esecuzione il contenitore della build, viene eseguito il ripristino dotnet .NET SDK e dotnet pubblicare comandi su tutti i progetti nella soluzione per compilare i bit di .NET. In questo caso, poiché eShopOnContainers ha anche un SPA basato su TypeScript e angolare per il codice client, è anche necessario controllare le dipendenze di JavaScript con npm, ma tale operazione non è correlato ai bit di .NET.

Il dotnet pubblicare le compilazioni di comando e pubblica l'output compilato nella cartella di ogni progetto per il... cartella /obj/Docker/Publish, come illustrato nella figura 8-15.

![](./media/image16.png)

**Figura 8-15.** Comando pubblicano i file binari generati dal dotnet

#### <a name="creating-the-docker-images-from-the-cli"></a>Creazione di immagini Docker da CLI

Dopo aver pubblicato l'output dell'applicazione per le cartelle correlate (all'interno di ogni progetto), il passaggio successivo consiste nel compilare effettivamente le immagini Docker. A tale scopo, si utilizza la compilazione di docker-compose e docker-comporre i comandi, come illustrato nella figura 8-16.

![](./media/image17.png)

**Nella figura 8-16.** Creazione di immagini Docker e i contenitori in esecuzione

Nella figura 8-17, è possibile vedere come il docker-compose creare l'esecuzione del comando.

![](./media/image18.png)

**Figura 8-17**. Le immagini Docker con la compilazione con docker-creare il comando di compilazione

La differenza tra il docker-compose compilare e comporre docker dei comandi è che compongono docker le compilazioni e le immagini di avvio.

Quando si utilizza Visual Studio, tutti questi passaggi vengono eseguiti dietro le quinte. Visual Studio compila l'applicazione .NET, crea le immagini Docker e consente di distribuire i contenitori nell'host Docker. Visual Studio offre funzionalità aggiuntive, ad esempio la possibilità di eseguire il debug ai contenitori in esecuzione in Docker, direttamente da Visual Studio.

Qui il takeway generale è che si è in grado di compilare la stessa modalità della pipeline dell'elemento di configurazione/CD deve compilare l'applicazione, ovvero da un contenitore invece che da un computer locale. Dopo aver create le immagini di, quindi è sufficiente eseguire le immagini Docker usando docker-comporre il comando.

#### <a name="additional-resources"></a>Risorse aggiuntive

-   **Compilazione di bit da un contenitore: configurazione della soluzione eShopOnContainers in un ambiente Windows CLI (dotnet CLI, Docker CLI e il codice di Visual Studio)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-up-in-a-Windows-CLI-Environment-(dotnet-CLI,-Docker-CLI-and-VS-code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[Precedente] (data-driven-crud-microservice.md) [Avanti] (container.md-server-database)
