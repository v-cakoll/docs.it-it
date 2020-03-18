---
title: Procedure dettagliate e panoramica introduttiva tecnica
description: Modernizza le applicazioni .NET esistenti con il cloud di Azure e i contenitori di Windows Panoramica delle procedure dettagliate e delle informazioni tecniche
ms.date: 04/28/2018
ms.openlocfilehash: 190b33c4307b09bab0543d481e66ac9328074a0d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69660889"
---
# <a name="walkthroughs-and-technical-get-started-overview"></a>Procedure dettagliate e panoramica introduttiva tecnica

Per limitare le dimensioni di questo e-book, sono stati resi disponibili ulteriori documentazione tecnica e le procedure dettagliate complete in un repository GitHub. The online series of walkthroughs that is described in this chapter covers the step-by-step setup of the multiple environments that are based on Windows Containers, and deployment to Azure.

Nelle sezioni seguenti viene illustrato il significato di ogni procedura dettagliata, i relativi obiettivi e la visione di alto livello e viene fornito un diagramma delle attività coinvolte. È possibile ottenere le procedure dettagliate stessi nel *wiki eShopModernizing* apps GitHub repo in <https://github.com/dotnet-architecture/eShopModernizing/wiki>.

## <a name="technical-walkthrough-list"></a>Elenco delle procedure dettagliate tecniche

Le procedure dettagliate introduttive seguenti forniscono indicazioni tecniche coerenti e complete per le app di esempio che è possibile sollevare e spostare usando i contenitori e quindi spostarsi usando più opzioni di distribuzione in Azure.The following get-started walkthroughs provide consistent and comprehensive technical guidance for sample apps that you can lift and shift by using containers, and then move by using multiple deployment choices in Azure.

Ognuna delle procedure dettagliate seguenti usa le nuove app eShopLegacy ed eShopModernizing di esempio, disponibili su GitHub all'indirizzo <https://github.com/dotnet-architecture/eShopModernizing>.

- **Presentazione delle app legacy di eShop (app di base da modernizzare)**

- **Contenitore delle app Web di ASP.NET esistenti (WebForms & MVC) con contenitori Di WindowsContainerize your existing ASP.NET web apps (WebForms & MVC) with Windows Containers**

- **Contenitore dei servizi WCF esistenti (app a più livelli) con i contenitori di WindowsContainerize your existing WCF services (N-Tier apps) with Windows Containers**

- **Distribuire l'app basata su contenitori di Windows nelle macchine virtuali di AzureDeploy your Windows Containers-based app to Azure VMs**

- **Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di AzureDeploy your Windows Containers-based apps to Kubernetes in Azure Container Service**

## <a name="walkthrough-1-tour-of-eshop-legacy-apps"></a>Procedura dettagliata 1: Tour delle app legacy di eShop

### <a name="technical-walkthrough-availability"></a>Disponibilità della procedura dettagliata tecnica

La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:

[EShopModernizing procedure dettagliate wiki](https://github.com/dotnet-architecture/eShopModernizing/wiki)

### <a name="overview"></a>Panoramica

In questa procedura dettagliata, è possibile esplorare l'implementazione iniziale di tre applicazioni legacy di esempio. Le prime due app Web di esempio hanno un'architettura monolitica e sono state create usando ASP.NET classici. Un'applicazione è basata su ASP.NET MVC 4.x; la seconda applicazione è basata su ASP.NET Web Form 4.x.
La terza app è un'app a 3 livelli composta da un'app WinForms client e da un servizio [Windows Communication Foundation (WCF)](../../framework/wcf/whats-wcf.md) lato server.

Tutte queste applicazioni sono disponibili presso il [repository GitHub eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing).

### <a name="goals"></a>Obiettivi

L'obiettivo principale di questa procedura dettagliata è semplicemente quello di acquisire familiarità con queste app e con il codice e la configurazione. È possibile configurare le app in modo che generino e utilizzino dati fittizi, senza usare il database SQL, a scopo di test. Questa configurazione facoltativa si basa sull'inserimento delle dipendenze, in modo disaccoppiato.

### <a name="scenario-1-aspnet-web-apps"></a>Scenario 1: ASP.NET di app Web

La figura seguente mostra lo scenario semplice delle applicazioni Web di ASP.NET legacy originali.

![Scenario di architettura semplice delle applicazioni Web ASP.NET legacy originali](./media/image5-1.png)

Dal punto di vista del dominio aziendale, entrambe le app offrono le stesse funzionalità di gestione del catalogo. I membri del team aziendale di eShop utilizzerebbero l'app per visualizzare e modificare il catalogo prodotti.

La figura seguente mostra le schermate iniziali dell'app.

![ASP.NET le applicazioni Web Form MVC e ASP.NET (tecnologie esistenti/legacy)](./media/image5-2.png)

Dipendenze in ASP.NET 4.x o versioni precedenti (per MVC o per Web Form) significa che queste applicazioni non verranno eseguite in .NET Core a meno che il codice non venga completamente riscritto utilizzando ASP.NET MVC principale.

### <a name="scenario-2-wcf-service-and-winforms-client-app-3-tier-app"></a>Scenario 2: servizio WCF e app client WinForms (app a 3 livelli)Scenario 2: WCF service and WinForms client app (3-Tier app)

La figura seguente mostra lo scenario semplice dell'applicazione legacy a 3 livelli originale.

![Scenario di architettura semplice dell'app a 3 livelli legacy originale con un servizio WCF e un'app client WinForms](./media/image5-1.5.png)

### <a name="benefits"></a>Vantaggi

I vantaggi di questa procedura dettagliata sono semplici: è sufficiente acquisire familiarità con il codice e le app iniziali.

### <a name="next-steps"></a>Passaggi successivi

Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:

- [Tour sulla linea di base ASP.NET le app MVC e Web Form "legacy"](https://github.com/dotnet-architecture/eShopModernizing/wiki/01.-Tour-on-the-ASP.NET-MVC-and-WebForms-apps-implementation-code)
- [Tour sul servizio WCF di base e sull'app "legacy" di WindowsForms (3 livelli)](https://github.com/dotnet-architecture/eShopModernizing/wiki/21.-Tour-on-the-WCF-service-and-WinForms-apps)

## <a name="walkthrough-2-containerize-your-existing-net-applications-with-windows-containers"></a>Procedura dettagliata 2: Containerize le applicazioni .NET esistenti con contenitori di WindowsWalkthrough 2: Containerize your existing .NET applications with Windows Containers

### <a name="overview"></a>Panoramica

Usare i contenitori di Windows per migliorare la distribuzione di applicazioni .NET esistenti, come quelle basate su MVC, Web Form o WCF, in ambienti di produzione, sviluppo e test.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è illustrare diverse opzioni per il contenitore di un'applicazione .NET Framework esistente. È possibile:

- Containerize l'applicazione utilizzando [Visual Studio 2017 Tools for Docker](/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker) (Visual Studio 2017 o versioni successive).

- Contenitore dell'applicazione aggiungendo manualmente un [Dockerfile](https://docs.docker.com/engine/reference/builder/), quindi utilizzando [l'interfaccia della riga di comando di Docker](https://docs.docker.com/engine/reference/commandline/cli/).

- Contenitore dell'applicazione utilizzando lo strumento [Img2Docker](https://github.com/docker/communitytools-image2docker-win) (uno strumento open source da Docker).

Questa procedura dettagliata è incentrata sull'approccio Visual Studio 2017 Tools for Docker, ma gli altri due approcci sono abbastanza simili per quanto riguarda l'utilizzo di Dockerfiles.This walkthrough focuses on the Visual Studio 2017 Tools for Docker approach, but the two approaches are fairly similar in regard to using Dockerfiles.

### <a name="scenario-1-containerized-aspnet-web-apps"></a>Scenario 1: app Web ASP.NET in contenitore

Figura seguente viene illustrato lo scenario per contenitori eShop applicazioni web legacy.

![Diagramma dell'architettura semplificato delle applicazioni in contenitore ASP.NET in un ambiente di sviluppo](./media/image5-3.png)

### <a name="scenario-2-containerized-wcf-service"></a>Scenario 2: servizio WCF con contenitoreScenario 2: Containerized WCF service

Figura seguente viene illustrato lo scenario per un'applicazione a 3 livelli con un servizio WCF contenitore.

![Diagramma dell'architettura semplificato del servizio WCF con contenitore in un ambiente di sviluppo](./media/image5-3.5.png)

### <a name="benefits"></a>Vantaggi

L'esecuzione dell'applicazione monolitica in un contenitore presenta dei vantaggi. In primo luogo, si crea un'immagine per l'applicazione. Da quel momento in everso, ogni distribuzione viene eseguita nello stesso ambiente. Ogni contenitore usa la stessa versione del sistema operativo, ha la stessa versione delle dipendenze installata, usa la stessa versione di .NET Framework e viene compilato utilizzando lo stesso processo. Fondamentalmente, è possibile controllare le dipendenze dell'applicazione utilizzando un'immagine Docker. Le dipendenze viaggiano con l'applicazione quando si distribuiscono i contenitori.

Un ulteriore vantaggio è che gli sviluppatori possono eseguire l'applicazione nell'ambiente coerente fornito dai contenitori di Windows.An additional vantaggio is that developers can run the application in the consistent environment that's provided by Windows Containers. I problemi che appaiono solo con determinate versioni possono essere individuati immediatamente, anziché emergere in un ambiente di gestione temporanea o di produzione. Le differenze negli ambienti di sviluppo utilizzati dai membri del team di sviluppo contano meno quando le applicazioni vengono eseguite in contenitori.

Le applicazioni containerizzate hanno anche una curva di scalabilità orizzontale più piatta. Le app containerizzate consentono di avere più istanze di applicazioni e servizi (basate su contenitori) in una macchina virtuale o in una macchina fisica rispetto alle normali distribuzioni di applicazioni per computer. Ciò si traduce in una maggiore densità e in un numero inferiore di risorse necessarie, soprattutto quando si utilizzano orchestratori come Kubernetes.

La containerizzazione, in situazioni ideali, non richiede di\#apportare modifiche al codice dell'applicazione (C ). Nella maggior parte degli scenari sono necessari solo i file di metadati di distribuzione Docker (file Dockerfiles e Docker Compose).

### <a name="next-steps"></a>Passaggi successivi

Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:

- [Come creare un contenitore delle app Web di .NET Framework con contenitori e Docker di Windows](https://github.com/dotnet-architecture/eShopModernizing/wiki/02.-How-to-containerize-the-.NET-Framework-web-apps-with-Windows-Containers-and-Docker)
- [Aggiunta del supporto Docker a un servizio WCFAdding Docker Support to a WCF service](https://github.com/dotnet-architecture/eShopModernizing/wiki/22.-Adding-Docker-Support)

## <a name="walkthrough-3-deploy-your-windows-containers-based-app-to-azure-vms"></a>Procedura dettagliata 3: Distribuire l'app basata su contenitori di Windows nelle macchine virtuali di AzureWalkthrough 3: Deploy your Windows Containers-based app to Azure VMs

### <a name="technical-walkthrough-availability"></a>Disponibilità della procedura dettagliata tecnica

La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

### <a name="overview"></a>Panoramica

La distribuzione in un host Docker in una macchina virtuale Windows Server 2016 (VM) in Azure consente di configurare rapidamente ambienti di sviluppo/test/gestione temporanea. Fornisce inoltre un'area comune per i tester o gli utenti aziendali per convalidare l'app. Le macchine virtuali possono anche essere ambienti di produzione IaaS (Infrastructure as a Service) validi.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è mostrare le alternative multiple disponibili quando si distribuiscono contenitori di Windows in macchine virtuali di Azure basate su Windows Server 2016 o versioni successive.

### <a name="scenarios"></a>Scenari

In questa procedura dettagliata vengono descritti diversi scenari.

#### <a name="scenario-a-deploy-to-an-azure-vm-from-a-dev-pc-through-docker-engine-connection"></a>Scenario A: Distribuire in una macchina virtuale di Azure da un PC di sviluppo tramite la connessione a Docker EngineScenario A: Deploy to an Azure VM from a dev PC through Docker Engine connection

![Distribuire in una macchina virtuale di Azure da un PC di sviluppo tramite una connessione del motore DockerDeploy to an Azure VM from a dev PC through a Docker Engine connection](./media/image5-4.png)

**Figura 5-4.** Distribuire in una macchina virtuale di Azure da un PC di sviluppo tramite una connessione del motore DockerDeploy to an Azure VM from a dev PC through a Docker Engine connection

#### <a name="scenario-b-deploy-to-an-azure-vm-through-a-docker-registry"></a>Scenario B: Deploy to an Azure VM through a Docker Registry

![Distribuire in una macchina virtuale di Azure tramite un Registro di sistema DockerDeploy to an Azure VM through a Docker Registry](./media/image5-5.png)

**Figura 5-5.** Distribuire in una macchina virtuale di Azure tramite un Registro di sistema DockerDeploy to an Azure VM through a Docker Registry

#### <a name="scenario-c-deploy-to-an-azure-vm-from-cicd-pipelines-in-azure-devops-services"></a>Scenario C: Deploy to an Azure VM from CI/CD pipelines in Azure DevOps Services

![Distribuire in una macchina virtuale di Azure da pipeline di CI/CD nei servizi DevOps di AzureDeploy to an Azure VM from CI/CD pipelines in Azure DevOps Services](./media/image5-6.png)

**Figura 5-6.** Distribuire in una macchina virtuale di Azure da pipeline di CI/CD nei servizi DevOps di AzureDeploy to an Azure VM from CI/CD pipelines in Azure DevOps Services

### <a name="azure-vms-for-windows-containers"></a>Azure VMs for Windows Containers

Le macchine virtuali di Azure per i contenitori di Windows sono macchine virtuali basate su Windows Server 2016, Windows 10 o versioni successive, entrambe con il motore Docker configurato. In most cases, Windows Server 2016 is used in the Azure VMs.

Azure fornisce attualmente una macchina virtuale denominata **Windows Server 2016 con contenitori.** È possibile utilizzare questa macchina virtuale per provare la nuova funzionalità Contenitore Windows Server, con Windows Server Core o Windows Nano Server.You can use this VM to try the new Windows Server Container feature, with either Windows Server Core or Windows Nano Server. Vengono installate le immagini del sistema operativo contenitore e quindi la macchina virtuale è pronta per l'uso con Docker.Container OS images are installed, and then the VM is ready to use with Docker.

### <a name="benefits"></a>Vantaggi

Anche se i contenitori di Windows possono essere distribuiti nelle macchine virtuali Windows Server 2016 locali, quando si distribuisce in Azure, si ottiene un modo più semplice per iniziare, con macchine virtuali Windows Server Container pronte all'uso. Si ottiene anche una posizione online comune accessibile ai tester e scalabilità automatica tramite i set di scalabilità delle macchine virtuali di Azure.You also get a common online location that's accessible to testers, and automatic scalability through Azure virtual machine scale sets.

### <a name="next-steps"></a>Passaggi successivi

Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/06.-Deploying-your-Windows-Containers-based-app-into-Azure-VMs-(Including-CI-CD)>

## <a name="walkthrough-4-deploy-your-windows-containers-based-apps-to-azure-container-instances-aci"></a>Procedura dettagliata 4: Distribuire le app basate su contenitori di Windows in istanze di contenitori di Azure

### <a name="technical-walkthrough-availability"></a>Disponibilità della procedura dettagliata tecnica

La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:

[Distribuzione delle app in ACI (istanze del contenitore di Azure)Deploying the Apps to ACI (Azure Container Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

### <a name="overview"></a>Panoramica

[Le istanze del contenitore di Azure (ACI)](https://docs.microsoft.com/azure/container-instances/) è il modo più rapido per avere un ambiente di sviluppo/test/staging per i contenitori in cui è possibile distribuire singole istanze di contenitori.

### <a name="goals"></a>Obiettivi

Questa procedura dettagliata illustra gli scenari principali per la distribuzione di contenitori di Windows in istanze di contenitori di Azure (ACI) e come è possibile distribuire le app eShopModernizing in ACI.

### <a name="scenarios"></a>Scenari

Possono esserci variazioni sulla distribuzione delle app eShopModernizing in ACI, ad esempio la distribuzione di una o tutte le app (app MVC, app WebForms o servizio WCF). Nello scenario seguente illustrato di seguito è possibile visualizzare l'app MVC ASP.NET più il contenitore SQL Server entrambi distribuiti come contenitori in aCI (istanze del contenitore di Azure).

![Distribuire in ACI da un ambiente di sviluppoDeploy to ACI from a development environment](./media/image5-3.5.6.png)

### <a name="benefits"></a>Vantaggi

Istanze di Azure Container semplifica la creazione e gestione di contenitori Docker in Azure, senza dover eseguire il provisioning di macchine virtuali o di adottare un servizio di livello superiore. Con ACI, è possibile distribuire direttamente un contenitore Windows in Azure ed esporlo a Internet con un nome di dominio completo (FQDN) in pochi secondi (a condizione che l'immagine del contenitore di Windows sia pronta in un Registro di sistema Docker come Docker Hub o Azure Container registro).

### <a name="considerations"></a>Considerazioni

La distribuzione di contenitori di Windows con .NET Framework / ASP.NET completo o SQL Server in istanze di contenitori di Azure (ACI) non è così veloce come la distribuzione a un normale host Docker (come Windows Server 2016 con contenitori di Windows) perché l'immagine Docker deve essere scaricata (estratta dal Registro di sistema Docker) ogni volta e le dimensioni dell'immagine del contenitore SQL (15,1 GB) e l'immagine del contenitore ASP.NET (13,9 GB) sono significativamente in grandi dimensioni, e le dimensioni dell'immagine del contenitore SQL (15,1 GB) e l'immagine del contenitore ASP.NET (13,9 GB) sono in genere elevato, e le dimensioni dell'immagine del contenitore SQL (15,1 GB) e dell'immagine del contenitore di ASP.NET (13,9 GB) sono in genere elevato, tuttavia è molto più economico che mantenere il proprio host docker (permanentemente on-line Windows Server 2016 con VM contenitori Windows in Azure) per non parlare di un intero orchestratore come Kubernetes in Azure (AKS) che è, d'altra parte, un'ottima scelta per le distribuzioni di produzione.

Come conclusione principale, l'uso delle istanze di Azure Container è un'opzione molto interessante per gli scenari di sviluppo/test e per le pipeline CI/CD.

## <a name="next-steps"></a>Passaggi successivi

Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:

[https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances)](https://github.com/dotnet-architecture/eShopModernizing/wiki/05.-Deploying-the-Apps-to-ACI-(Azure-Container-Instances))

## <a name="walkthrough-5-deploy-your-windows-containers-based-apps-to-kubernetes-in-azure-container-service"></a>Procedura dettagliata 5: Distribuire le app basate su contenitori di Windows in Kubernetes nel servizio contenitore di AzureWalkthrough 5: Deploy your Windows Containers-based apps to Kubernetes in Azure Container Service

### <a name="technical-walkthrough-availability"></a>Disponibilità della procedura dettagliata tecnica

La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

### <a name="overview"></a>Panoramica

Un'applicazione basata su contenitori Windows dovrà rapidamente usare le piattaforme, allontanandosi ancora di più dalle macchine virtuali IaaS. Ciò è necessario per ottenere facilmente un'elevata scalabilità e una migliore scalabilità automatizzata e per un miglioramento significativo nelle distribuzioni automatizzate e nel controllo delle versioni. È possibile raggiungere questi obiettivi usando l'agente di orchestrazione [Kubernetes](https://kubernetes.io/), disponibile in [Servizi contenitore](https://azure.microsoft.com/services/container-service/)di Azure .

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è imparare a distribuire un'applicazione basata su contenitore Windows a Kubernetes (denominata anche *K8s*) nel servizio contenitore di Azure. La distribuzione a Kubernetes da zero è un processo in due fasi:

1. Distribuire un cluster Kubernetes nel servizio contenitore di Azure.Deploy a Kubernetes cluster to Azure Container Service.

2. Distribuire l'applicazione e le risorse correlate nel cluster Kubernetes.

### <a name="scenarios"></a>Scenari

#### <a name="scenario-a-deploy-directly-to-a-kubernetes-cluster-from-a-dev-environment"></a>Scenario A: Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppoScenario A: Deploy directly to a Kubernetes cluster from a dev environment

![Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppoDeploy directly to a Kubernetes cluster from a development environment](./media/image5-7.png)

**Figura 5-7.** Distribuire direttamente in un cluster Kubernetes da un ambiente di sviluppoDeploy directly to a Kubernetes cluster from a development environment

#### <a name="scenario-b-deploy-to-a-kubernetes-cluster-from-cicd-pipelines-in-azure-devops-services"></a>Scenario B: Deploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services

![Distribuire in un cluster Kubernetes da pipeline DI CI/CD nei servizi DevOps di AzureDeploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services](./media/image5-8.png)

**Figura 5-8.** Distribuire in un cluster Kubernetes da pipeline DI CI/CD nei servizi DevOps di AzureDeploy to a Kubernetes cluster from CI/CD pipelines in Azure DevOps Services

### <a name="benefits"></a>Vantaggi

La distribuzione in un cluster in Kubernetes offre numerosi vantaggi. Il vantaggio principale è che si ottiene un ambiente pronto per la produzione in cui è possibile scalare orizzontalmente l'applicazione in base al numero di istanze del contenitore che si desidera utilizzare (scalabilità interna nei nodi esistenti) e in base al numero di nodi o macchine virtuali nel cluster ( scalabilità globale del cluster).

Il servizio contenitore di Azure ottimizza gli strumenti e le tecnologie open source più diffusi in modo specifico per Azure.Azure Container Service optimizes popular open source tools and technologies specifically for Azure. Si ottiene una soluzione aperta che offre portabilità, sia per i contenitori che per la configurazione dell'applicazione. Selezionare la dimensione, il numero di host e gli strumenti dell'agente di orchestrazione-servizio contenitore gestisce tutto il resto.

Con Kubernetes, gli sviluppatori possono passare dal pensare alle macchine fisiche e virtuali, alla pianificazione di un'infrastruttura incentrata sui contenitori che facilita le seguenti funzionalità, tra le altre:

- Applicazioni basate su più contenitori

- Replica delle istanze del contenitore e ridimensionamento automatico orizzontaleReplicating container instances and horizontal autoscaling

- Denominazione e individuazione (ad esempio, DNS interno)

- Bilanciamento dei carichi

- Aggiornamenti in sequenza

- Distribuzione di segreti

- Controlli di integrità delle applicazioni

## <a name="next-steps"></a>Passaggi successivi

Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

## <a name="walkthrough-6-deploy-your-windows-containers-based-apps-to-azure-app-service-for-containers"></a>Procedura dettagliata 6: Distribuire le app basate su contenitori di Windows nel servizio app di Azure per i contenitoriWalkthrough 6: Deploy your Windows Containers-based apps to Azure App Service for Containers

### <a name="technical-walkthrough-availability"></a>Disponibilità della procedura dettagliata tecnica

La procedura dettagliata tecnica completa è disponibile nel wiki del repository gitHub di eShopModernizing:

<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

### <a name="overview"></a>Panoramica

Una semplice applicazione in contenitori che usa i contenitori di Windows può essere facilmente distribuita nel servizio app di Azure per i contenitori. Questo è l'approccio consigliato per la maggior parte delle applicazioni basate su contenitori di Windows.This is the recommended approach for most Windows Container-based applications.

### <a name="goals"></a>Obiettivi

L'obiettivo di questa procedura dettagliata è imparare a distribuire un'applicazione basata su Contenitore di Windows al servizio app di Azure per i contenitori da un Registro di sistema (Docker Hub o Registro contenitori di Azure).

### <a name="scenario"></a>Scenario

![Distribuire l'app basata su contenitori di Windows nel servizio app di Azure per i contenitoriDeploy Windows Container-based app to Azure App Service for Containers](./media/image5-11.png)

### <a name="benefits"></a>Vantaggi

La distribuzione nel servizio app di Azure per i contenitori offre i vantaggi dei contenitori associati ai vantaggi DiAS del servizio app di Azure.Deploying to Azure App Service for Containers offers the benefits of containers paired with the PaaS benefits of Azure App Service. Il servizio app può essere facilmente ridimensionato sia verticalmente che orizzontalmente e può essere configurato per la scalabilità automatica per soddisfare le mutevoli esigenze. Gli aggiornamenti possono essere eseguiti senza tempi di inattività e la configurazione della distribuzione continua da un Registro di sistema è facilmente configurabile.

## <a name="next-steps"></a>Passaggi successivi

Esplora questo contenuto in modo più approfondito sul wiki Di GitHub:<https://github.com/dotnet-architecture/eShopModernizing/wiki/Deploy-Windows-Container-to-Azure-App-Service>

> [!div class="step-by-step"]
> [Successivo](modernize-existing-apps-to-cloud-optimized/migrate-to-hybrid-cloud-scenarios.md)
> [precedente](conclusions.md) <!-- Next Chapter -->
