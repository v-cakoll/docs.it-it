---
title: Procedure dettagliate e technical panoramica introduttiva
description: Modernizzare le applicazioni .NET esistenti con Cloud di Azure e i contenitori di Windows | Procedure dettagliate e technical panoramica introduttiva
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: e89f1e79eec16919b2e70952392b6f640433156b
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2019
ms.locfileid: "57846259"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Procedure dettagliate e technical panoramica introduttiva

Per limitare le dimensioni di questo e-book, documentazione tecnica aggiuntiva e le procedure dettagliate complete sono stati resi disponibili in un repository GitHub. La linea serie di procedure dettagliate che sono descritti in questo capitolo descrive la configurazione dettagliata di più ambienti basati su contenitori di Windows e la distribuzione in Azure.

Le sezioni seguenti illustrano ciò che ogni procedura dettagliata sui suoi obiettivi e una visione generale e fornisce un diagramma di attività che sono coinvolti. È possibile ottenere le procedure dettagliate autonomamente nel *eShopModernizing* App wiki di repository GitHub in [ https://github.com/dotnet-architecture/eShopModernizing/wiki ](https://github.com/dotnet-architecture/eShopModernizing/wiki).

## <a name="technical-walkthrough-list"></a>Elenco delle procedure dettagliate tecniche

Procedure dettagliate di introduzione seguenti forniscono indicazioni tecniche completa e coerente per le app di esempio che è possibile sollevare e spostare usando i contenitori e reinserirvi usando più opzioni di distribuzione in Azure.

Ognuna delle procedure dettagliate seguenti utilizza il nuovo esempio eShopLegacy eShopModernizing le App e quali sono disponibili in GitHub all'indirizzo [ https://github.com/dotnet-architecture/eShopModernizing ](https://github.com/dotnet-architecture/eShopModernizing).

- **Panoramica delle App legacy eShop (app linea di base per modernizzare)**

- **Distribuire le app web ASP.NET esistenti (Web Form e MVC) in un contenitore con contenitori Windows**

- **Distribuire i servizi WCF esistenti (App a più livelli) con i contenitori Windows in un contenitore**

- **Distribuire l'app basata su contenitori Windows in macchine virtuali di Azure**

- **Distribuire le app di Windows basata su contenitori in Kubernetes nel servizio contenitore di Azure**

- **Distribuire le app basate su contenitori Windows in Azure Service Fabric**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Procedura dettagliata 1: Panoramica delle App legacy eShop

### <a name="technical-walkthrough-availability"></a>Istruzioni dettagliate su disponibilità

La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[procedure wiki dettagliate eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>Panoramica

In questa procedura dettagliata, è possibile esplorare l'implementazione iniziale di tre applicazioni legacy di esempio. Le prime due App web di esempio dispone di un'architettura monolitica e sono state create utilizzando ASP.NET classico. Un'applicazione si basa su ASP.NET 4.x MVC; la seconda applicazione si basa su Web Form ASP.NET 4.x.
Il terzo app è un'app a 3 livelli composta da un lato server e un'app client di Windows Form [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) servizio.

Sono disponibili in tutte le applicazioni di [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Obiettivi

L'obiettivo principale di questa procedura dettagliata è semplicemente per acquisire familiarità con queste App e con il codice e configurazione. È possibile configurare le App in modo che possano generare e usare dati fittizi, senza usare il database SQL, a scopo di test. Questa configurazione facoltativa si basa sull'inserimento delle dipendenze, in modo disgiunto.

### <a name="scenario-1-aspnet-web-apps"></a>Scenario 1: App Web ASP.NET

La figura seguente illustra uno scenario semplice delle applicazioni web ASP.NET legacy originale.

![Scenario semplice architettura delle applicazioni web originale legacy ASP.NET](./media/image5-1.png)

Dalla prospettiva del dominio aziendale, entrambe le app offrono lo stesso catalogo le funzionalità di gestione. I membri del team di enterprise eShop utilizzerebbe l'app per visualizzare e modificare il catalogo dei prodotti.

La figura seguente mostra le schermate iniziale dell'app.

![Applicazioni MVC ASP.NET e Web Form ASP.NET (le tecnologie esistenti/legacy)](./media/image5-2.png)

Le dipendenze in ASP.NET 4.x o versioni precedenti (per MVC o Web Form) significa che queste applicazioni non verranno eseguito in .NET Core, a meno che il codice è completamente riscritto usando ASP.NET Core MVC.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Scenario 2: Client di Windows Forms app (app di livello 3) e un servizio WCF

La figura seguente illustra uno scenario semplice dell'applicazione legacy a 3 livelli originale.

![Scenario semplice architettura di app legacy originale a 3 livelli con un servizio WCF e un'app client di Windows Form](./media/image5-1.5.png)

### <a name="benefits"></a>Vantaggi

I vantaggi di questa procedura dettagliata sono semplici: Semplicemente acquisire familiarità con le app iniziale e il codice.

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto più approfondito su wiki di GitHub:

- [Panoramica sulla linea di base ASP.NET MVC e le app "legacy" Web Form](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [Panoramica sul servizio WCF di base e l'app "legacy" (livello 3) di Windows Form](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Procedura dettagliata 2: Distribuire le applicazioni .NET esistenti con contenitori Windows in un contenitore

### <a name="overview"></a>Panoramica

Usare i contenitori di Windows per migliorare la distribuzione delle applicazioni .NET esistenti, ad esempio quelle basate su Web Form, MVC o WCF, produzione, sviluppo e ambienti di test.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è descrive diverse opzioni per l'inserimento di un'applicazione esistente di .NET Framework nei contenitori. È possibile:

- Distribuire l'applicazione in un contenitore usando [Visual Studio 2017 Tools per Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versioni successive).

- Distribuire in un contenitore dell'applicazione aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)e quindi usando la [CLI di Docker](https://docs.docker.com/engine/reference/commandline/cli/).

- Distribuire l'applicazione in un contenitore usando il [Img2Docker](https://github.com/docker/communitytools-image2docker-win) strumento (uno strumento open source da Docker).

Questa procedura dettagliata si basa su Visual Studio 2017 Tools per l'approccio di Docker, ma gli altri due approcci sono abbastanza simili dal punto di vista usando i Dockerfile.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Scenario 1: App web ASP.NET nei contenitori

Nella figura seguente illustra lo scenario per applicazioni web legacy eShop nei contenitori.

![Diagramma dell'architettura semplificata in contenitori le applicazioni ASP.NET in un ambiente di sviluppo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>Scenario 2: Servizio WCF in contenitori

Nella figura seguente illustra lo scenario per un'app a 3 livelli con un servizio WCF in contenitori.

![Diagramma dell'architettura del servizio WCF in contenitori in un ambiente di sviluppo semplificato](./media/image5-3.5.png)

### <a name="benefits"></a>Vantaggi

Esistono vantaggi rispetto all'esecuzione dell'applicazione monolitica in un contenitore. In primo luogo, viene creata un'immagine per l'applicazione. Da quel momento, ogni distribuzione viene eseguito nello stesso ambiente. Ogni contenitore Usa la stessa versione del sistema operativo, ha la stessa versione di dipendenze installata, Usa la stessa versione di .NET framework e viene compilato con lo stesso processo. In pratica, si controllano le dipendenze dell'applicazione usando un'immagine Docker. Le dipendenze di pari passo con l'applicazione quando si distribuisce i contenitori.

Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente coerente che viene fornito dai contenitori di Windows. I problemi che vengono visualizzati solo con determinate versioni possono essere rilevati immediatamente, anziché emergere in un ambiente di gestione temporanea o produzione. Differenze in ambienti di sviluppo usati dai membri del team di sviluppo sono meno rilevanti quando le applicazioni eseguite nei contenitori.

Le applicazioni in contenitori hanno anche una curva di scalabilità orizzontale flatter. Le App in contenitori consentono di avere più applicazioni e istanze del servizio (basate su contenitori) in una macchina virtuale o fisica rispetto alle distribuzioni di applicazioni normali per ogni macchina. Questo si traduce in maggiore densità e meno necessarie risorse, soprattutto quando si usano gli agenti di orchestrazione come Kubernetes o Service Fabric.

Utilizzo dei contenitori, in situazioni ideali non è necessario apportare modifiche al codice dell'applicazione (C\#). Nella maggior parte degli scenari, è necessario solo i file di metadati di distribuzione di Docker (file Dockerfile e Docker Compose).

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto più approfondito su wiki di GitHub:

- [Come distribuire le app web di .NET Framework con i contenitori Windows e Docker in un contenitore](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [Aggiunta del supporto Docker a un servizio WCF](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Procedura dettagliata 3: Distribuire l'app basata su contenitori Windows in macchine virtuali di Azure

### <a name="technical-walkthrough-availability"></a>Istruzioni dettagliate su disponibilità

La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing: [https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

### <a name="overview"></a>Panoramica

Distribuzione in un host Docker in un Windows Server 2016 Virtual Machine (VM) in Azure consente di configurare rapidamente gli ambienti di sviluppo/test/staging. Offre inoltre una posizione frequente per i tester o utenti di business convalidare l'app. Le macchine virtuali possono rivelarsi infrastruttura valido come ambienti di produzione un servizio (IaaS).

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è descrive le alternative più, che è necessario quando si distribuisce i contenitori Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.

### <a name="scenarios"></a>Scenari

In questa procedura dettagliata vengono illustrati gli scenari diversi.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Scenario a: Distribuire in una VM di Azure da un PC di sviluppo tramite connessione al motore di Docker

![Distribuire in una VM di Azure da un computer di sviluppo tramite una connessione al motore di Docker](./media/image5-4.png)

**Figura 5-4.** Distribuire in una VM di Azure da un computer di sviluppo tramite una connessione al motore di Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Scenario b: Distribuire una macchina virtuale di Azure tramite un registro Docker

![Distribuire una macchina virtuale di Azure tramite un registro Docker](./media/image5-5.png)

**Figura 5-5.** Distribuire una macchina virtuale di Azure tramite un registro Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Scenario di c: Distribuire in una VM di Azure dalla pipeline CI/CD in servizi di Azure DevOps

![Distribuire in una VM di Azure dalla pipeline CI/CD in servizi di Azure DevOps](./media/image5-6.png)

**Figura 5-6.** Distribuire in una VM di Azure dalla pipeline CI/CD in servizi di Azure DevOps

### <a name="azure-vms-for-windows-containers"></a>Macchine virtuali di Azure per contenitori Windows

Macchine virtuali di Azure per contenitori Windows sono macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambi con il motore Docker configurare. Nella maggior parte dei casi, viene usato Windows Server 2016 in macchine virtuali di Azure.

Attualmente, Azure offre una macchina virtuale denominata **Windows Server 2016 with Containers**. È possibile usare questa macchina virtuale per provare la nuova funzionalità di contenitore di Windows Server con Windows Server Core o Windows Nano Server. Le immagini del sistema operativo del contenitore vengono installate, e quindi la macchina virtuale è pronta per l'uso con Docker.

### <a name="benefits"></a>Vantaggi

Sebbene i contenitori di Windows possono essere distribuiti in macchine virtuali in locale Windows Server 2016, quando si distribuiscono in Azure, si ottiene un modo più semplice per iniziare, con macchine virtuali di contenitore pronto da usare Windows Server. È anche possibile ottenere una posizione online comune che è accessibile ai tester e la scalabilità automatica tramite set di scalabilità di macchine virtuali di Azure.

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto più approfondito su wiki di GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/03.-How-to-deploy-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD))

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Procedura dettagliata 4: Distribuire le app di Windows basata su contenitori in istanze di contenitore di Azure (ACI)

### <a name="technical-walkthrough-availability"></a>Istruzioni dettagliate su disponibilità

La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[La distribuzione dell'App a ACI (istanze di contenitore di Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Panoramica

[Le istanze di contenitore di Azure (ACI)](https://docs.microsoft.com/azure/container-instances/) è il modo più rapido per disporre di un ambiente di sviluppo/test/staging contenitori in cui è possibile distribuire singole istanze di contenitori.

### <a name="goals"></a>Obiettivi

Questa procedura dettagliata illustra gli scenari principali quando si distribuisce i contenitori di Windows per le istanze di contenitore di Azure (ACI) e come è possibile distribuire le app eShopModernizing in ACI.

### <a name="scenarios"></a>Scenari

Possono esistere variazioni sulla distribuzione di App eShopModernizing in ACI quali la distribuzione solo una o tutte le App (app MVC, applicazione Web Form o servizio WCF). Nello scenario seguente illustrato di seguito è possibile visualizzare l'app ASP.NET MVC e il contenitore di SQL Server di entrambi gli elementi distribuiti come contenitori in ACI (istanze di contenitore di Azure).

![Distribuire da un ambiente di sviluppo in ACI](./media/image5-3.5.6.png)

### <a name="benefits"></a>Vantaggi

Istanze di contenitore di Azure rende semplice creare e gestire contenitori Docker in Azure, senza dover effettuare il provisioning di macchine virtuali o adottare un servizio di livello superiore. Con ACI, è possibile distribuire un contenitore Windows in Azure direttamente ed esporla a internet con un nome di dominio completo (FQDN) in pochi secondi (purché si disponga dell'immagine del contenitore Windows pronto in un registro Docker come contenitori di Azure o Hub Docker Registro di sistema).

### <a name="considerations"></a>Considerazioni

La distribuzione di contenitori di Windows con una versione completa di .NET Framework / ASP.NET o SQL Server in Azure le istanze di contenitore non è abbastanza veloce come distribuzione in un Host Docker normali (ad esempio, Windows Server 2016 con contenitori Windows) perché deve essere l'immagine Docker scaricato (estratta dal registro Docker) ogni volta e le dimensioni dell'immagine del contenitore SQL (15.1 GB) e l'immagine del contenitore ASP.NET (13.9 GB) sono significativamente grandi, tuttavia, è molto più economica rispetto a mantenere il proprio host docker (in modo permanente in linea Windows Server 2016 con VM di contenitori Windows in Azure) per non parlare di un intero agente di orchestrazione come Kubernetes in Azure (AKS/ACS) o Azure Service Fabric che sono, d'altra parte, un'ottima scelta per le distribuzioni di produzione.

Come principale conclusione, tramite le istanze di contenitore di Azure è un'opzione molto accattivante per gli scenari di sviluppo/Test e per le pipeline di integrazione continua/recapito Continuo.

## <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto più approfondito su wiki di GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)TBD)

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Procedura dettagliata 5: Distribuire le app di Windows basata su contenitori in Kubernetes nel servizio contenitore di Azure

### <a name="technical-walkthrough-availability"></a>Istruzioni dettagliate su disponibilità

La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

### <a name="overview"></a>Panoramica

Un'applicazione basata su contenitori Windows sarà necessario rapidamente a usare le piattaforme, spostando ulteriormente dalle macchine virtuali IaaS. Questo è necessario per ottenere con facilità la scalabilità elevata e meglio automatizzata della scalabilità e per un miglioramento significativo delle automaticamente le distribuzioni e controllo delle versioni. È possibile raggiungere questi obiettivi con l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile in [servizi contenitore di Azure](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su Windows contenitore in Kubernetes (detto anche *K8s*) nel servizio contenitore di Azure. Distribuzione di Kubernetes da zero è un processo in due passaggi:

1. Distribuire un cluster Kubernetes del servizio contenitore di Azure.

2. Distribuire l'applicazione e le risorse correlate al cluster Kubernetes.

### <a name="scenarios"></a>Scenari

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Scenario a: Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo](./media/image5-7.png)

**Figura 5-7.** Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Scenario b: Distribuire un cluster Kubernetes dalla pipeline CI/CD in servizi di Azure DevOps

![Distribuire un cluster Kubernetes dalla pipeline CI/CD in servizi di Azure DevOps](./media/image5-8.png)

**Figura 5-8.** Distribuire un cluster Kubernetes dalla pipeline CI/CD in servizi di Azure DevOps

### <a name="benefits"></a>Vantaggi

Esistono diversi vantaggi per la distribuzione in un cluster di Kubernetes. Il vantaggio più importante è che si ottiene un ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitore si desidera utilizzare (inner una scalabilità molto elevata di nodi esistenti) e in base al numero di nodi o macchine virtuali nel (cluster scalabilità globale del cluster).

Servizio contenitore di Azure consente di ottimizzare le tecnologie e strumenti open source più diffusi per Azure. Si ottiene una soluzione che offre la portabilità sia per i contenitori per la configurazione dell'applicazione. Selezionare le dimensioni, il numero di host, e dell'agente di orchestrazione strumenti-servizio contenitore gestisce tutto il resto.

Con Kubernetes, gli sviluppatori possono passare da pensare macchine fisiche e virtuali, alla pianificazione di un'infrastruttura incentrata sui contenitori che facilita le funzionalità seguenti, tra gli altri:

- Applicazioni basate su più contenitori

- La replica di istanze di contenitore e la scalabilità automatica orizzontale

- Denominazione e l'individuazione (ad esempio, il DNS interno)

- Bilanciamento del carico

- Aggiornamenti in sequenza

- Distribuzione segreti

- Controlli di integrità dell'applicazione

## <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto più approfondito su wiki di GitHub: [https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-C-CD))

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-service-fabric"></a>Procedura dettagliata 6: Distribuire le app basate su contenitori Windows in Azure Service Fabric

### <a name="technical-walkthrough-availability"></a>Istruzioni dettagliate su disponibilità

La procedura dettagliata tecnica completa è disponibile nella pagina wiki di repository GitHub eShopModernizing:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

### <a name="overview"></a>Panoramica

Un'applicazione basata su contenitori Windows rapidamente deve usare le piattaforme, spostando ulteriormente dalle macchine virtuali IaaS. Questo è necessario per ottenere con facilità la scalabilità elevata e meglio automatizzata della scalabilità e per un miglioramento significativo delle automaticamente le distribuzioni e controllo delle versioni. È possibile raggiungere questi obiettivi con Azure Service Fabric, che è disponibile nel cloud di Azure, ma è anche disponibile per l'uso in locale, l'agente di orchestrazione o anche in un altro cloud pubblico.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata consiste nel comprendere come distribuire un'applicazione basata su contenitore Windows in un cluster di Service Fabric in Azure. Distribuzione di Service Fabric da zero è un processo in due passaggi:

1. Distribuire un cluster di Service Fabric in Azure (o a un altro ambiente).

2. Distribuire l'applicazione e le risorse correlate per il cluster di Service Fabric.

### <a name="scenarios"></a>Scenari

#### <a name="scenario-a-deploy-directly-to-a-service-fabric-cluster-from-a-dev-environment"></a>Scenario a: Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo

![Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo](./media/image5-9.png)

> **Figura 5-9.** Distribuire direttamente in un cluster di Service Fabric da un ambiente di sviluppo

### <a name="scenario-b-deploy-to-a-service-fabric-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Scenario b: Distribuire in un cluster di Service Fabric dalla pipeline CI/CD in servizi di Azure DevOps

![Distribuire in un cluster di Service Fabric dalla pipeline CI/CD in servizi di Azure DevOps](./media/image5-10.png)

**Figura 5-10.** Distribuire in un cluster di Service Fabric dalla pipeline CI/CD in servizi di Azure DevOps

## <a name="benefits"></a>Vantaggi

I vantaggi della distribuzione in un cluster di Service Fabric sono simili ai vantaggi dell'uso di Kubernetes. Una differenza, tuttavia, è che Service Fabric è un ambiente di produzione più avanzato per le applicazioni di Windows rispetto a Kubernetes, che si trova in una fase beta per i contenitori Windows in Kubernetes versione 1.9 (dicembre 2017). Kubernetes è un ambiente più avanzato per Linux.

Il principale vantaggio dell'uso di Azure Service Fabric è di ottenere un ambiente di produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze di contenitore si desidera utilizzare (inner una scalabilità molto elevata di nodi esistenti) e in base al numero di i nodi o macchine virtuali del cluster (scalabilità globale del cluster).

Azure Service Fabric offre la portabilità per i contenitori sia per la configurazione dell'applicazione. È possibile avere un'infrastruttura di servizi del cluster in Azure o installarlo in locale nel proprio Data Center. È anche possibile installare un cluster di Service Fabric in un cloud diverso, ad esempio [Amazon AWS](https://blogs.msdn.microsoft.com/azureservicefabric/2017/05/18/tutorial-how-to-create-a-service-fabric-standalone-cluster-with-aws-ec2-instances/).

Con Service Fabric, gli sviluppatori possono passare da pensare macchine fisiche e virtuali per la pianificazione di un'infrastruttura incentrata sui contenitori che facilita le funzionalità seguenti, tra gli altri:

- Applicazioni basate su più contenitori.

- La replica di istanze di contenitore e la scalabilità automatica orizzontale.

- Denominazione e l'individuazione (ad esempio, il DNS interno).

- Bilanciamento del carico.

- Aggiornamenti in sequenza.

- Per la distribuzione dei segreti.

- Controlli di integrità dell'applicazione.

Le funzionalità seguenti sono esclusive in Service Fabric (rispetto a altri agenti di orchestrazione):

- Funzionalità di servizi con stato, tramite il modello applicativo di Reliable Services.

- Modello di attori, tramite il modello applicativo di Reliable Actors.

- Distribuire i processi di essenziale, oltre a contenitori Windows o Linux.

- Gli aggiornamenti in sequenza e controlli di integrità avanzate.

### <a name="next-steps"></a>Passaggi successivi

Esplorare il contenuto più approfondito su wiki di GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-How-to-deploy-your-Windows-Containers-based-apps-into-Azure-Service-Fabric-(Including-CI-CD))

> [!div class="step-by-step"]
> [Precedente](lift-and-shift-existing-apps-devops/migrate-to-hybrid-cloud-scenarios.md)
> [Successivo](conclusions.md)
