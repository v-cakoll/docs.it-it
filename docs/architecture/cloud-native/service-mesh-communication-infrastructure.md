---
title: Infrastruttura di comunicazione con mesh di servizi
description: Scopri come le tecnologie di service mesh semplificano la comunicazione dei microservizi nativi nel cloud
author: robvet
ms.date: 03/03/2020
ms.openlocfilehash: 6b177ef33b804ec35f3acb919539a97683e5a487
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523513"
---
# <a name="service-mesh-communication-infrastructure"></a>Infrastruttura di comunicazione con mesh di servizi

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In questo capitolo, abbiamo esplorato le sfide della comunicazione dei microservizi. Abbiamo detto che i team di sviluppo devono essere sensibili al modo in cui i servizi back-end comunicano tra loro. Idealmente, meno comunicazione tra servizi, meglio è. Tuttavia, l'evitamento non è sempre possibile, poiché i servizi back-end spesso si basano l'uno sull'altro per completare le operazioni.

Sono stati esplorati diversi approcci per l'implementazione della comunicazione HTTP sincrona e della messaggistica asincrona. In ognuno dei casi, lo sviluppatore è gravato con l'implementazione del codice di comunicazione. Il codice di comunicazione è complesso e richiede molto tempo. Decisioni errate possono portare a problemi di prestazioni significativi.

Un approccio più moderno alla comunicazione microservizio si concentra su una nuova tecnologia in rapida evoluzione, denominata *Service Mesh*. Una [rete mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) di servizio è un livello di infrastruttura configurabile con funzionalità integrate per gestire la comunicazione da servizio a servizio, resilienza e molti problemi trasversali. Sposta la responsabilità di queste preoccupazioni fuori dai microservizi e nel layer mesh di servizio. La comunicazione è astratta dai microservizi.

Un componente chiave di una rete mesh del servizio è un proxy. In un'applicazione cloud-native, un'istanza di un proxy è in genere collocata con ogni microservizio. Mentre vengono eseguiti in processi separati, i due sono strettamente collegati e condividono lo stesso ciclo di vita. Questo modello, noto come il [modello Sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar), ed è illustrato nella Figura 4-24.

![Rete di servizio con un'auto laterale](./media/service-mesh-with-side-car.png)

**Figura 4-24**. Rete di servizio con un'auto laterale

Si noti nella figura precedente come i messaggi vengono intercettati da un proxy che viene eseguito insieme a ogni microservizio. Ogni proxy può essere configurato con regole di traffico specifiche per il microservizio. Comprende i messaggi e può instradarli attraverso i vostri servizi e il mondo esterno.

Oltre a gestire la comunicazione da servizio a servizio, Service Mesh fornisce supporto per l'individuazione dei servizi e il bilanciamento del carico.

Una volta configurato, una rete mesh di servizio è altamente funzionale. La rete recupera un pool corrispondente di istanze da un endpoint di individuazione del servizio. Invia una richiesta a un'istanza del servizio specifica, registrando la latenza e il tipo di risposta del risultato. Sceglie l'istanza più probabile per restituire una risposta rapida in base a diversi fattori, tra cui la latenza osservata per le richieste recenti.

Una rete mesh di servizi gestisce i problemi di traffico, comunicazione e rete a livello di applicazione. Comprende i messaggi e le richieste. Una rete mesh del servizio in genere si integra con un agente di orchestrazione contenitore. Kubernetes supporta un'architettura estensibile in cui è possibile aggiungere una rete di servizi.

Nel capitolo 6, ci immeriamo in modo approfondito nelle tecnologie Service Mesh, tra cui una discussione sulla sua architettura e sulle implementazioni open source disponibili.

## <a name="summary"></a>Riepilogo

In questo capitolo sono stati illustrati i modelli di comunicazione nativi al cloud. È stato illustrato in che modo i client front-end comunicano con i microservizi back-end. Lungo la strada, abbiamo parlato di piattaforme API Gateway e comunicazione in tempo reale. Abbiamo quindi esaminato il modo in cui i microservizi comunicano con altri servizi back-end. Sono state esaminate sia la comunicazione HTTP sincrona che la messaggistica asincrona tra i servizi. Abbiamo coperto gRPC, una tecnologia imminente nel mondo cloud-native. Infine, abbiamo introdotto una nuova tecnologia in rapida evoluzione denominata Service Mesh che può semplificare la comunicazione dei microservizi.

Particolare enfasi è stata posta enfasi sui servizi di Azure gestiti che consentono di implementare la comunicazione nei sistemi nativi del cloud:Special emphasis was on managed Azure services that can help implement communication in cloud-native systems:

- [Gateway applicazione di AzureAzure Application Gateway](https://docs.microsoft.com/azure/application-gateway/overview)
- [Gestione API di Azure](https://azure.microsoft.com/services/api-management/)
- [Servizio Azure SignalR](https://azure.microsoft.com/services/signalr-service/)
- [Code di Archiviazione di Azure](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [Bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Griglia di eventi di AzureAzure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Hub eventi di AzureAzure Event Hub](https://azure.microsoft.com/services/event-hubs/)

Passiamo ora ai dati distribuiti nei sistemi nativi del cloud e ai vantaggi e alle sfide che presenta.

### <a name="references"></a>Riferimenti

- [Microservizi .NET: architettura per le applicazioni .NET containerizzate](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Progettazione della comunicazione tra servizi per i microserviziDesigning Interservice Communication for Microservices](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [Servizio SignalR di Azure, un servizio completamente gestito per aggiungere funzionalità in tempo realeAzure SignalR Service, a fully managed service to add real-time service](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Controller di ingresso del gateway API di AzureAzure API Gateway Ingress Controller](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [Informazioni sull'ingresso nel servizio Azure Kubernetes (AKS)About Ingress in Azure Kubernetes Service (AKS)](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [Documentazione gRPC](https://grpc.io/docs/guides/)

- [gRPC per sviluppatori WCF](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)

- [Confronto tra i servizi gRPC e le API HTTP](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [Creazione di servizi gRPC con video .NET](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
>[Successivo](grpc.md)
>[precedente](Database-per-microservice.md)
