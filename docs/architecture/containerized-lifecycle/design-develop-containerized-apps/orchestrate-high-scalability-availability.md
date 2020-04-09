---
title: Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate
description: Le applicazioni di produzione reale devono essere distribuite e gestite con agenti di orchestrazione che gestiscono l'integrità, il carico di lavoro e i cicli di vita di tutti i contenitori.
ms.date: 02/15/2019
ms.openlocfilehash: 369971455168026d768220dae6e2da5ce92bc698
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988999"
---
# <a name="orchestrating-microservices-and-multi-container-applications-for-high-scalability-and-availability"></a>Orchestrazione di microservizi e applicazioni a più contenitori per la scalabilità e la disponibilità elevate

L'uso di agenti di orchestrazione per applicazioni pronte per la produzione è essenziale se l'applicazione è basata su microservizi o suddivisa tra più contenitori. Come illustrato in precedenza, in un approccio basato su microservizi ogni microservizio è proprietario dei rispettivi modelli e dati, quindi sarà autonomo dal punto di vista dello sviluppo e della distribuzione. Anche se è disponibile un'applicazione più tradizionale costituita da più servizi, ad esempio SOA, saranno comunque disponibili più contenitori o servizi che comprendono una singola applicazione aziendale da distribuire come sistema distribuito. Il ridimensionamento e la gestione di questi tipi di sistemi sono complessi ed è quindi assolutamente necessario un agente di orchestrazione se si vuole ottenere un'applicazione a più contenitori pronta per la produzione e ridimensionabile.

La figura 4-6 illustra la distribuzione in un cluster di un'applicazione costituita da più microservizi (contenitori).

![Diagramma che mostra le applicazioni Docker composte in un cluster.](./media/orchestrate-high-scalability-availability/composed-docker-applications-cluster.png)

**Figura 4-6**. Cluster di contenitori

Si tratta di un approccio apparentemente logico. Occorre tuttavia stabilire come vengono gestiti il bilanciamento del carico, il routing e l'orchestrazione di queste applicazioni composte.

L'interfaccia della riga di comando Docker soddisfa le esigenze di gestione di un contenitore in un host, ma non è sufficiente quando si tratta di gestire più contenitori distribuiti in più host per applicazioni distribuite più complesse. Nella maggior parte dei casi è necessaria una piattaforma di gestione in grado di avviare automaticamente i contenitori, aumentare il numero di istanze per immagine dei contenitori, sospenderli o arrestarli in caso di necessità e idealmente controllare anche la rispettiva modalità di accesso a risorse come la rete e l'archiviazione dati.

Per andare oltre la gestione di singoli contenitori o app composte semplici e passare ad applicazioni aziendali di dimensioni maggiori con microservizi, è necessario usare l'orchestrazione e le piattaforme di clustering.

Dal punto di vista dell'architettura e dello sviluppo, se si creano applicazioni aziendali di grandi dimensioni basate su microservizi, è importante conoscere le piattaforme e i prodotti seguenti che supportano gli scenari avanzati:

- **Cluster e agenti di orchestrazione.** Quando è necessario aumentare il numero di istanze delle applicazioni in molti host Docker, ad esempio nel caso di un'applicazione di grandi dimensioni basata su microservizi, è essenziale poter gestire tutti questi host come un singolo cluster tramite l'astrazione della complessità della piattaforma sottostante. I cluster di contenitori e gli agenti di orchestrazione offrono questo vantaggio. Sono esempi di agenti di orchestrazione Azure Service Fabric e Kubernetes. Kubernetes è disponibile in Azure tramite il servizio Azure Kubernetes.

- **Utilità di pianificazione.** Per *pianificazione* si intende la possibilità per un amministratore di avviare contenitori in un cluster in modo che le utilità di pianificazione forniscano anche un'interfaccia utente. Un'utilità di pianificazione di cluster ha molte responsabilità, tra cui usare in modo efficiente le risorse del cluster, configurare i vincoli specificati dall'utente, bilanciare in modo efficiente il carico dei contenitori nei nodi e negli host e infine assicurare l'affidabilità in caso di errori, offrendo al tempo stesso una disponibilità elevata.

I concetti di cluster e utilità di pianificazione sono strettamente correlati, quindi i prodotti offerti da diversi fornitori includono spesso entrambi i set di funzionalità. La sezione seguente mostra le opzioni più importanti a livello di piattaforma e software disponibili per i cluster e per le utilità di pianificazione. Questi agenti di orchestrazione sono offerti ampiamente in cloud pubblici quali Azure.

## <a name="software-platforms-for-container-clustering-orchestration-and-scheduling"></a>Piattaforme software per il clustering, l'orchestrazione e la pianificazione dei contenitori

| Piattaforma | Commenti |
|:---:|:---|
| **Kubernetes** <br/> ![Un'immagine del logo Kubernetes.](./media/orchestrate-high-scalability-availability/kubernetes-container-orchestration-system-logo.png) | [*Kubernetes*](https://kubernetes.io/) è un prodotto open source che offre funzionalità per l'infrastruttura dei cluster, la pianificazione dei contenitori e l'orchestrazione. Consente di automatizzare la distribuzione, il ridimensionamento e la gestione di contenitori di applicazioni in cluster di host. <br/> <br/> *Kubernetes* offre un'infrastruttura incentrata sui contenitori che raggruppa i contenitori di applicazioni in unità logiche per semplificarne la gestione e l'individuazione. <br/> <br/> *Kubernetes* è maturo in Linux, meno maturo in Windows. |
| **Servizio Azure Kubernetes** <br/> ![Immagine del logo del servizio Azure Kubernetes.](./media/orchestrate-high-scalability-availability/azure-kubernetes-service-logo.png) | [Il servizio Azure Kubernetes (AKS)](https://azure.microsoft.com/services/kubernetes-service/) è un servizio di orchestrazione del contenitore Kubernetes gestito in Azure che semplifica la gestione, la distribuzione e le operazioni del cluster Kubernetes.Azure Kubernetes Service (AKS) is a managed Kubernetes container orchestration service in Azure that semplifies Kubernetes's management, deployment, and operations. |
| **Azure Service Fabric** <br/> ![Immagine del logo di Azure Service Fabric.](./media/orchestrate-high-scalability-availability/azure-service-fabric-logo.png) | [Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) è una piattaforma di microservizi Microsoft per la creazione di applicazioni. È un [agente di orchestrazione](https://docs.microsoft.com/azure/service-fabric/service-fabric-cluster-resource-manager-introduction) di servizi e crea cluster di macchine virtuali. Service Fabric può distribuire servizi come contenitori o come processi semplici. Può anche combinare servizi nei processi con servizi nei contenitori entro la stessa applicazione e lo stesso cluster. <br/> <br/> I cluster di *Service Fabric* possono essere distribuiti in Azure, in locale o in qualsiasi cloud. La distribuzione in Azure è tuttavia semplificata con un approccio gestito. <br/> <br/> *Service Fabric* offre [modelli di programmazione di Service Fabric](https://azure.microsoft.com/documentation/articles/service-fabric-choose-framework/) prescrittivi aggiuntivi e facoltativi, come [servizi con stato](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-services-introduction/) e [Reliable Actors](https://azure.microsoft.com/documentation/articles/service-fabric-reliable-actors-introduction/). <br/> <br/> *Service Fabric* è maturo in Windows (anni di evoluzione in Windows), meno maturo in Linux. <br/> <br/> I contenitori Linux e Windows sono supportati in Service Fabric dal 2017. |
| **Azure Service Fabric Mesh** <br/> ![Immagine del logo mesh di Azure Service Fabric.](./media/orchestrate-high-scalability-availability/azure-service-fabric-mesh-logo.png) | [*Azure Service Fabric Mesh*](https://docs.microsoft.com/azure/service-fabric-mesh/service-fabric-mesh-overview) è analogo a Service Fabric in termini di affidabilità, prestazioni cruciali e scalabilità, ma offre anche una piattaforma completamente gestita e serverless. Non è necessario gestire un cluster, macchine virtuali, risorse di archiviazione o configurazione della rete. È sufficiente concentrarsi sullo sviluppo dell'applicazione. <br/> <br/> *Service Fabric Mesh* supporta contenitori Windows e Linux, consentendo di sviluppare qualsiasi linguaggio di programmazione e framework di propria scelta.

## <a name="using-container-based-orchestrators-in-azure"></a>Uso degli agenti di orchestrazione basati su contenitori in Azure

Alcuni fornitori cloud, tra cui Azure, Amazon EC2 Container Service e Google Container Engine, offrono il supporto per contenitori Docker oltre al supporto per i contenitori e gli agenti di orchestrazione Docker. Azure offre il supporto per cluster e agenti di orchestrazione Docker tramite il servizio Azure Kubernetes, Azure Service Fabric e Azure Service Fabric Mesh.

## <a name="using-azure-kubernetes-service"></a>Servizio Azure Kubernetes

Un cluster Kubernetes crea vari pool di host Docker e li espone come un singolo host Docker virtuale, per consentire di distribuire più contenitori nel cluster e aumentare a piacere il numero di istanze contenitore. Il cluster gestirà tutte le operazioni di gestione complesse, ad esempio la scalabilità, l'integrità e così via.

Il servizio Azure Kubernetes consente di semplificare la creazione, la configurazione e la gestione in Azure di un cluster di macchine virtuali preconfigurate per l'esecuzione di applicazioni in contenitori. Usando una configurazione ottimizzata degli strumenti open source più diffusi per la pianificazione e l'orchestrazione, il servizio Azure Kubernetes consente di usare le competenze esistenti o di avvalersi delle vaste competenze in continua crescita della community per distribuire e gestire le applicazioni basate su contenitori in Microsoft Azure.

Il servizio Azure Kubernetes ottimizza la configurazione degli strumenti e delle tecnologie open source più diffusi per clustering Docker in modo specifico per Azure. Si ottiene una soluzione che offre la portabilità per la configurazione di contenitori e applicazioni. È sufficiente selezionare le dimensioni, il numero di host e gli strumenti dell'agente di orchestrazione. Il servizio Azure Kubernetes gestisce tutte le altre operazioni.

![Diagramma che mostra una struttura cluster Kubernetes.](./media/orchestrate-high-scalability-availability/kubernetes-cluster-simplified-structure.png)

**Figura 4-7**. Struttura semplificata e topologia del cluster Kubernetes

La figura 4-7 illustra la struttura di un cluster Kubernetes in cui un nodo master (VM) controlla la maggior parte del coordinamento del cluster. È possibile distribuire i contenitori al resto dei nodi che vengono gestiti come un singolo pool dal punto di vista dell'applicazione. Questa struttura consente di scalare aggiungendo migliaia o persino decine di migliaia di contenitori.

## <a name="development-environment-for-kubernetes"></a>Ambiente di sviluppo per Kubernetes

Nell'ambiente di sviluppo che [Docker ha annunciato nel mese di luglio 2018](https://blog.docker.com/2018/07/kubernetes-is-now-available-in-docker-desktop-stable-channel/) Kubernetes può essere eseguito anche in un singolo computer di sviluppo (Windows 10 o macOS) semplicemente installando [Docker Desktop](https://www.docker.com/community-edition). In un secondo momento sarà possibile procedere alla distribuzione nel cloud (servizio Azure Kubernetes) per altri test di integrazione, come illustrato nella figura 4-8.

![Diagramma che mostra Kubernetes in un computer di sviluppo quindi distribuito in AKS.](./media/orchestrate-high-scalability-availability/kubernetes-development-environment.png)

**Figura 4-8**. Esecuzione di Kubernetes in computer di sviluppo e nel cloud

## <a name="get-started-with-azure-kubernetes-service-aks"></a>Introduzione al servizio Azure Kubernetes

Per iniziare a usare il servizio Azure Kubernetes, distribuire un cluster del servizio Azure Kubernetes dal portale di Azure o tramite l'interfaccia della riga di comando. Per altre informazioni sulla distribuzione di un cluster Kubernetes in Azure, vedere [Distribuire un cluster del servizio Azure Kubernetes](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

Non sono previsti addebiti per il software installato per impostazione predefinita come parte del servizio Azure Kubernetes. Tutte le opzioni predefinite vengono implementate con software open source. Il servizio Azure Kubernetes è disponibile per più macchine virtuali in Azure. Vengono applicati addebiti solo per le istanze di risorse di calcolo scelte, oltre che per le altre risorse di infrastruttura sottostanti usate, ad esempio per le risorse di archiviazione e di rete. Non sono previsti addebiti incrementali per il servizio Azure Kubernetes.

Per altre informazioni sull'implementazione nella distribuzione in Kubernetes basata su `kubectl` e sui file con estensione `.yaml` originali, vedere il post che spiega come [impostare eShopOnContainers nel servizio Azure Kubernetes](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.-Setting-the-solution-up-in-AKS-(Azure-Kubernetes-Service)).

## <a name="deploy-with-helm-charts-into-kubernetes-clusters"></a>Distribuire con grafici Helm in cluster Kubernetes

Quando si distribuisce un'applicazione a un cluster Kubernetes, è possibile usare lo strumento dell'interfaccia della riga di comando `kubectl.exe` originale con i file di distribuzione basati sul formato nativo (file con estensione `.yaml`), come già accennato nella sezione precedente. Per le applicazioni Kubernetes più complesse, ad esempio durante la distribuzione di applicazioni complesse basate su microservizi, è tuttavia consigliabile usare [Helm](https://helm.sh/).

I grafici Helm consentono di definire, controllare la versione, installare, condividere, aggiornare o ripristinare lo stato precedente anche dell'applicazione Kubernetes più complessa.

Inoltre l'uso di Helm è consigliabile perché anche altri ambienti Kubernetes in Azure, come [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) sono basati sui grafici Helm.

Helm è gestito da [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/), in collaborazione con Microsoft, Google, Bitnami e la community di collaboratori di Helm.

Per altre informazioni sull'implementazione dei grafici Helm e Kubernetes, vedere il post che spiega come [usare i grafici Helm per distribuire eShopOnContainers nel servizio Azure Kubernetes](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.1-Deploying-to-AKS-using-Helm-Charts).

## <a name="use-azure-dev-spaces-for-you-kubernetes-application-lifecycle"></a>Usare Azure Dev Spaces per il ciclo di vita dell'applicazione Kubernetes

[Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces) offre un'esperienza di sviluppo kubernetes rapida e iterativa per i team. Con una configurazione minima del computer di sviluppo, è possibile eseguire il codice in maniera iterativa ed eseguire il debug dei contenitori direttamente nel servizio Azure Kubernetes. È possibile sviluppare in Windows, Mac o Linux usando strumenti familiari come Visual Studio, Visual Studio Code o la riga di comando.

Come accennato, Azure Dev Spaces usa i grafici Helm nella distribuzione delle applicazioni basate su contenitori.

Azure Dev Spaces aiuta i team di sviluppo a essere più produttivi in Kubernetes perché consente di eseguire rapidamente l'iterazione e il debug del codice direttamente in un cluster Kubernetes globale in Azure usando semplicemente Visual Studio 2017 o Visual Studio Code. Tale cluster Kubernetes in Azure è un cluster Kubernetes gestito condiviso, in modo che il team possa lavorare in modo collaborativo. È possibile sviluppare il codice in isolamento e quindi distribuirlo al cluster globale per poi eseguire test completi con altri componenti senza replicare o simulare le dipendenze.

Come illustrato nella figura 4-9, la funzionalità più differenziante in Azure Dev Spaces è la capacità di creare "spazi" che possono essere eseguiti in modo integrato nel resto della distribuzione globale nel cluster:As shown in the figure 4-9, the most differentiating feature in Azure Dev Spaces is the capability of creating 'spaces' that can run integrated to the rest of the global deployment in the cluster:

![Diagramma che mostra l'uso di più spazi negli spazi di sviluppo di Azure.Diagram showing the use of multiple spaces in Azure Dev Spaces.](./media/orchestrate-high-scalability-availability/use-multiple-spaces-azure-dev.png)

**Figura 4-9**. Uso di più spazi in Azure Dev Spaces

Azure Dev Spaces può combinare in modo trasparente microservizi di produzione con istanze di contenitore di sviluppo, per testare facilmente le nuove versioni. Fondamentalmente è possibile impostare uno spazio di sviluppo condiviso in Azure. Ogni sviluppatore può concentrarsi solo sulla parte assegnata dell'applicazione e sviluppare in modo iterativo il codice pre-commit in uno spazio di sviluppo che già contiene tutti gli altri servizi e le risorse del cloud da cui dipendono i suoi scenari. Le dipendenze sono sempre aggiornate e gli sviluppatori lavorano in un modo che rispecchia la produzione.

Azure Dev Spaces usa il concetto di spazio, che consente di lavorare in isolamento e senza timore di inficiare il lavoro degli altri membri del team. Questa funzionalità si basa sull'uso di prefissi URL, perciò se si usa un prefisso di Azure Dev Spaces nell'URL per una richiesta del contenitore, Azure Dev Spaces esegue una versione speciale del contenitore distribuito per quello spazio, se esistente. In caso contrario, verrà eseguita la versione globale/consolidata.

È possibile visualizzare la [pagina wiki eShopOnContainers in Azure Dev Spaces](https://github.com/dotnet-architecture/eShopOnContainers/wiki/10.2-Using-Azure-Dev-Spaces-and-AKS) per ottenere una visualizzazione pratica di un esempio concreto.

Per altre informazioni, vedere l'articolo sullo [sviluppo in team con Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/team-development-netcore).

## <a name="additional-resources"></a>Risorse aggiuntive

- **Introduzione al servizio Azure Kubernetes (AKS)Getting started with Azure Kubernetes Service (AKS)** \
  <https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal>

- **Spazi di sviluppo di AzureAzure Dev Spaces** \
  <https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces>

- **Kubernetes.** Il sito ufficiale. \
  <https://kubernetes.io/>

## <a name="using-azure-service-fabric"></a>Uso di Azure Service Fabric

Azure Service Fabric è nato dal passaggio di Microsoft dall'offerta di prodotti completi, di stile generalmente monolitico, all'offerta di servizi. L'esperienza di creazione e gestione di grandi servizi su larga scala, come il database SQL di Azure, Azure Cosmos DB, il bus di servizio di Azure o Backend di Cortana, ha dato forma a Service Fabric. La piattaforma si è evoluta nel tempo con l'adozione di un numero di servizi sempre maggiore. Era importante che Service Fabric potesse essere eseguito non solo in Azure, ma anche autonomamente nelle distribuzioni di Windows Server.

L'obiettivo di Service Fabric è risolvere i complicati problemi di creare ed eseguire un servizio e utilizzare le risorse di infrastruttura in maniera efficiente, in modo che i team possano risolvere i problemi aziendali usando un approccio ai microservizi.

Service Fabric offre due vaste aree per facilitare la creazione di applicazioni che usano un approccio basato sui microservizi:

- Una piattaforma che fornisce servizi di sistema per distribuire, ridimensionare, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema, in effetti, abilitano molte delle caratteristiche dei microservizi descritte in precedenza.

- API di programmazione, o framework, che facilitano la compilazione di applicazioni come microservizi: [Reliable Actors e Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). È possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API semplificano il processo e si integrano nella piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

Service Fabric è agnostico rispetto al modo in cui si crea il servizio ed è possibile usare qualsiasi tecnologia. Tuttavia, fornisce API di programmazione predefinite che rendono più semplice creare i microservizi.

Come illustrato nella figura 4-10, è possibile creare ed eseguire microservizi in Service Fabric come processi semplici o come contenitori Docker. È anche possibile combinare microservizi basati su contenitori con microservizi basati su processi all'interno dello stesso cluster di Service Fabric.

![Diagramma che mostra il confronto dei cluster di Azure Service Fabric.Diagram showing the comparison of Azure Service Fabric clusters.](./media/orchestrate-high-scalability-availability/azure-service-fabric-cluster-types.png)

**Figura 4-10**. Distribuzione di microservizi come processi o contenitori in Azure Service Fabric

Nella prima immagine vengono visualizzati i microservizi come processi, in cui ogni nodo esegue un processo per ogni microservizio. Nella seconda immagine vengono visualizzati i microservizi come contenitori, in cui ogni nodo esegue Docker con diversi contenitori, un contenitore per microservizio. I cluster di Service Fabric basati su host Linux e Windows possono eseguire rispettivamente contenitori Linux Docker e Windows.

Per informazioni aggiornate sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di piattaforma in cui è possibile definire una diversa architettura logica (microservizi aziendali o contesti delimitati) rispetto all'implementazione fisica. Se, ad esempio, in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) si implementano [Servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction), che verranno introdotti nella sezione seguente [Microservizi senza stato e con stato](#stateless-versus-stateful-microservices) si può sviluppare un concetto di microservizio aziendale con più servizi fisici.

Come illustrato nella figura 4-10 e da un punto di vista di microservizio logico/aziendale, quando si implementa un servizio Reliable con stato di Service Fabric, è in genere necessario implementare due livelli di servizi. Il primo è il servizio Reliable con stato di back-end, che gestisce più partizioni (ciascuna partizione è un servizio con stato). Il secondo è il servizio front-end, o Servizio gateway, responsabile del routing e dell'aggregazione dei dati in più partizioni o istanze del servizio con stato. Tale Servizio gateway gestisce anche la comunicazione lato client con i cicli di ripetizione che accedono al servizio back-end. Viene chiamato Servizio gateway se si implementa il servizio personalizzato. In alternativa, è possibile usare il [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) di Service Fabric predefinito.

![Diagramma che mostra diversi servizi con stato nei contenitori.](./media/orchestrate-high-scalability-availability/service-fabric-stateful-business-microservice.png)

**Figura 4-11**. Microservizio aziendale con diverse istanze del servizio con stato e un front-end di gateway personalizzato

In ogni caso, quando si usano i servizi Reliable con stato di Service Fabric, si ottiene anche un microservizio logico o aziendale (Bounded Context) che è costituito da più servizi fisici. Ognuno di questi, il servizio gateway e il servizio delle partizioni, può essere implementato come servizio API Web ASP.NET., come illustrato nella figura 4-11. Service Fabric è in grado di supportare i diversi servizi Reliable con stato in contenitori.

In Service Fabric, è possibile raggruppare e distribuire gruppi di servizi come [Applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), cioè l'unità di creazione pacchetto e distribuzione per l'agente di orchestrazione o il cluster. Di conseguenza, anche l'Applicazione di Service Fabric può essere mappata a questo limite del microservizio aziendale e logico autonomo, o Bounded Context, per poter distribuire questi servizi in modo autonomo.

### <a name="service-fabric-and-containers"></a>Service Fabric e contenitori

Per quanto riguarda i contenitori in Service Fabric, è anche possibile distribuire servizi in immagini del contenitore all'interno di un cluster di Service Fabric. Come illustrato nella figura 4-12, nella maggior parte dei casi è presente un solo contenitore per ogni servizio.

![Diagramma che mostra un contenitore per servizio inserito in un database.](./media/orchestrate-high-scalability-availability/azure-service-fabric-business-microservice.png)

**Figura 4-12**. Microservizio aziendale con numerosi servizi (contenitori) in Service Fabric

Un'applicazione Service Fabric può eseguire diversi contenitori che accedono a un database esterno e l'intero set sarebbe il limite logico di un microservizio aziendale. I cosiddetti contenitori "collaterali" (due contenitori che devono essere distribuiti insieme nell'ambito di un servizio logico), tuttavia, sono possibili anche in Service Fabric. La cosa importante è che un microservizio aziendale è rappresentato dal limite logico intorno a diversi elementi coesivi. In molti casi, può trattarsi di un unico servizio con un unico modello di dati, ma in altri casi possono essere presenti anche diversi servizi fisici.

Si noti che nella stessa applicazione di Service Fabric è possibile combinare servizi in processi e servizi all'interno di contenitori, come illustrato nella figura 4-13.

![Diagramma che mostra i servizi nei processi e nei contenitori nella stessa app.](./media/orchestrate-high-scalability-availability/business-microservice-mapped-to-service-fabric-application.png)

**Figura 4-13**. Microservizio aziendale mappato a un'applicazione di Service Fabric con contenitori e servizi con stato

Per altre informazioni sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservizi con stato e senza stato

Come accennato in precedenza, ogni microservizio (Bounded Context logico) deve essere proprietario di un modello di dominio (dati e logica). Nel caso dei microservizi senza stato, i database sono esterni e si avvalgono di opzioni relazionali (SQL Server) o di opzioni NoSQL (Azure Cosmos DB o MongoDB).

Ma anche i servizi stessi possono essere senza stato in Service Fabric, e ciò significa che i dati risiedono all'interno del microservizio. I dati potrebbero esistere non solo nello stesso server, ma all'interno del processo del microservizio, in memoria e persistenti sulle unità disco rigido e replicate in altri nodi. Figura 4-14 mostra i diversi approcci.

![Diagramma che mostra un confronto tra un servizio senza stato e con stato.](./media/orchestrate-high-scalability-availability/stateless-vs-stateful-microservices.png)

**Figura 4-14**. Microservizi con stato e senza stato

Nei servizi senza stato, lo stato (persistenza, database) viene mantenuto all'esterno del microservizio. Nei servizi con stato, lo stato viene mantenuto all'interno del microservizio. Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto ai microservizi con stato, perché l'approccio è simile agli schemi tradizionali e noti. Tuttavia, i microservizi senza stato impongono la latenza tra il processo e le origini dati, oltre a comportare più elementi quando si prova a migliorare le prestazioni con cache e code aggiuntive. Il risultato è che si può finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, i [microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possono rappresentare un'ottima soluzione in scenari avanzati, perché non prevedono alcuna latenza tra la logica di dominio e i dati. L'elaborazione di grandi quantità di dati, i back-end per i giochi, i database come servizio e altri scenari a bassa latenza traggono tutti vantaggio dai servizi con stato, che abilitano lo stato locale per un accesso più rapido.

I servizi con e senza stato sono complementari. Ad esempio, come si può vedere nel diagramma a destra nella Figura 4-14, un servizio con stato può essere suddiviso in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisca come servizio gateway che sappia come risolvere ogni partizione in base alle chiavi di partizione.

I servizi con stato presentano comunque degli svantaggi, Essi impongono un elevato livello di complessità da scalare orizzontalmente. Le funzionalità che in genere vengono implementate dai sistemi di database esterni devono essere indirizzate per attività quali la replica dei dati tra microservizi con stato e il partizionamento dei dati. Tuttavia, si tratta di una delle aree in cui un agente di orchestrazione come [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture), con i suoi [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis), può essere di grande aiuto, in particolare semplificando i microservizi con stato con l'[API Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework di microservizi che consentono servizi con stato, supportano il modello Attore e migliorano la tolleranza di errore e la latenza tra la logica di business e i dati sono Microsoft [Orleans](https://github.com/dotnet/orleans), di Microsoft Research e [Akka.NET](https://getakka.net/). Entrambi i framework stanno attualmente migliorando il supporto per Docker.

Si noti che anche i contenitori Docker sono senza stato. Se si vuole implementare un servizio con stato, è necessario uno dei framework prescrittivi e di livello superiore aggiuntivi di cui si è parlato in precedenza.

## <a name="using-azure-service-fabric-mesh"></a>Uso di Azure Service Fabric Mesh

Azure Service Fabric Mesh è un servizio completamente gestito che consente agli sviluppatori di compilare e distribuire applicazioni cruciali senza gestire alcuna infrastruttura. È possibile usare mesh Service Fabric per creare ed eseguire applicazioni di microservizi sicure e distribuite, ridimensionabili su richiesta.

Come illustrato nella figura 4-15, è possibile eseguire e ridimensionare le applicazioni ospitate in Service Fabric Mesh senza doversi preoccupare dell'infrastruttura su cui sono basate.

![Diagramma che mostra la distribuzione da un repository locale a Service Fabric Mesh.Diagram showing deployment from a local repository to Service Fabric Mesh.](media/orchestrate-high-scalability-availability/deploy-microservice-containers-apps-service-fabric-mesh.png)

**Figura 4-15**. Distribuzione di un'applicazione di microservizi/contenitori in Service Fabric Mesh

Dietro le quinte, Service Fabric Mesh è costituito da cluster di migliaia di computer. Tutte le operazioni cluster non sono visibili dallo sviluppatore. È sufficiente caricare i contenitori e specificare le risorse necessarie, i requisiti di disponibilità e i limiti delle risorse. Service Fabric Mesh alloca automaticamente l'infrastruttura richiesta per la distribuzione delle applicazioni e gestisce anche gli errori di infrastruttura, assicurandosi che le applicazioni siano a disponibilità elevata. È sufficiente preoccuparsi dell'integrità e della velocità di risposta dell'applicazione, ignorando l'infrastruttura.

Per ulteriori informazioni, vedere la [documentazione](https://docs.microsoft.com/azure/service-fabric-mesh/)di Service Fabric Mesh .

## <a name="choosing-orchestrators-in-azure"></a>Scelta degli agenti di orchestrazione in Azure

La tabella seguente offre indicazioni sull'agente di orchestrazione da usare a seconda dei carichi di lavoro e del sistema operativo.

![Immagine di una tabella che confronta Kubernetes e Service Fabric.](media/orchestrate-high-scalability-availability/orchestrator-selection-azure-guidance.png)

**Figura 4-16**. Selezione dell'agente di orchestrazione nel materiale sussidiario su Azure

>[!div class="step-by-step"]
>[Successivo](soa-applications.md)
>[precedente](deploy-azure-kubernetes-service.md)
