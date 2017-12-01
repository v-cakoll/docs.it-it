---
title: Con Visual Studio Tools per Docker (Visual Studio in Windows)
description: Ciclo di vita dell'applicazione nei contenitori Docker con strumenti e piattaforma Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d7a24633f5857bc5b72ebab42020627c645f4302
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2017
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Con Visual Studio Tools per Docker (Visual Studio in Windows)

Il flusso di lavoro di sviluppo quando si utilizza Visual Studio Tools per Docker è simile al flusso di lavoro quando si utilizza codice di Visual Studio e Docker CLI (in realtà, cui si basa la stessa di Docker CLI), ma è più facile iniziare, semplifica il processo e offre una maggiore produttività per la compilazione, esecuzione e la composizione di attività. È inoltre in grado di eseguire ed eseguire il debug ai contenitori tramite azioni semplici, ad esempio F5 e Ctrl + F5 da Visual Studio. Ancora più efficace, con 2017 di Visual Studio, oltre alla possibilità di esecuzione e il debug di un singolo contenitore, è anche possibile eseguire e il debug di un gruppo di contenitori (una soluzione completa) nello stesso momento se sono definiti nello stesso file docker compose.yml a livello di soluzione.

## <a name="configuring-your-local-environment"></a>Configurazione dell'ambiente locale

Con le versioni più recenti di Docker per Windows, è più semplice che mai, per sviluppare applicazioni di Docker poiché il programma di installazione è semplice, come illustrato nei riferimenti ai seguenti.

**Altre informazioni:** per ulteriori informazioni sull'installazione di Docker per Windows, passare a <https://docs.docker.com/docker-for-windows/>.

Se si utilizza Visual Studio 2015, è necessario disporre di Update 3 o versione successiva con Visual Studio Tools per Docker.

**Altre informazioni:** per istruzioni sull'installazione di Visual Studio, visitare [https://www.visualstudio.com/ \ edizioni dei prodotti/Visual Studio-2015-prodotto](https://www.visualstudio.com/products/vs-2015-product-editions).

Per visualizzare ulteriori informazioni sull'installazione di Visual Studio Tools per Docker, passare a <http://aka.ms/vstoolsfordocker> e <https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.

Se si utilizza Visual Studio 2017, il supporto di Docker è già incluso.

## <a name="using-docker-tools-in-visual-studio-2015"></a>Utilizzando gli strumenti di Docker in Visual Studio 2015

Visual Studio Tools per Docker offre un sistema coerente per sviluppare e convalidare i ai contenitori di Docker in locale per Linux in un host Linux Docker o macchina virtuale o i contenitori di Windows direttamente in Windows.

Se si usa un singolo contenitore, la prima cosa che occorre per iniziare è per attivare il supporto di Docker nel progetto .NET Core. A tale scopo, fare clic sul file di progetto, come illustrato nella figura 4-25.

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/Image/file/205468/1/Add-docker-Support.PNG](./media/image31.png)

Figura 4-25: l'attivazione del supporto di Docker per il progetto di Visual Studio

## <a name="using-docker-tools-in-visual-studio-2017"></a>Utilizzando gli strumenti di Docker in Visual Studio 2017

Quando si aggiunge il supporto di Docker per un progetto di servizio nella soluzione (vedere Figura 4-26), Visual Studio è non appena aggiunta di un DockerFile file al progetto, anche aggiunge una sezione di servizio per la soluzione docker compose.yml file (o creare i file se non sono esistere). È un modo semplice per iniziare la composizione della soluzione multicontainer; è quindi possibile aprire i file di docker compose.yml e aggiornarli con funzionalità aggiuntive.

![](./media/image32.png)

Figura 4-26: l'attivazione del supporto di soluzioni di Docker in un progetto di Visual Studio 2017

Questa azione aggiunge non solo DockerFile al progetto, aggiunge anche le righe di configurazione necessarie di codice per un globale compose.yml docker impostato a livello di soluzione.

È anche possibile attivare il supporto di Docker quando si crea un progetto ASP.NET Core in Visual Studio 2017, come illustrato nella figura 4-27.

![](./media/image33.png)

Figura 4-27: l'attivazione del supporto di Docker durante la creazione di un progetto

Dopo aver aggiunto il supporto di Docker per la soluzione in Visual Studio, è inoltre verrà visualizzato un nuovo albero di nodi in Esplora soluzioni con i file aggiunti docker-compose.yml, come illustrato nella figura 4-28.

![](./media/image34.PNG)

Figura 4-28: file compose.yml di docker è ora visualizzato in Esplora soluzioni

È possibile distribuire un multicontainer applicazione utilizzando un file di docker-compose.yml solo quando si esegue docker-comporre; Tuttavia, Visual Studio aggiunge un gruppo di elementi, in modo è possibile eseguire l'override di valori a seconda dell'ambiente (sviluppo e produzione) e l'esecuzione del tipo (release e debug). Questa funzionalità verrà spiegata meglio nei capitoli successivi.

**Altre informazioni:** per ulteriori informazioni sull'implementazione di servizi e l'utilizzo di Visual Studio Tools per Docker, leggere gli articoli seguenti:

Compilare, eseguire il debug, aggiornare e aggiornare le App in un contenitore Docker locale: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Distribuire un contenitore ASP.NET in un host Docker remoto: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)


>[!div class="step-by-step"]
[Precedente] (docker-App-interna-loop-workflow.md) [Avanti] (set-up-windows-containers-with-powershell.md)
