---
title: Gestione della complessità aziendale in un microservizio con i modelli DDD e CQRS
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Informazioni su come gestire scenari aziendali complessi applicando i modelli DDD e CQRS
ms.date: 10/08/2018
ms.openlocfilehash: d311641e2ac73205c04c3f1147b54991585ce851
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65639803"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="92686-103">Gestire la complessità aziendale in un microservizio con i modelli DDD e CQRS</span><span class="sxs-lookup"><span data-stu-id="92686-103">Tackle Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="92686-104">*Progettare un modello di dominio per ogni microservizio o contesto vincolato che rispecchi le informazioni esistenti sul dominio aziendale.*</span><span class="sxs-lookup"><span data-stu-id="92686-104">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="92686-105">Questa sezione illustra i microservizi più avanzati implementabili quando è necessario gestire sottosistemi complessi o i microservizi derivati dalla conoscenza degli esperti del settore con regole business in continua evoluzione.</span><span class="sxs-lookup"><span data-stu-id="92686-105">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="92686-106">I modelli di architettura usati in questa sezione si basano su approcci per la progettazione basata su domini (DDD) e la separazione di responsabilità per query e comandi (CQRS), come illustrato nella figura 7-1.</span><span class="sxs-lookup"><span data-stu-id="92686-106">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 7-1.</span></span>

![Differenza tra l'architettura esterna (modelli di microservizio, gateway API, comunicazioni resilienti, pubblicazione/sottoscrizione e così via) e l'architettura interna (basata su dati/CRUD, modelli DDD, inserimento di dipendenze, librerie multiple e così via).](./media/image1.png)

<span data-ttu-id="92686-108">**Figura 7-1**.</span><span class="sxs-lookup"><span data-stu-id="92686-108">**Figure 7-1**.</span></span> <span data-ttu-id="92686-109">Architettura di microservizi esterna e modelli di architettura interna per ogni microservizio a confronto</span><span class="sxs-lookup"><span data-stu-id="92686-109">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="92686-110">Tuttavia, la maggior parte delle tecniche per microservizi basati sui dati, ad esempio come implementare un servizio API Web ASP.NET Core o come esporre metadati Swagger con Swashbuckle o NSwag, è anche applicabile ai microservizi più avanzati implementati internamente con modelli DDD.</span><span class="sxs-lookup"><span data-stu-id="92686-110">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle or NSwag, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="92686-111">Questa sezione è un'estensione delle sezioni precedenti, poiché la maggior parte delle procedure illustrate prima si applicano anche qui o per qualsiasi tipo di microservizio.</span><span class="sxs-lookup"><span data-stu-id="92686-111">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="92686-112">Questa sezione fornisce innanzitutto informazioni dettagliate sui modelli CQRS semplificati usati nell'applicazione di riferimento eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="92686-112">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="92686-113">Successivamente, verrà fornita una panoramica delle tecniche DDD che consentono di individuare modelli comuni riutilizzabili nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="92686-113">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="92686-114">DDD è un argomento vasto con un'ampia gamma di risorse di apprendimento.</span><span class="sxs-lookup"><span data-stu-id="92686-114">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="92686-115">È possibile iniziare da pubblicazioni come [Domain-Driven Design](https://domainlanguage.com/ddd/) di Eric Evans e altro materiale di Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard e molti altri esperti di DDD/CQRS.</span><span class="sxs-lookup"><span data-stu-id="92686-115">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="92686-116">Ma la cosa più importante è tentare di apprendere come applicare le tecniche DDD da conversazioni, lavagne e sessioni di modellazione di dominio con esperti del dominio aziendale reale.</span><span class="sxs-lookup"><span data-stu-id="92686-116">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="92686-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="92686-117">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="92686-118">Progettazione basata su domini (DDD)</span><span class="sxs-lookup"><span data-stu-id="92686-118">DDD (Domain-Driven Design)</span></span>

- <span data-ttu-id="92686-119">**Eric Evans. Domain Language** \\</span><span class="sxs-lookup"><span data-stu-id="92686-119">**Eric Evans. Domain Language** \\</span></span>
  <https://domainlanguage.com/>

- <span data-ttu-id="92686-120">**Martin Fowler. Domain-Driven Design (Progettazione basata su domini)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-120">**Martin Fowler. Domain-Driven Design** \\</span></span>
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- <span data-ttu-id="92686-121">**Jimmy Bogard. Strengthening your domain: a primer (Rafforzamento del dominio: panoramica)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-121">**Jimmy Bogard. Strengthening your domain: a primer** \\</span></span>
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a><span data-ttu-id="92686-122">Pubblicazioni sulla progettazione DDD</span><span class="sxs-lookup"><span data-stu-id="92686-122">DDD books</span></span>

- <span data-ttu-id="92686-123">**Eric Evans. Domain-Driven Design (Progettazione basata su domini): Tackling Complexity in the Heart of Software (Gestione della complessità nel software)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-123">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software** \\</span></span>
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="92686-124">**Eric Evans. Domain-Driven Design Reference: (Riferimenti nella progettazione basata su domini) Definitions and Pattern Summaries (Riepiloghi di definizioni e modelli)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-124">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries** \\</span></span>
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- <span data-ttu-id="92686-125">**Vaughn Vernon. Implementing Domain-Driven Design (Implementazione della progettazione basata su domini)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-125">**Vaughn Vernon. Implementing Domain-Driven Design** \\</span></span>
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="92686-126">**Vaughn Vernon. Domain-Driven Design Distilled (Progettazione basata su domini - versione sintetizzata)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-126">**Vaughn Vernon. Domain-Driven Design Distilled** \\</span></span>
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- <span data-ttu-id="92686-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns (Applicazione di progettazione e modelli basati su domini)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-127">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns** \\</span></span>
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- <span data-ttu-id="92686-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET (Guida all'architettura a N livelli orientata ai domini .NET)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-128">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET** \\</span></span>
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- <span data-ttu-id="92686-129">**Abel Avram e Floyd Marinescu. Domain-Driven Design Quickly (Progettazione basata su domini - concetti principali)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-129">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly** \\</span></span>
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- <span data-ttu-id="92686-130">**Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design (Modelli, principi e procedure della progettazione basata su domini)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-130">**Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design** \\</span></span>
  <http://www.wrox.com/WileyCDA/WroxTitle/Patterns-Principles-and-Practices-of-Domain-Driven-Design.productCd-1118714709.html>

##### <a name="ddd-training"></a><span data-ttu-id="92686-131">Training per la progettazione DDD</span><span class="sxs-lookup"><span data-stu-id="92686-131">DDD training</span></span>

- <span data-ttu-id="92686-132">**Julie Lerman e Steve Smith. Domain-Driven Design Fundamentals (Nozioni fondamentali sulla progettazione basata su domini)** \\</span><span class="sxs-lookup"><span data-stu-id="92686-132">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals** \\</span></span>
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
><span data-ttu-id="92686-133">[Precedente](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[Successivo](apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="92686-133">[Previous](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
[Next](apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
