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
ms.openlocfilehash: 8098c62ac18593d8044d52cb24c4cd8859972e68
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="tackling-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="11723-104">Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS</span><span class="sxs-lookup"><span data-stu-id="11723-104">Tackling Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="11723-105">*Progettare un modello di dominio per ogni microservizio o contesto vincolato che rispecchi le informazioni esistenti sul dominio aziendale.*</span><span class="sxs-lookup"><span data-stu-id="11723-105">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="11723-106">Questa sezione illustra i microservizi più avanzati implementabili quando è necessario gestire sottosistemi complessi o i microservizi derivati dalla conoscenza degli esperti del settore con regole business in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="11723-106">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="11723-107">I modelli di architettura usati in questa sezione si basano su approcci per la progettazione basata su domini (DDD) e di tipo Command and Query Responsibility Segregation (CQRS), come illustrato nella figura 9-1.</span><span class="sxs-lookup"><span data-stu-id="11723-107">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 9-1.</span></span>

![](./media/image1.png)

<span data-ttu-id="11723-108">**Figura 9-1**.</span><span class="sxs-lookup"><span data-stu-id="11723-108">**Figure 9-1**.</span></span> <span data-ttu-id="11723-109">Architettura di microservizi esterna e modelli di architettura interna per ogni microservizio a confronto</span><span class="sxs-lookup"><span data-stu-id="11723-109">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="11723-110">Tuttavia, la maggior parte delle tecniche per microservizi basati sui dati, ad esempio come implementare un servizio API Web ASP.NET Core o come esporre metadati Swagger con Swashbuckle, è anche applicabile ai microservizi più avanzati implementati internamente con modelli DDD.</span><span class="sxs-lookup"><span data-stu-id="11723-110">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="11723-111">Questa sezione è un'estensione delle sezioni precedenti, poiché la maggior parte delle procedure illustrate prima si applicano anche qui o per qualsiasi tipo di microservizio.</span><span class="sxs-lookup"><span data-stu-id="11723-111">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="11723-112">Questa sezione fornisce innanzitutto informazioni dettagliate sui modelli CQRS semplificati usati nell'applicazione di riferimento eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="11723-112">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="11723-113">Successivamente, verrà fornita una panoramica delle tecniche DDD che consentono di individuare modelli comuni riutilizzabili nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="11723-113">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="11723-114">DDD è un argomento vasto con un'ampia gamma di risorse di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="11723-114">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="11723-115">È possibile iniziare da pubblicazioni come [Domain-Driven Design](https://domainlanguage.com/ddd/) di Eric Evans e altro materiale di Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard e molti altri esperti di DDD/CQRS.</span><span class="sxs-lookup"><span data-stu-id="11723-115">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="11723-116">Ma la cosa più importante è tentare di apprendere come applicare le tecniche DDD da conversazioni, lavagne e sessioni di modellazione di dominio con esperti del dominio aziendale reale.</span><span class="sxs-lookup"><span data-stu-id="11723-116">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="11723-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="11723-117">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="11723-118">Progettazione basata su domini (DDD)</span><span class="sxs-lookup"><span data-stu-id="11723-118">DDD (Domain-Driven Design)</span></span>

-   <span data-ttu-id="11723-119">**Eric Evans. (Domain Language) Linguaggio dei domini**
    [*https://domainlanguage.com/*](https://domainlanguage.com/)</span><span class="sxs-lookup"><span data-stu-id="11723-119">**Eric Evans. Domain Language**
[*https://domainlanguage.com/*](https://domainlanguage.com/)</span></span>

-   <span data-ttu-id="11723-120">**Martin Fowler. Domain-Driven Design (Progettazione basata su domini)**
    [*https://martinfowler.com/tags/domain%20driven%20design.html*](https://martinfowler.com/tags/domain%20driven%20design.html)</span><span class="sxs-lookup"><span data-stu-id="11723-120">**Martin Fowler. Domain-Driven Design**
[*https://martinfowler.com/tags/domain%20driven%20design.html*](https://martinfowler.com/tags/domain%20driven%20design.html)</span></span>

-   <span data-ttu-id="11723-121">**Jimmy Bogard. Strengthening your domain: a primer (Rafforzamento del dominio: panoramica)**
    [*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span><span class="sxs-lookup"><span data-stu-id="11723-121">**Jimmy Bogard. Strengthening your domain: a primer**
[*https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/*](https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/)</span></span>

##### <a name="ddd-books"></a><span data-ttu-id="11723-122">Pubblicazioni sulla progettazione DDD</span><span class="sxs-lookup"><span data-stu-id="11723-122">DDD books</span></span>

-   <span data-ttu-id="11723-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software (Progettazione basata su domini: gestire le complessità nel software)**
    [*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span><span class="sxs-lookup"><span data-stu-id="11723-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software**
[*https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/*](https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/)</span></span>

-   <span data-ttu-id="11723-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries (Riferimento alla progettazione basata su domini: definizioni e riepiloghi di modello)**
    [*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span><span class="sxs-lookup"><span data-stu-id="11723-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries**
[*https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/*](https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/)</span></span>

-   <span data-ttu-id="11723-125">**Vaughn Vernon. Implementing Domain-Driven Design (Implementazione della progettazione basata su domini)**
    [*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span><span class="sxs-lookup"><span data-stu-id="11723-125">**Vaughn Vernon. Implementing Domain-Driven Design**
[*https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/*](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/)</span></span>

-   <span data-ttu-id="11723-126">**Vaughn Vernon. Domain-Driven Design Distilled (Progettazione basata su domini - versione sintetizzata)**
    [*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span><span class="sxs-lookup"><span data-stu-id="11723-126">**Vaughn Vernon. Domain-Driven Design Distilled**
[*https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/*](https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/)</span></span>

-   <span data-ttu-id="11723-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns (Applicazione di progettazione e modelli basati su domini)**
    [*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span><span class="sxs-lookup"><span data-stu-id="11723-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns**
[*https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/*](https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/)</span></span>

-   <span data-ttu-id="11723-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET (Guida all'architettura a N livelli orientata ai domini .NET)**
    [*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span><span class="sxs-lookup"><span data-stu-id="11723-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET**
[*https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/*](https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/)</span></span>

-   <span data-ttu-id="11723-129">**Abel Avram e Floyd Marinescu. Domain-Driven Design Quickly (Progettazione basata su domini - concetti principali)**
    [*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span><span class="sxs-lookup"><span data-stu-id="11723-129">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly**
[*https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/*](https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/)</span></span>

<span data-ttu-id="11723-130">Training per la progettazione DDD</span><span class="sxs-lookup"><span data-stu-id="11723-130">DDD training</span></span>

-   <span data-ttu-id="11723-131">**Julie Lerman e Steve Smith. Domain-Driven Design Fundamentals (Nozioni fondamentali sulla progettazione basata su domini)**
    [*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span><span class="sxs-lookup"><span data-stu-id="11723-131">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals**
[*http://bit.ly/PS-DDD*](http://bit.ly/PS-DDD)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="11723-132">[Precedente] (../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md) [Successivo] (apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="11723-132">[Previous] (../multi-container-microservice-net-applications/background-tasks-with-ihostedservice.md) [Next] (apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
