---
title: Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
description: Le applicazioni di produzione reale devono essere distribuite e gestite con gli agenti di orchestrazione di gestire l'integrità, il carico di lavoro e i cicli di vita di tutti i contenitori.
ms.date: 02/15/2019
ms.openlocfilehash: 6cb41e632db7c7c6b9412bf54d2efeb44deee80f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644722"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate

Usando gli agenti di orchestrazione per le applicazioni di produzione è essenziale se l'applicazione è basata su microservizi o suddivise tra più contenitori. Come illustrato in precedenza, in un approccio basato su microservizi ogni microservizio è proprietario dei rispettivi modelli e dati, quindi sarà autonomo dal punto di vista dello sviluppo e della distribuzione. Anche se è disponibile un'applicazione più tradizionale costituita da più servizi, ad esempio SOA, saranno comunque disponibili più contenitori o servizi che comprendono una singola applicazione aziendale da distribuire come sistema distribuito. Il ridimensionamento e la gestione di questi tipi di sistemi sono complessi ed è quindi assolutamente necessario un agente di orchestrazione se si vuole ottenere un'applicazione a più contenitori pronta per la produzione e ridimensionabile.

Nella figura 4-6 illustra la distribuzione in un cluster di un'applicazione costituita da più microservizi (contenitori).

![Applicazioni Docker composte in un cluster: usare un contenitore per ogni istanza del servizio. I contenitori Docker sono "unità di distribuzione" e un contenitore è un'istanza di un Docker. Un host gestisce più contenitori](./media/image6.png)

**Figura 4-6**. Cluster di contenitori

Si tratta di un approccio apparentemente logico. Ma come si gestisce il bilanciamento del carico, il routing e orchestrare tali applicazioni composte?

L'interfaccia della riga di comando di Docker (CLI) soddisfa le esigenze di gestione di un contenitore in un host, ma è sufficiente per la gestione di più contenitori distribuiti su più host per le applicazioni distribuite più complesse. Nella maggior parte dei casi, è necessaria una piattaforma di gestione che verrà automaticamente avvia i contenitori, ridimensionare i contenitori con più istanze per ogni immagine, sospenderli o arrestarli quando è necessario e idealmente controllare anche la modalità di accesso a risorse come la rete e dati spazio di archiviazione.

Per andare oltre la gestione di singoli contenitori o App composte semplice e gestire applicazioni aziendali più grandi con microservizi, è necessario usare l'orchestrazione e le piattaforme di clustering.

Da un'architettura e sviluppo punto di vista, se si è aziendali di grandi dimensioni, building, basate su microservizi, applicazioni, è importante comprendere le piattaforme e i prodotti che supportano scenari avanzati seguenti:

- **Cluster e agenti di orchestrazione.** Quando è necessario scalare orizzontalmente le applicazioni in molti host Docker, ad esempio con un'applicazione basata su microservizi di grandi dimensioni, è fondamentale essere in grado di gestire tutti questi host come un singolo cluster tramite l'astrazione della complessità della piattaforma sottostante. I cluster di contenitori e gli agenti di orchestrazione offrono questo vantaggio. Sono esempi di agenti di orchestrazione Azure Service Fabric e Kubernetes. Kubernetes è disponibile in Azure tramite il servizio Azure Kubernetes.

- **Utilità di pianificazione.** *Pianificazione* significa avere la possibilità per un amministratore di avviare contenitori in un cluster, in modo che le utilità di pianificazione fornisce anche un'interfaccia utente per questa operazione. Un'utilità di pianificazione di cluster ha molte responsabilità, tra cui usare in modo efficiente le risorse del cluster, configurare i vincoli specificati dall'utente, bilanciare in modo efficiente il carico dei contenitori nei nodi e negli host e infine assicurare l'affidabilità in caso di errori, offrendo al tempo stesso una disponibilità elevata.

I concetti di cluster e utilità di pianificazione sono strettamente correlati, quindi i prodotti offerti da diversi fornitori includono spesso entrambi i set di funzionalità. La sezione seguente illustra la piattaforma più importante e scelte di software che disponibili per i cluster e le utilità di pianificazione. Questi agenti di orchestrazione sono ampiamente disponibili in cloud pubblici quali Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Piattaforme software per il clustering, l'orchestrazione e la pianificazione dei contenitori

| Piattaforma | Commenti |
|:---:|:---|
| **Kubernetes** <br/> ![Logo di Kubernetes](./media/kubernetes-logo.png) | [*Kubernetes*](https://kubernetes.io/) è un prodotto open source che offre funzionalità per l'infrastruttura dei cluster, la pianificazione dei contenitori e l'orchestrazione. Consente di automatizzare la distribuzione, il ridimensionamento e la gestione di contenitori di applicazioni in cluster di host. <br/> <br/> *Kubernetes* offre un'infrastruttura incentrata sui contenitori che raggruppa i contenitori di applicazioni in unità logiche per semplificarne la gestione e l'individuazione. <br/> <br/> *Kubernetes* è maturo in Linux, meno maturo in Windows. |
| **Azure Kubernetes Service (AKS)** <br/> ![Logo di Azure Kubernetes Service](./media/aks-logo.png) | Il [servizio Azure Kubernetes](https://azure.microsoft.com/services/kubernetes-service/) è un servizio di orchestrazione dei contenitori Kubernetes gestito in Azure, che semplifica gestione, distribuzioni e operazioni del cluster Kubernetes. |
| **Azure Service Fabric** <br/> ![Logo di Azure Service Fabric](./media/service-fabric-logo.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni. È un [agente di orchestrazione](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e crea cluster di macchine virtuali. Service Fabric può distribuire servizi come contenitori o come processi semplici. Può anche combinare servizi nei processi con servizi nei contenitori entro la stessa applicazione e lo stesso cluster. <br/> <br/> I cluster di *Service Fabric* possono essere distribuiti in Azure, in locale o in qualsiasi cloud. La distribuzione in Azure è tuttavia semplificata con un approccio gestito. <br/> <br/> *Service Fabric* offre [modelli di programmazione di Service Fabric](https://azure.microsoft.com/documentation/articles/service-fabric-choose-framework/) prescrittivi aggiuntivi e facoltativi, come [servizi con stato](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-services-introduction/) e [Reliable Actors](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-actors-introduction/). <br/> <br/> *Service Fabric* è maturo in Windows (anni di evoluzione in Windows), meno maturo in Linux. <br/> <br/> I contenitori Linux e Windows sono supportati in Service Fabric dal 2017. |
| **Azure Service Fabric Mesh** <br/> ![Logo di Azure Service Fabric Mesh](./media/azure-service-fabric-mesh-logo.png) | [*Azure Service Fabric Mesh* ](https://docs.microsoft.com/azure/service-fabric-mesh/service-fabric-mesh-overview) offre la stessa affidabilità, prestazioni mission-critical e scalabilità di Service Fabric, ma offre anche una piattaforma completamente gestita e senza server. Non è necessario gestire un cluster, macchine virtuali, risorse di archiviazione o configurazione della rete. È sufficiente concentrarsi sullo sviluppo dell'applicazione. <br/> <br/> *Service Fabric Mesh* supporta i contenitori sia Windows che Linux, consentendo di sviluppare con qualsiasi linguaggio di programmazione e framework di propria scelta.

## <a name="using-container-based-orchestrators-in-azure"></a>Usando gli agenti di orchestrazione basati su contenitori in Azure

Alcuni fornitori cloud offrono supporto per i contenitori Docker e Docker cluster e supporto di orchestrazione, inclusi Azure, servizio contenitore di Amazon EC2 e Google Container Engine. Azure fornisce il supporto di cluster e dell'agente di orchestrazione tramite Azure Kubernetes Service (AKS), Azure Service Fabric e Azure Service Fabric Mesh Docker.

## <a name="using-azure-kubernetes-service"></a>Servizio Azure Kubernetes

Un cluster Kubernetes pool diversi host Docker e li espone come un singolo host Docker virtuale, pertanto è possibile distribuire più contenitori nel cluster e scalabilità orizzontale con qualsiasi numero di istanze di contenitore. Il cluster gestirà tutte le operazioni di gestione complesse, ad esempio la scalabilità, l'integrità e così via.

Il servizio Azure Kubernetes consente di semplificare la creazione, la configurazione e la gestione in Azure di un cluster di macchine virtuali preconfigurate per l'esecuzione di applicazioni in contenitori. Usando una configurazione ottimizzata degli strumenti open source più diffusi per la pianificazione e l'orchestrazione, il servizio Azure Kubernetes consente di usare le competenze esistenti o di avvalersi delle vaste competenze in continua crescita della community per distribuire e gestire le applicazioni basate su contenitori in Microsoft Azure.

Il servizio Azure Kubernetes ottimizza la configurazione degli strumenti e delle tecnologie open source più diffusi per clustering Docker in modo specifico per Azure. Si ottiene una soluzione che offre la portabilità per la configurazione di contenitori e applicazioni. È sufficiente selezionare le dimensioni, il numero di host e gli strumenti dell'agente di orchestrazione. Il servizio Azure Kubernetes gestisce tutte le altre operazioni.

![Struttura del cluster Kubernetes: è presente un nodo master che gestisce DNS, utilità di pianificazione, proxy e così via e diversi nodi del ruolo di lavoro che ospitano i contenitori.](media/image36.png)

**Figura 4-7**. Struttura semplificata e topologia del cluster Kubernetes

Figura 4-7 mostra la struttura di un cluster Kubernetes in cui un nodo master (VM) controlla la maggior parte della coordinazione del cluster e distribuire contenitori al resto dei nodi che vengono gestiti come un singolo pool dal punto di vista dell'applicazione. Ciò consente di scalabilità a migliaia o persino decine di migliaia di contenitori.

## <a name="development-environment-for-kubernetes"></a>Ambiente di sviluppo per Kubernetes

Nell'ambiente di sviluppo che [Docker annunciato nel mese di luglio 2018](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/), Kubernetes anche possibile eseguire in un singolo computer di sviluppo (Windows 10 o macOS), installando semplicemente [Desktop Docker](https://www.docker.com/community-edition). In un secondo momento, è possibile distribuire nel cloud (AKS) per un'ulteriore test di integrazione, come illustrato nella figura 4-8.

![Docker ha annunciato il supporto dei computer di sviluppo per i cluster Kubernetes nel luglio 2018 con Docker Desktop.](media/kubernetes-development-environment.png)

**Figura 4-8**. Esecuzione di Kubernetes in computer di sviluppo e nel cloud

## <a name="get-started-with-azure-kubernetes-service-aks"></a>Iniziare a usare con Azure Kubernetes Service (AKS)

Per iniziare a usare servizio contenitore di AZURE, distribuire un cluster del servizio contenitore di AZURE dal portale di Azure o usando l'interfaccia della riga di comando. Per altre informazioni sulla distribuzione di un cluster del servizio Azure Container, vedere [Distribuire un cluster del servizio Azure Kubernetes](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

Non sono previsti addebiti per il software installato per impostazione predefinita come parte del servizio Azure Kubernetes. Tutte le opzioni predefinite vengono implementate con software open source. Il servizio Azure Kubernetes è disponibile per più macchine virtuali in Azure. Vengono applicati addebiti solo per le istanze di risorse di calcolo scelte, oltre che per le altre risorse di infrastruttura sottostanti usate, ad esempio per le risorse di archiviazione e di rete. Non sono previsti addebiti incrementali per il servizio Azure Kubernetes.

Per l'implementazione di ulteriori informazioni sulla distribuzione in Kubernetes basano `kubectl` e originali `.yaml` i file, vedere il post sul [impostazione eShopOnContainers nel servizio contenitore di AZURE (Azure Kubernetes Service)](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.-Setting-the-solution-up-in-AKS-(Azure-Kubernetes-Service)).

## <a name="deploy-with-helm-charts-into-kubernetes-clusters"></a>Distribuire con i grafici Helm nel cluster Kubernetes

Quando si distribuisce un'applicazione a un cluster Kubernetes, è possibile usare originale `kubectl.exe` strumento della riga di comando usando i file di distribuzione basato sul formato nativo (`.yaml` file), come già accennato nella sezione precedente. Per le applicazioni Kubernetes più complesse, ad esempio durante la distribuzione di applicazioni complesse basate su microservizi, è tuttavia consigliabile usare [Helm](https://helm.sh/).

I grafici Helm consente di definire, versione, installazione, condivisione, aggiornamento o il rollback anche l'applicazione più complessa di Kubernetes.

Inoltre l'uso di Helm è consigliabile perché anche altri ambienti Kubernetes in Azure, come [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) sono basati sui grafici Helm.

Helm è gestita dal [Foundation Computing nativa Cloud (CNCF)](https://www.cncf.io/) in collaborazione con Microsoft, Google, Bitnami e la community di collaboratore di Helm.

Per ulteriori informazioni sull'implementazione in grafici Helm e Kubernetes, vedere il post sul [usando i grafici Helm per distribuire eShopOnContainers in AKS](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.1-Deploying-to-AKS-using-Helm-Charts).

## <a name="use-azure-dev-spaces-for-you-kubernetes-application-lifecycle"></a>Usare spazi di sviluppo di Azure automaticamente Kubernetes application Lifecycle Management

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) offre un'esperienza di sviluppo rapida e iterativa di Kubernetes per i team. Con una configurazione minima del computer di sviluppo, è possibile eseguire in modo iterativo ed eseguire il debug dei contenitori direttamente nel servizio Azure Kubernetes. È possibile sviluppare in Windows, Mac o Linux usando strumenti familiari come Visual Studio, Visual Studio Code o la riga di comando.

Come accennato, spazi di sviluppo di Azure Usa i grafici Helm quando si distribuiscono applicazioni basate su contenitori.

Spazi di sviluppo Azure consente ai team di sviluppo di essere più produttivi in Kubernetes perché consente di eseguire l'iterazione rapidamente e il debug del codice direttamente in un cluster Kubernetes globale in Azure usando semplicemente Visual Studio 2017 o Visual Studio Code. Tale cluster Kubernetes in Azure è un cluster Kubernetes gestito condiviso, in modo che il team possa lavorare in modo collaborativo. È possibile sviluppare il codice in isolamento e quindi distribuirlo al cluster globale per poi eseguire test completi con altri componenti senza replicare o simulare le dipendenze.

Come illustrato nella figura 4-9, la funzionalità più differenziazione in spazi di sviluppo di Azure è la funzionalità di creazione di "spazi" che è possono eseguire integrati al resto della distribuzione globale nel cluster.

![Azure Dev Spaces può combinare in modo trasparente microservizi di produzione con istanze di contenitore di sviluppo, per testare facilmente le nuove versioni.](media/image38.png)

**Figura 4-9**. Uso di più spazi in Azure Dev Spaces

In pratica, è possibile configurare uno spazio di sviluppo condiviso in Azure. Ogni sviluppatore può concentrarsi solo la parte dell'applicazione e può in modo iterativo sviluppare il codice "Pre-commit" in uno spazio di sviluppo che già contiene tutti gli altri servizi e risorse che dipendono i suoi scenari cloud. Le dipendenze sono sempre aggiornate e gli sviluppatori lavorano in un ambiente che rispecchia quello di produzione.

Spazi di sviluppo Azure fornisce il concetto di uno spazio, che consente di lavorare in isolamento e senza il timore di compromettere il funzionamento i membri del team. Questa funzionalità si basa sui prefissi URL; Se si utilizza un prefisso dello spazio di sviluppo nell'URL per la richiesta di un contenitore, gli spazi di sviluppo di Azure esegue una versione speciale del contenitore in cui distribuito per lo spazio, se presente. In caso contrario, verrà eseguita la versione globale/consolidata.

È possibile vedere le [pagina wiki di eShopOnContainers in Azure Dev spazi](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.2-Using-Azure-Dev-Spaces-and-AKS) per ottenere una panoramica pratica in un esempio concreto.

Per altre informazioni, vedere l'articolo sul [lo sviluppo in Team con spazi di sviluppo Azure](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Risorse aggiuntive

- **Introduzione al servizio Azure Kubernetes** \
  <https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal>

- **Azure Dev Spaces** \
  <https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces>

- **Kubernetes.** Il sito ufficiale. \
  <https://kubernetes.io/>

## <a name="using-azure-service-fabric"></a>Uso di Azure Service Fabric

Azure Service Fabric si è verificato dal passaggio di Microsoft dalla fornitura di "box" prodotti preconfezionati, generalmente di tipo monolitico, alla fornitura dei servizi. L'esperienza di creazione e gestione di grandi servizi su larga scala, ad esempio Database SQL di Azure, Azure Cosmos DB, il Bus di servizio di Azure o Backend di Cortana, la forma di Service Fabric. La piattaforma si è evoluta nel tempo con la sua continua adozione da parte di un numero crescente di servizi. Cosa ancora più importante, Service Fabric doveva essere eseguito non solo in Azure, ma anche nelle distribuzioni autonome di Windows Server.

L'obiettivo di Service Fabric è risolvere i complicati problemi di creare ed eseguire un servizio e utilizzare le risorse di infrastruttura in maniera efficiente, in modo che i team possano risolvere i problemi aziendali usando un approccio ai microservizi.

Service Fabric fornisce due aree generali che consentono di creare applicazioni che usano un approccio ai microservizi:

- Una piattaforma che fornisce servizi di sistema per distribuire, ridimensionare, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema, in effetti, abilitano molte delle caratteristiche dei microservizi descritte in precedenza.

- API di programmazione, o framework, che aiutano a creare applicazioni come microservizi: [Reliable Actors e Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). È possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API semplificano il processo e si integrano nella piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

Service Fabric è agnostico rispetto al modo in cui si crea il servizio ed è possibile usare qualsiasi tecnologia. Tuttavia, fornisce API di programmazione predefinite che rendono più semplice creare i microservizi.

Come illustrato nella figura 4-10, è possibile creare ed eseguire microservizi in Service Fabric come processi semplici o come contenitori Docker. È anche possibile combinare microservizi basati su contenitori con microservizi basati su processi all'interno dello stesso cluster di Service Fabric.

![Confronto tra Azure service Fabric cluster: Microservizi come processi in cui ogni nodo viene eseguito un processo per ogni microservizio; I Microservizi come contenitori in cui ogni nodo esegue Docker con contenitori diversi, un contenitore per ogni microservizio.](./media/azure-service-fabric-cluster-types.png)

**Figura 4-10**. Distribuzione di microservizi come processi o contenitori in Azure Service Fabric

I cluster di Service Fabric basati su host Linux e Windows possono eseguire rispettivamente contenitori Linux Docker e Windows.

Per informazioni aggiornate sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di una piattaforma che consente di definire una diversa architettura logica (microservizi aziendali o contesti delimitati) rispetto all'implementazione fisica. Ad esempio, se si implementa [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) nelle [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), che vengono introdotti nella sezione successiva, "[senza stato e i microservizi con stato](#stateless-versus-stateful-microservices), "è un concetto di microservizio aziendale con più servizi fisici.

Come illustrato nella figura 4-10 e da una prospettiva di microservizio logico/aziendale, quando si implementa un servizio Reliable Services di Service Fabric con stato, in genere sarà necessario implementare due livelli di servizi. Il primo è il servizio Reliable con stato di back-end, che gestisce più partizioni (ciascuna partizione è un servizio con stato). Il secondo è il servizio front-end, o Servizio gateway, responsabile del routing e dell'aggregazione dei dati in più partizioni o istanze del servizio con stato. Tale Servizio gateway gestisce anche la comunicazione lato client con i cicli di ripetizione che accedono al servizio back-end. Viene chiamato Servizio gateway se si implementa il servizio personalizzato. In alternativa, è possibile usare il [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) di Service Fabric predefinito.

![Service Fabric ha prescrizione specifica per supportare i diversi servizi reliable con stati in contenitori.](./media/service-fabric-stateful-business-microservice.png)

**Figura 4-11**. Microservizio aziendale con più istanze di servizio con stato e un front-end di gateway personalizzato

In ogni caso, quando si usa Reliable Services di Service Fabric con stato, è un microservizio logico o aziendale (Bounded Context) composta da più servizi fisici. Ognuno di essi, il servizio Gateway e servizio partizione potrebbe essere implementato come servizi API Web ASP.NET, come illustrato nella figura 4-11.

In Service Fabric, è possibile raggruppare e distribuire gruppi di servizi come [Applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), cioè l'unità di creazione pacchetto e distribuzione per l'agente di orchestrazione o il cluster. Di conseguenza, anche l'Applicazione di Service Fabric può essere mappata a questo limite del microservizio aziendale e logico autonomo, o Bounded Context, per poter distribuire questi servizi in modo autonomo.

### <a name="service-fabric-and-containers"></a>Service Fabric e contenitori

Per quanto riguarda i contenitori in Service Fabric, è anche possibile distribuire servizi in immagini del contenitore all'interno di un cluster di Service Fabric. Come illustrato nella figura 4-12, la maggior parte dei casi si sarà solo un contenitore per ogni servizio.

![Un'applicazione di Service Fabric può eseguire contenitori diversi l'accesso a un database esterno e l'intero set sarebbe dal limite logico di un Microservizio aziendale](./media/azure-service-fabric-business-microservice.png)

**Figura 4-12**. Microservizio aziendale con numerosi servizi (contenitori) in Service Fabric

I cosiddetti contenitori "collaterali" (due contenitori che devono essere distribuiti insieme nell'ambito di un servizio logico), tuttavia, sono possibili anche in Service Fabric. La cosa importante è che un microservizio aziendale è rappresentato dal limite logico intorno a diversi elementi coesivi. In molti casi, può trattarsi di un unico servizio con un unico modello di dati, ma in altri casi possono essere presenti anche diversi servizi fisici.

Si noti che è possibile combinare servizi in contenitori, nella stessa applicazione, Service Fabric e servizi nei processi, come illustrato nella figura 4-13.

![Un'applicazione di service fabric in esecuzione i servizi e contenitori nello stesso nodo.](./media/business-microservice-mapped-to-service-fabric-application.png)

**Figura 4-13**. Microservizio aziendale mappato a un'applicazione di Service Fabric con contenitori e servizi con stato

Per altre informazioni sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservizi con stato e senza stato

Come accennato in precedenza, ogni microservizio (Bounded Context logico) deve essere proprietario di un modello di dominio (dati e logica). Nel caso dei microservizi senza stato, i database sono esterni e si avvalgono di opzioni relazionali (SQL Server) o di opzioni NoSQL (Azure Cosmos DB o MongoDB).

Ma anche i servizi stessi possono essere senza stato in Service Fabric, e ciò significa che i dati risiedono all'interno del microservizio. I dati potrebbero esistere non solo nello stesso server, ma all'interno del processo del microservizio, in memoria e persistenti sulle unità disco rigido e replicate in altri nodi. La figura 4-30 mostra i diversi approcci.

![In servizi senza stato verrà mantenuto lo stato (persistenza, database) all'esterno del microservizio. Nei servizi con stato viene mantenuto lo stato all'interno del microservizio.](./media/stateless-vs-stateful-microservices.png)

**Figura 4-14**. Microservizi con stato e senza stato

Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto ai microservizi con stato, perché l'approccio è simile agli schemi tradizionali e noti. Tuttavia, i microservizi senza stato impongono la latenza tra il processo e le origini dati, oltre a comportare più elementi quando si prova a migliorare le prestazioni con cache e code aggiuntive. Il risultato è che si può finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, i [microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possono rappresentare un'ottima soluzione in scenari avanzati, perché non prevedono alcuna latenza tra la logica di dominio e i dati. L'elaborazione di grandi quantità di dati, i back-end per i giochi, i database come servizio e altri scenari a bassa latenza traggono tutti vantaggio dai servizi con stato, che abilitano lo stato locale per un accesso più rapido.

I servizi con e senza stato sono complementari. Ad esempio, come può notare nel diagramma a destra nella figura 4-31, un servizio con stato può essere suddivisa in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisca come servizio gateway che sappia come risolvere ogni partizione in base alle chiavi di partizione.

I servizi con stato presentano comunque degli svantaggi, Perché impongono un livello di complessità alta scalabilità orizzontale. La funzionalità che verrebbe di solito implementata dai sistemi di database esterni deve essere indirizzata alle attività quali la replica di dati tra microservizi con stato e partizionamento dei dati. Tuttavia, si tratta di una delle aree in cui un agente di orchestrazione come [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture), con i suoi [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis), può essere di grande aiuto, in particolare semplificando i microservizi con stato con l'[API Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework del microservizio che abilitano i servizi con stato, che supportano lo schema Actor, e che migliorano la tolleranza di errore e la latenza tra logica di business e dati, sono Microsoft [Orleans](https://github.com/dotnet/orleans), di Microsoft Research, e [Akka.NET](https://getakka.net/). Entrambi i framework stanno attualmente migliorando il supporto per Docker.

Tenere presente che i contenitori Docker sono senza stato. Se si vuole implementare un servizio con stato, è necessario uno dei framework prescrittivi e di livello superiore aggiuntivi di cui si è parlato in precedenza.

## <a name="using-azure-service-fabric-mesh"></a>Uso di Azure Service Fabric Mesh

Della rete di Azure Service Fabric è un servizio completamente gestito che consente agli sviluppatori di compilare e distribuire applicazioni mission-critical senza dover gestire qualsiasi infrastruttura. Usare Service Fabric Mesh per compilare ed eseguire applicazioni di microservizi distribuite sicure e scalabili su richiesta.

Come illustrato nella figura 4-15, le applicazioni ospitate in Service Fabric Mesh eseguire e ridimensionare senza doversi preoccupare dell'infrastruttura fornendo l'alimentazione.

![Un'app multi-contenitore in esecuzione nel desktop di Docker può essere distribuita per Azure Service Fabric Mesh senza doverti preoccupare dell'infrastruttura.](media/image39.png)

**Figura 4-15**. Distribuzione di un'applicazione di microservizi/contenitori in Service Fabric Mesh

Dietro le quinte, Service Fabric Mesh è costituito da cluster di migliaia di computer. Tutte le operazioni dei cluster non sono visibili per lo sviluppatore. È sufficiente caricare i contenitori e specificare le risorse necessarie, i requisiti di disponibilità e i limiti delle risorse. Service Fabric Mesh alloca automaticamente l'infrastruttura richiesta dalla distribuzione dell'applicazione, gestendo anche gli errori di infrastruttura e assicurando la disponibilità elevata delle applicazioni. È sufficiente occuparsi dell'integrità e della velocità di risposta dell'applicazione, ignorando l'infrastruttura.

Per altre informazioni, vedere la [documentazione di Service Fabric Mesh](https://docs.microsoft.com/azure/service-fabric-mesh/).

## <a name="choosing-orchestrators-in-azure"></a>Scelta degli agenti di orchestrazione in Azure

La tabella seguente offre indicazioni sull'agente di orchestrazione da usare a seconda dei carichi di lavoro e del sistema operativo.

![Servizi di Azure Kubernetes è più maturo in Linux rispetto a in Windows e viene principalmente utilizzato per la distribuzione di microservizi basati su contenitori. Azure Service Fabric (sia cluster che mesh) è più maturo in Windows che in Linux ed è comunemente usato per microservizi basati su contenitori, microservizi basati su processi normali e servizi con stato.](media/image40.png)

**Figura 4-16**. Selezione dell'agente di orchestrazione nel materiale sussidiario su Azure

>[!div class="step-by-step"]
>[Precedente](soa-applications.md)
>[Successivo](deploy-azure-kubernetes-service.md)
