---
title: Progettazione del livello dell'applicazione di microservizi e dell'API Web
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | Progettazione del livello dell'applicazione di microservizi e dell'API Web
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d623a3bc542e0f044d73f405aa639bef0f6d1ec8
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="4d4af-104">Progettazione del livello dell'applicazione di microservizi e dell'API Web</span><span class="sxs-lookup"><span data-stu-id="4d4af-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="4d4af-105">Uso dei principi SOLID e dell'inserimento delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="4d4af-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="4d4af-106">I principi SOLID sono tecniche fondamentali da usare nelle applicazioni cruciali moderne, ad esempio lo sviluppo di un microservizio con schemi progettazione basata su domini.</span><span class="sxs-lookup"><span data-stu-id="4d4af-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="4d4af-107">SOLID è un acronimo che raggruppa cinque principi fondamentali:</span><span class="sxs-lookup"><span data-stu-id="4d4af-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="4d4af-108">SRP (Single Responsibility Principle, principio di singola responsabilità)</span><span class="sxs-lookup"><span data-stu-id="4d4af-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="4d4af-109">OCP (Open/Closed Principle, principio aperto/chiuso)</span><span class="sxs-lookup"><span data-stu-id="4d4af-109">Open/closed principle</span></span>

-   <span data-ttu-id="4d4af-110">LSP (Liskov Substitution Principle, principio di sostituzione di Liskov)</span><span class="sxs-lookup"><span data-stu-id="4d4af-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="4d4af-111">Principio di segregazione delle interfacce (Interface Segregation Principle)</span><span class="sxs-lookup"><span data-stu-id="4d4af-111">Interface Segregation principle</span></span>

-   <span data-ttu-id="4d4af-112">DIP (Dependency Inversion Principle, principio di inversione delle dipendenze)</span><span class="sxs-lookup"><span data-stu-id="4d4af-112">Dependency Inversion principle</span></span>

<span data-ttu-id="4d4af-113">SOLID si riferisce soprattutto alla progettazione dei livelli interni dell'applicazione o del microservizio e alla separazione delle reciproche dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4d4af-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="4d4af-114">Non è relativo al dominio, ma alla progettazione tecnica dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d4af-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="4d4af-115">L'ultimo principio, quello dell'inversione delle dipendenze, consente di disaccoppiare il livello infrastruttura dagli altri livelli e permette quindi una migliore implementazione disaccoppiata dei livelli di progettazione basata su domini.</span><span class="sxs-lookup"><span data-stu-id="4d4af-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="4d4af-116">L'inserimento delle dipendenze è un modo per implementare il principio di inversione delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4d4af-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="4d4af-117">È una tecnica per ottenere un regime di controllo libero tra gli oggetti e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4d4af-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="4d4af-118">Invece di creare direttamente un'istanza dei collaboratori o usare riferimenti statici, gli oggetti necessari a una classe per eseguire le azioni vengono forniti alla (o "inseriti nella") classe.</span><span class="sxs-lookup"><span data-stu-id="4d4af-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="4d4af-119">Nella maggior parte dei casi le classi dichiarano le dipendenze tramite il costruttore consentendo di seguire il principio delle dipendenze esplicite.</span><span class="sxs-lookup"><span data-stu-id="4d4af-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="4d4af-120">L'inserimento delle dipendenze si basa in genere su contenitori a inversione del controllo (IoC, Inversion of Control).</span><span class="sxs-lookup"><span data-stu-id="4d4af-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="4d4af-121">ASP.NET Core fornisce un semplice contenitore IoC predefinito, ma è anche possibile usare il contenitore IoC preferito, ad esempio Autofac o Ninject.</span><span class="sxs-lookup"><span data-stu-id="4d4af-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="4d4af-122">Se si seguono i principi SOLID, le classi tenderanno a essere piccole, con refactoring corretto e facili da testare.</span><span class="sxs-lookup"><span data-stu-id="4d4af-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="4d4af-123">Ma come sapere se nelle classi vengono inserite troppe dipendenze?</span><span class="sxs-lookup"><span data-stu-id="4d4af-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="4d4af-124">Se si usa l'inserimento delle dipendenze tramite il costruttore, sarà possibile determinarlo con facilità, semplicemente esaminando il numero di parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="4d4af-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="4d4af-125">Se le dipendenze sono troppe, ciò è in genere una prova (un [code smell](http://deviq.com/code-smells/)) che la classe sta provando a eseguire troppe operazioni e probabilmente sta violando il principio di singola responsabilità.</span><span class="sxs-lookup"><span data-stu-id="4d4af-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="4d4af-126">Per illustrare SOLID in dettaglio, servirebbe un'altra guida.</span><span class="sxs-lookup"><span data-stu-id="4d4af-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="4d4af-127">Questa guida presuppone quindi che si abbia solo una conoscenza di base di questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="4d4af-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="4d4af-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4d4af-128">Additional resources</span></span>

-   <span data-ttu-id="4d4af-129">**SOLID: Fundamental OOP Principles (SOLID: principi OOP fondamentali)**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="4d4af-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="4d4af-130">**Inversion of Control Containers and the Dependency Injection Pattern (Contenitori di inversione del controllo e modello di inserimento delle dipendenze)**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="4d4af-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="4d4af-131">**Steve Smith. New is Glue**
    [*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="4d4af-131">**Steve Smith. New is Glue**
[*https://ardalis.com/new-is-glue*](https://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="4d4af-132">[Indietro] (nosql-database-persistence-infrastructure.md) [Avanti] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="4d4af-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
