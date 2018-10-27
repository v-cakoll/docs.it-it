---
title: Orchestrazione di microservizi e applicazioni multicontenitore per scalabilità e disponibilità elevate
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 993f1d18637f39b6df4d876db8a0fe86e34391e3
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170354"
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Orchestrazione di microservizi e applicazioni multicontenitore per scalabilità e disponibilità elevate

L'uso di agenti di orchestrazione per applicazioni pronte per la produzione è essenziale se l'applicazione è basata su microservizi o semplicemente suddivisa tra più contenitori. Come illustrato in precedenza, in un approccio basato su microservizi ogni microservizio è proprietario dei rispettivi modelli e dati, quindi sarà autonomo dal punto di vista dello sviluppo e della distribuzione. Ma anche se si dispone di un'applicazione più tradizionale è costituito da più servizi (ad esempio SOA), è anche necessario più contenitori o servizi che comprendono un'applicazione di business che devono essere distribuite come un sistema distribuito. Questi tipi di sistemi sono complessi da scalare orizzontalmente e gestire; Pertanto, è assolutamente necessario un agente di orchestrazione se si desidera disporre di un'applicazione multicontenitore scalabile e pronti per la produzione.

Nella figura 4-6 illustra la distribuzione in un cluster di un'applicazione costituita da più microservizi (contenitori).

![](./media/image6.png)

Nella figura 4-6: un cluster di contenitori

Si tratta di un approccio apparentemente logico. Ma come si gestisce il bilanciamento del carico, il routing e orchestrare tali applicazioni composte?

L'interfaccia della riga di comando di Docker (CLI) soddisfa le esigenze di gestione di un contenitore in un host, ma è sufficiente per la gestione di più contenitori distribuiti su più host per le applicazioni distribuite più complesse. Nella maggior parte dei casi, è necessaria una piattaforma di gestione che verrà automaticamente avvia i contenitori, sospendere, o arrestarli quando necessario e idealmente controllare anche la modalità di accesso a risorse come la rete e archiviazione dei dati.

Per passare a un livello superiore rispetto alla gestione di singoli contenitori o app composte molto semplici e gestire ad applicazioni aziendali di dimensioni maggiori con microservizi, è necessario usare l'orchestrazione e le piattaforme di clustering.

Da un'architettura e sviluppo punto di vista, se si è aziendali di grandi dimensioni, building, basate su microservizi, applicazioni, è importante comprendere le piattaforme e i prodotti che supportano scenari avanzati seguenti:

-   **I cluster e agenti di orchestrazione** quando è necessario ridimensionare-orizzontalmente le applicazioni in molti host Docker, ad esempio con un'applicazione basata su microservizi di grandi dimensioni, è fondamentale essere in grado di gestire tutti gli host come un singolo cluster da astrazione della complessità della piattaforma sottostante. Questo è ciò che fornisce cluster di contenitori e gli agenti di orchestrazione. Esempi di agenti di orchestrazione sono Docker Swarm, Mesosphere DC/OS, Kubernetes (i primi tre disponibili tramite il servizio contenitore di Azure) e Azure Service Fabric.

-   **Le utilità di pianificazione** *pianificazione* significa avere la possibilità per un amministratore di avviare contenitori in un cluster in modo che forniscano anche un'interfaccia utente. Un'utilità di pianificazione di cluster ha diverse funzioni: da usare in modo efficiente le risorse del cluster, configurare i vincoli forniti dall'utente, ai contenitori di bilanciamento del carico in modo efficiente tra nodi e negli host e per essere efficace in caso di errori, fornendo alto disponibilità.

I concetti di cluster e utilità di pianificazione sono strettamente correlati, quindi i prodotti offerti da diversi fornitori includono spesso entrambi i set di funzionalità. Tabella 4-1 Elenca le piattaforme più importanti e scelte di software che disponibili per i cluster e le utilità di pianificazione. Questi cluster vengono generalmente offerti in cloud pubblici quali Azure.

Tabella 4-1: piattaforme Software per il contenitore di clustering, orchestrazione e la pianificazione

| Piattaforma | Descrizione |
|---|---|
| Docker Swarm<br/> ![Logo di docker Swarm](./media/image7.png) | Docker Swarm offre la possibilità di pianificare i contenitori Docker e del cluster. Tramite Swarm è possibile trasformare un pool di host Docker in un singolo host Docker virtuale. I client possono inviare richieste API a Swarm nella stesso modo in cui avviene per gli host, vale a dire che Swarm semplifica infatti per la scalabilità delle applicazioni a più host. <br /><br /> Docker Swarm è un prodotto dell'azienda Docker. <br /><br /> Docker v1.12 o versioni successive può eseguire la modalità Swarm nativa e predefinita. |
| Mesosphere DC/OS<br/>![Logo di mesosphere DC/OS](./media/image8.png) |  Mesosphere Enterprise DC/OS, basata su Apache Mesos, è una piattaforma pronta per la produzione per l'esecuzione di contenitori e applicazioni distribuite. <br /><br /> DC/OS esegue l'astrazione di una raccolta delle risorse disponibili nel cluster e le rende disponibili ai componenti basati su di esso. Marathon viene in genere usato come utilità di pianificazione integrata con DC/OS. |
| Google Kubernetes<br />![Logo Google Kubernetes](./media/image9.png) | Kubernetes è un prodotto open source che offre funzionalità per l'infrastruttura dei cluster, la pianificazione dei contenitori e l'orchestrazione. In tal modo è possibile automatizzare la distribuzione, ridimensionamento e la gestione dei contenitori di applicazioni in cluster di host. <br /><br /> Kubernetes offre un'infrastruttura incentrata sui contenitori che raggruppa i contenitori di applicazioni in unità logiche per semplificarne la gestione e l'individuazione. |
| Azure Service Fabric<br />![Logo di Azure Service Fabric](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni. È un [agente di orchestrazione](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e crea cluster di macchine virtuali. Per impostazione predefinita, Service Fabric distribuisce e attiva i servizi come processi, ma Service Fabric può distribuire servizi in immagini contenitore Docker. Più importante, è possibile combinare servizi nei processi con i servizi in contenitori nella stessa applicazione. <br /><br /> A partire da maggio 2017, la funzionalità di Service Fabric supporta i servizi di distribuzione come contenitori Docker è in stato di anteprima. <br /><br /> È possibile sviluppare servizi di Service Fabric in molti modi, usando il [modelli di programmazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) alla distribuzione [eseguibili guest](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) oltre a contenitori. Service Fabric supporta i modelli di applicazione prescrittivo, ad esempio [i servizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>Usando gli agenti di orchestrazione basati su contenitori in Azure

Alcuni fornitori cloud offrono supporto per i contenitori Docker e Docker cluster e supporto di orchestrazione, inclusi Azure, servizio contenitore di Amazon EC2 e Google Container Engine. Supporto per cluster e dell'agente di orchestrazione tramite il servizio contenitore di Azure, Azure offre Docker, come illustrato nella sezione successiva.

Un'altra opzione consiste nell'usare Azure Service Fabric, che supporta anche Docker basato su contenitori Linux e Windows. Service Fabric viene eseguito in Azure o qualsiasi altro cloud, nonché [locali](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Uso del servizio contenitore di Azure

Un cluster Docker crea pool di host Docker e li espone come un singolo host Docker virtuale, per consentire di distribuire più contenitori nel cluster. Il cluster gestirà tutte le operazioni di gestione complesse come la scalabilità e l'integrità. Figura 4-7 rappresenta una modalità di mapping di un cluster Docker per applicazioni composte al servizio contenitore.

Servizio contenitore fornisce un modo per semplificare la creazione, configurazione e gestione di un cluster di macchine virtuali preconfigurate per eseguire applicazioni in contenitori. Usa una configurazione ottimizzata degli strumenti di pianificazione e orchestrazione open source più diffusi, servizio contenitore ti offre la possibilità di usare le competenze esistenti o disegnare su un consistente e crescente bagaglio di competenze della community per distribuire e gestire basate su contenitori applicazioni in Azure.

Il servizio contenitore ottimizza la configurazione di diffusi strumenti open source di clustering Docker e le tecnologie in modo specifico per Azure. Si ottiene una soluzione che offre la portabilità per la configurazione di contenitori e applicazioni. È sufficiente selezionare le dimensioni, il numero di host e gli strumenti dell'agente di orchestrazione. Il servizio contenitore gestisce tutte le altre operazioni.

Servizio contenitore Usa immagini Docker per garantire che i contenitori di applicazioni siano completamente portabili. Supporta la scelta di piattaforme di orchestrazione open source, ad esempio DC/OS, Kubernetes e Docker Swarm per garantire che queste applicazioni può essere ridimensionata per migliaia o decine di migliaia di contenitori.

Con il servizio contenitore di Azure, è possibile sfruttare le funzionalità di livello aziendale di Azure mantenendo al tempo stesso la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

![](./media/image11.png)

Figura 4-7: opzioni nel servizio contenitore di Azure per il Clustering

Come illustrato nella figura 4-8, il servizio contenitore è semplicemente l'infrastruttura fornita da Azure per distribuire DC/OS, Kubernetes o Docker Swarm, ma non implementa alcun agente di orchestrazione aggiuntivo. Pertanto, il servizio contenitore è non un agente di orchestrazione, di conseguenza; è solo un'infrastruttura che sfrutta gli agenti di orchestrazione open source esistenti per i contenitori.

![](./media/image12.png)

Figura 4-8: agenti di orchestrazione nel servizio contenitore

Dal punto di vista dell'utilizzo, l'obiettivo del servizio contenitore di è fornire un ambiente di hosting di contenitori usando tecnologie e strumenti open source più diffusi. A questo scopo, espone gli endpoint API standard per l'agente di orchestrazione scelto. Usando questi endpoint, è possibile usare qualsiasi software che può comunicare con tali endpoint. Ad esempio, nel caso dell'endpoint Docker Swarm, è possibile usare la CLI di Docker. Per DC/OS è possibile scegliere di usare l'interfaccia della riga di comando di DC/OS.

### <a name="getting-started-with-container-service"></a>Introduzione al servizio contenitore

Per iniziare a usare il servizio contenitore, distribuire un cluster del servizio contenitore dal portale di Azure usando un modello di Azure Resource Manager o la [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). I modelli disponibili includono [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) e [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). È possibile modificare i modelli di avvio rapido per includere la configurazione di Azure aggiuntiva o avanzata.

**Altre informazioni** per altre informazioni sulla distribuzione di un cluster del servizio contenitore, sul sito Web di Azure, leggere [distribuire un cluster del servizio contenitore di Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

Non sono previsti addebiti per il software installato per impostazione predefinita come parte del servizio contenitore di Azure. Tutte le opzioni predefinite vengono implementate con software open source.

Servizio contenitore è attualmente disponibile per Standard A, D, DS, G e GS serie Linux VM in Azure. Vengono addebitate solo le istanze di calcolo che scegli, nonché le altre infrastruttura risorse sottostanti utilizzate, ad esempio rete e di archiviazione. Non esistono applicato alcun addebito incrementale per il servizio contenitore stesso.

### <a name="additional-resources"></a>Risorse aggiuntive

Di seguito sono posizioni in cui è possibile trovare informazioni aggiuntive:

-   Introduzione alle soluzioni con il servizio contenitore di hosting di contenitori Docker:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Panoramica di docker Swarm:  
    <https://docs.docker.com/swarm/overview/>

-   Panoramica della modalità Swarm:  
    <https://docs.docker.com/engine/swarm/>

-   Panoramica di mesosphere DC/OS:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (il sito ufficiale):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Uso di Service Fabric

Service Fabric si è verificato dal passaggio di Microsoft dalla fornitura di "box" prodotti preconfezionati, generalmente di tipo monolitico, alla fornitura dei servizi. L'esperienza di creazione e gestione di grandi servizi su larga scala, ad esempio Database SQL di Azure, Azure Document DB, il Bus di servizio di Azure o Backend di Cortana, la forma di Service Fabric. La piattaforma si è evoluta nel tempo con la sua continua adozione da parte di un numero crescente di servizi. Cosa ancora più importante, Service Fabric doveva essere eseguito non solo in Azure, ma anche nelle distribuzioni autonome di Windows Server.

L'obiettivo di Service Fabric consiste nel risolvere i difficili problemi di compilazione e l'esecuzione di un servizio e utilizzano in modo efficiente le risorse di infrastruttura in modo che i team possano risolvere i problemi aziendali usando un approccio ai microservizi.

Service Fabric fornisce due aree generali che consentono di creare applicazioni che usano un approccio ai microservizi:

-   Una piattaforma che fornisce servizi di sistema per distribuire, ridimensionare, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema è in vigore forniscono molte delle caratteristiche dei microservizi descritte in precedenza.

-   API di programmazione, o framework, che aiutano a creare applicazioni come microservizi: [Reliable Actors e Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Naturalmente, è possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API semplificano il processo e si integrano nella piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

Service Fabric è agnostico rispetto al modo in cui si crea il servizio ed è possibile usare qualsiasi tecnologia. Tuttavia, fornisce API di programmazione predefinite che rendono più semplice creare i microservizi.

Figura 4-9 viene illustrato come creare ed eseguire i microservizi in Service Fabric come processi semplici o come contenitori Docker. È anche possibile combinare microservizi basati su contenitori con microservizi basati su processi all'interno dello stesso cluster di Service Fabric.

![](./media/image13.png)

Figura 4-9: distribuzione di microservizi come processi o contenitori in Azure Service Fabric

Cluster di Service Fabric basati su host Linux e Windows può eseguire contenitori Linux Docker e i contenitori di Windows.

**Altre informazioni** per informazioni aggiornate sul supporto di contenitori in Service Fabric, sul sito Web di Azure, leggere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di una piattaforma a cui è possibile definire una diversa architettura logica (microservizi aziendali o contesti delimitati) rispetto all'implementazione fisica. Ad esempio, se si implementa [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) nelle [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), che vengono introdotti nella sezione successiva, "[senza stato e i microservizi con stato](#stateless-versus-stateful-microservices), "è un concetto di microservizio aziendale con più servizi fisici.

Come illustrato nella figura 4-10 e da una prospettiva di microservizio logico/aziendale, quando si implementa un servizio Reliable Services di Service Fabric con stato, in genere sarà necessario implementare due livelli di servizi. Il primo è il back-end servizio reliable con stato, che gestisce più partizioni. Il secondo è il servizio front-end, o servizio Gateway, responsabile delle aggregazioni di routing e i dati in più partizioni o istanze del servizio con stato. Tale servizio Gateway gestisce anche la comunicazione client-side con i cicli di ripetizione che accedono al servizio back-end usato in combinazione con Service Fabric [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Figura 4-10: microservizio aziendale con numerosi servizi con e senza stati in Service Fabric

In ogni caso, quando si usano i servizi Reliable con stato di Service Fabric, si ottiene anche un microservizio logico o aziendale (Bounded Context) che in genere è costituito da più servizi fisici. Ognuno di essi, il servizio Gateway e servizio partizione potrebbe essere implementato come servizi API Web ASP.NET, come illustrato nella figura 4-10.

In Service Fabric, è possibile raggruppare e distribuire gruppi di servizi come [Applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), cioè l'unità di creazione pacchetto e distribuzione per l'agente di orchestrazione o il cluster. L'applicazione di Service Fabric di conseguenza, potrebbe essere mappato a questo aziendali autonome e limite del microservizio logico o Bounded Context, nonché.

### <a name="service-fabric-and-containers"></a>Service Fabric e contenitori

Per quanto riguarda i contenitori in Service Fabric, è anche possibile distribuire servizi in immagini contenitore all'interno di un cluster di Service Fabric. Figura 4-11 illustra che la maggior parte dei casi sarà presente un solo contenitore per ogni servizio.

![](./media/image15.png)

Figura 4-11: microservizio aziendale con numerosi servizi (contenitori) in Service Fabric

Tuttavia, contenitori cosiddette "collaterali" (due contenitori che devono essere distribuiti insieme come parte di un servizio logico) sono possibili anche in Service Fabric. La cosa importante è che un microservizio aziendale è rappresentato dal limite logico intorno a diversi elementi coesivi. In molti casi, potrebbe essere un singolo servizio con un singolo modello di dati, ma in altri casi potrebbe essere diversi servizi fisici, nonché.

Al momento della stesura di questo documento (aprile 2017), in Service Fabric non è possibile distribuire servizi Reliable con stato SF sui contenitori, è possibile distribuire solo i contenitori guest, servizi senza stato o servizi actor nei contenitori. Ma si noti che è possibile combinare servizi in processi e servizi in contenitori nella stessa applicazione Service Fabric, come illustrato nella figura 4-12.

![](./media/image16.png)

Microservizio aziendale figura 4-12: mappata a un'applicazione di Service Fabric con contenitori e servizi con stati

Il supporto inoltre è diverso a seconda se si usano contenitori di Docker sui contenitori di Windows o Linux. Supporto per i contenitori in Service Fabric verrà espanso nelle prossime versioni. Per notizie aggiornate sul supporto di contenitori in Service Fabric, sul sito Web di Azure, leggere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservizi con stato e senza stato

Come accennato in precedenza, ogni microservizio (Bounded Context logico) deve essere proprietario di un modello di dominio (dati e logica). Nel caso i microservizi senza stato, i database saranno esterni, avvalendosi di opzioni relazionali come SQL Server o le opzioni NoSQL come MongoDB o Azure DocumentDB.

Ma i servizi stessi possono rivelarsi con stati, il che significa che i dati si trovano all'interno del microservizio. Questi dati potrebbero esistere non solo nello stesso server, ma all'interno del processo del microservizio, in memoria e persistenti sulle unità e replicato in altri nodi. Figura 4-13 mostra i diversi approcci.

![](./media/image17.png)

Figura 4-13: e i microservizi senza stato

Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto ai microservizi con stato perché l'approccio è simile ai modelli tradizionali e noti. Tuttavia, i microservizi senza stato impongono la latenza tra il processo e le origini dati, oltre a comportare più elementi quando si prova a migliorare le prestazioni con cache e code aggiuntive. Il risultato è che si può finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, [i microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possono eccellere in scenari avanzati, perché non è prevista alcuna latenza tra la logica di dominio e i dati. Back-end di gioco pesante, l'elaborazione di dati, database come un servizio e altri scenari a bassa latenza vantaggi offerti dai servizi con stato, che forniscono lo stato locale per un accesso più rapido.

I servizi con e senza stato sono complementari. Ad esempio, un servizio con stato può essere suddivisi in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisca come servizio gateway che sappia come risolvere ogni partizione in base alle chiavi di partizione.

I servizi con stato presentano comunque degli svantaggi, Perché impongono un livello di complessità che consente loro di scalare in orizzontale. La funzionalità che verrebbe di solito implementata dai sistemi di database esterni deve essere indirizzata alle attività quali la replica di dati tra microservizi con stato e partizionamento dei dati. Tuttavia, questa è una delle aree in cui un agente di orchestrazione come [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con relativo [reliable services con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) può aiutare la maggior parte, semplificando lo sviluppo e il ciclo di vita delle informazioni sullo stato microservizi con il [API di Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework del microservizio che abilitano i servizi con stato, che supportano lo schema Actor, e che migliorano la tolleranza di errore e la latenza tra logica di business e dati, sono Microsoft [Orleans](https://github.com/dotnet/orleans), di Microsoft Research, e [Akka.NET](https://getakka.net/). Entrambi i framework stanno attualmente migliorando il supporto per Docker.

Si noti che anche i contenitori Docker sono senza stato. Se si vuole implementare un servizio con stato, è necessario uno dei framework prescrittivi e di livello superiore aggiuntivi di cui si è parlato in precedenza. Al momento della stesura di questo articolo, tuttavia, i servizi con stato in Service Fabric non sono supportati come contenitori, solo come microservizi normali. Supporto di servizi Reliable services in contenitori sarà disponibile nelle versioni future di Service Fabric.


>[!div class="step-by-step"]
[Precedente](soa-applications.md)
[Successivo](docker-apps-development-environment.md)
