---
title: Utilizzando Azure Service Fabric
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Utilizzando Azure Service Fabric
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa15f9cf9bc60e9e70607da921f2ce2c75e39ec2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="using-azure-service-fabric"></a>Utilizzando Azure Service Fabric

Si è verificato Azure Service Fabric dalla transizione Microsoft di recapitare i prodotti, casella che erano in genere monolitici in stile, alla fornitura di servizi. L'esperienza di creare e gestire i servizi su larga scala, ad esempio Database SQL di Azure, Azure Cosmos DB, Azure Service Bus o back-end di Cortana, la forma di Service Fabric. La piattaforma si evolve nel tempo adottato più servizi. È importante Service Fabric è stato eseguito in Azure ma anche nelle distribuzioni di Windows Server autonomo.

L'obiettivo di Service Fabric è per risolvere i problemi di disco rigidi della compilazione e l'esecuzione di un servizio e utilizzano risorse di infrastruttura in modo efficiente, in modo che i team di risolvere i problemi di business utilizzando un approccio di microservizi.

Service Fabric fornisce due aree generali che consentono di compilare applicazioni che usano un approccio di microservizi:

-   Una piattaforma che fornisce servizi di sistema da distribuire, scalabilità, aggiornare, rilevare e riavviare i servizi non riusciti, individuare la posizione del servizio, gestire lo stato e monitorare l'integrità. Questi servizi di sistema, in effetti, abilitare molte delle caratteristiche di microservizi descritto in precedenza.

-   API di programmazione o Framework, che consentono di compilare applicazioni come microservizi: [attori affidabili e servizi affidabili](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Naturalmente, è possibile scegliere qualsiasi codice per la generazione del microservizio, ma queste API rendere più semplice il processo e vengono integrate con la piattaforma a un livello più profondo. In questo modo è possibile ottenere l'integrità e le informazioni di diagnostica oppure è possibile sfruttare la gestione dello stato affidabile.

È possibile usare qualsiasi tecnologia Service Fabric è indipendente rispetto alla modalità di compilazione del servizio. Tuttavia, fornisce le API di programmazione predefinite che rendono più semplice compilare microservizi.

Come illustrato nella figura 4-26, è possibile creare ed eseguire microservizi nell'infrastruttura del servizio come processi semplici o come contenitori di Docker. È anche possibile combinare basate sul contenitore microservizi con microservizi basato su processo all'interno dello stesso cluster di Service Fabric.

![](./media/image30.png)

**Figura 4-26**. La distribuzione di microservizi come processi o come contenitori in Azure Service Fabric

Cluster di Service Fabric in base alle host Linux e Windows può eseguire contenitori Docker Linux e Windows, rispettivamente.

Per informazioni aggiornate sul supporto di contenitori in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric è un buon esempio di una piattaforma in cui è possibile definire una diversa architettura logica (business microservizi o contesti limitata) rispetto all'implementazione fisica che sono stati introdotti nel [architettura logica e fisica architettura](#logical-architecture-versus-physical-architecture) sezione. Ad esempio, se si implementa [servizi Reliable con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) in [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), che vengono introdotti nella sezione [Stateless e con stato microservizi](#stateless-versus-stateful-microservices) in un secondo momento, è possibile avere un concetto microservizio business con più servizi fisici.

Come illustrato nella figura 4-27 e da una prospettiva di logica di business/microservizio, quando si implementa un servizio con stato affidabile Service Fabric il concetto, è in genere necessario implementare due livelli di servizi. Il primo è il servizio back-end con stato affidabile, che gestisce più partizioni (ogni partizione è un servizio con stato). Il secondo è il servizio front-end, oppure il servizio Gateway, responsabile delle aggregazioni di dati e di routing in più partizioni o le istanze del servizio con stato. Servizio Gateway gestisce inoltre la comunicazione client-side con i cicli di ripetizione l'accesso al servizio back-end.
Viene chiamato un servizio Gateway se si implementa il servizio personalizzata o alternatevely è inoltre possibile utilizzare l'infrastruttura del servizio di casella [servizio Proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image31.png)

**Figura 4-27**. Business microservizio con più istanze di servizio con stato e un gateway personalizzato front-end

In ogni caso, quando si utilizza servizi Reliable con stato dell'infrastruttura di servizio, è anche una logica o aziendale microservizio (contesto delimitata) che in genere sono costituito da più servizi fisici. Ognuno di essi, il servizio Gateway e il servizio di partizione potrebbe essere implementato come servizi API Web ASP.NET, come illustrato nella figura 4-26.

Nell'infrastruttura del servizio, è possibile raggruppare e gruppi di servizi come distribuire un [applicazione di Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), che è l'unità di assemblaggio e distribuzione per l'agente di orchestrazione o il cluster. Pertanto, l'applicazione di Service Fabric potrebbe essere mappato a questo aziendali autonome e limite logico microservizio o contesto delimitata, nonché, pertanto è possibile distribuire questi servizi in modo autonomo.

## <a name="service-fabric-and-containers"></a>Contenitori e Service Fabric

Per quanto riguarda i contenitori nell'infrastruttura del servizio, è inoltre possibile distribuire servizi di immagini contenitore all'interno di un cluster di Service Fabric. Come mostrato nella figura 4-28, la maggior parte dei casi verranno essere presente solo un contenitore per ogni servizio.

![](./media/image32.png)

**Figura 4-28**. Business microservizio con diversi servizi (contenitori) di Service Fabric

Tuttavia, sono inoltre disponibili in Service Fabric contenitori cosiddetti "car" (due contenitori che devono essere distribuiti insieme come parte di un servizio logico). La cosa importante è che un microservizio business rappresentato dal limite logico attorno agli elementi coesivi diversi. In molti casi, potrebbe essere un singolo servizio con un singolo modello di dati, ma in altri casi potrebbe essere anche i servizi fisici diversi.

A partire da mid 2017, nell'infrastruttura del servizio non è possibile distribuire servizi con stato affidabili SF sui contenitori, è possibile distribuire solo i servizi senza stati e i servizi actor di contenitori. Ma si noti che è possibile combinare i servizi nei processi e servizi nei contenitori nella stessa applicazione di Service Fabric, come illustrato nella figura 4-29.

![](./media/image33.png)

**Figura 4-29**. Business microservizio mappato a un'applicazione di Service Fabric con contenitori e i servizi con stati

Per ulteriori informazioni sul supporto di contenitore in Azure Service Fabric, vedere [Service Fabric e contenitori](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Senza stato e informazioni sullo stato microservizi

Come accennato in precedenza, ogni microservizio (logico delimitata contesto) deve essere proprietaria relativo modello di dominio (dati e logica). Nel caso di microservizi senza stato, i database verranno esterni, avvalendosi di opzioni relazionale come SQL Server o le opzioni di database NoSQL come MongoDB o Azure Cosmos DB.

Ma i servizi stessi possono essere anche informazioni sullo stato nell'infrastruttura del servizio, il che significa che i dati si trovano all'interno di microservizio. I dati potrebbero esistere non solo nello stesso server, ma all'interno del processo microservizio, in memoria e persistenti sulle unità disco rigido e replicate in altri nodi. Figura 4-30 Mostra i diversi approcci.

![](./media/image34.png)

**Figura 4-30**. Senza stato e informazioni sullo stato microservizi

Un approccio senza stato è perfettamente valido ed è più facile da implementare rispetto microservizi con stato, poiché l'approccio è simile ai modelli tradizionali e noti. Ma senza stati microservizi impongano la latenza tra il processo e le origini dati. Più lo spostamento di parti e comportano anche quando si sta tentando di migliorare le prestazioni con cache aggiuntiva e code. Il risultato è che possono finire con architetture complesse che hanno un numero eccessivo di livelli.

Al contrario, [microservizi con stato](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) possibile di excel in scenari avanzati, perché non è prevista una latenza tra la logica di dominio e i dati. Elaborazione dati, giochi nuovamente termina, un servizio, i database e altri scenari di bassa latenza tutti usufruire dei servizi con stati, che consentono un accesso più rapido dello stato locale.

Servizi senza stato sono complementari. Ad esempio, è possibile visualizzare in figura 4-30, nel diagramma di destra, che un servizio con stato può essere suddivisi in più partizioni. Per accedere a tali partizioni, potrebbe essere necessario un servizio senza stato che agisce come un servizio gateway in grado di risolvere ogni partizione in base alle chiavi di partizione.

Stato servizi presentano svantaggi. Che impongono un livello di complessità che consente a scalabilità orizzontale. Funzionalità che verrebbe in genere essere implementata dai sistemi di database esterni devono essere inviate per attività quali la replica dei dati in informazioni sullo stato microservizi e partizionamento dei dati. Tuttavia, si tratta di una delle aree in cui un agente di orchestrazione come [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con relativo [servizi affidabili con stati](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) consente la maggior parte, per semplificare lo sviluppo e il ciclo di vita di informazioni sullo stato microservizi utilizzando il [API dei servizi affidabili](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) e [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Altri framework microservizio che consentano ai servizi con stati, che supportano il modello attore e che ne migliorano la tolleranza di errore e la latenza tra la logica di business e dati sono Microsoft [Orleans](https://github.com/dotnet/orleans), da Microsoft Research e [ Akka.NET](http://getakka.net/). Entrambe le versioni attualmente siano migliorando il supporto per Docker.

Si noti che i contenitori di Docker sono senza stato. Se si desidera implementare un servizio con stato, è necessario uno dei framework precise e di livello superiore aggiuntive indicato in precedenza. 

>[!div class="step-by-step"]
[Precedente] (scalable-available-multi-container-microservice-applications.md) [Avanti] (... /docker-Application-Development-Process/index.MD)
