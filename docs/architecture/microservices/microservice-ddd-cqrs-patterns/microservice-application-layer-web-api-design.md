---
title: Progettazione del livello dell'applicazione di microservizi e dell'API Web
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | Brevi cenni sui principi SOLID per la progettazione del livello dell'applicazione.
ms.date: 10/08/2018
ms.openlocfilehash: 3c3b9f74e76e01deafa1f97de5d3250d57716014
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "68676518"
---
# <a name="design-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="8666f-103">Progettare il livello dell'applicazione di microservizi e dell'API Web</span><span class="sxs-lookup"><span data-stu-id="8666f-103">Design the microservice application layer and Web API</span></span>

## <a name="use-solid-principles-and-dependency-injection"></a><span data-ttu-id="8666f-104">Usare i principi SOLID e l'inserimento delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="8666f-104">Use SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="8666f-105">I principi SOLID sono tecniche fondamentali da usare nelle applicazioni cruciali moderne, ad esempio lo sviluppo di un microservizio con schemi progettazione basata su domini.</span><span class="sxs-lookup"><span data-stu-id="8666f-105">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="8666f-106">SOLID è un acronimo che raggruppa cinque principi fondamentali:</span><span class="sxs-lookup"><span data-stu-id="8666f-106">SOLID is an acronym that groups five fundamental principles:</span></span>

- <span data-ttu-id="8666f-107">SRP (Single Responsibility Principle, principio di singola responsabilità)</span><span class="sxs-lookup"><span data-stu-id="8666f-107">Single Responsibility principle</span></span>

- <span data-ttu-id="8666f-108">OCP (Open/Closed Principle, principio aperto/chiuso)</span><span class="sxs-lookup"><span data-stu-id="8666f-108">Open/closed principle</span></span>

- <span data-ttu-id="8666f-109">LSP (Liskov Substitution Principle, principio di sostituzione di Liskov)</span><span class="sxs-lookup"><span data-stu-id="8666f-109">Liskov substitution principle</span></span>

- <span data-ttu-id="8666f-110">Principio di segregazione delle interfacce (Interface Segregation Principle)</span><span class="sxs-lookup"><span data-stu-id="8666f-110">Interface Segregation principle</span></span>

- <span data-ttu-id="8666f-111">DIP (Dependency Inversion Principle, principio di inversione delle dipendenze)</span><span class="sxs-lookup"><span data-stu-id="8666f-111">Dependency Inversion principle</span></span>

<span data-ttu-id="8666f-112">SOLID si riferisce soprattutto alla progettazione dei livelli interni dell'applicazione o del microservizio e alla separazione delle reciproche dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8666f-112">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="8666f-113">Non è relativo al dominio, ma alla progettazione tecnica dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8666f-113">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="8666f-114">L'ultimo principio, quello dell'inversione delle dipendenze, consente di disaccoppiare il livello infrastruttura dagli altri livelli e permette quindi una migliore implementazione disaccoppiata dei livelli di progettazione basata su domini.</span><span class="sxs-lookup"><span data-stu-id="8666f-114">The final principle, the Dependency Inversion principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="8666f-115">L'inserimento delle dipendenze è un modo per implementare il principio di inversione delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8666f-115">Dependency Injection (DI) is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="8666f-116">È una tecnica per ottenere un regime di controllo libero tra gli oggetti e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="8666f-116">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="8666f-117">Invece di creare direttamente un'istanza dei collaboratori o usare riferimenti statici, gli oggetti necessari a una classe per eseguire le azioni vengono resi disponibili alla (o "inseriti nella") classe.</span><span class="sxs-lookup"><span data-stu-id="8666f-117">Rather than directly instantiating collaborators, or using static references (that is, using new…), the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="8666f-118">Nella maggior parte dei casi le classi dichiarano le dipendenze tramite il costruttore consentendo di seguire il principio delle dipendenze esplicite.</span><span class="sxs-lookup"><span data-stu-id="8666f-118">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="8666f-119">L'inserimento delle dipendenze si basa in genere su contenitori a inversione del controllo (IoC, Inversion of Control) specifici.</span><span class="sxs-lookup"><span data-stu-id="8666f-119">Dependency Injection is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="8666f-120">ASP.NET Core fornisce un semplice contenitore IoC predefinito, ma è anche possibile usare il contenitore IoC preferito, ad esempio Autofac o Ninject.</span><span class="sxs-lookup"><span data-stu-id="8666f-120">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="8666f-121">Se si seguono i principi SOLID, le classi tenderanno a essere piccole, con refactoring corretto e facili da testare.</span><span class="sxs-lookup"><span data-stu-id="8666f-121">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="8666f-122">Ma come sapere se nelle classi vengono inserite troppe dipendenze?</span><span class="sxs-lookup"><span data-stu-id="8666f-122">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="8666f-123">Se si usa l'inserimento delle dipendenze tramite il costruttore, sarà possibile determinarlo con facilità, semplicemente esaminando il numero di parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="8666f-123">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="8666f-124">Se le dipendenze sono troppe, ciò è in genere una prova (un [code smell](https://deviq.com/code-smells/)) che la classe sta provando a eseguire troppe operazioni e probabilmente sta violando il principio di singola responsabilità.</span><span class="sxs-lookup"><span data-stu-id="8666f-124">If there are too many dependencies, this is generally a sign (a [code smell](https://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="8666f-125">Per illustrare SOLID in dettaglio, servirebbe un'altra guida.</span><span class="sxs-lookup"><span data-stu-id="8666f-125">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="8666f-126">Questa guida presuppone quindi che si abbia solo una conoscenza di base di questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="8666f-126">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="8666f-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="8666f-127">Additional resources</span></span>

- <span data-ttu-id="8666f-128">**SOLID: Principi OOP fondamentali** </span><span class="sxs-lookup"><span data-stu-id="8666f-128">**SOLID: Fundamental OOP Principles** </span></span>\
  <https://deviq.com/solid/>

- <span data-ttu-id="8666f-129">**Inversione dei contenitori di controllo e il modello di inserimento delle dipendenzeInversion of Control Containers and the Dependency Injection pattern** </span><span class="sxs-lookup"><span data-stu-id="8666f-129">**Inversion of Control Containers and the Dependency Injection pattern** </span></span>\
  <https://martinfowler.com/articles/injection.html>

- <span data-ttu-id="8666f-130">**Steve Smith. Nuovo è colla** </span><span class="sxs-lookup"><span data-stu-id="8666f-130">**Steve Smith. New is Glue** </span></span>\
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> <span data-ttu-id="8666f-131">[Successivo](nosql-database-persistence-infrastructure.md)
> [precedente](microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="8666f-131">[Previous](nosql-database-persistence-infrastructure.md)
[Next](microservice-application-layer-implementation-web-api.md)</span></span>
