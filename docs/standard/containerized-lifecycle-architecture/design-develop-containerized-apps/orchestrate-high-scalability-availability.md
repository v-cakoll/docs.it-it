---
title: Orchestrazione di microservizi e multicontainer applicazioni per la scalabilità e disponibilità elevate
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 3a505e10b2a37032a7ccfefdf4a6f4bb64d65486
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Orchestrazione di microservizi e multicontainer applicazioni per la scalabilità e disponibilità elevate

L'uso di agenti di orchestrazione per applicazioni pronte per la produzione è essenziale se l'applicazione è basata su microservizi o semplicemente suddivisa tra più contenitori. Come illustrato in precedenza, in un approccio basato su microservizi ogni microservizio è proprietario dei rispettivi modelli e dati, quindi sarà autonomo dal punto di vista dello sviluppo e della distribuzione. Ma anche se si dispone di un'applicazione più tradizionale è costituito da più servizi (ad esempio SOA), è inoltre più contenitori o servizi che comprendono un'applicazione di business che devono essere distribuiti come un sistema distribuito. Questi tipi di sistemi sono complessi di scalabilità orizzontale e gestire; Pertanto, è indispensabile agente di orchestrazione se si desidera disporre di un'applicazione multicontainer ambiente di produzione e scalabile.

Figura 4-6 viene illustrata la distribuzione in un cluster di un'applicazione composta da più microservizi (contenitori).

![](./media/image6.png)

Figura 4-6: un cluster di contenitori

Si tratta di un approccio apparentemente logico. Ma, come si gestisce il bilanciamento del carico, routing e orchestrazione di queste applicazioni composte?

L'interfaccia della riga di comando di Docker (CLI) soddisfa le esigenze di gestione di un contenitore in un host, ma ricadere breve per quanto riguarda la gestione dei contenitori più distribuiti su più host per le applicazioni distribuite complesse. Nella maggior parte dei casi, è necessario una piattaforma di gestione che verrà automaticamente avviare contenitori, sospendere, o spegnerle quando necessario e idealmente inoltre controllare come accedono a risorse quali l'archiviazione di dati e di rete.

Per passare a un livello superiore rispetto alla gestione di singoli contenitori o app composte molto semplici e gestire ad applicazioni aziendali di dimensioni maggiori con microservizi, è necessario usare l'orchestrazione e le piattaforme di clustering.

Da un'architettura e sviluppo punto di vista, in caso di compilazione, grandi, in base microservizi, applicazioni, è importante comprendere le piattaforme e i prodotti che supportano scenari avanzati seguenti:

-   **I cluster e orchestrators** quando è necessario ridimensionare-out le applicazioni attraverso numerosi host Docker, ad esempio con un'applicazione basata su microservizi grandi dimensioni, è fondamentale per essere in grado di gestire tutti gli host come un singolo cluster da fornire l'astrazione della complessità della piattaforma sottostante. I cluster di contenitori e gli agenti di orchestrazione offrono questo vantaggio. Esempi di orchestrators sono Docker Swarm Mesosphere DC/OS, Kubernetes (i primi tre disponibili tramite il servizio contenitore di Azure) e Azure Service Fabric.

-   **Utilità di pianificazione** *pianificazione* significa avere la funzionalità di un amministratore per avviare i contenitori in un cluster in modo che, oltre a fornire un'interfaccia utente. Un'utilità di pianificazione di cluster con responsabilità diverse: da usare in modo efficiente le risorse del cluster, per impostare i vincoli forniti dall'utente, ai contenitori di bilanciamento del carico in modo efficiente tra nodi o host e affidabile per dagli errori fornendo alto disponibilità.

I concetti di cluster e utilità di pianificazione sono strettamente correlati, quindi i prodotti offerti da diversi fornitori includono spesso entrambi i set di funzionalità. Tabella 4-1 Elenca la piattaforma più importante e scelte di software che disponibili per i cluster e le utilità di pianificazione. Questi cluster sono in genere disponibili in cloud pubblici, come Azure.

Tabella 4-1: piattaforme di Software per il clustering di contenitore, orchestrazione e la pianificazione

| Piattaforma | Descrizione |
|---|---|
| Docker Swarm<br/> ![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image7.png) | Docker sciame offre la possibilità di inserire nel cluster e pianificare i contenitori di Docker. Tramite Swarm è possibile trasformare un pool di host Docker in un singolo host Docker virtuale. I client possono effettuare richieste di API al sciame nello stesso modo che agli host, vale a dire che sciame semplifica per la scalabilità delle applicazioni a più host. <br /><br /> Docker Swarm è un prodotto dell'azienda Docker. <br /><br /> Docker v1.12 o versioni successive può eseguire la modalità Swarm nativa e predefinita. |
| Mesosphere DC/OS<br/>![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image8.png) |  Mesosphere Enterprise DC/OS, basata su Apache Mesos, è una piattaforma pronta per la produzione per l'esecuzione di contenitori e applicazioni distribuite. <br /><br /> DC/OS esegue l'astrazione di una raccolta delle risorse disponibili nel cluster e le rende disponibili ai componenti basati su di esso. Marathon viene in genere usato come utilità di pianificazione integrata con DC/OS. |
| Kubernetes di Google<br />![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image9.png) | Kubernetes è un prodotto open source che offre funzionalità per l'infrastruttura dei cluster, la pianificazione dei contenitori e l'orchestrazione. Con questa soluzione, è possibile automatizzare operazioni di contenitori di applicazioni, scalabilità e la distribuzione per i cluster di host. <br /><br /> Kubernetes offre un'infrastruttura incentrata sui contenitori che raggruppa i contenitori di applicazioni in unità logiche per semplificarne la gestione e l'individuazione. |
| Azure Service Fabric<br />![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni. È un [agente di orchestrazione](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e crea cluster di macchine virtuali. Per impostazione predefinita, Service Fabric distribuisce e Attiva servizi come processi, ma Service Fabric è possibile distribuire servizi immagini contenitore con Docker. Più importante, è possibile combinare i servizi in processi con i servizi in contenitori nella stessa applicazione. <br /><br /> A partire da maggio 2017, la funzionalità dell'infrastruttura di servizio che supporta i servizi di distribuzione come contenitori di Docker è in stato di anteprima. <br /><br /> È possibile sviluppare servizi Service Fabric in diversi modi, mediante il [modelli di programmazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) alla distribuzione [eseguibili guest](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) nonché contenitori. Service Fabric supporta i modelli di applicazione rigorosa come [servizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>In Azure usando orchestrators basate sul contenitore

Diversi fornitori di cloud offrono il supporto di contenitori di Docker più cluster Docker e supporto di orchestrazione, tra cui Azure, servizio di Amazon EC2 contenitore e il motore di contenitore di Google. Supporto di cluster e orchestrator tramite il servizio contenitore di Azure, Azure offre Docker, come illustrato nella sezione successiva.

Un'altra opzione consiste nell'utilizzare Azure Service Fabric, che supporta anche Docker basato sui contenitori di Windows e Linux. Infrastruttura del servizio viene eseguito in Azure o in altri cloud nonché [locale](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Uso del servizio contenitore di Azure

Un cluster Docker crea pool di host Docker e li espone come un singolo host Docker virtuale, per consentire di distribuire più contenitori nel cluster. Il cluster consente di gestire tutte le funzionalità di gestione complesse come scalabilità e l'integrità. Figura 4-7 rappresenta il mapping di un cluster di Docker per comporre applicazioni al servizio di contenitore.

Il servizio contenitore fornisce un modo per semplificare la creazione, configurazione e gestione di un cluster di macchine virtuali che sono preconfigurati per l'esecuzione di applicazioni nei contenitori. Utilizza una configurazione ottimizzata di strumenti di pianificazione e l'orchestrazione open source più diffusi, il servizio contenitore offre la possibilità di usare le competenze esistenti o disegnare un corpo elevato e crescente di esperienza della community per distribuire e gestire basate sul contenitore applicazioni in Azure.

Il servizio contenitore consente di ottimizzare la configurazione di comuni strumenti di Docker clustering open source e tecnologie in modo specifico per Azure. Si ottiene una soluzione che offre la portabilità per la configurazione di contenitori e applicazioni. È sufficiente selezionare le dimensioni, il numero di host e gli strumenti dell'agente di orchestrazione. Il servizio contenitore gestisce tutte le altre operazioni.

Servizio contenitore utilizza le immagini Docker per assicurarsi che i contenitori di applicazioni siano completamente portabili. Supporta la scelta delle piattaforme open source orchestrazione come controller di dominio o del sistema operativo, Kubernetes e Docker Swarm per garantire che queste applicazioni adattabile a migliaia o persino decine di migliaia di contenitori.

Con il servizio contenitore di Azure, è possibile sfruttare le funzionalità di livello aziendale di Azure mantenendo al tempo stesso la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

![](./media/image11.png)

Figura 4-7: Clustering scelte contenitore nel servizio di Azure

Come illustrato nella figura 4-8, il servizio contenitore è semplicemente l'infrastruttura fornita da Azure per distribuire i controller di dominio/OS, Kubernetes o Docker Swarm, ma non implementa alcun orchestrator aggiuntive. Di conseguenza, il servizio contenitore è non agente di orchestrazione, di conseguenza; è solo un'infrastruttura che consente di sfruttare orchestrators open source esistente per i contenitori.

![](./media/image12.png)

Figura 4-8: Orchestrators nel servizio contenitore

Dal punto di vista dell'utilizzo, l'obiettivo di servizio di contenitore è fornire un ambiente host del contenitore usando tecnologie e strumenti open source più diffusi. A questo scopo, espone gli endpoint API standard per l'agente di orchestrazione scelto. Tramite questi endpoint, è possibile utilizzare qualsiasi software che può comunicare con gli endpoint. Ad esempio, nel caso l'endpoint Docker Swarm, è possibile utilizzare l'interfaccia CLI di Docker. Per DC/OS è possibile scegliere di usare l'interfaccia della riga di comando di DC/OS.

### <a name="getting-started-with-container-service"></a>Introduzione al servizio contenitore

Per iniziare a utilizzare il servizio di contenitore, si distribuisce un cluster il servizio contenitore dal portale di Azure utilizzando un modello di gestione risorse di Azure o [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). I modelli disponibili includono [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) e [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). È possibile modificare i modelli di avvio rapido per includere la configurazione di Azure aggiuntivo o avanzata.

**Altre informazioni** per ulteriori informazioni sulla distribuzione di un cluster del servizio di contenitore, nel sito Web di Azure, leggere [distribuire un cluster il servizio contenitore di Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

Non sono previsti addebiti per il software installato per impostazione predefinita come parte del servizio contenitore di Azure. Tutte le opzioni predefinite vengono implementate con software open source.

Il servizio contenitore è attualmente disponibile per le macchine virtuali Linux in Azure GS serie, D, di dominio Active Directory, G e A Standard. Viene addebitato solo per le istanze di calcolo che scelte e altre infrastrutture risorse sottostanti utilizzate, ad esempio l'archiviazione e rete. Non vi sono incrementali addebiti per il servizio contenitore stesso.

### <a name="additional-resources"></a>Risorse aggiuntive

Di seguito sono percorsi in cui è possibile trovare ulteriori informazioni:

-   Introduzione al contenitore Docker hosting soluzioni con il servizio contenitore:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Panoramica di docker sciame:  
    <https://docs.docker.com/swarm/overview/>

-   Panoramica sulla modalità di Swarm:  
    <https://docs.docker.com/engine/swarm/>

-   Panoramica di controller di dominio/OS mesosphere:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (sito ufficiale):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Utilizzo di Service Fabric

Si è verificato Service Fabric dalla transizione Microsoft da distribuire i prodotti di "casella", che erano in genere monolitici in stile, alla fornitura di servizi. L'esperienza di creare e gestire i servizi su larga scala, ad esempio Database SQL di Azure, database di documenti di Azure, Azure Service Bus o back-end di Cortana, la forma di Service Fabric. La piattaforma si è evoluta nel tempo con la sua continua adozione da parte di un numero crescente di servizi. Cosa ancora più importante, Service Fabric doveva essere eseguito non solo in Azure, ma anche nelle distribuzioni autonome di Windows Server.

L'obiettivo di Service Fabric è per risolvere i problemi di difficile della compilazione e l'esecuzione di un servizio e utilizzano risorse di infrastruttura in modo efficiente in modo che i team di risolvere i problemi di business utilizzando un approccio di microservizi.

Service Fabric fornisce due aree generali che consentono di creare applicazioni che usano un approccio ai microservizi:

-   Una piattaforma che fornisce servizi di sistema per distribuire, ridimensionare, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema in effetti forniscono molte delle caratteristiche di microservizi descritto in precedenza.

-   API di programmazione, o framework, che aiutano a creare applicazioni come microservizi: [Reliable Actors e Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Naturalmente, è possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API semplificano il processo e si integrano nella piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

Service Fabric è agnostico rispetto al modo in cui si crea il servizio ed è possibile usare qualsiasi tecnologia. Tuttavia, fornisce API di programmazione predefinite che rendono più semplice creare i microservizi.

Figura 4-9 viene illustrato come creare ed eseguire microservizi nell'infrastruttura del servizio come processi semplici o come contenitori di Docker. È anche possibile combinare microservizi basati su contenitori con microservizi basati su processi all'interno dello stesso cluster di Service Fabric.

![](./media/image13.png)

Figura 4-9: distribuzione di microservizi come processi o come contenitori in Azure Service Fabric

Cluster di Service Fabric in base alle host Linux e Windows è possibile eseguire i contenitori di Docker Linux e Windows.

**Altre informazioni** per informazioni aggiornate sul supporto di contenitori nell'infrastruttura del servizio, nel sito Web di Azure, leggere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di una piattaforma a cui è possibile definire una diversa architettura logica (business microservizi o contesti limitata) rispetto all'implementazione fisica. Ad esempio, se si implementa [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), che vengono introdotti nella sezione successiva, "[Stateless e con stato microservizi](#stateless-versus-stateful-microservices), "è un concetto microservizio business con più servizi fisici.

Come illustrato nella figura 4-10 e il concetto da una prospettiva di logica di business/microservizio, quando si implementa un servizio con stato affidabile Service Fabric, in genere sarà necessario implementare due livelli di servizi. Il primo è il servizio back-end con stato affidabile, che gestisce più partizioni. Il secondo è il servizio front-end, o Servizio gateway, responsabile del routing e dell'aggregazione dei dati in più partizioni o istanze del servizio con stato. Servizio Gateway gestisce inoltre la comunicazione client-side con i cicli di ripetizione l'accesso al servizio back-end utilizzato in combinazione con l'infrastruttura del servizio [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Figura 4-10: Business microservizio con diversi servizi senza stati e informazioni sullo stato in Service Fabric

In ogni caso, quando si usano i servizi Reliable con stato di Service Fabric, si ottiene anche un microservizio logico o aziendale (Bounded Context) che in genere è costituito da più servizi fisici. Ognuno di essi, il servizio Gateway e servizio partizione potrebbe essere implementato come servizi API Web ASP.NET, come illustrato nella figura 4-10.

In Service Fabric, è possibile raggruppare e distribuire gruppi di servizi come [Applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), cioè l'unità di creazione pacchetto e distribuzione per l'agente di orchestrazione o il cluster. L'applicazione dell'infrastruttura del servizio, pertanto potrebbe essere mappato a questo aziendali autonome e limite logico microservizio o contesto delimitata, nonché.

### <a name="service-fabric-and-containers"></a>Service Fabric e contenitori

Per quanto riguarda i contenitori nell'infrastruttura del servizio, è anche possibile distribuire servizi nelle immagini contenitore all'interno di un cluster di Service Fabric. Figura 4-11 viene illustrato che la maggior parte dei casi sarà presente solo un contenitore per ogni servizio.

![](./media/image15.png)

Figura 4-11: Business microservizio con diversi servizi (contenitori) di Service Fabric

Tuttavia, sono inoltre disponibili in Service Fabric contenitori cosiddetti "car" (due contenitori che devono essere distribuiti insieme come parte di un servizio logico). La cosa importante è che un microservizio aziendale è rappresentato dal limite logico intorno a diversi elementi coesivi. In molti casi, potrebbe essere un singolo servizio con un singolo modello di dati, ma potrebbe essere fisici diversi servizi, nonché in altri casi.

A partire da questa scrittura (aprile 2017), nell'infrastruttura del servizio non è possibile distribuire servizi con stato affidabili SF sui contenitori, è possibile distribuire solo contenitori guest, i servizi senza stati o i servizi actor di contenitori. Ma si noti che è possibile combinare i servizi nei processi e servizi nei contenitori nella stessa applicazione di Service Fabric, come illustrato nella figura 4-12.

![](./media/image16.png)

Figura 4-12: Business microservizio mappato a un'applicazione di Service Fabric con contenitori e i servizi con stati

Supporto è diverso a seconda che si utilizzi contenitori Docker sui contenitori di Windows o Linux. Verrà aperto il supporto per i contenitori di Service Fabric nelle prossime versioni. Per le notizie aggiornate sul supporto di contenitore nell'infrastruttura del servizio, nel sito Web di Azure, leggere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservizi con stato e senza stato

Come accennato in precedenza, ogni microservizio (Bounded Context logico) deve essere proprietario di un modello di dominio (dati e logica). Nel caso di microservizi senza stato, i database verranno esterni, avvalendosi di opzioni relazionale come SQL Server o le opzioni di database NoSQL come MongoDB o Azure DocumentDB.

Ma i servizi stessi inoltre possono essere con stati, il che significa che i dati si trovano all'interno di microservizio. I dati potrebbero esistere non solo nello stesso server, ma all'interno del processo microservizio, in memoria e persistenti nell'unità e replicate in altri nodi. Figura 4-13 illustra i diversi approcci.

![](./media/image17.png)

Figura 4-13: senza stato e informazioni sullo stato microservizi

Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto a microservizi con stato perché l'approccio è simile ai modelli tradizionali e noti. Tuttavia, i microservizi senza stato impongono la latenza tra il processo e le origini dati, oltre a comportare più elementi quando si prova a migliorare le prestazioni con cache e code aggiuntive. Il risultato è che si può finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, [microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possibile di excel in scenari avanzati in quanto non è prevista una latenza tra la logica di dominio e i dati. Back-end giochi elevato, l'elaborazione di dati, come un servizio e altri scenari di bassa latenza i vantaggi offerti dai servizi con stati, che forniscono lo stato locale di un accesso più rapido di database.

I servizi con e senza stato sono complementari. Ad esempio, un servizio con stato può essere suddivisi in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisca come servizio gateway che sappia come risolvere ogni partizione in base alle chiavi di partizione.

I servizi con stato presentano comunque degli svantaggi, Che impongono un livello di complessità che consenta di scalabilità orizzontale. La funzionalità che verrebbe di solito implementata dai sistemi di database esterni deve essere indirizzata alle attività quali la replica di dati tra microservizi con stato e partizionamento dei dati. Tuttavia, si tratta di una delle aree in cui un agente di orchestrazione come [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con relativo [servizi affidabili con stati](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) consente la maggior parte, per semplificare lo sviluppo e il ciclo di vita di informazioni sullo stato microservizi utilizzando il [API dei servizi affidabili](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework del microservizio che abilitano i servizi con stato, che supportano lo schema Actor, e che migliorano la tolleranza di errore e la latenza tra logica di business e dati, sono Microsoft [Orleans](https://github.com/dotnet/orleans), di Microsoft Research, e [Akka.NET](https://getakka.net/). Entrambi i framework stanno attualmente migliorando il supporto per Docker.

Si noti che anche i contenitori Docker sono senza stato. Se si vuole implementare un servizio con stato, è necessario uno dei framework prescrittivi e di livello superiore aggiuntivi di cui si è parlato in precedenza. Tuttavia, redazione del presente documento, i servizi con stati in Service Fabric non sono supportati come contenitori, solo come microservizi normale. Supporto di servizi affidabili in contenitori sarà disponibile nelle versioni future di Service Fabric.


>[!div class="step-by-step"]
[Precedente] (applications.md soa) [Avanti] (docker-App-sviluppo-environment.md)
