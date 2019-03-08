---
title: Visual Studio Tools per Docker in Windows
description: Conoscere gli strumenti di Docker disponibili in Visual Studio 2017 versione 15.7 e successive.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 78ea3e553e4e449b307bc3585ed66fa48d2c0d8e
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57680360"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>Usare gli strumenti di Docker in Visual Studio 2017 in Windows

Il flusso di lavoro per gli sviluppatori quando si usano gli strumenti di Docker inclusi in Visual Studio 2017 versione 15.7 e successive, è simile all'uso di Visual Studio Code e CLI di Docker (infatti, si basa la CLI di Docker stesso), ma è più semplice iniziare, semplifica il processo, e offre una maggiore produttività per la compilazione, esecuzione e la composizione di attività. Può anche eseguire e il debug dei contenitori tramite la consueta `F5` e `Ctrl+F5` chiavi da Visual Studio. Eseguire il debug di un'intera soluzione anche se i contenitori sono definiti nello stesso `docker-compose.yml` file a livello di soluzione.

## <a name="configure-your-local-environment"></a>Configurare l'ambiente locale

Con le versioni più recenti di Docker per Windows, è più facile che mai, per sviluppare applicazioni Docker perché il programma di installazione è semplice, come spiegato nei riferimenti ai seguenti.

> [! INFORMAZIONI] per altre informazioni sull'installazione di Docker per Windows, passare a (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio-2017"></a>Supporto docker in Visual Studio 2017

Esistono due livelli di supporto di Docker che è possibile aggiungere a un progetto. Nei progetti ASP.NET Core, è possibile aggiungere solo un `Dockerfile` file per il progetto dall'abilitazione del supporto Docker. Il livello successivo è il supporto di orchestrazione contenitore, che aggiunge un `Dockerfile` al progetto (se non esiste già) e un `docker-compose.yml` file a livello di soluzione. Viene aggiunto il supporto di orchestrazione contenitore, tramite Docker Compose, per impostazione predefinita in Visual Studio 2017 versioni 15.0 alla versione 15.7. Supporto di orchestrazione di contenitori è una funzionalità che prevede il consenso esplicito nelle versioni di Visual Studio 2017 15,8 o versione successive. Versione 15.8 un oggetto in un secondo momento il supporto Docker Compose e Service Fabric.

Il **Aggiungi > supporto Docker** e **Aggiungi > supporto dell'agente di orchestrazione dei contenitori** comandi si trovano nel menu di scelta rapida (o menu di scelta rapida) del nodo di progetto per un progetto ASP.NET Core in  **Esplora soluzioni**, come illustrato nella figura 4-31:

![Aggiungere l'opzione di menu supporto Docker in Visual Studio](./media/add-docker-support-menu.png)

**Figura 4-31**. Aggiunta del supporto Docker a un progetto di Visual Studio 2017

### <a name="add-docker-support"></a>Aggiungi supporto Docker

È possibile aggiungere il supporto Docker a un progetto ASP.NET Core esistente selezionando **Add** > **supporto Docker** nella **Esplora**. È anche possibile abilitare il supporto di Docker durante la creazione del progetto selezionando **Abilita supporto Docker** nel **nuova applicazione Web di ASP.NET Core** la finestra di dialogo visualizzata dopo aver fatto clic **OK** nella **nuovo progetto** finestra di dialogo, come illustrato nella figura 4-32.

![Abilitare il supporto di Docker per la nuova app web ASP.NET Core in Visual Studio](./media/enable-docker-support-visual-studio.png)

**Figura 4-32**. Abilitare il supporto Docker durante la creazione del progetto in Visual Studio 2017

Quando si aggiungono o si abilita supporto per Docker, Visual Studio aggiunge un *Dockerfile* file al progetto.

> [!NOTE]
> Quando si abilita supporto Docker Compose, durante la creazione del progetto per un progetto ASP.NET (.NET Framework, non a un progetto .NET Core), come illustrato nella figura 4-33, viene inoltre aggiunto il supporto di orchestrazione di contenitori.

![Abilitare Docker compose di supporto per un progetto ASP.NET](media/enable-docker-compose-support.png)

**Figura 4-33**. Attivazione del supporto per Docker Compose per un progetto ASP.NET in Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Aggiungere il supporto di orchestrazione di contenitori

Quando si desidera comporre una soluzione multi-contenitore, aggiungere il supporto di orchestrazione contenitore per i progetti. Ciò consente di eseguire ed eseguire il debug di un gruppo di contenitori (un'intera soluzione) nello stesso momento, se sono definiti nello stesso *docker-Compose. yml* file.

Per aggiungere il supporto di orchestrazione di contenitori, pulsante destro del mouse sul nodo soluzione o progetto in **Esplora soluzioni**, scegliere **Aggiungi > supporto di orchestrazione contenitore**. Quindi scegliere **Docker Compose** oppure **Service Fabric** per gestire i contenitori.

Dopo aver aggiunto il supporto di orchestrazione contenitore al progetto, viene visualizzato un file Docker aggiunti al progetto e un **docker-compose** aggiunto alla soluzione nella cartella **Esplora soluzioni**, come illustrato nella figura 4-34:

![File di docker in Esplora soluzioni in Visual Studio](media/docker-support-solution-explorer.png)

**Figura 4-34**. File di docker in Esplora soluzioni in Visual Studio 2017

Se *docker-Compose. yml* esiste già, Visual Studio aggiunge solo le righe di codice di configurazione necessarie a esso.

## <a name="configure-docker-tools"></a>Configurare gli strumenti di Docker

Dal menu principale scegliere **strumenti > Opzioni**, espandere **Container Tools > Impostazioni**. Le impostazioni di strumenti contenitore vengono visualizzate.

![Docker in Visual Studio degli strumenti, opzioni di visualizzazione: Automaticamente il pull delle immagini Docker richiesto nel caricamento del progetto, avvia automaticamente i contenitori in background, terminare automaticamente i contenitori in Chiudi soluzione e non chiedere conferma per considerare attendibile il certificato SSL.](./media/visual-studio-docker-tools-options.png)

**Figura 4-35**. Opzioni per gli strumenti di docker

Nella tabella seguente consente di decidere come impostare queste opzioni.

| nome | Impostazione predefinita | Si applica a | Descrizione |
| -----|:---------------:|:----------:| ----------- |
| Automaticamente il pull delle immagini Docker richiesto nel caricamento del progetto | Attivato | Docker Compose | Per ottenere migliori prestazioni durante il caricamento dei progetti, Visual Studio verrà avviato un'operazione di pull di Docker in background in modo che quando si è pronti per eseguire il codice, l'immagine è già stato scaricato o in fase di download. Se si sta semplicemente il caricamento di progetti e codice di esplorazione, è possibile disattivare questa funzionalità per evitare il download delle immagini del contenitore che non è necessario. |
| Avvia automaticamente i contenitori in background | Attivato | Docker Compose | Anche in questo caso per ottenere migliori prestazioni, Visual Studio crea un contenitore con punti di montaggio di volume pronti per quando viene compilato ed eseguito nel contenitore. Se si desidera controllare quando viene creato il contenitore, è possibile disattivare questa funzionalità. |
| Chiudono automaticamente i contenitori kill sulla soluzione | Attivato | Docker Compose | Disattivare questa funzionalità se si vuole contenitori per la soluzione continuare a eseguire dopo la chiusura della soluzione o chiusura di Visual Studio. |
| Non chiedere conferma per considerare attendibile il certificato SSL localhost | Disattivato | Progetti ASP.NET Core 2.1 | Se il certificato SSL localhost non è attendibile, Visual Studio richiederà ogni volta che si esegue il progetto, a meno che non è selezionata questa casella di controllo. |

> [!WARNING]
> Se non è attendibile il certificato SSL localhost e si seleziona la casella per eliminare la richiesta, richieste web HTTPS potrebbero non riuscire in fase di esecuzione nell'app o nel servizio. In tal caso, deselezionare il **non chiedere conferma** casella di controllo, eseguire il progetto e indicare attendibilità al prompt.

> [! INFORMAZIONI] per altri dettagli sull'implementazione di servizi e l'uso di Visual Studio Tools per Docker, leggere gli articoli seguenti:
>
>Debug di App in un contenitore Docker locale: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>Distribuire un contenitore ASP.NET in un registro contenitori con Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[Precedente](docker-apps-inner-loop-workflow.md)
>[Successivo](set-up-windows-containers-with-powershell.md)
