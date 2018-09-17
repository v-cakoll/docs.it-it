---
title: Uso di Visual Studio Tools per Docker (Visual Studio in Windows)
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: af14c92ab27885deec878dc33e7b94035f43e65b
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2018
ms.locfileid: "45743827"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Uso di Visual Studio Tools per Docker (Visual Studio in Windows)

Il flusso di lavoro di sviluppo quando si usa Visual Studio Tools per Docker è simile al flusso di lavoro quando si usa Visual Studio Code e CLI di Docker. Infatti, si basa la CLI di Docker stesso, ma è più semplice iniziare, semplifica il processo e fornisce una maggiore produttività per la compilazione, esecuzione e la composizione di attività. È anche possibile eseguire e il debug dei contenitori tramite semplici azioni, ad esempio F5 e Ctrl + F5 da Visual Studio. Con il supporto di orchestrazione contenitore facoltativo, oltre a essere in grado di eseguire ed eseguire il debug di un singolo contenitore, è possibile eseguire ed eseguire il debug di un gruppo di contenitori (un'intera soluzione) nello stesso momento. Definire solo i contenitori nella stessa *docker-Compose. yml* file a livello di soluzione.

## <a name="configuring-your-local-environment"></a>Configurazione dell'ambiente locale

Supporto per docker è incluso in Visual Studio 2017 con uno qualsiasi dei carichi di lavoro .NET e .NET Core installati. Installare Docker per Windows separatamente.

Con le versioni più recenti di Docker per Windows, è più facile che mai, per sviluppare applicazioni Docker perché il programma di installazione è semplice, come spiegato nei riferimenti ai seguenti.

**Altre informazioni:** per altre informazioni sull'installazione di Docker per Windows, passare a <https://docs.docker.com/docker-for-windows/>.

**Altre informazioni:** per istruzioni sull'installazione di Visual Studio, passare alla [ https://visualstudio.microsoft.com/downloads/ ](https://visualstudio.microsoft.com/downloads/).

Per visualizzare altre informazioni sull'installazione di Visual Studio Tools per Docker, passare a <http://aka.ms/vstoolsfordocker> e <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.

## <a name="using-docker-tools-in-visual-studio-2017"></a>Usando gli strumenti di Docker in Visual Studio 2017

Quando si aggiunge il supporto Docker a un progetto (vedere Figura 4-26), Visual Studio aggiunge un *Dockerfile* alla radice del progetto.

![Attivazione del supporto di soluzione Docker in un progetto di Visual Studio 2017](./media/image32.png)

Figura 4-26: attivazione del supporto di soluzione Docker in un progetto di Visual Studio 2017

 Viene aggiunto il supporto di orchestrazione contenitore, tramite Docker Compose, per impostazione predefinita nelle versioni di Visual Studio 2017 15.7 o versioni precedenti. Supporto di orchestrazione di contenitori è una funzionalità che prevede il consenso esplicito nelle versioni di Visual Studio 2017 15.8 o in un secondo momento, nel qual caso Docker Compose e Service Fabric sono supportati.

Con Visual Studio versione 15,8 e versioni successive, è possibile aggiungere il supporto per più progetti in una soluzione che dispongono di un contenitore associato. Pulsante destro del mouse sul nodo soluzione o progetto in **Esplora soluzioni**, scegliere **Add** > **supporto orchestrazione dei contenitori**.  Quindi scegliere **Docker Compose** oppure **Service Fabric** per gestire i contenitori.

Quando si sceglie **Docker Compose**, Visual Studio aggiunge una sezione di servizio all'interno della soluzione *docker-Compose. yml* file (o crea i file se non esistono). È un modo semplice per iniziare a comporre alla soluzione multi-contenitore. è quindi possibile aprire il *docker-Compose. yml* file e aggiornarli con funzionalità aggiuntive.

Questa azione aggiunge la configurazione necessarie righe di codice per un *docker-Compose. yml* impostato a livello di soluzione.

È anche possibile attivare il supporto Docker quando si crea un progetto ASP.NET Core in Visual Studio 2017, come illustrato nella figura 4-27.

![Attivazione del supporto Docker quando si crea un progetto](./media/image33.png)

Figura 4-27: attivazione del supporto Docker quando si crea un progetto

Dopo aver aggiunto il supporto Docker alla soluzione in Visual Studio, anche verrà visualizzato un nuovo albero di nodi in **Esplora soluzioni** con l'aggiunta *docker-Compose. yml* file, come illustrato nella figura 4-28.

![i file docker-Compose. yml ora visualizzano in Esplora soluzioni](./media/image34.PNG)

Figura 4-28: i file docker-Compose. yml ora visualizzano nel **Esplora soluzioni**

È possibile distribuire un'app multi-contenitore tramite una singola *docker-Compose. yml* durante l'esecuzione di file `docker-compose up`; tuttavia, Visual Studio aggiunge un gruppo di essi, in modo che è possibile eseguire l'override di valori a seconda dell'ambiente (sviluppo di applicazioni rispetto a ambiente di produzione) e l'esecuzione del tipo (release o debug). Questa funzionalità viene spiegata meglio nei capitoli successivi.

È anche possibile usare Service Fabric invece di Docker Compose per la gestione di più contenitori. Visualizzare [esercitazione: distribuire un'applicazione .NET in un contenitore Windows in Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container).

**Altre informazioni:** per altri dettagli sull'implementazione di servizi e l'uso di Visual Studio Tools per Docker, leggere gli articoli seguenti:

Compilare, eseguire il debug, aggiornare e aggiornare le App in un contenitore Docker locale: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Distribuire un contenitore Docker ASP.NET Core in un registro contenitori: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Precedente](docker-apps-inner-loop-workflow.md)
[Successivo](set-up-windows-containers-with-powershell.md)
