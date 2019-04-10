---
title: Definizione dell'applicazione a più contenitori con docker-compose.yml
description: Come specificare la composizione di microservizi per un'applicazione a più contenitori con docker-compose.yml.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 4f4918a6f26a617fad38c7955415c4ff559a9187
ms.sourcegitcommit: a3db1a9eafca89f95ccf361bc1833b47fbb2bb30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2019
ms.locfileid: "58920779"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="de994-103">Definizione dell'applicazione a più contenitori con docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="de994-103">Defining your multi-container application with docker-compose.yml</span></span>

<span data-ttu-id="de994-104">Il file [docker-compose.yml](https://docs.docker.com/compose/compose-file/) è stato introdotto nella sezione [Passaggio 4 di questa guida. Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span><span class="sxs-lookup"><span data-stu-id="de994-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application).</span></span> <span data-ttu-id="de994-105">Tuttavia esistono altri modi per usare i file docker-compose che vale la pena di esplorare in maggiore dettaglio.</span><span class="sxs-lookup"><span data-stu-id="de994-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="de994-106">È possibile, ad esempio, descrivere in modo esplicito la modalità di distribuzione dell'applicazione a più contenitori nel file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="de994-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="de994-107">Facoltativamente è possibile anche descrivere come si intende compilare le immagini Docker personalizzate.</span><span class="sxs-lookup"><span data-stu-id="de994-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="de994-108">Le immagini Docker personalizzate possono essere compilate anche con l'interfaccia della riga di comando di Docker.</span><span class="sxs-lookup"><span data-stu-id="de994-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="de994-109">In pratica è possibile definire ciascun contenitore da distribuire, più determinate caratteristiche per ogni distribuzione di contenitore.</span><span class="sxs-lookup"><span data-stu-id="de994-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="de994-110">Dopo aver creato un file di descrizione della distribuzione di più contenitori, è possibile distribuire l'intera soluzione con un'unica azione orchestrata dal comando dell'interfaccia della riga di comando [docker-compose up](https://docs.docker.com/compose/overview/) oppure in modo trasparente da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="de994-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="de994-111">In caso contrario, è necessario usare l'interfaccia della riga di comando di Docker per eseguire la distribuzione contenitore per contenitore in più passaggi usando il comando `docker run` dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="de994-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the `docker run` command from the command line.</span></span> <span data-ttu-id="de994-112">Pertanto ogni servizio definito in docker-compose.yml deve specificare esattamente un'immagine o una build.</span><span class="sxs-lookup"><span data-stu-id="de994-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="de994-113">Le altre chiavi sono facoltative e sono analoghe alle controparti della riga di comando `docker run`.</span><span class="sxs-lookup"><span data-stu-id="de994-113">Other keys are optional, and are analogous to their `docker run` command-line counterparts.</span></span>

<span data-ttu-id="de994-114">Il seguente codice YAML definisce un possibile file docker-compose.yml globale, ma unico per l'esempio eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="de994-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="de994-115">Non si tratta del file docker-compose reale di eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="de994-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="de994-116">È invece una versione semplificata e consolidata in un singolo file, ma non è il modo migliore per lavorare con i file docker-compose, come sarà illustrato in seguito.</span><span class="sxs-lookup"><span data-stu-id="de994-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

```yml
version: '3.4'

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

<span data-ttu-id="de994-117">La chiave radice in questo file sono i servizi.</span><span class="sxs-lookup"><span data-stu-id="de994-117">The root key in this file is services.</span></span> <span data-ttu-id="de994-118">Sotto questa chiave si definiscono i servizi da distribuire ed eseguire quando si esegue il comando `docker-compose up` o si esegue la distribuzione da Visual Studio usando questo file docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="de994-118">Under that key you define the services you want to deploy and run when you execute the `docker-compose up` command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="de994-119">In questo caso nel file docker compose.yml sono stati definiti più servizi, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="de994-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following table.</span></span>

| <span data-ttu-id="de994-120">Nome del servizio</span><span class="sxs-lookup"><span data-stu-id="de994-120">Service name</span></span> | <span data-ttu-id="de994-121">Description</span><span class="sxs-lookup"><span data-stu-id="de994-121">Description</span></span> |
|--------------|-------------|
| <span data-ttu-id="de994-122">webmvc</span><span class="sxs-lookup"><span data-stu-id="de994-122">webmvc</span></span>       | <span data-ttu-id="de994-123">Contenitore che include l'applicazione ASP.NET Core MVC che usa i microservizi da C\# sul lato server</span><span class="sxs-lookup"><span data-stu-id="de994-123">Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>|
| <span data-ttu-id="de994-124">catalog.api</span><span class="sxs-lookup"><span data-stu-id="de994-124">catalog.api</span></span>  | <span data-ttu-id="de994-125">Contenitore che include il microservizio API Web ASP.NET Core che gestisce i cataloghi</span><span class="sxs-lookup"><span data-stu-id="de994-125">Container including the Catalog ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="de994-126">ordering.api</span><span class="sxs-lookup"><span data-stu-id="de994-126">ordering.api</span></span> | <span data-ttu-id="de994-127">Contenitore che include il microservizio API Web ASP.NET Core che gestisce gli ordini</span><span class="sxs-lookup"><span data-stu-id="de994-127">Container including the Ordering ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="de994-128">sql.data</span><span class="sxs-lookup"><span data-stu-id="de994-128">sql.data</span></span>     | <span data-ttu-id="de994-129">Contenitore che esegue SQL Server per Linux, contenente i database di microservizi</span><span class="sxs-lookup"><span data-stu-id="de994-129">Container running SQL Server for Linux, holding the microservices databases</span></span> |
| <span data-ttu-id="de994-130">basket.api</span><span class="sxs-lookup"><span data-stu-id="de994-130">basket.api</span></span>   | <span data-ttu-id="de994-131">Contenitore con il microservizio API Web ASP.NET Core che gestisce i carrelli</span><span class="sxs-lookup"><span data-stu-id="de994-131">Container with the Basket ASP.NET Core Web API microservice</span></span> |
| <span data-ttu-id="de994-132">basket.data</span><span class="sxs-lookup"><span data-stu-id="de994-132">basket.data</span></span>  | <span data-ttu-id="de994-133">Contenitore che esegue il servizio cache REDIS, con il database dei carrelli come cache REDIS</span><span class="sxs-lookup"><span data-stu-id="de994-133">Container running the REDIS cache service, with the basket database as a REDIS cache</span></span> |

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="de994-134">Un semplice contenitore di API di servizi Web</span><span class="sxs-lookup"><span data-stu-id="de994-134">A simple Web Service API container</span></span>

<span data-ttu-id="de994-135">Concentrandosi su un singolo contenitore, la definizione del microservizio contenitore catalog.api è semplice:</span><span class="sxs-lookup"><span data-stu-id="de994-135">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

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

<span data-ttu-id="de994-136">La configurazione base di questo servizio con contenitore è la seguente:</span><span class="sxs-lookup"><span data-stu-id="de994-136">This containerized service has the following basic configuration:</span></span>

- <span data-ttu-id="de994-137">Si basa sull'immagine eshop/catalog.api personalizzata.</span><span class="sxs-lookup"><span data-stu-id="de994-137">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="de994-138">Per semplicità non esiste un'impostazione chiave build: nel file.</span><span class="sxs-lookup"><span data-stu-id="de994-138">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="de994-139">Ciò significa che l'immagine deve essere stata compilata in precedenza (con docker build) oppure è stata scaricata (con il comando docker pull) da un registro Docker.</span><span class="sxs-lookup"><span data-stu-id="de994-139">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

- <span data-ttu-id="de994-140">Definisce una variabile di ambiente denominata ConnectionString con la stringa di connessione che Entity Framework deve usare per accedere all'istanza di SQL Server contenente il modello di dati di catalogo.</span><span class="sxs-lookup"><span data-stu-id="de994-140">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="de994-141">In questo caso, lo stesso contenitore SQL Server contiene più database.</span><span class="sxs-lookup"><span data-stu-id="de994-141">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="de994-142">Pertanto la memoria necessaria nel computer di sviluppo per Docker è inferiore.</span><span class="sxs-lookup"><span data-stu-id="de994-142">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="de994-143">Tuttavia è possibile anche distribuire un contenitore SQL Server per ogni database di microservizi.</span><span class="sxs-lookup"><span data-stu-id="de994-143">However, you could also deploy one SQL Server container for each microservice database.</span></span>

- <span data-ttu-id="de994-144">Il nome SQL Server è sql.data, ovvero lo stesso nome usato per il contenitore in cui è in esecuzione l'istanza di SQL Server per Linux.</span><span class="sxs-lookup"><span data-stu-id="de994-144">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="de994-145">Questo approccio è vantaggioso perché la possibilità di usare questa risoluzione di nomi (interna all'host Docker) risolverà l'indirizzo di rete e non è quindi necessario conoscere l'IP interno per i contenitori a cui si sta accedendo da altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="de994-145">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="de994-146">Poiché la stringa di connessione viene definita da una variabile di ambiente, è possibile impostare questa variabile tramite un meccanismo diverso e in un momento diverso.</span><span class="sxs-lookup"><span data-stu-id="de994-146">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="de994-147">Ad esempio, è possibile impostare una stringa di connessione diversa durante la distribuzione in produzione negli host finali oppure dalle pipeline CI/CD in Azure DevOps Services o dal sistema DevOps preferito.</span><span class="sxs-lookup"><span data-stu-id="de994-147">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in Azure DevOps Services or your preferred DevOps system.</span></span>

- <span data-ttu-id="de994-148">Espone la porta 80 per l'accesso interno al servizio catalog.api all'interno dell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="de994-148">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="de994-149">L'host è attualmente una VM Linux perché si basa su un'immagine Docker per Linux, ma è possibile configurare il contenitore per l'esecuzione su un'immagine per Windows.</span><span class="sxs-lookup"><span data-stu-id="de994-149">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

- <span data-ttu-id="de994-150">Inoltra la porta 80 esposta sul contenitore alla porta esterna 5101 sul computer host Docker (la VM Linux).</span><span class="sxs-lookup"><span data-stu-id="de994-150">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

- <span data-ttu-id="de994-151">Collega il servizio Web al servizio sql.data, ossia l'istanza di SQL Server per il database Linux in esecuzione in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="de994-151">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="de994-152">Quando si specifica questa dipendenza, il contenitore catalog.api verrà avviato solo dopo l'avvio del contenitore sql.data; questo aspetto è importante perché per catalog.api è necessario che prima sia in esecuzione il database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de994-152">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="de994-153">Tuttavia, questo tipo di dipendenza di contenitore non è sufficiente in molti casi poiché Docker esegue il controllo solo a livello di contenitore.</span><span class="sxs-lookup"><span data-stu-id="de994-153">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="de994-154">In alcuni casi il servizio, in questo caso SQL Server, potrebbe non essere ancora pronto ed è quindi consigliabile implementare la logica di ripetizione con il backoff esponenziale nei microservizi client.</span><span class="sxs-lookup"><span data-stu-id="de994-154">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="de994-155">In questo modo, se un contenitore di dipendenza non è pronto per un breve periodo di tempo, l'applicazione sarà ancora resiliente.</span><span class="sxs-lookup"><span data-stu-id="de994-155">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

- <span data-ttu-id="de994-156">Viene configurata per consentire l'accesso ai server esterni: l'impostazione extra\_hosts consente di accedere ai server esterni o ai computer all'esterno dell'host Docker (quindi all'esterno della VM predefinita che è un host Docker di sviluppo), ad esempio un'istanza locale di SQL Server sul PC di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="de994-156">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="de994-157">Altre impostazioni più avanzate del file docker-compose.yml verranno illustrate nelle sezioni successive.</span><span class="sxs-lookup"><span data-stu-id="de994-157">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="de994-158">Utilizzo dei file docker-compose per usare più ambienti come destinazione</span><span class="sxs-lookup"><span data-stu-id="de994-158">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="de994-159">I file docker-compose.yml sono file di definizione e possono essere usati da più infrastrutture compatibili con questo formato.</span><span class="sxs-lookup"><span data-stu-id="de994-159">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="de994-160">Lo strumento più semplice è il comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="de994-160">The most straightforward tool is the docker-compose command.</span></span>

<span data-ttu-id="de994-161">Con il comando docker-compose è quindi possibile usare come destinazione i seguenti scenari principali.</span><span class="sxs-lookup"><span data-stu-id="de994-161">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="de994-162">Ambienti di sviluppo</span><span class="sxs-lookup"><span data-stu-id="de994-162">Development environments</span></span>

<span data-ttu-id="de994-163">Quando si sviluppano applicazioni, è importante poter eseguire un'applicazione in un ambiente di sviluppo isolato.</span><span class="sxs-lookup"><span data-stu-id="de994-163">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="de994-164">È possibile usare il comando dell'interfaccia della riga di comando docker-compose per creare questo ambiente oppure usare Visual Studio che esegue docker-compose in background.</span><span class="sxs-lookup"><span data-stu-id="de994-164">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="de994-165">Il file docker-compose.yml consente di configurare e documentare tutte le dipendenze di servizio dell'applicazione,come altri servizi, cache, database, code e così via.</span><span class="sxs-lookup"><span data-stu-id="de994-165">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="de994-166">Con il comando dell'interfaccia della riga di comando docker-compose è possibile creare e avviare uno o più contenitori per ogni dipendenza con un unico comando (docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="de994-166">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="de994-167">I file docker-compose.yml sono file di configurazione interpretati dal motore Docker, ma servono anche come utili file di documentazione sulla composizione dell'applicazione a più contenitori.</span><span class="sxs-lookup"><span data-stu-id="de994-167">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="de994-168">Ambienti di test</span><span class="sxs-lookup"><span data-stu-id="de994-168">Testing environments</span></span>

<span data-ttu-id="de994-169">Un aspetto importante di qualsiasi processo di distribuzione continua (CD) o di integrazione continua (CI) sono gli unit test e i test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="de994-169">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="de994-170">Questi test automatizzati richiedono un ambiente isolato per evitare impatti da parte degli utenti o di eventuali altre modifiche nei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="de994-170">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="de994-171">Con Docker Compose è possibile creare ed eliminare definitivamente l'ambiente isolato molto facilmente usando alcuni comandi al prompt dei comandi o script, come i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="de994-171">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose.test.override.yml down
```

#### <a name="production-deployments"></a><span data-ttu-id="de994-172">Distribuzioni in produzione</span><span class="sxs-lookup"><span data-stu-id="de994-172">Production deployments</span></span>

<span data-ttu-id="de994-173">È possibile anche usare Docker Compose per eseguire la distribuzione in un motore Docker remoto.</span><span class="sxs-lookup"><span data-stu-id="de994-173">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="de994-174">Un caso tipico consiste nella distribuzione di una singola istanza dell'host Docker, ad esempio una macchina virtuale in produzione o un server di cui viene eseguito il provisioning con [Docker Machine](https://docs.docker.com/machine/overview/).</span><span class="sxs-lookup"><span data-stu-id="de994-174">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span>

<span data-ttu-id="de994-175">Se si usa qualsiasi altro agente di orchestrazione (Microsoft Azure Service Fabric, Kubernetes e così via), può essere necessario aggiungere impostazioni di installazione e configurazione dei metadati, come quelle in docker-compose.yml, ma nel formato richiesto dall'altro agente di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="de994-175">If you are using any other orchestrator (Azure Service Fabric, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="de994-176">In ogni caso, docker-compose è un utile strumento e formato di metadati per lo sviluppo, i test e i flussi di lavoro di produzione, anche se il flusso di lavoro di produzione potrebbe variare in base all'agente di orchestrazione in uso.</span><span class="sxs-lookup"><span data-stu-id="de994-176">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="de994-177">Utilizzo di più file docker-compose per la gestione di ambienti diversi</span><span class="sxs-lookup"><span data-stu-id="de994-177">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="de994-178">Se si usano come destinazione ambienti diversi, è necessario usare più file compose.</span><span class="sxs-lookup"><span data-stu-id="de994-178">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="de994-179">In questo modo è possibile creare più varianti di configurazione a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="de994-179">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="de994-180">Override del file docker-compose base</span><span class="sxs-lookup"><span data-stu-id="de994-180">Overriding the base docker-compose file</span></span>

<span data-ttu-id="de994-181">È possibile usare un singolo file docker-compose.yml, come negli esempi semplificati illustrati nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="de994-181">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="de994-182">Tuttavia questo approccio non è consigliabile per la maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="de994-182">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="de994-183">Per impostazione predefinita, Compose legge due file: docker-compose.yml e un file docker-compose.override.yml facoltativo.</span><span class="sxs-lookup"><span data-stu-id="de994-183">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="de994-184">Come illustrato nella figura 6-11, quando si usa Visual Studio e si abilita il supporto Docker, Visual Studio crea anche un file docker-compose.vs.debug.g.yml aggiuntivo per il debug dell'applicazione. Per vedere questo file, accedere alla cartella obj\\Docker \\ nella cartella principale della soluzione.</span><span class="sxs-lookup"><span data-stu-id="de994-184">As shown in Figure 6-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.vs.debug.g.yml file for debugging the application, you can take a look at this file in folder obj\\Docker\\ in the main solution folder.</span></span>

![Struttura del file di progetto docker-compose: .dockerignore per ignorare i file, docker-compose.yml per comporre microservizi, docker-compose.override.yml per configurare l'ambiente dei microservizi.](./media/image12.png)

<span data-ttu-id="de994-186">**Figura 6-11**.</span><span class="sxs-lookup"><span data-stu-id="de994-186">**Figure 6-11**.</span></span> <span data-ttu-id="de994-187">File docker-compose in Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="de994-187">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="de994-188">È possibile modificare i file docker-compose con qualsiasi editor di codice di Visual Studio o Sublime ed eseguire l'applicazione con il comando docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="de994-188">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="de994-189">Per convenzione, il file docker-compose.yml contiene la configurazione base e altre impostazioni statiche.</span><span class="sxs-lookup"><span data-stu-id="de994-189">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="de994-190">Ciò significa che la configurazione del servizio non deve cambiare a seconda dell'ambiente di distribuzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="de994-190">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="de994-191">Il file docker-compose.override.yml, come suggerisce il nome, contiene le impostazioni di configurazione che eseguono l'override della configurazione base, ad esempio la configurazione che dipende dall'ambiente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="de994-191">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="de994-192">È possibile anche avere più file di override con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="de994-192">You can have multiple override files with different names also.</span></span> <span data-ttu-id="de994-193">I file di override in genere contengono informazioni aggiuntive necessarie per l'applicazione, ma specifiche per un ambiente o una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="de994-193">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="de994-194">Utilizzo di più ambienti come destinazione</span><span class="sxs-lookup"><span data-stu-id="de994-194">Targeting multiple environments</span></span>

<span data-ttu-id="de994-195">Un tipico caso d'uso è quello in cui si definiscono più file compose in modo da poter usare come destinazione più ambienti, ad esempio quello di produzione, staging, CI o sviluppo.</span><span class="sxs-lookup"><span data-stu-id="de994-195">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="de994-196">Per supportare queste differenze, è possibile suddividere la configurazione di Compose in più file, come illustrato nella figura 6-12.</span><span class="sxs-lookup"><span data-stu-id="de994-196">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 6-12.</span></span>

![È possibile combinare più file docker-compose\*.fml per gestire ambienti diversi.](./media/image13.png)

<span data-ttu-id="de994-198">**Figura 6-12**.</span><span class="sxs-lookup"><span data-stu-id="de994-198">**Figure 6-12**.</span></span> <span data-ttu-id="de994-199">Più file docker-compose che eseguono l'override di valori del file docker-compose.yml base</span><span class="sxs-lookup"><span data-stu-id="de994-199">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="de994-200">Iniziare con il file docker-compose.yml base.</span><span class="sxs-lookup"><span data-stu-id="de994-200">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="de994-201">Questo file base deve contenere le impostazioni di configurazione base o statiche, ossia che non cambiano in base all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="de994-201">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="de994-202">Ad esempio, eShopOnContainers ha come file di base il seguente file docker-compose.yml, semplificato con meno servizi.</span><span class="sxs-lookup"><span data-stu-id="de994-202">For example, the eShopOnContainers has the following docker-compose.yml file (simplified with less services) as the base file.</span></span>

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile
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

<span data-ttu-id="de994-203">I valori nel file docker-compose.yml base non devono essere modificati in base ai diversi ambienti di distribuzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="de994-203">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="de994-204">Se, ad esempio, si esamina con attenzione la definizione del servizio webmvc, si nota come queste informazioni sono più o meno le stesse indipendentemente dall'ambiente di destinazione.</span><span class="sxs-lookup"><span data-stu-id="de994-204">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="de994-205">Sono disponibili le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="de994-205">You have the following information:</span></span>

- <span data-ttu-id="de994-206">Il nome del servizio: webmvc.</span><span class="sxs-lookup"><span data-stu-id="de994-206">The service name: webmvc.</span></span>

- <span data-ttu-id="de994-207">L'immagine personalizzata del contenitore: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="de994-207">The container’s custom image: eshop/webmvc.</span></span>

- <span data-ttu-id="de994-208">Il comando per compilare l'immagine personalizzata di Docker, che indica il Dockerfile da usare.</span><span class="sxs-lookup"><span data-stu-id="de994-208">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

- <span data-ttu-id="de994-209">Le dipendenze da altri servizi, per cui questo contenitore viene avviato solo dopo che sono stati avviati gli altri contenitori di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="de994-209">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="de994-210">È possibile avere una configurazione aggiuntiva, ma il punto importante è che nel file docker-compose.yml base si impostano solo le informazioni comuni tra gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="de994-210">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="de994-211">Nel file docker-compose.override.yml o nei file simili per la produzione o lo staging si inserisce la configurazione specifica per ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="de994-211">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="de994-212">In genere, il file docker-compose.override.yml viene usato per l'ambiente di sviluppo, come nell'esempio seguente dall'applicazione eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="de994-212">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

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
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}
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
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
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

<span data-ttu-id="de994-213">In questo esempio, la configurazione di override dello sviluppo espone alcune porte all'host, definisce le variabili di ambiente con gli URL di reindirizzamento e specifica le stringhe di connessione per l'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="de994-213">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="de994-214">Queste impostazioni sono tutte relative solo all'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="de994-214">These settings are all just for the development environment.</span></span>

<span data-ttu-id="de994-215">Quando si esegue `docker-compose up` o lo si avvia da Visual Studio, il comando legge automaticamente le sostituzioni come se stesse unendo entrambi i file.</span><span class="sxs-lookup"><span data-stu-id="de994-215">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="de994-216">Si supponga di voler creare un altro file Compose per l'ambiente di produzione, con diversi valori di configurazione, porte o stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="de994-216">Suppose that you want another Compose file for the production environment, with different configuration values, ports or connection strings.</span></span> <span data-ttu-id="de994-217">È possibile creare un altro file di override, ad esempio un file denominato `docker-compose.prod.yml` con diverse impostazioni e variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="de994-217">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span> <span data-ttu-id="de994-218">Questo file potrebbe essere archiviato in un diverso repository Git oppure gestito e protetto da un team diverso.</span><span class="sxs-lookup"><span data-stu-id="de994-218">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="de994-219">Come distribuire un file di override specifico</span><span class="sxs-lookup"><span data-stu-id="de994-219">How to deploy with a specific override file</span></span>

<span data-ttu-id="de994-220">Per usare più file di override o un file di override con un nome diverso, è possibile usare l'opzione -f con il comando docker-compose e specificare i file.</span><span class="sxs-lookup"><span data-stu-id="de994-220">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="de994-221">Compose unisce i file nell'ordine in che cui vengono specificati alla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="de994-221">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="de994-222">Nell'esempio seguente viene illustrato come eseguire la distribuzione con i file di override.</span><span class="sxs-lookup"><span data-stu-id="de994-222">The following example shows how to deploy with override files.</span></span>

```console
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="de994-223">Utilizzo di variabili di ambiente nei file docker-compose</span><span class="sxs-lookup"><span data-stu-id="de994-223">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="de994-224">È utile, soprattutto negli ambienti di produzione, poter ottenere le informazioni di configurazione dalle variabili di ambiente, come mostrato negli esempi precedenti.</span><span class="sxs-lookup"><span data-stu-id="de994-224">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="de994-225">Per fare riferimento a una variabile di ambiente nei file docker-compose, usare la sintassi ${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="de994-225">You can reference an environment variable in your docker-compose files using the syntax ${MY\_VAR}.</span></span> <span data-ttu-id="de994-226">La riga seguente da un file docker compose.prod.yml mostra come fare riferimento al valore di una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="de994-226">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="de994-227">Le variabili di ambiente vengono create e inizializzate in modi diversi, a seconda dell'ambiente host (Linux, Windows, cluster basato su cloud e così via).</span><span class="sxs-lookup"><span data-stu-id="de994-227">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="de994-228">Tuttavia, un approccio pratico consiste nell'usare un file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="de994-228">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="de994-229">I file docker-compose supportano la dichiarazione di variabili di ambiente predefinite nel file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="de994-229">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="de994-230">Questi valori per le variabili di ambiente sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="de994-230">These values for the environment variables are the default values.</span></span> <span data-ttu-id="de994-231">Possono tuttavia essere sostituiti dai valori eventualmente definiti in ciascun ambiente (variabili del sistema operativo host o di ambiente dal cluster).</span><span class="sxs-lookup"><span data-stu-id="de994-231">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="de994-232">Inserire questo file con estensione env nella cartella da cui viene eseguito il comando docker-compose.</span><span class="sxs-lookup"><span data-stu-id="de994-232">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="de994-233">Nell'esempio seguente viene illustrato un file con estensione env, come il file [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) per l'applicazione eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="de994-233">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="de994-234">Docker-compose prevede che il formato di ogni riga di un file con estensione env sia \<variabile\>=\<valore\>.</span><span class="sxs-lookup"><span data-stu-id="de994-234">Docker-compose expects each line in an .env file to be in the format \<variable\>=\<value\>.</span></span>

<span data-ttu-id="de994-235">Si noti che i valori impostati nell'ambiente di runtime eseguono sempre l'override dei valori definiti all'interno del file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="de994-235">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="de994-236">Analogamente, anche i valori passati tramite gli argomenti del comando della riga di comando eseguono l'override dei valori predefiniti impostati nel file con estensione env.</span><span class="sxs-lookup"><span data-stu-id="de994-236">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="de994-237">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="de994-237">Additional resources</span></span>

- <span data-ttu-id="de994-238">**Panoramica di Docker Compose** \\</span><span class="sxs-lookup"><span data-stu-id="de994-238">**Overview of Docker Compose** \\</span></span>
    [https://docs.docker.com/compose/overview/](https://docs.docker.com/compose/overview/)

- <span data-ttu-id="de994-239">**Più file Compose** \\</span><span class="sxs-lookup"><span data-stu-id="de994-239">**Multiple Compose files** \\</span></span>
    [https://docs.docker.com/compose/extends/\#multiple-compose-files](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="de994-240">Creazione di immagini Docker ottimizzate con ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="de994-240">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="de994-241">Se si esplorano Docker e .NET Core sulle origini su Internet, si troveranno Dockerfile che illustrano la semplicità di creazione di un'immagine Docker copiando l'origine in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="de994-241">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="de994-242">Questi esempi suggeriscono che usando una configurazione semplice è possibile disporre di un'immagine Docker con l'ambiente fornito con l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="de994-242">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="de994-243">Nell'esempio seguente viene illustrato un Dockerfile semplice in questa ottica.</span><span class="sxs-lookup"><span data-stu-id="de994-243">The following example shows a simple Dockerfile in this vein.</span></span>

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/sdk:2.2
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="de994-244">Un Dockerfile come questo funzionerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="de994-244">A Dockerfile like this will work.</span></span> <span data-ttu-id="de994-245">Tuttavia è possibile ottimizzare in modo sostanziale le immagini, in particolare le immagini di produzione.</span><span class="sxs-lookup"><span data-stu-id="de994-245">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="de994-246">Nel modello basato su contenitori e microservizi si avviano costantemente contenitori.</span><span class="sxs-lookup"><span data-stu-id="de994-246">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="de994-247">L'utilizzi tipico dei contenitori non comporta il riavvio di un contenitore in sospensione perché il contenitore è eliminabile.</span><span class="sxs-lookup"><span data-stu-id="de994-247">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="de994-248">Gli agenti di orchestrazione, ad esempio Kubernetes e Azure Service Fabric, creano semplicemente nuove istanze delle immagini.</span><span class="sxs-lookup"><span data-stu-id="de994-248">Orchestrators (like Kubernetes and Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="de994-249">È quindi necessario ottimizzare precompilando l'applicazione quando viene compilata in modo che il processo di creazione dell'istanza sia più veloce.</span><span class="sxs-lookup"><span data-stu-id="de994-249">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="de994-250">Quando viene avviato, il contenitore deve essere pronto per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="de994-250">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="de994-251">Non eseguire il ripristino e la compilazione in fase di esecuzione, usando i comandi `dotnet restore` e `dotnet build` dall'interfaccia della riga di comando dotnet, come indicato in molti post di blog su .NET Core e Docker.</span><span class="sxs-lookup"><span data-stu-id="de994-251">You should not restore and compile at run time, using `dotnet restore` and `dotnet build` commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="de994-252">Il team .NET sta lavorando intensamente per rendere .NET Core e ASP.NET Core un framework ottimizzato per i contenitori.</span><span class="sxs-lookup"><span data-stu-id="de994-252">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="de994-253">Oltre al fatto che .NET Core è un framework leggero con un footprint della memoria ridotto, il team si è concentrato sulle immagini Docker ottimizzate per i tre scenari principali e le ha pubblicate in un registro dell'hub Docker in *dotnet/core*, a partire dalla versione 2.1:</span><span class="sxs-lookup"><span data-stu-id="de994-253">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on optimized Docker images for three main scenarios and published them in the Docker Hub registry at *dotnet/core*, beginning with version 2.1:</span></span>

1. <span data-ttu-id="de994-254">**Sviluppo**: la priorità è la possibilità di scorrere e sottoporre a debug rapidamente le modifiche e le dimensioni sono secondarie.</span><span class="sxs-lookup"><span data-stu-id="de994-254">**Development**: Where the priority is the ability to quickly iterate and debug changes, and where size is secondary.</span></span>

2. <span data-ttu-id="de994-255">**Compilazione**: la priorità è la compilazione dell'applicazione; sono inclusi file binari e altre dipendenze per ottimizzare i file binari.</span><span class="sxs-lookup"><span data-stu-id="de994-255">**Build**: The priority is compiling the application and includes binaries and other dependencies to optimize binaries.</span></span>

3. <span data-ttu-id="de994-256">**Produzione**: la priorità è la rapidità di distribuzione e avvio dei contenitori, quindi queste immagini sono limitate ai file binari e al contenuto necessario per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="de994-256">**Production**: Where the focus is fast deploying and starting of containers, so these images are limited to the binaries and the content needed to run the application.</span></span>

<span data-ttu-id="de994-257">A tale scopo, il team .NET offre quattro varianti di base in [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) (nell'hub Docker):</span><span class="sxs-lookup"><span data-stu-id="de994-257">To achieve this, the .NET team is providing four basic variants in [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) (at Docker Hub):</span></span>

1. <span data-ttu-id="de994-258">**sdk**: per gli scenari di sviluppo e compilazione</span><span class="sxs-lookup"><span data-stu-id="de994-258">**sdk**: for development and build scenarios</span></span>
1. <span data-ttu-id="de994-259">**aspnet**: per gli scenari di produzione di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="de994-259">**aspnet**: for ASP.NET production scenarios</span></span>
1. <span data-ttu-id="de994-260">**runtime**: per gli scenari di produzione di .NET</span><span class="sxs-lookup"><span data-stu-id="de994-260">**runtime**: for .NET production scenarios</span></span>
1. <span data-ttu-id="de994-261">**runtime-deps**: per gli scenari di produzione di [applicazioni indipendenti](../../../core/deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="de994-261">**runtime-deps**: for production scenarios of [self-contained applications](../../../core/deploying/index.md#self-contained-deployments-scd).</span></span>

<span data-ttu-id="de994-262">Per velocizzare l'avvio, le immagini di runtime impostano anche automaticamente aspnetcore\_urls sulla porta 80 e usano Ngen per creare una cache di immagini native degli assembly.</span><span class="sxs-lookup"><span data-stu-id="de994-262">For faster startup, runtime images also automatically set aspnetcore\_urls to port 80 and use Ngen to create a native image cache of assemblies.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="de994-263">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="de994-263">Additional resources</span></span>

- <span data-ttu-id="de994-264">**Compilazione di immagini Docker ottimizzate con ASP.NET Core** \\</span><span class="sxs-lookup"><span data-stu-id="de994-264">**Building Optimized Docker Images with ASP.NET Core** \\</span></span>
    [https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

- <span data-ttu-id="de994-265">**Compilazione di immagini Docker per applicazioni .NET Core** \\</span><span class="sxs-lookup"><span data-stu-id="de994-265">**Building Docker Images for .NET Core Applications** \\</span></span>
    [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](../../../core/docker/building-net-docker-images.md)

> [!div class="step-by-step"]
> <span data-ttu-id="de994-266">[Precedente](data-driven-crud-microservice.md)
> [Successivo](database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="de994-266">[Previous](data-driven-crud-microservice.md)
[Next](database-server-container.md)</span></span>
