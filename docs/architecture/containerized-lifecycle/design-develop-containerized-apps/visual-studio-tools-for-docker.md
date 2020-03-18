---
title: Visual Studio Tools per Docker in Windows
description: Informazioni sugli strumenti Docker disponibili in Visual Studio 2017 versione 15.7 e successive.
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673878"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>Usare gli strumenti di Docker in Visual Studio 2017 in Windows

Il flusso di lavoro per sviluppatori con gli strumenti di Docker inclusi in Visual Studio 2017 versione 15.7 e successive è simile all'uso di Visual Studio Code e dell'interfaccia della riga di comando di Docker (è infatti basato sulla stessa interfaccia della riga di comando di Docker), ma è più semplice da iniziare, semplifica il processo e offre una maggiore produttività per le attività di compilazione, esecuzione e composizione. Può anche eseguire i contenitori ed eseguirne il debug tramite le chiavi `F5` e `Ctrl+F5` abituali di Visual Studio. È anche possibile eseguire il debug di un'intera soluzione se i relativi contenitori sono definiti nello stesso file `docker-compose.yml` a livello della soluzione.

## <a name="configure-your-local-environment"></a>Configurare l'ambiente locale

Con le versioni più recenti di Docker per Windows è più facile che mai sviluppare applicazioni Docker, perché il programma di installazione è semplice, come spiegato nei riferimenti seguenti.

> [!TIP]
> Per altre informazioni sull'installazione di Docker per Windows, vedere (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio-2017"></a>Supporto di Docker in Visual Studio 2017

Esistono due livelli di supporto di Docker che possono essere aggiunti a un progetto. Nei progetti ASP.NET Core è possibile aggiungere solo un file `Dockerfile` al progetto abilitando il supporto di Docker. Il livello successivo è il supporto dell'orchestrazione dei contenitori, che aggiunge un `Dockerfile` al progetto, se non esiste già, e un file `docker-compose.yml` a livello della soluzione. Il supporto dell'orchestrazione dei contenitori tramite Docker Compose viene aggiunto automaticamente in Visual Studio 2017 dalla versione 15.0 alla versione 15.7. Il supporto dell'orchestrazione dei contenitori è una funzionalità che prevede il consenso esplicito in Visual Studio 2017 versione 15.8 e successive. Le versioni 15.8 e successive supportano Docker Compose e Service Fabric.

I comandi **Aggiungi > Supporto Docker** e **Aggiungi > Supporto per l'agente di orchestrazione del contenitore** sono disponibili nel menu di scelta rapida del nodo di progetto per un progetto ASP.NET Core in **Esplora soluzioni**, come illustrato nella figura 4-31:

![Opzione di menu Aggiungi Supporto Docker in Visual Studio](./media/add-docker-support-menu.png)

**Figura 4-31**. Aggiunta del supporto di Docker a un progetto di Visual Studio 2017

### <a name="add-docker-support"></a>Aggiungere il supporto di Docker

È possibile aggiungere il supporto Docker a un progetto ASP.NET Core esistente selezionando **Aggiungi** > **supporto Docker** in **Esplora soluzioni**. È anche possibile abilitare il supporto di Docker durante la creazione del progetto selezionando **Abilita supporto Docker** nella finestra di dialogo **Nuova applicazione Web ASP.NET Core** visualizzata dopo aver fatto clic su **OK** nella finestra di dialogo **Nuovo progetto**, come illustrato nella figura 4-32.

![Abilitare il supporto di Docker per la nuova app Web ASP.NET Core in Visual Studio](./media/enable-docker-support-visual-studio.png)

**Figura 4-32**. Abilitare il supporto di Docker durante la creazione del progetto in Visual Studio 2017

Quando si aggiunge o si abilita il supporto di Docker, Visual Studio aggiunge un file *Dockerfile* al progetto.

> [!NOTE]
> Quando si abilita il supporto di Docker Compose durante la creazione del progetto per un progetto ASP.NET (.NET Framework, non un progetto .NET Core), come illustrato nella figura 4-33, viene aggiunto anche il supporto dell'orchestrazione dei contenitori.

![Abilitare il supporto di Docker Compose per un progetto ASP.NET](media/enable-docker-compose-support.png)

**Figura 4-33**. Abilitare il supporto di Docker Compose per un progetto ASP.NET in Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Aggiungere il supporto dell'orchestrazione dei contenitori

Quando si vuole comporre una soluzione con più contenitori, aggiungere il supporto dell'orchestrazione dei contenitori ai progetti. Ciò consente di eseguire un gruppo di contenitori (un'intera soluzione) e di eseguirne il debug contemporaneamente, se sono definiti nello stesso file *docker-compose.yml*.

Per aggiungere il supporto dell'orchestrazione dei contenitori, fare clic con il pulsante destro del mouse sul nodo della soluzione o del progetto in **Esplora soluzioni** e scegliere **Aggiungi > Container Orchestration Support (Supporto dell'orchestrazione dei contenitori)**. Scegliere quindi **Docker Compose** o **Service Fabric** per gestire i contenitori.

Dopo aver aggiunto il supporto dell'orchestrazione dei contenitori al progetto, si noteranno un Dockerfile aggiunto al progetto e una cartella **docker-compose** aggiunta alla soluzione in **Esplora soluzioni**, come illustrato nella figura 4-34:

![File di Docker in Esplora soluzioni in Visual Studio](media/docker-support-solution-explorer.png)

**Figura 4-34**. File di Docker in Esplora soluzioni in Visual Studio 2017

Se il file *docker-compose.yml* esiste già, Visual Studio aggiunge solo le righe del codice di configurazione necessarie in tale file.

## <a name="configure-docker-tools"></a>Configurare gli strumenti di Docker

Dal menu principale scegliere **Strumenti > Opzioni** ed espandere **Strumenti contenitore > Impostazioni**. Vengono visualizzate le impostazioni degli strumenti contenitore.

![Opzioni degli strumenti Docker di Visual Studio, mostrando: Estrai automaticamente le immagini Docker necessarie al caricamento del progetto, Avvia automaticamente i contenitori in background, Uccidi automaticamente i contenitori alla chiusura della soluzione e Non richiedere l'attendibilità del certificato SSL.](./media/visual-studio-docker-tools-options.png)

**Figura 4-35**. Opzioni degli strumenti di Docker

La tabella seguente può essere utile per decidere come impostare queste opzioni.

| Nome | Impostazione predefinita | Si applica a | Descrizione |
| -----|:---------------:|:----------:| ----------- |
| Pull automatico delle immagini Docker richieste al caricamento del progetto | Attivato | Modello di Docker Compose | Per ottenere migliori prestazioni durante il caricamento dei progetti, Visual Studio avvierà un'operazione di pull automatico di Docker in modo che quando si è pronti per eseguire il codice l'immagine sia già stata scaricata o in fase di download. Se si stanno semplicemente caricando progetti ed esplorando codice, è possibile disattivare questa opzione per evitare che vengano scaricate immagini del contenitore non necessarie. |
| Avvia automaticamente i contenitori in background | Attivato | Modello di Docker Compose | Sempre per ottenere migliori prestazioni, Visual Studio crea un contenitore con punti di montaggio di volume pronti per quando viene compilato ed eseguito il contenitore. Se si vuole controllare quando viene creato il contenitore, disattivare questa opzione. |
| Termina automaticamente i contenitori alla chiusura della soluzione | Attivato | Modello di Docker Compose | Disattivare questa opzione se si vuole che i contenitori della soluzione continuino a essere eseguiti dopo la chiusura della soluzione o di Visual Studio. |
| Non chiedere di considerare attendibile il certificato SSL per localhost | Disattivato | Progetti ASP.NET Core 2.2 | Se il certificato SSL per localhost non è attendibile, Visual Studio lo richiederà ogni volta che si eseguirà il progetto, a meno che questa casella di controllo non sia selezionata. |

> [!WARNING]
> Se il certificato SSL per localhost non è attendibile e si seleziona la casella di controllo per eliminare la richiesta, le richieste Web HTTPS potrebbero non riuscire in fase di esecuzione nell'app o nel servizio. In questo caso, deselezionare la casella di controllo **Non chiedere**, eseguire il progetto e indicare l'attendibilità al prompt.

> [!TIP]
> Per altri dettagli sull'implementazione dei servizi e l'uso di Visual Studio Tools per Docker, vedere gli articoli seguenti:
>
>Debug delle applicazioni in un contenitore Docker locale: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>Distribuire un contenitore ASP.NET in un registro contenitori con Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[Successivo](docker-apps-inner-loop-workflow.md)
>[precedente](set-up-windows-containers-with-powershell.md)
