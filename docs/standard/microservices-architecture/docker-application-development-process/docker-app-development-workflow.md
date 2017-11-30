---
title: Flusso di lavoro di sviluppo per le app di Docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Flusso di lavoro di sviluppo per le app di Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 5a53aee4261a5a0bfc25b3520c50cf505b84f287
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="development-workflow-for-docker-apps"></a>Flusso di lavoro di sviluppo per le app di Docker

Il ciclo di vita di sviluppo di applicazioni inizia in corrispondenza di ogni macchina di sviluppatore, in cui lo sviluppatore codici l'applicazione utilizzando la lingua desiderata e sottopone a test in locale. Indipendentemente da quali lingua, framework e piattaforma sceglie lo sviluppatore, con questo flusso di lavoro, lo sviluppatore è sempre lo sviluppo e test contenitori di Docker, ma in questo modo localmente.

Ogni contenitore (un'istanza di un'immagine Docker) include i componenti seguenti:

-   Una selezione del sistema operativo (ad esempio, una distribuzione Linux, Windows Nano Server o Windows Server Core).

-   File aggiunti dallo sviluppatore (file binari dell'applicazione e così via).

-   Informazioni di configurazione (impostazioni di ambiente e le dipendenze).

## <a name="workflow-for-developing-docker-container-based-applications"></a>Flusso di lavoro per lo sviluppo di applicazioni basate sul contenitore Docker

Questa sezione viene descritto il *interna ciclo* flusso di lavoro di sviluppo per applicazioni basate sul contenitore Docker. Il flusso di lavoro ciclo interno significa è non tenendo conto del flusso di lavoro più ampia di DevOps e prevede solo il lavoro di sviluppo eseguito sul computer dello sviluppatore. I passaggi iniziali per configurare l'ambiente non sono inclusi, in quanto quelle vengono eseguite una sola volta.

Un'applicazione è costituita da propri servizi più librerie aggiuntive (dipendenze). Di seguito sono indicati i passaggi di base che accettano in genere quando si compila un'applicazione di Docker, come illustrato nella figura 5-1.

![](./media/image1.png)

**Figura 5-1.** Flusso di lavoro dettagliata per lo sviluppo di App contenitore Docker

In questa guida è descritta in dettaglio l'intero processo e ogni passaggio principale è illustrato concentrandosi su un ambiente di Visual Studio.

Quando si utilizza un approccio di sviluppo editor/CLI (ad esempio, codice di Visual Studio più CLI di Docker in macOS o Windows), è necessario conoscere ogni passaggio, in genere in modo più dettagliato rispetto all'utilizzo di Visual Studio. Per ulteriori informazioni sull'utilizzo in un ambiente di CLI, vedere l'e-book [ciclo di vita dell'applicazione contenitore di Docker con Platforms Microsoft e strumenti](http://aka.ms/dockerlifecycleebook/).

Quando si utilizza Visual Studio 2015 o Visual Studio 2017, molti di questi passaggi vengono gestiti automaticamente, che migliora la produttività. Ciò vale soprattutto quando si utilizza Visual Studio 2017 e le applicazioni multi-contenitore di destinazione. Ad esempio, con un solo clic, Visual Studio aggiunge il file Dockerfile e docker compose.yml ai progetti con la configurazione dell'applicazione. Quando si esegue l'applicazione in Visual Studio, crea l'immagine di Docker e si esegue l'applicazione contenitore più direttamente in Docker; consente anche di eseguire il debug di diversi contenitori in una sola volta. Queste funzionalità verranno migliorare la velocità di sviluppo.

Tuttavia, solo perché Visual Studio rende automatici i passaggi non significa che non è necessario sapere cosa è on sotto con Docker. Nelle istruzioni che segue, è pertanto in dettaglio ogni passaggio.

![](./media/image2.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Passaggio 1. Avviare la codifica e creare l'applicazione iniziale o una linea di base del servizio

Sviluppo di un'applicazione di Docker è simile a quello che si sviluppa un'applicazione senza Docker. La differenza è che quando si sviluppa per Docker, si distribuisce e si verifica l'applicazione o i servizi in esecuzione all'interno di contenitori di Docker nell'ambiente locale. Il contenitore può essere un contenitore di Linux o un contenitore di Windows.

### <a name="set-up-your-local-environment-with-visual-studio"></a>Configurare l'ambiente locale con Visual Studio

Per iniziare, accertarsi di avere [Docker Community Edition (CE)](https://www.docker.com/community-edition) per Windows installato, come illustrato nelle istruzioni seguenti:

[Introduzione a Docker CE per Windows](https://docs.docker.com/docker-for-windows/)

Inoltre, è necessario Visual Studio 2017, che installata. Questo è preferibile Visual Studio 2015 con Visual Studio Tools per Docker aggiuntivo, poiché Visual Studio 2017 ha più supporto avanzato per Docker, come il supporto per il debug di contenitori. Visual Studio 2017 include gli strumenti per Docker se è stata selezionata la **.NET Core e Docker** carico di lavoro durante l'installazione, come illustrato nella figura 5-2.

![](./media/image3.png)

**Figura 5-2**. Selezione di **.NET Core e Docker** carico di lavoro durante l'installazione di Visual Studio 2017

È possibile avviare la generazione di codice dell'applicazione in .NET normale (in genere in .NET Core se si prevede di usare i contenitori) anche prima dell'abilitazione di Docker nell'applicazione e la distribuzione e test in Docker. Tuttavia, è consigliabile iniziare lavorando Docker appena possibile, perché che sarà l'ambiente reale e di eventuali problemi possono essere individuati appena possibile. Questo è consigliabile in quanto Visual Studio rende più facile lavorare con Docker che quasi sembra trasparente, ad esempio durante il debug di applicazioni multi-contenitore da Visual Studio.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Introduzione a Docker CE per Windows**
    [*https://docs.docker.com/docker-for-windows/*](https://docs.docker.com/docker-for-windows/)

-   **Visual Studio 2017**
    [*https://www.visualstudio.com/vs/visual-studio-2017/*](https://www.visualstudio.com/vs/visual-studio-2017/)

![](./media/image4.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Passaggio 2. Creare un Dockerfile correlato a un'immagine di base .NET esistente

È necessario un Dockerfile per ogni immagine personalizzata che si desidera compilare; è necessario un Dockerfile per ogni contenitore da distribuire, anche se vengono distribuiti automaticamente da Visual Studio oppure manualmente, utilizzando l'interfaccia CLI di Docker (esecuzione di docker e docker-comporre comandi). Se l'applicazione contiene un singolo servizio personalizzato, è necessario un Dockerfile singolo. Se l'applicazione contiene più servizi (come in un'architettura di microservizi), è necessario un Dockerfile per ogni servizio.

Dockerfile viene inserito nella cartella radice dell'applicazione o del servizio. Contiene i comandi che indicano come configurare ed eseguire l'applicazione o servizio in un contenitore di Docker. È possibile creare manualmente un Dockerfile nel codice e aggiungerlo al progetto e le dipendenze di .NET.

Con Visual Studio e dei relativi strumenti di Docker, questa attività richiede solo pochi clic del mouse. Quando si crea un nuovo progetto in Visual Studio 2017, è disponibile un'opzione denominata **supporto contenitore abilitare (Docker)**, come illustrato nella figura 5-3.

![](./media/image5.png)

**Figura 5-3**. Abilitazione del supporto di Docker quando si crea un nuovo progetto in Visual Studio 2017

È inoltre possibile abilitare il supporto di Docker in un progetto nuovo o esistente facendo clic sul file di progetto in Visual Studio e selezionando l'opzione **Aggiungi Docker progetto supporta**, come illustrato nella figura 5-4.

![](./media/image6.png)

**Figura 5-4**. Abilitazione del supporto di Docker in un progetto di Visual Studio 2017 esistente

Questa azione su un progetto (ad esempio, un'applicazione Web ASP.NET o un servizio Web API) aggiunge un Dockerfile per il progetto con la configurazione necessaria. Viene inoltre aggiunto un file di docker compose.yml per l'intera soluzione. Nelle sezioni seguenti vengono descritte le informazioni da inserire in ciascuno di questi file. Visual Studio di eseguire questa operazione, ma è utile comprendere cosa deve essere posizionato in un Dockerfile.

### <a name="option-a-creating-a-project-using-an-existing-official-net-docker-image"></a>Opzione a: creazione di un progetto con un'immagine Docker .NET ufficiale esistente

È in genere creare un'immagine personalizzata per il contenitore all'inizio di un'immagine di base è possibile ottenere da un repository ufficiale al [Hub Docker](https://hub.docker.com/) Registro di sistema. Che è esattamente ciò che accade dietro le quinte quando si abilita il supporto di Docker in Visual Studio. Il Dockerfile utilizzerà un'immagine aspnetcore esistente.

In precedenza spiegare le immagini Docker e il repository è possibile utilizzare, a seconda del framework e del sistema operativo scelto. Ad esempio, se si desidera utilizzare ASP.NET Core (Linux o Windows), l'immagine da utilizzare è microsoft / aspnetcore:2.0. Pertanto, è sufficiente specificare quale immagine di Docker base da utilizzare per il contenitore. A tale scopo, l'aggiunta di da microsoft / aspnetcore:2.0 per i Dockerfile. Questo verrà eseguito automaticamente da Visual Studio, ma se fosse necessario aggiornare la versione, si aggiorna il valore.

L'utilizzo di un repository di immagini .NET ufficiale dall'Hub Docker con un numero di versione garantisce che la stessa funzionalità del linguaggio disponibili in tutti i computer (tra cui sviluppo, test e produzione).

Nell'esempio seguente viene illustrato un esempio di Dockerfile per un contenitore di ASP.NET Core.

```
FROM microsoft/aspnetcore:2.0
  
ARG source
  
WORKDIR /app
  
EXPOSE 80
  
COPY ${source:-obj/Docker/publish} .
  
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

In questo caso, il contenitore è basato sulla versione 2.0 dell'immagine di ASP.NET Core Docker ufficiale (multi-arch per Linux e Windows). Si tratta dell'impostazione `FROM microsoft/aspnetcore:2.0`. (Per ulteriori informazioni su questa immagine di base, vedere il [ASP.NET Core Docker immagine](https://hub.docker.com/r/microsoft/aspnetcore/) pagina e [.NET Core Docker immagine](https://hub.docker.com/r/microsoft/dotnet/) pagina.) Nel documento Dockerfile, è necessario anche indicano a Docker in ascolto sulla porta TCP che verrà utilizzato in fase di esecuzione (in questo caso, la porta 80, come configurato con l'impostazione di ESPORRE).

È possibile specificare ulteriori impostazioni di configurazione in Dockerfile, a seconda del linguaggio e il framework in uso. Ad esempio, la riga del punto di ingresso con \["dotnet", "MySingleContainerWebApp.dll"\] indica Docker per eseguire un'applicazione .NET Core. Se si utilizza il SDK e .NET Core CLI (dotnet CLI) per compilare ed eseguire l'applicazione .NET, questa impostazione potrebbe essere diversa. La riga inferiore è che la riga del punto di ingresso e altre impostazioni saranno diverse a seconda della lingua e la piattaforma che scelto per l'applicazione.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Creazione di immagini Docker per le applicazioni .NET Core**
    [*https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images*](https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images)

-   **Compilare la propria immagine**. Nella documentazione ufficiale di Docker.
    [*https://docs.docker.com/Engine/tutorials/dockerimages/*](https://docs.docker.com/engine/tutorials/dockerimages/)

### <a name="using-multi-arch-image-repositories"></a>Utilizzando repository più arch immagine

Un singolo repository può contenere le varianti della piattaforma, ad esempio un'immagine Linux e un'immagine di Windows. Questa funzionalità consente ai fornitori come Microsoft (creatori di immagine di base) creare un unico repository per coprire più piattaforme (ad esempio Linux e Windows). Ad esempio, il [microsoft/dotnet](https://hub.docker.com/r/microsoft/aspnetcore/) repository disponibile nel Registro di sistema Hub Docker offre supporto per Linux e Windows Nano Server con lo stesso nome di repository.

Se si specifica un tag, una piattaforma esplicita come nei casi seguenti:

-   **Microsoft/aspnetcore:2.0.0-jessie**

        .NET Core 2.0 runtime-only on Linux 

-   **Microsoft/aspnetcore:2.0.0-nanoserver**

        .NET Core 2.0 runtime-only on Windows Nano Server

Ma e questo è nuovo dal mid 2017, se si specifica il nome dell'immagine stessa, anche con lo stesso tag, le nuove immagini multi-arch (ad esempio, l'immagine di aspnetcore che supporta multi-arch) utilizzerà la versione di Linux o Windows in base all'host Docker del sistema operativo si sta distribuendo , come illustrato nell'esempio seguente:

-   **Microsoft / aspnetcore:2.0**

        Multi-arch: .NET Core 2.0 runtime-only on Linux or Windows Nano Server depending on the Docker host OS

In questo modo, quando è effettuare il pull di un'immagine da un host di Windows, effettuerà il pull la variante di Windows e lo stesso nome di immagine il pull da un host Linux estrarrà la variante Linux.

### <a name="option-b-creating-your-base-image-from-scratch"></a>Opzione b: creazione dell'immagine di base da zero

È possibile creare la propria immagine di base di Docker da zero. Questo scenario non è consigliato per un utente che si avvii con Docker, ma se si desidera impostare i bit specifici della propria immagine di base, è possibile farlo.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Archiviazione più immagini di .NET Core**.
https://github.com/dotnet/Announcements/issues/14 
-   **Creare un'immagine di base**. Documentazione ufficiale di Docker.
    [*https://docs.docker.com/Engine/UserGuide/ENG-Image/BaseImages/*](https://docs.docker.com/engine/userguide/eng-image/baseimages/)

![](./media/image7.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Passaggio 3. Creare immagini personalizzate Docker e incorporare l'applicazione o servizio in essi contenuti

Per ogni servizio dell'applicazione, è necessario creare un'immagine correlata. Se l'applicazione è costituito da un singolo servizio o applicazione web, è sufficiente una singola immagine.

Si noti che le immagini Docker vengono create automaticamente per l'utente in Visual Studio. I passaggi seguenti sono solo necessaria per il flusso di lavoro editor/CLI e descritto per maggiore chiarezza su ciò che accade sotto.

È, lo sviluppatore di necessario sviluppare e testare localmente finché non si esegue il push e compilato funzionalità o modificare al sistema di controllo del codice sorgente (ad esempio, per GitHub). Ciò significa che è necessario per le immagini Docker di creare e distribuire i contenitori in un host Docker locale (Windows o Linux VM) ed eseguire, testare e il debug in tali contenitori locale.

Per creare un'immagine personalizzata nell'ambiente locale tramite Docker CLI e il Dockerfile, è possibile utilizzare il comando di compilazione docker, come illustrato nella figura 5-5.

![](./media/image8.png)

**Figura 5-5**. Creazione di un'immagine Docker personalizzata

Facoltativamente, anziché eseguire direttamente la compilazione docker dalla cartella del progetto, è innanzitutto possibile generare una cartella distribuibile con le librerie .NET necessarie e i file binari eseguendo dotnet pubblicano e quindi utilizzano il comando di compilazione docker.

Si creerà un'immagine di Docker con il nome cesardl/netcore-webapi-microservizio-: prima di docker. In questo caso,: per primo è un tag che rappresenta una versione specifica. È possibile ripetere questo passaggio per ogni immagine personalizzata, che è necessario creare per l'applicazione di Docker composto.

Quando un'applicazione è costituita da più contenitori (ovvero, è un'applicazione multi-contenitore), è inoltre possibile utilizzare il comporre docker backup - comando di compilazione per compilare tutte le immagini correlate con un singolo comando con i metadati esposti nell'oggetto correlato. file compose.yml di docker.

È possibile trovare immagini esistenti nel repository locale tramite docker immagini comando, come illustrato nella figura 5-6.

![](./media/image9.png)

**Figura 5-6.** Visualizzazione di immagini esistente utilizzando il comando di immagini docker

### <a name="creating-docker-images-with-visual-studio"></a>La creazione di immagini Docker con Visual Studio

Quando si utilizza Visual Studio per creare un progetto con il supporto di Docker, non creare un'immagine in modo esplicito. L'immagine viene invece creata automaticamente quando si premere F5 e si esegue l'applicazione dockerized o il servizio. Questo passaggio è automatico in Visual Studio e non verrà visualizzato il verificarsi, ma è importante conoscere cosa accade in sotto.

![](./media/image10.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Passaggio 4. Definire i servizi in docker compose.yml quando si compila un'applicazione di multi-contenitore Docker

Il [docker compose.yml](https://docs.docker.com/compose/compose-file/) file consente di definire un set di servizi correlati da distribuire come un'applicazione composta con i comandi di distribuzione.

Per utilizzare un file docker compose.yml, è necessario creare il file principale o la cartella soluzione radice con contenuto simile a quello nell'esempio seguente:

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

Si noti che questo file compose.yml di docker è una versione semplificata e di merge. Contiene dati di configurazione statico per ogni contenitore (ad esempio, il nome dell'immagine personalizzata), che viene sempre applicato, nonché le informazioni di configurazione che potrebbero dipendere dall'ambiente di distribuzione, ad esempio la stringa di connessione. Nelle sezioni successive verrà illustrato come è possibile suddividere la configurazione di docker compose.yml in più docker comporre i file e i valori di sostituzione a seconda del tipo di ambiente e l'esecuzione (debug o release).

Nell'esempio di file docker compose.yml definisce cinque servizi: il servizio webmvc (un'applicazione web), due microservizi (catalog.api e ordering.api) e dati di un contenitore di origine, sql.data, basata su SQL Server per Linux in esecuzione come un contenitore. Ogni servizio viene distribuito come un contenitore, quindi un'immagine di Docker è necessaria per ogni.

Il file docker compose.yml specifica non solo i contenitori vengono utilizzati, ma la loro configurazione singolarmente. Ad esempio, la webmvc contenitore definizione nel file .yml:

-   Usa un eshop preesistente / immagine web: più di recente. Tuttavia, è inoltre possibile configurare l'immagine per essere compilato come parte di comporre docker esecuzione con una configurazione aggiuntiva in base a una compilazione: sezione nel file docker-compose.

-   Inizializza le due variabili di ambiente (CatalogUrl e OrderingUrl).

-   Inoltra la porta 80 sul contenitore per la porta esterna 80 sul computer host esposta.

-   Collega l'app web per il catalogo e l'ordine di servizio con il dipende\_impostazione. In questo modo il servizio di attesa fino a quando non vengono avviati i servizi.

Il file docker compose.yml in una sezione successiva verranno presentati quando trattati come implementare microservizi e App multi-contenitore.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Utilizzo di docker-compose.yml in Visual Studio 2017

Quando si aggiunge il supporto di soluzioni di Docker in un progetto di servizio in una soluzione di Visual Studio, come illustrato nella figura 5-7, Visual Studio aggiunge al progetto un Dockerfile e aggiunge una sezione di servizio (progetto) nella soluzione con i file compose.yml di docker. È un modo semplice per avviare la soluzione più contenitori di composizione. È quindi possibile aprire i file di docker compose.yml e aggiornarli con funzionalità aggiuntive.

![](./media/image6.png)

**Figura 5-7**. Aggiunta del supporto di Docker in Visual Studio 2017 facendo clic su un progetto ASP.NET Core

Aggiunta del supporto di Docker in Visual Studio non solo Dockerfile vengono aggiunti al progetto, ma aggiunge le informazioni di configurazione a più file docker-compose.yml globali che vengono impostati a livello di soluzione.

Dopo aver aggiunto il supporto di Docker per la soluzione in Visual Studio, si noterà anche un nuovo nodo (nel file di progetto di docker compose.dcproj) in Esplora soluzioni che contiene i file di docker-compose.yml aggiunto, come illustrato nella figura 5-8.

![](./media/image11.PNG)

**Figura 5-8**. Il **comporre docker** nodo dell'albero aggiunto in Esplora soluzioni di Visual Studio 2017

È possibile distribuire un'applicazione multi-contenitore con un file docker-compose.yml singolo utilizzando la composizione docker il comando. Tuttavia, Visual Studio aggiunge un gruppo di elementi, è possibile eseguire l'override di valori a seconda dell'ambiente (sviluppo e produzione) e l'esecuzione tipo (release e debug). Questa funzionalità verrà spiegata nelle sezioni successive.

![](./media/image12.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Passaggio 5. Compilare ed eseguire l'applicazione di Docker

Se l'applicazione dispone solo di un singolo contenitore, è possibile eseguirlo distribuendola all'host Docker (macchina virtuale o server fisico). Tuttavia, se l'applicazione contiene più servizi, è possibile distribuirlo come un'applicazione composta, utilizzando un unico comando CLI (docker-Scrivi backup), o con Visual Studio, che verrà utilizzato il comando dietro le quinte. Esaminare le diverse opzioni.

### <a name="option-a-running-a-single-container-with-docker-cli"></a>Opzione a: esecuzione di un singolo contenitore con Docker CLI

È possibile eseguire un contenitore Docker usando il comando docker run, come illustrato nella figura 5-9:

```
  docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

![](./media/image13.png)

**Figura 5-9**. Esecuzione di un contenitore Docker usando il comando docker run

In questo caso, il comando associa la porta interna 5000 del contenitore alla porta 80 del computer host. Ciò significa che l'host è in ascolto sulla porta 80 e con inoltro alla porta 5000 nel contenitore.

### <a name="option-b-running-a-multi-container-application"></a>Opzione b: esecuzione di un'applicazione multi-contenitore

Nella maggior parte degli scenari aziendali, un'applicazione di Docker verrà essere composta da più servizi, ovvero che è necessario eseguire un'applicazione multi-contenitore, come illustrato nella figura 5-10.

![](./media/image14.png)

**Figura 5-10**. Macchina virtuale con i contenitori di Docker distribuito

#### <a name="running-a-multi-container-application-with-the-docker-cli"></a>Esecuzione di un'applicazione multi-contenitore con l'interfaccia CLI di Docker

Per eseguire un'applicazione multi-contenitore con l'interfaccia CLI di Docker, è possibile eseguire docker-comporre il comando. Questo file di comando utilizza il compose.yml di docker è a livello di soluzione per distribuire un'applicazione multi-contenitore. Figura 5-11 Mostra i risultati quando si esegue il comando dalla directory del progetto principale, che contiene il file compose.yml di docker.

![](./media/image15.png)

**Figura 5-11**. Esempio risultati quando si esegue la composizione docker il comando

Dopo aver docker-comporre di esecuzione del comando, l'applicazione e i relativi contenitori correlati vengono distribuite in host Docker, come illustrato nella figura 5-10 rappresentazione macchina virtuale.

#### <a name="running-and-debugging-a-multi-container-application-with-visual-studio"></a>Esecuzione e il debug di un'applicazione multi-contenitore con Visual Studio 

Esecuzione di un'applicazione multi-contenitore utilizzando Visual Studio 2017 non è possibile ottenere più semplice. Non è possibile eseguire solo l'applicazione multi-contenitore, ma si è in grado di eseguire il debug di tutti i relativi contenitori direttamente da Visual Studio impostando punti di interruzione normale.

Come accennato in precedenza, ogni volta che si aggiungere il supporto di soluzioni di Docker in un progetto all'interno di una soluzione, il progetto è configurato nel file docker-compose.yml (a livello di soluzione) globale, che consente di eseguire o eseguire il debug in una sola volta l'intera soluzione. Avviare un contenitore per ogni progetto che dispone del supporto di soluzioni di Docker abilitato, Visual Studio ed esegue automaticamente tutti i passaggi interni (dotnet pubblica, compilazione docker, ecc.).

L'importante è che, come illustrato nella figura 5-12, in Visual Studio 2017 vi sia un ulteriore **Docker** comando per l'azione con tasto F5. Questa opzione consente di eseguire o eseguire il debug di un'applicazione multi-contenitore eseguendo tutti i contenitori che vengono definiti nei file di docker compose.yml a livello di soluzione. La possibilità di eseguire il debug delle soluzioni più contenitore significa che è possibile impostare più punti di interruzione, ogni punto di interruzione in un progetto diverso (contenitore) e durante il debug da Visual Studio verrà arrestato in corrispondenza dei punti di interruzione definiti in progetti diversi e in esecuzione in contenitori diversi.

![](./media/image16.png)

**Figura 5-12**. Le applicazioni di multi-contenitore in esecuzione in Visual Studio 2017

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Distribuire un contenitore ASP.NET in un host Docker remoto**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker*](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Una nota sui test e distribuzione con orchestrators

Il comporre docker backup e i comandi di docker eseguire (o in esecuzione e i contenitori in Visual Studio di debug) non risultano adeguate per i contenitori di test nell'ambiente di sviluppo. Tuttavia, non utilizzare questo approccio se la destinazione è il cluster di Docker e orchestrators Docker Swarm, Mesosphere DC/OS o Kubernetes. Se si utilizza un cluster come [Docker Swarm modalità](https://docs.docker.com/engine/swarm/) (disponibile in Docker CE per Windows e Mac dalla versione 1.12), è necessario distribuire e testare con altri comandi, ad esempio [servizio docker creare](https://docs.docker.com/engine/reference/commandline/service_create/) per servizi Single. Se si distribuisce un'applicazione composta da diversi contenitori, utilizzare [docker comporre bundle](https://docs.docker.com/compose/reference/bundle/) e [docker distribuire myBundleFile](https://docs.docker.com/engine/reference/commandline/deploy/) per distribuire l'applicazione come comporre un *stack*. Per ulteriori informazioni, vedere il post di blog [introduzione sperimentale bundle dell'applicazione distribuita](https://blog.docker.com/2016/06/docker-app-bundle/) nella documentazione di Docker. nel sito di Docker.

Per [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/) si usano i comandi di distribuzione diversi e anche gli script.

![](./media/image17.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Passaggio 6. Testare l'applicazione di Docker con l'host Docker locale

Questo passaggio può variare a seconda di ciò che esegue l'applicazione. In un'applicazione Web di base .NET semplice che viene distribuita come un singolo contenitore o un servizio, è possibile accedere al servizio aprendo un browser nell'host Docker e passando a un sito, come illustrato nella figura 5-13. (Se la configurazione in Dockerfile esegue il mapping a una porta dell'host che è diverso da 80 del contenitore, includono il post di host nell'URL).

![](./media/image18.png)

**Figura 5-13**. Esempio di test dell'applicazione di Docker in locale utilizzando localhost

Se l'host locale non fa riferimento a Docker host IP (per impostazione predefinita, quando si usa Docker CE, dovrebbe), per passare al servizio, usare l'indirizzo IP della scheda di rete del computer.

Si noti che questo URL nel browser utilizza la porta 80 per l'esempio di contenitore specifico vengono trattata. Tuttavia, internamente le richieste in corso il reindirizzamento alla porta 5000, perché questo è modo è stato distribuito con il comando docker run, come illustrato nel passaggio precedente.

È anche possibile testare l'applicazione utilizzando curl dal terminale, come illustrato nella figura 5-14. In un'installazione di Docker in Windows, il valore predefinito IP dell'Host Docker è sempre 10.0.75.1 aggiunta indirizzo IP effettivo del computer.

![](./media/image19.png)

**Figura 5-14**. Esempio di test dell'applicazione di Docker in locale utilizzando curl

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Test e debug di contenitori con Visual Studio 2017

Quando in esecuzione e i contenitori con Visual Studio 2017 di debug, è possibile eseguire il debug dell'applicazione .NET nello stesso modo come si farebbe in esecuzione senza contenitori.

### <a name="testing-and-debugging-without-visual-studio"></a>Test e debug senza Visual Studio

Se si sta sviluppando utilizzando l'approccio editor/CLI, debug contenitori risulta più difficile e si desideri eseguire il debug tramite la generazione di tracce.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Debug di applicazioni in un contenitore Docker locale**
    [*https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh*](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

-   **Steve Lasker. Compilare, eseguire il Debug, distribuire le app ASP.NET Core con Docker.** Video.
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115)

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Flusso di lavoro semplificata durante lo sviluppo di contenitori con Visual Studio

In effetti, il flusso di lavoro quando si utilizza Visual Studio è molto più semplice rispetto a se si utilizza l'approccio editor/CLI. La maggior parte dei passaggi necessari per Docker correlati di Dockerfile e docker compose.yml file sono nascosti o semplificati da Visual Studio, come illustrato nella figura 5-15.

![](./media/image20.png)

**Figura 5-15**. Flusso di lavoro semplificata durante lo sviluppo con Visual Studio

Inoltre, è necessario eseguire solo una volta al passaggio 2 (supporto per Docker aggiunta ai progetti). Pertanto, il flusso di lavoro è simile alle attività di sviluppo normale quando si utilizza .NET per lo sviluppo di altri. È necessario sapere cosa succede dietro le quinte (il processo di generazione di immagini, quali immagini di base in uso, la distribuzione di contenitori, e così via) e in alcuni casi che è anche necessario modificare il file Dockerfile o compose.yml di docker per personalizzare i comportamenti. Ma la maggior parte delle operazioni sia notevolmente semplificato tramite Visual Studio, rendendo è molto più produttivi.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Steve Lasker. Sviluppo di docker .NET con Visual Studio 2017**
    [*https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111*](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111)

-   **Jeffrey T. Fritz. Inserire un'App di .NET Core in un contenitore con i nuovi strumenti di Docker per Visual Studio**
    [*https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/*](https://blogs.msdn.microsoft.com/webdev/2016/11/16/new-docker-tools-for-visual-studio/)

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Per impostare i contenitori di Windows utilizza i comandi di PowerShell in un Dockerfile 

[Contenitori di Windows](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/about/about_overview) consentono di convertire le applicazioni di Windows esistenti in immagini Docker e distribuirle con gli stessi strumenti come il resto dell'ecosistema di Docker. Per usare i contenitori di Windows, eseguire i comandi di PowerShell in Dockerfile, come illustrato nell'esempio seguente:

```
FROM microsoft/windowsservercore
  
LABEL Description="IIS" Vendor="Microsoft" Version="10"
  
RUN powershell -Command Add-WindowsFeature Web-Server
  
CMD [ "ping", "localhost", "-t" ]
```

In questo caso, ci stiamo utilizzando un'immagine di base di Windows Server Core (impostazione FROM) e l'installazione di IIS con un comando di PowerShell (l'impostazione di esecuzione). In modo analogo, è inoltre possibile utilizzare i comandi di PowerShell per impostare i componenti aggiuntivi quali ASP.NET 4. x, .NET 4.6 o qualsiasi altro software di Windows. Ad esempio, il comando seguente in un Dockerfile Configura ASP.NET 4.5:

```
RUN powershell add-windowsfeature web-asp-net45
```

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Dockerfile-docker/ASPNET.** Comandi di Powershell di esempio per l'esecuzione da dockerfile per includere funzionalità di Windows.
    [*https://github.com/Microsoft/ASPNET-docker/BLOB/master/4.6.2/Dockerfile*](https://github.com/Microsoft/aspnet-docker/blob/master/4.6.2/Dockerfile)

>[!div class="step-by-step"]
[Precedente] (index.md) [Avanti] (... / net-core-single-containers-linux-windows-server-hosts/index.md)
