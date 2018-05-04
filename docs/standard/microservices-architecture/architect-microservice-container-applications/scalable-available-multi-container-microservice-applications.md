---
title: Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c484372c0b5626fc20c8991a432e62353baa7a4c
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate

L'uso di agenti di orchestrazione per applicazioni pronte per la produzione è essenziale se l'applicazione è basata su microservizi o semplicemente suddivisa tra più contenitori. Come illustrato in precedenza, in un approccio basato su microservizi ogni microservizio è proprietario dei rispettivi modelli e dati, quindi sarà autonomo dal punto di vista dello sviluppo e della distribuzione. Anche se è disponibile un'applicazione più tradizionale costituita da più servizi, ad esempio SOA, saranno comunque disponibili più contenitori o servizi che comprendono una singola applicazione aziendale da distribuire come sistema distribuito. Il ridimensionamento e la gestione di questi tipi di sistemi sono complessi ed è quindi assolutamente necessario un agente di orchestrazione se si vuole ottenere un'applicazione a più contenitori pronta per la produzione e ridimensionabile.

La figura 4-23 illustra la distribuzione in un cluster di un'applicazione costituita da più microservizi (contenitori).

![](./media/image23.PNG)

**Figura 4-23**. Cluster di contenitori

Si tratta di un approccio apparentemente logico. Occorre tuttavia stabilire come vengono gestiti il bilanciamento del carico, il routing e l'orchestrazione di queste applicazioni.

Il semplice motore Docker in host Docker singoli soddisfa le esigenze di gestione di istanze singole per immagine su un host, ma non è sufficiente in caso di gestione di più contenitori distribuiti su più host per applicazioni distribuite più complesse. Nella maggior parte dei casi è necessaria una piattaforma di gestione in grado di avviare automaticamente i contenitori, ridimensionare i contenitori con più istanze per immagine, sospenderli o arrestarli in caso di necessità e idealmente controllare anche la rispettiva modalità di accesso a risorse come la rete e l'archiviazione dati.

Per passare a un livello superiore rispetto alla gestione di singoli contenitori o app composte molto semplici e gestire ad applicazioni aziendali di dimensioni maggiori con microservizi, è necessario usare l'orchestrazione e le piattaforme di clustering.

Dal punto di vista dell'architettura e dello sviluppo, se si creano applicazioni aziendali composte di grandi dimensioni e basate su microservizi, è importante comprendere le piattaforme e i prodotti seguenti che supportano gli scenari avanzati:

**Cluster e agenti di orchestrazione**. Quando è necessario aumentare il numero di istanze delle applicazioni in molti host Docker, ad esempio nel caso di un'applicazione di grandi dimensioni basata su microservizi, è essenziale poter gestire tutti questi host come un singolo cluster tramite l'astrazione della complessità della piattaforma sottostante. I cluster di contenitori e gli agenti di orchestrazione offrono questo vantaggio. Alcuni agenti di orchestrazione disponibili sono Azure Service Fabric, Kubernetes, Docker Swarm e Mesosphere DC/OS. Gli ultimi tre agenti di orchestrazione open source sono disponibili in Azure tramite il servizio contenitore di Azure.

**Utilità di pianificazione**. Per *pianificazione* si intende la possibilità per un amministratore di avviare contenitori in un cluster in modo che forniscano anche un'interfaccia utente. Un'utilità di pianificazione di cluster ha molte responsabilità, tra cui usare in modo efficiente le risorse del cluster, configurare i vincoli forniti dall'utente, bilanciare in modo efficiente il carico dei contenitori nei nodi e negli host e infine assicurare l'affidabilità in caso di errori, offrendo al tempo stesso una disponibilità elevata.

I concetti di cluster e utilità di pianificazione sono strettamente correlati, quindi i prodotti offerti da diversi fornitori includono spesso entrambi i set di funzionalità. L'elenco seguente mostra le opzioni più importanti a livello di piattaforma e software disponibili per i cluster e per le utilità di pianificazione. Questi agenti di orchestrazione sono in genere offerti in cloud pubblici quali Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Piattaforme software per il clustering, l'orchestrazione e la pianificazione dei contenitori

Kubernetes

![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image24.png)

> Kubernetes è un prodotto open source che offre funzionalità per l'infrastruttura dei cluster, la pianificazione dei contenitori e l'orchestrazione. Consente di automatizzare la distribuzione, il ridimensionamento e la gestione di contenitori di applicazioni in cluster di host.
>
> Kubernetes offre un'infrastruttura incentrata sui contenitori che raggruppa i contenitori di applicazioni in unità logiche per semplificarne la gestione e l'individuazione.
>
> Kubernetes è maturo in Linux, meno maturo in Windows.

Docker Swarm

![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image25.png)

> Docker Swarm consente di creare cluster e pianificazioni per i contenitori Docker. Tramite Swarm è possibile trasformare un pool di host Docker in un singolo host Docker virtuale. I client possono inviare richieste API a Swarm con una procedura analoga a quella per gli host. Swarm semplifica infatti il ridimensionamento delle applicazioni in più host.
>
> Docker Swarm è un prodotto dell'azienda Docker.
>
> Docker v1.12 o versioni successive può eseguire la modalità Swarm nativa e predefinita.

Mesosphere DC/OS

![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image26.png)

> Mesosphere Enterprise DC/OS, basata su Apache Mesos, è una piattaforma pronta per la produzione per l'esecuzione di contenitori e applicazioni distribuite.
>
> DC/OS esegue l'astrazione di una raccolta delle risorse disponibili nel cluster e le rende disponibili ai componenti basati su di esso. Marathon viene in genere usato come utilità di pianificazione integrata con DC/OS.
>
> DC/OS è maturo in Linux, meno maturo in Windows.

Azure Service Fabric

![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image27.png)

> [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni. È un [agente di orchestrazione](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e crea cluster di macchine virtuali. Service Fabric può distribuire servizi come contenitori o come processi semplici. Può anche combinare servizi nei processi con servizi nei contenitori entro la stessa applicazione e lo stesso cluster.
>
> Service Fabric offre [modelli di programmazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) prescrittivi aggiuntivi e facoltativi, come [servizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).
>
> Service Fabric è maturo in Windows (anni di evoluzione in Windows), meno maturo in Linux. 
> I contenitori Linux e Windows sono supportati in Service Fabric dal 2017.

## <a name="using-container-based-orchestrators-in-microsoft-azure"></a>Uso degli agenti di orchestrazione basati su contenitori in Microsoft Azure

Alcuni fornitori cloud, tra cui Microsoft Azure, Amazon EC2 Container Service e Google Container Engine, offrono il supporto per contenitori Docker oltre al supporto per i contenitori e l'agente di orchestrazione Docker. Microsoft Azure offre il supporto per cluster e agente di orchestrazione Docker tramite il servizio contenitore di Azure, come illustrato nella sezione successiva.

È anche possibile usare Microsoft Azure Service Fabric, una piattaforma di microservizi, che supporta contenitori Linux e Windows basati su Docker. È possibile eseguire Service Fabric in Azure o in qualsiasi altro cloud e anche [in locale](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Uso del servizio contenitore di Azure

Un cluster Docker crea pool di host Docker e li espone come un singolo host Docker virtuale, per consentire di distribuire più contenitori nel cluster. Il cluster gestirà tutte le operazioni di gestione complesse, ad esempio la scalabilità, l'integrità e così via. La figura 4-24 rappresenta il mapping di un cluster Docker per applicazioni composte al servizio contenitore di Azure.

Il servizio contenitore di Azure consente di semplificare la creazione, la configurazione e la gestione di un cluster di macchine virtuali preconfigurate per l'esecuzione di applicazioni in contenitori. Usando una configurazione ottimizzata degli strumenti open source più diffusi per la pianificazione e l'orchestrazione, il servizio contenitore di Azure consente di usare le competenze esistenti o di avvalersi delle vaste competenze in continua crescita della community per distribuire e gestire le applicazioni basate su contenitori in Microsoft Azure.

Il servizio contenitore di Azure ottimizza la configurazione degli strumenti e delle tecnologie open source più diffusi per clustering Docker in modo specifico per Azure. Si ottiene una soluzione che offre la portabilità per la configurazione di contenitori e applicazioni. È sufficiente selezionare le dimensioni, il numero di host e gli strumenti dell'agente di orchestrazione. Il servizio contenitore gestisce tutte le altre operazioni.

![](./media/image28.png)

**Figura 4-24**. Opzioni per il clustering nel servizio contenitore di Azure

Il servizio contenitore di Azure sfrutta i vantaggi delle immagini Docker per assicurare la portabilità completa dei contenitori delle applicazioni. Supporta qualsiasi piattaforma di orchestrazione open source, tra cui DC/OS (con tecnologia Apache Mesos), Kubernetes (creato in origine da Google) e Docker Swarm, per assicurare che queste applicazioni possano essere ridimensionate fino a migliaia o decine di migliaia di contenitori.

Il servizio contenitore di Azure consente di sfruttare i vantaggi delle funzionalità di livello aziendale di Azure, mantenendo al tempo stesso la portabilità delle applicazioni, inclusi i livelli di orchestrazione.

![](./media/image29.png)

**Figura 4-25**. Agenti di orchestrazione nel servizio contenitore di Azure

Come illustrato nella figura 4-25, il servizio contenitore di Azure è semplicemente l'infrastruttura fornita da Azure per distribuire DC/OS, Kubernetes o Docker Swarm, ma non implementa alcun agente di orchestrazione aggiuntivo. Il servizio contenitore di Azure non è quindi un agente di orchestrazione. Si tratta solo di un'infrastruttura che sfrutta i vantaggi degli agenti di orchestrazione open source esistenti per i contenitori.

Dal punto di vista dell'utilizzo, l'obiettivo del servizio contenitore di Azure consiste nel fornire un ambiente di hosting di contenitori tramite strumenti e tecnologie open source più diffusi. A questo scopo, espone gli endpoint API standard per l'agente di orchestrazione scelto. Usando questi endpoint, è possibile sfruttare i vantaggi di qualsiasi software in grado di comunicare con tali endpoint. Ad esempio, nel caso dell'endpoint di Docker Swarm è possibile scegliere di usare l'interfaccia della riga di comando di Docker. Per DC/OS è possibile scegliere di usare l'interfaccia della riga di comando di DC/OS.

### <a name="getting-started-with-azure-container-service"></a>Iniziare a usare il servizio contenitore di Azure 

Per iniziare a usare il servizio contenitore di Azure, distribuire un cluster del servizio contenitore di Azure dal portale di Azure tramite un modello di Azure Resource Manager o l'[interfaccia della riga di comando](https://docs.microsoft.com/cli/azure/install-azure-cli). I modelli disponibili includono [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) e [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). I modelli della guida introduttiva possono essere modificati per includere impostazioni di configurazione aggiuntive o avanzate di Azure. Per altre informazioni sulla distribuzione di un cluster del servizio contenitore di Azure, vedere [Distribuire un cluster del servizio contenitore di Azure](https://docs.microsoft.com/azure/container-service/container-service-deployment) nel sito Web Azure.

Non sono previsti addebiti per il software installato per impostazione predefinita come parte del servizio contenitore di Azure. Tutte le opzioni predefinite vengono implementate con software open source.

Il servizio contenitore di Azure è attualmente disponibile per macchine virtuali Linux Standard di serie A, D, DS, G e GS in Azure. Non vengono applicati addebiti per le istanze di risorse di calcolo scelte, oltre che per le altre risorse di infrastruttura sottostanti usate, ad esempio per le risorse di archiviazione e di rete. Non sono previsti inoltre addebiti incrementali per il servizio contenitore di Azure.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Introduction to Docker container hosting solutions with Azure Container Service**
    [*https://docs.microsoft.com/azure/container-service/container-service-intro*](https://docs.microsoft.com/azure/container-service/container-service-intro) (Introduzione alle soluzioni di hosting del contenitore Docker con servizio contenitore di Azure)

-   **Docker Swarm overview**
    [*https://docs.docker.com/swarm/overview/*](https://docs.docker.com/swarm/overview/)(Panoramica di Docker Swarm)

-   **Swarm mode overview**
    [*https://docs.docker.com/engine/swarm/*](https://docs.docker.com/engine/swarm/)(Panoramica della modalità Swarm)

-   **Mesosphere DC/OS Overview**
    [*https://docs.mesosphere.com/1.7/overview/*](https://docs.mesosphere.com/1.7/overview/) (Panoramica di Mesosphere DC/OS)

-   **Kubernetes.** Sito ufficiale.\
    [*https://kubernetes.io/*](https://kubernetes.io/)


>[!div class="step-by-step"]
[Indietro] (resilient-high-availability-microservices.md) [Avanti] (using-azure-service-fabric.md)
