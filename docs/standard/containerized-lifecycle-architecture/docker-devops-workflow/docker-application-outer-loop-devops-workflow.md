---
title: Passaggi nel flusso di lavoro DevOps ciclo esterno per un'applicazione di Docker
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: b88eb5637bf266ab2e0a6d255f2e83f6aadc8af2
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106162"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Passaggi nel flusso di lavoro DevOps ciclo esterno per un'applicazione di Docker

Figura 5-1 presenta un'immagine di end-to-end dei passaggi che costituiscono il flusso di lavoro ciclo esterno DevOps.

![](./media/image1.png)

Figura 5-1: DevOps ciclo esterno flusso di lavoro per le applicazioni di Docker con gli strumenti di Microsoft

A questo punto, si esamineranno ognuno di questi passaggi in maggiore dettaglio.

## <a name="step-1-inner-loop-development-workflow"></a>Passaggio 1: Il lavoro di sviluppo ciclo interno

Questo passaggio è illustrato in dettaglio nel capitolo 4, ma, per ricapitolare, ecco in cui inizia il ciclo esterno, dal momento in cui uno sviluppatore inserisce codice per il sistema di gestione del controllo origine (ad esempio Git) di inizializzazione di azioni di pipeline CI.

## <a name="step-2-source-code-control-integration-and-management-with-visual-studio-team-services-and-git"></a>Passaggio 2: Integrazione di controllo del codice sorgente e la gestione con Visual Studio Team Services e Git

In questo passaggio, è necessario disporre di un sistema di controllo della versione per raccogliere una versione consolidata di tutto il codice proveniente da sviluppatori diversi del team.

Anche se può sembrare natura secondo ciclo alla maggior parte degli sviluppatori, quando si creano applicazioni di Docker in una vita di DevOps di controllo del codice sorgente (SCC) e la gestione del codice sorgente, è importante sottolineare che non è necessario inviare le immagini Docker con l'applicazione direttamente al globale Docker Registro di sistema (ad esempio del Registro di sistema contenitore di Azure o Hub Docker) dal computer dello sviluppatore. Al contrario, le immagini Docker per essere rilasciata e distribuiti in ambienti di produzione devono essere create esclusivamente sul codice sorgente che viene integrato nella compilazione globale o nella pipeline CI in base al repository di codice sorgente (ad esempio Git).

Le immagini locali create dagli sviluppatori stessi consigliabile utilizzarlo solo per gli sviluppatori durante il test nelle proprie macchine. Ecco perché è essenziale per la pipeline DevOps attivata dal codice di controllo del codice sorgente.

Visual Studio Team Services e Team Foundation Server supporta Git e Team Foundation Version Control. È possibile scegliere tra di essi e usarlo per un'esperienza di Microsoft end-to-end. Tuttavia, è anche possibile gestire il codice in un repository esterno (ad esempio GitHub, repository Git locale o Subversion) e ancora essere in grado di connettersi ad esso e ottenere il codice come punto di partenza per la pipeline CI DevOps.

## <a name="step-3-build-ci-integrate-and-test-with-visual-studio-team-services-and-docker"></a>Passaggio 3: Compilazione CI, integrare e testare con Visual Studio Team Services e Docker

CI è apparsa come standard per il testing di software moderno e recapito. La soluzione di Docker mantiene una netta separazione delle problematiche tra i team di sviluppo e le operazioni. Immutabilità delle immagini Docker garantisce una distribuzione ripetibile tra ciò che ha sviluppato, testato mediante CI ed eseguire nell'ambiente di produzione. Motore docker distribuite tra più portatili sviluppatore e dell'infrastruttura di test rende i contenitori portabile tra gli ambienti.

A questo punto, dopo aver creato un sistema di controllo della versione con il codice corretto inviato, è necessario un *servizio di compilazione* per prelevare il codice ed eseguire i test e alla build globale.

Il flusso di lavoro interno per questo passaggio (elemento di configurazione, compilazione, test) riguarda la costruzione di una pipeline CI costituito il repository di codice (Git, e così via), il server di compilazione (Visual Studio Team Services), il motore Docker e un registro di sistema di Docker.

È possibile utilizzare Visual Studio Team Services come base per la compilazione di applicazioni e l'impostazione di pipeline dell'elemento di configurazione e per la pubblicazione compilati "elementi" per un "repository di artefatti," descritta nel passaggio successivo.

Quando si usa Docker per la distribuzione, gli elementi"finale" da distribuire immagini Docker con l'applicazione o servizi incorporate all'interno di essi. Queste immagini sono push o pubblicate in un *Registro di sistema di Docker* (vale a dire un archivio privato, ad esempio quelli a cui è possibile che nel Registro di sistema contenitore di Azure o di una pubblica, ad esempio del Registro di sistema dell'Hub Docker, che viene usato comunemente per le immagini di base ufficiale).

Ecco il concetto di base: CI la pipeline verrà interrotto utilizzato da un commit a un repository di controllo del codice sorgente come Git. Il commit causerà Visual Studio Team Services eseguire un processo di compilazione all'interno di un contenitore Docker e, al completamento di tale processo, eseguire il push un'immagine Docker nel Registro di sistema di Docker, come illustrato nella figura 5-2.

![](./media/image2.png)

Figura 5-2: I passaggi coinvolti in CI

Ecco i passaggi di base degli elementi di configurazione del flusso di lavoro con Docker e Visual Studio Team Services:

1.  Lo sviluppatore inserisce un commit a un repository di controllo del codice sorgente (Git/Visual Studio Team Services, GitHub e così via).

2.  Se si usa Visual Studio Team Services o Git, CI è incorporata, che significa che è sufficiente selezionare una casella di controllo in Visual Studio Team Services. Se si usa un controllo del codice sorgente esterno (ad esempio GitHub), un *webhook* verrà avvisare Visual Studio Team Services dell'aggiornamento o eseguire il push in GitHub/Git.

3.  Visual Studio Team Services estrae il repository SCC, inclusi il DockerFile che descrivono l'immagine, nonché il codice dell'applicazione e di test.

4.  Visual Studio Team Services crea un'immagine Docker e l'etichetta con un numero di build.

5.  Visual Studio Team Services crea un'istanza del contenitore Docker all'interno dell'Host Docker sottoposto a provisioning e vengono eseguiti i test appropriati.

6.  Se i test hanno esito positivo, l'immagine viene innanzitutto cui per un nome significativo, in modo da sapere è una build"documento" (ad esempio "/ 1.0.0" o qualsiasi altra etichetta) e quindi inseriti nel Registro di sistema Docker (Hub Docker, del Registro di sistema di Azure contenitore, DTR e così via)

### <a name="implementing-the-ci-pipeline-with-visual-studio-team-services-and-the-docker-extension-for-visual-studio-team-services"></a>Implementazione della pipeline CI con Visual Studio Team Services e l'estensione Docker per Visual Studio Team Services

Il [estensione di Visual Studio Team Services Docker](https://aka.ms/vstsdockerextension) aggiunge un'attività alla pipeline dell'elemento di configurazione con cui è possibile costruire immagini Docker, push immagini Docker in un registro Docker autenticato, eseguire le immagini Docker o eseguire altre operazioni offerti dal Docker CLI. Aggiunge anche un'attività Docker Compose che è possibile utilizzare per compilare, eseguire il push ed eseguire multicontainer Docker applicazioni o eseguire altre operazioni offerti l'interfaccia CLI comporre Docker, come illustrato nella figura 5-3.

![](./media/image3.png)

Figura 5-3: la pipeline di elementi di configurazione di Docker in Visual Studio Team Services

L'estensione Docker è possibile utilizzare gli endpoint del servizio per gli host Docker e del contenitore o i registri di immagine. Il valore predefinito di attività per l'utilizzo di un host Docker locale, se disponibile (attualmente è necessario un agente di Visual Studio Team Services personalizzato); in caso contrario, è necessario fornire una connessione all'host Docker. Le azioni che dipendono l'autenticazione con un Docker del Registro di sistema, ad esempio il push di un'immagine, è necessario che venga fornito una Docker connessione del Registro di sistema.

L'estensione di Visual Studio Team Services Docker vengono installati i componenti seguenti nell'account di Visual Studio Team Services:

-   Un endpoint del servizio per la connessione a un registro di sistema di Docker

-   Un endpoint del servizio per la connessione a un Host del contenitore Docker

-   Un'attività di Docker per le operazioni seguenti:

-   Compilare un'immagine

-   Push un'immagine o un repository di un registro di sistema

-   Eseguire un'immagine in un contenitore

-   Eseguire un comando di Docker

-   Un'attività per eseguire un comando di Docker Compose Docker Compose

Con queste attività di Visual Studio Team Services, una generazione macchina virtuale Host Docker Linux/provisioning in Azure e preferito Docker Registro di sistema (del Registro di sistema di Azure contenitore, Hub Docker, DTR Docker privato o qualsiasi altro Docker del Registro di sistema) è possibile assemblare le pipeline CI Docker in un molto coerente.

***Requisiti:***

-   Visual Studio Team Services o per le installazioni locali, Team Foundation Server 2015 Update 3 o versione successiva.

-   Un agente di Visual Studio Team Services con i file binari di Docker.

Un modo semplice per creare uno di questi consiste nell'utilizzare Docker per eseguire un contenitore in base all'immagine di Docker dell'agente di Visual Studio Team Services.

**Altre informazioni** leggere approfondire le proprie assemblaggio un Visual Studio Team Services Docker degli elementi di configurazione di pipeline e per visualizzare procedure dettagliate, visitare i siti seguenti:

In esecuzione un agente di Visual Studio Team Services come un contenitore Docker: [ https://hub.docker.com/r/\ -agente di vsts di microsoft / /](https://hub.docker.com/r/microsoft/vsts-agent/)

Estensione Docker di Visual Studio Team Services: <https://aka.ms/vstsdockerextension>

La creazione di immagini di .NET Core Linux Docker con Visual Studio Team Services: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

La creazione di un computer di compilazione del servizio Visual Studio Team basati su Linux con il supporto di Docker: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Integrare, testare e convalidare multicontainer applicazioni di Docker

In genere, la maggior parte delle applicazioni di Docker sono composti da più contenitori anziché un singolo contenitore. Un buon esempio è un'applicazione orientata ai servizi microservizi per i quali è un contenitore per ogni microservizio. Ma, anche senza criteri approccio microservizi rigorosamente seguenti, è molto probabile che l'applicazione di Docker potrebbe essere composti da più servizi o i contenitori.

Pertanto, dopo la creazione dei contenitori di applicazioni nella pipeline di elementi di configurazione, è necessario distribuire, integrare e testare l'applicazione nel suo complesso con tutti i relativi contenitori all'interno di un host Docker integrazione o persino in un cluster di test al quale sono limitate ai contenitori distribuito.

Se si usa un singolo host, è possibile utilizzare i comandi di Docker, ad esempio docker-comporre per compilare e distribuire i contenitori correlati per testare e convalidare l'ambiente di Docker in una singola macchina virtuale. Tuttavia, se si lavora con un cluster di orchestrator come controller di dominio/OS, Kubernetes o Docker Swarm, è necessario distribuire i contenitori tramite un meccanismo diverso o un agente di orchestrazione, in base alla propria selezionato cluster/utilità di pianificazione.

Di seguito sono diversi tipi di test che è possibile eseguire in contenitori Docker:

-   Unit test per i contenitori di Docker

-   Gruppi di test di applicazioni correlate o microservizi

-   Nelle versioni di produzione e "Canarie" di test

L'aspetto importante è che, durante l'esecuzione di test funzionali e integrazione, è necessario eseguire tali test di fuori dei contenitori. Test è necessario non essere definite ed eseguite all'interno di contenitori che si desidera distribuire, poiché i contenitori sono basati sulle immagini statiche che devono essere simili a quelli che verranno distribuiti nell'ambiente di produzione.

Una soluzione molto attuabile durante il test di scenari più avanzati, ad esempio test diversi cluster (test cluster, gestione temporanea del cluster e cluster in produzione) consiste nel pubblicare le immagini a un registro di sistema per eseguire il test nei cluster diversi.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Eseguire il push l'immagine di Docker applicazione personalizzata nel Registro di sistema globale di Docker

Dopo avranno testate e convalidate le immagini Docker, è opportuno assegnare contrassegni e pubblicarli nel Registro di sistema Docker. Il Registro di sistema di Docker è un'informazione fondamentale nel ciclo di vita dell'applicazione Docker perché è la posizione centrale in cui si archiviano i test personalizzati (noto anche come "documento immagini") da distribuire in ambienti QA e produzione.

Simile al modo in cui il codice dell'applicazione archiviato nel repository del controllo del codice sorgente (Git, e così via) è il "origine di dati reali", il Registro di sistema di Docker è "origine di dati reali" per l'applicazione binario o bit da distribuire in ambienti di produzione o di conferma del controllo.

In genere, si potrebbe voler essere il repository privati per le immagini personalizzate in un repository privato nel Registro di sistema contenitore di Azure o in un registro di sistema locale, ad esempio registro attendibile Docker o nel Registro di sistema di cloud pubblico con accesso limitato (ad esempio Hub docker), anche se in quest'ultimo caso, se il codice non è open source, deve considerare attendibile la sicurezza del fornitore. In entrambi i casi, il metodo mediante il quale si esegue questa operazione è piuttosto simile ed è in definitiva basato sul comando docker push, come illustrato nella figura 5-4.

![](./media/image4.png)

Figura 5-4: pubblicazione di immagini personalizzate al Registro di sistema di Docker

Ci sono più offerte di registri Docker da fornitori di cloud, ad esempio del Registro di sistema di Azure contenitore del Registro di sistema di Amazon Web Services contenitore, del Registro di sistema di Google contenitore, Quay del Registro di sistema e così via.

Utilizza l'estensione di Visual Studio Team Services Docker, è possibile distribuire un set di immagini di servizio definiti da un file docker compose.yml, con più tag, a un autenticato Docker del Registro di sistema (ad esempio Azure contenitore del Registro di sistema), come illustrato nella figura 5-5.

![](./media/image5.png)

Figura 5-5: utilizzo di Visual Studio Team Services per pubblicazione immagini personalizzate a un registro di sistema di Docker

**Altre informazioni** per altre informazioni sull'estensione Docker per Visual Studio Team Services, passare a <https://aka.ms/vstsdockerextension>. Per ulteriori informazioni sul Registro di sistema contenitore di Azure, passare a <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Passaggio 4: CD, distribuzione

Immutabilità delle immagini Docker garantisce una distribuzione ripetibile con ciò che ha sviluppato, testato mediante CI ed eseguire nell'ambiente di produzione. Dopo aver creato le immagini Docker applicazione pubblicate nel Registro di sistema Docker (pubblico o privato), è possibile distribuirli agli ambienti diversi che possono verificarsi (ambiente di produzione, controllo di qualità, gestione temporanea, e così via) da pipeline CD utilizzando Visual Studio Team Services le attività della pipeline o gestione del rilascio di Visual Studio Team Services.

Tuttavia, a questo punto dipende dal tipo di applicazione di Docker si sta distribuendo. Distribuzione di un'applicazione semplice (da una composizione e distribuzione punto di vista), ad esempio un monolitico dell'applicazione che comprende alcuni contenitori o i servizi e distribuita su alcuni server o le macchine virtuali è molto diversa dalla distribuzione di un'applicazione più complessa, ad esempio un applicazione orientata ai servizi microservizi con la funzionalità iperscalabile. Questi due scenari sono illustrati nelle sezioni seguenti.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Distribuzione composto da applicazioni di Docker in più ambienti di Docker

Verrà ora esaminato il primo scenario il meno complesso: la distribuzione agli semplice Docker host (macchine virtuali o i server) in un unico ambiente o in più ambienti (QA, gestione temporanea e produzione). In questo scenario, la pipeline CD può essere utilizzata internamente docker-comporre (delle attività di distribuzione di Visual Studio Team Services) per distribuire le applicazioni di Docker con il relativo set correlato di contenitori o servizi, come illustrato nella figura 5-6.

![](./media/image6.png)

Figura 5-6: distribuzione dei contenitori di applicazioni semplici Docker host ambienti Registro di sistema

Figura 5-7 evidenzia come connettersi l'elemento di configurazione di compilazione agli ambienti QA/test tramite Visual Studio Team Services facendo clic su Docker Compose nella finestra di dialogo Aggiungi attività. Tuttavia, quando si distribuisce agli ambienti di produzione o gestione temporanea, in genere utilizzare le funzionalità di gestione del rilascio gestisce più ambienti (ad esempio QA, gestione temporanea e produzione). Se si distribuisce per singolo host Docker, è usando Visual Studio Team Services attività "Docker Compose" (che consiste nel richiamare docker-comporre il comando dietro le quinte). Se si distribuisce il servizio di contenitore di Azure, Usa l'attività di distribuzione di Docker, come illustrato nella sezione che segue.

![](./media/image7.png)

Figura 5-7: aggiunta di un'attività Docker Compose in una pipeline di Visual Studio Team Services

Quando si crea una versione in Visual Studio Team Services, richiede un set di elementi di input. Questi sono destinati a essere modificabile per tutta la durata della versione in ambienti diversi. Quando si introducono i contenitori, gli elementi di input identificano le immagini in un registro di sistema per la distribuzione. A seconda del modo in cui questi vengono identificati, essi non sono garantiti come rimangono invariati per tutta la durata della versione, il caso più evidente quando si fa riferimento a "myimage:latest" da un file docker-compose.

L'estensione Docker per Visual Studio Team Services offre la possibilità di generare gli artefatti di compilazione che contengono l'immagine del Registro di sistema un digest garantiti per identificare in modo univoco la stessa immagine binaria. Si tratta ciò che si vuole poter usare come input a una versione.

### <a name="managing-releases-to-docker-environments-by-using-visual-studio-team-services-release-management"></a>Gestione dei rilasci in ambienti di Docker con gestione del rilascio di Visual Studio Team Services

Tramite le estensioni di Visual Studio Team Services, è possibile compilare una nuova immagine, pubblicarla in un registro di sistema di Docker, eseguirlo in Linux o Windows host e utilizzare i comandi, ad esempio docker-comporre per distribuire più contenitori come un'intera applicazione, intera l'oggetto visivo Funzionalità di Team Services Release Management Studio destinate a più ambienti, come illustrato nella figura 5-8.

![](./media/image8.png)

Figura 5-8: configurazione di Visual Studio Team Services Docker Compose attività da Visual Studio Team Services Release Management

Tuttavia, tenere presente che lo scenario illustrato nella figura 5-6 e implementato in figura 5-8 è piuttosto semplice (consiste nel distribuire in macchine virtuali e host Docker semplice, e sarà presente un singolo contenitore o un'istanza per ogni immagine) e probabilmente deve essere utilizzato solo per lo sviluppo o test sc con. Nella maggior parte degli scenari di produzione dell'organizzazione, si desidera avere la disponibilità elevata e scalabilità per gestire dal bilanciamento del carico tra più nodi, i server e le macchine virtuali, oltre "i failover intelligenti" in modo che se un server o un nodo ha esito negativo, i servizi e i contenitori verranno spostati in un altro server host o VM. In tal caso, è necessario tecnologie più avanzate quali i cluster di contenitore, orchestrators e le utilità di pianificazione. Pertanto, il modo per distribuire tali cluster è precisamente tramite gli scenari avanzati illustrati nella sezione successiva.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Distribuzione di applicazioni complesse di Docker ai cluster Docker (controller di dominio/OS Kubernetes e Docker Swarm)

La natura delle applicazioni distribuite richiede risorse di calcolo che sono inoltre distribuite. Per le funzionalità di scala di produzione, è necessario che le funzionalità che forniscono la scalabilità elevate di clustering e disponibilità elevata in base alle risorse in pool.

È possibile distribuire manualmente i contenitori per tali cluster da uno strumento di interfaccia CLI, ad esempio Docker Swarm (come l'uso [creare servizio docker](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) o un'interfaccia utente web, ad esempio [Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) per controller di dominio/OS cluster, ma è necessario riservare che solo per i test della distribuzione punctual o per scopi di gestione, ad esempio la scalabilità orizzontale o a scopo di monitoraggio.

Da un CD punto di vista e Visual Studio Team Services in particolare, è possibile eseguire attività di distribuzione in modo speciale effettuata da ambienti di gestione del rilascio di Visual Studio Team Services che verranno distribuire le applicazioni nei contenitori in cluster distribuite in Servizio di contenitore, come illustrato nella figura 5 a 9.

![](./media/image9.png)

Figura 5-9: distribuzione di applicazioni distribuite per il servizio contenitore

Inizialmente, quando si distribuisce a determinati cluster o orchestrators, in genere utilizzare meccanismi per ogni orchestrator (vale a dire, controller di dominio/OS Mesosphere o Kubernetes dispongono di meccanismi di distribuzione diversi rispetto a Docker e Docker e gli script di distribuzione specifico Swarm) anziché il più semplice e facile da usare docker-comporre strumento in base al file di definizione compose.yml docker. Tuttavia, ringraziamenti l'attività di Microsoft Visual Studio Team Services Docker distribuire, illustrato nella figura 5-10, ora anche distribuire al controller di dominio o sistema operativo utilizzando solo il file docker-compose.yml familiare perché Microsoft esegue tale "traduzione" per l'utente (dal docker compose.yml file in altri formati necessari dal controller di dominio/OS).

![](./media/image10.png)

Figura 5 a 10: aggiunta dell'attività distribuire Docker per l'ambiente di RM

Figura 5-11 viene illustrato come è possibile modificare l'attività di distribuzione di Docker e specificare il tipo di destinazione (contenitore del servizio controller di dominio/sistema operativo Azure, in questo caso), il File di comporre Docker e la connessione Docker del Registro di sistema (ad esempio del Registro di sistema contenitore di Azure o Hub Docker). Si tratta in cui l'attività recupererà le immagini Docker personalizzate pronto all'uso deve essere distribuito come i contenitori inclusi nel cluster di controller di dominio/OS.

![](./media/image11.png)

Figura 5-11: Docker Distribuisci attività definizione distribuzione al contenitore del servizio controller di dominio/sistema operativo Azure

**Altre informazioni** per altre informazioni sulla pipeline CD con Visual Studio Team Services e Docker, visitare i siti seguenti:

Estensione di Visual Studio Team Services per Docker e il servizio contenitore di Azure: [ https://aka.ms/\ vstsdockerextension](https://aka.ms/vstsdockerextension)

Servizio di contenitore di Azure: <https://aka.ms/azurecontainerservice>

Controller di dominio mesosphere/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Passaggio 5: Eseguire e gestire

Poiché in esecuzione e la gestione delle applicazioni in fase di produzione enterprise livello è un oggetto principale in di se stesso e a causa del tipo di operazioni e persone lavorano a tale livello (operatori IT), nonché l'ambito di grandi dimensioni di quest'area, è stata dedicato dell'intero accanto capitolo di descriverlo.

## <a name="step-6-monitor-and-diagnose"></a>Passaggio 6: Monitoraggio e diagnosi

In questo argomento anche viene illustrato nel capitolo successivo come parte delle attività che esegue le operazioni IT in sistemi di produzione. Tuttavia, è importante per evidenziare che le informazioni ottenute in questo passaggio necessario inserire nuovamente al team di sviluppo in modo che l'applicazione verrà costantemente migliorata. Da tale punto di vista fa anche parte di DevOps, anche se le attività e le operazioni vengono in genere eseguite da IT.

Solo quando il monitoraggio e diagnostica è piene al 100% all'interno dell'area di autenticazione di DevOps sono i processi di monitoraggio e analitica eseguita dal team di sviluppo in ambienti di test o beta. Questa operazione viene eseguita mediante l'esecuzione di test di carico o semplicemente monitorando beta o ambienti di conferma del controllo, in cui beta tester sta cercando le nuove versioni.

>[!div class="step-by-step"]
[Precedente](index.md)
[Successivo](../run-manage-monitor-docker-environments/index.md)
