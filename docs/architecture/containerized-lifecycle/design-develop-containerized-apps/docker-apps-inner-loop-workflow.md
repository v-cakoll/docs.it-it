---
title: Flusso di lavoro di sviluppo del ciclo interno per le app Docker
description: Informazioni sul flusso di lavoro del ciclo interno per lo sviluppo di applicazioni Docker.
ms.date: 02/15/2019
ms.openlocfilehash: bce047bd5ba75f9ef652a294ff6a15656fc5ac34
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738412"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flusso di lavoro di sviluppo del ciclo interno per le app Docker

Prima di attivare il flusso di lavoro del ciclo esterno che coinvolge l'intero ciclo DevOps, è necessario che tutto abbia inizio nel computer dello sviluppatore. Si scrive il codice dell'app stessa usando i linguaggi o le piattaforme preferiti, e la si testa in locale (figura 4-21). In ogni caso, la questione importante è una. Indipendentemente dal linguaggio, dal framework o dalle piattaforme scelti, in questo flusso di lavoro specifico si sviluppano e testano sempre contenitori Docker, ma a livello locale.

![Diagramma che mostra il concetto di ambiente di sviluppo del ciclo interno.](./media/docker-apps-inner-loop-workflow/inner-loop-development-context.png)

**Figura 4-21**. Contesto di sviluppo del ciclo interno

Il contenitore o l'istanza di un'immagine Docker conterrà i componenti seguenti:

- Un sistema operativo a scelta, ad esempio una distribuzione Linux o Windows

- File aggiunti dallo sviluppatore, ad esempio file binari dell'app

- Informazioni di configurazione, ad esempio impostazioni di ambiente e dipendenze

- Istruzioni per i processi che Docker dovrà eseguire

È possibile configurare il flusso di lavoro di sviluppo del ciclo interno che prevede l'uso di Docker come processo. Questo processo viene descritto nella sezione successiva. Tenere presente che i passaggi iniziali per configurare l'ambiente non sono inclusi, perché è sufficiente eseguire la configurazione una sola volta.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Compilazione di una singola app all'interno di un contenitore Docker usando Visual Studio Code e l'interfaccia della riga di comando di Docker

Le app sono costituite da servizi personalizzati e raccolte aggiuntive, vale a dire dipendenze.

La figura 4-22 illustra i passaggi di base che devono essere generalmente eseguiti per compilare un'app Docker e le descrizioni dettagliate di ogni passaggio.

![Diagramma che mostra i sette passaggi necessari per creare un'app in contenitori.](./media/docker-apps-inner-loop-workflow/life-cycle-containerized-apps-docker-cli.png)

**Figura 4-22**. Flusso di lavoro generale del ciclo di vita di applicazioni Docker in contenitori tramite l'interfaccia della riga di comando di Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Passaggio 1: Avviare la codifica nel codice di Visual Studio e creare la linea di base iniziale dell'app/servizioStep 1: Start coding in Visual Studio Code and create your initial app/service baseline

Sviluppare un'applicazione Docker è simile a sviluppare un'applicazione senza l'uso di Docker. La differenza consiste nel fatto che, durante lo sviluppo, l'applicazione o i servizi vengono distribuiti e testati mentre sono in esecuzione all'interno di contenitori Docker nell'ambiente locale, ad esempio una macchina virtuale Linux o Windows.

**Configurare l'ambiente locale**

Con le versioni più recenti di Docker per Mac e Windows, sviluppare applicazioni Docker non è mai stato tanto semplice e la configurazione è molto facile.

> [!TIP]
> Per istruzioni sulla configurazione di Docker per Windows, passare a <https://docs.docker.com/docker-for-windows/>.
>
>Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.

Sarà anche necessario un editor di codice, con il quale sarà effettivamente possibile sviluppare l'applicazione usando al tempo stesso l'interfaccia della riga di comando di Docker.

Microsoft fornisce Visual Studio Code, che è un editor di codice leggero che è supportato in Windows, Linux e macOS e fornisce IntelliSense con [il supporto per molti linguaggi](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python e la maggior parte dei linguaggi moderni), [debug](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [le estensioni supportano](https://code.visualstudio.com/docs/extensions/overview). Questo editor è una grande misura per gli sviluppatori macOS e Linux. In Windows, you can also use Visual Studio.

> [!TIP]
> Per istruzioni sull'installazione di Visual Studio Code per Windows, <https://code.visualstudio.com/docs/setup/setup-overview/>Linux o macOS, visitare il percorso .
>
> Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.

È possibile usare l'interfaccia della riga di comando di Docker e scrivere il codice usando qualsiasi editor di codice. L'uso di Visual Studio Code con l'estensione Docker consente però di creare facilmente file `Dockerfile` e `docker-compose.yml` nell'area di lavoro. Usando l'interfaccia della riga di comando di Docker riportata di seguito, è anche possibile eseguire attività e script dall'IDE di Visual Studio Code per eseguire comandi di Docker.

L'estensione Docker per Visual Studio Code offre le funzionalità seguenti:

- Generazione automatica dei file `Dockerfile` e `docker-compose.yml`

- Evidenziazione della sintassi e suggerimenti al passaggio del mouse sui file `docker-compose.yml` e `Dockerfile`

- IntelliSense (completamenti) per i file `Dockerfile` e `docker-compose.yml`

- Analisi (errori e avvisi) per i file `Dockerfile`

- Integrazione del riquadro comandi (F1) per la maggior parte dei comuni comandi di Docker

- Integrazione dell'utilità di esplorazione per la gestione di immagini e contenitori

- Distribuzione di immagini da Docker Hub e da registri contenitori Azure in Servizio app di Azure

Per installare l'estensione Docker, premere CTRL + MAIUSC + P, digitare `ext install`, quindi eseguire il comando Installa estensione per visualizzare l'elenco delle estensioni del Marketplace. Successivamente, digitare **docker** per filtrare i risultati, quindi selezionare l'estensione del supporto per Docker come illustrato nella figura 4-23.

![Visualizzazione dell'estensione Docker per Visual Studio Code.](./media/docker-apps-inner-loop-workflow/install-docker-extension-vs-code.png)

**Figura 4-23**. Installazione dell'estensione Docker in Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Passaggio 2: Creare un DockerFile correlato a un'immagine esistente (ambienti OS o dev semplici come .NET Core, Node.js e Ruby)

Per ogni immagine da creare e per ogni contenitore da implementare è necessario un `DockerFile`. Se l'app è costituita da un solo servizio personalizzato, sarà necessario un singolo `DockerFile`. Se invece l'app è costituita da più servizi, come nel caso di un'architettura di microservizi, sarà necessario un `Dockerfile` per ogni servizio.

Il `DockerFile` viene comunemente inserito nella cartella radice dell'app o del servizio e contiene i comandi necessari che indicano a Docker come configurare ed eseguire l'app o il servizio. È possibile creare il `DockerFile` e aggiungerlo al progetto insieme al codice (Node.js, .NET Core e così via), oppure se non si ha familiarità con l'ambiente, è consigliabile leggere il suggerimento seguente.

> [!TIP]
> È possibile usare l'estensione Docker per avere indicazioni sull'uso dei file `Dockerfile` e `docker-compose.yml` correlati ai contenitori Docker. Probabilmente alla fine non si userà questo strumento per scrivere questi tipi di file. L'estensione Docker resta comunque un buon punto di partenza che consente di accelerare la curva di apprendimento.

La figura 4-24 visualizza come il file docker-compose viene aggiunto usando l'estensione Docker per Visual Studio Code.

![Visualizzazione della console dell'estensione Docker per Visual Studio Code.](./media/docker-apps-inner-loop-workflow/add-docker-files-to-workspace-command.png)

**Figura 4-24**. File Docker aggiunti usando il **comando Add Docker files to Workspace** (Aggiungi file Docker all'area di lavoro)

Quando si aggiunge un DockerFile, si specifica l'immagine Docker `FROM mcr.microsoft.com/dotnet/core/aspnet`di base da utilizzare , ad esempio using . Si creerà generalmente l'immagine personalizzata sulla base di un'immagine disponibile in un qualsiasi repository ufficiale nel [registro Docker Hub](https://hub.docker.com/), ad esempio un'[immagine per .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) o una [per Node.js](https://hub.docker.com/_/node/).

***Usare un'immagine Docker ufficiale esistente***

L'uso di un repository ufficiale di uno stack di linguaggio con un numero di versione assicura che le stesse funzionalità del linguaggio siano disponibili in tutti i computer, inclusi quelli di sviluppo, test e produzione.

Di seguito viene riportato un esempio di Dockerfile per un contenitore .NET Core:

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

In questo caso l'immagine si basa sulla versione 2.2 dell'immagine Docker ufficiale di ASP.NET Core (multiarchitettura per Linux e Windows), come indicato dalla riga `FROM mcr.microsoft.com/dotnet/core/aspnet:2.2`. Per altre informazioni su questo argomento, vedere la pagina [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) (Immagine Docker di ASP.NET Core) e la pagina [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) (Immagine Docker di .NET Core).

Nel Dockerfile è possibile indicare a Docker la porta TCP di ascolto che si userà in fase di esecuzione, ad esempio la porta 80.

Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso. Ad esempio la riga `ENTRYPOINT` con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker di eseguire un'applicazione .NET Core. Se si usa l'SDK e l'interfaccia della riga di comando di .NET Core(`dotnet CLI`) per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa. In sostanza la riga ENTRYPOINT e altre impostazioni dipendono dal linguaggio e della piattaforma scelti per l'applicazione.

> [!TIP]
> Per altre informazioni sulla creazione di immagini Docker per applicazioni .NET Core, passare a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.
>
> Per altre informazioni sulla creazione di immagini personalizzate, passare a <https://docs.docker.com/engine/tutorials/dockerimages/>.

**Usare repository di immagini multiarchitettura**

Un singolo nome di un'immagine in un repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine Windows. Questa funzionalità consente a fornitori come Microsoft, che sono creatori di immagini di base, di creare un unico repository per più piattaforme, ad esempio Linux e Windows. Il repository [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) disponibile nel registro Docker Hub offre ad esempio supporto per Linux e Windows Nano Server usando lo stesso nome immagine.

Eseguendo il pull dell'immagine [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) da un host Windows si ottiene la variante Windows mentre se si esegue il pull dello stesso nome immagine da un host Linux si ottiene la variante Linux.

***Creare l'immagine di base da zero***

È possibile creare l'immagine Docker di base personalizzata da zero, come descritto in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) usando Docker. Non si tratta probabilmente dello scenario più adatto se non si ha ancora familiarità con Docker. È tuttavia possibile adottare questo approccio se si vogliono impostare i bit specifici dell'immagine di base personalizzata.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Passaggio 3: Creare le immagini Docker personalizzate incorporando il servizio in esso

Per ogni servizio personalizzato comprensivo dell'app sarà necessario creare un'immagine correlata. Se l'app è costituita da un singolo servizio o una singola app Web, sarà sufficiente una sola immagine.

> [!NOTE]
> Se si prende in considerazione il "flusso di lavoro del ciclo esterno di DevOps", le immagini saranno create da un processo di compilazione automatico ogni volta che si esegue il push del codice sorgente in un repository Git (integrazione continua). In questo modo le immagini saranno create in quell'ambiente globale partendo dal codice sorgente.
>
> Prima di poter considerare il ciclo esterno, è necessario verificare effettivamente che l'applicazione Docker funzioni correttamente in modo che non venga eseguito il push di codice che potrebbe non funzionare nel sistema di controllo del codice sorgente (Git e così via).
>
> Gli sviluppatori devono quindi prima di tutto eseguire l'intero processo del ciclo interno per testarlo in locale e continuare lo sviluppo finché vogliono eseguire il push di una funzionalità completa oppure passare al sistema di controllo del codice sorgente.

Per creare un'immagine nell'ambiente locale e utilizzando il DockerFile, è possibile utilizzare il comando docker `docker-compose up --build` build, come illustrato nella figura 4-25 (è anche possibile eseguire per le applicazioni composte da diversi contenitori/servizi).

![Screenshot che mostra l'output della console del comando docker build.](./media/docker-apps-inner-loop-workflow/run-docker-build-command.png)

**Figura 4-25**. Esecuzione del comando docker build

Oppure, anziché eseguire direttamente `docker build` dalla cartella di progetto, è possibile prima generare una cartella distribuibile con le librerie di .NET necessarie usando il comando di esecuzione `dotnet publish`, poi eseguire `docker build`.

Questo esempio crea un'immagine Docker denominata `cesardl/netcore-webapi-microservice-docker:first`. `:first` è un tag, ad esempio una versione specifica. È possibile eseguire questo passaggio per ogni immagine personalizzata che si vuole creare per l'applicazione Docker composta con diversi contenitori.

È possibile trovare le immagini esistenti nel repository locale del computer di sviluppo usando il comando docker images, come illustrato nella figura 4-26.

![Output della console del comando docker images che illustra le immagini esistenti.](./media/docker-apps-inner-loop-workflow/view-existing-images-with-docker-images.png)

**Figura 4-26**. Visualizzazione delle immagini esistenti usando il comando docker images

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Passaggio 4: Definire i servizi in docker-compose.yml quando si crea un'app Docker composta con più serviziStep 4: Define your services in docker-compose.yml when building a composed Docker app with multiple services

Il file `docker-compose.yml` consente di definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione illustrati nel passaggio della sezione successiva.

Creare il file nella cartella principale o radice della soluzione con un contenuto simile a quello illustrato nel file `docker-compose.yml`:

```yml
version: '3.4'
services:
  web:
    build: .
    ports:
     - "81:80"
    volumes:
     - .:/code
    depends_on:
     - redis
  redis:
    image: redis
```

In questo caso particolare il file definisce due servizi: il servizio Web, vale a dire il servizio personalizzato, e il servizio Redis, un comune servizio cache. Ogni servizio verrà distribuito come contenitore, quindi è necessaria un'immagine Docker concreta per ognuno. Per questo servizio Web specifico, l'immagine dovrà eseguire le operazioni seguenti:

- Eseguire la compilazione dal Dockerfile nella directory corrente

- Inoltrare la porta 80 esposta nel contenitore alla porta 81 nel computer host

- Montare la directory del progetto nell'host/nel codice all'interno del contenitore, in modo che sia possibile modificare il codice senza dover creare nuovamente l'immagine

- Collegare il servizio Web al servizio Redis

Il servizio Redis usa l'[immagine Redis pubblica più recente](https://hub.docker.com/_/redis/) di cui si esegue il pull dal registro Docker Hub. [Redis](https://redis.io/) è un sistema comune di cache per applicazioni lato server.

### <a name="step-5-build-and-run-your-docker-app"></a>Passaggio 5: Creare ed eseguire l'app DockerStep 5: Build and run your Docker app

Se l'app ha un solo contenitore, è possibile eseguirla distribuendola all'host Docker, vale a dire una macchina virtuale o un server fisico. Se invece l'app è costituita da più servizi, è anche necessario *comporla*. Esistono opzioni diverse.

***Opzione A: Eseguire un singolo contenitore o servizioOption A: Run a single container or service***

È possibile eseguire l'immagine Docker usando il comando docker run, come illustrato di seguito:

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

Per questo tipo specifico di distribuzione, le richieste inviate alla porta 80 saranno reindirizzate alla porta interna 5000. A questo punto l'applicazione si trova in ascolto sulla porta esterna 80 a livello di host.

***Opzione B: comporre ed eseguire un'applicazione con più contenitoriOption B: Compose and run a multiple-container application***

Nella maggior parte degli scenari aziendali un'applicazione Docker sarà composta da più servizi. In questi casi è possibile eseguire il comando `docker-compose up` (figura 4-27), che userà il file docker-compose.yml che probabilmente è stato creato in precedenza. Se eseguito, questo comando distribuisce un'applicazione composta con tutti i relativi contenitori correlati.

![Output della console del comando docker-compose up.](./media/docker-apps-inner-loop-workflow/results-docker-compose-up.png)

**Figura 4-27**. Risultati ottenuti eseguendo il comando "docker-compose up"

Dopo aver eseguito il comando `docker-compose up`, l'applicazione e i relativi contenitori correlati vengono distribuiti nell'host Docker, come illustrato nella figura 4-28 (rappresentazione delle macchina virtuale).

![Macchina virtuale che esegue applicazioni con più contenitori.](./media/docker-apps-inner-loop-workflow/vm-with-docker-containers-deployed.png)

**Figura 4-28**. VM con contenitori Docker distribuiti

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Passaggio 6: Testare l'applicazione Docker (localmente, nella macchina virtuale del CD locale)Step 6: Test your Docker application (locally, in your local CD VM)

Questo passaggio varia in base all'ambito dell'app.

In una semplice API Web .NET Core "Hello World" distribuita come un contenitore o servizio singolo sarà sufficiente accedere al servizio specificando la porta TCP indicata nel Dockerfile.

Per passare al servizio quando il localhost non è attivo, trovare l'indirizzo IP del computer usando il comando seguente:

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

Nell'host Docker aprire un browser e passare al sito. Verrà visualizzato il servizio o l'app in esecuzione, come illustrato nella figura 4-29.

![Visualizzazione del browser con la risposta da localhost/API/values.](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-localhost.png)

**Figura 4-29**. Test dell'applicazione Docker in locale tramite localhost

Si noti che si sta usando la porta 80, ma internamente si viene reindirizzati alla porta 5000, in base alla distribuzione eseguita con `docker run`, che è stata illustrata in precedenza.

È possibile testare l'app usando CURL dal terminale. In un'installazione Docker in Windows l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4-30.

![Output della console con http://10.0.75.1/API/values ottenuto tramite CURL](./media/docker-apps-inner-loop-workflow/test-docker-app-locally-curl.png)

**Figura 4-30**. Test di un'applicazione Docker in locale tramite CURL

**Debug di un contenitore in esecuzione in Docker**

Visual Studio Code supporta il debug Docker se si usa Node.js e altre piattaforme, ad esempio contenitori di .NET Core.

È anche possibile eseguire il debug di contenitori .NET Core o .NET Framework in Docker quando si usa Visual Studio per Windows o Mac, come descritto nella sezione successiva.

> [!TIP]
> Per ulteriori informazioni sul debug dei contenitori Docker Node.js, vedere <https://blog.docker.com/2016/07/live-debugging-docker/> e <https://docs.microsoft.com/archive/blogs/user_ed/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more>.

>[!div class="step-by-step"]
>[Successivo](docker-apps-development-environment.md)
>[precedente](visual-studio-tools-for-docker.md)
