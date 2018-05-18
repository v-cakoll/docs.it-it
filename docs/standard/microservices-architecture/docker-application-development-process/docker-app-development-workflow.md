---
title: Flusso di lavoro di sviluppo per app Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Flusso di lavoro di sviluppo per app Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 2eb205e85300f22108b866e8446d6730d89ae6cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="development-workflow-for-docker-apps"></a>Flusso di lavoro di sviluppo per app Docker

Il ciclo di vita dello sviluppo applicativo inizia al computer di ogni sviluppatore quando l'applicazione viene scritta usando un determinato linguaggio e viene testata in locale. Indipendentemente dal linguaggio, il framework e la piattaforma scelti, con questo flusso di lavoro lo sviluppatore scrive e testa sempre contenitori Docker, ma localmente.

Ogni contenitore, ovvero un'istanza di un'immagine Docker, include i componenti seguenti:

-   Un sistema operativo a scelta, come una distribuzione Linux, Windows Nano Server o Windows Server Core.

-   File aggiunti dallo sviluppatore, ovvero file binari dell'applicazione e così via.

-   Informazioni di configurazione, come impostazioni di ambiente e dipendenze.

## <a name="workflow-for-developing-docker-container-based-applications"></a>Flusso di lavoro per lo sviluppo di applicazioni Docker basate su contenitore

Questa sezione descrive il flusso di lavoro di sviluppo a *ciclo interno* per applicazioni Docker basate su contenitore. Flusso di lavoro a ciclo interno significa che non tiene conto del flusso di lavoro DevOps più ampio e si concentra solo sul lavoro di sviluppo eseguito sul computer dello sviluppatore. I passaggi iniziali per configurare l'ambiente non sono inclusi, in quanto sono eseguiti una sola volta.

Un'applicazione è costituita da servizi e raccolte aggiuntive, ossia dipendenze. Di seguito sono indicati i passaggi di base che si eseguono in genere quando si compila un'applicazione Docker, come illustrato nella figura 5-1.

![](./media/image1.png)

**Figura 5-1.** Flusso di lavoro passo per passo per lo sviluppo di applicazioni Docker in contenitori

Questa guida descrive nei dettagli l'intero processo e ogni passaggio principale è spiegato con riferimento all'ambiente Visual Studio.

Quando si usa un approccio di sviluppo editor/CLI, ad esempio codice Visual Studio e CLI di Docker in macOS o Windows, di solito è necessario conoscere ogni passaggio in modo più dettagliato rispetto all'uso di Visual Studio. Per altre informazioni sull'uso di un ambiente CLI, vedere l'e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](http://aka.ms/dockerlifecycleebook/) (Ciclo di vita di un'applicazione Docker in un contenitore con piattaforme e strumenti Microsoft).

Quando si usa Visual Studio 2015 o Visual Studio 2017, molti di questi passaggi sono gestiti automaticamente e questo migliora notevolmente la produttività. Ciò vale soprattutto quando si usa Visual Studio 2017 con applicazioni a più contenitori. Ad esempio, con un solo clic, Visual Studio aggiunge ai progetti il Dockerfile e il file docker-compose.yml con la configurazione per l'applicazione. Quando si esegue l'applicazione in Visual Studio, viene creata l'immagine Docker e l'applicazione a più contenitori viene eseguita direttamente in Docker; è anche possibile eseguire il debug di diversi contenitori contemporaneamente. Queste funzionalità rendono lo sviluppo più veloce.

Tuttavia, anche se Visual Studio automatizza questi passaggi, ciò non significa che non sia necessario sapere cosa succede dietro le quinte con Docker. Perciò il materiale sussidiario che segue descrive dettagliatamente ogni passaggio.

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Passaggio 1. Iniziare a scrivere il codice e ad abbozzare l'applicazione o il servizio

Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza Docker. La differenza è che, quando si sviluppa per Docker, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale. Il contenitore può essere di tipo Linux o Windows.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Configurare l'ambiente locale con Visual Studio

Per iniziare, accertarsi che sia installato [Docker Community Edition (CE)](https://www.docker.com/community-edition) per Windows, come spiegato nelle istruzioni seguenti:

[Introduzione a Docker CE per Windows](https://docs.docker.com/docker-for-windows/)

Inoltre è necessario avere installato Visual Studio 2017. Questa versione è preferibile rispetto a Visual Studio 2015 con il componente aggiuntivo Visual Studio Tools for Docker perché Visual Studio 2017 è dotato di un supporto più avanzato per Docker, ad esempio supporta il debug dei contenitori. Visual Studio 2017 include gli strumenti per Docker se è stato selezionato il carico di lavoro **.NET Core e Docker** durante l'installazione, come illustrato nella figura 5-2.

![](./media/image3.png)

**Figura 5-2**. Selezione del carico di lavoro **.NET Core e Docker** durante l'installazione di Visual Studio 2017

È possibile iniziare a scrivere il codice dell'applicazione in .NET normale, di solito in .NET Core se si prevede di usare contenitori, anche prima di attivare Docker nell'applicazione e di eseguire la distribuzione e i test in Docker, ma si consiglia di iniziare a lavorare in Docker appena possibile, perché quello sarà l'ambiente reale e gli eventuali problemi possono essere individuati velocemente. Si consiglia di procedere in questo modo perché Visual Studio facilita così tanto il lavoro con Docker da diventare quasi trasparente, soprattutto quando lo si usa per eseguire il debug di applicazioni a più contenitori.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Get started with Docker CE for Windows (Introduzione a Docker CE per Windows)**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio 2017**
    [*https://www.visualstudio.com/downloads/*](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Passaggio 2. Creare un Dockerfile correlato a un'immagine di base .NET esistente

È necessario un Dockerfile per ogni immagine personalizzata che si desidera creare; è necessario un Dockerfile per ogni contenitore da distribuire, sia che si esegua la distribuzione automaticamente da Visual Studio o manualmente con la CLI di Docker: comandi docker run e docker-compose. Se l'applicazione contiene un solo servizio personalizzato, è necessario un solo Dockerfile. Se l'applicazione contiene più servizi, come in un'architettura a microservizi, è necessario un Dockerfile per ogni servizio.

Il Dockerfile viene inserito nella cartella radice dell'applicazione o del servizio. Contiene i comandi che indicano a Docker come configurare ed eseguire l'applicazione o il servizio in un contenitore. È possibile creare manualmente un Dockerfile nel codice e aggiungerlo al progetto insieme alle dipendenze .NET.

Con Visual Studio e i relativi strumenti per Docker questa attività richiede solo pochi clic del mouse. Quando si crea un nuovo progetto in Visual Studio 2017, è disponibile un'opzione denominata **Abilita supporto Docker**, come illustrato nella figura 5-3.

![](./media/image5.png)

**Figura 5-3**. Abilitazione del supporto Docker quando si crea un nuovo progetto in Visual Studio 2017

È possibile abilitare il supporto Docker in un progetto nuovo o esistente facendo clic con il pulsante destro del mouse sul file di progetto in Visual Studio e selezionando l'opzione **Aggiungi Supporto Docker**, come illustrato nella figura 5-4.

![](./media/image6.png)

**Figura 5-4**. Abilitazione del supporto Docker in un progetto Visual Studio 2017 esistente

Questa azione eseguita su un progetto, come un'applicazione Web ASP.NET o un servizio Web API, aggiunge un Dockerfile al progetto con la configurazione necessaria. Aggiunge anche un file docker-compose.yml per l'intera soluzione. Nelle sezioni seguenti sono descritte le informazioni da inserire in ciascuno di questi file. Visual Studio fa tutto questo automaticamente, ma è utile sapere cosa deve contenere un Dockerfile.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>Opzione A: creazione di un progetto con un'immagine Docker .NET ufficiale esistente

In genere si crea un'immagine personalizzata per il contenitore sopra un'immagine di base che è possibile ottenere da un repository ufficiale nel registro [Hub Docker](https://hub.docker.com/). Questo è esattamente ciò che accade dietro le quinte quando si attiva il supporto Docker in Visual Studio. Il Dockerfile userà un'immagine aspnetcore esistente.

In precedenza si è visto le immagini e repository Docker da usare in base al framework e al sistema operativo scelto. Ad esempio, se si desidera usare ASP.NET Core (Linux o Windows), l'immagine da utilizzare è microsoft/aspnetcore:2.0. Pertanto è sufficiente specificare l'immagine Docker di base che sarà usata per il contenitore. Lo si fa aggiungendo FROM microsoft/aspnetcore:2.0 al Dockerfile. Visual Studio esegue l'operazione automaticamente, ma se si aggiornasse la versione, verrebbe aggiornato anche questo valore.

L'uso di un repository ufficiale di immagini .NET di Docker Hub con un numero di versione garantisce che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.

L'esempio seguente illustra un esempio di Dockerfile per un contenitore ASP.NET Core.

```Dockerfile
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

In questo caso il contenitore è basato sulla versione 2.0 dell'immagine ASP.NET Core Docker ufficiale (multi-arch per Linux e Windows). Si tratta dell'impostazione `FROM microsoft/aspnetcore:2.0`. Per altre informazioni su questa immagine di base, vedere la pagina [ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) (Immagine ASP.NET Core Docker) e la pagina [.NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/) (Immagine .NET Core Docker). Nel Dockerfile è necessario anche indicare al Docker di rimanere in ascolto sulla porta TCP che sarà usata in fase di esecuzione, in questo caso la porta 80 configurata con l'impostazione EXPOSE.

Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso. Ad esempio, la riga ENTRYPOINT con \["dotnet", "MySingleContainerWebApp.dll"\] indica a Docker di eseguire un'applicazione .NET Core. Se si usa l'SDK e la CLI di .NET Core, ovvero la CLI dotnet per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa. In sostanza la riga ENTRYPOINT e altre impostazioni saranno diverse a seconda del linguaggio e della piattaforma scelti per l'applicazione.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Compilazione di immagini Docker per applicazioni .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](../../../core/docker/building-net-docker-images.md)

-   **Creare un'immagine**. Nella documentazione ufficiale di Docker.
    [*https://docs.docker.com/engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>Uso di repository di immagini multi-arch

Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows. Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows. Ad esempio, il repository [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) disponibile nel registro Docker Hub fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di repository.

Se si specifica un tag, ci si rivolge a una piattaforma esplicita come nei casi seguenti:

-   **microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

Ma, e questa è una novità da metà 2017, se si specifica lo stesso nome di immagine, anche con lo stesso tag, le nuove immagini multi-arch, come l'immagine aspnetcore che supporta multi-arch, useranno la versione Linux o Windows in base al sistema operativo host Docker che si sta distribuendo, come illustrato nell'esempio seguente:

-   **microsoft/aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

In questo modo, se si esegue il pull di un'immagine da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome di immagine da un host Linux si ottiene la variante Linux.

### <a name="option-b-creating-your-base-image-from-scratch"></a>Opzione B: creazione dell'immagine di base da zero

È possibile creare un'immagine Docker di base da zero. Questo scenario non è consigliato se non si conosce bene Docker, ma se si vuole creare la propria immagine di base è possibile farlo.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Immagini multi-arch .NET Core**.
https://github.com/dotnet/announcements/issues/14 
-   **Creare un'immagine di base**. Documentazione ufficiale di Docker.
    [*https://docs.docker.com/engine/userguide/eng-image/baseimages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Passaggio 3. Creare le immagini Docker personalizzate e incorporare l'applicazione o il servizio in esse

Per ogni servizio dell'applicazione è necessario creare un'immagine correlata. Se l'applicazione è costituita da un singolo servizio o applicazione Web, è sufficiente una singola immagine.

Si noti che le immagini Docker vengono create automaticamente in Visual Studio. I passaggi seguenti sono necessari solo per il flusso di lavoro editor/CLI e sono descritti per chiarire meglio ciò che succede dietro le quinte.

Lo sviluppatore deve eseguire lo sviluppo e i test localmente finché non esegue il push di una funzionalità o di una modifica completa nel sistema di controllo del codice sorgente, ad esempio in GitHub. Ciò significa che è necessario creare le immagini Docker e distribuire i contenitori in un host Docker locale, ovvero una VM Windows o Linux, nonché eseguire, testare ed eseguire il debug in tali contenitori locale.

Per creare un'immagine personalizzata nell'ambiente locale tramite la CLI di Docker e il Dockerfile, è possibile usare il comando docker build, come illustrato nella figura 5-5.

![](./media/image8.png)

**Figura 5-5**. Creazione di un'immagine Docker personalizzata

Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è possibile generare innanzitutto una cartella distribuibile con le raccolte .NET e i file binari necessari eseguendo dotnet publish e quindi usando il comando docker build.

Verrà creata così un'immagine Docker con il nome cesardl/netcore-webapi-microservice-docker:first. In questo caso :first è un tag che rappresenta una versione specifica. È possibile ripetere questo passaggio per ogni immagine personalizzata da creare per l'applicazione Docker composta.

Quando un'applicazione è costituita da più contenitori, è un'applicazione a più contenitori, è anche possibile usare il comando docker-compose up --build per compilare tutte le immagini correlate con un singolo comando usando i metadati esposti nei file docker-compose.yml correlati.

È possibile trovare le immagini esistenti nel repository locale tramite il comando docker images, come illustrato nella figura 5-6.

![](./media/image9.png)

**Figura 5-6.** Visualizzazione di immagini esistente con il comando docker images

### <a name="creating-docker-images-with-visual-studio"></a>Creazione di immagini Docker con Visual Studio

Quando si usa Visual Studio per creare un progetto con il supporto Docker, non si crea un'immagine in modo esplicito. L'immagine viene invece creata automaticamente quando si premere F5 e si esegue l'applicazione o il servizio Docker. Questo passaggio è automatico e invisibile in Visual Studio, ma è importante sapere cosa succede dietro le quinte.

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Passaggio 4. Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori

Il file [docker compose.yml](https://docs.docker.com/compose/compose-file/) consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione.

Per usare un file docker-compose.yml, è necessario creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello nell'esempio seguente:

```yml
version: '3'
  
services:

  webmvc:
    image: eshop/web
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
    ports:
      - "80:80"
    depends_on:
      - catalog.api
      - ordering.api

  catalog.api:
    image: eshop/catalog.api
    environment: 
      - ConnectionString=Server=sql.data;Database=CatalogDB;…
    ports:
      - "81:80"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=OrderingDb;…
    ports:
      - "82:80"
    extra_hosts:
      - "CESARDLBOOKVHD:10.0.75.1"
    depends_on:
      - sql.data

  sql.data:
    image: mssql-server-linux:latest
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"

```

Si noti che questo file docker-compose.yml è una versione semplificata e unita. Contiene dati di configurazione statici per ogni contenitore, ad esempio il nome dell'immagine personalizzata, sempre applicabili, nonché informazioni di configurazione che potrebbero dipendere dall'ambiente di distribuzione, ad esempio la stringa di connessione. In seguito si vedrà come suddividere la configurazione di docker-compose.yml in più file docker-compose e sostituire valori a seconda del tipo di ambiente e di esecuzione, ovvero debug o release.

L'esempio del file docker-compose.yml definisce cinque servizi: il servizio webmvc, che è un'applicazione Web; due microservizi, ovvero catalog.api e ordering.api; un contenitore origine dati, sql.data, basato su SQL Server per Linux eseguito come contenitore. Ogni servizio è distribuito come contenitore, quindi è necessaria un'immagine Docker per ciascuno.

Il file docker-compose.yml specifica non solo quali contenitori vengono usati, ma come sono configurati singolarmente. Ad esempio, la definizione del contenitore webmvc nel file .yml:

-   Usa un'immagine eshop/web:latest precompilata. Tuttavia, è anche possibile configurare l'immagine in modo che sia compilata come parte dell'esecuzione di docker-compose con una configurazione aggiuntiva basata su una sezione build: nel file docker-compose.

-   Inizializza due variabili di ambiente, ovvero CatalogUrl e OrderingUrl.

-   Inoltra la porta 80 esposta sul contenitore alla porta esterna 80 sul computer host.

-   Collega l'app Web al catalogo e al servizio di ordinazione con l'impostazione depends\_on. In questo modo il servizio attende fino a quando vengono avviati i servizi.

Il file docker-compose.yml sarà esaminato di nuovo in una sezione successiva in cui sarà descritto come implementare microservizi e app a più contenitori.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Utilizzo di docker-compose.yml in Visual Studio 2017

Quando si aggiunge il supporto per soluzioni Docker a un progetto di servizio in una soluzione Visual Studio, come illustrato nella figura 5-7, Visual Studio aggiunge al progetto un Dockerfile e aggiunge una sezione di servizio (progetto) alla soluzione con i file docker-compose.yml. Questo è un modo semplice per iniziare a comporre una soluzione a più contenitori. È quindi possibile aprire i file docker-compose.yml e aggiornarli con funzionalità aggiuntive.

![](./media/image6.png)

**Figura 5-7**. Aggiunta del supporto Docker in Visual Studio 2017 facendo clic con il pulsante destro del mouse su un progetto ASP.NET Core

Aggiungendo il supporto Docker in Visual Studio non solo viene aggiunto il Dockerfile al progetto, ma vengono aggiunte le informazioni di configurazione a più file docker-compose.yml globali che sono impostati a livello di soluzione.

Dopo aver aggiunto il supporto Docker alla soluzione in Visual Studio, si noterà anche un nuovo nodo in Esplora soluzioni, nel file di progetto docker-compose.dcproj, che contiene i file docker-compose.yml aggiunti, come illustrato nella figura 5-8.

![](./media/image11.PNG)

**Figura 5-8**. Il nodo dell'albero **docker-compose** aggiunto in Esplora soluzioni di Visual Studio 2017

È possibile distribuire un'applicazione a più contenitori con un file docker-compose.yml singolo usando il comando docker-compose up. Tuttavia Visual Studio ne aggiunge un gruppo, perciò è possibile sostituire i valori a seconda dell'ambiente, ovvero sviluppo o produzione, e del tipo di esecuzione, ossia release o debug. Questa funzionalità sarà spiegata nelle sezioni successive.

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Passaggio 5. Compilare ed eseguire l'applicazione Docker

Se l'applicazione ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, ovvero una VM o un server fisico. Se invece l'applicazione contiene più servizi, è possibile distribuirla come applicazione composta, usando un unico comando della CLI, ossia docker-compose up, o con Visual Studio, che userà lo stesso comando dietro le quinte. Le diverse opzioni sono esaminate di seguito.

### <a name="option-a-running-a-single-container-with-docker-cli"></a>Opzione A: esecuzione di un singolo contenitore con la CLI di Docker

È possibile eseguire un contenitore Docker usando il comando docker run, come illustrato nella figura 5-9:

```console
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**Figura 5-9**. Esecuzione di un contenitore Docker usando il comando docker run

In questo caso il comando associa la porta interna 5000 del contenitore alla porta 80 del computer host. Ciò significa che l'host è in ascolto sulla porta 80 e inoltra alla porta 5000 nel contenitore.

### <a name="option-b-running-a-multi-container-application"></a>Opzione B: esecuzione di un'applicazione a più contenitori

Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà composta da più servizi, perciò sarà necessario eseguire un'applicazione a più contenitori, come illustrato nella figura 5-10.

![](./media/image14.png)

**Figura 5-10**. VM con contenitori Docker distribuiti

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>Esecuzione di un'applicazione a più contenitori con la CLI di Docker

Per eseguire un'applicazione a più contenitori con la CLI di Docker, è possibile eseguire il comando docker-compose up. Questo comando usa il file docker-compose.yml disponibile a livello di soluzione per distribuire un'applicazione a più contenitori. La figura 5-11 mostra i risultati che si ottengono quando si esegue il comando dalla directory principale del progetto, che contiene il file docker-compose.yml.

![](./media/image15.png)

**Figura 5-11**. Esempio di risultati ottenuti eseguendo il comando docker-compose up

Dopo l'esecuzione del comando docker-compose up, l'applicazione e i contenitori correlati vengono distribuiti nell'host Docker, come illustrato nella rappresentazione di VM della figura 5-10.

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>Esecuzione e debug di un'applicazione a più contenitori con Visual Studio 

Eseguire un'applicazione a più contenitori con Visual Studio 2017 è molto semplice. Non solo è possibile eseguire l'applicazione a più contenitori, ma è possibile eseguire il debug di tutti i relativi contenitori direttamente da Visual Studio impostando punti di interruzione normali.

Come accennato in precedenza, ogni volta che si aggiungere il supporto Docker a un progetto all'interno di una soluzione, il progetto è configurato nel file docker-compose.yml globale, a livello di soluzione, che consente di eseguire l'intera soluzione o di eseguirne il debug in una sola volta. Visual Studio avvia un solo contenitore per ogni progetto che ha il supporto Docker abilitato ed esegue automaticamente tutti i passaggi interni, ovvero pubblicazione dotnet, compilazione docker, ecc.

La cosa importante è che, come illustrato nella figura 5-12, in Visual Studio 2017 è presente un ulteriore comando **Docker** per il tasto funzione F5. Questa opzione consente di eseguire un'applicazione a più contenitori o di eseguirne il debug eseguendo tutti i contenitori definiti nei file docker-compose.yml a livello di soluzione. Grazie alla capacità di eseguire il debug delle soluzioni a più contenitori, è possibile impostare più punti di interruzione, ciascuno in un progetto (contenitore) diverso, e durante il debug da Visual Studio l'esecuzione viene arrestata in corrispondenza dei punti di interruzione definiti in progetti diversi ed eseguiti in contenitori diversi.

![](./media/image16.png)

**Figura 5-12**. Esecuzione di applicazioni a più contenitori in Visual Studio 2017

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Distribuire un contenitore ASP.NET in un host Docker remoto**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Una nota sul test e la distribuzione con agenti di orchestrazione

I comandi docker-compose up e docker run, o l'esecuzione e il debug dei contenitori in Visual Studio, sono adeguati per eseguire test sui contenitori nell'ambiente di sviluppo. Questo approccio invece non si deve usare se la destinazione è costituita da cluster e agenti di orchestrazione Docker come Swarm, Mesosphere DC/OS o Kubernetes. Se si usa un cluster come la [modalità Docker Swarm](https://docs.docker.com/engine/swarm/), disponibile in Docker CE per Windows e Mac dalla versione 1.12, è necessario eseguire la distribuzione e i test con altri comandi, ad esempio [docker service create](https://docs.docker.com/engine/reference/commandline/service_create/) per servizi singoli. Se si distribuisce un'applicazione composta da diversi contenitori, usare [docker compose bundle](https://docs.docker.com/compose/reference/bundle/) e [docker deploy myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) per distribuire l'applicazione composta come *stack*. Per altre informazioni, vedere il post di blog [Introducing Experimental Distributed Application Bundles](https://blog.docker.com/2016/06/docker-app-bundle/) (Presentazione di bundle applicativi distribuiti sperimentali) nella documentazione di Docker nel sito di Docker.

Per [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) si usano comandi di distribuzione e script diversi.

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Passaggio 6. Testare l'applicazione Docker usando l'host Docker locale

Questo passaggio varia in base a ciò che l'applicazione sta facendo. In un'applicazione Web .NET Core semplice che viene distribuita come contenitore o servizio singolo è possibile accedere al servizio aprendo un browser nell'host Docker e passando a quel sito, come illustrato nella figura 5-13. Se la configurazione nel Dockerfile abbina il contenitore a una porta dell'host diversa dalla 80, includere la porta host nell'URL.

![](./media/image18.png)

**Figura 5-13**. Esempio di test dell'applicazione Docker in locale mediante localhost

Se localhost non punta all'IP dell'host Docker, come succede per impostazione predefinita quando si usa Docker CE, per passare al servizio usare l'indirizzo IP della scheda di rete del computer.

Si noti che questo URL nel browser usa la porta 80 per lo specifico contenitore di esempio di cui si tratta. Tuttavia internamente le richieste vengono reindirizzate alla porta 5000 perché è stato distribuito in questo modo con il comando docker run, come illustrato nel passaggio precedente.

È anche possibile testare l'applicazione usando curl dal terminale, come illustrato nella figura 5-14. In un'installazione di Docker in Windows, il valore IP dell'host Docker predefinito è sempre 10.0.75.1 in aggiunta all'indirizzo IP effettivo del computer.

![](./media/image19.png)

**Figura 5-14**. Esempio di test dell'applicazione Docker in locale mediante curl

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Test e debug di contenitori con Visual Studio 2017

Quando si eseguono contenitori e se ne esegue il debug con Visual Studio 2017, è possibile eseguire il debug dell'applicazione .NET nello stesso modo che si userebbe per l'esecuzione senza contenitori.

### <a name="testing-and-debugging-without-visual-studio"></a>Test e debug senza Visual Studio

Se si sviluppa usando l'approccio editor/CLI, eseguire il debug dei contenitori è più difficile ed è preferibile farlo tramite la generazione di tracce.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Debug delle applicazioni in un contenitore Docker locale**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker. Compilare, eseguire il debug e distribuire app ASP.NET Core con Docker.** Video.
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Flusso di lavoro semplificato per lo sviluppo di contenitori con Visual Studio

Il flusso di lavoro quando si usa Visual Studio è molto più semplice rispetto all'uso dell'approccio editor/CLI. La maggior parte dei passaggi richiesti da Docker correlati ai file Dockerfile e docker-compose.yml sono nascosti o semplificati da Visual Studio, come illustrato nella figura 5-15.

![](./media/image20.png)

**Figura 5-15**. Flusso di lavoro semplificato per lo sviluppo con Visual Studio

Inoltre è sufficiente eseguire una sola volta il passaggio 2, ovvero l'aggiunta del supporto Docker ai progetti. Pertanto il flusso di lavoro è simile alle attività di sviluppo normale quando si usa .NET per qualsiasi altro tipo di sviluppo. È necessario sapere cosa succede dietro le quinte, ad esempio il processo di creazione delle immagini, quali immagini di base vengono usate, la distribuzione dei contenitori e così via; in alcuni casi è anche necessario modificare il file Dockerfile o docker-compose.ym per personalizzare i comportamenti. Se si usa Visual Studio la maggior parte del lavoro viene notevolmente semplificata e la produttività è maggiore.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Steve Lasker. .NET Docker Development with Visual Studio 2017 (Sviluppo di Docker .NET con Visuali Studio 2017)**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey T. Fritz. Put a .NET Core App in a Container with the new Docker Tools for Visual Studio (Inserire un'app di .NET Core in un contenitore con i nuovi strumenti di Docker per Visual Studio)**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Uso dei comandi di PowerShell in un Dockerfile per configurare contenitori Windows 

I [contenitori Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) consentono di convertire applicazioni Windows esistenti in immagini Docker e distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker. Per usare i contenitori Windows si eseguono i comandi di PowerShell in Dockerfile, come illustrato nell'esempio seguente:

```Dockerfile
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

In questo caso si usa un'immagine di base di Windows Server Core (impostazione FROM) e si installa IIS con un comando di PowerShell (impostazione RUN). In modo analogo è possibile usare i comandi di PowerShell anche per configurare componenti aggiuntivi come ASP.NET 4. x, .NET 4.6 o qualsiasi altro software Windows. Ad esempio il comando seguente in un Dockerfile configura ASP.NET 4.5:

```Dockerfile
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Risorse aggiuntive

-   **aspnet-docker/Dockerfile.** Comandi di Powershell di esempio eseguibili da dockerfile per includere funzionalità di Windows.
    [*https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[Previous] (index.md) [Next] (../net-core-single-containers-linux-windows-server-hosts/index.md)
