---
title: Procedure dettagliate e panoramica introduttiva tecnica
description: Modernizzare le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows | Procedure dettagliate e panoramica introduttiva tecnica
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2019
ms.locfileid: "69660889"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Procedure dettagliate e panoramica introduttiva tecnica

Per limitare le dimensioni di questo e-book, la documentazione tecnica aggiuntiva e le procedure dettagliate complete sono state rese disponibili in un repository GitHub. La serie online di procedure dettagliate descritte in questo capitolo illustra la configurazione dettagliata dei diversi ambienti basati sui contenitori di Windows e la distribuzione in Azure.

Le sezioni seguenti illustrano le informazioni su ogni procedura dettagliata, gli obiettivi e la visione di alto livello e forniscono un diagramma delle attività che interessano. È possibile ottenere le procedure dettagliate nel wiki del repository GitHub *eShopModernizing* apps in <https://github.com/dotnet-architecture/eShopModernizing/wiki>.

## <a name="technical-walkthrough-list"></a>Elenco di procedure tecniche

Le procedure dettagliate introduttive riportate di seguito forniscono indicazioni tecniche coerenti e complete per le app di esempio che è possibile spostare e spostare usando i contenitori e quindi spostarsi usando più opzioni di distribuzione in Azure.

Ognuna delle procedure dettagliate seguenti usa le nuove app eShopLegacy e eShopModernizing di esempio, disponibili su GitHub in <https://github.com/dotnet-architecture/eShopModernizing>.

- **Panoramica delle app legacy di eShop (app di base per la modernizzazione)**

- **Distribuire le app Web ASP.NET esistenti (Web Form & MVC) con i contenitori di Windows**

- **Distribuire i servizi WCF esistenti (app a più livelli) con i contenitori di Windows**

- **Distribuire l'app basata su contenitori Windows in macchine virtuali di Azure**

- **Distribuire le app basate su contenitori Windows in Kubernetes nel servizio contenitore di Azure**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Procedura dettagliata 1: Panoramica delle app legacy di eShop

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata relativa alla disponibilità

La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:

[procedure dettagliate del wiki eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>Panoramica

In questa procedura dettagliata è possibile esplorare l'implementazione iniziale di tre applicazioni legacy di esempio. Le prime due app Web di esempio hanno un'architettura monolitica e sono state create usando ASP.NET classiche. Un'applicazione è basata su ASP.NET 4. x MVC; la seconda applicazione è basata su Web Form ASP.NET 4. x.
La terza app è un'app a tre livelli composta da un'app client WinForms e un servizio Windows Communication Foundation lato server [(WCF)](../../framework/wcf/whats-wcf.md) .

Tutte queste applicazioni sono disponibili nel [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Obiettivi

L'obiettivo principale di questa procedura dettagliata è semplicemente acquisire familiarità con queste app e con il codice e la configurazione. È possibile configurare le app in modo che generino e usino dati fittizi, senza usare il database SQL, a scopo di test. Questa configurazione facoltativa è basata sull'inserimento delle dipendenze, in modo separato.

### <a name="scenario-1-aspnet-web-apps"></a>Scenario 1: app Web ASP.NET

La figura seguente illustra lo scenario semplice delle applicazioni Web ASP.NET legacy originali.

![Scenario di architettura semplice delle applicazioni Web ASP.NET legacy originali](./media/image5-1.png)

Dal punto di vista del dominio aziendale, entrambe le app offrono le stesse funzionalità di gestione del catalogo. I membri del team di eShop Enterprise useranno l'app per visualizzare e modificare il catalogo prodotti.

Nella figura seguente sono illustrate le schermate iniziali dell'app.

![Applicazioni Web Form ASP.NET MVC e ASP.NET (tecnologie esistenti/legacy)](./media/image5-2.png)

Le dipendenze in ASP.NET 4. x o versioni precedenti (per MVC o per Web Form) indicano che queste applicazioni non vengono eseguite in .NET Core, a meno che il codice non venga completamente riscritto usando ASP.NET Core MVC.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Scenario 2: servizio WCF e app client WinForms (app a 3 livelli)

La figura seguente illustra lo scenario semplice dell'applicazione legacy a 3 livelli originale.

![Scenario di architettura semplice dell'app a 3 livelli originale legacy con un servizio WCF e un'app client WinForms](./media/image5-1.5.png)

### <a name="benefits"></a>Vantaggi

I vantaggi di questa procedura dettagliata sono semplici: è sufficiente acquisire familiarità con il codice e le app iniziali.

### <a name="next-steps"></a>Passaggi successivi

Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:

- [Panoramica sulle app ASP.NET MVC e Web Forms "Legacy" di base](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [Presentazione del servizio WCF di base e dell'app Windows Forms (a 3 livelli) "Legacy"](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Procedura dettagliata 2: distribuire le applicazioni .NET esistenti con i contenitori di Windows

### <a name="overview"></a>Panoramica

Usare i contenitori di Windows per migliorare la distribuzione di applicazioni .NET esistenti, come quelle basate su MVC, Web Form o WCF, in ambienti di produzione, sviluppo e test.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è mostrare diverse opzioni per inserimento un'applicazione .NET Framework esistente. È possibile:

- Distribuire l'applicazione con [Visual studio 2017 Tools per Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (visual studio 2017 o versioni successive).

- Distribuire l'applicazione aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/)e quindi usando l'interfaccia della riga di comando di [Docker](https://docs.docker.com/engine/reference/commandline/cli/).

- Distribuire l'applicazione usando lo strumento [Img2Docker](https://github.com/docker/communitytools-image2docker-win) (uno strumento open source di Docker).

Questa procedura dettagliata è incentrata sull'approccio di Visual Studio 2017 Tools per Docker, ma gli altri due approcci sono piuttosto simili per quanto riguarda l'uso di Dockerfile.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Scenario 1: app Web ASP.NET in contenitori

La figura seguente illustra lo scenario per le applicazioni di app Web legacy del eShop in contenitori.

![Diagramma dell'architettura semplificato di applicazioni ASP.NET in contenitori in un ambiente di sviluppo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>Scenario 2: servizio WCF in contenitori

La figura seguente illustra lo scenario per un'applicazione a 3 livelli con un servizio WCF in contenitori.

![Diagramma dell'architettura semplificato del servizio WCF in contenitori in un ambiente di sviluppo](./media/image5-3.5.png)

### <a name="benefits"></a>Vantaggi

L'esecuzione di un'applicazione monolitica in un contenitore presenta alcuni vantaggi. Prima di tutto, creare un'immagine per l'applicazione. Da quel momento in poi, ogni distribuzione viene eseguita nello stesso ambiente. Ogni contenitore usa la stessa versione del sistema operativo, è installata la stessa versione delle dipendenze, usa la stessa versione di .NET Framework e viene compilata utilizzando lo stesso processo. In pratica, è possibile controllare le dipendenze dell'applicazione usando un'immagine docker. Le dipendenze viaggiano con l'applicazione quando si distribuiscono i contenitori.

Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente coerente fornito dai contenitori di Windows. I problemi che si verificano solo con determinate versioni possono essere individuati immediatamente, anziché essere visualizzati in un ambiente di gestione temporanea o di produzione. Le differenze negli ambienti di sviluppo usati dai membri del team di sviluppo sono meno importanti quando le applicazioni vengono eseguite nei contenitori.

Le applicazioni incluse in contenitori hanno anche una curva con scalabilità orizzontale più piatta. Le app in contenitori consentono di avere più istanze di applicazioni e servizi (basate sui contenitori) in una macchina virtuale o in un computer fisico rispetto alle distribuzioni di applicazioni normali per ogni computer. Questo si traduce in una maggiore densità e meno risorse necessarie, soprattutto quando si usano agenti di orchestrazione come Kubernetes.

La creazione di contenitori, in situazioni ideali, non richiede alcuna modifica al codice dell'applicazione (C\#). Nella maggior parte degli scenari sono necessari solo i file di metadati di distribuzione Docker (Dockerfile e file di Docker Compose).

### <a name="next-steps"></a>Passaggi successivi

Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:

- [Come distribuire le app Web di .NET Framework con i contenitori di Windows e Docker](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [Aggiunta del supporto Docker a un servizio WCF](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Procedura dettagliata 3: distribuire l'app basata su contenitori Windows in macchine virtuali di Azure

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata relativa alla disponibilità

La procedura dettagliata tecnica completa è disponibile nel repository GitHub eShopModernizing wiki: <https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>Panoramica

La distribuzione in un host Docker in una macchina virtuale Windows Server 2016 (VM) in Azure consente di configurare rapidamente ambienti di sviluppo/test/gestione temporanea. Fornisce inoltre un posto comune a tester o utenti aziendali per convalidare l'app. Le macchine virtuali possono anche essere ambienti di produzione di infrastruttura distribuita come servizio (IaaS) validi.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è mostrare le diverse alternative disponibili quando si distribuiscono i contenitori di Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.

### <a name="scenarios"></a>Scenari

In questa procedura dettagliata sono descritti diversi scenari.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Scenario A: eseguire la distribuzione in una macchina virtuale di Azure da un computer di sviluppo tramite la connessione al motore Docker

![Eseguire la distribuzione in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker](./media/image5-4.png)

**Figura 5-4.** Eseguire la distribuzione in una macchina virtuale di Azure da un computer di sviluppo tramite una connessione al motore Docker

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Scenario B: distribuire in una macchina virtuale di Azure tramite un registro Docker

![Eseguire la distribuzione in una macchina virtuale di Azure tramite un registro Docker](./media/image5-5.png)

**Figura 5-5.** Eseguire la distribuzione in una macchina virtuale di Azure tramite un registro Docker

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Scenario C: eseguire la distribuzione in una macchina virtuale di Azure da pipeline CI/CD in Azure DevOps Services

![Eseguire la distribuzione in una macchina virtuale di Azure da pipeline CI/CD in Azure DevOps Services](./media/image5-6.png)

**Figura 5-6.** Eseguire la distribuzione in una macchina virtuale di Azure da pipeline CI/CD in Azure DevOps Services

### <a name="azure-vms-for-windows-containers"></a>VM di Azure per i contenitori di Windows

Le macchine virtuali di Azure per i contenitori di Windows sono macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambe con il motore Docker configurato. Nella maggior parte dei casi, Windows Server 2016 viene usato nelle VM di Azure.

Azure fornisce attualmente una macchina virtuale denominata **Windows Server 2016 con i contenitori**. È possibile usare questa macchina virtuale per provare la nuova funzionalità contenitore di Windows Server, con Windows Server Core o Windows nano server. Le immagini del sistema operativo del contenitore sono installate, quindi la macchina virtuale è pronta per l'uso con Docker.

### <a name="benefits"></a>Vantaggi

Sebbene i contenitori di Windows possano essere distribuiti in macchine virtuali Windows Server 2016 locali, quando si esegue la distribuzione in Azure, si ottiene un modo più semplice per iniziare, con macchine virtuali contenitore Windows Server pronte all'uso. Si ottiene anche un percorso online comune accessibile ai tester e la scalabilità automatica tramite i set di scalabilità di macchine virtuali di Azure.

### <a name="next-steps"></a>Passaggi successivi

Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Procedura dettagliata 4: distribuire le app basate su contenitori Windows in istanze di contenitore di Azure (ACI)

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata relativa alla disponibilità

La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:

[Distribuzione delle app in ACI (istanze di contenitore di Azure)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Panoramica

[Istanze di contenitore di Azure](https://docs.microsoft.com/azure/container-instances/) è il modo più rapido per avere un ambiente di sviluppo/test/gestione temporanea di contenitori in cui è possibile distribuire singole istanze di contenitori.

### <a name="goals"></a>Obiettivi

Questa procedura dettagliata illustra gli scenari principali per la distribuzione di contenitori di Windows in istanze di contenitore di Azure (ACI) e come è possibile distribuire app eShopModernizing in ACI.

### <a name="scenarios"></a>Scenari

È possibile che si verifichino variazioni di distribuzione delle app eShopModernizing in ACI, ad esempio la distribuzione di una o tutte le app (app MVC, app Web Form o servizio WCF). Nel seguente scenario illustrato di seguito è possibile visualizzare l'app MVC ASP.NET più il contenitore SQL Server entrambi distribuiti come contenitori in ACI (istanze di contenitore di Azure).

![Eseguire la distribuzione in ACI da un ambiente di sviluppo](./media/image5-3.5.6.png)

### <a name="benefits"></a>Vantaggi

Istanze di contenitore di Azure semplifica la creazione e la gestione di contenitori Docker in Azure, senza dover eseguire il provisioning di macchine virtuali o adottare un servizio di livello superiore. Con ACI è possibile distribuire direttamente un contenitore Windows in Azure ed esporlo a Internet con un nome di dominio completo (FQDN) in pochi secondi (a condizione che l'immagine del contenitore di Windows sia pronta in un registro Docker, ad esempio l'hub Docker o il contenitore di Azure). Registro di sistema).

### <a name="considerations"></a>Considerazioni

La distribuzione di contenitori di Windows con .NET Framework completo/ASP.NET o SQL Server in istanze di contenitore di Azure non è molto veloce quanto la distribuzione in un normale host Docker, ad esempio Windows Server 2016 con contenitori Windows, perché il l'immagine Docker deve essere scaricata (pull dal registro Docker) ogni volta e le dimensioni dell'immagine del contenitore SQL (15,1 GB) e dell'immagine del contenitore ASP.NET (13,9 GB) sono molto grandi. Tuttavia è molto più economico rispetto alla gestione del proprio host Docker (Windows in linea permanente) Server 2016 con VM di contenitori Windows in Azure) per non menzionare un intero agente di orchestrazione come Kubernetes in Azure (AKS), che è d'altra parte una scelta ottimale per le distribuzioni di produzione.

Come conclusione principale, l'uso di istanze di contenitore di Azure è un'opzione molto interessante per gli scenari di sviluppo e test e per le pipeline CI/CD.

## <a name="next-steps"></a>Passaggi successivi

Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Procedura dettagliata 5: distribuire le app basate su contenitori Windows in Kubernetes nel servizio contenitore di Azure

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata relativa alla disponibilità

La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a>Panoramica

Un'applicazione basata su contenitori di Windows dovrà usare rapidamente le piattaforme, allontanandosi ancora più dalle macchine virtuali IaaS. Questa operazione è necessaria per ottenere facilmente scalabilità elevata e una migliore scalabilità automatica e per un miglioramento significativo delle distribuzioni e del controllo delle versioni automatizzate. Per raggiungere questi obiettivi, è possibile usare l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile nei [Servizi contenitore di Azure](https://azure.microsoft.com/services/container-service/).

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata consiste nell'apprendere come distribuire un'applicazione basata su contenitore Windows in Kubernetes (anche denominata *K8s*) nel servizio contenitore di Azure. La distribuzione in Kubernetes da zero è un processo in due passaggi:

1. Distribuire un cluster Kubernetes nel servizio contenitore di Azure.

2. Distribuire l'applicazione e le risorse correlate al cluster Kubernetes.

### <a name="scenarios"></a>Scenari

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Scenario A: distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo](./media/image5-7.png)

**Figura 5-7.** Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppo

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Scenario B: distribuire in un cluster Kubernetes da pipeline CI/CD in Azure DevOps Services

![Eseguire la distribuzione in un cluster Kubernetes da pipeline CI/CD in Azure DevOps Services](./media/image5-8.png)

**Figura 5-8.** Eseguire la distribuzione in un cluster Kubernetes da pipeline CI/CD in Azure DevOps Services

### <a name="benefits"></a>Vantaggi

La distribuzione in un cluster in Kubernetes presenta numerosi vantaggi. Il vantaggio principale è che si ottiene un ambiente di produzione in cui è possibile scalare verticalmente l'applicazione in base al numero di istanze di contenitore che si vuole usare (scalabilità interna nei nodi esistenti) e in base al numero di nodi o macchine virtuali nel cluster ( scalabilità globale del cluster.

Il servizio contenitore di Azure ottimizza le tecnologie e gli strumenti open source più diffusi in modo specifico per Azure. Si ottiene una soluzione aperta che offre la portabilità, sia per i contenitori che per la configurazione dell'applicazione. Si selezionano le dimensioni, il numero di host e gli strumenti di orchestrazione-il servizio contenitore gestisce tutto il resto.

Con Kubernetes, gli sviluppatori possono progredire dalla riflessione su macchine fisiche e virtuali, alla pianificazione di un'infrastruttura incentrata sul contenitore che facilita le funzionalità seguenti, tra le altre:

- Applicazioni basate su più contenitori

- Replica di istanze di contenitore e scalabilità automatica orizzontale

- Denominazione e individuazione (ad esempio, DNS interno)

- Bilanciamento del carico

- Aggiornamenti in sequenza

- Distribuzione dei segreti

- Controlli di integrità dell'applicazione

## <a name="next-steps"></a>Passaggi successivi

Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a>Procedura dettagliata 6: distribuire le app basate su contenitori Windows nel servizio app Azure per i contenitori

### <a name="technical-walkthrough-availability"></a>Procedura dettagliata relativa alla disponibilità

La procedura dettagliata tecnica completa è disponibile nella wiki del repository GitHub eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a>Panoramica

Una semplice applicazione in contenitori con i contenitori di Windows può essere facilmente distribuita al servizio app Azure per i contenitori. Si tratta dell'approccio consigliato per la maggior parte delle applicazioni basate su contenitore Windows.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata consiste nell'apprendere come distribuire un'applicazione basata su contenitore Windows per app Azure servizio per i contenitori da un registro (hub Docker o Azure Container Registry).

### <a name="scenario"></a>Scenario

![Distribuire un'app basata su contenitori Windows nel servizio app Azure per i contenitori](./media/image5-11.png)

### <a name="benefits"></a>Vantaggi

La distribuzione nel servizio app Azure per i contenitori offre i vantaggi dei contenitori abbinati ai vantaggi PaaS di app Azure servizio. Il servizio app può essere facilmente ridimensionato verticalmente e orizzontalmente e può essere configurato per la scalabilità automatica per soddisfare le esigenze mutevoli. Gli aggiornamenti possono essere eseguiti senza tempi di inattività e la configurazione della distribuzione continua da un registro di sistema è facilmente configurabile.

## <a name="next-steps"></a>Passaggi successivi

Esplorare questo contenuto in modo più dettagliato sul wiki di GitHub: <https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

> [!div class="step-by-step"]
> [Precedente](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [Successivo](conclusions.md) <!-- Next Chapter -->
