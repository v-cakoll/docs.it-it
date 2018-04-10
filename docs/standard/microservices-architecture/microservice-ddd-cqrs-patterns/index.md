---
title: Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 45f29a8d19e49685f864b7ca83e466ceb1f73a62
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a>Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS

*Progettare un modello di dominio per ogni microservizio o contesto vincolato che rispecchi le informazioni esistenti sul dominio aziendale.*

Questa sezione illustra i microservizi più avanzati implementabili quando è necessario gestire sottosistemi complessi o i microservizi derivati dalla conoscenza degli esperti del settore con regole business in continua evoluzione. I modelli di architettura usati in questa sezione si basano su approcci per la progettazione basata su domini (DDD) e di tipo Command and Query Responsibility Segregation (CQRS), come illustrato nella figura 9-1.

![](./media/image1.png)

**Figura 9-1**. Architettura di microservizi esterna e modelli di architettura interna per ogni microservizio a confronto

Tuttavia, la maggior parte delle tecniche per microservizi basati sui dati, ad esempio come implementare un servizio API Web ASP.NET Core o come esporre metadati Swagger con Swashbuckle, è anche applicabile ai microservizi più avanzati implementati internamente con modelli DDD. Questa sezione è un'estensione delle sezioni precedenti, poiché la maggior parte delle procedure illustrate prima si applicano anche qui o per qualsiasi tipo di microservizio.

Questa sezione fornisce innanzitutto informazioni dettagliate sui modelli CQRS semplificati usati nell'applicazione di riferimento eShopOnContainers. Successivamente, verrà fornita una panoramica delle tecniche DDD che consentono di individuare modelli comuni riutilizzabili nelle applicazioni.

DDD è un argomento vasto con un'ampia gamma di risorse di apprendimento. È possibile iniziare da pubblicazioni come [Domain-Driven Design](https://domainlanguage.com/ddd/) di Eric Evans e altro materiale di Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard e molti altri esperti di DDD/CQRS. Ma la cosa più importante è tentare di apprendere come applicare le tecniche DDD da conversazioni, lavagne e sessioni di modellazione di dominio con esperti del dominio aziendale reale.

#### <a name="additional-resources"></a>Risorse aggiuntive

##### <a name="ddd-domain-driven-design"></a>Progettazione basata su domini (DDD)

-   **Eric Evans. Domain Language (Linguaggio di dominio)**
    [*http://domainlanguage.com/*](http://domainlanguage.com/)

-   **Martin Fowler. Domain-Driven Design (Progettazione basata su domini)**
    [*http://martinfowler.com/tags/domain%20driven%20design.html*](http://martinfowler.com/tags/domain%20driven%20design.html)

-   **Jimmy Bogard. Strengthening your domain: a primer (Rafforzamento del dominio: panoramica)**
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)

##### <a name="ddd-books"></a>Pubblicazioni sulla progettazione DDD

-   **Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)

-   **Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)

-   **Vaughn Vernon. Implementing Domain-Driven Design**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)

-   **Vaughn Vernon. Domain-Driven Design Distilled**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)

-   **Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)

-   **Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)

-   **Abel Avram e Floyd Marinescu. Domain-Driven Design Quickly**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)

Training per la progettazione DDD

-   **Julie Lerman e Steve Smith. Domain-Driven Design Fundamentals (Nozioni fondamentali sulla progettazione basata su domini)**
    [*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)


>[!div class="step-by-step"]
[Precedente] (../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md) [Successivo] (apply-simplified-microservice-cqrs-ddd-patterns.md)
