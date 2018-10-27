---
title: Flusso di lavoro di sviluppo a ciclo interno per le app Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: be9c3fe165be32df43073919904b85120c52d595
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50034461"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flusso di lavoro di sviluppo a ciclo interno per le app Docker

Prima di attivare il flusso di lavoro ciclo esterno che si estende l'intera DevOps del ciclo, tutto ha inizio in ogni computer dello sviluppatore, scrittura di codice dell'app stessa, usando i propri linguaggi Preferiti o piattaforme e testarla in locale (figura 4-14). Ma in ogni caso, si avrà un aspetto molto importante in comune, indipendentemente da quale linguaggio, framework o piattaforme scelto. In questo flusso di lavoro specifico, sempre sviluppa e si testa i contenitori di Docker, ma in locale.

![](./media/image18.png)

Contesto di sviluppo ciclo interno figura 4-14:

Il contenitore o l'istanza di un'immagine Docker conterrà questi componenti:

-   Una selezione del sistema operativo (ad esempio, una distribuzione Linux o Windows)

-   File aggiunti dallo sviluppatore (ad esempio, file binari dell'app)

-   Configurazione (ad esempio, le impostazioni di ambiente e le dipendenze)

-   Istruzioni per i processi eseguiti da Docker

È possibile impostare il flusso di lavoro di sviluppo a ciclo interno che prevede l'utilizzo di Docker come il processo (descritto nella sezione successiva). Tenere conto che i passaggi iniziali per configurare l'ambiente non è incluso, perché è necessario eseguire tale operazione una sola volta.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Creazione di una singola app all'interno di un contenitore Docker usando Visual Studio Code e CLI di Docker

Le app sono composti da servizi e librerie aggiuntive (dipendenze).

Figura 4-15 illustra i passaggi di base che è in genere necessario eseguire durante la creazione di un'app Docker, seguita da una descrizione dettagliata di ogni passaggio.

![](./media/image19.png)

Figura 4-15: flusso di lavoro generale per il ciclo di vita per applicazioni Docker in contenitori usando l'interfaccia CLI di Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Passaggio 1: Avviare la codifica in Visual Studio Code e creare la linea di base di app/servizio iniziale

Il modo in cui si sviluppa l'applicazione è molto simile al modo in che cui avviene senza Docker. La differenza è che durante lo sviluppo, distribuzione e test di applicazioni o servizi in esecuzione all'interno di contenitori Docker inseriti nell'ambiente locale (ad esempio, una VM Linux o Windows).

**Configurazione dell'ambiente locale**

Con le versioni più recenti di Docker per Mac e Windows, è più facile che mai per lo sviluppo di applicazioni di Docker, e il programma di installazione è semplice.

**Altre informazioni** per istruzioni sulla configurazione di Docker per Windows, vedere [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).

Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.

Inoltre, è necessario un editor di codice in modo che è effettivamente possibile sviluppare l'applicazione quando si usa l'interfaccia CLI di Docker.

Microsoft fornisce Visual Studio Code, ovvero un editor di codice leggero che è supportato in Mac, Windows e Linux e offre il supporto IntelliSense con [supporto per molti linguaggi](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python e la maggior parte moderni linguaggi), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [supporto delle estensioni](https://code.visualstudio.com/docs/extensions/overview). Questo editor è un candidato ideale per sviluppatori Mac e Linux. In Windows, è anche possibile usare l'applicazione completa di Visual Studio.

**Altre informazioni** per istruzioni sull'installazione di Visual Studio per Windows, Mac o Linux, vedere <https://code.visualstudio.com/docs/setup/setup-overview/>.

È possibile lavorare con CLI di Docker e scrivere il codice usando qualsiasi editor di codice, ma se si usa Visual Studio Code, rende il è più facile autore Dockerfile e docker-Compose. yml file nell'area di lavoro. Inoltre, è possibile eseguire le attività Visual Studio Code dall'IDE che richiederà gli script che possono essere in esecuzione di operazioni elaborate tramite la CLI di Docker di sotto.

Visual Studio Code viene fornito da un'estensione, che è necessario installare. A tale scopo, premere Ctrl + MAIUSC + P, digitare **ext installare**, quindi eseguire le estensioni: comando per l'estensione installa per visualizzare l'elenco di estensioni di Marketplace. Successivamente, digitare **docker** per filtrare i risultati e quindi selezionare il file Dockerfile e il File Docker Compose (yml) estensione del supporto, come illustrato nella figura 4-16.

![](./media/image20.png)

Figura 4-16: installazione dell'estensione Docker in Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Passaggio 2: Creare un DockerFile correlato a un'immagine esistente (normale del sistema operativo o ambienti di sviluppo, come Ruby, Node. js e .NET Core)

È necessario un DockerFile per ogni immagine personalizzata da compilare e ogni contenitore da distribuire, pertanto, se l'app è costituita da un solo servizio personalizzato, sarà necessario un solo DockerFile. Tuttavia, se l'app è costituita da più servizi (ad esempio un'architettura di microservizi), è necessario un Dockerfile per ogni servizio.

Il DockerFile viene in genere posizionato all'interno della cartella radice dell'app o del servizio e contiene i comandi necessari in modo che Docker sa come configurare ed eseguire tale applicazione o servizio. È possibile creare i DockerFile e aggiungerlo al progetto insieme a codice (Node. js, .NET Core, e così via), o, se si ha familiarità con l'ambiente, esaminiamo il suggerimento seguente.

> [!TIP]
> È possibile usare uno strumento da riga di comando denominato [yo docker](https://github.com/Microsoft/generator-docker), che esegue scaffolding delle file dal progetto nella lingua si sceglie e aggiunge i file di configurazione di Docker necessari. In pratica, per assistere gli sviluppatori Guida introduttiva, viene creato il documento DockerFile appropriato, docker-Compose. yml e altri script associato per compilare ed eseguire i contenitori Docker. Il generatore yeoman richiederà alcune domande, porre l'host del contenitore selezionato sviluppo language e di destinazione.

![yo docker](./media/image21.png)

Ad esempio, nella figura 4-17 due schermate dai terminali in Windows e in un computer Mac, in entrambi i casi, in esecuzione yo docker, che genera i codice progetti di esempio (attualmente .NET Core, Golang e Node. js come lingue supportate) già configurati per l'utilizzo in parte superiore di Docker.

![](./media/image22.PNG)  ![](./media/image23.png)

Figura 4-17: yo docker strumento di comando in Windows (left) e in un computer Mac

Figura 4-18 presenta un esempio di uso di yo docker dopo aver creato un progetto .NET Core esistente in grado di essere sottoposto a scaffolding.

![](./media/image24.PNG)

Figura 4-18: yo docker con una versione esistente di .NET Core project posto

Da DockerFile, è specificare quale immagine Docker di base sarà possibile usare (ad esempio, tramite "da microsoft/dotnet:1.0.0-core"). È in genere compilerà l'immagine personalizzata all'inizio di un'immagine di base che è possibile ottenere da qualsiasi repository ufficiale nel [registro Docker Hub](https://hub.docker.com/) (ad esempio un [immagine per .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o uno [per Node. js](https://hub.docker.com/_/node/)).

***Opzione a: usare un'immagine Docker ufficiale esistente***

Uso di un repository ufficiale di uno stack di linguaggio con un numero di versione garantisce che le stesse funzionalità del linguaggio sono disponibili in tutti i computer (tra cui sviluppo, test e produzione).

Seguito è riportato un esempio di DockerFile per un contenitore di .NET Core:

```
# Base Docker image to use
FROM microsoft/aspnetcore:1.0.1\

# Set the Working Directory and files to be copied to the image
ARG source
WORKDIR /app
COPY ${source:-bin/Release/PublishOutput} .

# Configure the listening port to 80 (Internal/Secured port within Docker host)
EXPOSE 80

# Application entry point
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

In questo caso, Usa la versione 1.0.1 dell'immagine ASP.NET Core Docker ufficiale per Linux denominato microsoft/aspnetcore:1.0.1. Per altri dettagli, consultare il [pagina di ASP.NET Core Docker Image](https://hub.docker.com/r/microsoft/aspnetcore/) e il [pagina di .NET Core Docker Image](https://hub.docker.com/r/microsoft/dotnet/). È anche possibile usare un'altra immagine confrontabile, ad esempio il nodo: 4-onbuild per Node. js o molte altre immagini preconfigurate per i linguaggi di sviluppo, sono disponibili all'indirizzo [Hub Docker](https://hub.docker.com/explore/).

Nel DockerFile, è necessario anche indicare a Docker in ascolto sulla porta TCP si userà in fase di esecuzione (ad esempio la porta 80).

Sono presenti altre righe di configurazione che è possibile aggiungere nel DockerFile a seconda del linguaggio/framework in uso, in modo che Docker sa come eseguire l'app. Ad esempio, è necessario la riga ENTRYPOINT con \["dotnet", "MyCustomMicroservice.dll"\] per eseguire un'app .NET Core, anche se è possibile avere più varianti a seconda dell'approccio per compilare ed eseguire il servizio. Se si usa il SDK e una riga di comando dotnet per compilare ed eseguire l'app .NET, potrebbe essere leggermente diverso. La conclusione è che la riga ENTRYPOINT e altre righe saranno diverse a seconda del linguaggio o piattaforma che scelta per l'applicazione.

**Altre informazioni** per informazioni sulla compilazione di immagini Docker per applicazioni .NET Core, vedere <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.

Per altre informazioni sulla creazione di immagini personalizzate, passare a [ https://docs.docker.com/engine/\ esercitazioni/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).

**Repository di immagini multipiattaforma**

Man mano che diventano i contenitori di Windows più prevalenti, un singolo repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e Windows. Si tratta di una nuova funzionalità di Docker che rende possibile per i fornitori di usare un unico repository per coprire più piattaforme, quali [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, che sono disponibili nel Registro di sistema DockerHub. Man mano che la funzionalità attiva, il pull di questa immagine da un host Windows richiamerà la variante di Windows, mentre il pull lo stesso nome di immagine da un host Linux richiamerà la variante Linux.

***Opzione b: creare l'immagine di base da zero***

È possibile creare la propria immagine di base di Docker da zero, come illustrato in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) da Docker. Questo è uno scenario che probabilmente non è adatto a te se si sta iniziando con Docker, ma se si desidera impostare i bit specifici della propria immagine di base, è possibile farlo.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Passaggio 3: Creare le immagini Docker personalizzate in essa l'incorporamento del servizio

Per ogni servizio personalizzata che comprende l'app, è necessario creare un'immagine correlata. Se l'app è costituito da un singolo servizio o un'app web, è necessario avere una sola immagine.

> [!NOTE]
> Quando prendendo in considerazione il "ciclo esterno flusso di lavoro DevOps", le immagini verranno create da un processo di compilazione automatica ogni volta che si esegue il push del codice sorgente in un repository Git (Continuous Integration) in modo che le immagini verranno create in quell'ambiente globale dal codice sorgente.

Tuttavia, prima che passa a tale route ciclo esterno, è necessario verificare che l'applicazione Docker in realtà funziona correttamente in modo che non sono push del codice che potrebbe non funzionare correttamente per il sistema di controllo sorgente (Git e così via).

Pertanto, ogni sviluppatore deve prima eseguire l'intero processo di ciclo interno per testare in locale e continuare a sviluppare fino a quando non desiderano eseguire il push di una funzionalità completa o modificare il sistema di controllo sorgente.

Per creare un'immagine nell'ambiente locale e Usa il DockerFile, è possibile usare il comando docker build, come illustrato nella figura 4-19 (è anche possibile eseguire docker-compose up-- compilazione per applicazioni composte da diversi contenitori/servizi).

![](./media/image25.png)

Figura 4-19: esecuzione di compilazione di docker

Facoltativamente, anziché eseguire direttamente docker build dalla cartella del progetto, è innanzitutto possibile generare una cartella distribuibile con le librerie di .NET necessarie tramite l'esecuzione di dotnet publish di e quindi eseguire la compilazione docker.

In questo esempio verrà creata un'immagine Docker con il nome cesardl/netcore-webapi-microservizio-docker: first (: first è un tag, ad esempio una versione specifica). È possibile eseguire questo passaggio per ogni immagine personalizzata che è necessario creare per l'applicazione Docker composta con diversi contenitori.

È possibile trovare le immagini esistenti nel repository locale (computer di sviluppo) usando docker immagini comando, come illustrato nella figura 4-20.

![](./media/image26.png)

La figura 4-20: visualizzazione di immagini esistente con le immagini docker

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Passaggio 4: (Facoltativo) definire i servizi in docker-Compose. yml quando si compila un'applicazione Docker composta con più servizi

Con il file docker-Compose. yml è possibile definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione illustrati nella sezione Passaggio successiva.

È necessario creare file in principale o la cartella soluzione radice; deve avere un contenuto simile al file docker-Compose. yml seguente:

```yml
version: '2'
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

In questo caso particolare, questo file definisce due servizi: il servizio web (il servizio personalizzato) e il servizio redis (un servizio popolare cache). Ogni servizio verrà distribuito come un contenitore, pertanto è necessario usare un'immagine Docker concreta per ognuno. Per questo servizio web specifico, l'immagine dovrà eseguire le operazioni seguenti:

-   Compilazione del dockerfile nella directory corrente

-   Inoltrare la porta 80 esposta sul contenitore alla porta 81 nel computer host

-   Montare la directory del progetto nell'host in cui /code all'interno del contenitore, rendendo possibile la modifica del codice senza dover ricompilare l'immagine

-   Collegare il servizio web al servizio redis

Il servizio redis Usa il [immagine redis pubblica più recente](https://hub.docker.com/_/redis/) estratto dal registro Docker Hub. [redis](https://redis.io/) è un sistema di cache molto diffusa per le applicazioni lato server.

### <a name="step-5-build-and-run-your-docker-app"></a>Passaggio 5: Compilare ed eseguire l'app Docker

Se l'app ha solo un singolo contenitore, è sufficiente eseguirla distribuendola all'host Docker (macchina virtuale o server fisico). Tuttavia, se l'app è costituita da più servizi, devi *comporlo*anche. Esaminiamo le diverse opzioni.

***Opzione di esecuzione di r: un singolo contenitore o un servizio***

È possibile eseguire l'immagine Docker usando il comando docker run, come illustrato di seguito:

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

Si noti che per questa distribuzione specifica, si saranno essere reindirizzando le richieste inviate alla porta 80 alla porta interna 5000. A questo punto, l'applicazione è in ascolto sulla porta esterna 80 a livello di host.

***Opzione b: Compose ed eseguire un'applicazione di più contenitori***

Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà essere composte da più servizi. In questi casi, è possibile eseguire il comando docker-compose backup (figura 4-21), che userà il file docker-Compose. yml che è stato creato in precedenza. Questo comando consente di distribuire un'applicazione composta con tutti i contenitori correlati.

![](./media/image27.png)

Figura 4-21: risultati dell'esecuzione del comando "docker-compose up"

Dopo l'esecuzione di docker-compose backup, si distribuisce l'applicazione e i relativi contenitori correlati nell'Host Docker, come illustrato nella figura 4-22, la rappresentazione in forma di macchina virtuale.

![](./media/image28.png)

Figura 4-22: macchina virtuale con contenitori Docker distribuiti

Nota comando docker-compose up e docker eseguire potrebbe essere sufficiente per il test dei contenitori nell'ambiente di sviluppo, ma non usarli affatto se si prevede di gestire i cluster Docker e gli agenti di orchestrazione come Docker Swarm, Mesosphere DC/OS o Kubernetes Per poter essere in grado di aumentare le prestazioni. Se si usa un cluster, ad esempio [modalità Docker Swarm](https://docs.docker.com/engine/swarm/) , disponibile in Docker per Windows e Mac dalla versione 1.12, è necessario distribuire e testare con comandi aggiuntivi, ad esempio per servizi singoli di creazione servizio docker, o quando si è distribuzione di un'app composte da diversi contenitori, usando docker compose bundle e distribuzione docker myBundleFile, distribuendo l'app composto come uno stack, come illustrato nell'articolo [bundle dell'applicazione distribuita](https://blog.docker.com/2016/06/docker-app-bundle/) da Docker.

Per la [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](https://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) si usano i comandi di distribuzione diversi e gli script, nonché.

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Passaggio 6: Testare l'applicazione Docker (in locale, nella macchina virtuale locale CD)

Questo passaggio varia a seconda di ciò che esegue l'app.

In un semplice .NET Core API Web "Hello World" distribuito come un singolo contenitore o un servizio, è sufficiente accedere al servizio, fornendo la porta TCP specificata nel DockerFile.

Se localhost non è attivata, per passare al servizio, trovare l'indirizzo IP per la macchina tramite questo comando:

docker machine ip *your-container-name*

Nell'host Docker, aprire un browser e passare a tale sito. il servizio app/in esecuzione, verrà visualizzato come illustrato nella figura 4-23.

![](./media/image29.png)

Figura 4-23: test dell'applicazione Docker in locale mediante localhost

Si noti che utilizza la porta 80, ma internamente è stata viene reindirizzata alla porta 5000 perché si tratta di come è stata distribuita con docker run, come illustrato in precedenza.

È possibile verificarlo usando CURL dal terminale. In un'installazione di Docker in Windows, l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4-24.

![](./media/image30.png)

La figura 4-24: test di un'applicazione Docker in locale mediante CURL

**Debug di un contenitore in esecuzione in Docker**

Visual Studio Code supporta debug Docker se si usa Node. js e altre piattaforme quali contenitori .NET Core.

È anche possibile eseguire il debug dei contenitori di .NET Core in Docker quando si usa Visual Studio, come descritto nella sezione successiva.

**Altre informazioni:** per altre informazioni sul debug di contenitori Docker di Node. js, passare alla <https://blog.docker.com/2016/07/live-debugging-docker/> e [ https://blogs.msdn.microsoft.com/\ utente\_ed/2016/02/27 o Visual-Studio-code-New-Features-13-big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).


>[!div class="step-by-step"]
[Precedente](docker-apps-development-environment.md)
[Successivo](visual-studio-tools-for-docker.md)
