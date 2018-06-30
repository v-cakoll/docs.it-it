---
title: Flusso di lavoro di sviluppo di ciclo interno per le app di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 9e578599c61053704202946772c43bdb5ef895c2
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105589"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flusso di lavoro di sviluppo di ciclo interno per le app di Docker

Prima che venga attivato il flusso di lavoro ciclo esterno spanning DevOps intero ciclo, vengono avviate in ogni computer dello sviluppatore, la generazione di codice l'app stessa, utilizzando le piattaforme o linguaggi Preferiti e testarlo in locale (figura 4-14). Ma in ogni caso, si avrà un aspetto molto importante in comune, indipendentemente da quali lingua, framework o piattaforme scelto. In questo flusso di lavoro specifico, sempre sviluppa e si testa dei contenitori di Docker, ma in locale.

![](./media/image18.png)

Contesto di sviluppo Inner loop figura 4-14:

Il contenitore o l'istanza di un'immagine Docker conterrà questi componenti:

-   Una selezione del sistema operativo (ad esempio, una distribuzione di Linux o Windows)

-   File aggiunti dallo sviluppatore (ad esempio, file binari dell'app)

-   Configurazione (ad esempio, le impostazioni di ambiente e le dipendenze)

-   Istruzioni per quali processi eseguiti da Docker

È possibile impostare il flusso di lavoro di sviluppo di ciclo interno che prevede l'utilizzo di Docker come il processo (descritto nella sezione successiva). Prendere in considerazione che i passaggi iniziali per configurare l'ambiente non viene incluso, poiché è necessario eseguire tale operazione una sola volta.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>La creazione di una singola app in un contenitore Docker usando Visual Studio Code e CLI di Docker

Le app vengono eseguite dal proprio servizi più librerie aggiuntive (dipendenze).

Figura 4-15 mostra i passaggi di base che in genere è necessario eseguire quando si compila un'app di Docker, seguita da una descrizione dettagliata di ogni passaggio.

![](./media/image19.png)

Figura 4-15: flusso di lavoro generale per il ciclo di vita delle applicazioni di Docker contenitore con Docker CLI

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Passaggio 1: Avviare la codifica nel codice di Visual Studio e creare la linea di base iniziale/servizio app

Il modo in cui si sviluppa l'applicazione è molto simile a quello che eseguire questa operazione senza Docker. La differenza è che durante lo sviluppo, si distribuisce e si testa l'applicazioni o servizi in esecuzione all'interno di contenitori di Docker inseriti nell'ambiente locale (ad esempio una VM Linux o Windows).

**Configurazione dell'ambiente locale**

Con le versioni più recenti di Docker per Windows e Mac, è più semplice che mai per lo sviluppo di applicazioni di Docker e il programma di installazione è semplice.

**Altre informazioni** per istruzioni sulla configurazione di Docker per Windows, visitare [ https://docs.docker.com/docker-for-windows/ ](https://docs.docker.com/docker-for-windows/).

Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.

Inoltre, è necessario un editor di codice in modo che è effettivamente possibile sviluppare l'applicazione durante l'utilizzo di Docker CLI.

Microsoft fornisce codice di Visual Studio, ovvero un editor di codice semplice che è supportato in Mac, Windows e Linux e fornisce IntelliSense con [supporto per molte lingue](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python e la maggior parte linguaggi moderni), [debug](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [supporto delle estensioni](https://code.visualstudio.com/docs/extensions/overview). Questo editor è un candidato ideale per gli sviluppatori Mac e Linux. In Windows, è anche possibile usare l'applicazione completa di Visual Studio.

**Altre informazioni** per istruzioni sull'installazione di Visual Studio per Windows, Mac o Linux, vedere [ http://code.visualstudio.com/docs/setup/setup-overview/https://docs.docker.com/docker-for-mac/ ](http://code.visualstudio.com/docs/setup/setup-overview/https:/docs.docker.com/docker-for-mac/).

È possibile lavorare con Docker CLI e scrivere il codice utilizzando qualsiasi editor di codice, ma se si utilizza codice di Visual Studio, semplifica ne semplifica l'autore Dockerfile e docker compose.yml file nell'area di lavoro. Inoltre, è possibile eseguire le attività di Visual Studio Code dall'IDE che richiederà script che può essere in esecuzione di operazioni elaborate tramite Docker CLI sotto.

Codice di Visual Studio viene fornito da un'estensione, è necessario installare. A tale scopo, premere Ctrl + MAIUSC + P, digitare **ext installare**, quindi eseguire le estensioni: comando per l'installazione di estensione per visualizzare l'elenco di estensioni di Marketplace. Successivamente, digitare **docker** per filtrare i risultati e quindi selezionare il Dockerfile e Docker comporre File (yml) estensione del supporto, come illustrato nella figura 4-16.

![](./media/image20.png)

Figura 4-16: installazione dell'estensione Docker nel codice di Visual Studio

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Passaggio 2: Creare un DockerFile correlato a un'immagine esistente (normale del sistema operativo o ambienti di sviluppo come Ruby, Node. js e .NET Core)

È necessario un DockerFile per ogni immagine personalizzata da compilare e per ogni contenitore da distribuire, pertanto, se l'app è costituita da un singolo servizio personalizzato, sarà necessario un DockerFile singolo. Tuttavia, se l'app è costituita da più servizi (come in un'architettura di microservizi), è necessario un Dockerfile per ogni servizio.

DockerFile in genere posizionato all'interno della cartella radice dell'applicazione o nel servizio e contiene i comandi necessari in modo che Docker sa come configurare ed eseguire tale app o un servizio. È possibile creare i DockerFile e aggiungerlo al progetto insieme a codice (Node. js, .NET Core e così via), o, se si ha familiarità con l'ambiente, esaminiamo il suggerimento seguente.

> [!TIP]
> È possibile utilizzare uno strumento da riga di comando denominato [yo docker](https://github.com/Microsoft/generator-docker), che esistano file dal progetto in linguaggio si sceglie e aggiunge i file di configurazione di Docker necessari. In pratica, per assistere gli sviluppatori Guida introduttiva, viene creato il DockerFile appropriato, compose.yml docker e gli altri script associato per compilare ed eseguire i contenitori di Docker. Il generatore yeoman verrà richiesto ad alcune domande, porre l'host del contenitore selezionato sviluppo linguaggio e di destinazione.

![yo docker](./media/image21.png)

Ad esempio, nella figura 4-17 mostra due schermate dai terminali in Windows e su un Mac, in entrambi i casi, in esecuzione yo docker, che genera i codice progetti di esempio (attualmente .NET Core Golang e Node. js come lingue supportate) già configurati per l'utilizzo in parte superiore di Docker.

![](./media/image22.PNG)  ![](./media/image23.png)

Figura 4-17: yo docker strumento di comando in Windows (a sinistra) e su un Mac

Figura 4-18 viene presentato un esempio di utilizzo yo docker dopo aver ottenuto un progetto .NET Core esistente nella posizione in cui essere scaffolding.

![](./media/image24.PNG)

Figura 4-18: yo docker con una versione esistente di .NET Core progetto posto

Del dockerfile, specificare quale immagine di Docker base sarà possibile usare (ad esempio tramite "da microsoft/dotnet:1.0.0-core"). Verrà compilato in genere l'immagine personalizzata nella parte superiore di un'immagine di base che è possibile ottenere da qualsiasi repository ufficiale nella [Registro di sistema dell'Hub Docker](https://hub.docker.com/) (come un [immagine per .NET Core](https://hub.docker.com/r/microsoft/dotnet/) o uno [per Node. js](https://hub.docker.com/_/node/)).

***Opzione a: usare un'immagine Docker ufficiale esistente***

Usa un repository ufficiale di uno stack di lingua con un numero di versione assicura che la stessa funzionalità del linguaggio disponibili in tutti i computer (tra cui sviluppo, test e produzione).

Ecco un esempio di DockerFile per un contenitore di .NET Core:

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

In questo caso, utilizzata la versione 1.0.1 dell'immagine di ASP.NET Core Docker ufficiale per Linux denominato microsoft/aspnetcore:1.0.1. Per ulteriori dettagli, consultare il [pagina ASP.NET Core Docker immagine](https://hub.docker.com/r/microsoft/aspnetcore/) e il [pagina .NET Core Docker immagine](https://hub.docker.com/r/microsoft/dotnet/). Sia anche possibile utilizzare un'altra immagine confrontabile, ad esempio il nodo: 4-onbuild per Node. js o molte altre immagini preconfigurate per linguaggi di sviluppo, sono disponibili in [Hub Docker](https://hub.docker.com/explore/).

Nel documento DockerFile, è necessario anche indicano a Docker di in ascolto sulla porta TCP che verrà utilizzato in fase di esecuzione (ad esempio la porta 80).

Sono presenti altre righe di configurazione che è possibile aggiungere in DockerFile a seconda del linguaggio/framework in uso, in modo Docker sa come eseguire l'app. Ad esempio, è necessario con la riga di punto di ingresso \["dotnet", "MyCustomMicroservice.dll"\] per eseguire un'applicazione .NET Core, anche se è possibile avere più varianti in base l'approccio per compilare ed eseguire il servizio. Se si utilizza il SDK e dotnet CLI per compilare ed eseguire l'app .NET, potrebbe essere leggermente diverso. In sostanza è che la riga di punto di ingresso più righe aggiuntive sarà diverse a seconda della lingua/piattaforma che scelto per l'applicazione.

**Altre informazioni** per informazioni sulla creazione di immagini Docker per le applicazioni .NET Core, passare a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.

Per ulteriori informazioni sulla creazione di immagini personalizzate, passare a [ https://docs.docker.com/engine/\ esercitazioni/dockerimages/](https://docs.docker.com/engine/tutorials/dockerimages/).

**Repository di immagini multipiattaforma**

Non appena prevalenti più contenitori di Windows, un unico archivio può contenere le varianti della piattaforma, ad esempio un'immagine Linux e Windows. Si tratta di una nuova funzionalità presto disponibile in Docker che rende possibile per i fornitori di utilizzare un unico repository per coprire più piattaforme, ad esempio [microsoft/aspdotnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) repository, è disponibile a DockerHub del Registro di sistema. Come la funzionalità include alive, questa immagine il pull da un host Windows eseguirà il pull la variante di Windows, mentre lo stesso nome di immagine il pull da un host Linux estrarrà la variante Linux.

***Opzione b: creare l'immagine di base da zero***

È possibile creare la propria immagine di base di Docker da zero, come illustrato in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) da Docker. Si tratta di uno scenario che probabilmente non è più appropriato se si sta avviando solo con Docker, ma se si desidera impostare i bit specifici della propria immagine di base, è possibile farlo.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Passaggio 3: Creare immagini Docker personalizzate durante l'incorporamento del servizio in essa contenuti

Per ogni servizio personalizzata che comprende l'app, dovrai creare un'immagine correlata. Se l'app è costituito da un singolo servizio o l'app web, è necessario solo una singola immagine.

> [!NOTE]
> Quando si prende in considerazione il "ciclo esterno DevOps flusso di lavoro", le immagini verranno create da un processo di compilazione automatizzato ogni volta che si esegue il push del codice sorgente in un repository Git (integrazione continua) in modo che le immagini verranno create in tale ambiente globale dal codice sorgente.

Tuttavia, prima vengono prese in considerazione passare a tale route ciclo esterno, è necessario assicurarsi che l'applicazione di Docker in realtà funziona correttamente in modo da essi non inserire il codice che potrebbe non funzionare correttamente al sistema di controllo di origine (Git e così via).

Pertanto, ogni sviluppatore deve prima effettuare l'intero processo interna ciclo di test in locale e continuare a sviluppare fino a quando non si desidera il push di una funzionalità di completamento o modificare per il controllo del codice sorgente.

Per creare un'immagine in ambiente locale e usano il DockerFile, è possibile utilizzare il comando di compilazione docker, come illustrato nella figura 4-19 (è anche possibile eseguire comporre docker backup - compilazione per le applicazioni composte da diversi contenitori/servizi).

![](./media/image25.png)

Figura 4-19: esecuzione di compilazione docker

Facoltativamente, anziché eseguire direttamente docker compilazione dalla cartella del progetto, è innanzitutto possibile generare una cartella distribuibile con le librerie .NET necessarie tramite dotnet esecuzione comando pubblica e quindi eseguire la compilazione docker.

In questo esempio, si crea un'immagine di Docker con il nome cesardl/netcore-webapi-microservizio-docker: first (: per primo è un tag, ad esempio una versione specifica). È possibile eseguire questo passaggio per ogni immagine personalizzata, che è necessario creare per l'applicazione di Docker composto con diversi contenitori.

È possibile trovare immagini esistenti nel repository locale (computer di sviluppo) tramite docker immagini comando, come illustrato nella figura 4 a 20.

![](./media/image26.png)

Figura 4-20: visualizzazione di immagini esistente con immagini docker

### <a name="step-4-optional-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Passaggio 4: (Facoltativo) definire i servizi in docker-compose.yml quando si compila un'app di Docker composta con più servizi

Con il file compose.yml docker è possibile definire un set di servizi correlati da distribuire come un'applicazione composta con i comandi di distribuzione illustrati nella sezione Passaggio successiva.

È necessario creare file in principale o alla cartella della soluzione radice; è necessario un contenuto simile al file docker compose.yml seguente:

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

In questo caso specifico, questo file definisce due servizi: il servizio web (il servizio personalizzato) e il servizio di redis (servizio di cache comuni). Ogni servizio verrà distribuito come un contenitore, pertanto è necessario usare un'immagine Docker concreta per ogni. Per questo servizio web specifico, l'immagine sarà necessario eseguire le operazioni seguenti:

-   Compilazione del dockerfile nella directory corrente

-   Inoltrare la porta 80 del contenitore su porta 81 del computer host esposta

-   Montare la directory del progetto nell'host a /code. all'interno del contenitore, rendendo possibile la modifica del codice senza dover ricreare l'immagine

-   Collegare il servizio web al servizio di redis

Il servizio di redis Usa il [immagine di redis pubblica più recente](https://hub.docker.com/_/redis/) effettuato il pull dal Registro di sistema dell'Hub Docker. [redis](https://redis.io/) è un sistema cache molto diffuso per applicazioni sul lato server.

### <a name="step-5-build-and-run-your-docker-app"></a>Passaggio 5: Compilare ed eseguire l'app di Docker

Se l'applicazione ha solo un singolo contenitore, è sufficiente eseguire distribuendola all'host Docker (macchina virtuale o server fisico). Tuttavia, se l'app è costituito da più servizi, è necessario *comporlo*anche. Esaminare le diverse opzioni.

***Opzione r: eseguire un singolo contenitore o un servizio***

È possibile eseguire l'immagine di Docker usando il comando docker run, come illustrato di seguito:

```
docker run -t -d -p 80:5000
cesardl/netcore-webapi-microservice-docker:first
```

Si noti che per questo tipo di distribuzione, si verranno essere reindirizzamento delle richieste inviate alla porta 80 per la porta interna 5000. A questo punto, l'applicazione è in ascolto sulla porta 80 a livello di host esterna.

***Opzione b: comporre ed eseguire un'applicazione contenitore multiplo***

Nella maggior parte degli scenari aziendali, un'applicazione di Docker verrà essere composti da più servizi. In questi casi, è possibile eseguire il comando comporre docker backup (figura 4-21), che verrà usato il file docker compose.yml potrebbe essere creato in precedenza. Eseguendo questo comando consente di distribuire un'applicazione composta con tutti i relativi contenitori correlati.

![](./media/image27.png)

Figura 4-21 che generava: risultati dell'esecuzione del comando "docker-comporre backup"

Dopo aver eseguito docker-comporre backup, la distribuzione dell'applicazione e il failover dei contenitori correlati all'Host Docker, come illustrato nella figura 4-22, nella rappresentazione di macchina virtuale.

![](./media/image28.png)

Figura 4-22: macchina virtuale con i contenitori di Docker distribuito

Nota docker-comporre backup e docker eseguire potrebbero essere sufficienti per il test ai contenitori nell'ambiente di sviluppo, ma si potrebbero non usarle se si prevede di gestire i cluster di Docker e orchestrators Docker Swarm Mesosphere DC/OS o Kubernetes Per poter essere in grado di applicare la scalabilità verticale. Se si usa un cluster, ad esempio [Docker Swarm modalità](https://docs.docker.com/engine/swarm/) (disponibile in Docker per Windows e Mac dalla versione 1.12), è necessario distribuire e testare con altri comandi, ad esempio servizio docker di creare servizi single o quando si è distribuzione di un'applicazione composta da diversi contenitori, usando docker comporre bundle e docker distribuire myBundleFile, distribuendo l'app composto come uno stack, come illustrato nell'articolo [bundle dell'applicazione distribuita](https://blog.docker.com/2016/06/docker-app-bundle/) da Docker.

Per [DC/OS](https://mesosphere.com/blog/2015/09/02/dcos-cli-command-line-tool-datacenter/) e [Kubernetes](http://kubernetes.io/docs/user-guide/deployments/#creating-a-deployment) si usano i comandi di distribuzione diversi e gli script, nonché.

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Passaggio 6: Testare l'applicazione di Docker (in locale, nella macchina virtuale locale CD)

Questo passaggio varia a seconda di ciò che esegue l'app.

In un molto .NET Core API Web semplice "Hello World" distribuito come un singolo contenitore o un servizio, è sufficiente accedere al servizio, fornendo la porta TCP specificata nel DockerFile.

Se localhost non è attivato, per passare al servizio, individuare l'indirizzo IP per la macchina con il seguente comando:

docker Virtual ip *nome contenitore*

Nell'host Docker, aprire un browser e passare a tale sito; verrà visualizzata l'app/servizio in esecuzione, come illustrato nella figura 4-23.

![](./media/image29.png)

Figura 4-23: il test dell'applicazione di Docker in locale utilizzando localhost

Si noti che utilizza la porta 80, ma internamente è stata viene reindirizzata alla porta 5000, ovvero come è stata distribuita con docker run, come spiegato in precedenza.

È possibile testare questo utilizzando CURL dal terminale. In un'installazione di Docker in Windows, l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4 e 24.

![](./media/image30.png)

Figura 4-24: test di un'applicazione di Docker in locale usando CURL

**Debug di un contenitore in esecuzione in Docker**

Codice di Visual Studio supporta Docker debug se si utilizza Node. js e altre piattaforme, ad esempio i contenitori di .NET Core.

È anche possibile eseguire il debug dei contenitori di .NET Core in Docker quando si utilizza Visual Studio, come descritto nella sezione successiva.

**Altre informazioni:** per altre informazioni sul debug contenitori Docker Node. js, passare alla <https://blog.docker.com/2016/07/live-debugging-docker/> e [ https://blogs.msdn.microsoft.com/\ utente\_ed/2016/02/27 / Visual-Studio-code-New-Features-13-big-Debugging-Updates-Rich-Object-Hover-Conditional-Breakpoints-Node-js-mono-more/](https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/).


>[!div class="step-by-step"]
[Precedente](docker-apps-development-environment.md)
[Successivo](visual-studio-tools-for-docker.md)
