---
title: Definizione dell'applicazione a più contenitori con docker-compose.yml
description: Architettura di microservizi .NET per le applicazioni nei contenitori .NET | Definizione dell'applicazione a più contenitori con docker-compose.yml
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.openlocfilehash: ded2e5399938be25005776963b0310b6a49d0353
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="dcb30-103">Definizione dell'applicazione a più contenitori con docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="dcb30-103">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="dcb30-104">Il file [docker-compose.yml](https://docs.docker.com/compose/compose-file/) è stato introdotto nella sezione [Passaggio 4 di questa guida. Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori](#step4_define_svcs_in_docker_compose_yml).</span><span class="sxs-lookup"><span data-stu-id="dcb30-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="dcb30-105">Tuttavia esistono altri modi per usare i file docker-compose che vale la pena di esplorare in maggiore dettaglio.</span><span class="sxs-lookup"><span data-stu-id="dcb30-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="dcb30-106">È possibile, ad esempio, descrivere in modo esplicito la modalità di distribuzione dell'applicazione a più contenitori nel file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="dcb30-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="dcb30-107">Facoltativamente è possibile anche descrivere come si intende compilare le immagini Docker personalizzate.</span><span class="sxs-lookup"><span data-stu-id="dcb30-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="dcb30-108">Le immagini Docker personalizzate possono essere compilate anche con l'interfaccia della riga di comando di Docker.</span><span class="sxs-lookup"><span data-stu-id="dcb30-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="dcb30-109">In pratica è possibile definire ciascun contenitore da distribuire, più determinate caratteristiche per ogni distribuzione di contenitore.</span><span class="sxs-lookup"><span data-stu-id="dcb30-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="dcb30-110">Dopo aver creato un file di descrizione della distribuzione di più contenitori, è possibile distribuire l'intera soluzione con un'unica azione orchestrata dal comando dell'interfaccia della riga di comando [docker-compose up](https://docs.docker.com/compose/overview/) oppure in modo trasparente da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dcb30-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="dcb30-111">In caso contrario, sarebbe necessario usare l'interfaccia della riga di comando di Docker per eseguire la distribuzione contenitore per contenitore in più passaggi usando il comando docker run dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dcb30-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="dcb30-112">Pertanto ogni servizio definito in docker-compose.yml deve specificare esattamente un'immagine o una build.</span><span class="sxs-lookup"><span data-stu-id="dcb30-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="dcb30-113">Le altre chiavi sono facoltative e sono analoghe alle controparti della riga di comando docker run.</span><span class="sxs-lookup"><span data-stu-id="dcb30-113">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="dcb30-114">Il seguente codice YAML definisce un possibile file docker-compose.yml globale, ma unico per l'esempio eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="dcb30-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="dcb30-115">Non si tratta del file docker-compose reale di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="dcb30-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="dcb30-116">È invece una versione semplificata e consolidata in un singolo file, ma non è il modo migliore per lavorare con i file docker-compose, come sarà illustrato in seguito.</span><span class="sxs-lookup"><span data-stu-id="dcb30-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

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

<span data-ttu-id="dcb30-117">La chiave radice in questo file sono i servizi.</span><span class="sxs-lookup"><span data-stu-id="dcb30-117">The root key in this file is services.</span></span> <span data-ttu-id="dcb30-118">Sotto questa chiave si definiscono i servizi che si vuole distribuire ed eseguire quando si esegue il comando docker-compose up o quando si esegue la distribuzione da Visual Studio usando questo file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="dcb30-118">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="dcb30-119">In questo caso, nel file docker compose.yml sono stati definiti più servizi, come descritto nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="dcb30-120">webmvc Contenitore che include l'applicazione ASP.NET Core MVC che usa i microservizi da C\# sul lato server</span><span class="sxs-lookup"><span data-stu-id="dcb30-120">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="dcb30-121">catalog.api Contenitore che include il microservizio API Web ASP.NET Core che gestisce i cataloghi</span><span class="sxs-lookup"><span data-stu-id="dcb30-121">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="dcb30-122">ordering.api Contenitore che include il microservizio API Web ASP.NET Core che gestisce gli ordini</span><span class="sxs-lookup"><span data-stu-id="dcb30-122">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="dcb30-123">sql.data Contenitore che esegue SQL Server per Linux, contenente i database di microservizi</span><span class="sxs-lookup"><span data-stu-id="dcb30-123">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="dcb30-124">basket.API Contenitore con il microservizio API Web ASP.NET Core che gestisce i carrelli</span><span class="sxs-lookup"><span data-stu-id="dcb30-124">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="dcb30-125">basket.data Contenitore che esegue il servizio cache REDIS, con il database dei carrelli come cache REDIS</span><span class="sxs-lookup"><span data-stu-id="dcb30-125">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="dcb30-126">Un semplice contenitore di API di servizi Web</span><span class="sxs-lookup"><span data-stu-id="dcb30-126">A simple Web Service API container</span></span>

<span data-ttu-id="dcb30-127">Concentrandosi su un singolo contenitore, la definizione del microservizio contenitore catalog.api è semplice:</span><span class="sxs-lookup"><span data-stu-id="dcb30-127">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

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

<span data-ttu-id="dcb30-128">La configurazione base di questo servizio con contenitore è la seguente:</span><span class="sxs-lookup"><span data-stu-id="dcb30-128">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="dcb30-129">Si basa sull'immagine eshop/catalog.api personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dcb30-129">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="dcb30-130">Per semplicità non esiste un'impostazione chiave build: nel file.</span><span class="sxs-lookup"><span data-stu-id="dcb30-130">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="dcb30-131">Ciò significa che l'immagine deve essere stata compilata in precedenza (con docker build) oppure è stata scaricata (con il comando docker pull) da un registro Docker.</span><span class="sxs-lookup"><span data-stu-id="dcb30-131">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="dcb30-132">Definisce una variabile di ambiente denominata ConnectionString con la stringa di connessione che Entity Framework deve usare per accedere all'istanza di SQL Server contenente il modello di dati di catalogo.</span><span class="sxs-lookup"><span data-stu-id="dcb30-132">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="dcb30-133">In questo caso, lo stesso contenitore SQL Server contiene più database.</span><span class="sxs-lookup"><span data-stu-id="dcb30-133">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="dcb30-134">Pertanto la memoria necessaria nel computer di sviluppo per Docker è inferiore.</span><span class="sxs-lookup"><span data-stu-id="dcb30-134">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="dcb30-135">Tuttavia è possibile anche distribuire un contenitore SQL Server per ogni database di microservizi.</span><span class="sxs-lookup"><span data-stu-id="dcb30-135">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="dcb30-136">Il nome SQL Server è sql.data, ovvero lo stesso nome usato per il contenitore in cui è in esecuzione l'istanza di SQL Server per Linux.</span><span class="sxs-lookup"><span data-stu-id="dcb30-136">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="dcb30-137">Questo approccio è vantaggioso perché la possibilità di usare questa risoluzione di nomi (interna all'host Docker) risolverà l'indirizzo di rete e non è quindi necessario conoscere l'IP interno per i contenitori a cui si sta accedendo da altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="dcb30-137">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="dcb30-138">Poiché la stringa di connessione viene definita da una variabile di ambiente, è possibile impostare questa variabile tramite un meccanismo diverso e in un momento diverso.</span><span class="sxs-lookup"><span data-stu-id="dcb30-138">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="dcb30-139">Ad esempio, è possibile impostare una stringa di connessione diversa durante la distribuzione in produzione negli host finali oppure dalle pipeline CI/CD in VSTS o dal sistema DevOps preferito.</span><span class="sxs-lookup"><span data-stu-id="dcb30-139">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="dcb30-140">Espone la porta 80 per l'accesso interno al servizio catalog.api all'interno dell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="dcb30-140">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="dcb30-141">L'host è attualmente una VM Linux perché si basa su un'immagine Docker per Linux, ma è possibile configurare il contenitore per l'esecuzione su un'immagine per Windows.</span><span class="sxs-lookup"><span data-stu-id="dcb30-141">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="dcb30-142">Inoltra la porta 80 esposta sul contenitore alla porta esterna 5101 sul computer host Docker (la VM Linux).</span><span class="sxs-lookup"><span data-stu-id="dcb30-142">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="dcb30-143">Collega il servizio Web al servizio sql.data, ossia l'istanza di SQL Server per il database Linux in esecuzione in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="dcb30-143">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="dcb30-144">Quando si specifica questa dipendenza, il contenitore catalog.api verrà avviato solo dopo l'avvio del contenitore sql.data; questo aspetto è importante perché per catalog.api è necessario che prima sia in esecuzione il database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="dcb30-144">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="dcb30-145">Tuttavia, questo tipo di dipendenza di contenitore non è sufficiente in molti casi poiché Docker esegue il controllo solo a livello di contenitore.</span><span class="sxs-lookup"><span data-stu-id="dcb30-145">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="dcb30-146">In alcuni casi il servizio, in questo caso SQL Server, potrebbe non essere ancora pronto ed è quindi consigliabile implementare la logica di ripetizione con il backoff esponenziale nei microservizi client.</span><span class="sxs-lookup"><span data-stu-id="dcb30-146">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="dcb30-147">In questo modo, se un contenitore di dipendenza non è pronto per un breve periodo di tempo, l'applicazione sarà ancora resiliente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-147">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="dcb30-148">Viene configurata per consentire l'accesso ai server esterni: l'impostazione extra\_hosts consente di accedere ai server esterni o ai computer all'esterno dell'host Docker (quindi all'esterno della VM predefinita che è un host Docker di sviluppo), ad esempio un'istanza locale di SQL Server sul PC di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dcb30-148">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="dcb30-149">Altre impostazioni più avanzate del file docker-compose.yml verranno illustrate nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="dcb30-149">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="dcb30-150">Utilizzo dei file docker-compose per usare più ambienti come destinazione</span><span class="sxs-lookup"><span data-stu-id="dcb30-150">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="dcb30-151">I file docker-compose.yml sono file di definizione e possono essere usati da più infrastrutture compatibili con questo formato.</span><span class="sxs-lookup"><span data-stu-id="dcb30-151">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="dcb30-152">Lo strumento più semplice è il comando docker-compose, ma anche altri strumenti come gli agenti di orchestrazione, ad esempio Docker Swarm, sono compatibili con questo file.</span><span class="sxs-lookup"><span data-stu-id="dcb30-152">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="dcb30-153">Con il comando docker-compose è quindi possibile usare come destinazione i seguenti scenari principali.</span><span class="sxs-lookup"><span data-stu-id="dcb30-153">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="dcb30-154">Ambienti di sviluppo</span><span class="sxs-lookup"><span data-stu-id="dcb30-154">Development environments</span></span>

<span data-ttu-id="dcb30-155">Quando si sviluppano applicazioni, è importante poter eseguire un'applicazione in un ambiente di sviluppo isolato.</span><span class="sxs-lookup"><span data-stu-id="dcb30-155">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="dcb30-156">È possibile usare il comando dell'interfaccia della riga di comando docker-compose per creare questo ambiente oppure usare Visual Studio che esegue docker-compose in background.</span><span class="sxs-lookup"><span data-stu-id="dcb30-156">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="dcb30-157">Il file docker-compose.yml consente di configurare e documentare tutte le dipendenze di servizio dell'applicazione,come altri servizi, cache, database, code e così via.</span><span class="sxs-lookup"><span data-stu-id="dcb30-157">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="dcb30-158">Con il comando dell'interfaccia della riga di comando docker-compose è possibile creare e avviare uno o più contenitori per ogni dipendenza con un unico comando (docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="dcb30-158">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="dcb30-159">I file docker-compose.yml sono file di configurazione interpretati dal motore Docker, ma servono anche come utili file di documentazione sulla composizione dell'applicazione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="dcb30-159">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="dcb30-160">Ambienti di test</span><span class="sxs-lookup"><span data-stu-id="dcb30-160">Testing environments</span></span>

<span data-ttu-id="dcb30-161">Un aspetto importante di qualsiasi processo di distribuzione continua (CD) o di integrazione continua (CI) sono gli unit test e i test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-161">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="dcb30-162">Questi test automatizzati richiedono un ambiente isolato per evitare impatti da parte degli utenti o di eventuali altre modifiche nei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-162">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="dcb30-163">Con Docker Compose è possibile creare ed eliminare definitivamente l'ambiente isolato molto facilmente usando alcuni comandi al prompt dei comandi o script, come i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="dcb30-163">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="dcb30-164">Distribuzioni in produzione</span><span class="sxs-lookup"><span data-stu-id="dcb30-164">Production deployments</span></span>

<span data-ttu-id="dcb30-165">È possibile anche usare Docker Compose per eseguire la distribuzione in un motore Docker remoto.</span><span class="sxs-lookup"><span data-stu-id="dcb30-165">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="dcb30-166">Un caso tipico consiste nella distribuzione di una singola istanza dell'host Docker, ad esempio una macchina virtuale in produzione o un server di cui viene eseguito il provisioning con [Docker Machine](https://docs.docker.com/machine/overview/).</span><span class="sxs-lookup"><span data-stu-id="dcb30-166">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="dcb30-167">Potrebbe anche essere un intero cluster [Docker Swarm](https://docs.docker.com/swarm/overview/) perché anche i cluster sono compatibili con i file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="dcb30-167">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="dcb30-168">Se si usa qualsiasi altro agente di orchestrazione (Microsoft Azure Service Fabric, Mesos DC/OS, Kubernetes, ecc.), potrebbe essere necessario aggiungere impostazioni di installazione e configurazione dei metadati, come quelle in docker-compose.yml, ma nel formato richiesto dall'altro agente di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-168">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="dcb30-169">In ogni caso, docker-compose è un utile strumento e formato di metadati per lo sviluppo, i test e i flussi di lavoro di produzione, anche se il flusso di lavoro di produzione potrebbe variare in base all'agente di orchestrazione in uso.</span><span class="sxs-lookup"><span data-stu-id="dcb30-169">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="dcb30-170">Utilizzo di più file docker-compose per la gestione di ambienti diversi</span><span class="sxs-lookup"><span data-stu-id="dcb30-170">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="dcb30-171">Se si usano come destinazione ambienti diversi, è necessario usare più file compose.</span><span class="sxs-lookup"><span data-stu-id="dcb30-171">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="dcb30-172">In questo modo è possibile creare più varianti di configurazione a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-172">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="dcb30-173">Override del file docker-compose base</span><span class="sxs-lookup"><span data-stu-id="dcb30-173">Overriding the base docker-compose file</span></span>

<span data-ttu-id="dcb30-174">È possibile usare un singolo file docker-compose.yml, come negli esempi semplificati illustrati nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="dcb30-174">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="dcb30-175">Tuttavia questo approccio non è consigliabile per la maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="dcb30-175">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="dcb30-176">Per impostazione predefinita, Compose legge due file: docker-compose.yml e un file docker-compose.override.yml facoltativo.</span><span class="sxs-lookup"><span data-stu-id="dcb30-176">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="dcb30-177">Come illustrato nella figura 8-11, quando si usa Visual Studio e si abilita il supporto di Docker, Visual Studio crea anche un file docker-compose.ci.build.yml aggiuntivo da usare dalle pipeline CI/CD come in VSTS.</span><span class="sxs-lookup"><span data-stu-id="dcb30-177">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.ci.build,yml file for you to use from your CI/CD pipelines like in VSTS.</span></span>

![](./media/image12.png)

<span data-ttu-id="dcb30-178">**Figura 8-11**.</span><span class="sxs-lookup"><span data-stu-id="dcb30-178">**Figure 8-11**.</span></span> <span data-ttu-id="dcb30-179">File docker-compose in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="dcb30-179">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="dcb30-180">È possibile modificare i file docker-compose con qualsiasi editor di codice di Visual Studio o Sublime ed eseguire l'applicazione con il comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="dcb30-180">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="dcb30-181">Per convenzione, il file docker-compose.yml contiene la configurazione base e altre impostazioni statiche.</span><span class="sxs-lookup"><span data-stu-id="dcb30-181">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="dcb30-182">Ciò significa che la configurazione del servizio non deve cambiare a seconda dell'ambiente di distribuzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-182">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="dcb30-183">Il file docker-compose.override.yml, come suggerisce il nome, contiene le impostazioni di configurazione che eseguono l'override della configurazione base, ad esempio la configurazione che dipende dall'ambiente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-183">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="dcb30-184">È possibile anche avere più file di override con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="dcb30-184">You can have multiple override files with different names also.</span></span> <span data-ttu-id="dcb30-185">I file di override in genere contengono informazioni aggiuntive necessarie per l'applicazione, ma specifiche per un ambiente o una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-185">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="dcb30-186">Utilizzo di più ambienti come destinazione</span><span class="sxs-lookup"><span data-stu-id="dcb30-186">Targeting multiple environments</span></span>

<span data-ttu-id="dcb30-187">Un tipico caso d'uso è quello in cui si definiscono più file compose in modo da poter usare come destinazione più ambienti, ad esempio quello di produzione, staging, CI o sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dcb30-187">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="dcb30-188">Per supportare queste differenze, è possibile dividere la configurazione di Compose in più file, come illustrato nella figura 8-12.</span><span class="sxs-lookup"><span data-stu-id="dcb30-188">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="dcb30-189">**Figura 8-12**.</span><span class="sxs-lookup"><span data-stu-id="dcb30-189">**Figure 8-12**.</span></span> <span data-ttu-id="dcb30-190">Più file docker-compose che eseguono l'override di valori del file docker-compose.yml base</span><span class="sxs-lookup"><span data-stu-id="dcb30-190">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="dcb30-191">Iniziare con il file docker-compose.yml base.</span><span class="sxs-lookup"><span data-stu-id="dcb30-191">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="dcb30-192">Questo file base deve contenere le impostazioni di configurazione base o statiche, ossia che non cambiano in base all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-192">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="dcb30-193">Ad esempio, il file base di eShopOnContainers è il file docker-compose.yml seguente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-193">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

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

<span data-ttu-id="dcb30-194">I valori nel file docker-compose.yml base non devono essere modificati in base ai diversi ambienti di distribuzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-194">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="dcb30-195">Se, ad esempio, si esamina con attenzione la definizione del servizio webmvc, si nota come queste informazioni sono più o meno le stesse indipendentemente dall'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-195">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="dcb30-196">Sono disponibili le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="dcb30-196">You have the following information:</span></span>

-   <span data-ttu-id="dcb30-197">Il nome del servizio: webmvc.</span><span class="sxs-lookup"><span data-stu-id="dcb30-197">The service name: webmvc.</span></span>

-   <span data-ttu-id="dcb30-198">L'immagine personalizzata del contenitore: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="dcb30-198">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="dcb30-199">Il comando per compilare l'immagine personalizzata di Docker, che indica il Dockerfile da usare.</span><span class="sxs-lookup"><span data-stu-id="dcb30-199">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="dcb30-200">Le dipendenze da altri servizi, per cui questo contenitore viene avviato solo dopo che sono stati avviati gli altri contenitori di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="dcb30-200">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="dcb30-201">È possibile avere una configurazione aggiuntiva, ma il punto importante è che nel file docker-compose.yml base si impostano solo le informazioni comuni tra gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="dcb30-201">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="dcb30-202">Nel file docker-compose.override.yml o nei file simili per la produzione o lo staging si inserisce la configurazione specifica per ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-202">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="dcb30-203">In genere, il file docker-compose.override.yml viene usato per l'ambiente di sviluppo, come nell'esempio seguente dall'applicazione eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="dcb30-203">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

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

<span data-ttu-id="dcb30-204">In questo esempio, la configurazione di override dello sviluppo espone alcune porte all'host, definisce le variabili di ambiente con gli URL di reindirizzamento e specifica le stringhe di connessione per l'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dcb30-204">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="dcb30-205">Queste impostazioni sono tutte relative solo all'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dcb30-205">These settings are all just for the development environment.</span></span>

<span data-ttu-id="dcb30-206">Quando si esegue `docker-compose up` o lo si avvia da Visual Studio, il comando legge automaticamente le sostituzioni come se stesse unendo entrambi i file.</span><span class="sxs-lookup"><span data-stu-id="dcb30-206">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="dcb30-207">Si supponga di voler creare un altro file Compose per l'ambiente di produzione, con diversi valori di configurazione, porte o stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-207">Suppose that you want another Compose file for the production environment, with different configuration values, ports or connection strings.</span></span> <span data-ttu-id="dcb30-208">È possibile creare un altro file di override, ad esempio un file denominato `docker-compose.prod.yml` con diverse impostazioni e variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-208">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span>  <span data-ttu-id="dcb30-209">Questo file potrebbe essere archiviato in un diverso repository Git oppure gestito e protetto da un team diverso.</span><span class="sxs-lookup"><span data-stu-id="dcb30-209">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="dcb30-210">Come distribuire un file di override specifico</span><span class="sxs-lookup"><span data-stu-id="dcb30-210">How to deploy with a specific override file</span></span>

<span data-ttu-id="dcb30-211">Per usare più file di override o un file di override con un nome diverso, è possibile usare l'opzione -f con il comando docker-compose e specificare i file.</span><span class="sxs-lookup"><span data-stu-id="dcb30-211">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="dcb30-212">Compose unisce i file nell'ordine in che cui vengono specificati alla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dcb30-212">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="dcb30-213">Nell'esempio seguente viene illustrato come eseguire la distribuzione con i file di override.</span><span class="sxs-lookup"><span data-stu-id="dcb30-213">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="dcb30-214">Utilizzo di variabili di ambiente nei file docker-compose</span><span class="sxs-lookup"><span data-stu-id="dcb30-214">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="dcb30-215">È utile, soprattutto negli ambienti di produzione, poter ottenere le informazioni di configurazione dalle variabili di ambiente, come mostrato negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="dcb30-215">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="dcb30-216">Fare riferimento a una variabile di ambiente nei file docker-compose usando la sintassi \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="dcb30-216">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="dcb30-217">La riga seguente da un file docker compose.prod.yml mostra come fare riferimento al valore di una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-217">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="dcb30-218">Le variabili di ambiente vengono create e inizializzate in modi diversi, a seconda dell'ambiente host (Linux, Windows, cluster basato su cloud e così via).</span><span class="sxs-lookup"><span data-stu-id="dcb30-218">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="dcb30-219">Tuttavia, un approccio pratico consiste nell'usare un file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="dcb30-219">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="dcb30-220">I file docker-compose supportano la dichiarazione di variabili di ambiente predefinite nel file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="dcb30-220">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="dcb30-221">Questi valori per le variabili di ambiente sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="dcb30-221">These values for the environment variables are the default values.</span></span> <span data-ttu-id="dcb30-222">Possono tuttavia essere sostituiti dai valori eventualmente definiti in ciascun ambiente (variabili del sistema operativo host o di ambiente dal cluster).</span><span class="sxs-lookup"><span data-stu-id="dcb30-222">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="dcb30-223">Inserire questo file con estensione env nella cartella da cui viene eseguito il comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="dcb30-223">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="dcb30-224">Nell'esempio seguente viene illustrato un file con estensione env, come il file [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) per l'applicazione eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="dcb30-224">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="dcb30-225">Docker-compose prevede che il formato di ogni riga di un file con estensione env sia &lt;variabile&gt;=&lt;valore&gt;.</span><span class="sxs-lookup"><span data-stu-id="dcb30-225">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="dcb30-226">Si noti che i valori impostati nell'ambiente di runtime eseguono sempre l'override dei valori definiti all'interno del file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="dcb30-226">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="dcb30-227">Analogamente, anche i valori passati tramite gli argomenti del comando della riga di comando eseguono l'override dei valori predefiniti impostati nel file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="dcb30-227">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="dcb30-228">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dcb30-228">Additional resources</span></span>

-   <span data-ttu-id="dcb30-229">**Overview of Docker Compose**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/) (Panoramica di Docker Compose)</span><span class="sxs-lookup"><span data-stu-id="dcb30-229">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="dcb30-230">**Multiple Compose files**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files) (Più file Compose)</span><span class="sxs-lookup"><span data-stu-id="dcb30-230">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="dcb30-231">Creazione di immagini Docker ottimizzate con ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="dcb30-231">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="dcb30-232">Se si esplorano Docker e .NET Core sulle origini su Internet, si troveranno Dockerfile che illustrano la semplicità di creazione di un'immagine Docker copiando l'origine in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="dcb30-232">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="dcb30-233">Questi esempi suggeriscono che usando una configurazione semplice è possibile disporre di un'immagine Docker con l'ambiente fornito con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-233">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="dcb30-234">Nell'esempio seguente viene illustrato un Dockerfile semplice in questa ottica.</span><span class="sxs-lookup"><span data-stu-id="dcb30-234">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="dcb30-235">Un Dockerfile come questo funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-235">A Dockerfile like this will work.</span></span> <span data-ttu-id="dcb30-236">Tuttavia è possibile ottimizzare in modo sostanziale le immagini, in particolare le immagini di produzione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-236">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="dcb30-237">Nel modello basato su contenitori e microservizi si avviano costantemente contenitori.</span><span class="sxs-lookup"><span data-stu-id="dcb30-237">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="dcb30-238">L'utilizzi tipico dei contenitori non comporta il riavvio di un contenitore in sospensione perché il contenitore è eliminabile.</span><span class="sxs-lookup"><span data-stu-id="dcb30-238">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="dcb30-239">Gli agenti di orchestrazione, ad esempio Docker Swarm, Kubernetes, DCOS o Azure Service Fabric, creano semplicemente nuove istanze delle immagini.</span><span class="sxs-lookup"><span data-stu-id="dcb30-239">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="dcb30-240">È quindi necessario ottimizzare precompilando l'applicazione quando viene compilata in modo che il processo di creazione dell'istanza sia più veloce.</span><span class="sxs-lookup"><span data-stu-id="dcb30-240">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="dcb30-241">Quando viene avviato, il contenitore deve essere pronto per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-241">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="dcb30-242">Non eseguire il ripristino e la compilazione in fase di esecuzione, usando i comandi dotnet restore e dotnet build dall'interfaccia della riga di comando dotnet, come indicato in molti post di blog su .NET Core e Docker.</span><span class="sxs-lookup"><span data-stu-id="dcb30-242">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="dcb30-243">Il team .NET sta lavorando intensamente per rendere .NET Core e ASP.NET Core un framework ottimizzato per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="dcb30-243">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="dcb30-244">.NET Core non è solo un framework leggero con un ingombro di memoria ridotto; il team si è concentrato sulle prestazioni di avvio e ha prodotto alcune immagini Docker ottimizzate, ad esempio [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) disponibile in [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), rispetto alle immagini regolari [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="dcb30-244">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="dcb30-245">L'immagine [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) fornisce l'impostazione automatica di aspnetcore\_urls per la porta 80 e la cache pre-ngend degli assembly; entrambe le impostazioni consentono un avvio più rapido.</span><span class="sxs-lookup"><span data-stu-id="dcb30-245">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="dcb30-246">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dcb30-246">Additional resources</span></span>

-   <span data-ttu-id="dcb30-247">**Building Optimized Docker Images with ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/) (Compilazione di immagini Docker ottimizzate con ASP.NET Core)</span><span class="sxs-lookup"><span data-stu-id="dcb30-247">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="dcb30-248">Compilazione dell'applicazione da un contenitore (CI) di compilazione</span><span class="sxs-lookup"><span data-stu-id="dcb30-248">Building the application from a build (CI) container</span></span>

<span data-ttu-id="dcb30-249">Un altro vantaggio di Docker è che consente di compilare l'applicazione da un contenitore preconfigurato, come illustrato nella figura 8-13 senza la necessità di creare una VM o un computer di compilazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-249">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="dcb30-250">È possibile usare o testare il contenitore di compilazione eseguendolo nel computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dcb30-250">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="dcb30-251">L'aspetto ancora più interessante è tuttavia che è possibile usare lo stesso contenitore di compilazione dalla pipeline CI (Continuous Integration).</span><span class="sxs-lookup"><span data-stu-id="dcb30-251">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="dcb30-252">**Figura 8-13**.</span><span class="sxs-lookup"><span data-stu-id="dcb30-252">**Figure 8-13**.</span></span> <span data-ttu-id="dcb30-253">Docker build-container per la compilazione di binari .NET</span><span class="sxs-lookup"><span data-stu-id="dcb30-253">Docker build-container compiling your .NET binaries</span></span> 

<span data-ttu-id="dcb30-254">Per questo scenario viene fornita l'immagine [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/), che è possibile usare per compilare e creare le app ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="dcb30-254">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="dcb30-255">L'output viene inserito in un'immagine basata sull'immagine [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), che è un'immagine di runtime ottimizzata, come indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="dcb30-255">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="dcb30-256">L'immagine aspnetcore-build contiene tutto ciò che occorre per compilare un'applicazione ASP.NET Core, tra cui .NET Core, ASP.NET SDK, npm, Bower, Gulp e così via.</span><span class="sxs-lookup"><span data-stu-id="dcb30-256">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="dcb30-257">Queste dipendenze sono necessarie in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="dcb30-257">We need these dependencies at build time.</span></span> <span data-ttu-id="dcb30-258">Non si intende tuttavia mantenerle con l'applicazione in fase di esecuzione perché renderebbero l'immagine inutilmente grande.</span><span class="sxs-lookup"><span data-stu-id="dcb30-258">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="dcb30-259">Nell'applicazione eShopOnContainers è possibile compilare l'applicazione da un contenitore semplicemente eseguendo il comando docker-compose seguente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-259">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="dcb30-260">La figura 8-14 mostra questo comando in esecuzione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dcb30-260">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="dcb30-261">**Figura 8-14.**</span><span class="sxs-lookup"><span data-stu-id="dcb30-261">**Figure 8-14.**</span></span> <span data-ttu-id="dcb30-262">Compilazione dell'applicazione .NET da un contenitore</span><span class="sxs-lookup"><span data-stu-id="dcb30-262">Building your .NET application from a container</span></span>

<span data-ttu-id="dcb30-263">Come si può notare, il contenitore in esecuzione è ci-build\_1.</span><span class="sxs-lookup"><span data-stu-id="dcb30-263">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="dcb30-264">È basato sull'immagine aspnetcore-build ed è quindi possibile compilare e creare l'intera applicazione all'interno del contenitore, anziché dal PC.</span><span class="sxs-lookup"><span data-stu-id="dcb30-264">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="dcb30-265">Questo è il motivo per cui in realtà si stanno creando e compilando i progetti .NET Core in Linux, perché quel contenitore è in esecuzione sull'host predefinito Linux Docker.</span><span class="sxs-lookup"><span data-stu-id="dcb30-265">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="dcb30-266">Il file [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) per questa immagine (parte di eShopOnContainers) contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="dcb30-266">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="dcb30-267">Si noti che avvia un contenitore di compilazione usando l'immagine [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/).</span><span class="sxs-lookup"><span data-stu-id="dcb30-267">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

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

* <span data-ttu-id="dcb30-268">A partire da **.NET Core 2.0**, il comando `dotnet restore` viene eseguito automaticamente quando viene eseguito il comando `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="dcb30-268">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="dcb30-269">Dopo che il contenitore di compilazione è in esecuzione, vengono eseguiti i comandi dotnet restore e dotnet publish di .NET SDK su tutti i progetti nella soluzione per compilare i bit .NET.</span><span class="sxs-lookup"><span data-stu-id="dcb30-269">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="dcb30-270">In questo caso, poiché eShopOnContainers include anche un'applicazione a pagina singola basata su TypeScript e Angular per il codice client, è necessario anche controllare le dipendenze JavaScript con npm, ma questa operazione non è correlata ai bit di .NET.</span><span class="sxs-lookup"><span data-stu-id="dcb30-270">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="dcb30-271">Il comando dotnet publish compila e pubblica l'output compilato all'interno della cartella di ogni progetto nella cartella ../obj/Docker/publish, come illustrato nella figura 8-15.</span><span class="sxs-lookup"><span data-stu-id="dcb30-271">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="dcb30-272">**Figura 8-15.**</span><span class="sxs-lookup"><span data-stu-id="dcb30-272">**Figure 8-15.**</span></span> <span data-ttu-id="dcb30-273">File binari generati dal comando dotnet publish</span><span class="sxs-lookup"><span data-stu-id="dcb30-273">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="dcb30-274">Creazione di immagini Docker dall'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="dcb30-274">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="dcb30-275">Dopo che l'output dell'applicazione viene pubblicato nelle cartelle correlate (all'interno di ogni progetto), il passaggio successivo consiste nel creare effettivamente le immagini Docker.</span><span class="sxs-lookup"><span data-stu-id="dcb30-275">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="dcb30-276">A tale scopo si usano i comandi docker-compose build e docker-compose up, come illustrato nella figura 8-16.</span><span class="sxs-lookup"><span data-stu-id="dcb30-276">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="dcb30-277">**Figura 8-16.**</span><span class="sxs-lookup"><span data-stu-id="dcb30-277">**Figure 8-16.**</span></span> <span data-ttu-id="dcb30-278">Creazione di immagini Docker ed esecuzione di contenitori</span><span class="sxs-lookup"><span data-stu-id="dcb30-278">Building Docker images and running the containers</span></span>

<span data-ttu-id="dcb30-279">Nella figura 8-17 è possibile esaminare come viene eseguito il comando docker-compose build.</span><span class="sxs-lookup"><span data-stu-id="dcb30-279">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="dcb30-280">**Figura 8-17**.</span><span class="sxs-lookup"><span data-stu-id="dcb30-280">**Figure 8-17**.</span></span> <span data-ttu-id="dcb30-281">Creazione di immagini Docker con il comando docker-compose build</span><span class="sxs-lookup"><span data-stu-id="dcb30-281">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="dcb30-282">La differenza tra i comandi docker-compose build e docker-compose up è che il secondo crea e avvia le immagini.</span><span class="sxs-lookup"><span data-stu-id="dcb30-282">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="dcb30-283">Quando si usa Visual Studio, tutti questi passaggi vengono eseguiti dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="dcb30-283">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="dcb30-284">Visual Studio compila l'applicazione .NET, crea le immagini Docker e distribuisce i contenitori nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="dcb30-284">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="dcb30-285">Visual Studio offre funzionalità aggiuntive, come la possibilità di eseguire il debug dei contenitori in esecuzione in Docker direttamente da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dcb30-285">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="dcb30-286">La conclusione generale è che è possibile compilare l'applicazione allo stesso modo in cui la compilerebbe la pipeline CI/CD, da un contenitore invece che da un computer locale.</span><span class="sxs-lookup"><span data-stu-id="dcb30-286">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="dcb30-287">Dopo aver creato le immagini, è sufficiente eseguire le immagini Docker usando il comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="dcb30-287">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="dcb30-288">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="dcb30-288">Additional resources</span></span>

-   <span data-ttu-id="dcb30-289">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)) (Compilazione di bit da un contenitore: impostazione della soluzione eShopOnContainers in un ambiente Windows CLI (dotnet CLI, Docker CLI e codice di Visual Studio), -Docker-CLI-e codice VS)</span><span class="sxs-lookup"><span data-stu-id="dcb30-289">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dcb30-290">[Indietro] (data-driven-crud-microservice.md) [Avanti] (database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="dcb30-290">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
