---
title: Uso di Azure Service Fabric
description: Informazioni sui modelli di applicazione Azure Service Fabric che è possibile usare, oltre all'uso di Service Fabric solo per l'orchestrazione di contenitori.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/20/2018
ms.openlocfilehash: b29be05f5ab353ddfae0d23211efaf57979d0604
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53126965"
---
# <a name="using-azure-service-fabric"></a>Uso di Azure Service Fabric

Azure Service Fabric è nato dal passaggio di Microsoft dall'offerta di prodotti completi, di stile decisamente monolitico, all'offerta di servizi. L'esperienza di creazione e gestione di grandi servizi su larga scala, come il database SQL di Microsoft Azure, Azure Cosmos DB, il bus di servizio di Microsoft Azure e il back-end di Cortana, ha dato forma a Service Fabric. La piattaforma si è evoluta nel tempo con la sua continua adozione da parte di un numero crescente di servizi. Cosa ancora più importante, Service Fabric doveva essere eseguito non solo in Azure, ma anche nelle distribuzioni autonome di Windows Server.

L'obiettivo di Service Fabric è risolvere i complicati problemi di creare ed eseguire un servizio e utilizzare le risorse di infrastruttura in maniera efficiente, in modo che i team possano risolvere i problemi aziendali usando un approccio ai microservizi.

Service Fabric fornisce due aree generali che consentono di creare applicazioni che usano un approccio ai microservizi:

- Una piattaforma che fornisce servizi di sistema per distribuire, ridimensionare, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema, in effetti, abilitano molte delle caratteristiche dei microservizi descritte in precedenza.

- API di programmazione o framework che aiutano a creare applicazioni come microservizi: [Reliable Actors e Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). È possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API semplificano il processo e si integrano nella piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

Service Fabric è agnostico rispetto al modo in cui si crea il servizio ed è possibile usare qualsiasi tecnologia. Tuttavia, fornisce API di programmazione predefinite che rendono più semplice creare i microservizi.

Come illustrato nella figura 4-27, è possibile creare ed eseguire microservizi in Service Fabric come processi semplici o come contenitori Docker. È anche possibile combinare microservizi basati su contenitori con microservizi basati su processi all'interno dello stesso cluster di Service Fabric.

![Confronto tra cluster di Azure Service Fabric: microservizi basati su processi, in cui ogni nodo esegue un processo per ogni microservizio, e microservizi basati su contenitori, in cui ogni nodo esegue Docker con più contenitori, uno per ogni microservizio.](./media/image30.png)

**Figura 4-27**. Distribuzione di microservizi come processi o contenitori in Azure Service Fabric

I cluster di Service Fabric basati su host Linux e Windows possono eseguire rispettivamente contenitori Linux Docker e Windows.

Per informazioni aggiornate sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di piattaforma in cui è possibile definire una diversa architettura logica (microservizi aziendali o contesti delimitati) rispetto all'implementazione fisica che è stata introdotta nella sezione [Architettura logica e architettura fisica](logical-versus-physical-architecture.md). Se, ad esempio, si implementano [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction), presentati nella sezione [Microservizi con stato e senza stato](#stateless-versus-stateful-microservices) più avanti, si può sviluppare un concetto di microservizio aziendale con più servizi fisici.

Come illustrato nella figura 4-28 e da una prospettiva di microservizio logico/aziendale, quando si implementa un servizio Reliable con stato di Service Fabric, è in genere necessario implementare due livelli di servizi. Il primo è il servizio Reliable con stato di back-end, che gestisce più partizioni (ciascuna partizione è un servizio con stato). Il secondo è il servizio front-end, o Servizio gateway, responsabile del routing e dell'aggregazione dei dati in più partizioni o istanze del servizio con stato. Tale Servizio gateway gestisce anche la comunicazione lato client con i cicli di ripetizione che accedono al servizio back-end. Viene chiamato Servizio gateway se si implementa il servizio personalizzato. In alternativa, è possibile usare il [proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) di Service Fabric predefinito.

![](./media/image31.png)

**Figura 4-28**. Microservizio aziendale con diverse istanze del servizio con stato e un front-end di gateway personalizzato

In ogni caso, quando si usano i servizi Reliable con stato di Service Fabric, si ottiene anche un microservizio logico o aziendale (Bounded Context) che in genere è costituito da più servizi fisici. Ognuno di questi, il Servizio gateway e il servizio di partizione, può essere implementato come servizio API Web ASP.NET., come illustrato nella figura 4-28.

In Service Fabric, è possibile raggruppare e distribuire gruppi di servizi come [Applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), cioè l'unità di creazione pacchetto e distribuzione per l'agente di orchestrazione o il cluster. Di conseguenza, anche l'Applicazione di Service Fabric può essere mappata a questo limite del microservizio aziendale e logico autonomo, o Bounded Context, per poter distribuire questi servizi in modo autonomo.

## <a name="service-fabric-and-containers"></a>Service Fabric e contenitori

Per quanto riguarda i contenitori in Service Fabric, è anche possibile distribuire servizi in immagini del contenitore all'interno di un cluster di Service Fabric. Come illustrato nella figura 4-29, nella maggior parte dei casi è presente un solo contenitore per ogni servizio.

![Un'applicazione di Service Fabric può eseguire diversi contenitori con accesso a un database esterno. L'intero set costituisce il limite logico di un microservizio aziendale](./media/image32.png)

**Figura 4-29**. Microservizio aziendale con numerosi servizi (contenitori) in Service Fabric

I cosiddetti contenitori "collaterali" (due contenitori che devono essere distribuiti insieme nell'ambito di un servizio logico), tuttavia, sono possibili anche in Service Fabric. La cosa importante è che un microservizio aziendale è rappresentato dal limite logico intorno a diversi elementi coesivi. In molti casi, può trattarsi di un unico servizio con un unico modello di dati, ma in altri casi possono essere presenti anche diversi servizi fisici.

Si noti che nella stessa applicazione di Service Fabric è possibile combinare servizi di processi e servizi all'interno di contenitori, come illustrato nella figura 4-30.

![Applicazione di Service Fabric che esegue servizi e contenitori nello stesso nodo.](./media/image33.png)

**Figura 4-30**. Microservizio aziendale mappato a un'applicazione di Service Fabric con contenitori e servizi con stato

Per altre informazioni sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservizi con stato e senza stato

Come accennato in precedenza, ogni microservizio (Bounded Context logico) deve essere proprietario di un modello di dominio (dati e logica). Nel caso dei microservizi senza stato, i database sono esterni e si avvalgono di opzioni relazionali (SQL Server) o di opzioni NoSQL (Azure Cosmos DB o MongoDB).

Ma anche i servizi stessi possono essere senza stato in Service Fabric, e ciò significa che i dati risiedono all'interno del microservizio. I dati potrebbero esistere non solo nello stesso server, ma all'interno del processo del microservizio, in memoria e persistenti sulle unità disco rigido e replicate in altri nodi. La figura 4-30 mostra i diversi approcci.

![Nei servizi senza stato, lo stato (persistenza, database) viene mantenuto all'esterno del microservizio. Nei servizi con stato, gli stati vengono mantenuti all'interno del microservizio.](./media/image34.png)

**Figura 4-31**. Microservizi con stato e senza stato

Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto ai microservizi con stato, perché l'approccio è simile agli schemi tradizionali e noti. Tuttavia, i microservizi senza stato impongono la latenza tra il processo e le origini dati, oltre a comportare più elementi quando si prova a migliorare le prestazioni con cache e code aggiuntive. Il risultato è che si può finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, i [microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possono rappresentare un'ottima soluzione in scenari avanzati, perché non prevedono alcuna latenza tra la logica di dominio e i dati. L'elaborazione di grandi quantità di dati, i back-end per i giochi, i database come servizio e altri scenari a bassa latenza traggono tutti vantaggio dai servizi con stato, che abilitano lo stato locale per un accesso più rapido.

I servizi con e senza stato sono complementari. Come si può vedere nel diagramma a destra della figura 4-31, ad esempio, un servizio con stato può essere suddiviso in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisca come servizio gateway che sappia come risolvere ogni partizione in base alle chiavi di partizione.

I servizi con stato presentano comunque degli svantaggi, perché impongono un livello di complessità che permette di aumentare il numero di istanze. La funzionalità che verrebbe di solito implementata dai sistemi di database esterni deve essere indirizzata alle attività quali la replica di dati tra microservizi con stato e partizionamento dei dati. Tuttavia, si tratta di una delle aree in cui un agente di orchestrazione come [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture), con i suoi [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis), può essere di grande aiuto, in particolare semplificando i microservizi con stato con l'[API Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework del microservizio che abilitano i servizi con stato, che supportano lo schema Actor, e che migliorano la tolleranza di errore e la latenza tra logica di business e dati, sono Microsoft [Orleans](https://github.com/dotnet/orleans), di Microsoft Research, e [Akka.NET](https://getakka.net/). Entrambi i framework stanno attualmente migliorando il supporto per Docker.

Si noti che anche i contenitori Docker sono senza stato. Se si vuole implementare un servizio con stato, è necessario uno dei framework prescrittivi e di livello superiore aggiuntivi di cui si è parlato in precedenza.

## <a name="using-azure-service-fabric-mesh"></a>Uso di Azure Service Fabric Mesh 

Azure Service Fabric Mesh è un servizio completamente gestito che consente agli sviluppatori di compilare e distribuire applicazioni cruciali senza gestire alcuna infrastruttura. Usare Service Fabric Mesh per compilare ed eseguire applicazioni di microservizi distribuite sicure e scalabili su richiesta. 

Come illustrato nella figura 4-32, è possibile eseguire e ridimensionare le applicazioni ospitate in Service Fabric Mesh senza doversi preoccupare dell'infrastruttura su cui sono basate.

![È possibile distribuire in Azure Service Fabric Mesh un'app multicontenitore in esecuzione nel desktop di Docker senza doversi preoccupare dell'infrastruttura.](media/image39.png)

**Figura 4-32**. Distribuzione di un'applicazione di microservizi/contenitori in Service Fabric Mesh

Dietro le quinte, Service Fabric Mesh è costituito da cluster di migliaia di computer. Tutte le operazioni dei cluster non sono visibili per lo sviluppatore. È sufficiente caricare i contenitori e specificare le risorse necessarie, i requisiti di disponibilità e i limiti delle risorse. Service Fabric Mesh alloca automaticamente l'infrastruttura richiesta dalla distribuzione dell'applicazione, gestendo anche gli errori di infrastruttura e assicurando la disponibilità elevata delle applicazioni. È sufficiente occuparsi dell'integrità e della velocità di risposta dell'applicazione, ignorando l'infrastruttura.

Per altre informazioni, vedere la [documentazione di Service Fabric Mesh](https://docs.microsoft.com/azure/service-fabric-mesh/).

## <a name="choosing-orchestrators-in-azure"></a>Scelta degli agenti di orchestrazione in Azure

La tabella seguente offre indicazioni sull'agente di orchestrazione da usare a seconda dei carichi di lavoro e del sistema operativo.

![Il servizio Kubernetes di Azure è più maturo in Linux che in Windows e viene usato principalmente per la distribuzione di microservizi basati su contenitori. Azure Service Fabric (sia cluster che mesh) è più maturo in Windows che in Linux ed è comunemente usato per microservizi basati su contenitori, microservizi basati su processi normali e servizi con stato.](media/image40.png)

**Figura 4-33**. Selezione dell'agente di orchestrazione nel materiale sussidiario su Azure

>[!div class="step-by-step"]
>[Precedente](scalable-available-multi-container-microservice-applications.md)
>[Successivo](../docker-application-development-process/index.md)