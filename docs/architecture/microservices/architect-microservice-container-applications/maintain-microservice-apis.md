---
title: Creazione, evoluzione e controllo delle versioni di API e contratti dei microservizi
description: Creare API e contratti dei microservizi tenendo in considerazione l'evoluzione e il controllo delle versioni poiché le esigenze cambiano.
ms.date: 09/20/2018
ms.openlocfilehash: 1972d02d8bf7935c71bfd383707ae19ea2baded9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672898"
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Creazione, evoluzione e controllo delle versioni di API e contratti dei microservizi

Un'API di microservizio è un contratto tra il servizio e i relativi client. Sarà possibile sviluppare un microservizio in modo indipendente solo se non si infrange il contratto API, ecco perché il contratto riveste un'importanza particolare. Se si modifica il contratto, ci saranno ripercussioni sulle applicazioni client o sul gateway API.

La natura della definizione dell'API dipende dal protocollo in uso. Ad esempio, se si usa la messaggistica (come [AMQP](https://www.amqp.org/)), l'API è costituita dai tipi di messaggio. Se si usano i servizi HTTP e RESTful, l'API è costituita dagli URL e dai formati JSON delle richieste e delle risposte.

Tuttavia, anche se si effettua una scelta ponderata del contratto iniziale, un'API del servizio dovrà necessariamente evolversi nel tempo. Quando ciò accade, in particolare se si tratta di un'API pubblica usata da più applicazioni client, in genere non è possibile imporre a tutti i client di eseguire l'aggiornamento al nuovo contratto API. Di norma, occorre procedere a una distribuzione incrementale delle nuove versioni di un servizio, in modo che vengano eseguite contemporaneamente sia le nuove versioni di un contratto di servizio che quelle precedenti. Quindi, è importante disporre di una strategia per il controllo delle versioni del servizio.

Quando le modifiche dell'API sono di lieve entità, ad esempio in caso di aggiunta di attributi o di parametri all'API, i client che usano un'API precedente dovrebbero eseguire l'aggiornamento e usare la nuova versione del servizio. Potrebbe essere possibile fornire valori predefiniti per tutti gli attributi mancanti richiesti e i client potrebbero ignorare eventuali attributi di risposta aggiuntivi.

Tuttavia, talvolta è necessario apportare modifiche sostanziali e incompatibili a un'API del servizio. Dal momento che potrebbe non essere possibile imporre ai servizi o alle applicazioni client di eseguire immediatamente l'aggiornamento alla nuova versione, un servizio deve essere in grado di supportare le versioni precedenti dell'API per un determinato periodo. Se si usa un meccanismo basato su HTTP, ad esempio REST, un approccio possibile è incorporare il numero di versione dell'API nell'URL o in un'intestazione HTTP. È quindi possibile scegliere se implementare entrambe le versioni del servizio contemporaneamente nella stessa istanza del servizio o distribuire istanze diverse che gestiscono le differenti versioni dell'API. Un approccio valido potrebbe essere lo [schema Mediator](https://en.wikipedia.org/wiki/Mediator_pattern) (ad esempio, la [libreria MediatR](https://github.com/jbogard/MediatR)), che consente di separare le diverse versioni dell'implementazione in gestori indipendenti.

Infine, se si usa un'architettura REST, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) è la soluzione migliore per garantire il controllo delle versioni dei servizi e consentire l'uso di API in grado di evolversi.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Scott Hanselman. ASP.NET il controllo delle versioni delle API Web RESTful di base semplificato** \
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- **Controllo delle versioni di un'API Web RESTfulVersioning a RESTful web API** \
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- **Roy Fielding. Controllo delle versioni, Hypermedia e RESTVersioning, Hypermedia, and REST** \
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

>[!div class="step-by-step"]
>[Successivo](asynchronous-message-based-communication.md)
>[precedente](microservices-addressability-service-registry.md)
