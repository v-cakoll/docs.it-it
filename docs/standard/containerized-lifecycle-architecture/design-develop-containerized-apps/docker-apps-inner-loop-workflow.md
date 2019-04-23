---
title: Flusso di lavoro di sviluppo del ciclo interno per le app Docker
description: Descrive il flusso di lavoro "ciclo interno" per lo sviluppo di applicazioni Docker.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 36fcf5769376375854c2a2631e26e8b136df0de6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58920909"
---
# <a name="inner-loop-development-workflow-for-docker-apps"></a>Flusso di lavoro di sviluppo del ciclo interno per le app Docker

Prima di attivare il flusso di lavoro ciclo esterno che si estende l'intera DevOps del ciclo, tutto ha inizio in ogni computer dello sviluppatore, scrittura di codice dell'app stessa, usando i propri linguaggi Preferiti o piattaforme e testarla in locale (figura 4-21). Ma in ogni caso, sarà necessario un punto importante in comune, indipendentemente da quale linguaggio, framework o piattaforme scelto. In questo flusso di lavoro specifico, vengono sempre lo sviluppo, test sui contenitori di Docker, ma in locale.

![Passaggio 1: codice/esecuzione/Debug](./media/image18.png)

**Figura 4-21**. Contesto di sviluppo a ciclo interno

Il contenitore o l'istanza di un'immagine Docker conterrà questi componenti:

-   Una selezione del sistema operativo (ad esempio, una distribuzione Linux o Windows)

- File aggiunti dallo sviluppatore (ad esempio, file binari dell'app)

-   Configurazione (ad esempio, le impostazioni di ambiente e le dipendenze)

- Istruzioni per i processi eseguiti da Docker

È possibile impostare il flusso di lavoro di sviluppo a ciclo interno che prevede l'utilizzo di Docker come il processo (descritto nella sezione successiva). È consigliabile che i passaggi iniziali per configurare l'ambiente non sono inclusi, perché è sufficiente eseguire una volta.

## <a name="building-a-single-app-within-a-docker-container-using-visual-studio-code-and-docker-cli"></a>Creazione di una singola app all'interno di un contenitore Docker usando Visual Studio Code e CLI di Docker

Le app sono composti da servizi e librerie aggiuntive (dipendenze).

Figura 4-22 illustra i passaggi di base che è in genere necessario eseguire durante la creazione di un'app Docker, seguita da una descrizione dettagliata di ogni passaggio.

![Panoramica del flusso di lavoro: Passaggio 1: codice, passaggio 2: scrittura di Dockerfile, passaggio 3: creare immagini definite con i Dockerfile, passaggio 4: definire i servizi con file docker-Compose, passaggio 5: eseguire contenitori o App composte, passaggio 6 - Test App, passaggio 7: eseguire il Push per iniziare il ciclo esterno (pipeline CI/CD) oppure continuare de veloping.](./media/image19.png)

**Figura 4-22**. Flusso di lavoro generale per il ciclo di vita per applicazioni Docker in contenitori usando l'interfaccia CLI di Docker

### <a name="step-1-start-coding-in-visual-studio-code-and-create-your-initial-appservice-baseline"></a>Passaggio 1: Iniziare a scrivere codice in Visual Studio Code e creare la linea di base di app/servizio iniziale

Il modo in cui si sviluppa l'applicazione è simile al modo in che cui avviene senza Docker. La differenza è che durante lo sviluppo, si ha la distribuzione e test di applicazioni o servizi in esecuzione all'interno di contenitori Docker inseriti nell'ambiente locale (ad esempio, una VM Linux o Windows).

**Configurazione dell'ambiente locale**

Con le versioni più recenti di Docker per Mac e Windows, è più facile che mai per lo sviluppo di applicazioni di Docker, e il programma di installazione è semplice.

> [! INFORMAZIONI]
>
> Per istruzioni sulla configurazione di Docker per Windows, passare a <https://docs.docker.com/docker-for-windows/>.
>
>Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.

Inoltre, è necessario un editor di codice in modo che è effettivamente possibile sviluppare l'applicazione quando si usa l'interfaccia CLI di Docker.

Microsoft fornisce Visual Studio Code, ovvero un editor di codice leggero che è supportato in Mac, Windows e Linux e offre il supporto IntelliSense con [supporto per molti linguaggi](https://code.visualstudio.com/docs/languages/overview) (JavaScript, .NET, Go, Java, Ruby, Python e la maggior parte moderni linguaggi), [debugging](https://code.visualstudio.com/Docs/editor/debugging), [integrazione con Git](https://code.visualstudio.com/Docs/editor/versioncontrol) e [supporto delle estensioni](https://code.visualstudio.com/docs/extensions/overview). Questo editor è un candidato ideale per sviluppatori Mac e Linux. In Windows, è anche possibile usare l'applicazione completa di Visual Studio.

> [! INFORMAZIONI]
>
> Per istruzioni sull'installazione di Visual Studio Code per Windows, Mac o Linux, vedere <https://code.visualstudio.com/docs/setup/setup-overview/>.
>
> Per istruzioni sulla configurazione di Docker per Mac, passare a <https://docs.docker.com/docker-for-mac/>.

È possibile lavorare con CLI di Docker e scrivere il codice usando qualsiasi editor di codice, ma con Visual Studio Code con l'estensione Docker semplifica all'autore `Dockerfile` e `docker-compose.yml` file nell'area di lavoro. È anche possibile eseguire le attività e gli script dall'IDE di Visual Studio Code per eseguire i comandi di Docker tramite la CLI di Docker di sotto.

L'estensione Docker per Visual Studio Code offre le funzionalità seguenti:

- Automatic `Dockerfile` e `docker-compose.yml` generazione di file

- Suggerimenti per la sintassi di evidenziazione e passare il mouse per `docker-compose.yml` e `Dockerfile` file

- IntelliSense (completamento) per `Dockerfile` e `docker-compose.yml` file

- Il Lint (errori e avvisi) per `Dockerfile` file

- Comando dell'integrazione tavolozza (F1) per i comandi di Docker più comuni

- Integrazione di soluzioni per la gestione delle immagini e contenitori

- Distribuire le immagini da DockerHub e registri contenitori di Azure del servizio App di Azure

Per installare l'estensione Docker, premere Ctrl + MAIUSC + P, digitare `ext install`, quindi eseguire il comando per l'estensione installa per visualizzare l'elenco di estensioni di Marketplace. Successivamente, digitare **docker** per filtrare i risultati e quindi selezionare l'estensione del supporto per Docker, come illustrato nella figura 4-23.

![Visualizzazione dell'estensione Docker per Visual Studio Code.](./media/image20.png)

**Figura 4-23**. Installazione dell'estensione Docker in Visual Studio Code

### <a name="step-2-create-a-dockerfile-related-to-an-existing-image-plain-os-or-dev-environments-like-net-core-nodejs-and-ruby"></a>Passaggio 2: Creare un DockerFile correlato a un'immagine esistente (normale del sistema operativo o ambienti di sviluppo, come Ruby, Node. js e .NET Core)

È necessario un `DockerFile` per ogni immagine personalizzata da compilare e ogni contenitore da distribuire. Se l'app è costituita da un solo servizio personalizzato, è necessario un singolo `DockerFile`. Ma se l'app è costituita da più servizi (ad esempio un'architettura di microservizi), è necessario uno `Dockerfile` per ogni servizio.

Il `DockerFile` comunemente viene inserito nella cartella radice dell'app o del servizio e contiene i comandi necessari in modo che Docker sa come configurare ed eseguire tale applicazione o servizio. È possibile creare il `DockerFile` e aggiungerlo al progetto insieme al codice (Node. js, .NET Core, e così via), o, se si ha familiarità con l'ambiente, esaminiamo il suggerimento seguente.

> [!TIP]
>
> È possibile usare l'estensione Docker per ottenere istruzioni utili quando si usa la `Dockerfile` e `docker-compose.yml` file correlati per i contenitori Docker. Alla fine, è probabilmente necessario scrivere questi tipi di file senza questo strumento, ma tramite l'estensione Docker è un buon punto di partenza che consente di accelerare la curva di apprendimento.

Nella figura 4-24, è possibile visualizzare come un comando docker-compose file viene aggiunto tramite l'estensione Docker per Visual Studio Code.

![Visualizzazione della console dell'estensione Docker per Visual Studio Code.](./media/image24.png)

**Figura 4-24**. File docker aggiunti usando il **file Docker aggiungere al comando dell'area di lavoro**

Quando si aggiunge un DockerFile, è specificare quale immagine Docker di base che verranno utilizzati (come l'uso di `FROM mcr.microsoft.com/dotnet/core/aspnet`). In genere si creerà un'immagine personalizzata all'inizio di un'immagine di base che si ottiene da qualsiasi repository ufficiale nel [registro Docker Hub](https://hub.docker.com/) (ad esempio un [immagine per .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/) o quello [per Node. js](https://hub.docker.com/_/node/)).

***Usare un'immagine Docker ufficiale esistente***

Uso di un repository ufficiale di uno stack di linguaggio con un numero di versione garantisce che le stesse funzionalità del linguaggio sono disponibili in tutti i computer (tra cui sviluppo, test e produzione).

Di seguito è riportato un esempio di DockerFile per un contenitore di .NET Core:

```Dockerfile
# Base Docker image to use  
FROM mcr.microsoft.com/dotnet/core/aspnet:2.1
  
# Set the Working Directory and files to be copied to the image  
ARG source  
WORKDIR /app  
COPY ${source:-bin/Release/PublishOutput} .  
  
# Configure the listening port to 80 (Internal/Secured port within Docker host)  
EXPOSE 80  
  
# Application entry point  
ENTRYPOINT ["dotnet", "MyCustomMicroservice.dll"]
```

In questo caso, l'immagine si basa sulla versione 2.1 dell'immagine ASP.NET Core Docker ufficiale (multi-arch per Linux e Windows), in base alla riga `FROM mcr.microsoft.com/dotnet/core/aspnet:2.1`. (Per altre informazioni su questo argomento, vedere la [ASP.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) pagina e il [.NET Core Docker Image](https://hub.docker.com/_/microsoft-dotnet-core/) pagina).

Nel DockerFile, è possibile indicare anche Docker per l'ascolto della porta TCP che verrà usato in fase di esecuzione (ad esempio la porta 80).

Nel Dockerfile è possibile specificare altre impostazioni di configurazione in base al linguaggio e al framework in uso. Ad esempio, il `ENTRYPOINT` linea con `["dotnet", "MySingleContainerWebApp.dll"]` indica a Docker per eseguire un'applicazione .NET Core. Se si usa il SDK e .NET Core CLI (`dotnet CLI`) per compilare ed eseguire l'applicazione .NET, questa impostazione sarà diversa. L'aspetto essenziale qui è che la riga ENTRYPOINT e altre impostazioni dipendono dal linguaggio e piattaforma che scelta per l'applicazione.

> [! INFORMAZIONI]
>
> Per altre informazioni sulla creazione di immagini Docker per applicazioni .NET Core, passare a <https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images>.
>
> Per altre informazioni sulla creazione di immagini personalizzate, passare a <https://docs.docker.com/engine/tutorials/dockerimages/>.

**Usare i repository di immagini multi-arch**

Il nome di un'immagine singola in un repository può contenere varianti di piattaforme, ad esempio un'immagine Linux e un'immagine di Windows. Questa funzionalità consente a fornitori come Microsoft (creatori di immagini di base) creare un unico repository per più piattaforme (vale a dire, Linux e Windows). Ad esempio, il [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) repository disponibili nel Registro di sistema dell'Hub Docker fornisce il supporto per Linux e Windows Nano Server usando lo stesso nome di immagine.

Eseguire il pull il [dotnet/core/aspnet](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) pull di immagini da un host Windows la variante di Windows, mentre il pull lo stesso nome di immagine da un host Linux estrae la variante Linux.

***Creare l'immagine di base da zero***

È possibile creare la propria immagine di base di Docker da zero, come illustrato in questo [articolo](https://docs.docker.com/engine/userguide/eng-image/baseimages/) da Docker. Questo scenario è probabile che non la migliore se stai iniziando con Docker, ma se si desidera impostare i bit specifici della propria immagine di base, è possibile farlo.

### <a name="step-3-create-your-custom-docker-images-embedding-your-service-in-it"></a>Passaggio 3: Creare le immagini Docker personalizzate in essa l'incorporamento del servizio

Per ogni servizio personalizzata che comprende l'app, è necessario creare un'immagine correlata. Se l'app è costituito da un singolo servizio o un'app web, è necessario avere una sola immagine.

> [!NOTE]
>
> Quando prendendo in considerazione il "ciclo esterno flusso di lavoro DevOps", verranno create le immagini da un processo di compilazione automatica ogni volta che eseguire il push del codice sorgente in un repository Git (Continuous Integration), in modo che le immagini verranno create in quell'ambiente globale dal codice sorgente.
>
> Ma prima che passa a tale route ciclo esterno, è necessario verificare che l'applicazione Docker in realtà funziona correttamente in modo che non sono push del codice che potrebbe non funzionare correttamente per il sistema di controllo sorgente (Git e così via).
>
> Pertanto, ogni sviluppatore deve prima eseguire l'intero processo di ciclo interno per testare in locale e continuare a sviluppare fino a quando non desiderano eseguire il push di una funzionalità completa o modificare il sistema di controllo sorgente.

Per creare un'immagine nell'ambiente locale e Usa il DockerFile, è possibile usare il comando docker build, come illustrato nella figura 4-25 (è anche possibile eseguire `docker-compose up --build` per applicazioni composte da diversi contenitori/servizi).

![Output della console per la compilazione di docker-Compose, che mostra le immagini di avanzamento del download.](./media/image25.png)

**Figura 4-25**. Compilazione di docker in esecuzione

Facoltativamente, anziché eseguire direttamente `docker build` dalla cartella del progetto, è innanzitutto possibile generare una cartella distribuibile con le librerie di .NET necessarie tramite l'esecuzione `dotnet publish` comandi e quindi eseguire `docker build`.

In questo esempio crea un'immagine Docker con il nome `cesardl/netcore-webapi-microservice-docker:first` (`:first` è un tag, ad esempio una versione specifica). È possibile eseguire questo passaggio per ogni immagine personalizzata che è necessario creare per l'applicazione Docker composta con diversi contenitori.

È possibile trovare le immagini esistenti nel repository locale (computer di sviluppo) usando docker immagini comando, come illustrato nella figura 4-26.

![Output della console da immagini docker di comando, che mostra le immagini esistenti.](./media/image26.png)

**Figura 4-26**. Visualizzazione immagini esistente con le immagini docker

### <a name="step-4-define-your-services-in-docker-composeyml-when-building-a-composed-docker-app-with-multiple-services"></a>Passaggio 4: Definire i servizi in docker-Compose. yml quando si compila un'applicazione Docker composta con più servizi

Con la `docker-compose.yml` file, è possibile definire un set di servizi correlati da distribuire come applicazione composta con i comandi di distribuzione illustrati nella sezione Passaggio successiva.

Creare file in principale o la cartella soluzione radice; deve essere contenuto simile a quello illustrato in questo `docker-compose.yml` file:

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

In questo caso particolare, questo file definisce due servizi: il servizio web (il servizio personalizzato) e il servizio redis (un servizio popolare cache). Ogni servizio verrà distribuito come un contenitore, pertanto è necessario usare un'immagine Docker concreta per ognuno. Per questo servizio web specifico, l'immagine dovrà eseguire le operazioni seguenti:

- Compilazione del dockerfile nella directory corrente

- Inoltrare la porta 80 esposta sul contenitore alla porta 81 nel computer host

- Montare la directory del progetto nell'host in cui /code all'interno del contenitore, rendendo possibile la modifica del codice senza dover ricompilare l'immagine

- Collegare il servizio web al servizio redis

Il servizio redis Usa il [immagine redis pubblica più recente](https://hub.docker.com/_/redis/) estratto dal registro Docker Hub. [redis](https://redis.io/) è un sistema di cache più diffusi per le applicazioni lato server.

### <a name="step-5-build-and-run-your-docker-app"></a>Passaggio 5: Compilare ed eseguire l'app Docker

Se l'app ha solo un singolo contenitore, è sufficiente eseguirla distribuendola all'host Docker (macchina virtuale o server fisico). Tuttavia, se l'app è costituita da più servizi, devi *comporlo*anche. Esaminiamo le diverse opzioni.

***Opzione a: Eseguire un singolo contenitore o un servizio***

È possibile eseguire l'immagine Docker usando il comando docker run, come illustrato di seguito:

```console
docker run -t -d -p 80:5000 cesardl/netcore-webapi-microservice-docker:first
```

Per questa distribuzione specifica, si saranno reindirizzando le richieste inviate alla porta 80 alla porta interna 5000. A questo punto l'applicazione è in ascolto sulla porta esterna 80 a livello di host.

***Opzione b: Creare ed eseguire un'applicazione di più contenitori***

Nella maggior parte degli scenari aziendali, un'applicazione Docker sarà essere composte da più servizi. In questi casi, è possibile eseguire il `docker-compose up` comando (figura 4-27), che userà il file docker-Compose. yml che è stato creato in precedenza. Questo comando consente di distribuire un'applicazione composta con tutti i contenitori correlati.

![Output di console il comando docker-compose up comando.](./media/image27.png)

**Figura 4-27**. Risultati dell'esecuzione del comando "docker-compose up"

Dopo aver eseguito `docker-compose up`, si distribuisce l'applicazione e i relativi contenitori correlati nell'Host Docker, come illustrato nella figura 4-28, nella rappresentazione di VM.

![La macchina virtuale in esecuzione applicazioni multicontenitore.](./media/image28.png)

**Figura 4-28**. VM con contenitori Docker distribuiti

### <a name="step-6-test-your-docker-application-locally-in-your-local-cd-vm"></a>Passaggio 6: Testare l'applicazione Docker (in locale, nella macchina virtuale locale CD)

Questo passaggio varia a seconda di ciò che esegue l'app.

In un semplice API .NET Core Web "Hello World" distribuito come un singolo contenitore o un servizio, è sufficiente accedere al servizio, fornendo la porta TCP specificata nel DockerFile.

Se localhost non è attivata, per passare al servizio, trovare l'indirizzo IP per la macchina tramite questo comando:

```console
docker-machine {IP} {YOUR-CONTAINER-NAME}
```

Nell'host Docker, aprire un browser e passare a tale sito. il servizio app/in esecuzione, verrà visualizzato come illustrato nella figura 4-29.

![Visualizzazione di esplorazione della risposta da localhost/API/values.](./media/image29.png)

**Figura 4-29**. Test dell'applicazione Docker in locale mediante localhost

Si noti che utilizza la porta 80, ma internamente viene reindirizzata alla porta 5000 perché si tratta di come è stato distribuito con `docker run`, come illustrato in precedenza.

È possibile verificarlo usando CURL dal terminale. In un'installazione di Docker in Windows, l'indirizzo IP predefinito è 10.0.75.1, come illustrato nella figura 4-30.

![Output dall'introduzione della console di http://10.0.75.1/API/values con curl](./media/image30.png)

**Figura 4-30**. Test di un'applicazione Docker in locale mediante CURL

**Debug di un contenitore in esecuzione in Docker**

Visual Studio Code supporta debug Docker se si usa Node. js e altre piattaforme quali contenitori .NET Core.

È anche possibile eseguire il debug dei contenitori di .NET Framework o .NET Core in Docker quando si usa Visual Studio per Windows o Mac, come descritto nella sezione successiva.

> [! INFORMAZIONI]
>
> Per altre informazioni sul debug di contenitori Docker di Node. js, passare a <https://blog.docker.com/2016/07/live-debugging-docker/> e <https://blogs.msdn.microsoft.com/user_ed/2016/02/27/visual-studio-code-new-features-13-big-debugging-updates-rich-object-hover-conditional-breakpoints-node-js-mono-more/>.

>[!div class="step-by-step"]
>[Precedente](docker-apps-development-environment.md)
>[Successivo](visual-studio-tools-for-docker.md)
