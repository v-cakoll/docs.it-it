---
title: Infrastruttura di comunicazione con mesh di servizi
description: Informazioni su come le tecnologie di servizi Mesh semplificano la comunicazione di microservizi nativa del cloud
author: robvet
ms.date: 09/10/2019
ms.openlocfilehash: 66bc69580cc56efe725683c16a047aeb07e7e840
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76780924"
---
# <a name="service-mesh-communication-infrastructure"></a>Infrastruttura di comunicazione con mesh di servizi

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

In questo capitolo sono state esaminate le esigenze della comunicazione di microservizi. Abbiamo detto che i team di sviluppo devono essere sensibili al modo in cui i servizi back-end comunicano tra loro. Idealmente, migliore è la comunicazione tra i servizi. Tuttavia, l'elusione non è sempre possibile perché i servizi back-end si basano spesso su un altro per completare le operazioni.

Sono stati esaminati diversi approcci per l'implementazione della comunicazione HTTP sincrona e della messaggistica asincrona. In ognuno dei casi, lo sviluppatore è sovraccarico nell'implementazione del codice di comunicazione. Il codice di comunicazione è complesso e a elevato utilizzo di tempo. Decisioni non corrette possono causare gravi problemi di prestazioni.

Un approccio più moderno ai centri di comunicazione del microservizio intorno a una tecnologia nuova e in rapida evoluzione intitolata *Service mesh*. Una [rete mesh di servizi](https://www.nginx.com/blog/what-is-a-service-mesh/) è un livello di infrastruttura configurabile con funzionalità predefinite per gestire la comunicazione da servizio a servizio, la resilienza e molte problematiche trasversali. Viene spostata la responsabilità di questi problemi tra i microservizi e il livello mesh del servizio. La comunicazione viene sottratta dai microservizi.

Un componente chiave di una rete mesh di servizi è un proxy. In un'applicazione nativa del cloud, un'istanza di un proxy si trova in genere in un percorso condiviso con ogni microservizio. Mentre vengono eseguiti in processi distinti, i due elementi sono strettamente collegati e condividono lo stesso ciclo di vita. Questo modello, noto come [modello sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar), è illustrato nella figura 4-23.

![Rete di servizi con un'auto laterale](./media/service-mesh-with-side-car.png)

**Figura 4-23**. Rete di servizi con un'auto laterale

Si noti che nella figura precedente il modo in cui i messaggi vengono intercettati da un proxy eseguito insieme a ogni microservizio. Ogni proxy può essere configurato con regole di traffico specifiche del microservizio. Riconosce i messaggi ed è in grado di instradarli tra i servizi e il mondo esterno.

Oltre alla gestione della comunicazione da servizio a servizio, la rete mesh del servizio fornisce supporto per l'individuazione dei servizi e il bilanciamento del carico.

Una volta configurata, una mesh del servizio è altamente funzionante. Il mesh recupera un pool di istanze corrispondente da un endpoint di individuazione del servizio. Invia una richiesta a un'istanza del servizio specifica, registrando la latenza e il tipo di risposta del risultato. Consente di scegliere l'istanza con maggiore probabilità di restituire una risposta rapida in base a fattori diversi, inclusa la latenza osservata per le richieste recenti.

Una rete mesh di servizi gestisce problemi di traffico, comunicazione e rete a livello di applicazione. Riconosce messaggi e richieste. Una mesh di servizi si integra in genere con un agente di orchestrazione del contenitore. Kubernetes supporta un'architettura estendibile in cui è possibile aggiungere una mesh di servizi.

Nel capitolo 6 vengono approfondite le tecnologie di rete di servizi, inclusa una discussione sulla sua architettura e sulle implementazioni open source disponibili.

## <a name="summary"></a>Riepilogo

In questo capitolo sono stati illustrati i modelli di comunicazione nativi del cloud. Abbiamo iniziato esaminando il modo in cui i client front-end comunicano con microservizi back-end. Abbiamo parlato delle piattaforme del gateway API e della comunicazione in tempo reale. È stato quindi esaminato il modo in cui i microservizi comunicano con altri servizi back-end. Sono state esaminate sia la comunicazione HTTP sincrona che la messaggistica asincrona tra i servizi. Abbiamo trattato gRPC, una tecnologia imminente nel mondo nativo del cloud. È stata infine introdotta una tecnologia nuova e in rapida evoluzione denominata mesh di servizi in grado di semplificare la comunicazione di microservizi.

Particolare enfasi sui servizi di Azure gestiti che consentono di implementare la comunicazione nei sistemi nativi del cloud:

- [Gateway applicazione Azure](https://docs.microsoft.com/azure/application-gateway/overview)
- [Gestione API di Azure](https://azure.microsoft.com/services/api-management/)
- [Servizio Azure SignalR](https://azure.microsoft.com/services/signalr-service/)
- [Code di archiviazione di Azure](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [Bus di servizio di Azure](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Griglia di eventi di Azure](https://docs.microsoft.com/azure/event-grid/overview)
- [Hub eventi di Azure](https://azure.microsoft.com/services/event-hubs/)

Si passa quindi ai dati distribuiti nei sistemi nativi del cloud e ai vantaggi e alle esigenze che presenta.

### <a name="references"></a>Riferimenti

- [Microservizi .NET: architettura per le applicazioni .NET in contenitori](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Progettazione della comunicazione tra servizi per i microservizi](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [Servizio Azure SignalR, un servizio completamente gestito per l'aggiunta di funzionalità in tempo reale](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Controller di ingresso del gateway API di Azure](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [Informazioni sul traffico in ingresso in Azure Kubernetes Service (AKS)](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [GRPC pratici](https://www.worldcat.org/title/practical-grpc/oclc/1042342319)

- [Documentazione di gRPC](https://grpc.io/docs/guides/)

- [gRPC per sviluppatori WCF](https://bing.com) [libro gRPC di Mark]

- [Confronto tra i servizi gRPC e le API HTTP](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

>[!div class="step-by-step"]
>[Precedente](rest-grpc.md)
>[Successivo](Database-per-microservice.md)
