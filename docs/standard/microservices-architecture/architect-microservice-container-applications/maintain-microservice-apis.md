---
title: Creazione, evoluzione e controllo delle versioni di API e contratti dei microservizi
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | Creazione, evoluzione e controllo delle versioni di API e contratti dei microservizi
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: a2ec577a12cf677c2ec5e20a6f3e862911c82fbb
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105693"
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Creazione, evoluzione e controllo delle versioni di API e contratti dei microservizi

Un'API di microservizio è un contratto tra il servizio e i relativi client. Sarà possibile sviluppare un microservizio in modo indipendente solo se non si infrange il contratto API, ecco perché il contratto riveste un'importanza particolare. Se si modifica il contratto, ci saranno ripercussioni sulle applicazioni client o sul gateway API.

La natura della definizione dell'API dipende dal protocollo in uso. Ad esempio, se si usa la messaggistica (come [AMQP](https://www.amqp.org/)), l'API è costituita dai tipi di messaggio. Se si usano i servizi HTTP e RESTful, l'API è costituita dagli URL e dai formati JSON delle richieste e delle risposte.

Tuttavia, anche se si effettua una scelta ponderata del contratto iniziale, un'API del servizio dovrà necessariamente evolversi nel tempo. Quando ciò accade, in particolare se si tratta di un'API pubblica utilizzata da più applicazioni client, in genere non è possibile imporre a tutti i client di eseguire l'aggiornamento al nuovo contratto API. Di norma, occorre procedere a una distribuzione incrementale delle nuove versioni di un servizio, in modo che vengano eseguite contemporaneamente sia le nuove versioni di un contratto di servizio che quelle precedenti. Pertanto, è importante disporre di una strategia per il controllo delle versioni del servizio.

Quando le modifiche dell'API sono di lieve entità, ad esempio in caso di aggiunta di attributi o di parametri all'API, i client che usano un'API precedente dovrebbero eseguire l'aggiornamento e usare la nuova versione del servizio. Potrebbe essere possibile fornire valori predefiniti per tutti gli attributi mancanti richiesti e i client potrebbero ignorare eventuali attributi di risposta aggiuntivi.

Tuttavia, talvolta è necessario apportare modifiche sostanziali e incompatibili a un'API del servizio. Dal momento che potrebbe non essere possibile imporre ai servizi o alle applicazioni client di eseguire immediatamente l'aggiornamento alla nuova versione, un servizio deve essere in grado di supportare le versioni precedenti dell'API per un determinato periodo. Se si usa un meccanismo basato su HTTP come REST, un possibile approccio consiste nell'incorporare il numero di versione dell'API nell'URL o in un'intestazione HTTP. È quindi possibile scegliere se implementare entrambe le versioni del servizio contemporaneamente nella stessa istanza del servizio o distribuire istanze diverse che gestiscono le differenti versioni dell'API. Un approccio valido potrebbe essere lo [schema Mediator](https://en.wikipedia.org/wiki/Mediator_pattern) (ad esempio, la [libreria MediatR](https://github.com/jbogard/MediatR)), che consente di separare le diverse versioni dell'implementazione in gestori indipendenti.

Infine, se si usa un'architettura REST, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) è la soluzione migliore per garantire il controllo delle versioni dei servizi e consentire l'uso di API in grado di evolversi.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy**
    <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx> (Controllo facilitato delle versioni delle API Web ASP.NET Core RESTful)

-   **Versioning a RESTful web API**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api) (Controllo delle versioni delle API Web)

-   **Roy Fielding. Versioning, Hypermedia, and REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning> (Controllo delle versioni, ipermedia e REST)


>[!div class="step-by-step"]
[Precedente](asynchronous-message-based-communication.md)
[Successivo](microservices-addressability-service-registry.md)
