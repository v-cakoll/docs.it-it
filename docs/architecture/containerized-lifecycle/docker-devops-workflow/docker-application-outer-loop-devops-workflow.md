---
title: Passaggi nel flusso di lavoro DevOps del ciclo esterno per un'applicazione Docker
description: Informazioni sui passaggi del "ciclo esterno" del flusso di lavoro DevOps
ms.date: 02/15/2019
ms.openlocfilehash: 735f92c00cd6279649ec3b0c35cfb00543f21a8c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936787"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Passaggi nel flusso di lavoro DevOps del ciclo esterno per un'applicazione Docker

La figura 5-1 mostra una rappresentazione end-to-end dei passaggi che comprendono il flusso di lavoro del ciclo esterno DevOps. Mostra il "ciclo esterno" di DevOps. Quando viene eseguito il push del codice al repository, viene avviata una pipeline di integrazione continua, quindi viene attivata la pipeline di distribuzione continua nella quale viene distribuita l'applicazione. La metrica registrata dalle applicazioni distribuite viene reinserita nel carico di lavoro di sviluppo, in cui si svolge il "ciclo interno", pertanto i team di sviluppo hanno a disposizione dati reali per soddisfare le esigenze dell'organizzazione e degli utenti finali.

![Diagramma che mostra i 6 passaggi del flusso di lavoro del ciclo esterno DevOps.](./media/docker-application-outer-loop-devops-workflow/overview-dev-ops-outter-loop-workflow.png)

**Figura 5-1**. Flusso di lavoro del ciclo esterno DevOps per le applicazioni Docker con strumenti Microsoft

Di seguito verrà esaminato ognuno di questi passaggi in maggior dettaglio.

## <a name="step-1-inner-loop-development-workflow"></a>Passaggio 1: Flusso di lavoro di sviluppo del ciclo internoStep 1: Inner-loop development workflow

Questo passaggio è illustrato in dettaglio nel capitolo 4. Tuttavia, per ricapitolare, questo è il punto in cui inizia il ciclo esterno, il momento in cui lo sviluppatore esegue il push del codice al sistema di gestione del controllo del codice sorgente (ad esempio Git) che avvia le azioni della pipeline di integrazione continua.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Passaggio 2: Integrazione e gestione del controllo del codice sorgente con i servizi DevOps e Git di AzureStep 2: Source-Code Control integration and management with Azure DevOps Services and Git

Per questo passaggio è necessario avere un sistema di controllo delle versioni per raccogliere una versione consolidata di tutto il codice proveniente da diversi sviluppatori del team.

Sebbene il controllo del codice sorgente (SCC) e la gestione del codice sorgente possano sembrare attività scontate alla maggior parte degli sviluppatori, quando si creano applicazioni Docker in un ciclo di vita DevOps è importante sottolineare che le immagini Docker non devono essere inviate con l'applicazione direttamente al registro Docker globale, ad esempio al Registro Azure Container o a Docker Hub, dal computer dello sviluppatore. Al contrario, le immagini Docker che devono essere rilasciate e distribuite negli ambienti di produzione devono essere create esclusivamente nel codice sorgente che viene integrato nella pipeline di compilazione o integrazione continua basata sul repository del codice sorgente, ad esempio Git.

Le immagini locali generate dagli sviluppatori dovrebbero essere usate solo dagli sviluppatori durante i test nei propri computer. Per questa ragione è fondamentale avere la pipeline DevOps attivata dal codice di controllo del codice sorgente.

Azure DevOps Services e Team Foundation Server supportano Git e il controllo della versione di Team Foundation. È possibile scegliere una delle due opzioni e usarla per un'esperienza Microsoft end-to-end. Tuttavia, è anche possibile gestire il codice in repository esterni, ad esempio GitHub, repository Git locali o Subversion, ed essere ancora in grado di connettersi e ottenere il codice come punto di partenza della pipeline di integrazione continua DevOps.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Passaggio 3: Creare, CI, integrare e testare con i servizi DevOps di Azure e DockerStep 3: Build, CI, Integrate, and Test with Azure DevOps Services and Docker

L'integrazione continua rappresenta oggi uno standard per il test e la distribuzione dei software moderni. La soluzione Docker mantiene una netta separazione delle problematiche tra il team di sviluppo e il team operazioni. L'immutabilità delle immagini Docker assicura una distribuzione ripetibile tra ciò che viene sviluppato, testato tramite l'integrazione continua ed eseguito in produzione. Il motore Docker distribuito nei portatili degli sviluppatori e nell'infrastruttura di test rende i contenitori portatili tra gli ambienti.

Ora che si dispone di un sistema di controllo delle versioni cui è stato inviato il codice corretto, è necessario un *servizio di compilazione* per prelevare il codice ed eseguire la compilazione globale e i test.

Il flusso di lavoro interno per questo passaggio (integrazione continua, compilazione, test) prevede la costruzione di una pipeline di integrazione continua che include il repository del codice (Git e così via), il server di compilazione (Azure DevOps Services), il motore Docker e un registro Docker.

È possibile usare Azure DevOps Services come base per la creazione delle applicazioni e l'impostazione della pipeline di integrazione continua e per la pubblicazione degli "artefatti" della compilazione in un "repository degli artefatti", descritte nel passaggio successivo.

Quando si usa Docker per la distribuzione, gli "artefatti finali" da distribuire sono immagini Docker con l'applicazione o i servizi incorporati. Queste immagini vengono sottoposte a push o vengono pubblicate in un *registro Docker*, ovvero un repository privato simile a quelli di Registro Azure Container o un repository pubblico come il registro Docker Hub solitamente usato per le immagini di base ufficiali.

Ecco il concetto di base: la pipeline CI verrà avviata da un commit in un repository SCC come Git. Il commit fa in modo che Azure DevOps Services esegua un processo di compilazione all'interno di un contenitore Docker e, al termine del processo, esegue il push di un'immagine Docker nel registro Docker, come illustrato nella figura 5-2. La prima parte del ciclo esterno prevede i passaggi da 1 a 3, dal codice, eseguire, eseguire il debug e convalidare, quindi il codice repo fino al passaggio di compilazione e test CI.

![Diagramma che mostra i tre passaggi coinvolti nel flusso di lavoro CI.](./media/docker-application-outer-loop-devops-workflow/continuous-integration-steps.png)

**Figura 5-2**. Passaggi previsti nell'integrazione continua

Di seguito sono elencati i passaggi del flusso di lavoro di integrazione continua di base con Docker e Azure DevOps Services:

1. Lo sviluppatore esegue il push di un commit in un repository di controllo del codice sorgente (Git o Azure DevOps Services, GitHub e così via).

2. Se si usa Azure DevOps Services o Git, l'integrazione continua è incorporata, ovvero è sufficiente selezionare una casella di controllo in Azure DevOps Services. Se si usa un controllo del codice sorgente esterno, come GitHub, `webhook` segnala a Azure DevOps Services l'aggiornamento o il push in Git o GitHub.

3. Azure DevOps Services esegue il pull del repository di controllo del codice sorgente contenente il Dockerfile che descrive l'immagine e il codice dell'applicazione e del test.

4. Azure DevOps Services compila un'immagine Docker e assegna all'immagine un'etichetta con il numero di build.

5. Azure DevOps Services crea un'istanza del contenitore Docker all'interno dell'host Docker di cui è stato effettuato il provisioning ed esegue i test appropriati.

6. Se i test hanno esito positivo, viene innanzitutto assegnata all'immagine un'etichetta con un nome significativo a indicare che si tratta di una build verificata, (ad esempio "/1.0.0" oppure qualsiasi altra etichetta) e viene quindi eseguito il push dell'immagine nel registro Docker (Docker Hub, Registro Azure Container, DTR e così via)

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementazione della pipeline di integrazione continua con Azure DevOps Services e l'estensione Docker per Azure DevOps Services

Visual Studio Azure DevOps Services contiene modelli di compilazione e versione che è possibile usare nella pipeline CI/CD con cui le immagini Docker vengono compilate, ne viene eseguito il push in un registro Docker autenticato, vengono eseguite oppure vengono eseguite altre operazioni offerte dall'interfaccia della riga di comando Docker. Azure DevOps Services aggiunge anche un'attività Docker Compose che consente di compilare, eseguire il push ed eseguire applicazioni Docker con più contenitori oppure eseguire altre operazioni offerte dall'interfaccia della riga di comando Docker Compose, come illustrato nella figura 5-3.

![Screenshot of the Docker CI pipeline in Azure DevOps.](./media/docker-application-outer-loop-devops-workflow/docker-ci-pipeline-azure-devops.png)

**Figura 5-3**. Pipeline di integrazione continua di Docker in Azure DevOps Services con modelli di compilazione e versione e attività associate.

È possibile usare i modelli e le attività per costruire gli artefatti CI/CD per la compilazione, il test e la distribuzione in Azure Service Fabric, nel servizio Azure Kubernetes e offerte simili.

Con queste attività di Visual Studio Team Services, un host o una macchina virtuale Linux-Docker compilata di cui è stato effettuato il provisioning in Azure e il registro Docker desiderato (Registro Azure Container, Docker Hub, un DTR Docker privato o un altro registro Docker) è possibile assemblare la propria pipeline di integrazione continua Docker in un modo molto coerente.

***Requisiti:***

- Azure DevOps Services oppure, per le installazioni locali, Team Foundation Server 2015 Update 3 o versioni successive.

- Un agente Azure DevOps Services con i file binari Docker.

  Un modo semplice per creare uno di questi agenti consiste nell'usare Docker per eseguire un contenitore basato sull'immagine Docker dell'agente Azure DevOps Services.

> [!INFORMATION] Per altre informazioni su come assemblare un pipeline di integrazione continua Docker di Azure DevOps Services e visualizzare le procedure dettagliate, visitare i siti seguenti:
>
> - Esecuzione di un agente Visual Studio Team Services (ora Azure DevOps Services) come contenitore Docker: \
>   <https://hub.docker.com/_/microsoft-azure-pipelines-vsts-agent>
>
> - Compilazione di immagini Linux Docker di .NET Core con Azure DevOps Services: \
>   <https://docs.microsoft.com/archive/blogs/stevelasker/building-net-core-linux-docker-images-with-visual-studio-team-services>
>
> - Creazione di un computer di compilazione Visual Studio Team Service basato su Linux con il supporto Docker: \
>   <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multi-container-docker-applications"></a>Integrare, testare e convalidare applicazioni Docker con più contenitori

In genere, la maggior parte delle applicazioni Docker sono composte da più contenitori anziché da un singolo contenitore. Un buon esempio è un'applicazione orientata ai microservizi con un contenitore per ogni microservizio. Tuttavia, anche senza seguire rigorosamente i modelli di approccio dei microservizi, è probabile che l'applicazione Docker sia composta da più contenitori o servizi.

Di conseguenza, dopo aver compilato i contenitori dell'applicazione nella pipeline di integrazione continua, è necessario anche distribuire, integrare e testare l'applicazione nel suo complesso con tutti i contenitori all'interno di un host Docker di integrazione o in un cluster di test in cui vengono distribuiti i contenitori.

Se si usa un singolo host, è possibile usare i comandi Docker, ad esempio docker-compose, per compilare e distribuire i contenitori correlati per testare e convalidare l'ambiente Docker in una singola macchina virtuale. Se si usa invece un cluster di agenti di orchestrazione come DC/OS, Kubernetes o Docker Swarm, è necessario distribuire i contenitori tramite un meccanismo o un agente di orchestrazione diverso, a seconda del cluster o dell'utilità di pianificazione selezionata.

Di seguito sono riportati diversi tipi di test che è possibile eseguire su contenitori Docker:

- Unit test per i contenitori Docker

- Gruppi di test di applicazioni o microservizi correlati

- Test in ambiente di produzione e versioni "canary"

È importante tenere presente che durante l'esecuzione dei test di integrazione e funzionali, i test devono essere eseguiti dall'esterno dei contenitori. I test non sono contenuti e non vengono eseguiti nei contenitori da distribuire poiché i contenitori sono basati su immagini statiche che corrisponderebbero esattamente a quelle in distribuzione nell'ambiente di produzione.

Per il test di scenari più avanzati come quelli con più cluster (cluster di test, cluster di staging e cluster di produzione) può essere utile pubblicare le immagini in un registro per poterle testare nei diversi cluster.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Eseguire il push dell'immagine Docker dell'applicazione personalizzata nel registro Docker globale

Dopo aver testato e convalidato le immagini Docker è possibile assegnare un tag e pubblicarle nel registro Docker. Il registro Docker è un elemento fondamentale del ciclo di vita dell'applicazione Docker poiché rappresenta la posizione centrale in cui viene archiviato il test personalizzato (chiamato anche "immagini verificate") da distribuire negli ambienti di controllo di qualità e produzione.

Analogamente al codice dell'applicazione archiviato nel repository di controllo del codice sorgente (Git e così via) che rappresenta la "fonte della verità", il registro Docker è la "fonte della verità" per l'applicazione binaria o i bit da distribuire negli ambienti di controllo di qualità e produzione.

In genere si preferisce archiviare i repository privati per le immagini personalizzate in un repository privato in Registro Azure Container o in un registro locale come Docker Trusted Registry oppure in un registro pubblico sul cloud con accesso limitato (come Docker Hub), sebbene in quest'ultimo caso se il codice non è open source è necessario fidarsi della sicurezza del fornitore. In entrambi i casi, il metodo usato è simile e basato sul comando `docker push`, come illustrato nella figura 5-4.

![Diagramma che mostra il push di immagini personalizzate in un registro contenitori.](./media/docker-application-outer-loop-devops-workflow/docker-push-custom-images.png)

**Figura 5-4**. Pubblicazione di immagini personalizzate nel registro Docker

Nel passaggio 3, per l'integrazione e il test (CI) è possibile pubblicare le immagini Docker risultati in un registro privato o pubblico. I fornitori di cloud offrono diversi registri Docker come Registro Azure Container, il registro contenitori di Amazon Web Services, Google Container Registry, Quay Registry e così via.

Usando le attività Docker è possibile eseguire il push di un set di immagini di servizio definito da un file `docker-compose.yml`, con più tag, in un registro Docker autenticato (come Registro Azure Container), come illustrato nella figura 5-5.

![Screenshot che mostra il passaggio per pubblicare immagini in un Registro di sistema.](./media/docker-application-outer-loop-devops-workflow/publish-custom-image-to-docker-registry.png)

**Figura 5-5**. Uso di Azure DevOps Services per la pubblicazione di immagini personalizzate in un registro Docker

> [!INFORMATION] Per altre informazioni su Registro Azure Container, vedere <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Passaggio 4: CD, distribuzioneStep 4: CD, Deploy

L'immutabilità delle immagini Docker assicura una distribuzione ripetibile con ciò che viene sviluppato, testato tramite l'integrazione continua ed eseguito in produzione. Dopo aver pubblicato le immagini Docker dell'applicazione nel registro Docker pubblico o privato è possibile distribuirle in più ambienti (produzione, controllo di qualità, staging e così via) dalla pipeline di distribuzione continua usando le attività della pipeline Azure DevOps Services oppure la gestione del rilascio di Azure DevOps Services.

A questo punto, tuttavia, la procedura varia a seconda del tipo di applicazione Docker da distribuire. La distribuzione di un'applicazione semplice in termini di composizione e distribuzione come un'applicazione monolitica costituita da alcuni contenitori o servizi e distribuita su pochi server o macchine virtuali è diversa dalla distribuzione di un'applicazione complessa come un'applicazione orientata ai microservizi con capacità di iperscalabilità. Questi due scenari sono descritti nelle sezioni seguenti.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Distribuzione di applicazioni Docker composte in più ambienti Docker

Verrà descritto per primo lo scenario meno complesso: la distribuzione in host Docker semplici (macchine virtuali o server) in un unico ambiente o in più ambienti (controllo di qualità, staging e produzione). In questo scenario la pipeline di distribuzione continua può usare internamente docker-compose (dalle attività di distribuzione di Azure DevOps Services) per distribuire le applicazioni Docker con il relativo set di contenitori o servizi, come illustrato nella figura 5-6.

![Diagramma che mostra il passaggio di distribuzione del CD in tre ambienti.](./media/docker-application-outer-loop-devops-workflow/deploy-app-containers-to-docker-host-environments.png)

**Figura 5-6**. Distribuzione dei contenitori dell'applicazione nel registro ambienti host di Docker

La figura 5-7 illustra come connettere l'integrazione continua di compilazione ad ambienti di controllo di qualità/test tramite Azure DevOps Services facendo clic su Docker Compose nella finestra di dialogo Aggiungi attività. Tuttavia, durante la distribuzione in ambienti di staging o produzione si usano in genere le funzionalità di gestione del rilascio per la gestione di più ambienti, ad esempio degli ambienti di controllo di qualità, staging e produzione. Se si esegue la distribuzione in singoli host Docker, si usa l'attività "Docker Compose" di Azure DevOps Services che richiama il comando `docker-compose up` in background. Se si esegue la distribuzione nel servizio Azure Kubernetes, viene usata l'attività Distribuzione di Docker, come descritto nella sezione seguente.

![Screenshot della finestra di dialogo Aggiungi attività dell'attività Componi docker.](./media/docker-application-outer-loop-devops-workflow/add-tasks-docker-compose.png)

**Figura 5-7**. Aggiunta di un'attività Docker Compose in una pipeline Azure DevOps Services

Quando si crea una versione in Azure DevOps Services è necessario un set di artefatti di input. Questi artefatti devono essere immutabili per la durata della versione, in tutti gli ambienti. Quando si inseriscono i contenitori, gli artefatti di input identificano le immagini in un registro per la distribuzione. A seconda del modo in cui vengono identificate queste immagini, non ne è garantita immutabilità per tutta la durata della versione, in particolare quando si fa riferimento a `myimage:latest` da un file `docker-compose`.

I modelli di Azure DevOps Services consentono di creare artefatti di compilazione contenenti i codici hash dell'immagine del registro specifici che identificano in modo univoco lo stesso binario immagine. Si tratta degli elementi che si vuole usare come input per una versione.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Gestione dei rilasci per gli ambienti Docker tramite la gestione del rilascio di Azure DevOps Services

Usando i modelli di Azure DevOps Services è possibile compilare una nuova immagine, pubblicarla in un registro Docker, eseguirla su host Linux o Windows e usare comandi, ad esempio `docker-compose`, per distribuire più contenitori come applicazione completa, il tutto tramite le funzionalità di gestione del rilascio di Azure DevOps Services progettate per più ambienti, come illustrato nella figura 5-8.

![Screenshot che mostra la configurazione delle versioni di composizione Docker.](./media/docker-application-outer-loop-devops-workflow/configure-docker-compose-release.png)

**Figura 5-8**. Configurazione delle attività Docker Compose di Azure DevOps Services dalla gestione del rilascio di Azure DevOps Services

Tenere presente che lo scenario illustrato nella figura 5-6 e implementato nella figura 5-8 è uno scenario semplice (la distribuzione viene eseguita in host Docker e macchine virtuali singoli con un contenitore o istanza per ogni immagine) che probabilmente verrà usato solo per scenari di sviluppo o test. Nella maggior parte degli scenari di produzione si preferisce disporre di disponibilità elevata e di una scalabilità facile da gestire con un bilanciamento del carico su più nodi, server e macchine virtuali e "failover intelligenti" in modo che se si verifica un errore in un server o in un nodo, i relativi servizi e contenitori vengano spostati in un altro server o un'altra macchina virtuale host. In quel caso saranno necessarie tecnologie più avanzate, ad esempio cluster di contenitori, agenti di orchestrazione e utilità di pianificazione. Di conseguenza, la distribuzione nei cluster avviene gestendo gli scenari avanzati descritti nella sezione seguente.

### <a name="deploying-docker-applications-to-docker-clusters"></a>Distribuzione di applicazioni Docker in cluster Docker

Le applicazioni distribuite richiedono risorse di calcolo distribuite. Per avere capacità a livello di produzione, è necessario avere capacità di clustering che offrono scalabilità e disponibilità elevate basate su risorse in pool.

Sebbene sia possibile distribuire i contenitori manualmente in questo tipo di cluster da uno strumento dell'interfaccia della riga di comando o un'interfaccia utente Web, è consigliabile riservare questo tipo di lavoro manuale per individuare operazioni di test o gestione delle distribuzioni come scalabilità o monitoraggio.

Dal punto di vista della distribuzione continua, in particolare di Azure DevOps Services, è possibile eseguire attività specifiche per la distribuzione dagli ambienti di gestione del rilascio di Azure DevOps Services che eseguiranno la distribuzione delle applicazioni aggiunte a contenitori in cluster distribuiti nel servizio contenitore, come illustrato nella figura 5-9.

![Diagramma che mostra il passaggio di distribuzione del CD che distribuisce agli agenti di orchestrazione.](./media/docker-application-outer-loop-devops-workflow/cd-deploy-to-orchestrators.png)

**Figura 5-9**. Distribuzione di applicazioni distribuite nel servizio contenitore

Inizialmente, durante la distribuzione in determinati cluster o agenti di orchestrazione, venivano in genere usati script e meccanismi di distribuzione specifici per ogni agente di orchestrazione (Kubernetes e Service Fabric hanno meccanismi di distribuzione diversi) anziché lo strumento `docker-compose` più semplice e facile da usare basato sul file di definizione `docker-compose.yml`. Tuttavia, grazie all'attività Distribuzione di Docker di Azure DevOps Services, illustrata nella figura 5-10, è ora possibile anche distribuire negli agenti di orchestrazione supportati semplicemente usando il file `docker-compose.yml` poiché lo strumento esegue la "conversione" automaticamente (dal file `docker-compose.yml` nel formato richiesto dall'agente di orchestrazione).

![Screenshot che mostra l'attività Distribuisci a Kubernetes.](./media/docker-application-outer-loop-devops-workflow/add-deploy-to-kubernetes-task.png)

**Figura 5-10**. Aggiunta dell'attività Distribuisci in Kubernetes all'ambiente

La figura 5-11 illustra come modificare l'attività Distribuisci in Kubernetes con le sezioni disponibili per la configurazione. Questa attività recupera le immagini Docker personalizzate pronte all'uso da distribuire come contenitori nel cluster.

![Screenshot che mostra la configurazione dell'attività Distribuisci in Kubernetes.](./media/docker-application-outer-loop-devops-workflow/edit-deploy-to-kubernetes-task.png)

**Figura 5-11**. Definizione dell'attività Distribuzione di Docker con distribuzione in DC/OS di ACS

> [!INFORMATION] Per altre informazioni sulla pipeline di distribuzione continua con Azure DevOps Services e Docker, visitare <https://azure.microsoft.com/services/devops/pipelines>

## <a name="step-5-run-and-manage"></a>Passaggio 5: Eseguire e gestire

Poiché l'esecuzione e la gestione di applicazioni a livello di produzione aziendale sono una questione della massima importanza e considerato il tipo di operazioni e gli utenti che operano a quel livello (operazioni IT) e l'enorme ambito di quest'area, l'intero capitolo successivo è dedicato a questi argomenti.

## <a name="step-6-monitor-and-diagnose"></a>Passaggio 6: Monitorare e diagnosticare

Questo argomento è trattato anche nel capitolo successivo come parte delle attività eseguite dal settore IT nei sistemi di produzione. È importante tuttavia sottolineare che le informazioni dettagliate ottenute in questo passaggio devono essere inviate al team di sviluppo per consentire un miglioramento continuo dell'applicazione. Da questo punto di vista, è anche parte di DevOps, sebbene le attività e le operazioni vengano in genere eseguite dal settore IT.

Soltanto al completamento del monitoraggio e della diagnostica in DevOps, il team di sviluppo esegue i processi di monitoraggio e analisi negli ambienti di test o beta. Questa operazione viene eseguita tramite l'esecuzione di test di carico o monitorando gli ambienti beta o di controllo di qualità in cui i beta tester provano a usare le nuove versioni.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
