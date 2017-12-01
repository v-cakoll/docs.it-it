---
title: "Sovranità di dati per ogni microservizio"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Sovranità di dati per ogni microservizio"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c51daae04215cfa6f5b5b8d2158a8ed1a8949652
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="data-sovereignty-per-microservice"></a>Sovranità di dati per ogni microservizio

Una regola per l'architettura di microservizi importante è che ogni microservizio deve essere proprietaria dominio dati e logica. Come proprietario di un'applicazione completa la logica e i dati, pertanto deve ogni microservizio possedere la logica e i dati in un ciclo di vita autonomo, con la distribuzione indipendente per ogni microservizio.

Ciò significa che il modello concettuale del dominio variano tra i sottosistemi o microservizi. Prendere in considerazione le applicazioni aziendali, customer relationship management (CRM) applicazioni, transazionale acquistano sottosistemi e i sottosistemi di supporto clienti ogni chiamata di dati e gli attributi di entità cliente univoco e ognuno utilizza un altro Contesto associato (BC).

Questo principio è simile in [progettazione basati su dominio (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design), dove ogni [contesto delimitata](https://martinfowler.com/bliki/BoundedContext.html) o sottosistema autonomo o un servizio deve essere proprietaria relativo modello di dominio (dati e logica e il comportamento). Ogni contesto delimitata DDD è correlata a una business microservizio (uno o più servizi). (È expand in questo punto, sul modello di contesto limitato nella sezione successiva).

D'altra parte, l'approccio tradizionale (dati monolitico) utilizzata in molte applicazioni è disporre di una o pochi database centralizzato. Questo è spesso un database SQL normalizzato che viene utilizzato per l'intera applicazione e tutti i sottosistemi relativo interni, come illustrato nella figura 4-7.

![](./media/image7.png)

**Figura 4-7**. Confronto di dati sovranità: monolitico database anziché microservizi

L'approccio centralizzato database inizialmente è più semplice e sembra per consentire il riutilizzo di entità in sottosistemi diversi per qualsiasi coerente. Ma in realtà che si finisce con le tabelle di grandi dimensioni che gestiscono molti diversi sottosistemi, e che includono gli attributi e le colonne che non sono necessari nella maggior parte dei casi. è come provare a utilizzare la mappa fisica stesso per escursionismo un breve riepilogo, richiede un trip giornata car e apprendimento geography.

Un'applicazione monolitica con in genere un solo database relazionale ha due importanti vantaggi: [transazioni ACID](https://en.wikipedia.org/wiki/ACID) e il linguaggio SQL, sia funzionante tra tutte le tabelle e i dati relativi all'applicazione. Questo approccio consente di scrivere facilmente una query che combina i dati da più tabelle.

Tuttavia, l'accesso ai dati diventa più complessa quando si passa a un'architettura di microservizi. Ma anche quando le transazioni ACID possono o devono essere utilizzate all'interno di un microservizio o il contesto limitato, i dati di proprietà di ogni microservizio sono privati per tale microservizio e accessibile solo tramite l'API microservizio. Incapsulamento dei dati garantisce che i microservizi ad accoppiamento debole e possono evolvere indipendentemente uno da altro. Se più servizi accedesse agli stessi dati, gli aggiornamenti dello schema sono necessario coordinare gli aggiornamenti a tutti i servizi. Ciò causa l'interruzione del ciclo di vita autonomia microservizio. Ma le strutture di dati distribuiti significa che non è possibile apportare una singola transazione ACID tra microservizi. Questo significa che a sua volta quando un processo di business interessa più microservizi, è necessario utilizzare la coerenza eventuale. Questo è molto più difficile da implementare rispetto ai join SQL semplice; Analogamente, molte altre funzionalità di database relazionale non sono disponibili in più microservizi.

Continua anche, microservizi diversi utilizzano spesso diversi *tipi* di database. Archivio applicazioni moderne e processo di diversi tipi di dati e un database relazionale non è sempre la scelta migliore. Per alcuni casi d'uso, un database NoSQL come Azure DocumentDB o MongoDB potrebbe disporre di un modello di dati più semplice e offrono migliori prestazioni e scalabilità rispetto a un database SQL, ad esempio SQL Server o Database SQL di Azure. In altri casi, un database relazionale è ancora l'approccio migliore. Pertanto, le applicazioni basate su microservizi spesso utilizzare una combinazione di database SQL e database NoSQL, talvolta denominato il [polyglot persistenza](http://martinfowler.com/bliki/PolyglotPersistence.html) approccio.

Un'architettura partizionata, polyglot permanente per l'archivio dati presenta numerosi vantaggi. Tra cui servizi loosely-coupled e migliori prestazioni, scalabilità, costi e la gestibilità. Tuttavia, può causare alcuni problemi di gestione di dati distribuiti, come verrà illustrato "[che identifica i limiti di modello di dominio](#identifying-domain-model-boundaries-for-each-microservice)" più avanti in questo capitolo.

## <a name="the-relationship-between-microservices-and-the-bounded-context-pattern"></a>La relazione tra microservizi e il criterio di contesto limitato

Il concetto di microservizio deriva il [modello delimitata contesto (BC)](http://martinfowler.com/bliki/BoundedContext.html) in [progettazione basati su dominio (DDD)](https://en.wikipedia.org/wiki/Domain-driven_design). DDD riguarda i modelli di grandi dimensioni suddividendo li in più BCs e siano espliciti sui loro limiti. Ogni BC deve avere il proprio modello e il database. ogni microservizio appartiene allo stesso modo, i dati correlati. Inoltre, in genere ogni BC ha il proprio [linguaggio universale](http://martinfowler.com/bliki/UbiquitousLanguage.html) per la comunicazione tra gli sviluppatori di software e gli esperti di dominio.

Tali condizioni (principalmente le entità di dominio) in linguaggio universale possono avere nomi diversi in contesti diversi delimitata, entità di dominio anche quando diversi condividono la stessa identità (vale a dire l'ID univoco utilizzato per leggere l'entità dall'archiviazione). Ad esempio, in un contesto limitato per il profilo utente, l'entità utente di dominio potrebbe condividere identità con l'entità di dominio dell'acquirente nel contesto limitato di ordinamento.

Un microservizio equivale pertanto un contesto limitato, ma specifica inoltre che è un servizio distribuito. È compilato come processo separato per ogni contesto delimitata e deve utilizzare i protocolli distribuiti indicati in precedenza, ad esempio HTTP/HTTPS, WebSockets, o [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol). Criterio di contesto limitato, tuttavia, non specificare se il contesto delimitata è un servizio distribuito o se è semplicemente un limite logico (ad esempio un sottosistema generico) all'interno di un'applicazione monolitico distribuzione.

È importante evidenziare che la definizione di un servizio per ogni contesto delimitata è un buon punto di partenza. Ma non si dispone di vincolare la progettazione a esso. In alcuni casi è necessario progettare un contesto delimitato o microservizio business è costituita da diversi servizi fisici. Ma in definitiva, entrambi i modelli, delimitata contesto e microservizio, ovvero sono strettamente correlati.

DDD dei vantaggi di microservizi ottenendo reali limiti sotto forma di microservizi distribuita. Ma idee come la condivisione non di modello tra microservizi ciò che si desidera anche in un contesto delimitato.

### <a name="additional-resources"></a>Risorse aggiuntive

-   **Chris Richardson. Modello: Per ogni servizio del Database**
    [*http://microservices.io/patterns/data/database-per-service.html*](http://microservices.io/patterns/data/database-per-service.html)

-   **Martin Fowler. BoundedContext**
    [*http://martinfowler.com/bliki/BoundedContext.html*](http://martinfowler.com/bliki/BoundedContext.html)

-   **Martin Fowler. PolyglotPersistence**
    [*http://martinfowler.com/bliki/PolyglotPersistence.html*](http://martinfowler.com/bliki/PolyglotPersistence.html)

-   **Alberto Brandolini. Progettazione con il Mapping del contesto basata su domini strategico**
    [*https://www.infoq.com/articles/ddd-contextmapping*](https://www.infoq.com/articles/ddd-contextmapping)


>[!div class="step-by-step"]
[Precedente] (architecture.md microservizi) [Avanti] (logico-e-fisica-architecture.md)
