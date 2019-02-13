---
title: Passaggi nel flusso di lavoro DevOps ciclo esterno per un'applicazione Docker
description: Informazioni sulla procedura per il ciclo"esterno" del flusso di lavoro DevOps
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b75e9df1c31e8bcebcaa6d56336a6aa499d13e1d
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220939"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Passaggi nel flusso di lavoro DevOps ciclo esterno per un'applicazione Docker

Figura 5-1 presenta una descrizione di end-to-end dei passaggi che comprendono il flusso di lavoro DevOps ciclo esterno.

![](./media/image1.png)

Figura 5-1: Flusso di lavoro ciclo esterno DevOps per le applicazioni Docker con strumenti Microsoft

A questo punto, verrà ora esaminato ognuno di questi passaggi in maggiore dettaglio.

## <a name="step-1-inner-loop-development-workflow"></a>Passaggio 1: Flusso di lavoro di sviluppo a ciclo interno

Questo passaggio è illustrato in dettaglio nel capitolo 4, ma, per ricapitolare, ecco dove inizia il ciclo esterno, dal momento in cui uno sviluppatore effettua il push di codice per il sistema di gestione di controllo di origine (ad esempio Git) che ha avviato le azioni della pipeline di integrazione continua.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Passaggio 2: Integrazione del controllo del codice sorgente e gestione dei servizi di Azure DevOps e Git

A questo punto, è necessario disporre di un sistema di controllo della versione per raccogliere una versione codificata di tutto il codice proveniente da diversi sviluppatori del team.

Anche se può sembrare abitudine a maggior parte degli sviluppatori, durante la creazione di applicazioni Docker in un ciclo di vita di DevOps del ciclo di controllo del codice sorgente (SCC) e la gestione del codice sorgente, è essenziale sottolineare che non è necessario inviare le immagini Docker con l'applicazione direttamente per il global Docker del Registro di sistema (ad esempio registro contenitori di Azure o Hub Docker) dal computer dello sviluppatore. Al contrario, le immagini Docker venga rilasciato e distribuiti in ambienti di produzione devono essere create esclusivamente sul codice sorgente che viene integrato nella compilazione globale o della pipeline di integrazione continua basata su repository del codice sorgente (ad esempio Git).

Devono usare immagini locale generate dagli stessi sviluppatori solo dagli sviluppatori durante il test entro le proprie macchine. È per questo motivo è fondamentale per avere la pipeline di DevOps attivata dal codice di controllo del codice sorgente.

Azure DevOps Services e Team Foundation Server supporta Git e Team Foundation Version Control. È possibile scegliere tra di essi e usarlo per un'esperienza di Microsoft end-to-end. Tuttavia, è anche possibile gestire il codice in repository esterni (ad esempio, GitHub, i repository Git locale o Subversion) e ancora essere in grado di connettersi alla cache e ottenere il codice come punto di partenza per la pipeline di integrazione continua di DevOps.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Passaggio 3: Compilare, integrazione continua, integrare e testare con DevOps di Azure i servizi e Docker

Integrazione continua è emersa come standard per la distribuzione e test del software moderno. La soluzione di Docker mantiene una netta separazione delle problematiche tra i team di sviluppo e operazioni. Immutabilità delle immagini Docker assicura una distribuzione ripetibile tra ciò che ha sviluppato, testato con integrazione continua ed eseguire nell'ambiente di produzione. Motore docker distribuito tra i computer portatili per gli sviluppatori e infrastruttura di test rende i contenitori portatile per gli ambienti.

A questo punto, dopo aver creato un sistema di controllo della versione con il codice corretto invio, è necessario un *servizio di compilazione* per prelevare il codice ed eseguire la compilazione globali e i test.

Il flusso di lavoro interno per questo passaggio (CI, compilazione, test) riguarda la costruzione di una pipeline di integrazione continua costituita nel repository del codice (Git, e così via), il server di compilazione (servizi di Azure DevOps), il motore Docker e un registro Docker.

È possibile utilizzare servizi di Azure DevOps come base per la creazione delle applicazioni e impostare la pipeline di integrazione continua e per la pubblicazione di "elementi" compilati da un "repository di elementi," come illustrato nel passaggio successivo.

Quando si usa Docker per la distribuzione, gli elementi"finale" per la distribuzione delle immagini Docker con l'applicazione o i servizi incorporate in esse contenute. Queste immagini vengono effettuato il push o pubblicate in un *registro Docker* (vale a dire un repository privato, ad esempio quelli in Registro contenitori di Azure è possibile avere o una pubblica, ad esempio del Registro di sistema dell'Hub Docker, che viene usato comunemente per le immagini ufficiali di base).

Ecco il concetto di base: La pipeline CI sarà avviata approvazione da un commit a un repository di controllo del codice sorgente come Git. Il commit causerà servizi DevOps di Azure eseguire un processo di compilazione all'interno di un contenitore Docker e, al completamento del processo, eseguire il push un'immagine Docker nel Registro di sistema di Docker, come illustrato nella figura 5-2.

![](./media/image2.png)

Figura 5-2: I passaggi relativi all'integrazione continua

Ecco i passaggi di base degli elementi di configurazione del flusso di lavoro con Docker e servizi di Azure DevOps:

1.  Lo sviluppatore effettua il push di un commit a un repository di controllo del codice sorgente (Git/DevOps servizi di Azure, GitHub e così via).

2.  Se si usa Azure DevOps Service o Git, integrazione continua è incorporato, il che significa che è sufficiente selezionare una casella di controllo in servizi di Azure DevOps. Se si usa un controllo del codice sorgente esterna (ad esempio, GitHub), un *webhook* verrà notificare all'utente di servizi di Azure DevOps dell'aggiornamento o eseguire il push Git e GitHub.

3.  Servizi di Azure DevOps estrae il repository di controllo del codice sorgente, tra cui il documento DockerFile che descrivono l'immagine, nonché il codice dell'applicazione e di test.

4.  Servizi di Azure DevOps crea un'immagine Docker e l'etichetta con un numero di build.

5.  Servizi di Azure DevOps crea un'istanza del contenitore Docker all'interno dell'Host Docker con provisioning e vengono eseguiti i test appropriati.

6.  Se i test hanno esito positivo, l'immagine è rietichettato prima di tutto a un nome significativo, in modo da sapere è una compilazione"documento" (ad esempio "/ 1.0.0" o qualsiasi altra etichetta) e quindi eseguire il push nel Registro di Docker (Docker Hub, registro contenitori di Azure, DTR e così via)

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementazione della pipeline di integrazione continua con servizi di Azure DevOps e l'estensione Docker per i servizi di Azure DevOps

Il [estensione Docker di servizi di Azure DevOps](https://aka.ms/vstsdockerextension) aggiunge un'attività alla pipeline di integrazione continua con la quale è possibile compilare immagini Docker, eseguire il push delle immagini Docker in un registro Docker autenticato, eseguire immagini Docker o eseguire altre operazioni offerti da Docker INTERFACCIA DELLA RIGA DI COMANDO. Aggiunge anche un'attività di Docker Compose che è possibile usare per compilare, eseguire il push ed eseguire applicazioni multicontenitore Docker o eseguire altre operazioni offerte dal comando Docker Compose, come illustrato nella figura 5-3.

![](./media/image3.png)

Figura 5-3: La pipeline di integrazione continua di Docker in servizi di Azure DevOps

L'estensione Docker possa usare gli endpoint di servizio per gli host Docker e del contenitore o i registri di immagini. Il valore predefinito di attività all'uso di un host Docker locale, se disponibile (attualmente è necessario un agente di servizi di Azure DevOps personalizzato); in caso contrario, è necessario specificare una connessione all'host Docker. Le azioni che dipendono l'autenticazione con un registro Docker, ad esempio il push di un'immagine, è necessario specificare un comando Docker connessione del Registro di sistema.

L'estensione Docker di servizi di Azure DevOps installa i componenti seguenti nell'account di servizi di Azure DevOps:

-   Un endpoint del servizio per la connessione a un registro Docker

-   Un endpoint del servizio per la connessione a un Host del contenitore Docker

-   Un'attività di Docker per eseguire le operazioni seguenti:

-   Compilare un'immagine

-   Push di un'immagine o un repository in un registro

-   Eseguire un'immagine in un contenitore

-   Eseguire un comando di Docker

-   Un'attività di Docker Compose per eseguire un comando di Docker Compose

Con queste attività di servizi di Azure DevOps, una compilazione Host Docker Linux/macchine Virtuali sottoposte a provisioning in Azure e il registro Docker preferito (registro contenitori di Azure, Hub Docker, Docker privato DTR o qualsiasi altro registro Docker) è possibile assemblare la pipeline di integrazione continua di Docker in un molto modo coerente.

***Requisiti:***

-   Servizi di Azure DevOps o per le installazioni locali, Team Foundation Server 2015 Update 3 o versione successiva.

-   Un agente di servizi di Azure DevOps con i file binari Docker.

Un modo semplice per creare uno di questi è usare Docker per eseguire un contenitore in base all'immagine Docker dell'agente di servizi di Azure DevOps.

**Altre informazioni** per leggere ulteriori informazioni su un'integrazione continua Docker di Azure DevOps servizi di assemblaggio di pipeline e visualizzare procedure dettagliate, visitare i siti seguenti:

Esegue l'agente di servizi di DevOps di Azure come contenitore Docker: [ https://hub.docker.com/r/\ microsoft/vsts-agent /](https://hub.docker.com/r/microsoft/vsts-agent/)

Estensione Azure DevOps servizi Docker: <https://aka.ms/vstsdockerextension>

Creazione di immagini Linux Docker per .NET Core con i servizi di Azure DevOps: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Creazione di un computer di compilazione basato su Linux con Visual Studio Team Services con il supporto Docker: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Integrare, testare e convalidare applicazioni multicontenitore di Docker

In genere, la maggior parte delle applicazioni Docker sono composti da più contenitori anziché un singolo contenitore. Un buon esempio è un'applicazione orientata ai microservizi per i quali sarebbe necessario un contenitore per ogni microservizio. Ma, anche senza seguire strettamente i modelli di approccio di microservizi, è molto probabile che l'applicazione Docker potrebbe essere composte da più contenitori o servizi.

Di conseguenza, dopo aver compilato i contenitori di applicazioni nella pipeline di integrazione continua, è anche necessario distribuire, integrare e testare l'applicazione nel suo complesso con tutti i contenitori all'interno di un host Docker integration o persino in un cluster di test al quale sono i contenitori distribuito.

Se si usa un singolo host, è possibile usare i comandi di Docker, ad esempio docker-compose per compilare e distribuire i contenitori correlati per testare e convalidare l'ambiente Docker in una singola macchina virtuale. Tuttavia, se si lavora con un cluster dell'agente di orchestrazione DC/OS, Kubernetes o Docker Swarm, è necessario distribuire i contenitori tramite un meccanismo diverso o un agente di orchestrazione, a seconda di selezionato cluster o utilità di pianificazione.

Di seguito sono tipi diversi di test che è possibile eseguire con i contenitori Docker:

-   Gli unit test per i contenitori Docker

-   Test dei gruppi di applicazioni correlate o microservizi

-   Testare in produzione e "canary" nelle versioni

Il punto importante è che quando si esegue l'integrazione e test funzionali, è necessario eseguire questi test da fuori dai contenitori. Test non devono essere definiti ed eseguire all'interno dei contenitori che si desidera distribuire, poiché i contenitori sono basati su immagini statiche che devono essere esattamente come quelle che verranno distribuiti nell'ambiente di produzione.

Un'opzione molto fattibile durante il test di scenari più avanzati, quali i test di diversi cluster (test cluster, cluster di gestione temporanea e cluster di produzione) consiste nel pubblicare le immagini in un registro per testare in vari cluster.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Eseguire il push dell'immagine Docker personalizzata dell'applicazione in globale registro Docker

Dopo che le immagini Docker sono state testate e convalidate, è opportuno assegnare contrassegni e pubblicarli nel registro Docker. Il Registro di Docker è un'informazione fondamentale nel ciclo di vita dell'applicazione Docker perché è la posizione centrale in cui vengono archiviati i test personalizzati (noto anche come "immagini documento") per la distribuzione in ambienti di controllo di qualità e produzione.

Analogamente al modo in cui il codice dell'applicazione archiviato nel repository di controllo del codice sorgente (Git, e così via) è il "source of truth", il Registro di Docker è la "fonte di veridicità" per applicazione binario o bit per la distribuzione in ambienti di produzione o di controllo di qualità.

In genere, si potrebbe voler avere repository privato per le immagini personalizzate in un repository privato in Registro contenitori di Azure in un'istanza di registro in locale, ad esempio registro attendibile Docker o in un registro di sistema di cloud pubblico con accesso limitato (ad esempio Hub docker), anche se in quest'ultimo caso, se il codice non è open source e deve considerare attendibile la sicurezza del fornitore. In entrambi i casi, il metodo mediante il quale si esegue questa operazione è abbastanza simile e infine si basa sul comando docker push, come illustrato nella figura 5-4.

![](./media/image4.png)

Figura 5-4: Pubblicazione di immagini personalizzate al registro Docker

Sono disponibili più offerte di registri Docker da fornitori cloud, ad esempio registro contenitori di Azure, registro contenitori di servizi Web Amazon, registro contenitori di Google, Quay del Registro di sistema e così via.

Uso dell'estensione Docker di servizi di Azure DevOps, è possibile inserire un set di immagini di servizio definiti da un file docker-Compose. yml, con più tag, in un registro Docker autenticato (ad esempio, registro contenitori di Azure), come illustrato nella figura 5-5.

![](./media/image5.png)

Figura 5-5: Con servizi di Azure DevOps per le immagini personalizzate di pubblicazione in un registro Docker

**Altre informazioni** per altre informazioni sull'estensione Docker per i servizi di Azure DevOps, passare a <https://aka.ms/vstsdockerextension>. Per altre informazioni su registro contenitori di Azure, passare a <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Passaggio 4: Recapito Continuo, distribuzione

Immutabilità delle immagini Docker assicura una distribuzione ripetibile con ciò che ha sviluppato, testato con integrazione continua ed eseguire nell'ambiente di produzione. Dopo aver creato le immagini Docker applicazione pubblicate nel registro Docker (privato o pubblico), è possibile distribuirle agli ambienti diversi che potrebbe essere (ambiente di produzione, controllo qualità, staging, e così via) dalla pipeline di recapito Continuo tramite servizi di Azure DevOps le attività della pipeline o servizi di Release Management per Azure DevOps.

Tuttavia, a questo punto dipende il tipo di applicazione Docker si distribuiscono. Distribuire una semplice applicazione (da una composizione e la distribuzione punto di vista), ad esempio un monolitica dell'applicazione che comprende alcuni contenitori o servizi e distribuita da alcuni server o macchine virtuali è molto diversa dalla distribuzione di un'applicazione più complessa, ad esempio un applicazione orientata ai microservizi con capacità su scala molto vasta. Questi due scenari sono illustrati nelle sezioni seguenti.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Distribuzione composto da applicazioni Docker in più ambienti Docker

Verrà ora illustrato lo scenario meno complesso: distribuzione semplice host Docker (macchine virtuali o server) in un singolo ambiente o a più ambienti (controllo di qualità, staging e produzione). In questo scenario, la pipeline di distribuzione può essere utilizzata internamente docker-compose (delle attività di distribuzione di servizi di Azure DevOps) per distribuire le applicazioni Docker con il relativo set correlati di contenitori o servizi, come illustrato nella figura 5-6.

![](./media/image6.png)

Figura 5-6: Distribuzione di contenitori di applicazioni semplici registro ambienti host di Docker

Figura 5-7 evidenzia come è possibile connettersi l'elemento di configurazione di compilazione per gli ambienti di test/controllo qualità tramite servizi di Azure DevOps facendo clic su Docker Compose nella finestra di dialogo Aggiungi attività. Tuttavia, durante la distribuzione in ambienti di gestione temporanea o produzione, in genere utilizzare funzionalità di Release Management, gestione di più ambienti (ad esempio di controllo di qualità, staging e produzione). Se si esegue la distribuzione host Docker singoli, Usa i servizi di Azure DevOps attività "Docker Compose" (che consiste nel richiamare docker-compose comando dietro le quinte). Se si esegue la distribuzione del servizio contenitore di Azure, Usa l'attività di distribuzione di Docker, come illustrato nella sezione che segue.

![](./media/image7.png)

Figura 5-7: Aggiunta di un'attività di Docker Compose in una pipeline di servizi di Azure DevOps

Quando si crea una versione in servizi di Azure DevOps, richiede un set di elementi di input. Questi devono essere non modificabile per tutta la durata della versione in più ambienti. Quando si introducono i contenitori, gli elementi di input identificano immagini in un registro per la distribuzione. A seconda del modo in cui queste associazioni sono identificabili, essi non è garantito che rimangono invariati per tutta la durata della versione, il caso più evidente in corso quando si fa riferimento a "myimage:latest" da un file docker-Compose.

L'estensione Docker per i servizi di Azure DevOps ti offre la possibilità di generare gli artefatti di compilazione che contengono immagini specifiche del Registro di sistema esegue il digest garantite identificare in modo univoco la stessa immagine binaria. Si tratta di ciò che si vuole usare come input per una versione.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>La gestione delle versioni per gli ambienti Docker usando Azure DevOps Services Release Management

Tramite le estensioni di servizi di Azure DevOps, è possibile creare una nuova immagine, pubblicarlo in un registro Docker, eseguirlo in Linux o Windows host e usare i comandi, ad esempio docker-compose per distribuire più contenitori come un'intera applicazione, tutto grazie a DevOps di Azure Servizi destinate per più ambienti, le funzionalità di Release Management come illustrato nella figura 5-8.

![](./media/image8.png)

Figura 5-8: Configurazione delle attività di Azure DevOps servizi Docker Compose da servizi di Release Management per Azure DevOps

Tuttavia, tenere presente che lo scenario illustrato nella figura 5-6 e implementato nella figura 5-8 è piuttosto elementare (consiste nel distribuire in macchine virtuali e host Docker semplice e vi sarà un singolo contenitore o un'istanza per ogni immagine) e probabilmente deve essere usato solo per lo sviluppo o test sc con. Nella maggior parte degli scenari di produzione dell'organizzazione, si desidera avere disponibilità elevata e facile da gestire la scalabilità dal bilanciamento del carico tra più nodi, i server e le macchine virtuali, oltre a "failover intelligente" in modo che se un server o un nodo ha esito negativo, i servizi e i contenitori verranno spostati a un altro server host o macchina virtuale. In tal caso, è necessario più avanzate tecnologie come i cluster del contenitore, gli agenti di orchestrazione e le utilità di pianificazione. Di conseguenza, il modo per distribuire a tali cluster è precisamente agli scenari avanzati illustrati nella sezione successiva.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Distribuzione di applicazioni complesse di Docker per i cluster Docker (DC/OS, Kubernetes e Docker Swarm)

La natura delle applicazioni distribuite richiede risorse di calcolo che vengono distribuite anche. Per le funzionalità a livello di produzione, è necessario avere le funzionalità che forniscono una scalabilità elevata di clustering e disponibilità elevata basata sulle risorse in pool.

È possibile distribuire manualmente i contenitori a tali cluster usando uno strumento della riga di comando, ad esempio Docker Swarm (gradiscano [create del servizio di docker](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) o un'interfaccia utente web, ad esempio [Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) per DC/OS cluster, ma è necessario riservare che solo per test di distribuzione punctual o per scopi di gestione, ad esempio la scalabilità orizzontale o a fini di monitoraggio.

Dal punto di vista di CD e i servizi di Azure DevOps in particolare, è possibile eseguire le attività di distribuzione effettuata in modo speciale dagli ambienti di gestione del rilascio di servizi di Azure DevOps che distribuiranno le applicazioni in contenitori per i cluster distribuiti nel contenitore Servizio, come illustrato nella figura 5-9.

![](./media/image9.png)

Figura 5-9: Distribuzione di applicazioni distribuite nel servizio contenitore di

Inizialmente, durante la distribuzione di determinati i cluster o gli agenti di orchestrazione, in genere utilizzare meccanismi per ogni agente di orchestrazione (vale a dire, Mesosphere DC/OS o Kubernetes dispongono di meccanismi di distribuzione diversi rispetto a Docker e Docker e gli script di distribuzione specifico Swarm) anziché il più semplice e facile da usare docker-compose strumento basato sul file di definizione del docker-Compose. yml. Tuttavia, grazie all'attività distribuzione di Microsoft Azure DevOps servizi Docker, illustrato nella figura 5-10, è ora anche possibile distribuire a DC/OS utilizzando solo il file docker-Compose. yml familiarità perché Microsoft esegue tale "conversione" per l'utente (dal file docker-Compose. yml in altri formati necessari per DC/OS).

![](./media/image10.png)

Figura 5-10: Aggiunta dell'attività di distribuzione Docker per Gestione risorse di ambiente

Figura 5-11 viene illustrato come è possibile modificare l'attività di distribuzione Docker e specificare il tipo di destinazione (Azure DC/OS del servizio contenitore, in questo caso), il File Docker Compose e la connessione al registro Docker (ad esempio registro contenitori di Azure o Hub Docker). Si tratta in cui l'attività recupererà le immagini Docker personalizzate pronti da usare per la distribuzione come i contenitori nel cluster DC/OS.

![](./media/image11.png)

Figura 5-11: Docker Deploy attività definizione distribuzione a Azure DC/OS del servizio contenitore

**Altre informazioni** per altre informazioni sulla pipeline di recapito Continuo con servizi di Azure DevOps e Docker, visitare i siti seguenti:

Estensione servizi di DevOps di Azure per Docker e servizio contenitore di Azure: [ https://aka.ms/\ vstsdockerextension](https://aka.ms/vstsdockerextension)

Servizio contenitore di Azure: <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Passaggio 5: Eseguire e gestire

Perché è in esecuzione e la gestione delle applicazioni in produzione dell'organizzazione a livello di è un argomento principale in e di se stesso e a causa di un tipo di operazioni e persone che lavorano a tale livello (operazioni IT), nonché l'ambito di grandi dimensioni di quest'area, è stata dedicata l'intero successivamente capitolo per spiegarlo.

## <a name="step-6-monitor-and-diagnose"></a>Passaggio 6: Monitorare e diagnosticare

Questo argomento inoltre viene descritto nel capitolo successivo come parte delle attività che esegue operazioni IT in sistemi di produzione. Tuttavia, è importante evidenziare che di informazioni approfondite ottenute in questo passaggio è necessario inserire nuovamente al team di sviluppo in modo che l'applicazione viene continuamente migliorata. Da tale punto di vista, è anche parte della metodologia DevOps, anche se l'attività e le operazioni vengono in genere eseguite dall'IT.

Solo quando il monitoraggio e diagnostica è 100 percento entro l'area di autenticazione della metodologia DevOps sono i processi di monitoraggio e analitica eseguita dal team di sviluppo in ambienti di test o beta. Questa operazione viene eseguita mediante l'esecuzione di test di carico o semplicemente monitorando beta o ambienti di controllo di qualità, in cui permettere a beta tester sta provando le nuove versioni.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
