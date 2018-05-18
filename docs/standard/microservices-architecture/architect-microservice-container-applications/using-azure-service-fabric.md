---
title: Uso di Azure Service Fabric
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Uso di Azure Service Fabric
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: d65968e3d37f53cceee55120110ad4bb3c13d304
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="using-azure-service-fabric"></a>Uso di Azure Service Fabric

Azure Service Fabric è nato dal passaggio di Microsoft dall'offerta di prodotti completi, di stile decisamente monolitico, all'offerta di servizi. L'esperienza di creazione e gestione di grandi servizi su larga scala, come il database SQL di Microsoft Azure, Azure Cosmos DB, il bus di servizio di Microsoft Azure o Backend di Cortana, ha dato forma a Service Fabric. La piattaforma si è evoluta nel tempo con la sua continua adozione da parte di un numero crescente di servizi. Cosa ancora più importante, Service Fabric doveva essere eseguito non solo in Azure, ma anche nelle distribuzioni autonome di Windows Server.

L'obiettivo di Service Fabric è risolvere i complicati problemi di creare ed eseguire un servizio e utilizzare le risorse di infrastruttura in maniera efficiente, in modo che i team possano risolvere i problemi aziendali usando un approccio ai microservizi.

Service Fabric fornisce due aree generali che consentono di creare applicazioni che usano un approccio ai microservizi:

-   Una piattaforma che fornisce servizi di sistema per distribuire, ridimensionare, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema, in effetti, abilitano molte delle caratteristiche dei microservizi descritte in precedenza.

-   API di programmazione, o framework, che aiutano a creare applicazioni come microservizi: [Reliable Actors e Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Naturalmente, è possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API semplificano il processo e si integrano nella piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

Service Fabric è agnostico rispetto al modo in cui si crea il servizio ed è possibile usare qualsiasi tecnologia. Tuttavia, fornisce API di programmazione predefinite che rendono più semplice creare i microservizi.

Come illustrato nella figura 4-26, è possibile creare ed eseguire microservizi in Service Fabric come processi semplici o come contenitori Docker. È anche possibile combinare microservizi basati su contenitori con microservizi basati su processi all'interno dello stesso cluster di Service Fabric.

![](./media/image30.png)

**Figura 4-26**. Distribuzione di microservizi come processi o contenitori in Azure Service Fabric

I cluster di Service Fabric basati su host Linux e Windows possono eseguire rispettivamente contenitori Linux Docker e Windows.

Per informazioni aggiornate sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di piattaforma in cui è possibile definire una diversa architettura logica (microservizi aziendali o contesti delimitati) rispetto all'implementazione fisica che è stata introdotta nella sezione [Architettura logica e architettura fisica](#logical-architecture-versus-physical-architecture). Ad esempio, se in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) si implementano [Servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction), che verranno introdotti nella sezione [Microservizi senza stato e con stato](#stateless-versus-stateful-microservices) più avanti, si può sviluppare un concetto di microservizio aziendale con più servizi fisici.

Come illustrato nella figura 4-27 e da una prospettiva di microservizio logico/aziendale, quando si implementa un servizio Reliable con stato di Service Fabric in genere è necessario implementare due livelli di servizi. Il primo è il servizio Reliable con stato di back-end, che gestisce più partizioni (ciascuna partizione è un servizio con stato). Il secondo è il servizio front-end, o Servizio gateway, responsabile del routing e dell'aggregazione dei dati in più partizioni o istanze del servizio con stato. Tale Servizio gateway gestisce anche la comunicazione del lato client con i cicli di ripetizione che accedono al servizio back-end.
Viene chiamato Servizio gateway se si implementa il servizio personalizzato; in alternativa, è possibile usare il servizio predefinito [Proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) di Service Fabric.

![](./media/image31.png)

**Figura 4-27**. Microservizio aziendale con diverse istanze del servizio con stato e un front-end di gateway personalizzato

In ogni caso, quando si usano i servizi Reliable con stato di Service Fabric, si ottiene anche un microservizio logico o aziendale (Bounded Context) che in genere è costituito da più servizi fisici. Ciascuno di essi, il Servizio gateway e il servizio Partizione, potrebbe essere implementato come servizio API Web ASP.NET. come mostrato nella figura 4-26.

In Service Fabric, è possibile raggruppare e distribuire gruppi di servizi come [Applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), cioè l'unità di creazione pacchetto e distribuzione per l'agente di orchestrazione o il cluster. Di conseguenza, anche l'Applicazione di Service Fabric può essere mappata a questo limite del microservizio aziendale e logico autonomo, o Bounded Context, per poter distribuire questi servizi in modo autonomo.

## <a name="service-fabric-and-containers"></a>Service Fabric e contenitori

Per quanto riguarda i contenitori in Service Fabric, è anche possibile distribuire servizi in immagini del contenitore all'interno di un cluster di Service Fabric. Come mostrato nella figura 4-28, nella maggior parte dei casi sarà presente un solo contenitore per ogni servizio.

![](./media/image32.png)

**Figura 4-28**. Microservizio aziendale con numerosi servizi (contenitori) in Service Fabric

Tuttavia, i cosiddetti contenitori "collaterali" (due contenitori che devono essere distribuiti insieme come parte di un servizio logico) sono possibili anche in Service Fabric. La cosa importante è che un microservizio aziendale è rappresentato dal limite logico intorno a diversi elementi coesivi. In molti casi, potrebbe essere un singolo servizio con un singolo modello di dati, ma in altri casi potrebbero esserci anche diversi servizi fisici.

A partire dalla metà del 2017, in Service Fabric non è possibile distribuire Servizi Reliable con stato di Service Fabric sui contenitori: si possono distribuire solo servizi senza stato e servizi Actor nei contenitori. Si noti però che è possibile combinare servizi in processi e servizi in contenitori nella stessa applicazione di Service Fabric, come illustrato nella figura 4-29.

![](./media/image33.png)

**Figura 4-29**. Microservizio aziendale mappato a un'applicazione di Service Fabric con contenitori e servizi con stato

Per altre informazioni sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservizi con stato e senza stato

Come accennato in precedenza, ogni microservizio (Bounded Context logico) deve essere proprietario di un modello di dominio (dati e logica). Nel caso dei microservizi senza stato, i database saranno esterni, avvalendosi di opzioni relazionali come SQL Server o le opzioni NoSQL come MongoDB o Azure Cosmos DB.

Ma anche i servizi stessi possono essere senza stato in Service Fabric, e ciò significa che i dati risiedono all'interno del microservizio. I dati potrebbero esistere non solo nello stesso server, ma all'interno del processo del microservizio, in memoria e persistenti sulle unità disco rigido e replicate in altri nodi. La figura 4-30 mostra i diversi approcci.

![](./media/image34.png)

**Figura 4-30**. Microservizi con stato e senza stato

Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto ai microservizi con stato, perché l'approccio è simile agli schemi tradizionali e noti. Tuttavia, i microservizi senza stato impongono la latenza tra il processo e le origini dati, oltre a comportare più elementi quando si prova a migliorare le prestazioni con cache e code aggiuntive. Il risultato è che si può finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, i [microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possono eccellere in scenari avanzati, perché non è prevista alcuna latenza tra la logica di dominio e i dati. L'elaborazione di grandi quantità di dati, i back-end per i giochi, i database come servizio e altri scenari a bassa latenza traggono tutti vantaggio dai servizi con stato, che abilitano lo stato locale per un accesso più rapido.

I servizi con e senza stato sono complementari. Ad esempio, come si può vedere nella figura 4-30, nel diagramma a destra, un servizio con stato può essere suddiviso in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisca come servizio gateway che sappia come risolvere ogni partizione in base alle chiavi di partizione.

I servizi con stato presentano comunque degli svantaggi, perché impongono un livello di complessità che permette di aumentare il numero di istanze. La funzionalità che verrebbe di solito implementata dai sistemi di database esterni deve essere indirizzata alle attività quali la replica di dati tra microservizi con stato e partizionamento dei dati. Tuttavia, si tratta di una delle aree in cui un agente di orchestrazione come [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture), con i suoi [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis), può essere di grande aiuto, in particolare semplificando i microservizi con stato con l'[API Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework del microservizio che abilitano i servizi con stato, che supportano lo schema Actor, e che migliorano la tolleranza di errore e la latenza tra logica di business e dati, sono Microsoft [Orleans](https://github.com/dotnet/orleans), di Microsoft Research, e [Akka.NET](https://getakka.net/). Entrambi i framework stanno attualmente migliorando il supporto per Docker.

Si noti che anche i contenitori Docker sono senza stato. Se si vuole implementare un servizio con stato, è necessario uno dei framework prescrittivi e di livello superiore aggiuntivi di cui si è parlato in precedenza. 

>[!div class="step-by-step"]
[Indietro] (scalable-available-multi-container-microservice-applications.md) [Avanti] (../docker-application-development-process/index.md)
