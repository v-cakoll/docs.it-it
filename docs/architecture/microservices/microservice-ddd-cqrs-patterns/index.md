---
title: Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Informazioni su come gestire scenari aziendali complessi applicando i modelli DDD e CQRS
ms.date: 10/08/2018
ms.openlocfilehash: 852073548a66fbe568fc5c2531342db944d5a8b0
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144643"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="a27c4-103">Gestire la complessità aziendale in un microservizio con i modelli DDD e CQRS</span><span class="sxs-lookup"><span data-stu-id="a27c4-103">Tackle Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="a27c4-104">*Progettare un modello di dominio per ogni microservizio o contesto vincolato che rispecchi le informazioni esistenti sul dominio aziendale.*</span><span class="sxs-lookup"><span data-stu-id="a27c4-104">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="a27c4-105">Questa sezione illustra i microservizi più avanzati implementabili quando è necessario gestire sottosistemi complessi o i microservizi derivati dalla conoscenza degli esperti del settore con regole business in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="a27c4-105">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="a27c4-106">I modelli di architettura usati in questa sezione si basano su approcci per la progettazione basata su domini (DDD) e la separazione di responsabilità per query e comandi (CQRS), come illustrato nella figura 7-1.</span><span class="sxs-lookup"><span data-stu-id="a27c4-106">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 7-1.</span></span>

:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="Diagramma che confronta modelli di architettura interni ed esterni.":::
<span data-ttu-id="a27c4-108">Differenza tra l'architettura esterna (modelli di microservizio, gateway API, comunicazioni resilienti, pubblicazione/sottoscrizione e così via) e l'architettura interna (basata su dati/CRUD, modelli DDD, inserimento di dipendenze, librerie multiple e così via).</span><span class="sxs-lookup"><span data-stu-id="a27c4-108">Difference between external architecture: microservice patterns, API gateways, resilient communications, pub/sub, etc., and internal architecture: data driven/CRUD, DDD patterns, dependency injection, multiple libraries, etc.</span></span>
:::image-end:::

<span data-ttu-id="a27c4-109">**Figura 7-1**.</span><span class="sxs-lookup"><span data-stu-id="a27c4-109">**Figure 7-1**.</span></span> <span data-ttu-id="a27c4-110">Architettura di microservizi esterna e modelli di architettura interna per ogni microservizio a confronto</span><span class="sxs-lookup"><span data-stu-id="a27c4-110">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="a27c4-111">Tuttavia, la maggior parte delle tecniche per microservizi basati sui dati, ad esempio come implementare un servizio API Web ASP.NET Core o come esporre metadati Swagger con Swashbuckle o NSwag, è anche applicabile ai microservizi più avanzati implementati internamente con modelli DDD.</span><span class="sxs-lookup"><span data-stu-id="a27c4-111">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle or NSwag, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="a27c4-112">Questa sezione è un'estensione delle sezioni precedenti, poiché la maggior parte delle procedure illustrate prima si applicano anche qui o per qualsiasi tipo di microservizio.</span><span class="sxs-lookup"><span data-stu-id="a27c4-112">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="a27c4-113">Questa sezione fornisce innanzitutto informazioni dettagliate sui modelli CQRS semplificati usati nell'applicazione di riferimento eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="a27c4-113">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="a27c4-114">Successivamente, verrà fornita una panoramica delle tecniche DDD che consentono di individuare modelli comuni riutilizzabili nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a27c4-114">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="a27c4-115">DDD è un argomento vasto con un'ampia gamma di risorse di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="a27c4-115">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="a27c4-116">È possibile iniziare da pubblicazioni come [Domain-Driven Design](https://domainlanguage.com/ddd/) di Eric Evans e altro materiale di Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard e molti altri esperti di DDD/CQRS.</span><span class="sxs-lookup"><span data-stu-id="a27c4-116">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="a27c4-117">Ma la cosa più importante è tentare di apprendere come applicare le tecniche DDD da conversazioni, lavagne e sessioni di modellazione di dominio con esperti del dominio aziendale reale.</span><span class="sxs-lookup"><span data-stu-id="a27c4-117">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="a27c4-118">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a27c4-118">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="a27c4-119">Progettazione basata su domini (DDD)</span><span class="sxs-lookup"><span data-stu-id="a27c4-119">DDD (Domain-Driven Design)</span></span>

- <span data-ttu-id="a27c4-120">**Eric Evans. Lingua del dominio** </span><span class="sxs-lookup"><span data-stu-id="a27c4-120">**Eric Evans. Domain Language** </span></span>\
  <https://domainlanguage.com/>

- <span data-ttu-id="a27c4-121">**Martin Fowler. Progettazione basata su dominio** </span><span class="sxs-lookup"><span data-stu-id="a27c4-121">**Martin Fowler. Domain-Driven Design** </span></span>\
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- <span data-ttu-id="a27c4-122">**Jimmy Bogard. Potenziamento del dominio: un Nozioni di fondo** </span><span class="sxs-lookup"><span data-stu-id="a27c4-122">**Jimmy Bogard. Strengthening your domain: a primer** </span></span>\
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a><span data-ttu-id="a27c4-123">Pubblicazioni sulla progettazione DDD</span><span class="sxs-lookup"><span data-stu-id="a27c4-123">DDD books</span></span>

- <span data-ttu-id="a27c4-124">**Eric Evans. Progettazione basata su domini: affrontare la complessità nel cuore del software** </span><span class="sxs-lookup"><span data-stu-id="a27c4-124">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="a27c4-125">**Eric Evans. Riferimento alla progettazione basata su dominio: definizioni e riepiloghi dei modelli** </span><span class="sxs-lookup"><span data-stu-id="a27c4-125">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- <span data-ttu-id="a27c4-126">**Vaughn Vernon. Implementazione della progettazione basata su dominio** </span><span class="sxs-lookup"><span data-stu-id="a27c4-126">**Vaughn Vernon. Implementing Domain-Driven Design** </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="a27c4-127">**Vaughn Vernon. Progettazione basata su dominio distillata** </span><span class="sxs-lookup"><span data-stu-id="a27c4-127">**Vaughn Vernon. Domain-Driven Design Distilled** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- <span data-ttu-id="a27c4-128">**Jimmy Nilsson. Applicazione di modelli e progettazione basati su dominio** </span><span class="sxs-lookup"><span data-stu-id="a27c4-128">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns** </span></span>\
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- <span data-ttu-id="a27c4-129">**Cesar de la Torre. Guida all'architettura orientata ai domini a N livelli con .NET** </span><span class="sxs-lookup"><span data-stu-id="a27c4-129">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET** </span></span>\
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- <span data-ttu-id="a27c4-130">**Abel Avram e Floyd Marinescu. Progettazione basata su dominio rapidamente** </span><span class="sxs-lookup"><span data-stu-id="a27c4-130">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- <span data-ttu-id="a27c4-131">**Scott Millett, Nick Tune-patterns, principi e procedure di progettazione basata su dominio** </span><span class="sxs-lookup"><span data-stu-id="a27c4-131">**Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design** </span></span>\
  <https://www.wiley.com/Patterns%2C+Principles%2C+and+Practices+of+Domain+Driven+Design-p-9781118714706>

##### <a name="ddd-training"></a><span data-ttu-id="a27c4-132">Training per la progettazione DDD</span><span class="sxs-lookup"><span data-stu-id="a27c4-132">DDD training</span></span>

- <span data-ttu-id="a27c4-133">**Julie Lerman e Steve Smith. Nozioni fondamentali sulla progettazione basata su dominio** </span><span class="sxs-lookup"><span data-stu-id="a27c4-133">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals** </span></span>\
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
><span data-ttu-id="a27c4-134">[Precedente](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md) 
> [Avanti](apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="a27c4-134">[Previous](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
[Next](apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
