---
title: Microservizio creazione in evoluzione e controllo delle versioni delle API e i contratti
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Microservizio creazione in evoluzione e controllo delle versioni delle API e i contratti
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 433711c3479eafd52bf9f5d53faf8e5707c6c624
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Microservizio creazione in evoluzione e controllo delle versioni delle API e i contratti

Un microservizio API è un contratto tra il servizio e i relativi client. Sarà in grado di evolvere in modo indipendente un microservizio solo se non si interrompe il contratto API, motivo per cui il contratto è così importante. Se si modifica il contratto, avrà impatto sulle applicazioni client o il API Gateway.

La natura della definizione dell'API dipende dal quale protocollo in uso. Ad esempio, se si utilizza la messaggistica (ad esempio [AMQP](https://www.amqp.org/)), l'API è costituita da tipi di messaggio. Se si utilizza HTTP e servizi, l'API è costituita dagli URL e i formati di richiesta e risposta JSON.

Tuttavia, anche se si sta con attenzione il contratto iniziale, un'API del servizio sarà necessario cambiare nel tempo. Quando ciò si verifica, e in particolare se l'API è un'API pubblica utilizzata da più applicazioni client, è in genere non è possibile imporre a tutti i client per eseguire l'aggiornamento per il nuovo contratto API. In genere, è necessario distribuire in modo incrementale le nuove versioni di un servizio in modo che sia vecchi che nuove versioni di un contratto di servizio sono in esecuzione contemporaneamente. Pertanto, è importante disporre di una strategia per il controllo delle versioni del servizio.

Quando le modifiche delle API sono troppo piccole, ad esempio se aggiungere gli attributi o i parametri all'API, i client che usano un'API precedente devono passare e di lavoro con la nuova versione del servizio. Potrebbe essere in grado di fornire i valori predefiniti per tutti gli attributi mancanti necessari e il client potrebbe essere in grado di ignorare eventuali attributi aggiuntivi di risposta.

Tuttavia, talvolta è necessario apportare modifiche principali e incompatibili a un'API del servizio. Poiché potrebbe non essere in grado di imporre applicazioni o servizi client per eseguire immediatamente l'aggiornamento alla nuova versione, un servizio deve supportare le versioni precedenti dell'API per un determinato periodo. Se si utilizza un meccanismo basato su HTTP, ad esempio REST, un approccio consiste nell'incorporare il numero di versione dell'API nell'URL o in un'intestazione HTTP. È possibile quindi decidere tra implementa entrambe le versioni del servizio contemporaneamente nella stessa istanza del servizio o istanze diverse che ognuno di gestire una versione dell'API di distribuzione. Un approccio valido per questo è il [modello mediatore](https://en.wikipedia.org/wiki/Mediator_pattern) (ad esempio, [MediatR libreria](https://github.com/jbogard/MediatR)) per separare le versioni diverse di implementazione nei gestori indipendenti.

Infine, se si utilizza un'architettura REST, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) è la soluzione migliore per il controllo delle versioni dei servizi e consentendo evolversi API.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Scott Hanselman. Controllo delle versioni API Web RESTful Core ASP.NET semplificato**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

-   **Controllo delle versioni di un'API web RESTful**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Controllo delle versioni e Hypermedia REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning>


>[!div class="step-by-step"]
[Precedente] (asincrono-messaggio-base-communication.md) [Avanti] (microservizi indirizzabilità-servizio registry.md)
