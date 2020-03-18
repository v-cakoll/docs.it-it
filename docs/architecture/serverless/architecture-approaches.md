---
title: Approcci per l'architettura - App senza server
description: Introduzione agli approcci architetturali per la creazione di applicazioni aziendali basate su cloud, dalle architetture a più livelli a quella senza server.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522892"
---
# <a name="architecture-approaches"></a><span data-ttu-id="c8d35-103">Approcci all'architettura</span><span class="sxs-lookup"><span data-stu-id="c8d35-103">Architecture approaches</span></span>

<span data-ttu-id="c8d35-104">Comprendere gli approcci esistenti per l'architettura di app aziendali consente di chiarire il ruolo svolto da serverless.</span><span class="sxs-lookup"><span data-stu-id="c8d35-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="c8d35-105">Ci sono molti approcci e modelli che si sono evoluti nel corso di decenni di sviluppo software, e tutti hanno i propri pro e contro.</span><span class="sxs-lookup"><span data-stu-id="c8d35-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="c8d35-106">In molti casi, la soluzione definitiva non può comportare la decisione su un unico approccio, ma può integrare diversi approcci.</span><span class="sxs-lookup"><span data-stu-id="c8d35-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="c8d35-107">Gli scenari di migrazione spesso comportano il passaggio da un approccio all'architettura all'altro attraverso un approccio ibrido.</span><span class="sxs-lookup"><span data-stu-id="c8d35-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="c8d35-108">In questo capitolo viene fornita una panoramica dei modelli di architettura logica e fisica per le applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="c8d35-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="c8d35-109">Modelli di architettura</span><span class="sxs-lookup"><span data-stu-id="c8d35-109">Architecture patterns</span></span>

<span data-ttu-id="c8d35-110">Le applicazioni aziendali moderne seguono una varietà di modelli di architettura.</span><span class="sxs-lookup"><span data-stu-id="c8d35-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="c8d35-111">Questa sezione rappresenta un'indagine sui modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="c8d35-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="c8d35-112">I modelli elencati di seguito non sono necessariamente tutte le procedure consigliate, ma illustrano approcci diversi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="c8d35-113">Per altre informazioni, vedere [Guida all'architettura delle applicazioni](https://docs.microsoft.com/azure/architecture/guide/)di Azure .For more information, see Azure application architecture guide .</span><span class="sxs-lookup"><span data-stu-id="c8d35-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="c8d35-114">Monoliti</span><span class="sxs-lookup"><span data-stu-id="c8d35-114">Monoliths</span></span>

<span data-ttu-id="c8d35-115">Molte applicazioni aziendali seguono un modello monolito.</span><span class="sxs-lookup"><span data-stu-id="c8d35-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="c8d35-116">Le applicazioni legacy vengono spesso implementate come monoliti.</span><span class="sxs-lookup"><span data-stu-id="c8d35-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="c8d35-117">Nel modello monolito, tutti i problemi dell'applicazione sono contenuti in un'unica distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c8d35-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="c8d35-118">Tutto, dall'interfaccia utente alle chiamate al database, è incluso nella stessa codebase.</span><span class="sxs-lookup"><span data-stu-id="c8d35-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Architettura monolite](./media/monolith-architecture.png)

<span data-ttu-id="c8d35-120">L'approccio monolitico presenta diversi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="c8d35-121">Spesso è facile tirare giù una singola base di codice e iniziare a lavorare.</span><span class="sxs-lookup"><span data-stu-id="c8d35-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="c8d35-122">Il tempo di rampup può essere inferiore e la creazione di ambienti di test è semplice come fornire una nuova copia.</span><span class="sxs-lookup"><span data-stu-id="c8d35-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="c8d35-123">Il monolite può essere progettato per includere più componenti e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="c8d35-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="c8d35-124">Sfortunatamente, il modello monolito tende a rompersi su larga scala.</span><span class="sxs-lookup"><span data-stu-id="c8d35-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="c8d35-125">I principali svantaggi dell'approccio monolitico includono:</span><span class="sxs-lookup"><span data-stu-id="c8d35-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="c8d35-126">Difficile lavorare in parallelo nella stessa base di codice.</span><span class="sxs-lookup"><span data-stu-id="c8d35-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="c8d35-127">Qualsiasi modifica, indipendentemente dal fatto che sia semplice, richiede la distribuzione di una nuova versione dell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="c8d35-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="c8d35-128">Il refactoring influisce potenzialmente sull'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="c8d35-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="c8d35-129">Spesso l'unica soluzione per scalare è quella di creare più copie a uso elevato di risorse del monolite.</span><span class="sxs-lookup"><span data-stu-id="c8d35-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="c8d35-130">Man mano che i sistemi si espandono o vengono acquisiti altri sistemi, l'integrazione può essere difficile.</span><span class="sxs-lookup"><span data-stu-id="c8d35-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="c8d35-131">Può essere difficile da testare a causa della necessità di configurare l'intero monolite.</span><span class="sxs-lookup"><span data-stu-id="c8d35-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="c8d35-132">Il riutilizzo del codice è impegnativo e spesso altre app finiscono per avere le proprie copie del codice.</span><span class="sxs-lookup"><span data-stu-id="c8d35-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="c8d35-133">Molte aziende considerano il cloud un'opportunità per migrare le applicazioni monolistiche e allo stesso tempo eseguirne il refactoring in modelli più utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="c8d35-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="c8d35-134">È comune suddividere le singole applicazioni e componenti per consentirne la manutenzione, la distribuzione e la scalabilità separata.</span><span class="sxs-lookup"><span data-stu-id="c8d35-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="c8d35-135">Applicazioni A N livelli</span><span class="sxs-lookup"><span data-stu-id="c8d35-135">N-Layer applications</span></span>

<span data-ttu-id="c8d35-136">Logica dell'applicazione della partizione applicativa a più livelli in livelli specifici.</span><span class="sxs-lookup"><span data-stu-id="c8d35-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="c8d35-137">I livelli più comuni includono:</span><span class="sxs-lookup"><span data-stu-id="c8d35-137">The most common layers include:</span></span>

- <span data-ttu-id="c8d35-138">Interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c8d35-138">User interface</span></span>
- <span data-ttu-id="c8d35-139">Logica di business</span><span class="sxs-lookup"><span data-stu-id="c8d35-139">Business logic</span></span>
- <span data-ttu-id="c8d35-140">Accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="c8d35-140">Data access</span></span>

<span data-ttu-id="c8d35-141">Altri livelli possono includere middleware, elaborazione batch e API.</span><span class="sxs-lookup"><span data-stu-id="c8d35-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="c8d35-142">È importante notare che i layer sono logici.</span><span class="sxs-lookup"><span data-stu-id="c8d35-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="c8d35-143">Anche se sono sviluppati in isolamento, possono essere tutti distribuiti nella stessa piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c8d35-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![Architettura A N livelli](./media/n-layer-architecture.png)

<span data-ttu-id="c8d35-145">L'approccio N-Layer presenta diversi vantaggi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="c8d35-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="c8d35-146">Il refactoring è isolato in un livello.</span><span class="sxs-lookup"><span data-stu-id="c8d35-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="c8d35-147">I team possono creare, testare, distribuire e gestire livelli separati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c8d35-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="c8d35-148">I layer possono essere scambiati, ad esempio il livello dati può accedere a più database senza richiedere modifiche al livello dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="c8d35-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="c8d35-149">Serverless può essere utilizzato per implementare uno o più livelli.</span><span class="sxs-lookup"><span data-stu-id="c8d35-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="c8d35-150">Microservizi</span><span class="sxs-lookup"><span data-stu-id="c8d35-150">Microservices</span></span>

<span data-ttu-id="c8d35-151">Le architetture di microservizi contengono caratteristiche comuni che **[includono:Microservicess](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contain common characteristics that include:</span><span class="sxs-lookup"><span data-stu-id="c8d35-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="c8d35-152">Le applicazioni sono composte da diversi piccoli servizi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="c8d35-153">Ogni servizio viene eseguito nel proprio processo.</span><span class="sxs-lookup"><span data-stu-id="c8d35-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="c8d35-154">I servizi sono allineati intorno ai domini aziendali.</span><span class="sxs-lookup"><span data-stu-id="c8d35-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="c8d35-155">I servizi comunicano tramite API leggere, in genere usando HTTP come trasporto.</span><span class="sxs-lookup"><span data-stu-id="c8d35-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="c8d35-156">I servizi possono essere distribuiti e aggiornati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="c8d35-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="c8d35-157">I servizi non dipendono da un singolo archivio dati.</span><span class="sxs-lookup"><span data-stu-id="c8d35-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="c8d35-158">Il sistema è progettato tenendo presente un errore e l'app potrebbe comunque essere eseguita anche in caso di errore di alcuni servizi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="c8d35-159">I microservizi non devono essere reciprocamente esclusivi ad altri approcci di architettura.</span><span class="sxs-lookup"><span data-stu-id="c8d35-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="c8d35-160">Ad esempio, un'architettura a più livelli può utilizzare microservizi per il livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="c8d35-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="c8d35-161">È anche possibile implementare microservizi in diversi modi, dalle directory virtuali negli host IIS ai contenitori.</span><span class="sxs-lookup"><span data-stu-id="c8d35-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="c8d35-162">Le caratteristiche dei microservizi li rendono particolarmente ideali per le implementazioni senza server.</span><span class="sxs-lookup"><span data-stu-id="c8d35-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Architettura di microservizi](./media/microservices-architecture.png)

<span data-ttu-id="c8d35-164">I pro delle architetture di microservizi includono:</span><span class="sxs-lookup"><span data-stu-id="c8d35-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="c8d35-165">Il refactoring è spesso isolato in un singolo servizio.</span><span class="sxs-lookup"><span data-stu-id="c8d35-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="c8d35-166">I servizi possono essere aggiornati indipendentemente l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="c8d35-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="c8d35-167">Resilienza ed elasticità possono essere sintonizzate sulle esigenze dei singoli servizi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="c8d35-168">Lo sviluppo può avvenire in parallelo su team e piattaforme diversi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="c8d35-169">È più semplice scrivere test completi per i servizi isolati.</span><span class="sxs-lookup"><span data-stu-id="c8d35-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="c8d35-170">I microservizi sono dotati di sfide proprie, tra cui:</span><span class="sxs-lookup"><span data-stu-id="c8d35-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="c8d35-171">Determinare quali servizi sono disponibili e come chiamarli.</span><span class="sxs-lookup"><span data-stu-id="c8d35-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="c8d35-172">Gestione del ciclo di vita dei servizi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="c8d35-173">Comprendere in che modo i servizi si incastrano nell'applicazione complessiva.</span><span class="sxs-lookup"><span data-stu-id="c8d35-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="c8d35-174">Test completo del sistema delle chiamate effettuate attraverso servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="c8d35-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="c8d35-175">In definitiva ci sono soluzioni per affrontare tutte queste sfide, tra cui attingere ai vantaggi di serverless che vengono discussi più avanti.</span><span class="sxs-lookup"><span data-stu-id="c8d35-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c8d35-176">[Successivo](index.md)
>[precedente](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="c8d35-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
