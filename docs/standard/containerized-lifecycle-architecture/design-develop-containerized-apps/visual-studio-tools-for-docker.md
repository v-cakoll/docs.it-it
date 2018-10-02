---
title: Visual Studio Tools per Docker in Windows
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: 7daac744238feb38358e4cc0ab185e90257aa98d
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2018
ms.locfileid: "48027455"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Uso di Visual Studio Tools per Docker (Visual Studio in Windows)

Visual Studio Tools per flusso di lavoro sviluppo di Docker è simile al flusso di lavoro quando si usa Visual Studio Code e CLI di Docker. Infatti, si basa la CLI di Docker stesso, ma è più semplice iniziare, semplifica il processo e fornisce una maggiore produttività per la compilazione, esecuzione e la composizione di attività. Eseguire e il debug dei contenitori tramite semplici azioni, ad esempio **F5** e **Ctrl**+**F5**. Con il supporto di orchestrazione contenitore facoltativo, oltre a essere in grado di eseguire ed eseguire il debug di un singolo contenitore, è possibile eseguire ed eseguire il debug di un gruppo di contenitori (un'intera soluzione) nello stesso momento.

> [!NOTE]
> Questo articolo si applica a Visual Studio in Windows e non in Visual Studio per Mac.

## <a name="configure-your-local-environment"></a>Configurare l'ambiente locale

Con le versioni più recenti di Docker per Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), il programma di installazione semplice semplifica lo sviluppo di applicazioni di Docker.

Supporto per docker è incluso in Visual Studio 2017. Scaricare Visual Studio 2017 di seguito: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>Usare gli strumenti di Docker in Visual Studio 2017

Esistono due livelli di supporto di Docker che è possibile aggiungere a un progetto. Nei progetti di app web .NET Core, puoi semplicemente aggiungere una *Dockerfile* file per il progetto dall'abilitazione del supporto Docker. Il livello successivo è il supporto di orchestrazione contenitore, che aggiunge un *Dockerfile* al progetto (se non esiste già) e una *docker-Compose. yml* file a livello di soluzione. Viene aggiunto il supporto di orchestrazione contenitore, tramite Docker Compose, per impostazione predefinita nelle versioni di Visual Studio 2017 15.7 o versioni precedenti. Supporto di orchestrazione di contenitori è una funzionalità che prevede il consenso esplicito nelle versioni di Visual Studio 2017 15.8 o in un secondo momento, nel qual caso Docker Compose e Service Fabric sono supportati.

Il **Add** > **supporto Docker** e **Add** > **orchestrazione dei contenitori supporto** sono comandi il menu di scelta rapida (o menu di scelta rapida) del nodo di progetto per un progetto di app web nello **Esplora soluzioni**, come illustrato nella figura 4-26:

![Aggiungere l'opzione di menu supporto Docker in Visual Studio](media/add-docker-support-menu.png)

Figura 4-26: aggiunta del supporto Docker a un progetto di Visual Studio 2017

### <a name="add-docker-support"></a>Aggiungi supporto Docker

È possibile aggiungere il supporto Docker a un progetto di app web .NET Core esistente selezionando **Add** > **supporto Docker** nella **Esplora**. È anche possibile abilitare il supporto di Docker durante la creazione del progetto selezionando **Abilita supporto Docker** nel **nuova applicazione Web di ASP.NET Core** la finestra di dialogo visualizzata dopo aver fatto clic **OK** nella **nuovo progetto** finestra di dialogo, come illustrato nella figura 4-27.

![Abilitare il supporto di Docker per la nuova app web ASP.NET Core in Visual Studio](./media/enable-docker-support-visual-studio.png)

Figura 4-27: abilitare il supporto Docker durante la creazione del progetto in Visual Studio 2017

Quando si aggiungono o si abilita supporto per Docker, Visual Studio aggiunge un *Dockerfile* file al progetto.

> [!NOTE]
> Quando si abilita il supporto di Docker Compose durante la creazione del progetto per un progetto di app web di .NET Framework (non un progetto .NET Core web app) come illustrato nella figura 4-28, viene inoltre aggiunto il supporto di orchestrazione di contenitori.
>
> ![Abilitare Docker compose di supporto per un progetto di app web di .NET Framework](media/enable-docker-compose-support.png)

> Figura 4-28: attivazione del supporto per Docker Compose in un progetto di app web di .NET Framework in Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Aggiungere il supporto di orchestrazione di contenitori

Quando si desidera comporre una soluzione multicontenitore, aggiungere il supporto di orchestrazione contenitore per i progetti. Ciò consente di eseguire ed eseguire il debug di un gruppo di contenitori (un'intera soluzione) nello stesso momento, se sono definiti nello stesso *docker-Compose. yml* file.

Per aggiungere il supporto di orchestrazione di contenitori, pulsante destro del mouse sul nodo soluzione o progetto in **Esplora soluzioni**, scegliere **Add** > **contenitore orchestrazione supporta**. Quindi scegliere **Docker Compose** oppure **Service Fabric** per gestire i contenitori.

Dopo aver aggiunto il supporto di orchestrazione contenitore al progetto, viene visualizzato un file Docker aggiunti al progetto e un **docker-compose** aggiunto alla soluzione nella cartella **Esplora soluzioni**, come illustrato nella figura 4-29:

![File di docker in Esplora soluzioni in Visual Studio](media/docker-support-solution-explorer.png)

Figura 4-29: file di Docker in Esplora soluzioni in Visual Studio 2017

Se *docker-Compose. yml* esiste già, Visual Studio aggiunge solo le righe di codice di configurazione necessarie a esso.

**Altre informazioni:** per altri dettagli sull'implementazione di servizi e l'uso di Visual Studio Tools per Docker, leggere gli articoli seguenti:

Compilare, eseguire il debug, aggiornare e aggiornare le App in un contenitore Docker locale: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Distribuire un contenitore Docker ASP.NET Core in un registro contenitori: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Precedente](docker-apps-inner-loop-workflow.md)
[Successivo](set-up-windows-containers-with-powershell.md)