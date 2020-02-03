---
title: Flusso di lavoro di sviluppo per app Docker
description: Informazioni dettagliate sul flusso di lavoro richiesto per lo sviluppo delle applicazioni basate su Docker. Iniziare gradualmente e approfondire alcuni dettagli per ottimizzare i Dockerfile e terminare con il flusso di lavoro semplificato disponibile quando si usa Visual Studio.
ms.date: 01/07/2019
ms.openlocfilehash: 53675bf974069e9052d6d03b2743314af6f13cf9
ms.sourcegitcommit: feb42222f1430ca7b8115ae45e7a38fc4a1ba623
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2020
ms.locfileid: "76965789"
---
# <a name="development-workflow-for-docker-apps"></a>Flusso di lavoro di sviluppo per app Docker

Il ciclo di vita dello sviluppo applicativo inizia nel computer dello sviluppatore, che qui scrive l'applicazione usando il linguaggio preferito ed esegue i relativi test in locale. Con questo flusso di lavoro, indipendentemente dal linguaggio, dal framework e dalla piattaforma scelti, si sviluppano e testano sempre contenitori Docker, ma a livello locale.

Ogni contenitore, ovvero un'istanza di un'immagine Docker, include i componenti seguenti:

- Un sistema operativo a scelta, ad esempio una distribuzione Linux, Windows Nano Server o Windows Server Core.

- I file aggiunti durante lo sviluppo, ad esempio, il codice sorgente e i file binari dell'applicazione.

- Informazioni di configurazione, ad esempio impostazioni di ambiente e dipendenze.

## <a name="workflow-for-developing-docker-container-based-applications"></a>Flusso di lavoro per lo sviluppo di applicazioni Docker basate su contenitore

Questa sezione descrive il flusso di lavoro di sviluppo a *ciclo interno* per applicazioni Docker basate su contenitore. Il flusso di lavoro a ciclo interno significa che non sta considerando il flusso di lavoro DevOps più ampio, che può includere fino alla distribuzione di produzione, e si concentra solo sul lavoro di sviluppo svolto nel computer dello sviluppatore. I passaggi iniziali per configurare l'ambiente non sono inclusi, poiché vengono eseguiti una sola volta.

Un'applicazione è costituita da servizi e raccolte aggiuntive, ossia dipendenze. Di seguito sono indicati i passaggi di base che si eseguono in genere quando si compila un'applicazione Docker, come illustrato nella figura 5-1.

:::image type="complex" source="./media/docker-app-development-workflow/life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramma che illustra i 7 passaggi necessari per creare un'app in contenitori.":::
Il processo di sviluppo per le app docker: 1-scrivere il codice dell'app, 2-scrivere Dockerfile/s, 3-creare immagini definite in Dockerfile/s, 4-(facoltativo) comporre servizi nel file Docker-compose. yml, 5-eseguire il contenitore o l'app Docker-compose, 6 testare l'app o i microservizi, 7 push nel repository e ripetere.
:::image-end:::

**Figura 5-1.** Flusso di lavoro passo per passo per lo sviluppo di applicazioni Docker in contenitori

Questa sezione descrive nei dettagli l'intero processo e ogni passaggio principale è spiegato con riferimento all'ambiente Visual Studio.

Quando si usa un approccio di sviluppo editor/CLI, ad esempio codice Visual Studio e CLI di Docker in macOS o Windows, di solito è necessario conoscere ogni passaggio in modo più dettagliato rispetto all'uso di Visual Studio. Per altre informazioni sull'uso di un ambiente CLI, vedere l'e-book [Containerized Docker Application lifecycle with Microsoft Platforms and Tools](https://aka.ms/dockerlifecycleebook/) (Ciclo di vita di un'applicazione Docker in un contenitore con piattaforme e strumenti Microsoft).

Se si usa Visual Studio 2017, molti passaggi sono gestiti automaticamente e questo migliora notevolmente la produttività. Ciò vale soprattutto quando si usa Visual Studio 2017 con applicazioni a più contenitori. Ad esempio, con un solo clic, Visual Studio aggiunge ai progetti il Dockerfile e il file docker-compose.yml con la configurazione per l'applicazione. Quando si esegue l'applicazione in Visual Studio, viene creata l'immagine Docker e l'applicazione a più contenitori viene eseguita direttamente in Docker; è anche possibile eseguire il debug di diversi contenitori contemporaneamente. Queste funzionalità rendono lo sviluppo più veloce.

Tuttavia, anche se Visual Studio automatizza questi passaggi, ciò non significa che non sia necessario sapere cosa succede dietro le quinte con Docker. Di conseguenza, il materiale sussidiario seguente illustra in dettaglio ogni passaggio.

![Immagine per il passaggio 1.](./media/docker-app-development-workflow/step-1-code-your-app.png)

## <a name="step-1-start-coding-and-create-your-initial-application-or-service-baseline"></a>Passaggio 1. Iniziare a scrivere il codice e ad abbozzare l'applicazione o il servizio

Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza Docker. La differenza è che, quando si sviluppa per Docker, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale (una macchina virtuale Linux configurata da Docker o direttamente Windows se si usano i contenitori Windows).

### <a name="set-up-your-local-environment-with-visual-studio"></a>Configurare l'ambiente locale con Visual Studio

Per iniziare, accertarsi che sia installato [Docker Community Edition (CE)](https://docs.docker.com/docker-for-windows/) per Windows, come spiegato nelle istruzioni seguenti:

[Introduzione a Docker CE per Windows](https://docs.docker.com/docker-for-windows/)

Inoltre, è necessario Visual Studio 2017 versione 15.7 o successive con il carico di lavoro **Sviluppo multipiattaforma .NET Core** installato, come illustra la figura 5-2.

![Screenshot della selezione dello sviluppo multipiattaforma .NET Core.](./media/docker-app-development-workflow/dotnet-core-cross-platform-development.png)

**Figura 5-2**. Selezione del carico di lavoro **Sviluppo multipiattaforma .NET Core** durante l'installazione di Visual Studio 2017

È possibile iniziare a scrivere il codice dell'applicazione in .NET normale, di solito in .NET Core se si prevede di usare contenitori, anche prima di attivare Docker nell'applicazione e di eseguire la distribuzione e i test in Docker, ma si consiglia di iniziare a lavorare in Docker appena possibile, perché quello sarà l'ambiente reale e gli eventuali problemi possono essere individuati velocemente. Si consiglia di procedere in questo modo perché Visual Studio facilita così tanto il lavoro con Docker da diventare quasi trasparente, soprattutto quando lo si usa per eseguire il debug di applicazioni a più contenitori.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Introduzione a Docker CE per Windows** \
  <https://docs.docker.com/docker-for-windows/>

- **Visual Studio 2017** \
  [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)

![Immagine del passaggio 2.](./media/docker-app-development-workflow/step-2-write-dockerfile.png)

## <a name="step-2-create-a-dockerfile-related-to-an-existing-net-base-image"></a>Passaggio 2: Creare un Dockerfile correlato a un'immagine di base .NET esistente

È necessario un Dockerfile per ogni immagine personalizzata che si desidera creare; è necessario un Dockerfile per ogni contenitore da distribuire, sia che si esegua la distribuzione automaticamente da Visual Studio o manualmente con la CLI di Docker: comandi docker run e docker-compose. Se l'applicazione contiene un solo servizio personalizzato, è necessario un solo Dockerfile. Se l'applicazione contiene più servizi, come in un'architettura a microservizi, è necessario un Dockerfile per ogni servizio.

Il Dockerfile viene inserito nella cartella radice dell'applicazione o del servizio. Contiene i comandi che indicano a Docker come configurare ed eseguire l'applicazione o il servizio in un contenitore. È possibile creare manualmente un Dockerfile nel codice e aggiungerlo al progetto insieme alle dipendenze .NET.

Con Visual Studio e i relativi strumenti per Docker questa attività richiede solo pochi clic del mouse. Quando si crea un nuovo progetto in Visual Studio 2017, è disponibile un'opzione denominata **Abilita supporto Docker**, come illustrato nella figura 5-3.

![Screenshot che mostra la casella di controllo Abilita supporto docker.](./media/docker-app-development-workflow/enable-docker-support-check-box.png)

**Figura 5-3**. Abilitazione del supporto Docker quando si crea un nuovo progetto ASP.NET Core in Visual Studio 2017

È anche possibile abilitare il supporto Docker in un progetto di app Web ASP.NET Core esistente facendo clic con il pulsante destro del mouse sul progetto in **Esplora soluzioni** e selezionando **Aggiungi** > **Supporto Docker**, come illustrato nella figura 5-4.

![Screenshot che mostra l'opzione di supporto Docker nel menu Aggiungi.](./media/docker-app-development-workflow/add-docker-support-option.png)

**Figura 5-4**. Abilitazione del supporto Docker in un progetto Visual Studio 2017 esistente

Questa azione aggiunge un *Dockerfile* al progetto con la configurazione richiesta ed è disponibile solo nei progetti ASP.NET Core.

In modo analogo, Visual Studio può anche aggiungere un file docker-compose.yml per l'intera soluzione con l'opzione di **aggiunta del supporto dell'agente di orchestrazione dei contenitori**. Nel passaggio 4 questa opzione verrà esaminata in modo più dettagliato.

### <a name="using-an-existing-official-net-docker-image"></a>Uso di un'immagine Docker .NET ufficiale esistente

In genere per il contenitore si crea un'immagine personalizzata sopra un'immagine di base che è possibile ottenere da un repository ufficiale come il registro [Hub Docker](https://hub.docker.com/). Questo è esattamente ciò che accade dietro le quinte quando si attiva il supporto Docker in Visual Studio. Il Dockerfile userà un'immagine `aspnetcore` esistente.

In precedenza si è visto le immagini e repository Docker da usare in base al framework e al sistema operativo scelto. Ad esempio, se si usa ASP.NET Core (Linux o Windows), l'immagine da usare è `mcr.microsoft.com/dotnet/core/aspnet:2.2`. Pertanto è sufficiente specificare l'immagine Docker di base che sarà usata per il contenitore. A tale scopo, aggiungere `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2` al Dockerfile. Visual Studio esegue l'operazione automaticamente, ma se si aggiornasse la versione, verrebbe aggiornato anche questo valore.

L'uso di un repository ufficiale di immagini .NET di Docker Hub con un numero di versione garantisce che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.

L'esempio seguente illustra un esempio di Dockerfile per un contenitore ASP.NET Core.

```Dockerfile
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
ARG source
WORKDIR /app
EXPOSE 80
COPY ${source:-obj/Docker/publish} .
ENTRYPOINT ["dotnet", " MySingleContainerWebApp.dll "]
```

In questo caso l'immagine si basa sulla versione 2.2 dell'immagine Docker ufficiale di ASP.NET Core (multiarchitettura per Linux e Windows). Si tratta dell'impostazione `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`. Per altre informazioni su questa immagine di base, vedere la pagina dell' [immagine Docker di .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) . In Dockerfile è anche necessario indicare a Docker di restare in ascolto sulla porta TCP che verrà usata in fase di esecuzione (in questo caso, la porta 80, come configurata con l'impostazione EXPOSE).

Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso. Ad esempio, la riga ENTRYPOINT con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker di eseguire un'applicazione .NET Core. Se si usa l'SDK e l'interfaccia della riga di comando di .NET Core, ovvero l'interfaccia della riga di comando dotnet, per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa. In sostanza la riga ENTRYPOINT e altre impostazioni saranno diverse a seconda del linguaggio e della piattaforma scelti per l'applicazione.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Compilazione di immagini Docker per applicazioni .NET Core** \
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

- **Creare un'immagine**. Nella documentazione ufficiale di Docker.\
  <https://docs.docker.com/engine/tutorials/dockerimages/>

- **Rimanere aggiornati con le immagini del contenitore .NET** \
  <https://devblogs.microsoft.com/dotnet/staying-up-to-date-with-net-container-images/>

- **Uso combinato di .NET e Docker - Aggiornamento DockerCon 2018** \
  <https://devblogs.microsoft.com/dotnet/using-net-and-docker-together-dockercon-2018-update/>

### <a name="using-multi-arch-image-repositories"></a>Uso di repository di immagini multi-arch

Un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows. Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows. Ad esempio, il repository [dotnet/core](https://hub.docker.com/_/microsoft-dotnet-core/) disponibile nel registro dell'hub Docker fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di repository.

Se si specifica un tag, ci si rivolge a una piattaforma esplicita come nei casi seguenti:

- `microsoft/dotnet:2.2-aspnetcore-runtime-stretch-slim` \
  Destinazioni: solo runtime .NET Core 2.2 in Linux

- `microsoft/dotnet:2.2-aspnetcore-runtime-nanoserver-1809` \
  Destinazioni: solo runtime .NET Core 2.2 in Windows Nano Server

Ma se si specifica lo stesso nome di immagine, anche con lo stesso tag, le immagini multi-arch, ad esempio l'immagine `aspnetcore`, useranno la versione Linux o Windows in base al sistema operativo host Docker che si sta distribuendo, come illustrato nell'esempio seguente:

- `microsoft/dotnet:2.2-aspnetcore-runtime` \
  Multiarchitettura: solo runtime .NET Core 2.2 in Linux e Windows Nano Server in base al sistema operativo dell'host Docker

In questo modo, se si esegue il pull di un'immagine da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome di immagine da un host Linux si ottiene la variante Linux.

### <a name="multi-stage-builds-in-dockerfile"></a>Compilazioni in più fasi in Dockerfile

Il Dockerfile è simile a uno script batch. Esegue le operazioni che sarebbe necessario eseguire per configurare il computer dalla riga di comando.

Inizia con un'immagine di base che imposta il contesto iniziale, analogamente al filesystem di avvio, e si trova nella parte superiore del sistema operativo host. Non si tratta di un sistema operativo, ma è possibile considerarlo come il sistema operativo all'interno del contenitore.

L'esecuzione di ogni riga di comando crea un nuovo livello nel filesystem con le modifiche di quello precedente, in modo che la combinazione generi il filesystem risultante.

Poiché ogni nuovo livello viene creato sopra il livello precedente e le dimensioni dell'immagine risultante aumentano ad ogni comando, le immagini possono diventare molto grandi se devono includere, ad esempio, l'SDK necessario per compilare e pubblicare un'applicazione.

Qui è dove le compilazioni in più fasi entrano in gioco (da Docker 17.05 e versioni successive) e dimostrano tutta la loro efficacia.

L'idea di base è che è possibile separare il processo di esecuzione Dockerfile in più fasi, in cui una fase è un'immagine iniziale seguita da uno o più comandi e l'ultima fase determina le dimensioni dell'immagine finale.

In breve, le compilazioni in più fasi consentono di suddividere la creazione in diversi passaggi e quindi assemblare l'immagine finale usando solo le directory pertinenti delle fasi intermedie. La strategia generale per usare questa funzionalità è:

1. Usare un'immagine di base dell'SDK (le dimensioni non sono importanti), con tutto ciò che serve per compilare e pubblicare l'applicazione in una cartella e quindi

2. usare un'immagine di base, piccola e solo di runtime, e copiare la cartella di pubblicazione della fase precedente per produrre un'immagine finale di dimensioni ridotte.

Probabilmente il modo migliore per comprendere la compilazione in più fasi è esaminare un Dockerfile in dettaglio, riga per riga, quindi si può iniziare con il Dockerfile creato da Visual Studio quando si aggiunge il supporto Docker a un progetto e vedere alcune ottimizzazioni in un secondo momento.

Il Dockerfile iniziale può avere un aspetto simile al seguente:

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS build
 6  WORKDIR /src
 7  COPY src/Services/Catalog/Catalog.API/Catalog.API.csproj …
 8  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.AspNetCore.HealthChecks …
 9  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions.HealthChecks …
10  COPY src/BuildingBlocks/EventBus/IntegrationEventLogEF/ …
11  COPY src/BuildingBlocks/EventBus/EventBus/EventBus.csproj …
12  COPY src/BuildingBlocks/EventBus/EventBusRabbitMQ/EventBusRabbitMQ.csproj …
13  COPY src/BuildingBlocks/EventBus/EventBusServiceBus/EventBusServiceBus.csproj …
14  COPY src/BuildingBlocks/WebHostCustomization/WebHost.Customization …
15  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
16  COPY src/BuildingBlocks/HealthChecks/src/Microsoft.Extensions …
17  RUN dotnet restore src/Services/Catalog/Catalog.API/Catalog.API.csproj
18  COPY . .
19  WORKDIR /src/src/Services/Catalog/Catalog.API
20  RUN dotnet build Catalog.API.csproj -c Release -o /app
21
22  FROM build AS publish
23  RUN dotnet publish Catalog.API.csproj -c Release -o /app
24
25  FROM base AS final
26  WORKDIR /app
27  COPY --from=publish /app .
28  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

E questi sono i dettagli, riga per riga:

- **#1 riga:** Iniziare una fase con un'immagine di base di sola esecuzione "Small", chiamarla come **base** per riferimento.

- **#2 riga:** Creare la directory **/app** nell'immagine.

- **#3 riga:** Esporre la porta **80**.

- **#5 riga:** Inizia una nuova fase con l'immagine "large" per la compilazione e la pubblicazione. Chiamare **Build** per riferimento.

- **#6 riga:** Creare la directory **/src** nell'immagine.

- **#7 riga:** Fino alla riga 16, copiare i file di progetto con **estensione csproj** a cui si fa riferimento per poter ripristinare i pacchetti in un secondo momento.

- **#17 riga:** Ripristinare i pacchetti per il progetto **Catalog. API** e i progetti a cui si fa riferimento.

- **#18 riga:** Copiare **tutti gli alberi di directory per la soluzione** (ad eccezione dei file/directory inclusi nel file con **estensione dockerignore** ) nella directory **/src** nell'immagine.

- **#19 riga:** Modificare la cartella corrente nel progetto **Catalog. API** .

- **#20 riga:** Compilare il progetto (e altre dipendenze del progetto) e l'output nella directory **/app** nell'immagine.

- **#22 riga:** Inizia una nuova fase continuando dalla compilazione. Chiamarlo **Publish** for Reference.

- **#23 riga:** Pubblicare il progetto e le dipendenze e l'output nella directory **/app** nell'immagine.

- **#25 riga:** Iniziare una nuova fase continuando da **base** e chiamarla **finale**.

- **#26 riga:** Modificare la directory corrente in **/app**.

- **#27 riga:** Copiare la directory **/app** dalla fase di **pubblicazione** alla directory corrente.

- **#28 riga:** Definire il comando da eseguire all'avvio del contenitore.

Esaminare ora alcune ottimizzazioni che consentono di migliorare le prestazioni generali del processo che, nel caso di eShopOnContainers, corrispondono a circa 22 minuti o più per la compilazione della soluzione completa nei contenitori Linux.

Si può sfruttare la funzionalità di cache per i livelli di Docker, che è piuttosto semplice: se l'immagine di base e i comandi corrispondono ad altri già eseguiti in precedenza, è possibile usare solo il livello risultante senza dover eseguire i comandi, risparmiando tempo.

Quindi, concentrarsi sulla fase **build**, dove le righe 5 e 6 sono praticamente le stesse, ma le righe da 7 a 17 sono diverse per ogni servizio di eShopOnContainers, quindi devono essere eseguite ogni singola volta. Tuttavia, se le righe da 7 a 16 sono state modificate in:

```Dockerfile
COPY . .
```

Si avrebbe lo stesso per ogni servizio, verrebbe copiata l'intera soluzione e verrebbe creato un livello di dimensioni maggiori ma:

1. Il processo di copia verrebbe eseguito solo la prima volta (e quando si ricompila se viene modificato un file) e userebbe la cache per tutti gli altri servizi e

2. Poiché l'immagine più grande si verifica in una fase intermedia, non influisce sulle dimensioni dell'immagine finale.

Un'altra ottimizzazione significativa riguarda il comando `restore` eseguito alla riga 17, che è diverso per ogni servizio di eShopOnContainers. Se si modifica tale riga semplicemente in:

```Dockerfile
RUN dotnet restore
```

I pacchetti verrebbero ripristinati per l'intera soluzione, ma anche in questo caso l'operazione verrebbe eseguita una sola volta, anziché 15 volte come con la strategia attuale.

Tuttavia, `dotnet restore` viene eseguito solo se è presente un solo progetto o file di soluzione nella cartella, quindi ottenere questo risultato è un po' più complesso e il modo per ottenerlo, senza entrare troppo nel dettaglio, è questo:

1. Aggiungere le righe seguenti al file **DOCKERIGNORE**:

   - `*.sln`, per ignorare tutti i file di soluzione nella struttura della cartella principale

   - `!eShopOnContainers-ServicesAndWebApps.sln`, per includere solo questo file di soluzione.

2. Includere l'argomento `/ignoreprojectextensions:.dcproj` a `dotnet restore`, in modo che ignori anche il progetto docker-compose e ripristini solo i pacchetti per la soluzione eShopOnContainers-ServicesAndWebApps.

Per l'ottimizzazione finale, la riga 20 risulta ridondante, poiché anche la riga 23 compila l'applicazione e praticamente viene subito dopo la riga 20, quindi si ha un altro comando che richiede molto tempo.

Il file risultante quindi è:

```Dockerfile
 1  FROM mcr.microsoft.com/dotnet/core/aspnet:2.2 AS base
 2  WORKDIR /app
 3  EXPOSE 80
 4
 5  FROM mcr.microsoft.com/dotnet/core/sdk:2.2 AS publish
 6  WORKDIR /src
 7  COPY . .
 8  RUN dotnet restore /ignoreprojectextensions:.dcproj
 9  WORKDIR /src/src/Services/Catalog/Catalog.API
10  RUN dotnet publish Catalog.API.csproj -c Release -0 /app
11
12  FROM base AS final
13  WORKDIR /app
14  COPY --from=publish /app
15  ENTRYPOINT ["dotnet", "Catalog.API.dll"]
```

### <a name="creating-your-base-image-from-scratch"></a>Creazione dell'immagine di base da zero

È possibile creare un'immagine Docker di base da zero. Questo scenario non è consigliato se non si conosce bene Docker, ma se si vuole creare la propria immagine di base è possibile farlo.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Immagini multi-arch .NET Core**.\
  <https://github.com/dotnet/announcements/issues/14>

- **Creare un'immagine di base**. Documentazione ufficiale di Docker.\
  <https://docs.docker.com/develop/develop-images/baseimages/>

![Immagine per il passaggio 3.](./media/docker-app-development-workflow/step-3-create-dockerfile-defined-images.png)

## <a name="step-3-create-your-custom-docker-images-and-embed-your-application-or-service-in-them"></a>Passaggio 3. Creare le immagini Docker personalizzate e incorporare l'applicazione o il servizio in esse

Per ogni servizio dell'applicazione è necessario creare un'immagine correlata. Se l'applicazione è costituita da un singolo servizio o applicazione Web, è sufficiente una singola immagine.

Si noti che le immagini Docker vengono create automaticamente in Visual Studio. I passaggi seguenti sono necessari solo per il flusso di lavoro editor/CLI e sono descritti per chiarire meglio ciò che succede dietro le quinte.

Lo sviluppatore deve eseguire lo sviluppo e i test localmente finché non esegue il push di una funzionalità o di una modifica completa nel sistema di controllo del codice sorgente, ad esempio in GitHub. Ciò significa che è necessario creare le immagini Docker e distribuire i contenitori in un host Docker locale, ovvero una VM Windows o Linux, nonché eseguire, testare ed eseguire il debug in tali contenitori locale.

Per creare un'immagine personalizzata nell'ambiente locale tramite la CLI di Docker e il Dockerfile, è possibile usare il comando docker build, come illustrato nella figura 5-5.

![Screenshot che mostra l'output della console del comando Docker Build.](./media/docker-app-development-workflow/run-docker-build-command.png)

**Figura 5-5**. Creazione di un'immagine Docker personalizzata

Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è possibile generare innanzitutto una cartella distribuibile con le raccolte .NET e i file binari necessari eseguendo `dotnet publish` e quindi usando il comando `docker build`.

Verrà creata un'immagine Docker con il nome `cesardl/netcore-webapi-microservice-docker:first`. In questo caso :first è un tag che rappresenta una versione specifica. È possibile ripetere questo passaggio per ogni immagine personalizzata da creare per l'applicazione Docker composta.

Quando un'applicazione è costituita da più contenitori, ovvero è un'applicazione a più contenitori, è anche possibile usare il comando `docker-compose up --build` per compilare tutte le immagini correlate con un singolo comando usando i metadati esposti nei file docker-compose.yml correlati.

È possibile trovare le immagini esistenti nel repository locale tramite il comando docker images, come illustrato nella figura 5-6.

![Output della console del comando docker images che illustra le immagini esistenti.](./media/docker-app-development-workflow/view-existing-images-with-docker-images.png)

**Figura 5-6.** Visualizzazione di immagini esistente con il comando docker images

### <a name="creating-docker-images-with-visual-studio"></a>Creazione di immagini Docker con Visual Studio

Quando si usa Visual Studio per creare un progetto con il supporto Docker, non si crea un'immagine in modo esplicito. L'immagine viene invece creata automaticamente quando si preme **F5** (o **CTRL-F5**) e si esegue l'applicazione o il servizio Docker. Questo passaggio è automatico e invisibile in Visual Studio, ma è importante sapere cosa succede dietro le quinte.

![Immagine per il passaggio 4 facoltativo.](./media/docker-app-development-workflow/step-4-define-services-docker-compose-yml.png)

## <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application"></a>Passaggio 4. Definire i servizi in docker-compose.yml quando si compila un'applicazione Docker a più contenitori

Il file [docker compose.yml](https://docs.docker.com/compose/compose-file/) consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione. Configura inoltre le proprie relazioni di dipendenza e la configurazione di runtime.

Per usare un file docker-compose.yml, è necessario creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello nell'esempio seguente:

```yml
version: '3.4'

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
      - ConnectionString=Server=sql.data;Port=1433;Database=CatalogDB;…
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

Questo file docker-compose.yml è una versione semplificata e unita. Contiene dati di configurazione statici per ogni contenitore, ad esempio il nome dell'immagine personalizzata, che sono sempre richiesti, nonché informazioni di configurazione che possono dipendere dall'ambiente di distribuzione, ad esempio la stringa di connessione. Nelle sezioni successive si vedrà come suddividere la configurazione di docker-compose.yml in più file docker-compose e come sostituire valori a seconda del tipo di ambiente e di esecuzione (debug o release).

L'esempio di file docker-compose.yml definisce quattro servizi: il servizio `webmvc` (un'applicazione Web), due microservizi (`ordering.api` e `basket.api`) e un contenitore origine dati, `sql.data`, basato su SQL Server per Linux eseguito come contenitore. Ogni servizio verrà distribuito come contenitore, quindi è necessaria un'immagine Docker per ognuno.

Il file docker-compose.yml specifica non solo quali contenitori vengono usati, ma come sono configurati singolarmente. Ad esempio, la definizione del contenitore `webmvc` nel file YML:

- Usa un'immagine `eshop/web:latest` predefinita. Tuttavia, è anche possibile configurare l'immagine in modo che sia compilata come parte dell'esecuzione di docker-compose con una configurazione aggiuntiva basata su una sezione build: nel file docker-compose.

- Inizializza due variabili di ambiente, ovvero CatalogUrl e OrderingUrl.

- Inoltra la porta 80 esposta sul contenitore alla porta esterna 80 sul computer host.

- Collega l'app Web al catalogo e al servizio di ordinazione con l'impostazione depends_on. In questo modo il servizio attende fino a quando vengono avviati i servizi.

Il file docker-compose.yml sarà esaminato di nuovo in una sezione successiva in cui sarà descritto come implementare microservizi e app a più contenitori.

### <a name="working-with-docker-composeyml-in-visual-studio-2017"></a>Utilizzo di docker-compose.yml in Visual Studio 2017

Oltre ad aggiungere un Dockerfile a un progetto, come indicato in precedenza, Visual Studio 2017 (dalla versione 15,8 in) può aggiungere il supporto per l'agente di orchestrazione per Docker Compose a una soluzione.

Quando si aggiunge il supporto dell'agente di orchestrazione del contenitore, come illustrato nella figura 5-7, per la prima volta, Visual Studio crea il Dockerfile per il progetto e crea un nuovo progetto (sezione servizio) nella soluzione con diversi file `docker-compose*.yml` globali e quindi aggiunge il progetto a tali file. È quindi possibile aprire i file docker-compose.yml e aggiornarli con funzionalità aggiuntive.

È necessario ripetere questa operazione per ogni progetto che si vuole includere nel file docker-compose.yml.

Al momento della stesura di questo articolo, Visual Studio supporta gli agenti di orchestrazione Docker Compose e Service Fabric.

![Screenshot che mostra l'opzione di supporto dell'agente di orchestrazione dei contenitori nel menu di scelta rapida del progetto](./media/docker-app-development-workflow/add-container-orchestrator-support-option.png)

**Figura 5-7**. Aggiunta del supporto Docker in Visual Studio 2017 facendo clic con il pulsante destro del mouse su un progetto ASP.NET Core

Dopo aver aggiunto il supporto dell'agente di orchestrazione alla soluzione in Visual Studio, si noterà anche un nuovo nodo nel file di progetto `docker-compose.dcproj` in Esplora soluzioni, che contiene i file docker-compose.yml aggiunti, come illustrato nella figura 5-8.

![Screenshot del nodo Docker-compose in Esplora soluzioni.](./media/docker-app-development-workflow/docker-compose-tree-node.png)

**Figura 5-8**. Il nodo dell'albero **docker-compose** aggiunto in Esplora soluzioni di Visual Studio 2017

È possibile distribuire un'applicazione a più contenitori con un singolo file docker-compose.yml usando il comando `docker-compose up`. Tuttavia Visual Studio ne aggiunge un gruppo, quindi è possibile sostituire i valori in base all'ambiente, che può essere di sviluppo o di produzione, e al tipo di esecuzione (versione o debug). Questa funzionalità sarà spiegata nelle sezioni successive.

![Immagine per il passaggio 5.](./media/docker-app-development-workflow/step-5-run-containers-compose-app.png)

## <a name="step-5-build-and-run-your-docker-application"></a>Passaggio 5. Compilare ed eseguire l'applicazione Docker

Se l'applicazione ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, ovvero una VM o un server fisico. Se invece l'applicazione contiene più servizi, è possibile distribuirla come applicazione composta, usando un unico comando della CLI, ossia docker-compose up, o con Visual Studio, che userà lo stesso comando dietro le quinte. Le diverse opzioni sono esaminate di seguito.

### <a name="option-a-running-a-single-container-application"></a>Opzione A: esecuzione di un'applicazione a contenitore singolo

#### <a name="using-docker-cli"></a>Con l'interfaccia della riga di comando di Docker

È possibile eseguire un contenitore Docker usando il comando `docker run`, come illustrato nella figura 5-9:

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

Il comando precedente crea una nuova istanza di contenitore dall'immagine specificata, ogni volta che viene eseguito. È possibile usare il parametro `--name` per assegnare un nome al contenitore e quindi usare `docker start {name}` (o usare l'ID del contenitore o il nome automatico) per eseguire un'istanza del contenitore esistente.

![Screenshot che esegue un contenitore Docker usando il comando Docker Run.](./media/docker-app-development-workflow/use-docker-run-command.png)

**Figura 5-9**. Esecuzione di un contenitore Docker usando il comando docker run

In questo caso il comando associa la porta interna 5000 del contenitore alla porta 80 del computer host. Ciò significa che l'host è in ascolto sulla porta 80 e inoltra alla porta 5000 nel contenitore.

L'hash visualizzato è l'ID del contenitore e viene assegnato anche un nome leggibile casuale se non si usa l'opzione `--name`.

#### <a name="using-visual-studio"></a>Utilizzo di Visual Studio

Se non è stato aggiunto il supporto dell'agente di orchestrazione dei contenitori, è anche possibile eseguire un'applicazione a singolo contenitore in Visual Studio premendo **CTRL+F5** e usare **F5** per eseguire il debug dell'applicazione all'interno del contenitore. Il contenitore viene eseguito in locale usando docker run.

### <a name="option-b-running-a-multi-container-application"></a>Opzione B: esecuzione di un'applicazione a più contenitori

Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà composta da più servizi, perciò sarà necessario eseguire un'applicazione a più contenitori, come illustrato nella figura 5-10.

![Macchina virtuale con diversi contenitori Docker](./media/docker-app-development-workflow/vm-with-docker-containers-deployed.png)

**Figura 5-10**. VM con contenitori Docker distribuiti

#### <a name="using-docker-cli"></a>Con l'interfaccia della riga di comando di Docker

Per eseguire un'applicazione a più contenitori con l'interfaccia della riga di comando di Docker, si usa il comando `docker-compose up`. Questo comando usa il file **docker-compose.yml** disponibile a livello di soluzione per distribuire un'applicazione a più contenitori. La figura 5-11 illustra i risultati che si ottengono quando si esegue il comando dalla directory principale della soluzione, che contiene il file docker-compose.yml.

![Schermata visualizzata quando si esegue il comando docker-compose up](./media/docker-app-development-workflow/results-docker-compose-up.png)

**Figura 5-11**. Esempio di risultati ottenuti eseguendo il comando docker-compose up

Dopo l'esecuzione del comando docker-compose up, l'applicazione e i contenitori correlati vengono distribuiti nell'host Docker, come illustra la figura 5-10.

#### <a name="using-visual-studio"></a>Utilizzo di Visual Studio

Eseguire un'applicazione a più contenitori con Visual Studio 2017 è molto semplice. Basta premere **CTRL+F5** per l'esecuzione o **F5** per il debug, come di consueto, impostando il progetto **docker-compose** come progetto di avvio.  Visual Studio gestisce tutte le impostazioni necessarie, quindi è possibile creare punti di interruzione come di consueto ed eseguire il debug del risultato finale, ovvero processi indipendenti in esecuzione in "server remoti".

Come accennato in precedenza, ogni volta che si aggiungere il supporto Docker a un progetto all'interno di una soluzione, il progetto è configurato nel file docker-compose.yml globale, a livello di soluzione, che consente di eseguire l'intera soluzione o di eseguirne il debug in una sola volta. Visual Studio avvia un solo contenitore per ogni progetto che ha il supporto Docker abilitato ed esegue automaticamente tutti i passaggi interni, ovvero pubblicazione dotnet, compilazione docker, ecc.

Per avere un'idea di tutta la complessità, esaminare il file:

`{root solution folder}\obj\Docker\docker-compose.vs.debug.g.yml`

La cosa importante è che, come illustrato nella figura 5-12, in Visual Studio 2017 è presente un ulteriore comando **Docker** per il tasto funzione F5. Questa opzione consente di eseguire un'applicazione a più contenitori o di eseguirne il debug eseguendo tutti i contenitori definiti nei file docker-compose.yml a livello di soluzione. Grazie alla capacità di eseguire il debug delle soluzioni a più contenitori, è possibile impostare più punti di interruzione, ciascuno in un progetto (contenitore) diverso, e durante il debug da Visual Studio l'esecuzione viene arrestata in corrispondenza dei punti di interruzione definiti in progetti diversi ed eseguiti in contenitori diversi.

![Screenshot della barra degli strumenti di debug che esegue un progetto Docker-compose.](./media/docker-app-development-workflow/debug-toolbar-docker-compose-project.png)

**Figura 5-12**. Esecuzione di applicazioni a più contenitori in Visual Studio 2017

### <a name="additional-resources"></a>Risorse aggiuntive

- **Distribuire un contenitore ASP.NET a un host Docker remoto** \
  <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

### <a name="a-note-about-testing-and-deploying-with-orchestrators"></a>Una nota sul test e la distribuzione con agenti di orchestrazione

I comandi docker-compose up e docker run, o l'esecuzione e il debug dei contenitori in Visual Studio, sono adeguati per eseguire test sui contenitori nell'ambiente di sviluppo. È consigliabile non usare questo approccio per le distribuzioni di produzione, in cui la destinazione deve essere un agente di orchestrazione, ad esempio [Kubernetes](https://kubernetes.io/) o [Service Fabric](https://azure.microsoft.com/services/service-fabric/). Se si usa Kubernetes, è necessario usare i [Pod](https://kubernetes.io/docs/concepts/workloads/pods/pod/) per organizzare i contenitori e i [Servizi](https://kubernetes.io/docs/concepts/services-networking/service/) per la rete. Si usano anche le [distribuzioni](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) per organizzare la creazione e la modifica dei pod.

![Immagine per il passaggio 6.](./media/docker-app-development-workflow/step-6-test-app-microservices.png)

## <a name="step-6-test-your-docker-application-using-your-local-docker-host"></a>Passaggio 6. Testare l'applicazione Docker usando l'host Docker locale

Questo passaggio varia in base a ciò che l'applicazione sta facendo. In un'applicazione Web .NET Core semplice che viene distribuita come contenitore o servizio singolo è possibile accedere al servizio aprendo un browser nell'host Docker e passando a quel sito, come illustrato nella figura 5-13. Se la configurazione nel Dockerfile abbina il contenitore a una porta dell'host diversa dalla 80, includere la porta host nell'URL.

![Screenshot della risposta da localhost/API/values.](./media/docker-app-development-workflow/test-docker-app-locally-localhost.png)

**Figura 5-13**. Esempio di test dell'applicazione Docker in locale mediante localhost

Se localhost non punta all'IP dell'host Docker, come accade per impostazione predefinita quando si usa Docker CE, per passare al servizio usare l'indirizzo IP della scheda di rete del computer.

Si noti che questo URL nel browser usa la porta 80 per lo specifico contenitore di esempio di cui si tratta. Tuttavia internamente le richieste vengono reindirizzate alla porta 5000 perché è stato distribuito in questo modo con il comando docker run, come illustrato nel passaggio precedente.

È anche possibile testare l'applicazione usando curl dal terminale, come illustrato nella figura 5-14. In un'installazione di Docker in Windows, il valore IP dell'host Docker predefinito è sempre 10.0.75.1 in aggiunta all'indirizzo IP effettivo del computer.

![L'output della console è quello di ottenere la http://10.0.75.1/API/values con curl.](./media/docker-app-development-workflow/test-docker-app-locally-curl.png)

**Figura 5-14**. Esempio di test dell'applicazione Docker in locale mediante curl

### <a name="testing-and-debugging-containers-with-visual-studio-2017"></a>Test e debug di contenitori con Visual Studio 2017

Quando si eseguono contenitori e se ne esegue il debug con Visual Studio 2017, è possibile eseguire il debug dell'applicazione .NET nello stesso modo che si userebbe per l'esecuzione senza contenitori.

### <a name="testing-and-debugging-without-visual-studio"></a>Test e debug senza Visual Studio

Se si sviluppa usando l'approccio editor/CLI, eseguire il debug dei contenitori è più difficile ed è preferibile farlo usando la generazione di tracce.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Debug delle applicazioni in un contenitore Docker locale** \
  [https://docs.microsoft.com/visualstudio/containers/edit-and-refresh](/visualstudio/containers/edit-and-refresh)

- **Steve Lasker. Compila, Esegui il debug, Distribuisci ASP.NET Core app con Docker.** Video. \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T115>

## <a name="simplified-workflow-when-developing-containers-with-visual-studio"></a>Flusso di lavoro semplificato per lo sviluppo di contenitori con Visual Studio

Il flusso di lavoro quando si usa Visual Studio è molto più semplice rispetto all'uso dell'approccio editor/CLI. La maggior parte dei passaggi richiesti da Docker correlati ai file Dockerfile e docker-compose.yml sono nascosti o semplificati da Visual Studio, come illustrato nella figura 5-15.

:::image type="complex" source="./media/docker-app-development-workflow/simplified-life-cycle-containerized-apps-docker-cli.png" alt-text="Diagramma che illustra i cinque passaggi semplificati necessari per creare un'app.":::
Il processo di sviluppo per le app docker: 1-scrivere il codice dell'app, 2-scrivere Dockerfile/s, 3-creare immagini definite in Dockerfile/s, 4-(facoltativo) comporre servizi nel file Docker-compose. yml, 5-eseguire il contenitore o l'app Docker-compose, 6 testare l'app o i microservizi, 7 push nel repository e ripetere.
:::image-end:::

**Figura 5-15**. Flusso di lavoro semplificato per lo sviluppo con Visual Studio

Inoltre è sufficiente eseguire una sola volta il passaggio 2, ovvero l'aggiunta del supporto Docker ai progetti. Pertanto il flusso di lavoro è simile alle attività di sviluppo normale quando si usa .NET per qualsiasi altro tipo di sviluppo. È necessario sapere cosa succede dietro le quinte, ad esempio il processo di creazione delle immagini, le immagini di base in uso, la distribuzione dei contenitori e così via. In alcuni casi è anche necessario modificare il Dockerfile o il file docker-compose.yml per personalizzare i comportamenti. Se si usa Visual Studio la maggior parte del lavoro viene notevolmente semplificata e la produttività è maggiore.

### <a name="additional-resources"></a>Risorse aggiuntive

- **Sviluppo di Docker .NET con Visual Studio 2017** \
  <https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T111>

## <a name="using-powershell-commands-in-a-dockerfile-to-set-up-windows-containers"></a>Uso dei comandi di PowerShell in un Dockerfile per configurare contenitori Windows

I [contenitori Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/index) consentono di convertire applicazioni Windows esistenti in immagini Docker e distribuirle con gli stessi strumenti che si usano con il resto dell'ecosistema Docker. Per usare i contenitori Windows si eseguono i comandi di PowerShell in Dockerfile, come illustrato nell'esempio seguente:

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

- **aspnet-docker/Dockerfile.** Esempi di comandi di PowerShell eseguibili da Dockerfile per includere funzionalità di Windows.\
  <https://github.com/Microsoft/aspnet-docker/blob/master/4.7.1-windowsservercore-ltsc2016/runtime/Dockerfile>

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](../multi-container-microservice-net-applications/index.md)
