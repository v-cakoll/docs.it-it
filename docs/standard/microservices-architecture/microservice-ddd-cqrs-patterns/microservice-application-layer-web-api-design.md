---
title: Progettare il livello di applicazione microservizio e l'API Web
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Progettare il livello di applicazione microservizio e l'API Web
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="08af3-104">Progettare il livello di applicazione microservizio e l'API Web</span><span class="sxs-lookup"><span data-stu-id="08af3-104">Designing the microservice application layer and Web API</span></span>

## <a name="using-solid-principles-and-dependency-injection"></a><span data-ttu-id="08af3-105">Utilizzando i principi a tinta unita e inserimento di dipendenze</span><span class="sxs-lookup"><span data-stu-id="08af3-105">Using SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="08af3-106">Tinta unite principi sono critiche tecniche da utilizzare in qualsiasi applicazione moderna e mission-critical, ad esempio lo sviluppo di un microservizio con i modelli di DDD.</span><span class="sxs-lookup"><span data-stu-id="08af3-106">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="08af3-107">Tinta unita è l'acronimo di principi fondamentali di cinque gruppi:</span><span class="sxs-lookup"><span data-stu-id="08af3-107">SOLID is an acronym that groups five fundamental principles:</span></span>

-   <span data-ttu-id="08af3-108">Principio di responsabilità singolo</span><span class="sxs-lookup"><span data-stu-id="08af3-108">Single Responsibility principle</span></span>

-   <span data-ttu-id="08af3-109">Principio di apertura/chiusura</span><span class="sxs-lookup"><span data-stu-id="08af3-109">Open/closed principle</span></span>

-   <span data-ttu-id="08af3-110">Principio di sostituzione Liskov</span><span class="sxs-lookup"><span data-stu-id="08af3-110">Liskov substitution principle</span></span>

-   <span data-ttu-id="08af3-111">Principio di inversione di separazione</span><span class="sxs-lookup"><span data-stu-id="08af3-111">Inversion Segregation principle</span></span>

-   <span data-ttu-id="08af3-112">Principio di inversione di dipendenza</span><span class="sxs-lookup"><span data-stu-id="08af3-112">Dependency Inversion principle</span></span>

<span data-ttu-id="08af3-113">SOLIDO è più su come progettare l'applicazione o microservizio interno livelli e sulle disaccoppiamento dipendenze tra di essi.</span><span class="sxs-lookup"><span data-stu-id="08af3-113">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="08af3-114">Non è correlato al dominio, ma per la progettazione tecnica dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="08af3-114">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="08af3-115">Il principio finale, il principio di inversione di dipendenze (DI), consente di separare il livello di infrastruttura dal resto dei livelli, che consente a un'implementazione separata migliore dei livelli DDD.</span><span class="sxs-lookup"><span data-stu-id="08af3-115">The final principle, the Dependency Inversion (DI) principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="08af3-116">SEN è un modo per implementare il principio di inversione di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="08af3-116">DI is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="08af3-117">È una tecnica per l'implementazione dell'accoppiamento debole tra gli oggetti e le relative dipendenze.</span><span class="sxs-lookup"><span data-stu-id="08af3-117">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="08af3-118">Anziché creare direttamente un'istanza di collaboratori o utilizzando i riferimenti statici, gli oggetti che è necessario che una classe per eseguire le azioni sono forniti a (o "inseriti in") della classe.</span><span class="sxs-lookup"><span data-stu-id="08af3-118">Rather than directly instantiating collaborators, or using static references, the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="08af3-119">In genere, le classi verranno dichiarare le relative dipendenze attraverso il relativo costruttore, consentendo loro di seguire il principio di dipendenze esplicite.</span><span class="sxs-lookup"><span data-stu-id="08af3-119">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="08af3-120">SEN si basa in genere per contenitori specifici che Inversion of Control (IoC).</span><span class="sxs-lookup"><span data-stu-id="08af3-120">DI is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="08af3-121">ASP.NET Core fornisce un semplice contenitore IoC incorporato, ma è anche possibile usare il contenitore IoC preferito, ad esempio Autofac o Ninject.</span><span class="sxs-lookup"><span data-stu-id="08af3-121">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="08af3-122">Seguendo i principi a tinta unita, le classi verranno tendenzialmente naturalmente piccole, ben fornita e facilmente testate.</span><span class="sxs-lookup"><span data-stu-id="08af3-122">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="08af3-123">Ma come possibile fa a sapere se sono venga introdotto troppe dipendenze in classi?</span><span class="sxs-lookup"><span data-stu-id="08af3-123">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="08af3-124">Se si utilizza DI tramite il costruttore, sarà facile rilevare che semplicemente esaminando il numero di parametri per il costruttore.</span><span class="sxs-lookup"><span data-stu-id="08af3-124">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="08af3-125">Se sono presenti troppe dipendenze, si tratta in genere un segno (un [codice odore](http://deviq.com/code-smells/)) la classe sta tentando di eccessivo che è probabile che violano il principio di responsabilità singolo.</span><span class="sxs-lookup"><span data-stu-id="08af3-125">If there are too many dependencies, this is generally a sign (a [code smell](http://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="08af3-126">Occorrere un'altra Guida per coprire CONTINUO in modo dettagliato.</span><span class="sxs-lookup"><span data-stu-id="08af3-126">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="08af3-127">Pertanto, questa guida è necessario conoscere solo un minimo di questi argomenti.</span><span class="sxs-lookup"><span data-stu-id="08af3-127">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="08af3-128">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="08af3-128">Additional resources</span></span>

-   <span data-ttu-id="08af3-129">**CONTINUO: Principi fondamentali OOP**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span><span class="sxs-lookup"><span data-stu-id="08af3-129">**SOLID: Fundamental OOP Principles**
[*http://deviq.com/solid/*](http://deviq.com/solid/%20)</span></span>

-   <span data-ttu-id="08af3-130">**Inversione di contenitori di controlli e il modello di inserimento di dipendenze**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span><span class="sxs-lookup"><span data-stu-id="08af3-130">**Inversion of Control Containers and the Dependency Injection pattern**
[*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)</span></span>

-   <span data-ttu-id="08af3-131">**Steve Smith. Novità è Glue**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span><span class="sxs-lookup"><span data-stu-id="08af3-131">**Steve Smith. New is Glue**
[*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="08af3-132">[Precedente] (nosql-database-persistenza-infrastructure.md) [Avanti] (microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="08af3-132">[Previous] (nosql-database-persistence-infrastructure.md) [Next] (microservice-application-layer-implementation-web-api.md)</span></span>
