---
title: Distribuzione di applicazioni Web .NET Core basate su singolo contenitore in host di Linux o Windows Nano Server
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Distribuzione di applicazioni Web .NET Core basate su singolo contenitore in host di Linux o Windows Nano Server
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/27/2018
ms.openlocfilehash: 45be99a86a52ed450b795ca5f91c01ab82c7da47
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43778003"
---
# <a name="deploying-single-container-based-net-core-web-applications-on-linux-or-windows-nano-server-hosts"></a>Distribuzione di applicazioni Web .NET Core basate su singolo contenitore in host di Linux o Windows Nano Server

_È possibile usare i contenitori Docker per la distribuzione monolitica delle applicazioni Web più semplici. Ciò migliora le pipeline di integrazione continua e distribuzione continua e consente di ottenere risultati ottimali dalla distribuzione alla produzione, evitando situazioni in cui quello che funziona in un singolo computer non funziona più nell'ambiente di produzione._

Un'architettura basata su microservizi offre numerosi vantaggi, ma al costo di una maggiore complessità. In alcuni casi i costi superano i vantaggi e un'applicazione con distribuzione monolitica in esecuzione in un unico contenitore o in pochi contenitori rappresenta un'opzione migliore.

Un'applicazione monolitica potrebbe non essere facilmente scomponibile in microservizi ben distinti. Si è appreso che questi microservizi devono essere partizionati in base alla funzione e dovrebbero funzionare indipendentemente uno dall'altro per garantire un'applicazione più resiliente. Se non è possibile fornire sezioni di funzionalità per l'applicazione, una separazione aggiunge solo complessità.

Per un'applicazione potrebbe non essere necessaria la scalabilità delle funzionalità in modo indipendente. Si supponga che nelle prime fasi del ciclo di vita dell'applicazione di riferimento `eShopOnContainers` il traffico non abbia giustificato la separazione delle funzionalità in microservizi diversi. Il traffico è sufficientemente ridotto cosicché aggiungere risorse a un servizio significa aggiungere risorse a tutti i servizi. Il lavoro aggiuntivo richiesto per separare l'applicazione in servizi distinti implica un vantaggio minimo.

Inoltre, nelle prime fasi di sviluppo di un'applicazione i limiti funzionali naturali potrebbero non essere ancora chiari. Durante lo sviluppo di un prodotto valido minimo, la separazione naturale potrebbe non essere ancora emersa.

Alcune di queste condizioni potrebbero essere temporanee. Si potrebbe iniziare creando un'applicazione monolitica e successivamente separare alcune funzionalità da sviluppare e distribuire come microservizi. Altre condizioni potrebbero essere essenziali per i problemi dell'applicazione, vale a dire che l'applicazione potrebbe non essere mai suddivisa in più microservizi.

La separazione di un'applicazione in più processi distinti presenta anche il problema del sovraccarico. La separazione delle funzionalità in processi diversi aumenta la complessità. I protocolli di comunicazione diventano più complessi. Invece delle chiamate ai metodi, è necessario usare comunicazioni asincrone tra i servizi. Quando si passa a un'architettura di microservizi, è necessario aggiungere molti dei blocchi predefiniti implementati nella versione dei microservizi dell'applicazione `eShopOnContainers`: gestione del bus di eventi, resilienza dei messaggi e nuovi tentativi, coerenza futura e altro ancora.

Una versione molto semplificata di eShopOnContainers (denominata [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) e inclusa nello stesso repository GitHub) viene eseguita come applicazione MVC monolitica. Come descritto, questa scelta di progettazione offre alcuni vantaggi. È possibile scaricare l'origine per questa applicazione da GitHub ed eseguirla in locale. Anche questa applicazione monolitica trae vantaggio dalla distribuzione in un ambiente basato su contenitori.

Da una parte, la distribuzione in contenitori significa che ogni istanza dell'applicazione è eseguita nello stesso ambiente. Ciò include l'ambiente di sviluppo in cui hanno luogo le fasi di test preliminare e di sviluppo. Il team di sviluppo può eseguire l'applicazione in un ambiente basato su contenitori corrispondente all'ambiente di produzione.

Inoltre, la scalabilità orizzontale delle applicazioni incluse in contenitori è garantita a costi inferiori. Come illustrato in precedenza, un ambiente basato su contenitori consente una maggiore condivisione di risorse rispetto agli ambienti di macchine virtuali tradizionali.

Infine, l'inserimento dell'applicazione in contenitori impone una separazione tra la logica di business e il server di archiviazione. Di pari passo con la scalabilità orizzontale dell'applicazione, i vari contenitori si baseranno tutti su un singolo supporto di archiviazione fisica, che sarà in genere un server a disponibilità elevata che esegue un database di SQL Server.

## <a name="application-tour"></a>Presentazione dell'applicazione

L'applicazione [eShopWeb](https://github.com/dotnet-architecture/eShopOnContainers/tree/master/src/Web/WebMonolithic) rappresenta una parte dell'applicazione eShopOnContainers in esecuzione come applicazione monolitica, ovvero un'applicazione ASP.NET Core MVC in esecuzione in .NET Core. Fornisce principalmente le funzionalità di esplorazione del catalogo descritte nelle sezioni precedenti.

L'applicazione usa un database di SQL Server per l'archiviazione del catalogo. Nelle distribuzioni basate su contenitori questa applicazione monolitica può accedere allo stesso archivio dati dell'applicazione basata su microservizi. L'applicazione è configurata per l'esecuzione di SQL Server in un contenitore insieme all'applicazione monolitica. In un ambiente di produzione SQL Server sarebbe eseguito in un computer a disponibilità elevata, all'esterno dell'host Docker. Per praticità, in un ambiente di sviluppo o di test è consigliabile eseguire SQL Server nel relativo contenitore.

Il set di funzionalità iniziale consente solo l'esplorazione del catalogo. Gli aggiornamenti garantiscono il set di funzionalità completo dell'applicazione inserita nel contenitore. Un'architettura di applicazioni Web monolitiche più avanzata è descritta nell'e-book [ASP.NET Web Application architecture practices](https://aka.ms/webappebook) (Pratiche relative all'architettura dell'applicazione Web ASP.NET) e nella pagina dell'[applicazione di esempio eShopOnWeb](https://aka.ms/WebAppArchitecture) correlata.

## <a name="docker-support"></a>Supporto per Docker

Il progetto eShopOnWeb viene eseguito in .NET Core. Può essere eseguito sia in contenitori basati su Linux che in contenitori basati su Windows. Si noti che per la distribuzione di Docker viene usato lo stesso tipo di host per SQL Server. I contenitori basati su Linux consentono un footprint minore e sono preferibili.

Visual Studio offre un modello di progetto che aggiunge il supporto per Docker a una soluzione. Fare clic con il pulsante destro del mouse sul progetto, fare clic su **Aggiungi** e quindi su **Supporto Docker**. Il modello aggiunge un file Docker al progetto e un nuovo progetto **docker-compose** che fornisce un file *docker-compose.yml* di avvio. Questo passaggio è già stato eseguito nel progetto eShopOnWeb scaricato da GitHub. Si noterà che la soluzione contiene il progetto **eShopOnWeb** e il progetto **docker-compose**, come mostrato nella figura 6-1.

![](./media/image1.png)

**Figura 6-1**. Progetto **docker-compose** in un'applicazione Web a un solo contenitore

Questi file sono file docker-compose standard, coerenti con qualsiasi progetto Docker. Possono essere usati con Visual Studio o dalla riga di comando. Questa applicazione viene eseguita in .NET Core e usa contenitori Linux. Pertanto, è anche possibile codificarla, compilarla ed eseguirla in un computer Mac o Linux.

Il file *docker-compose.yml* contiene informazioni sulle immagini da compilare e i contenitori da avviare. I modelli specificano come compilare l'immagine `eshopweb` e avviare i contenitori dell'applicazione. È necessario aggiungere la dipendenza da SQL Server includendo la relativa immagine (ad esempio `mssql-server-linux`) e un servizio per l'immagine sql.data per Docker per compilare e avviare tale contenitore. Queste impostazioni sono mostrate nell'esempio seguente:

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web
    build:
    context: ./eShopWeb
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  sql.data:
    image: microsoft/mssql-server-linux
```

La direttiva `depends_on` indica a Docker che l'immagine eShopWeb dipende dall'immagine sql.data. Le righe al di sotto di `depends_on` sono le istruzioni per compilare un'immagine con tag `sql.data` usando l'immagine `microsoft/mssql-server-linux`.

Il progetto **docker-compose** visualizza gli altri file docker-compose sotto il nodo *docker-compose.yml* principale per fornire un'indicazione visiva che questi file sono correlati. Il file *docker-compose-override.yml* contiene le impostazioni per entrambi i servizi, come le stringhe di connessione e altre impostazioni dell'applicazione.

L'esempio seguente mostra il file *docker-compose.vs.debug.yml*, che contiene le impostazioni usate per il debug in Visual Studio. In tale file all'immagine eshopweb è accodato il tag dev. Ciò consente di separare le immagini di debug da quelle della versione, in modo che le informazioni di debug non vengano distribuite accidentalmente in un ambiente di produzione:

```yml
version: '2'

services:
  eshopweb:
    image: eshop/web:dev
    build:
    args:
    source: ${DOCKER_BUILD_SOURCE}
    environment:
      - DOTNET_USE_POLLING_FILE_WATCHER=1
    volumes:
      - ./eShopWeb:/app
      - ~/.nuget/packages:/root/.nuget/packages:ro
      - ~/clrdbg:/clrdbg:ro
    entrypoint: tail -f /dev/null
    labels:
      - "com.microsoft.visualstudio.targetoperatingsystem=linux"
```

L'ultimo file aggiunto è *docker-compose.ci.build.yml*, che potrebbe essere usato dalla riga di comando per compilare il progetto da un server CI. Questo file compose avvia un contenitore Docker che compila le immagini necessarie per l'applicazione. L'esempio seguente mostra il contenuto del file *docker-compose.ci.build.yml*:

```yml
version: '2'

services:
  ci-build:
    image: microsoft/aspnetcore-build:latest
    volumes:
      - .:/src
    working_dir: /src
  command: /bin/bash -c "dotnet restore ./eShopWeb.sln && dotnet publish  ./eShopWeb.sln -c Release -o ./obj/Docker/publish"
```

> [!NOTE]
> A partire da .NET Core SDK 2.0, il comando [dotnet restore](../../../core/tools/dotnet-restore.md) viene eseguito automaticamente quando si esegue [dotnet publish](../../../core/tools/dotnet-publish.md).

Si noti che l'immagine è un'immagine di compilazione ASP.NET Core. L'immagine include gli strumenti SDK e per la compilazione per compilare l'applicazione e creare le immagini necessarie. L'esecuzione del progetto **docker-compose** tramite questo file avvia il contenitore della build dall'immagine, quindi compila l'immagine dell'applicazione in tale contenitore. È necessario specificare tale file *docker-compose* come parte della riga di comando per compilare l'applicazione in un contenitore Docker, quindi avviarla.

In Visual Studio è possibile eseguire l'applicazione in contenitori Docker selezionando il progetto **docker-compose** come progetto di avvio e quindi premendo CTRL+F5 (F5 per eseguire il debug), come con qualsiasi altra applicazione. Quando si avvia il progetto **docker-compose**, Visual Studio esegue **docker-compose** usando il file *docker-compose.yml*, il file *docker-compose.override.yml* e uno dei file docker-compose.vs\*. Dopo che l'applicazione è stata avviata, il browser si avvia automaticamente in Visual Studio.

Se si avvia l'applicazione nel debugger, Visual Studio si collega all'applicazione in esecuzione in Docker.

## <a name="troubleshooting"></a>Risoluzione dei problemi

Questa sezione descrive alcuni problemi che potrebbero verificarsi durante l'esecuzione dei contenitori in locale e presenta alcune correzioni.

### <a name="stop-docker-containers"></a>Arresto di contenitori Docker

Dopo avere avviato l'applicazione inclusa nei contenitori, i contenitori continuano a essere eseguiti, anche dopo che è stato interrotto il debug. È possibile eseguire il comando `docker ps` dalla riga di comando per visualizzare i contenitori in esecuzione. Il comando `docker stop` arresta un contenitore in esecuzione, come illustrato nella figura 6-2.

![](./media/image2.png)

**Figura 6-2**. Elenco e arresto di contenitori con i comandi dell'interfaccia della riga di comando docker ps e docker stop

Potrebbe essere necessario arrestare i processi in esecuzione quando si passa da una configurazione all'altra. In caso contrario, il contenitore che esegue l'applicazione Web usa la porta per l'applicazione (5106 in questo esempio).

### <a name="add-docker-to-your-projects"></a>Aggiunta di Docker ai progetti

La procedura guidata che aggiunge il supporto per Docker comunica con il processo Docker in esecuzione. La procedura guidata non verrà eseguita correttamente se Docker non è in esecuzione quando si avvia la procedura guidata. La procedura guidata esamina la scelta del contenitore corrente per aggiungere il supporto per Docker corretto. Per aggiungere il supporto per i contenitori Windows, eseguire la procedura guidata mentre Docker è in esecuzione con i contenitori Windows configurati. Per aggiungere il supporto per i contenitori Linux, eseguire la procedura guidata mentre Docker è in esecuzione con i contenitori Linux configurati.

>[!div class="step-by-step"]
[Precedente](../docker-application-development-process/docker-app-development-workflow.md)
[Successivo](../containerize-net-framework-applications/index.md)
