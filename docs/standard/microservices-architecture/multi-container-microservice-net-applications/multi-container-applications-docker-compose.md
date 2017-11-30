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
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="8cb11-104">Definizione dell'applicazione multi-contenitore con docker compose.yml</span><span class="sxs-lookup"><span data-stu-id="8cb11-104">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="8cb11-105">In questa Guida, il [docker compose.yml](https://docs.docker.com/compose/compose-file/) file è stato introdotto nella sezione [passaggio 4. Definire i servizi in docker compose.yml quando si compila un'applicazione di multi-contenitore Docker](#step4_define_svcs_in_docker_compose_yml).</span><span class="sxs-lookup"><span data-stu-id="8cb11-105">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="8cb11-106">Tuttavia, esistono altri modi per usare i file docker-compose sono è opportuno considerare in modo dettagliato.</span><span class="sxs-lookup"><span data-stu-id="8cb11-106">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="8cb11-107">Ad esempio, è possibile descrivere in modo esplicito come si desidera distribuire l'applicazione a più contenitori nel file compose.yml di docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-107">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="8cb11-108">Facoltativamente, è possibile descrivere come si intende compilare le immagini Docker personalizzate.</span><span class="sxs-lookup"><span data-stu-id="8cb11-108">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="8cb11-109">(Le immagini Docker personalizzato possono anche essere compilate con l'interfaccia CLI di Docker.)</span><span class="sxs-lookup"><span data-stu-id="8cb11-109">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="8cb11-110">In pratica, è possibile definire ognuno dei contenitori di cui che si desidera distribuire più determinate caratteristiche per la distribuzione di ogni contenitore.</span><span class="sxs-lookup"><span data-stu-id="8cb11-110">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="8cb11-111">Dopo aver creato un file di descrizione del multi-contenitore di distribuzione, è possibile distribuire l'intera soluzione in un'unica azione orchestrata dal [docker comporre backup](https://docs.docker.com/compose/overview/) comando CLI, oppure è possibile distribuirlo in modo trasparente da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8cb11-111">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="8cb11-112">In caso contrario, è necessario utilizzare l'interfaccia CLI di Docker per distribuire dal contenitore in più passaggi tramite il comando docker run dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cb11-112">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="8cb11-113">Pertanto, ogni servizio definito in docker compose.yml deve specificare esattamente un'immagine o di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-113">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="8cb11-114">Le altre chiavi sono facoltativi e sono analoghi alle loro controparti della riga di comando di esecuzione di docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-114">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="8cb11-115">Il seguente codice YAML è la definizione di un file di possibili globale ma singolo docker-compose.yml per l'esempio eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8cb11-115">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="8cb11-116">Questa operazione è il file effettivo docker-compose da eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8cb11-116">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="8cb11-117">In alternativa, è una versione semplificata e consolidata in un singolo file, non è il miglior modo di lavorare con docker-comporre i file, come spiegato più avanti.</span><span class="sxs-lookup"><span data-stu-id="8cb11-117">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

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

<span data-ttu-id="8cb11-118">La chiave radice in questo file è di servizi.</span><span class="sxs-lookup"><span data-stu-id="8cb11-118">The root key in this file is services.</span></span> <span data-ttu-id="8cb11-119">In tale chiave è definire i servizi che si desidera distribuire ed eseguire quando si esegue la composizione docker di comando oppure quando si distribuiscono da Visual Studio usando il file compose.yml di docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-119">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="8cb11-120">In questo caso, il file di docker compose.yml ha più servizi definiti, come descritto nell'elenco seguente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-120">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="8cb11-121">webmvc contenitore che include l'applicazione ASP.NET MVC di base che utilizza il microservizi dal lato server C\#</span><span class="sxs-lookup"><span data-stu-id="8cb11-121">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="8cb11-122">Catalog.API contenitore che include il microservizio catalogo ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="8cb11-122">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="8cb11-123">Contenitore che include il microservizio ordinamento API Web di ASP.NET Core Ordering.API</span><span class="sxs-lookup"><span data-stu-id="8cb11-123">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="8cb11-124">Contenitore che esegue SQL Server per Linux, che contiene i database di microservizi SQL.Data</span><span class="sxs-lookup"><span data-stu-id="8cb11-124">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="8cb11-125">Basket.API contenitore con il microservizio Basket ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="8cb11-125">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="8cb11-126">Basket.Data contenitore in esecuzione il servizio cache REDIS, con il database di acquisti come cache REDIS</span><span class="sxs-lookup"><span data-stu-id="8cb11-126">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="8cb11-127">Un contenitore di API del servizio Web semplice</span><span class="sxs-lookup"><span data-stu-id="8cb11-127">A simple Web Service API container</span></span>

<span data-ttu-id="8cb11-128">Porre l'attenzione su un singolo contenitore, il contenitore catalog.api-microservizio presenta una semplice definizione:</span><span class="sxs-lookup"><span data-stu-id="8cb11-128">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

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

<span data-ttu-id="8cb11-129">Questo servizio nei contenitori con la configurazione di base seguente:</span><span class="sxs-lookup"><span data-stu-id="8cb11-129">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="8cb11-130">È basato sull'immagine eshop/catalog.api personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8cb11-130">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="8cb11-131">Per semplicità, non è disponibile alcuna compilazione: l'impostazione nel file di chiave.</span><span class="sxs-lookup"><span data-stu-id="8cb11-131">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="8cb11-132">Ciò significa che l'immagine devono essere stati creati in precedenza (con la compilazione docker) o sono stati scaricati (con il comando di docker pull) dal Registro di sistema qualsiasi Docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-132">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="8cb11-133">Definisce una variabile di ambiente denominata ConnectionString con la stringa di connessione da utilizzare da Entity Framework per accedere all'istanza di SQL Server che contiene il modello di dati del catalogo.</span><span class="sxs-lookup"><span data-stu-id="8cb11-133">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="8cb11-134">In questo caso, lo stesso contenitore di SQL Server contiene più database.</span><span class="sxs-lookup"><span data-stu-id="8cb11-134">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="8cb11-135">Pertanto, è necessario minore quantità di memoria nel computer di sviluppo per Docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-135">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="8cb11-136">Tuttavia, è inoltre possibile distribuire un contenitore di SQL Server per ogni database microservizio.</span><span class="sxs-lookup"><span data-stu-id="8cb11-136">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="8cb11-137">Il nome di SQL Server è sql.data, ovvero lo stesso nome utilizzato per il contenitore in cui è in esecuzione l'istanza di SQL Server per Linux.</span><span class="sxs-lookup"><span data-stu-id="8cb11-137">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="8cb11-138">Questa operazione è utile; è possibile utilizzare la risoluzione dei nomi (interna per l'host Docker) verrà risolto l'indirizzo di rete in modo che non è necessario conoscere l'indirizzo IP interno per i contenitori che si accede da altri contenitori.</span><span class="sxs-lookup"><span data-stu-id="8cb11-138">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="8cb11-139">Poiché la stringa di connessione è definita da una variabile di ambiente, è possibile impostare tale variabile tramite un meccanismo diverso e in un altro momento.</span><span class="sxs-lookup"><span data-stu-id="8cb11-139">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="8cb11-140">Ad esempio, è possibile impostare una stringa di connessione diversi durante la distribuzione nell'ambiente di produzione in host finale, oppure dalle pipeline CI/CD-ROM in Visual Studio Team Services o il sistema DevOps preferito.</span><span class="sxs-lookup"><span data-stu-id="8cb11-140">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="8cb11-141">Espone la porta 80 per l'accesso interno per il servizio catalog.api all'interno dell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-141">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="8cb11-142">L'host è attualmente una VM Linux perché si basa su un'immagine di Docker per Linux, ma è possibile configurare il contenitore eseguire su un'immagine di Windows.</span><span class="sxs-lookup"><span data-stu-id="8cb11-142">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="8cb11-143">Inoltra la porta 80 del contenitore su porta 5101 nel computer host Docker (la VM Linux) esposta.</span><span class="sxs-lookup"><span data-stu-id="8cb11-143">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="8cb11-144">Il servizio web fornisca un collegamento al servizio sql.data (l'istanza di SQL Server per il database di Linux in esecuzione in un contenitore).</span><span class="sxs-lookup"><span data-stu-id="8cb11-144">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="8cb11-145">Quando si specifica questa dipendenza, il contenitore catalog.api non verrà avviato fino a quando non è già avviato il contenitore sql.data; prima di tutto questo è importante perché catalog.api deve contenere il database di SQL Server e in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-145">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="8cb11-146">Tuttavia, questo tipo di contenitore dipendenza non è sufficiente in molti casi, perché Docker controlla solo a livello di contenitore.</span><span class="sxs-lookup"><span data-stu-id="8cb11-146">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="8cb11-147">In alcuni casi il servizio (in questo caso SQL Server) potrebbe comunque non essere pronto, pertanto è consigliabile implementare la logica di ripetizione tentativi con backoff esponenziale in microservizi il client.</span><span class="sxs-lookup"><span data-stu-id="8cb11-147">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="8cb11-148">In questo modo, se un contenitore di dipendenza non è pronto per un breve periodo di tempo, l'applicazione sarà comunque resiliente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-148">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="8cb11-149">Si è configurato per consentire l'accesso a server esterni: aggiuntivo\_host impostazione consente di accedere a server esterni o i computer all'esterno dell'host Docker (vale a dire, compreso il valore predefinito di VM Linux che rappresenta uno sviluppo Docker host), ad esempio un database SQL locale Istanza del server del computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8cb11-149">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="8cb11-150">Esistono inoltre altre impostazioni di docker compose.yml più avanzate che verranno illustrati nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8cb11-150">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="8cb11-151">Tramite docker-creare file in più ambienti di destinazione</span><span class="sxs-lookup"><span data-stu-id="8cb11-151">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="8cb11-152">I file di docker compose.yml sono file di definizione e possono essere utilizzati da più infrastrutture che utilizzano tale formato.</span><span class="sxs-lookup"><span data-stu-id="8cb11-152">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="8cb11-153">Lo strumento più semplice è docker-comporre comando, ma altri strumenti come orchestrators (ad esempio, Docker Swarm) inoltre comprendere tale file.</span><span class="sxs-lookup"><span data-stu-id="8cb11-153">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="8cb11-154">Pertanto, tramite il comando è possibile utilizzare i seguenti scenari principali di docker-comporre.</span><span class="sxs-lookup"><span data-stu-id="8cb11-154">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="8cb11-155">Ambienti di sviluppo</span><span class="sxs-lookup"><span data-stu-id="8cb11-155">Development environments</span></span>

<span data-ttu-id="8cb11-156">Quando si sviluppano applicazioni, è importante essere in grado di eseguire un'applicazione in un ambiente di sviluppo isolato.</span><span class="sxs-lookup"><span data-stu-id="8cb11-156">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="8cb11-157">È possibile utilizzare il comando CLI per creare tale ambiente oppure utilizzare Visual Studio che usa docker-comporre dietro le quinte docker-comporre.</span><span class="sxs-lookup"><span data-stu-id="8cb11-157">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="8cb11-158">Il file docker compose.yml consente di configurare e tutte le dipendenze dell'applicazione del servizio (altri servizi, cache, i database, code e così via) del documento.</span><span class="sxs-lookup"><span data-stu-id="8cb11-158">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="8cb11-159">Utilizzando il comando CLI di docker-comporre, è possibile creare e avviare uno o più contenitori per ogni dipendenza con un unico comando (docker-costituiscono backup).</span><span class="sxs-lookup"><span data-stu-id="8cb11-159">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="8cb11-160">I file di docker compose.yml sono interpretati dal motore Docker i file di configurazione, ma anche fungere da file di documentazione pratico sulla composizione di un'applicazione multi-contenitore.</span><span class="sxs-lookup"><span data-stu-id="8cb11-160">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="8cb11-161">Ambienti di test</span><span class="sxs-lookup"><span data-stu-id="8cb11-161">Testing environments</span></span>

<span data-ttu-id="8cb11-162">Una parte importante di qualsiasi distribuzione continua (CD) o un processo di integrazione continua (CI) sono unit test e test di integrazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-162">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="8cb11-163">Questi test automatizzati richiedono un ambiente isolato in modo che non sono interessate dagli utenti o qualsiasi altra differenza nei dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-163">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="8cb11-164">Tramite Docker Compose si possono creare ed eliminare tale ambiente isolato in modo molto semplice in alcuni comandi dal prompt dei comandi o script, ad esempio i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cb11-164">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="8cb11-165">Distribuzioni di produzione</span><span class="sxs-lookup"><span data-stu-id="8cb11-165">Production deployments</span></span>

<span data-ttu-id="8cb11-166">Per distribuire in un motore Docker remota, è possibile utilizzare anche Compose.</span><span class="sxs-lookup"><span data-stu-id="8cb11-166">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="8cb11-167">Un caso tipico consiste nella distribuzione di una singola istanza di host Docker (ad esempio una macchina virtuale di produzione o di un server eseguito il provisioning con [Docker macchina](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="8cb11-167">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="8cb11-168">Ma potrebbe anche essere un intero [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, a causa di cluster sono inoltre compatibili con i file di docker compose.yml.</span><span class="sxs-lookup"><span data-stu-id="8cb11-168">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="8cb11-169">Se si utilizza orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes e così via), si potrebbe essere necessario aggiungere le impostazioni di configurazione di installazione e i metadati come quelle in docker compose.yml, ma nel formato richiesto da altro agente di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-169">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="8cb11-170">In ogni caso, creare docker è un formato di metadati e lo strumento ideale per flussi di lavoro di sviluppo, test e produzione, anche se il flusso di lavoro di produzione può variare all'agente di orchestrazione in uso.</span><span class="sxs-lookup"><span data-stu-id="8cb11-170">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="8cb11-171">Utilizzo di più docker-comporre i file per la gestione di ambienti diversi</span><span class="sxs-lookup"><span data-stu-id="8cb11-171">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="8cb11-172">Se la destinazione ambienti diversi, è necessario utilizzare più comporre i file.</span><span class="sxs-lookup"><span data-stu-id="8cb11-172">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="8cb11-173">Ciò consente di creare più varianti di configurazione a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-173">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="8cb11-174">Si esegue l'override del file base docker-compose</span><span class="sxs-lookup"><span data-stu-id="8cb11-174">Overriding the base docker-compose file</span></span>

<span data-ttu-id="8cb11-175">È possibile utilizzare un file singolo docker-compose.yml come illustrato negli esempi semplificati illustrato nelle sezioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8cb11-175">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="8cb11-176">Tuttavia, non è consigliabile per la maggior parte delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="8cb11-176">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="8cb11-177">Per impostazione predefinita, composizione legge due file, un compose.yml di docker e un file docker-compose.override.yml facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8cb11-177">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="8cb11-178">Come illustrato nella figura 8-11, quando si utilizza Visual Studio e attivazione del supporto di Docker, Visual Studio crea anche i file e alcuni file aggiuntivi utilizzati per il debug.</span><span class="sxs-lookup"><span data-stu-id="8cb11-178">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates those files plus some additional files used for debugging.</span></span>

![](./media/image12.png)

<span data-ttu-id="8cb11-179">**Figura 8-11**.</span><span class="sxs-lookup"><span data-stu-id="8cb11-179">**Figure 8-11**.</span></span> <span data-ttu-id="8cb11-180">file in Visual Studio 2017 docker-comporre</span><span class="sxs-lookup"><span data-stu-id="8cb11-180">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="8cb11-181">È possibile modificare i file docker-compose con qualsiasi editor di codice di Visual Studio o Sublime ed eseguire l'applicazione con la composizione di docker comando di backup.</span><span class="sxs-lookup"><span data-stu-id="8cb11-181">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="8cb11-182">Per convenzione, il file di docker compose.yml contiene la configurazione di base e altre impostazioni statiche.</span><span class="sxs-lookup"><span data-stu-id="8cb11-182">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="8cb11-183">Ciò significa che la configurazione del servizio non è necessario cambiare a seconda dell'ambiente di distribuzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-183">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="8cb11-184">Il file di docker compose.override.yml, come suggerisce il nome, contiene le impostazioni di configurazione che eseguono l'override di configurazione di base, ad esempio di configurazione che varia a seconda dell'ambiente di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-184">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="8cb11-185">Inoltre, è possibile avere più file di sostituzione con nomi diversi.</span><span class="sxs-lookup"><span data-stu-id="8cb11-185">You can have multiple override files with different names also.</span></span> <span data-ttu-id="8cb11-186">I file di sostituzione in genere contengono informazioni aggiuntive necessarie per l'applicazione ma specifico in un ambiente o a una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-186">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="8cb11-187">Più ambienti di destinazione</span><span class="sxs-lookup"><span data-stu-id="8cb11-187">Targeting multiple environments</span></span>

<span data-ttu-id="8cb11-188">Un caso di utilizzo tipico è quando si definiscono più costituiscono i file in modo è possibile associare più ambienti, ad esempio produzione, gestione temporanea, l'elemento di configurazione o di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8cb11-188">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="8cb11-189">Per supportare queste differenze, è possibile suddividere la configurazione di composizione in più file, come illustrato nella figura 8-12.</span><span class="sxs-lookup"><span data-stu-id="8cb11-189">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="8cb11-190">**Figura 8-12**.</span><span class="sxs-lookup"><span data-stu-id="8cb11-190">**Figure 8-12**.</span></span> <span data-ttu-id="8cb11-191">Docker-creare più file di override dei valori nel file di base di docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="8cb11-191">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="8cb11-192">Iniziare con il file di base-compose.yml di docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-192">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="8cb11-193">Questo file di base deve contenere le impostazioni di configurazione di base o statico che non cambiano a seconda dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-193">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="8cb11-194">Ad esempio, il eShopOnContainers ha il seguente file docker compose.yml del file base.</span><span class="sxs-lookup"><span data-stu-id="8cb11-194">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

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

<span data-ttu-id="8cb11-195">Non modificare i valori nel file di base di docker-compose.yml a causa di ambienti di distribuzione di destinazione diverso.</span><span class="sxs-lookup"><span data-stu-id="8cb11-195">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="8cb11-196">Se si sta lavorando la definizione del servizio webmvc, ad esempio, è possibile visualizzare come tali informazioni sono molto simile all'indipendentemente da quale ambiente potrebbe essere destinando l'app.</span><span class="sxs-lookup"><span data-stu-id="8cb11-196">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="8cb11-197">Sono le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="8cb11-197">You have the following information:</span></span>

-   <span data-ttu-id="8cb11-198">Il nome del servizio: webmvc.</span><span class="sxs-lookup"><span data-stu-id="8cb11-198">The service name: webmvc.</span></span>

-   <span data-ttu-id="8cb11-199">Immagine personalizzata del contenitore: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="8cb11-199">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="8cb11-200">Il comando per compilare l'immagine personalizzata di Docker, che indica quale Dockerfile da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="8cb11-200">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="8cb11-201">Dipendenze da altri servizi, in modo da questo contenitore non viene avviato fino a quando non sono stati avviati i contenitori di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="8cb11-201">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="8cb11-202">È possibile avere una configurazione aggiuntiva, ma l'aspetto importante è che nel file di base-compose.yml di docker, si desidera impostare le informazioni che sono comuni a tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="8cb11-202">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="8cb11-203">Docker compose.override.yml i file analoghi per la produzione o gestione temporanea, quindi è consigliabile inserire configurazione specifiche per ogni ambiente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-203">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="8cb11-204">In genere, il compose.override.yml di docker viene usato per l'ambiente di sviluppo, come nell'esempio seguente da eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="8cb11-204">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

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

<span data-ttu-id="8cb11-205">In questo esempio, la configurazione della sostituzione sviluppo espone alcune porte all'host, definisce le variabili di ambiente con gli URL di reindirizzamento e specifica le stringhe di connessione per l'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8cb11-205">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="8cb11-206">Queste impostazioni sono tutte solo per l'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8cb11-206">These settings are all just for the development environment.</span></span>

<span data-ttu-id="8cb11-207">Quando si esegue comporre docker backup oppure avviarlo da Visual Studio, il comando legge le sostituzioni automaticamente come se sono stati l'unione di entrambi i file.</span><span class="sxs-lookup"><span data-stu-id="8cb11-207">When you run docker-compose up (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="8cb11-208">Si supponga che un altro file di composizione per l'ambiente di produzione, con valori di configurazione diverso.</span><span class="sxs-lookup"><span data-stu-id="8cb11-208">Suppose that you want another Compose file for the production environment, with different configuration values.</span></span> <span data-ttu-id="8cb11-209">È possibile creare un altro file di sostituzione, simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-209">You can create another override file, like the following.</span></span> <span data-ttu-id="8cb11-210">(Questo file potrebbe essere archiviato in un repository Git diversi o gestito e protetto da un team diverso.)</span><span class="sxs-lookup"><span data-stu-id="8cb11-210">(This file might be stored in a different Git repo or managed and secured by a different team.)</span></span>

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

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="8cb11-211">Come distribuire un file di override specifico</span><span class="sxs-lookup"><span data-stu-id="8cb11-211">How to deploy with a specific override file</span></span>

<span data-ttu-id="8cb11-212">Per usare più file di sostituzione o di un file di sostituzione con un nome diverso, è possibile utilizzare l'opzione -f con il comando di docker-comporre e specificare i file.</span><span class="sxs-lookup"><span data-stu-id="8cb11-212">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="8cb11-213">Comporre unisce i file nell'ordine in che cui vengono specificati nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cb11-213">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="8cb11-214">Nell'esempio seguente viene illustrato come distribuire i file di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-214">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="8cb11-215">Utilizzo di variabili di ambiente in docker-composizione file</span><span class="sxs-lookup"><span data-stu-id="8cb11-215">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="8cb11-216">È utile, soprattutto in ambienti di produzione, per essere in grado di ottenere informazioni di configurazione dalle variabili di ambiente, come negli esempi precedenti è stato illustrato.</span><span class="sxs-lookup"><span data-stu-id="8cb11-216">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="8cb11-217">Una variabile di ambiente si fa riferimento nei file docker-compose utilizzando la sintassi \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="8cb11-217">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="8cb11-218">La riga seguente da un file docker compose.prod.yml viene illustrato come fare riferimento al valore di una variabile di ambiente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-218">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="8cb11-219">Le variabili di ambiente vengono create e inizializzate in modi diversi, a seconda dell'ambiente host (Linux, Windows, il cluster di Cloud, ecc.).</span><span class="sxs-lookup"><span data-stu-id="8cb11-219">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="8cb11-220">Tuttavia, un approccio pratico consiste nell'utilizzare un file .env.</span><span class="sxs-lookup"><span data-stu-id="8cb11-220">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="8cb11-221">I file docker-compose supportano la dichiarazione di variabili di ambiente predefinite nel file .env.</span><span class="sxs-lookup"><span data-stu-id="8cb11-221">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="8cb11-222">Questi valori per le variabili di ambiente sono i valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8cb11-222">These values for the environment variables are the default values.</span></span> <span data-ttu-id="8cb11-223">Ma possono essere sostituite dai valori che sia stata definita in ognuno degli ambienti (sistema operativo host o le variabili di ambiente dal cluster).</span><span class="sxs-lookup"><span data-stu-id="8cb11-223">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="8cb11-224">Inserire questo file .env nella cartella in cui la composizione docker comando viene eseguito da.</span><span class="sxs-lookup"><span data-stu-id="8cb11-224">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="8cb11-225">Nell'esempio seguente viene illustrato un file di .env come il [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file per l'applicazione eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="8cb11-225">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="8cb11-226">Comporre docker prevede che ogni riga in un file nel formato .env &lt;variabile&gt;=&lt;valore&gt;.</span><span class="sxs-lookup"><span data-stu-id="8cb11-226">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="8cb11-227">Si noti che i valori impostati nell'ambiente di runtime sempre eseguire l'override di valori definiti all'interno del file .env.</span><span class="sxs-lookup"><span data-stu-id="8cb11-227">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="8cb11-228">In modo analogo, i valori passati tramite gli argomenti della riga di comando comando inoltre sostituiscano i valori predefiniti impostati nel file .env.</span><span class="sxs-lookup"><span data-stu-id="8cb11-228">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="8cb11-229">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8cb11-229">Additional resources</span></span>

-   <span data-ttu-id="8cb11-230">**Panoramica di Docker comporre**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="8cb11-230">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="8cb11-231">**Più file di composizione**
    [*https://docs.docker.com/compose/extends/\#file comporre più*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="8cb11-231">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="8cb11-232">Creazione di immagini di ASP.NET Core Docker ottimizzate</span><span class="sxs-lookup"><span data-stu-id="8cb11-232">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="8cb11-233">Se si Esplora Docker e .NET Core su origini su Internet, si noterà Dockerfile che illustrano la semplicità di creazione di un'immagine Docker copiando l'origine in un contenitore.</span><span class="sxs-lookup"><span data-stu-id="8cb11-233">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="8cb11-234">Questi esempi è consigliabile che utilizza una configurazione semplice, è possibile creare un'immagine di Docker con l'ambiente incluso nel pacchetto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-234">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="8cb11-235">Nell'esempio seguente viene illustrato un semplice Dockerfile in questo vein.</span><span class="sxs-lookup"><span data-stu-id="8cb11-235">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="8cb11-236">Un Dockerfile questo funzionerà.</span><span class="sxs-lookup"><span data-stu-id="8cb11-236">A Dockerfile like this will work.</span></span> <span data-ttu-id="8cb11-237">Tuttavia, è possibile ottimizzare sostanzialmente le immagini, in particolare le immagini di produzione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-237">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="8cb11-238">In un contenitore e il modello di microservizi, viene avviato costantemente contenitori.</span><span class="sxs-lookup"><span data-stu-id="8cb11-238">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="8cb11-239">L'utilizzo tipico di contenitori non viene riavviato un contenitore di sospensione, perché il contenitore è eliminabile.</span><span class="sxs-lookup"><span data-stu-id="8cb11-239">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="8cb11-240">Orchestrators (ad esempio, Docker Swarm, Kubernetes, DCOS o Azure Service Fabric) è sufficiente creare nuove istanze delle immagini.</span><span class="sxs-lookup"><span data-stu-id="8cb11-240">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="8cb11-241">Ciò significa che è necessario ottimizzare la precompilazione dell'applicazione quando viene generata in modo che il processo di creazione dell'istanza sia più veloce.</span><span class="sxs-lookup"><span data-stu-id="8cb11-241">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="8cb11-242">Quando viene avviato il contenitore, deve essere pronto per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-242">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="8cb11-243">Non ripristinare e compilare in fase di esecuzione, utilizzando dotnet dotnet e ripristino compilare comandi dotnet CLI che, come illustrato nella molti post di blog su .NET Core e Docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-243">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="8cb11-244">Il team di .NET è stato operazioni importanti per rendere un framework ottimizzato per il contenitore di .NET Core e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="8cb11-244">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="8cb11-245">Non solo è .NET Core un framework semplice con un footprint di memoria di piccole dimensioni; il team ha con stato attivo sulle prestazioni di avvio e prodotti alcune immagini Docker ottimizzati, ad esempio il [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) immagine disponibile all'indirizzo [Hub Docker](https://hub.docker.com/r/microsoft/aspnetcore/), rispetto alle normali [ Microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) immagini.</span><span class="sxs-lookup"><span data-stu-id="8cb11-245">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="8cb11-246">Il [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) immagine fornisce l'impostazione automatica di aspnetcore\_URL per la porta 80 e la cache di pre-ngend degli assembly; entrambe le impostazioni comportare un avvio più rapido.</span><span class="sxs-lookup"><span data-stu-id="8cb11-246">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="8cb11-247">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8cb11-247">Additional resources</span></span>

-   <span data-ttu-id="8cb11-248">**Creazione di immagini di Docker con ASP.NET Core ottimizzate**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="8cb11-248">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="8cb11-249">Compilazione dell'applicazione da un contenitore di compilazione (CI)</span><span class="sxs-lookup"><span data-stu-id="8cb11-249">Building the application from a build (CI) container</span></span>

<span data-ttu-id="8cb11-250">Un altro vantaggio di Docker è possibile compilare l'applicazione da un contenitore preconfigurato, come illustrato nella figura 8-13, pertanto non è necessario creare un computer di compilazione o di una macchina virtuale per compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-250">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="8cb11-251">È possibile utilizzare o di test compilazione contenitore eseguendolo in computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="8cb11-251">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="8cb11-252">Ma l'aspetto ancora più interessante è che è possibile utilizzare lo stesso contenitore di compilazione da pipeline dell'elemento di configurazione (integrazione continua).</span><span class="sxs-lookup"><span data-stu-id="8cb11-252">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="8cb11-253">**Figura 8-13**.</span><span class="sxs-lookup"><span data-stu-id="8cb11-253">**Figure 8-13**.</span></span> <span data-ttu-id="8cb11-254">Compilazione di bit di .NET da un contenitore di componenti</span><span class="sxs-lookup"><span data-stu-id="8cb11-254">Components building .NET bits from a container</span></span>

<span data-ttu-id="8cb11-255">Per questo scenario, si forniscono le [aspnetcore/microsoft-compilazione](https://hub.docker.com/r/microsoft/aspnetcore-build/) immagine, è possibile utilizzare per compilare e ottenere il ASP.NET Core app.</span><span class="sxs-lookup"><span data-stu-id="8cb11-255">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="8cb11-256">In un'immagine in base a cui viene inserito l'output di [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) immagine, che è un'immagine ottimizzata di runtime, come evidenziata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="8cb11-256">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="8cb11-257">L'immagine aspnetcore compilazione contiene tutto ciò che occorre per compilare un'applicazione ASP.NET di base, tra cui .NET Core, il SDK di ASP.NET, npm, Bower, Gulp e così via.</span><span class="sxs-lookup"><span data-stu-id="8cb11-257">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="8cb11-258">Abbiamo bisogno di queste dipendenze in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="8cb11-258">We need these dependencies at build time.</span></span> <span data-ttu-id="8cb11-259">Ma si desidera eseguire con l'applicazione in fase di esecuzione perché renderebbe l'immagine inutilmente grandi.</span><span class="sxs-lookup"><span data-stu-id="8cb11-259">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="8cb11-260">Nell'applicazione eShopOnContainers, è possibile compilare l'applicazione da un contenitore solo eseguendo le operazioni seguenti docker-compongono comando.</span><span class="sxs-lookup"><span data-stu-id="8cb11-260">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="8cb11-261">Figura 8-14 mostra questo comando in esecuzione dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="8cb11-261">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="8cb11-262">**Figura 8-14.**</span><span class="sxs-lookup"><span data-stu-id="8cb11-262">**Figure 8-14.**</span></span> <span data-ttu-id="8cb11-263">Compilazione dell'applicazione .NET da un contenitore</span><span class="sxs-lookup"><span data-stu-id="8cb11-263">Building your .NET application from a container</span></span>

<span data-ttu-id="8cb11-264">Come si può notare, il contenitore in cui è in esecuzione è la compilazione di ci\_1 contenitore.</span><span class="sxs-lookup"><span data-stu-id="8cb11-264">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="8cb11-265">Questa è basata sull'immagine di aspnetcore compilazione in modo che è possibile compilare e ottenere l'intera applicazione all'interno del contenitore invece che dal PC.</span><span class="sxs-lookup"><span data-stu-id="8cb11-265">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="8cb11-266">Vale a dire perché in realtà è la creazione e la compilazione di progetti .NET Core in Linux, perché tale contenitore è in esecuzione nell'host Docker Linux predefinito.</span><span class="sxs-lookup"><span data-stu-id="8cb11-266">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="8cb11-267">Il [docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file di immagine (parte di eShopOnContainers) contiene il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="8cb11-267">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="8cb11-268">Si noterà che avvia un contenitore di compilazione usando il [aspnetcore/microsoft-compilazione](https://hub.docker.com/r/microsoft/aspnetcore-build/) immagine.</span><span class="sxs-lookup"><span data-stu-id="8cb11-268">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

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

* <span data-ttu-id="8cb11-269">A partire da **2.0 di .NET Core**, `dotnet restore` comando viene eseguita automaticamente quando il `dotnet publish` comando viene eseguito.</span><span class="sxs-lookup"><span data-stu-id="8cb11-269">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="8cb11-270">Una volta installato e in esecuzione il contenitore della build, viene eseguito il ripristino dotnet .NET SDK e dotnet pubblicare comandi su tutti i progetti nella soluzione per compilare i bit di .NET.</span><span class="sxs-lookup"><span data-stu-id="8cb11-270">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="8cb11-271">In questo caso, poiché eShopOnContainers ha anche un SPA basato su TypeScript e angolare per il codice client, è anche necessario controllare le dipendenze di JavaScript con npm, ma tale operazione non è correlato ai bit di .NET.</span><span class="sxs-lookup"><span data-stu-id="8cb11-271">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="8cb11-272">Il dotnet pubblicare le compilazioni di comando e pubblica l'output compilato nella cartella di ogni progetto per il... cartella /obj/Docker/Publish, come illustrato nella figura 8-15.</span><span class="sxs-lookup"><span data-stu-id="8cb11-272">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="8cb11-273">**Figura 8-15.**</span><span class="sxs-lookup"><span data-stu-id="8cb11-273">**Figure 8-15.**</span></span> <span data-ttu-id="8cb11-274">Comando pubblicano i file binari generati dal dotnet</span><span class="sxs-lookup"><span data-stu-id="8cb11-274">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="8cb11-275">Creazione di immagini Docker da CLI</span><span class="sxs-lookup"><span data-stu-id="8cb11-275">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="8cb11-276">Dopo aver pubblicato l'output dell'applicazione per le cartelle correlate (all'interno di ogni progetto), il passaggio successivo consiste nel compilare effettivamente le immagini Docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-276">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="8cb11-277">A tale scopo, si utilizza la compilazione di docker-compose e docker-comporre i comandi, come illustrato nella figura 8-16.</span><span class="sxs-lookup"><span data-stu-id="8cb11-277">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="8cb11-278">**Nella figura 8-16.**</span><span class="sxs-lookup"><span data-stu-id="8cb11-278">**Figure 8-16.**</span></span> <span data-ttu-id="8cb11-279">Creazione di immagini Docker e i contenitori in esecuzione</span><span class="sxs-lookup"><span data-stu-id="8cb11-279">Building Docker images and running the containers</span></span>

<span data-ttu-id="8cb11-280">Nella figura 8-17, è possibile vedere come il docker-compose creare l'esecuzione del comando.</span><span class="sxs-lookup"><span data-stu-id="8cb11-280">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="8cb11-281">**Figura 8-17**.</span><span class="sxs-lookup"><span data-stu-id="8cb11-281">**Figure 8-17**.</span></span> <span data-ttu-id="8cb11-282">Le immagini Docker con la compilazione con docker-creare il comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="8cb11-282">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="8cb11-283">La differenza tra il docker-compose compilare e comporre docker dei comandi è che compongono docker le compilazioni e le immagini di avvio.</span><span class="sxs-lookup"><span data-stu-id="8cb11-283">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="8cb11-284">Quando si utilizza Visual Studio, tutti questi passaggi vengono eseguiti dietro le quinte.</span><span class="sxs-lookup"><span data-stu-id="8cb11-284">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="8cb11-285">Visual Studio compila l'applicazione .NET, crea le immagini Docker e consente di distribuire i contenitori nell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="8cb11-285">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="8cb11-286">Visual Studio offre funzionalità aggiuntive, ad esempio la possibilità di eseguire il debug ai contenitori in esecuzione in Docker, direttamente da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8cb11-286">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="8cb11-287">Qui il takeway generale è che si è in grado di compilare la stessa modalità della pipeline dell'elemento di configurazione/CD deve compilare l'applicazione, ovvero da un contenitore invece che da un computer locale.</span><span class="sxs-lookup"><span data-stu-id="8cb11-287">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="8cb11-288">Dopo aver create le immagini di, quindi è sufficiente eseguire le immagini Docker usando docker-comporre il comando.</span><span class="sxs-lookup"><span data-stu-id="8cb11-288">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="8cb11-289">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8cb11-289">Additional resources</span></span>

-   <span data-ttu-id="8cb11-290">**Compilazione di bit da un contenitore: configurazione della soluzione eShopOnContainers in un ambiente Windows CLI (dotnet CLI, Docker CLI e il codice di Visual Studio)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-up-in-a-Windows-CLI-Environment-(dotnet-CLI,-Docker-CLI-and-VS-code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="8cb11-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="8cb11-291">[Precedente] (data-driven-crud-microservice.md) [Avanti] (container.md-server-database)</span><span class="sxs-lookup"><span data-stu-id="8cb11-291">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
