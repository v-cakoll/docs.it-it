---
title: Orchestrazione di microservizi e multicontainer applicazioni per la scalabilità e disponibilità elevate
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/19/2017
ms.openlocfilehash: 5c7016fa8b731170a63f5d0f9d9bed3b72090be4
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106379"
---
# <a name="orchestrating-microservices-and-multicontainer-applications-for-high-scalability-and-availability"></a>Orchestrazione di microservizi e multicontainer applicazioni per la scalabilità e disponibilità elevate

L'uso di agenti di orchestrazione per applicazioni pronte per la produzione è essenziale se l'applicazione è basata su microservizi o semplicemente suddivisa tra più contenitori. Come illustrato in precedenza, in un approccio basato su microservizi ogni microservizio è proprietario dei rispettivi modelli e dati, quindi sarà autonomo dal punto di vista dello sviluppo e della distribuzione. Ma anche se si dispone di un'applicazione più tradizionale è costituito da più servizi (ad esempio, SOA), è inoltre più contenitori o servizi che comprendono un'applicazione di business che devono essere distribuiti come un sistema distribuito. Questi tipi di sistemi vengono complessi per scalare in orizzontale e gestire; è pertanto assolutamente necessario agente di orchestrazione se si desidera disporre di un'applicazione multicontainer produzione e scalabile.

Figura 4-6 viene illustrata la distribuzione in un cluster di un'applicazione composta da più microservizi (contenitori).

![](./media/image6.png)

Figura 4-6: un cluster di contenitori

Si tratta di un approccio apparentemente logico. Ma, come si gestisce il bilanciamento del carico, routing e la coordinazione di queste applicazioni composte?

L'interfaccia della riga di comando di Docker (CLI) soddisfi le esigenze di gestione di un contenitore in un singolo host, ma ricadere breve per quanto riguarda alla gestione dei contenitori più distribuiti su più host per le applicazioni distribuite più complesse. Nella maggior parte dei casi, è necessario una piattaforma di gestione che verrà automaticamente avviare contenitori, sospendere, o spegnerle quando necessario e idealmente inoltre controllare come accedono alle risorse, ad esempio l'archiviazione di rete e i dati.

Per passare a un livello superiore rispetto alla gestione di singoli contenitori o app composte molto semplici e gestire ad applicazioni aziendali di dimensioni maggiori con microservizi, è necessario usare l'orchestrazione e le piattaforme di clustering.

Da un'architettura e sviluppo punto di vista, nel caso di compilazione, grandi, basato su microservizi, applicazioni, è importante comprendere le piattaforme e i prodotti che supportano scenari avanzati seguenti:

-   **I cluster e orchestrators** quando è necessario ridimensionare-out le applicazioni attraverso numerosi host Docker, ad esempio con un'applicazione basata su microservizi grandi dimensioni, è fondamentale per essere in grado di gestire tutti gli host come un singolo cluster da astrazione della complessità della piattaforma sottostante. I cluster di contenitori e gli agenti di orchestrazione offrono questo vantaggio. Esempi di orchestrators sono Docker Swarm Mesosphere DC/OS, Kubernetes (i primi tre disponibili tramite il servizio contenitore di Azure) e Azure Service Fabric.

-   **Utilità di pianificazione** *pianificazione* significa avere le funzionalità per un amministratore avviare i contenitori in un cluster in modo che oltre a fornire un'interfaccia utente. Un'utilità di pianificazione di cluster con responsabilità diverse: da usare in modo efficiente le risorse del cluster, per impostare i vincoli forniti dall'utente, ai contenitori di bilanciamento del carico in modo efficiente tra nodi o host e affidabile per dagli errori, offrendo alto disponibilità.

I concetti di cluster e utilità di pianificazione sono strettamente correlati, quindi i prodotti offerti da diversi fornitori includono spesso entrambi i set di funzionalità. Tabella 4-1 Elenca i più importanti della piattaforma e scelte di software che disponibili per i cluster e le utilità di pianificazione. Questi cluster sono in genere disponibili in cloud pubblici, ad esempio Azure.

Tabella 4-1: piattaforme Software per contenitore clustering, orchestrazione e la pianificazione

| Piattaforma | Descrizione |
|---|---|
| Docker Swarm<br/> ![http://rancher.com/wp-content/themes/rancher-2016/assets/images/swarm.png?v=2016-07-10-am](./media/image7.png) | Sciame docker offre la possibilità di cluster e pianificare i contenitori di Docker. Tramite Swarm è possibile trasformare un pool di host Docker in un singolo host Docker virtuale. I client possono eseguire richieste di API per sciame nello stesso modo in cui agli host, vale a dire che sciame rende semplice per la scalabilità delle applicazioni a più host. <br /><br /> Docker Swarm è un prodotto dell'azienda Docker. <br /><br /> Docker v1.12 o versioni successive può eseguire la modalità Swarm nativa e predefinita. |
| Mesosphere DC/OS<br/>![https://mesosphere.com/wp-content/uploads/2016/04/logo-horizontal-styled.png](./media/image8.png) |  Mesosphere Enterprise DC/OS, basata su Apache Mesos, è una piattaforma pronta per la produzione per l'esecuzione di contenitori e applicazioni distribuite. <br /><br /> DC/OS esegue l'astrazione di una raccolta delle risorse disponibili nel cluster e le rende disponibili ai componenti basati su di esso. Marathon viene in genere usato come utilità di pianificazione integrata con DC/OS. |
| Google Kubernetes<br />![https://pbs.twimg.com/media/Bt\_pEfqCAAAiVyz.png](./media/image9.png) | Kubernetes è un prodotto open source che offre funzionalità per l'infrastruttura dei cluster, la pianificazione dei contenitori e l'orchestrazione. In questo modo è possibile automatizzare operazioni di contenitori di applicazioni, scalabilità e la distribuzione in cluster degli host. <br /><br /> Kubernetes offre un'infrastruttura incentrata sui contenitori che raggruppa i contenitori di applicazioni in unità logiche per semplificarne la gestione e l'individuazione. |
| Azure Service Fabric<br />![https://azure.microsoft.com/svghandler/service-fabric?width=600&height=315](./media/image10.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni. È un [agente di orchestrazione](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e crea cluster di macchine virtuali. Per impostazione predefinita, Service Fabric distribuisce e Attiva servizi come processi, ma Service Fabric è possibile distribuire servizi immagini contenitore con Docker. Più importante, è possibile combinare servizi nei processi con i servizi in contenitori nella stessa applicazione. <br /><br /> A partire da maggio 2017, la funzionalità dell'infrastruttura di servizio che supporta la distribuzione dei servizi come contenitori di Docker è in stato di anteprima. <br /><br /> È possibile sviluppare servizi di Service Fabric in diversi modi, usando il [modelli di programmazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework) alla distribuzione [guest eseguibili](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-existing-app) , nonché i contenitori. Service Fabric supporta i modelli di applicazione ricchi di indicazioni, ad esempio [servizi con stati](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

## <a name="using-container-based-orchestrators-in-azure"></a>In Azure usando orchestrators basate sul contenitore

Diversi fornitori di cloud offrono il supporto dei contenitori di Docker più cluster Docker e supporto di orchestrazione, tra cui Azure, servizio contenitore EC2 Amazon e il motore di contenitori di Google. Azure supporta Docker cluster e orchestrator tramite il servizio contenitore di Azure, come illustrato nella sezione successiva.

Un'altra opzione consiste nell'usare Azure Service Fabric, che supporta anche Docker basati su Linux e i contenitori di Windows. Service Fabric viene eseguito in Azure o in qualsiasi altro cloud nonché [locale](https://docs.microsoft.com/azure/service-fabric/service-fabric-deploy-anywhere).

## <a name="using-azure-container-service"></a>Uso del servizio contenitore di Azure

Un cluster Docker crea pool di host Docker e li espone come un singolo host Docker virtuale, per consentire di distribuire più contenitori nel cluster. Il cluster gestirà tutte le funzionalità di gestione complesse come scalabilità e l'integrità. Figura 4-7 rappresenta come un cluster di Docker per comporre applicazioni esegue il mapping al servizio di contenitore.

Il servizio contenitore fornisce un modo per semplificare la creazione, configurazione e gestione di un cluster di macchine virtuali che sono preconfigurati per l'esecuzione di applicazioni nei contenitori. Utilizza una configurazione ottimizzata degli strumenti di pianificazione e l'orchestrazione open source più diffusi, il servizio contenitore offre la possibilità di usare le competenze esistenti disegnare o in un corpo elevato e crescente di esperienza della community per distribuire e gestire basate sul contenitore applicazioni in Azure.

Il servizio contenitore consente di ottimizzare la configurazione di più diffusi Docker clustering open source strumenti e tecnologie in modo specifico per Azure. Si ottiene una soluzione che offre la portabilità per la configurazione di contenitori e applicazioni. È sufficiente selezionare le dimensioni, il numero di host e gli strumenti dell'agente di orchestrazione. Il servizio contenitore gestisce tutte le altre operazioni.

Servizio contenitore utilizza le immagini Docker per assicurarsi che i contenitori di applicazioni siano completamente portabili. Supporta la scelta del piattaforme open source orchestrazione come controller di dominio/OS Kubernetes e Docker Swarm per garantire che queste applicazioni adattabile a migliaia o persino decine di migliaia di contenitori.

Con il servizio contenitore di Azure, è possibile sfruttare le funzionalità aziendale di Azure pur mantenendo la portabilità dell'applicazione, inclusi i livelli di orchestrazione.

![](./media/image11.png)

Figura 4-7: Clustering scelte nel servizio contenitore di Azure

Come illustrato nella figura 4-8, il servizio contenitore è semplicemente l'infrastruttura fornita da Azure per poter distribuire controller di dominio/OS, Kubernetes o Docker Swarm, ma non implementa alcun orchestrator aggiuntive. Di conseguenza, il servizio contenitore è non agente di orchestrazione, di conseguenza; è solo un'infrastruttura che consente di sfruttare orchestrators open source esistente per i contenitori.

![](./media/image12.png)

Figura 4-8: Orchestrators nel servizio contenitore

Dal punto di vista dell'utilizzo, l'obiettivo di servizio di contenitore consiste nello specificare un ambiente di host contenitore usando tecnologie e strumenti open source più diffusi. A questo scopo, espone gli endpoint API standard per l'agente di orchestrazione scelto. Tramite questi endpoint, è possibile utilizzare qualsiasi software che può comunicare con gli endpoint. Ad esempio, nel caso l'endpoint Docker Swarm, è possibile scegliere di utilizzare l'interfaccia CLI di Docker. Per DC/OS è possibile scegliere di usare l'interfaccia della riga di comando di DC/OS.

### <a name="getting-started-with-container-service"></a>Introduzione a servizio contenitore

Per iniziare a utilizzare il servizio contenitore, si distribuisce un cluster il servizio contenitore dal portale di Azure utilizzando un modello di gestione risorse di Azure o il [CLI](https://docs.microsoft.com/cli/azure/install-azure-cli). I modelli disponibili includono [Docker Swarm](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-swarm), [Kubernetes](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-kubernetes) e [DC/OS](https://github.com/Azure/azure-quickstart-templates/tree/master/101-acs-dcos). È possibile modificare i modelli di avvio rapido per includere la configurazione di Azure aggiuntiva o avanzata.

**Altre informazioni** per altre informazioni sulla distribuzione di un cluster il servizio contenitore, sul sito Web di Azure, leggere [distribuire un cluster il servizio contenitore di Azure](https://docs.microsoft.com/azure/container-service/dcos-swarm/container-service-deployment).

Non sono previsti addebiti per il software installato per impostazione predefinita come parte del servizio contenitore di Azure. Tutte le opzioni predefinite vengono implementate con software open source.

Servizio di contenitore è attualmente disponibile per Standard A, D, DS, G e le macchine virtuali Linux serie GS in Azure. Vengono addebitati solo per le istanze di calcolo che scelte e altre infrastrutture risorse sottostanti utilizzate, ad esempio l'archiviazione e rete. Non vi sono incrementali addebiti per il servizio contenitore stesso.

### <a name="additional-resources"></a>Risorse aggiuntive

Di seguito sono posizioni in cui è possibile trovare informazioni aggiuntive:

-   Introduzione al contenitore Docker hosting soluzioni con il servizio contenitore:  
    https://docs.microsoft.com/azure/container-service/kubernetes/container-service-intro-kubernetes>

-   Panoramica di sciame docker:  
    <https://docs.docker.com/swarm/overview/>

-   Swarm Panoramica sulla modalità:  
    <https://docs.docker.com/engine/swarm/>

-   Panoramica di controller di dominio/OS mesosphere:    
    <https://docs.mesosphere.com/1.7/overview/>

-   Kubernetes (sito ufficiale):  
    <https://kubernetes.io/>

## <a name="using-service-fabric"></a>Usando Service Fabric

Si è verificato Service Fabric da eseguire la transizione da offrire prodotti software "finestra", che erano in genere monolitiche in stile, alla fornitura di servizi Microsoft. L'esperienza di creare e gestire i servizi su larga scala, ad esempio Database SQL di Azure, Azure Documentdb, Azure Service Bus o back-end di Cortana, la forma di Service Fabric. La piattaforma si è evoluta nel tempo con la sua continua adozione da parte di un numero crescente di servizi. Cosa ancora più importante, Service Fabric doveva essere eseguito non solo in Azure, ma anche nelle distribuzioni autonome di Windows Server.

L'obiettivo di Service Fabric è per risolvere i problemi di compilazione che eseguono un servizio e utilizzano risorse di infrastruttura in modo efficiente, in modo che i team possono risolvere problemi aziendali usando un approccio di microservizi difficile.

Service Fabric fornisce due aree generali che consentono di creare applicazioni che usano un approccio ai microservizi:

-   Una piattaforma che fornisce servizi di sistema per distribuire, ridimensionare, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema in effetti forniscono molte delle caratteristiche di microservizi descritto in precedenza.

-   API di programmazione, o framework, che aiutano a creare applicazioni come microservizi: [Reliable Actors e Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Naturalmente, è possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API semplificano il processo e si integrano nella piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

Service Fabric è agnostico rispetto al modo in cui si crea il servizio ed è possibile usare qualsiasi tecnologia. Tuttavia, fornisce API di programmazione predefinite che rendono più semplice creare i microservizi.

Figura 4-9 viene illustrato come è possibile creare ed eseguire microservizi in Service Fabric come processi semplici o come contenitori Docker. È anche possibile combinare microservizi basati su contenitori con microservizi basati su processi all'interno dello stesso cluster di Service Fabric.

![](./media/image13.png)

Figura 4-9: distribuzione di microservizi come processi o come contenitori in Azure Service Fabric

Cluster di Service Fabric in base alle host Linux e Windows è possibile eseguire i contenitori di Docker Linux e i contenitori di Windows.

**Altre informazioni** per informazioni aggiornate sul supporto dei contenitori in Service Fabric, sul sito Web di Azure, leggere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di una piattaforma a cui è possibile definire una diversa architettura logica (business microservizi o contesti limitata) rispetto all'implementazione fisica. Ad esempio, se si implementa [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), che vengono introdotti nella sezione successiva, "[Stateless e con stato microservizi](#stateless-versus-stateful-microservices), "è un concetto microservizio business con più servizi fisici.

Come illustrato nella figura 4-10 e il concetto dalla prospettiva del microservizio logico/business, quando si implementa un servizio con stato affidabile Service Fabric, è in genere necessario implementare due livelli di servizi. Il primo è il servizio back-end con stato affidabile, che gestisce più partizioni. Il secondo è il servizio front-end, o Servizio gateway, responsabile del routing e dell'aggregazione dei dati in più partizioni o istanze del servizio con stato. Il servizio Gateway gestisce inoltre la comunicazione client-side con i cicli di ripetizione l'accesso al servizio back-end utilizzato in combinazione con Service Fabric [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image14.png)

Figura 4-10: Business microservizio con diversi servizi con stati e senza stati in Service Fabric

In ogni caso, quando si usano i servizi Reliable con stato di Service Fabric, si ottiene anche un microservizio logico o aziendale (Bounded Context) che in genere è costituito da più servizi fisici. Ognuno di essi, il servizio Gateway e partizione servizio potrebbe essere implementato come servizi API Web ASP.NET, come illustrato nella figura 4-10.

In Service Fabric, è possibile raggruppare e distribuire gruppi di servizi come [Applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), cioè l'unità di creazione pacchetto e distribuzione per l'agente di orchestrazione o il cluster. L'applicazione di Service Fabric di conseguenza, potrebbe essere mappato a questo aziendali autonome e limite logico microservizio o contesto delimitata, nonché.

### <a name="service-fabric-and-containers"></a>Service Fabric e contenitori

Per quanto riguarda i contenitori di Service Fabric, è anche possibile distribuire servizi nelle immagini contenitore all'interno di un cluster di Service Fabric. La figura 4-11 illustra che la maggior parte dei casi sarà presente solo un contenitore per ogni servizio.

![](./media/image15.png)

Figura 4-11: Business microservizio con diversi servizi (contenitori) di Service Fabric

Contenitori cosiddetti "car" (due contenitori che devono essere distribuiti insieme come parte di un servizio logico) sono però anche possibili in Service Fabric. La cosa importante è che un microservizio aziendale è rappresentato dal limite logico intorno a diversi elementi coesivi. In molti casi, potrebbe essere un singolo servizio con un singolo modello di data, ma in altri casi potrebbe essere necessario fisici diversi servizi, nonché.

A partire da questa scrittura (aprile 2017), in Service Fabric non è possibile distribuire servizi con stato affidabili SF sui contenitori, ovvero è possibile distribuire solo i contenitori di guest, servizi senza stati o servizi actor di contenitori. Ma si noti che è possibile combinare servizi nei processi e servizi nei contenitori nella stessa applicazione di Service Fabric, come illustrato nella figura 4-12.

![](./media/image16.png)

Figura 4-12: Business microservizio mappato a un'applicazione di Service Fabric con i contenitori e i servizi con stati

Il supporto è diverso a seconda se si utilizza i contenitori di Docker in Linux o i contenitori di Windows. Verrà aperto il supporto per i contenitori di Service Fabric nelle prossime versioni. Per le notizie aggiornate sul supporto del contenitore in Service Fabric, sul sito Web di Azure, leggere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservizi con stato e senza stato

Come accennato in precedenza, ogni microservizio (Bounded Context logico) deve essere proprietario di un modello di dominio (dati e logica). Nel caso di microservizi senza stato, i database verranno esterni, avvalendosi di opzioni relazionale, ad esempio SQL Server o le opzioni di database NoSQL come MongoDB o Azure DocumentDB.

Ma i servizi stessi inoltre possono essere con stati, il che significa che i dati si trovano all'interno di microservizio. Questi dati potrebbero esistere non solo nello stesso server, ma all'interno del processo microservizio, in memoria e persistenti sulle unità e replicate in altri nodi. Figura 4-13 illustra i diversi approcci.

![](./media/image17.png)

Figura 4-13: senza stato e microservizi con stato

Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto microservizi con stato perché l'approccio è simile ai modelli tradizionali e quelle note. Tuttavia, i microservizi senza stato impongono la latenza tra il processo e le origini dati, oltre a comportare più elementi quando si prova a migliorare le prestazioni con cache e code aggiuntive. Il risultato è che si può finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, [microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possibile di excel in scenari avanzati in quanto non è prevista una latenza tra la logica di dominio e i dati. Sistemi back-end giochi di elaborazione dati, database come servizio e altri scenari a bassa latenza i vantaggi offerti dai servizi con stati, che forniscono lo stato locale di un accesso più rapido.

I servizi con e senza stato sono complementari. Ad esempio, un servizio con stato può essere suddivisi in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisca come servizio gateway che sappia come risolvere ogni partizione in base alle chiavi di partizione.

I servizi con stato presentano comunque degli svantaggi, Che impongono un livello di complessità che consenta loro di scalare in orizzontale. La funzionalità che verrebbe di solito implementata dai sistemi di database esterni deve essere indirizzata alle attività quali la replica di dati tra microservizi con stato e partizionamento dei dati. Si tratta tuttavia una delle aree in cui desidera che agente di orchestrazione [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con relativo [servizi reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) utili per la maggior parte, ovvero per semplificare lo sviluppo e il ciclo di vita delle informazioni sullo stato microservizi utilizzando il [API per servizi affidabili](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework del microservizio che abilitano i servizi con stato, che supportano lo schema Actor, e che migliorano la tolleranza di errore e la latenza tra logica di business e dati, sono Microsoft [Orleans](https://github.com/dotnet/orleans), di Microsoft Research, e [Akka.NET](https://getakka.net/). Entrambi i framework stanno attualmente migliorando il supporto per Docker.

Si noti che anche i contenitori Docker sono senza stato. Se si vuole implementare un servizio con stato, è necessario uno dei framework prescrittivi e di livello superiore aggiuntivi di cui si è parlato in precedenza. Tuttavia, stesura, i servizi con stati in Service Fabric non sono supportati come contenitori, solo come microservizi normale. Supporto di servizi affidabili nei contenitori sarà disponibile nelle versioni future di Service Fabric.


>[!div class="step-by-step"]
[Precedente](soa-applications.md)
[Successivo](docker-apps-development-environment.md)
