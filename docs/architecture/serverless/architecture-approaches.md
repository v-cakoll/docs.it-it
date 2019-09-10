---
title: Approcci di architettura-app senza server
description: Introduzione agli approcci di architettura per la creazione di applicazioni aziendali basate su cloud, da architetture a più livelli a senza server.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ee529abd1f6955d4f542464dd9a2380dd663571f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577804"
---
# <a name="architecture-approaches"></a><span data-ttu-id="1323a-103">Approcci all'architettura</span><span class="sxs-lookup"><span data-stu-id="1323a-103">Architecture approaches</span></span>

<span data-ttu-id="1323a-104">Comprendere gli approcci esistenti per l'architettura delle app aziendali consente di chiarire il ruolo svolto da server.</span><span class="sxs-lookup"><span data-stu-id="1323a-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="1323a-105">Ci sono molti approcci e modelli che si sono evoluti oltre decenni di sviluppo del software e hanno tutti i propri vantaggi e svantaggi.</span><span class="sxs-lookup"><span data-stu-id="1323a-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="1323a-106">In molti casi, la soluzione definitiva potrebbe non comportare la scelta di un singolo approccio, ma può integrare diversi approcci.</span><span class="sxs-lookup"><span data-stu-id="1323a-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="1323a-107">Gli scenari di migrazione spesso coinvolgono lo spostamento da un approccio dell'architettura a un altro tramite un approccio ibrido.</span><span class="sxs-lookup"><span data-stu-id="1323a-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="1323a-108">In questo capitolo viene fornita una panoramica dei modelli di architettura logica e fisica per le applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="1323a-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="1323a-109">Modelli di architettura</span><span class="sxs-lookup"><span data-stu-id="1323a-109">Architecture patterns</span></span>

<span data-ttu-id="1323a-110">Le applicazioni aziendali moderne seguono un'ampia gamma di modelli di architettura.</span><span class="sxs-lookup"><span data-stu-id="1323a-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="1323a-111">Questa sezione rappresenta un sondaggio di modelli comuni.</span><span class="sxs-lookup"><span data-stu-id="1323a-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="1323a-112">Gli schemi elencati di seguito non sono necessariamente tutte le procedure consigliate, ma illustrano approcci diversi.</span><span class="sxs-lookup"><span data-stu-id="1323a-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="1323a-113">Per altre informazioni, vedere [Guida all'architettura delle applicazioni di Azure](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="1323a-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="1323a-114">Strutture monolitiche</span><span class="sxs-lookup"><span data-stu-id="1323a-114">Monoliths</span></span>

<span data-ttu-id="1323a-115">Molte applicazioni aziendali seguono uno schema monolitico.</span><span class="sxs-lookup"><span data-stu-id="1323a-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="1323a-116">Le applicazioni legacy vengono spesso implementate come monolitici.</span><span class="sxs-lookup"><span data-stu-id="1323a-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="1323a-117">Nel modello monolitico, tutti i problemi relativi alle applicazioni sono contenuti in una singola distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1323a-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="1323a-118">Tutti gli elementi dall'interfaccia utente alle chiamate al database sono inclusi nella stessa codebase.</span><span class="sxs-lookup"><span data-stu-id="1323a-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Architettura monolitica](./media/monolith-architecture.png)

<span data-ttu-id="1323a-120">L'approccio monolitico presenta diversi vantaggi.</span><span class="sxs-lookup"><span data-stu-id="1323a-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="1323a-121">Spesso è facile estrarre una singola codebase e iniziare a lavorare.</span><span class="sxs-lookup"><span data-stu-id="1323a-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="1323a-122">Il tempo di preparazione della rampa può essere inferiore e la creazione di ambienti di test è semplice quanto fornire una nuova copia.</span><span class="sxs-lookup"><span data-stu-id="1323a-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="1323a-123">Il monolito può essere progettato per includere più componenti e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1323a-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="1323a-124">Sfortunatamente, il modello monolitico tende a suddividere la scalabilità.</span><span class="sxs-lookup"><span data-stu-id="1323a-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="1323a-125">Gli svantaggi principali dell'approccio monolitico includono:</span><span class="sxs-lookup"><span data-stu-id="1323a-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="1323a-126">Difficile lavorare in parallelo nella stessa codebase.</span><span class="sxs-lookup"><span data-stu-id="1323a-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="1323a-127">Qualsiasi modifica, indipendentemente dalla banalità, richiede la distribuzione di una nuova versione dell'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="1323a-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="1323a-128">Il refactoring potrebbe influire sull'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="1323a-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="1323a-129">Spesso l'unica soluzione per la scalabilità consiste nel creare più copie a elevato utilizzo di risorse del monolito.</span><span class="sxs-lookup"><span data-stu-id="1323a-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="1323a-130">Con l'espansione dei sistemi o l'acquisizione di altri sistemi, l'integrazione può essere difficile.</span><span class="sxs-lookup"><span data-stu-id="1323a-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="1323a-131">Potrebbe essere difficile eseguire il test a causa della necessità di configurare l'intero Monolith.</span><span class="sxs-lookup"><span data-stu-id="1323a-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="1323a-132">Il riutilizzo del codice è complesso e spesso le altre app finiscono con le proprie copie di codice.</span><span class="sxs-lookup"><span data-stu-id="1323a-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="1323a-133">Molte aziende si affacciano sul cloud come opportunità per eseguire la migrazione di applicazioni monolitiche e allo stesso tempo effettuare il refactoring a modelli più utilizzabili.</span><span class="sxs-lookup"><span data-stu-id="1323a-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="1323a-134">È comune suddividere i singoli componenti e applicazioni per consentirne la manutenzione, la distribuzione e la scalabilità separatamente.</span><span class="sxs-lookup"><span data-stu-id="1323a-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="1323a-135">Applicazioni a N livelli</span><span class="sxs-lookup"><span data-stu-id="1323a-135">N-Layer applications</span></span>

<span data-ttu-id="1323a-136">Logica dell'applicazione della partizione di applicazione a più livelli in livelli specifici.</span><span class="sxs-lookup"><span data-stu-id="1323a-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="1323a-137">I livelli più comuni includono:</span><span class="sxs-lookup"><span data-stu-id="1323a-137">The most common layers include:</span></span>

* <span data-ttu-id="1323a-138">Interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="1323a-138">User interface</span></span>
* <span data-ttu-id="1323a-139">Logica di business</span><span class="sxs-lookup"><span data-stu-id="1323a-139">Business logic</span></span>
* <span data-ttu-id="1323a-140">Accesso ai dati</span><span class="sxs-lookup"><span data-stu-id="1323a-140">Data access</span></span>

<span data-ttu-id="1323a-141">Altri livelli possono includere middleware, elaborazione batch e API.</span><span class="sxs-lookup"><span data-stu-id="1323a-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="1323a-142">È importante notare che i livelli sono logici.</span><span class="sxs-lookup"><span data-stu-id="1323a-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="1323a-143">Sebbene siano sviluppate in isolamento, possono essere tutte distribuite nella stessa piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1323a-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![Architettura a N livelli](./media/n-layer-architecture.png)

<span data-ttu-id="1323a-145">L'approccio a N livelli presenta diversi vantaggi, tra cui:</span><span class="sxs-lookup"><span data-stu-id="1323a-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="1323a-146">Il refactoring è isolato a un livello.</span><span class="sxs-lookup"><span data-stu-id="1323a-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="1323a-147">I team possono compilare, testare, distribuire e gestire livelli separati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="1323a-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="1323a-148">I livelli possono essere scambiati, ad esempio il livello dati può accedere a più database senza richiedere modifiche al livello dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1323a-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="1323a-149">Il server può essere utilizzato per implementare uno o più livelli.</span><span class="sxs-lookup"><span data-stu-id="1323a-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="1323a-150">Microservizi</span><span class="sxs-lookup"><span data-stu-id="1323a-150">Microservices</span></span>

<span data-ttu-id="1323a-151">Le architetture di **[microservizi](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** contengono caratteristiche comuni che includono:</span><span class="sxs-lookup"><span data-stu-id="1323a-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="1323a-152">Le applicazioni sono costituite da diversi servizi di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="1323a-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="1323a-153">Ogni servizio viene eseguito nel proprio processo.</span><span class="sxs-lookup"><span data-stu-id="1323a-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="1323a-154">I servizi sono allineati intorno ai domini aziendali.</span><span class="sxs-lookup"><span data-stu-id="1323a-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="1323a-155">I servizi comunicano tramite API semplici, in genere tramite HTTP come trasporto.</span><span class="sxs-lookup"><span data-stu-id="1323a-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="1323a-156">I servizi possono essere distribuiti e aggiornati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="1323a-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="1323a-157">I servizi non dipendono da un singolo archivio dati.</span><span class="sxs-lookup"><span data-stu-id="1323a-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="1323a-158">Il sistema è stato progettato in modo anomalo e l'app potrebbe essere ancora in esecuzione anche quando determinati servizi hanno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1323a-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="1323a-159">I microservizi non devono essere reciprocamente esclusivi ad altri approcci di architettura.</span><span class="sxs-lookup"><span data-stu-id="1323a-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="1323a-160">Ad esempio, un'architettura a più livelli può usare microservizi per il livello intermedio.</span><span class="sxs-lookup"><span data-stu-id="1323a-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="1323a-161">È anche possibile implementare i microservizi in diversi modi, dalle directory virtuali negli host IIS ai contenitori.</span><span class="sxs-lookup"><span data-stu-id="1323a-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="1323a-162">Le caratteristiche dei microservizi li rendono particolarmente ideali per le implementazioni senza server.</span><span class="sxs-lookup"><span data-stu-id="1323a-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Architettura di microservizi](./media/microservices-architecture.png)

<span data-ttu-id="1323a-164">I vantaggi delle architetture di microservizi includono:</span><span class="sxs-lookup"><span data-stu-id="1323a-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="1323a-165">Il refactoring è spesso isolato in un singolo servizio.</span><span class="sxs-lookup"><span data-stu-id="1323a-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="1323a-166">I servizi possono essere aggiornati in modo indipendente l'uno dall'altro.</span><span class="sxs-lookup"><span data-stu-id="1323a-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="1323a-167">La resilienza e l'elasticità possono essere ottimizzate in modo da soddisfare le esigenze dei singoli servizi.</span><span class="sxs-lookup"><span data-stu-id="1323a-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="1323a-168">Lo sviluppo può avvenire in parallelo tra diversi team e piattaforme.</span><span class="sxs-lookup"><span data-stu-id="1323a-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="1323a-169">È più facile scrivere test completi per i servizi isolati.</span><span class="sxs-lookup"><span data-stu-id="1323a-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="1323a-170">I microservizi vengono affrontati con le proprie esigenze, tra cui:</span><span class="sxs-lookup"><span data-stu-id="1323a-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="1323a-171">Determinare quali servizi sono disponibili e come chiamarli.</span><span class="sxs-lookup"><span data-stu-id="1323a-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="1323a-172">Gestione del ciclo di vita dei servizi.</span><span class="sxs-lookup"><span data-stu-id="1323a-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="1323a-173">Informazioni sul modo in cui i servizi si integrano nell'applicazione complessiva.</span><span class="sxs-lookup"><span data-stu-id="1323a-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="1323a-174">Test completi del sistema di chiamate effettuate in servizi diversi.</span><span class="sxs-lookup"><span data-stu-id="1323a-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="1323a-175">Infine, esistono soluzioni per risolvere tutti questi problemi, tra cui sfruttare i vantaggi offerti da server senza server descritti in seguito.</span><span class="sxs-lookup"><span data-stu-id="1323a-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1323a-176">[Precedente](index.md)
>[Successivo](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="1323a-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>