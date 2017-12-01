---
title: "Orchestrazione di microservizi e le applicazioni multi-contenitore per la scalabilità e disponibilità elevate"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Orchestrazione di microservizi e le applicazioni multi-contenitore per la scalabilità e disponibilità elevate"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ec33901a0ddc9e5b58263440b0e4399e687c6904
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrazione di microservizi e le applicazioni multi-contenitore per la scalabilità e disponibilità elevate

Utilizzare orchestrators per le applicazioni di ambiente di produzione è essenziale se l'applicazione è basata sul microservizi o semplicemente suddivisi tra più contenitori. Come descritto in precedenza, in un approccio basato su microservizio, ogni microservizio possiede il modello e i dati in modo che sia di un punto di vista di distribuzione e sviluppo. Tuttavia, anche se si dispone di un'applicazione più tradizionale è costituito da più servizi (ad esempio SOA), si disporrà di più contenitori o servizi che comprendono un'applicazione di business che devono essere distribuiti come un sistema distribuito. Questi tipi di sistemi sono complessi di scalabilità orizzontale e gestire; Pertanto, è indispensabile agente di orchestrazione se si desidera disporre di un'applicazione contenitore più ambienti di produzione e scalabile.

Figura 4-23 illustra la distribuzione in un cluster di un'applicazione composta da più microservizi (contenitori).

![](./media/image23.PNG)

**Figura 4-23**. Un cluster di contenitori

Si differenzia da un approccio logico. Ma, come bilanciamento carico di gestione, routing e la coordinazione questi composte da applicazioni?

Il motore Docker normale negli host Docker singolo soddisfa le esigenze di gestire le istanze di singola immagine in un host, ma ricadere breve per quanto riguarda la gestione dei contenitori più distribuiti su più host per le applicazioni distribuite complesse. Nella maggior parte dei casi, è necessario una piattaforma di gestione che verrà automaticamente contenitori, i contenitori di scalabilità orizzontale con più istanze per ogni immagine di avvio, sospenderli o spegnerle quando necessario e idealmente inoltre controllare la modalità con cui accedono alle risorse come la rete e i dati spazio di archiviazione.

Per andare oltre la gestione dei singoli contenitori o le app di comporre molto semplice e spostamento verso più grandi applicazioni aziendali con microservizi, è necessario attivare di orchestrazione e al clustering di piattaforme.

Da un'architettura e sviluppo punto di vista, se si sta compilando una grande impresa costituita da applicazioni basate su microservizi, è importante comprendere le piattaforme e i prodotti che supportano scenari avanzati seguenti:

**I cluster e orchestrators**. Quando è necessario scalare orizzontalmente le applicazioni attraverso numerosi host Docker, come quando un'applicazione basata su microservizio grandi dimensioni, è importante essere in grado di gestire tutti gli host come un singolo cluster mediante l'astrazione della complessità della piattaforma sottostante. Che rappresenta il cluster di contenitore e orchestrators fornire. Esempi di orchestrators sono Azure Service Fabric, Kubernetes, Docker Swarm e Mesosphere controller di dominio o sistema operativo. Le ultime tre orchestrators open source disponibili in Azure tramite il servizio contenitore di Azure.

**Utilità di pianificazione**. *Pianificazione* significa avere la funzionalità di un amministratore per avviare i contenitori in un cluster in modo oltre a fornire un'interfaccia utente. Un'utilità di pianificazione di cluster con responsabilità diverse: da usare in modo efficiente le risorse del cluster, per impostare i vincoli forniti dall'utente, ai contenitori di bilanciamento del carico in modo efficiente tra nodi o host e affidabile per dagli errori fornendo alto disponibilità.

I concetti di un cluster e un'utilità di pianificazione sono strettamente correlati, pertanto i prodotti disponibili da fornitori diversi spesso forniscono entrambi i set di funzionalità. Nell'elenco seguente viene illustrata la piattaforma più importante e scelte di software che disponibili per i cluster e le utilità di pianificazione. Questi orchestrators sono in genere disponibili in cloud pubblici, come Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Piattaforme software per il clustering di contenitore, orchestrazione e la pianificazione

Kubernetes

![https://PBS.twimg.com/Media/BT\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes è un prodotto open source che offre funzionalità che è compreso tra l'infrastruttura di cluster e il contenitore di programmazione alle funzionalità di orchestrazione. Consente di automatizzare la distribuzione, ridimensionamento e delle operazioni di contenitori di applicazioni per i cluster di host.
>
> Kubernetes fornisce un'infrastruttura incentrato sul contenitore che raggruppa i contenitori di applicazioni in unità logiche per facilità di gestione e l'individuazione.
>
> Kubernetes è obsoleta in Linux, è meno avanzata in Windows.

Sciame docker

![http://rancher.com/WP-Content/Themes/rancher-2016/Assets/Images/Swarm.PNG?v=2016-07-10-AM](./media/image25.png)

> Docker sciame consente di pianificare i contenitori di Docker e del cluster. Utilizzando sciame, è possibile trasformare un pool di host Docker in un singolo host Docker virtuale. I client possono effettuare le richieste di API per Swarm esattamente come che avviene per gli host, vale a dire che sciame consente alle applicazioni di adattarsi a più host.
>
> Sciame docker è un prodotto da Docker, la società.
>
> V 1.12 docker o in un secondo momento eseguire modalità nativa e incorporati Swarm.

Controller di dominio mesosphere/OS

![https://mesosphere.com/wp-content/uploads/2016/04/logo-Horizontal-Styled.PNG](./media/image26.png)

> Mesosphere Enterprise DC/OS (basato su Apache Mesos) è una piattaforma di ambiente di produzione per l'esecuzione di contenitori e le applicazioni distribuite.
>
> Controller di dominio/OS funziona tramite l'astrazione di una raccolta di risorse disponibili nel cluster e rendere tali risorse disponibili per i componenti compilati su di esso. Maratona viene in genere utilizzato come un'utilità di pianificazione integrata con controller di dominio o del sistema operativo.
>
> Controller di dominio o sistema operativo è avanzata in Linux, è meno avanzata in Windows.

Azure Service Fabric

![https://Azure.microsoft.com/svghandler/Service-fabric?Width=600&Height=315](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni. Si tratta di un [orchestrator](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e creato un cluster di macchine. Service Fabric è possibile distribuire servizi come contenitori o processi normali. È possibile anche combinazione servizi nei processi con i servizi in contenitori all'interno della stessa applicazione e del cluster.
>
> Service Fabric fornisce aggiuntive e facoltative rigorosa [modelli di programmazione di Service Fabric ](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) come [servizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).
>
> Service Fabric è avanzata in Windows (anni evoluzione di Windows), meno avanzata in Linux. 
> Contenitori di Linux e Windows sono supportati in Service Fabric dal 2017.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Utilizzo di orchestrators basate sul contenitore in Microsoft Azure

Diversi fornitori di cloud offrono il supporto di contenitori di Docker più cluster Docker e supporto di orchestrazione, tra cui Microsoft Azure, servizio di Amazon EC2 contenitore e il motore di contenitore di Google. Microsoft Azure supporta Docker cluster e orchestrator tramite servizio contenitore di Azure (ACS), come illustrato nella sezione successiva.

Un'altra opzione consiste nell'usare Microsoft Azure Service Fabric (un microservizi platform), che supporta anche Docker basato sui contenitori di Windows e Linux. Service Fabric in esecuzione in Azure o qualsiasi altro cloud ed esegue anche [locale](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Tramite il servizio contenitore di Azure

Un cluster di Docker pool più host Docker e li espone come un unico host Docker virtuale, pertanto è possibile distribuire più contenitori nel cluster. Il cluster consente di gestire tutte le funzionalità di gestione complesse, quali la scalabilità, integrità e così via. Figura 4-24 rappresenta la modalità di mapping per servizio contenitore di Azure (ACS) in un cluster di Docker per comporre applicazioni.

ACS fornisce un modo per semplificare la creazione, configurazione e gestione di un cluster di macchine virtuali che sono preconfigurati per l'esecuzione di applicazioni nei contenitori. Ottimizzare la configurazione di strumenti di pianificazione e l'orchestrazione open source più diffusi, ACS consente di usare le competenze esistenti o creare un corpo elevato e crescente di esperienza della community per distribuire e gestire applicazioni basate sul contenitore in Microsoft Azure .

Il servizio contenitore di Azure consente di ottimizzare la configurazione di comuni strumenti di Docker clustering open source e tecnologie in modo specifico per Azure. È possibile ottenere una soluzione aperta che offre la portabilità per i contenitori e configurazione dell'applicazione. Si seleziona la dimensione, il numero di host e gli strumenti di orchestrator e il servizio contenitore gestisce tutto il resto.

![](./media/image28.png)

**Figura 4-24**. Clustering scelte contenitore nel servizio di Azure

ACS sfrutta le immagini Docker per assicurarsi che i contenitori di applicazioni siano completamente portabili. Supporta la scelta delle piattaforme open source orchestrazione come controller di dominio o del sistema operativo (con tecnologia Mesos Apache), Kubernetes (originariamente creato da Google) e Docker Swarm, per garantire che queste applicazioni possono essere ridimensionate a migliaia o persino decine di migliaia di contenitori.

Il servizio contenitore di Azure consente di sfruttare le funzionalità di livello aziendale di Azure mantenendo al tempo stesso la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

![](./media/image29.png)

**Figura 4-25**. Orchestrators in ACS

Come illustrato nella figura 4-25, il servizio contenitore di Azure è semplicemente l'infrastruttura fornita da Azure per distribuire i controller di dominio/OS, Kubernetes o Docker Swarm, ma ACS non implementa alcun orchestrator aggiuntive. Pertanto, ACS non è un agente di orchestrazione di conseguenza, solo un'infrastruttura che sfrutta esistente orchestrators open source per i contenitori.

Dal punto di vista dell'utilizzo, l'obiettivo di servizio di contenitore di Azure è fornire un ambiente host del contenitore usando tecnologie e strumenti open source più diffusi. A tal fine, che espone gli endpoint API standard per la scelta orchestrator. Tramite questi endpoint, è possibile utilizzare qualsiasi software in grado di comunicare con gli endpoint. Ad esempio, nel caso l'endpoint Docker Swarm, è possibile utilizzare l'interfaccia della riga di comando di Docker (CLI). Per controller di dominio o del sistema operativo, è possibile scegliere di utilizzare l'interfaccia CLI di controller di dominio o del sistema operativo.

### <a name="getting-started-with-azure-container-service"></a>Introduzione al servizio di contenitore di Azure 

Per iniziare a utilizzare il servizio contenitore di Azure, si distribuisce un cluster il servizio contenitore di Azure dal portale di Azure utilizzando un modello di gestione risorse di Azure o [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). I modelli disponibili includono [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes), e [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). Per includere la configurazione di Azure aggiuntiva o avanzata, è possono modificare i modelli di avvio rapido. Per ulteriori informazioni sulla distribuzione di un cluster il servizio contenitore di Azure, vedere [distribuire un cluster il servizio contenitore di Azure](https://docs.microsoft.com/azure/container-service/container-service-deployment) sul sito Web di Azure.

Sono non state tariffe per tutti i software installati per impostazione predefinita come parte del servizio ACS. Tutte le opzioni predefinite sono implementate con software open source.

ACS è attualmente disponibile per la serie di Standard A, D, DS, G e GS macchine virtuali Linux in Azure. Viene addebitato solo per le istanze di calcolo che si sceglie, nonché altri infrastruttura risorse sottostanti utilizzate, ad esempio l'archiviazione e rete. Non sono previsti costi incrementali per ACS se stesso.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Introduzione a soluzioni con il servizio contenitore di Azure contenitore Docker**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro)

-   **Panoramica di docker sciame**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)

-   **Panoramica sulla modalità di Swarm**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)

-   **Panoramica di controller di dominio/OS mesosphere**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/)

-   **Kubernetes.** Il sito ufficiale. \
    [*http://kubernetes.IO/*](http://kubernetes.io/)


>[!div class="step-by-step"]
[Precedente] (resilienti-elevata-disponibilità-microservices.md) [Avanti] (con-azure-servizio-fabric.md)
