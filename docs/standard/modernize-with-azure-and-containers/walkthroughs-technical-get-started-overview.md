---
title: Procedure dettagliate e technical Panoramica avviata
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows | procedure dettagliate e technical Panoramica avviata
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: e78dd4a324ca9fc973f1aa0d8e6a9abe1341876c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Procedure dettagliate e technical Panoramica avviata 

Per limitare le dimensioni di questo manuale e, sono stati apportati documentazione tecnica aggiuntiva e le procedure dettagliate di complete disponibile in un repository di GitHub. La serie in linea di procedure dettagliate in cui sono descritto in questo capitolo descrive la procedura di configurazione di più ambienti basati su contenitori di Windows e la distribuzione in Azure.

Le sezioni seguenti illustrano ciò che ogni procedura dettagliata è sui relativi obiettivi, la visione generale- e fornisce un diagramma di attività che sono coinvolti. È possibile ottenere le procedure dettagliate autonomamente nel *eShopModernizing* wiki repository GitHub di App in [https://github.com/dotnet-architecture/eShopModernizing/wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki).

# <a name="technical-walkthrough-list"></a>Elenco di istruzioni dettagliate

Le procedure dettagliate seguenti avviato get forniscono linee guida tecnica completa e coerenza per le app di esempio che è possibile sollevare e spostare usando i contenitori e quindi spostare utilizzando più opzioni di distribuzione in Azure.

Ognuna delle procedure dettagliate seguenti utilizza il nuovo esempio eShopLegacy eShopModernizing le App e quali sono disponibili in GitHub all'indirizzo [https://github.com/dotnet-architecture/eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

-   **Presentazione dell'App legacy eShop**

-   **Le applicazioni .NET esistenti con i contenitori di Windows inserita in un contenitore**

-   **Distribuire l'app basata su contenitori di Windows in macchine virtuali di Azure**

-   **Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di Azure**

-   **Distribuire le app basate su contenitori di Windows Azure Service Fabric**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Procedura dettagliata 1: Panoramica delle applicazioni legacy eShop

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata tecniche disponibilità

Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/01.-tour-on-eShopModernizing-Apps-Implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

### <a name="overview"></a>Panoramica

In questa procedura dettagliata, è possibile esplorare l'implementazione iniziale due applicazioni di esempio legacy. Entrambe le app di esempio dispone di un'architettura monolitica e sono state create tramite ASP.NET classico. Un'applicazione basata su ASP.NET 4. x MVC; la seconda applicazione è basata su Web Form ASP.NET 4. x. Entrambe le applicazioni presenti il [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

È possibile inserita in un contenitore entrambe le app di esempio, simile al modo in cui è possibile inserita in un contenitore un classico [Windows Communication Foundation](https://docs.microsoft.com/dotnet/framework/wcf/whats-wcf) applicazione (WCF) deve essere utilizzato come un'applicazione desktop. Per un esempio, vedere [eShopModernizingWCFWinForms](https://github.com/dotnet-architecture/eShopModernizingWCFWinForms).

### <a name="goals"></a>Obiettivi

L'obiettivo principale di questa procedura dettagliata è semplicemente per acquisire familiarità con queste App e con il codice e configurazione. È possibile configurare le App in modo che possano generare e utilizzare dati fittizi, senza l'utilizzo del database SQL, a scopo di test. Questa configurazione facoltativa è basata sul inserimento di dipendenze, in modo separato.

### <a name="scenario"></a>Scenario

Figura 5-1 viene illustrato un semplice scenario di applicazioni legacy originale.

> ![Scenario semplice architettura delle applicazioni legacy originale](./media/image5-1.png)
>
> **Figura 5-1.** Scenario semplice architettura delle applicazioni legacy originale

Da una prospettiva di dominio aziendale, entrambe le app offrono lo stesso catalogo le funzionalità di gestione. I membri del team enterprise eShop utilizzerebbe l'app per visualizzare e modificare il catalogo dei prodotti. Figura 5-2 è illustrata la schermata iniziale di app.

![Applicazioni ASP.NET MVC e Web Form ASP.NET (le tecnologie esistenti/legacy)](./media/image5-2.png)

> **Figura 5-2.** Applicazioni ASP.NET MVC e Web Form ASP.NET (le tecnologie esistenti/legacy)

Si tratta di applicazioni web che consentono di esplorare e modificare le voci di catalogo. Il fatto che entrambe le app offrono le stesse funzionalità di business funzionali è sufficiente per il confronto. È possibile visualizzare un processo di modernizzazione simile per le app che sono state create tramite il framework ASP.NET MVC e Web Form ASP.NET.

Le dipendenze in ASP.NET 4. x o versioni precedenti (per MVC o Web Form) significa che queste applicazioni non verranno eseguito su .NET Core, a meno che il codice è completamente riscritto utilizzando ASP.NET MVC di base. Viene descritto il punto che se non si desidera progettare nuovamente o riscrivere il codice, è possibile inserita in un contenitore applicazioni esistenti e continuare a usare le stesse tecnologie .NET e lo stesso codice. È possibile vedere come è possibile eseguire applicazioni come questi contenitori, senza apportare modifiche al codice legacy.

### <a name="benefits"></a>Vantaggi

I vantaggi di questa procedura dettagliata sono semplici: semplicemente acquisire familiarità con la configurazione di codice e l'applicazione, in base a inserimento di dipendenze. Quindi, è possibile provare a utilizzare questo approccio quando è inserita in un contenitore e distribuire in più ambienti in futuro.

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/01.-tour-on-eShopModernizing-Apps-Implementation-code](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-eShopModernizing-apps-implementation-code)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Procedura dettagliata 2: Inserita in un contenitore le applicazioni .NET esistenti con i contenitori di Windows

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata tecniche disponibilità

Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/02.-How-to-containerized-the-.NET-Framework-Web-Apps-with-Windows-Containers-and-Docker](https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-DockerTBD)

### <a name="overview"></a>Panoramica

Utilizzare i contenitori di Windows per migliorare la distribuzione di applicazioni .NET esistenti, ad esempio quelle basate su WCF, MVC o Web Form per gli ambienti di test, sviluppo e produzione.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è descrivere le diverse opzioni per containerizing un'applicazione esistente di .NET Framework. È possibile:

-   L'applicazione inserita in un contenitore utilizzando [Visual Studio 2017 Tools per Docker](https://docs.microsoft.com/dotnet/core/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versioni successive).

-   L'applicazione inserita in un contenitore aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)e quindi utilizzando il [CLI di Docker](https://docs.docker.com/engine/reference/commandline/cli/).

-   L'applicazione inserita in un contenitore utilizzando il [Img2Docker](https://github.com/docker/communitytools-image2docker-win) strumento (uno strumento open source da Docker).

Questa procedura dettagliata si concentra sugli strumenti di Visual Studio 2017 per approccio Docker, ma gli altri due approcci sono piuttosto simili relativamente all'utilizzo di Dockerfile.

### <a name="scenario"></a>Scenario

Figura 5-3 viene illustrato lo scenario per le applicazioni legacy eShop nei contenitori.

> ![Diagramma dell'architettura semplificata delle applicazioni nei contenitori in un ambiente di sviluppo](./media/image5-3.png)
>
> **Figura 5-3.** Diagramma dell'architettura semplificata delle applicazioni nei contenitori in un ambiente di sviluppo

### <a name="benefits"></a>Vantaggi

Esistono vantaggi rispetto all'esecuzione dell'applicazione monolitica in un contenitore. Creare un'immagine per l'applicazione. Da quel momento in poi, ogni distribuzione viene eseguito nello stesso ambiente. Ogni contenitore Usa la stessa versione del sistema operativo, ha la stessa versione di dipendenze installata, Usa la stessa versione di .NET framework e viene compilato con lo stesso processo. In pratica, controllare le dipendenze dell'applicazione tramite un'immagine di Docker. Quando si distribuiscono i contenitori, le dipendenze viaggiano con l'applicazione.

Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente di coerente fornito dai contenitori di Windows. I problemi che vengono visualizzati solo con alcune versioni possono essere rilevati immediatamente, invece di replica in un ambiente di gestione temporanea o produzione. Differenze in ambienti di sviluppo utilizzati dai membri del team di sviluppo è importante minore quando le applicazioni eseguite nei contenitori.

Le applicazioni nei contenitori hanno anche una curva di scalabilità orizzontale più semplice. Le applicazioni nei contenitori consentono di disporre di altre applicazioni e le istanze del servizio (basate su contenitori) in una macchina virtuale o un computer fisico rispetto alle distribuzioni applicazione regolare per ogni macchina. Questo si traduce in maggiore densità e meno necessarie risorse, soprattutto quando si utilizzano orchestrators come Kubernetes o Service Fabric.

Creazione dei contenitori, in situazioni ideali, non è necessario apportare modifiche al codice dell'applicazione (C\#). Nella maggior parte degli scenari, è necessario solo i file di metadati di distribuzione (file Dockerfile e Docker Compose) Docker.

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub: [https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker](https://https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerized-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Procedura dettagliata 3: Distribuire l'app basata su contenitori di Windows in macchine virtuali di Azure

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata tecniche disponibilità

Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/03.-How-to-deploy-Your-Windows-Containers-based-App-INTO-Azure-VMS-(including-ci-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Panoramica

La distribuzione in un host Docker in una macchina virtuale Windows Server 2016 in Azure consente di configurare rapidamente gli ambienti di sviluppo/test/staging. Offre inoltre una posizione comune per i tester o gli utenti di business convalidare l'app. Macchine virtuali, inoltre, possono essere ambienti di produzione IaaS validi.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è di illustrare le alternative più, che è necessario quando si distribuiscono i contenitori di Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.

### <a name="scenarios"></a>Scenari

In questa procedura dettagliata sono illustrati i diversi scenari.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Scenario a: distribuire una macchina virtuale di Azure da un PC di sviluppo tramite una connessione al motore Docker

![Distribuire in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker](./media/image5-4.png)

> **Figura 5-4.** Distribuire in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Scenario b: distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker

![Distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker](./media/image5-5.png)

> **Figura 5-5.** Distribuire una macchina virtuale di Azure tramite un registro di sistema di Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-visual-studio-team-services"></a>Scenario c: distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services

![Distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services](./media/image5-6.png)

> **Figura 5-6.** Distribuire una macchina virtuale di Azure dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services

### <a name="azure-vms-for-windows-containers"></a>Macchine virtuali di Azure per i contenitori di Windows

Macchine virtuali di Azure per i contenitori di Windows sono semplicemente le macchine virtuali basate su Windows 10, Windows Server 2016 o versioni successive, entrambi con il motore Docker impostare. Nella maggior parte dei casi, utilizzare Windows Server 2016 in macchine virtuali di Azure.

Azure offre attualmente di una macchina virtuale denominata **Windows Server 2016 con contenitori**. È possibile utilizzare questa macchina virtuale per provare la nuova funzionalità di contenitore di Windows Server, con Windows Server Core o Nano Server di Windows. Immagini del sistema operativo contenitore vengono installate e quindi la macchina virtuale è pronta all'uso con Docker.

### <a name="benefits"></a>Vantaggi

Sebbene i contenitori di Windows possono essere distribuiti a macchine virtuali in locale Windows Server 2016, quando si distribuiscono in Azure, è possibile ottenere un modo più semplice per iniziare, con macchine virtuali di contenitore pronto all'uso Windows Server. Anche possibile ottenere un percorso online comune che è accessibile ai tester e la scalabilità automatica tramite il set di scalabilità di macchine Virtuali di Azure.

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/03.-How-to-deploy-Your-Windows-Containers-based-App-INTO-Azure-VMS-(including-ci-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Procedura dettagliata 4: Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di Azure

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata tecniche disponibilità

Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/04.-How-to-deploy-Your-Windows-Containers-based-Apps-INTO-Kubernetes-in-Azure-Container-Service-(including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Panoramica

Un'applicazione che si basa sui contenitori di Windows, rapidamente è necessario utilizzare le piattaforme, spostando ulteriormente da macchine virtuali IaaS. Questo è necessario per ottenere facilmente la scalabilità elevata meglio la scalabilità automatica e per un miglioramento significativo automaticamente le distribuzioni e controllo delle versioni. È possibile raggiungere questi obiettivi tramite l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile in [servizi contenitore Azure](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su contenitore di Windows per Kubernetes (chiamato anche *K8s*) nel servizio contenitore di Azure. La distribuzione in Kubernetes da zero è un processo in due passaggi:

1.  Distribuire un cluster Kubernetes al servizio di contenitore di Azure.

2.  Distribuire l'applicazione e le relative risorse nel cluster Kubernetes.

### <a name="scenarios"></a>Scenari

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Scenario a: distribuire direttamente a un cluster Kubernetes da un ambiente di sviluppo

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo](./media/image5-7.png)

> **Figura 5-7.** Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-team-services"></a>Scenario b: distribuire a un cluster Kubernetes CI/CD pipeline in Team Services

![Distribuire un cluster Kubernetes dalla pipeline CI/CD-ROM in Team Services](./media/image5-8.png)

> **Figura 5-8.** Distribuire un cluster Kubernetes dalla pipeline CI/CD-ROM in Team Services

### <a name="benefits"></a>Vantaggi

Esistono numerosi vantaggi per la distribuzione a un cluster in Kubernetes. Il vantaggio più importante è che si ottiene un ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitori, si desidera utilizzare (scalabilità interna in nodi esistenti) e in base al numero di nodi o le macchine virtuali in (il cluster scalabilità globale del cluster).

Il servizio contenitore di Azure consente di ottimizzare tecnologie e strumenti open source più diffusi in particolare per Azure. È possibile ottenere una soluzione aperta che offre la portabilità, per i contenitori e per la configurazione dell'applicazione. Selezionare la dimensione, il numero di host, e orchestrator strumenti-Container servizio gestisce tutti gli altri elementi.

Con Kubernetes, gli sviluppatori possono sullo stato da considerare macchine fisiche e virtuali, per la pianificazione di un'infrastruttura incentrato sul contenitore che facilita le seguenti funzionalità, tra gli altri:

-   In base a più contenitori di applicazioni

-   La replica delle istanze di contenitori e il ridimensionamento orizzontale

-   Denominazione e individuazione (ad esempio, DNS interno)

-   Bilanciamento del carico

-   Gli aggiornamenti in sequenza

-   Distribuzione di segreti

-   Controlli di integrità dell'applicazione

## <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub: [(https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service- Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Procedura dettagliata 5: Distribuire le app basate su contenitori di Windows Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata tecniche disponibilità

Procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/05.-How-to-deploy-Your-Windows-Containers-based-Apps-INTO-Azure-Service-fabric-(including-ci-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Panoramica

Un'applicazione che si basa sui contenitori di Windows, rapidamente è necessario utilizzare le piattaforme, spostando ulteriormente da macchine virtuali IaaS. Questo è necessario per ottenere facilmente la scalabilità elevata meglio la scalabilità automatica e per un miglioramento significativo automaticamente le distribuzioni e controllo delle versioni. È possibile raggiungere questi obiettivi tramite orchestrator Azure Service Fabric è disponibile nel cloud di Azure, ma è anche disponibile per l'utilizzo di on-premise, o anche in un cloud pubblico diverso.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su Windows contenitore a un cluster di Service Fabric in Azure. Distribuzione di Service Fabric da zero è un processo in due passaggi:

1.  Distribuire un cluster di Service Fabric in Azure (o in un ambiente diverso).

2.  Distribuire l'applicazione e le relative risorse nel cluster di Service Fabric.

### <a name="scenarios"></a>Scenari

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Scenario a: distribuire direttamente a un cluster di Service Fabric da un ambiente di sviluppo

![Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo](./media/image5-9.png)

> **Figura 5-9.** Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-team-services"></a>Scenario b: distribuire a un cluster di Service Fabric dal CI/CD-ROM pipeline in Team Services

![Distribuire un cluster di Service Fabric dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services](./media/image5-10.png)

> **Figura 5-10.** Distribuire un cluster di Service Fabric dalla pipeline/CD degli elementi di configurazione in Visual Studio Team Services

## <a name="benefits"></a>Vantaggi

I vantaggi della distribuzione a un cluster nell'infrastruttura del servizio sono simili ai vantaggi dell'utilizzo Kubernetes. Una differenza, tuttavia, è che Service Fabric è un ambiente di produzione molto avanzata per le applicazioni di Windows rispetto a Kubernetes, che è stato in anteprima per i contenitori di Windows, fino all'inizio fallback di 2017. (Kubernetes è un ambiente più avanzato per Linux). 

Il principale vantaggio dell'utilizzo di Azure Service Fabric è che si dispone di un ambiente di ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitori, si desidera utilizzare (scalabilità interna in nodi esistenti) e in base al numero di i nodi o macchine virtuali in cluster (scalabilità globale del cluster).

Azure Service Fabric offre portabilità per i contenitori e per la configurazione dell'applicazione. È un'infrastruttura del servizio cluster in Azure oppure installarlo in locale nel proprio Data Center. È anche possibile installare un cluster di Service Fabric in un cloud diverso, ad esempio [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

Con Service Fabric, gli sviluppatori possono sullo stato da considerare macchine fisiche e virtuali per la pianificazione di un'infrastruttura incentrato sul contenitore che facilita le seguenti funzionalità, tra gli altri:

-   Applicazioni basate su più contenitori.

-   La replica di istanze di contenitori e scalabilità orizzontale automatica.

-   Denominazione e individuazione (ad esempio, DNS interno).

-   Bilanciamento del carico.

-   Aggiornamenti in sequenza.

-   Distribuire i segreti.

-   Controlla l'integrità dell'applicazione.

Le seguenti funzionalità sono esclusive nell'infrastruttura di servizio (rispetto a altro orchestrators):

-   Funzionalità di servizi con stato, tramite il modello applicazione servizi affidabili.

-   Modello di attori, tramite il modello di applicazione Reliable Actors.

-   Distribuire processi ossa bare, oltre ai contenitori di Windows o Linux.

-   Gli aggiornamenti in sequenza e controlli di integrità avanzati.

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto di informazioni più dettaglio su wiki di GitHub:

[https://github.com/dotnet-Architecture/eShopModernizing/Wiki/05.-How-to-deploy-Your-Windows-Containers-based-Apps-INTO-Azure-Service-fabric-(including-ci-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

>[!div class="step-by-step"]
[Precedente](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
[Successivo](conclusions.md)
