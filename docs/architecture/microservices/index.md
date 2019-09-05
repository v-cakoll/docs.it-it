---
title: Microservizi .NET. Architettura per le applicazioni .NET incluse in contenitori
description: Architettura dei microservizi .NET per le applicazioni .NET in contenitori | I microservizi sono servizi modulari e distribuibili in modo indipendente. I contenitori Docker (per Linux e Windows) semplificano le attività di distribuzione e test riunendo un servizio e le relative dipendenze in una singola unità che viene quindi eseguita in un ambiente isolato.
ms.date: 01/07/2019
ms.openlocfilehash: 55520153e0b926a97d0384f0b50b4c929f452f19
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2019
ms.locfileid: "70296841"
---
# <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="68a97-105">Microservizi .NET: Architettura per le applicazioni .NET incluse in contenitori</span><span class="sxs-lookup"><span data-stu-id="68a97-105">.NET Microservices: Architecture for Containerized .NET Applications</span></span>

![Copertina](./media/cover-small.png)

<span data-ttu-id="68a97-107">**EDIZIONE v2.2** - aggiornato ad ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="68a97-107">**EDITION v2.2** - Updated to ASP.NET Core 2.2</span></span>

<span data-ttu-id="68a97-108">Questa guida offre un'introduzione allo sviluppo di applicazioni basate su microservizi e alla relativa gestione tramite i contenitori.</span><span class="sxs-lookup"><span data-stu-id="68a97-108">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="68a97-109">Vengono descritti gli approcci alla progettazione e all'implementazione dell'architettura mediante i contenitori di .NET Core e Docker.</span><span class="sxs-lookup"><span data-stu-id="68a97-109">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> 

<span data-ttu-id="68a97-110">Per rendere più semplice iniziare, la guida illustra un'applicazione di riferimento basata su microservizi e inclusa in un contenitore che è possibile esplorare.</span><span class="sxs-lookup"><span data-stu-id="68a97-110">To make it easier to get started, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="68a97-111">L'applicazione di riferimento è disponibile nel repository GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="68a97-111">The reference application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

## <a name="action-links"></a><span data-ttu-id="68a97-112">Collegamenti all'azione</span><span class="sxs-lookup"><span data-stu-id="68a97-112">Action links</span></span>

- <span data-ttu-id="68a97-113">Scaricare questo eBook nel formato preferito: | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-epub) |</span><span class="sxs-lookup"><span data-stu-id="68a97-113">Download this eBook in your format of choice: | [PDF](https://aka.ms/microservicesebook) | [MOBI](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-mobi) | [EPUB](https://www.microsoft.com/net/download/thank-you/microservices-architecture-ebook-epub) |</span></span>

- <span data-ttu-id="68a97-114">Clonare o eseguire il fork dell'applicazione di riferimento [eShopOnContainers su GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span><span class="sxs-lookup"><span data-stu-id="68a97-114">Clone/Fork the reference application [eShopOnContainers on GitHub](https://github.com/dotnet-architecture/eShopOnContainers)</span></span>
 
- <span data-ttu-id="68a97-115">Guardare il [video introduttivo su Channel 9](https://aka.ms/microservices-video)</span><span class="sxs-lookup"><span data-stu-id="68a97-115">Watch the [introductory video on Channel 9](https://aka.ms/microservices-video)</span></span>

- <span data-ttu-id="68a97-116">Ottenere immediatamente informazioni sull'[architettura di microservizi](https://aka.ms/MicroservicesArchitecture)</span><span class="sxs-lookup"><span data-stu-id="68a97-116">Get to know the [Microservices Architecture](https://aka.ms/MicroservicesArchitecture) right away</span></span>

## <a name="introduction"></a><span data-ttu-id="68a97-117">Introduzione</span><span class="sxs-lookup"><span data-stu-id="68a97-117">Introduction</span></span>

<span data-ttu-id="68a97-118">Sempre più spesso nelle aziende vengono usati i contenitori per realizzare risparmi sui costi, risolvere i problemi di distribuzione e migliorare DevOps e operazioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="68a97-118">Enterprises are increasingly realizing cost savings, solving deployment problems, and improving DevOps and production operations by using containers.</span></span> <span data-ttu-id="68a97-119">Microsoft ha introdotto innovazioni dei contenitori per Windows e Linux tramite la creazione di prodotti come il servizio Azure Kubernetes e Azure Service Fabric, oltre che attraverso la collaborazione con aziende leader del settore come Docker, Mesosphere e Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="68a97-119">Microsoft has been releasing container innovations for Windows and Linux by creating products like Azure Kubernetes Service and Azure Service Fabric, and by partnering with industry leaders like Docker, Mesosphere, and Kubernetes.</span></span> <span data-ttu-id="68a97-120">Questi prodotti offrono soluzioni per i contenitori che consentono alle aziende di creare e distribuire le applicazioni con la velocità e la scalabilità del cloud, indipendentemente dalla piattaforma o dagli strumenti scelti.</span><span class="sxs-lookup"><span data-stu-id="68a97-120">These products deliver container solutions that help companies build and deploy applications at cloud speed and scale, whatever their choice of platform or tools.</span></span>

<span data-ttu-id="68a97-121">Docker sta diventando lo standard di fatto nel settore dei contenitori, supportato dai più significativi fornitori negli ecosistemi Windows e Linux</span><span class="sxs-lookup"><span data-stu-id="68a97-121">Docker is becoming the de facto standard in the container industry, supported by the most significant vendors in the Windows and Linux ecosystems.</span></span> <span data-ttu-id="68a97-122">(Microsoft è uno dei principali fornitori cloud che supportano Docker). In futuro, probabilmente Docker sarà presente in qualsiasi data center nel cloud o locale.</span><span class="sxs-lookup"><span data-stu-id="68a97-122">(Microsoft is one of the main cloud vendors supporting Docker.) In the future, Docker will probably be ubiquitous in any datacenter in the cloud or on-premises.</span></span>

<span data-ttu-id="68a97-123">Inoltre, l'architettura dei [microservizi](https://martinfowler.com/articles/microservices.html) sta emergendo come un importante approccio alle applicazioni distribuite di importanza strategica.</span><span class="sxs-lookup"><span data-stu-id="68a97-123">In addition, the [microservices](https://martinfowler.com/articles/microservices.html) architecture is emerging as an important approach for distributed mission-critical applications.</span></span> <span data-ttu-id="68a97-124">In un'architettura basata su microservizi, l'applicazione si basa su una raccolta di servizi che possono essere sviluppati, testati, distribuiti e sottoposti a controllo della versione in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="68a97-124">In a microservice-based architecture, the application is built on a collection of services that can be developed, tested, deployed, and versioned independently.</span></span>

## <a name="about-this-guide"></a><span data-ttu-id="68a97-125">Informazioni sulla guida</span><span class="sxs-lookup"><span data-stu-id="68a97-125">About this guide</span></span>

<span data-ttu-id="68a97-126">Questa guida offre un'introduzione allo sviluppo di applicazioni basate su microservizi e alla relativa gestione tramite i contenitori.</span><span class="sxs-lookup"><span data-stu-id="68a97-126">This guide is an introduction to developing microservices-based applications and managing them using containers.</span></span> <span data-ttu-id="68a97-127">Vengono descritti gli approcci alla progettazione e all'implementazione dell'architettura mediante i contenitori di .NET Core e Docker.</span><span class="sxs-lookup"><span data-stu-id="68a97-127">It discusses architectural design and implementation approaches using .NET Core and Docker containers.</span></span> <span data-ttu-id="68a97-128">Per rendere più semplice iniziare a usare i contenitori e i microservizi, la guida illustra un'applicazione di riferimento basata su microservizi e inclusa in un contenitore che è possibile esplorare.</span><span class="sxs-lookup"><span data-stu-id="68a97-128">To make it easier to get started with containers and microservices, the guide focuses on a reference containerized and microservice-based application that you can explore.</span></span> <span data-ttu-id="68a97-129">L'applicazione di esempio è disponibile nel repository GitHub [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers).</span><span class="sxs-lookup"><span data-stu-id="68a97-129">The sample application is available at the [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub repo.</span></span>

<span data-ttu-id="68a97-130">Questa guida fornisce indicazioni di base per lo sviluppo e l'architettura principalmente a livello di ambiente di sviluppo, con particolare attenzione per due tecnologie: Docker e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68a97-130">This guide provides foundational development and architectural guidance primarily at a development environment level with a focus on two technologies: Docker and .NET Core.</span></span> <span data-ttu-id="68a97-131">La guida dovrebbe essere letta al momento di valutare la progettazione dell'applicazione, senza considerare l'infrastruttura (cloud o locale) dell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="68a97-131">Our intention is that you read this guide when thinking about your application design without focusing on the infrastructure (cloud or on-premises) of your production environment.</span></span> <span data-ttu-id="68a97-132">Sarà possibile prendere le decisioni relative all'infrastruttura in un secondo momento, durante la creazione delle applicazioni di produzione.</span><span class="sxs-lookup"><span data-stu-id="68a97-132">You will make decisions about your infrastructure later, when you create your production-ready applications.</span></span> <span data-ttu-id="68a97-133">Pertanto, questa guida è pensata per essere indipendente dall'infrastruttura e maggiormente incentrata sull'ambiente di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="68a97-133">Therefore, this guide is intended to be infrastructure agnostic and more development-environment-centric.</span></span>

<span data-ttu-id="68a97-134">Dopo aver consultato questa guida, il passaggio successivo sarà acquisire informazioni sui microservizi disponibili per la produzione in Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="68a97-134">After you have studied this guide, your next step would be to learn about production-ready microservices on Microsoft Azure.</span></span>

## <a name="version"></a><span data-ttu-id="68a97-135">Versione</span><span class="sxs-lookup"><span data-stu-id="68a97-135">Version</span></span>

<span data-ttu-id="68a97-136">Questa guida è stata rivista per includere la versione **.NET Core 2.2** e numerosi aggiornamenti aggiuntivi correlati alla stessa "generazione" di tecnologie (ovvero</span><span class="sxs-lookup"><span data-stu-id="68a97-136">This guide has been revised to cover **.NET Core 2.2** version plus many additional updates related to the same “wave” of technologies (that is.</span></span> <span data-ttu-id="68a97-137">Azure e tecnologie aggiuntive di terze parti) in coincidenza con .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68a97-137">Azure and additional 3rd party technologies) coinciding in time with .NET Core 2.2.</span></span> <span data-ttu-id="68a97-138">Per tale motivo anche la versione stampata è stata aggiornata alla versione **2.2**.</span><span class="sxs-lookup"><span data-stu-id="68a97-138">That’s why the book version has also been updated to version **2.2**.</span></span> 

## <a name="what-this-guide-does-not-cover"></a><span data-ttu-id="68a97-139">Argomenti non trattati dalla guida</span><span class="sxs-lookup"><span data-stu-id="68a97-139">What this guide does not cover</span></span>

<span data-ttu-id="68a97-140">Questa guida non tratta gli argomenti relativi a ciclo di vita delle applicazioni, DevOps, pipeline CI/CD o lavoro in team.</span><span class="sxs-lookup"><span data-stu-id="68a97-140">This guide does not focus on the application lifecycle, DevOps, CI/CD pipelines, or team work.</span></span> <span data-ttu-id="68a97-141">La guida complementare [Ciclo di vita delle applicazioni Docker incluse in contenitori con la piattaforma e gli strumenti Microsoft](https://aka.ms/dockerlifecycleebook) è dedicata a tali argomenti.</span><span class="sxs-lookup"><span data-stu-id="68a97-141">The complementary guide [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) focuses on that subject.</span></span> <span data-ttu-id="68a97-142">La presente guida inoltre non contiene i dettagli relativi all'implementazione nell'infrastruttura Azure, ad esempio le informazioni sugli specifici agenti di orchestrazione.</span><span class="sxs-lookup"><span data-stu-id="68a97-142">The current guide also does not provide implementation details on Azure infrastructure, such as information on specific orchestrators.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="68a97-143">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="68a97-143">Additional resources</span></span>

- <span data-ttu-id="68a97-144">**Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft** (e-book scaricabile)</span><span class="sxs-lookup"><span data-stu-id="68a97-144">**Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book)</span></span>  
    <https://aka.ms/dockerlifecycleebook>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="68a97-145">Destinatari della guida</span><span class="sxs-lookup"><span data-stu-id="68a97-145">Who should use this guide</span></span>

<span data-ttu-id="68a97-146">Questa guida è stata scritta per gli sviluppatori e gli architetti di soluzioni che non hanno familiarità con lo sviluppo di applicazioni basate su Docker e l'architettura basata su microservizi.</span><span class="sxs-lookup"><span data-stu-id="68a97-146">We wrote this guide for developers and solution architects who are new to Docker-based application development and to microservices-based architecture.</span></span> <span data-ttu-id="68a97-147">La guida è destinata ai professionisti che vogliono sapere come progettare e implementare applicazioni di prova con le tecnologie di sviluppo Microsoft (con particolare attenzione per .NET Core) e i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="68a97-147">This guide is for you if you want to learn how to architect, design, and implement proof-of-concept applications with Microsoft development technologies (with special focus on .NET Core) and with Docker containers.</span></span>

<span data-ttu-id="68a97-148">Questa guida è inoltre utile per i responsabili decisionali tecnici, ad esempio gli Enterprise Architect, che hanno bisogno di una panoramica dell'architettura e della tecnologia prima di decidere quale approccio scegliere per le applicazioni distribuite nuove e moderne.</span><span class="sxs-lookup"><span data-stu-id="68a97-148">You will also find this guide useful if you are a technical decision maker, such as an enterprise architect, who wants an architecture and technology overview before you decide on what approach to select for new and modern distributed applications.</span></span>

### <a name="how-to-use-this-guide"></a><span data-ttu-id="68a97-149">Come usare questa guida</span><span class="sxs-lookup"><span data-stu-id="68a97-149">How to use this guide</span></span>

<span data-ttu-id="68a97-150">Nella prima parte della guida vengono presentati i contenitori Docker, viene illustrato come scegliere tra .NET Core e .NET Framework come framework di sviluppo e viene fornita una panoramica dei microservizi.</span><span class="sxs-lookup"><span data-stu-id="68a97-150">The first part of this guide introduces Docker containers, discusses how to choose between .NET Core and the .NET Framework as a development framework, and provides an overview of microservices.</span></span> <span data-ttu-id="68a97-151">Questo contenuto è destinato ai progettisti e ai responsabili decisionali tecnici che vogliono una panoramica generale, senza informazioni dettagliate relative all'implementazione del codice.</span><span class="sxs-lookup"><span data-stu-id="68a97-151">This content is for architects and technical decision makers who want an overview but don't need to focus on code implementation details.</span></span>

<span data-ttu-id="68a97-152">La seconda parte della guida inizia con la sezione [Processo di sviluppo per le applicazioni basate su Docker](./docker-application-development-process/index.md).</span><span class="sxs-lookup"><span data-stu-id="68a97-152">The second part of the guide starts with the [Development process for Docker based applications](./docker-application-development-process/index.md) section.</span></span> <span data-ttu-id="68a97-153">Si concentra sullo sviluppo e sui modelli dei microservizi per l'implementazione di applicazioni tramite .NET Core e Docker.</span><span class="sxs-lookup"><span data-stu-id="68a97-153">It focuses on development and microservice patterns for implementing applications using .NET Core and Docker.</span></span> <span data-ttu-id="68a97-154">Questa sezione sarà di particolare interesse per gli sviluppatori e i progettisti che vogliono concentrarsi sul codice e sui dettagli relativi a modelli e implementazione.</span><span class="sxs-lookup"><span data-stu-id="68a97-154">This section will be of most interest to developers and architects who want to focus on code and on patterns and implementation details.</span></span>

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a><span data-ttu-id="68a97-155">Applicazione di riferimento correlata basata su microservizi e contenitori: eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="68a97-155">Related microservice and container-based reference application: eShopOnContainers</span></span>

<span data-ttu-id="68a97-156">L'applicazione eShopOnContainers è un'applicazione open-source di riferimento per .NET Core e i microservizi, progettata per la distribuzione mediante i contenitori Docker.</span><span class="sxs-lookup"><span data-stu-id="68a97-156">The eShopOnContainers application is an open-source reference app for .NET Core and microservices that is designed to be deployed using Docker containers.</span></span> <span data-ttu-id="68a97-157">L'applicazione è costituita da più sottosistemi, inclusi diversi front-end con interfaccia utente per negozi online (un'app Web MVC, un'applicazione Web a pagina singola e un'app per dispositivi mobili nativa).</span><span class="sxs-lookup"><span data-stu-id="68a97-157">The application consists of multiple subsystems, including several e-store UI front ends (a Web MVC app, a Web SPA, and a native mobile app).</span></span> <span data-ttu-id="68a97-158">Include inoltre i microservizi e i contenitori back-end per tutte le operazioni lato server necessarie.</span><span class="sxs-lookup"><span data-stu-id="68a97-158">It also includes the back-end microservices and containers for all required server-side operations.</span></span> 

<span data-ttu-id="68a97-159">Lo scopo dell'applicazione consiste nel presentare i modelli di architettura.</span><span class="sxs-lookup"><span data-stu-id="68a97-159">The purpose of the application is to showcase architectural patterns.</span></span> <span data-ttu-id="68a97-160">**NON È UN MODELLO DA USARE IN PRODUZIONE** per avviare applicazioni reali.</span><span class="sxs-lookup"><span data-stu-id="68a97-160">**IT IS NOT A PRODUCTION-READY TEMPLATE** to start real-world applications.</span></span> <span data-ttu-id="68a97-161">Di fatto, l'applicazione è in uno stato beta permanente, perché viene usata anche per testare le nuove tecnologie potenzialmente interessanti quando diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="68a97-161">In fact, the application is in a permanent beta state, as it’s also used to test new potentially interesting technologies as they show up.</span></span>

## <a name="send-us-your-feedback"></a><span data-ttu-id="68a97-162">Inviateci i vostri commenti!</span><span class="sxs-lookup"><span data-stu-id="68a97-162">Send us your feedback!</span></span>

<span data-ttu-id="68a97-163">Questa guida è stata scritta per aiutare il lettore a comprendere l'architettura delle applicazioni incluse in contenitori e dei microservizi in .NET.</span><span class="sxs-lookup"><span data-stu-id="68a97-163">We wrote this guide to help you understand the architecture of containerized applications and microservices in .NET.</span></span> <span data-ttu-id="68a97-164">La guida e l'applicazione di riferimento correlata sono in evoluzione, pertanto qualsiasi commento è molto apprezzato.</span><span class="sxs-lookup"><span data-stu-id="68a97-164">The guide and related reference application will be evolving, so we welcome your feedback!</span></span> <span data-ttu-id="68a97-165">È possibile inviare eventuali commenti su come migliorare la guida all'indirizzo:</span><span class="sxs-lookup"><span data-stu-id="68a97-165">If you have comments about how this guide can be improved, please send them to:</span></span>

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

## <a name="credits"></a><span data-ttu-id="68a97-166">Crediti</span><span class="sxs-lookup"><span data-stu-id="68a97-166">Credits</span></span>

<span data-ttu-id="68a97-167">Coautori:</span><span class="sxs-lookup"><span data-stu-id="68a97-167">Co-Authors:</span></span>

> <span data-ttu-id="68a97-168">**Cesar de la Torre**, Senior PM, team del prodotto .NET, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="68a97-168">**Cesar de la Torre**, Sr. PM, .NET product team, Microsoft Corp.</span></span>
>
> <span data-ttu-id="68a97-169">**Bill Wagner**, Senior Content Developer, C+E, Microsoft Corp.</span><span class="sxs-lookup"><span data-stu-id="68a97-169">**Bill Wagner**, Sr. Content Developer, C+E, Microsoft Corp.</span></span>
>
> <span data-ttu-id="68a97-170">**Mike Rousos**, Principal Software Engineer, team DevDiv CAT, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-170">**Mike Rousos**, Principal Software Engineer, DevDiv CAT team, Microsoft</span></span>

<span data-ttu-id="68a97-171">Editor:</span><span class="sxs-lookup"><span data-stu-id="68a97-171">Editors:</span></span>

> <span data-ttu-id="68a97-172">**Mike Pope**</span><span class="sxs-lookup"><span data-stu-id="68a97-172">**Mike Pope**</span></span>
>
> <span data-ttu-id="68a97-173">**Steve Hoag**</span><span class="sxs-lookup"><span data-stu-id="68a97-173">**Steve Hoag**</span></span>

<span data-ttu-id="68a97-174">Collaboratori e revisori:</span><span class="sxs-lookup"><span data-stu-id="68a97-174">Participants and reviewers:</span></span>

> <span data-ttu-id="68a97-175">**Jeffrey Richter**, Partner Software Eng, team di Azure, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-175">**Jeffrey Richter**, Partner Software Eng, Azure team, Microsoft</span></span>
>
> <span data-ttu-id="68a97-176">**Jimmy Bogard**, Chief Architect di Headspring</span><span class="sxs-lookup"><span data-stu-id="68a97-176">**Jimmy Bogard**, Chief Architect at Headspring</span></span>
>
> <span data-ttu-id="68a97-177">**Udi Dahan**, fondatore e CEO di Particular Software</span><span class="sxs-lookup"><span data-stu-id="68a97-177">**Udi Dahan**, Founder & CEO, Particular Software</span></span>
>
> <span data-ttu-id="68a97-178">**Jimmy Nilsson**, cofondatore e CEO di Factor10</span><span class="sxs-lookup"><span data-stu-id="68a97-178">**Jimmy Nilsson**, Co-founder and CEO of Factor10</span></span>
>
> <span data-ttu-id="68a97-179">**Glenn Condron**, Senior Program Manager, team di ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68a97-179">**Glenn Condron**, Sr. Program Manager, ASP.NET team</span></span>
>
> <span data-ttu-id="68a97-180">**Mark Fussell**, Principal PM Lead, team di Azure Service Fabric, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-180">**Mark Fussell**, Principal PM Lead, Azure Service Fabric team, Microsoft</span></span>
>
> <span data-ttu-id="68a97-181">**Diego Vega**, PM Lead, team di Entity Framework, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-181">**Diego Vega**, PM Lead, Entity Framework team, Microsoft</span></span>
>
> <span data-ttu-id="68a97-182">**Barry Dorrans**, Senior Security Program Manager</span><span class="sxs-lookup"><span data-stu-id="68a97-182">**Barry Dorrans**, Sr. Security Program Manager</span></span>
>
> <span data-ttu-id="68a97-183">**Rowan Miller**, Senior Program Manager, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-183">**Rowan Miller**, Sr. Program Manager, Microsoft</span></span>
>
> <span data-ttu-id="68a97-184">**Ankit Asthana**, Principal PM Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-184">**Ankit Asthana**, Principal PM Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="68a97-185">**Scott Hunter**, Partner Director PM, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-185">**Scott Hunter**, Partner Director PM, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="68a97-186">**Nish Anil**, Senior Program Manager, team di .NET, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-186">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="68a97-187">**Dylan Reisenberger**, Architect and Dev Lead di Polly</span><span class="sxs-lookup"><span data-stu-id="68a97-187">**Dylan Reisenberger**, Architect and Dev Lead at Polly</span></span>
>
> <span data-ttu-id="68a97-188">**Steve "ardalis" Smith** - Software Architect e Trainer - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="68a97-188">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="68a97-189">**Ian Cooper**, Coding Architect di Brighter</span><span class="sxs-lookup"><span data-stu-id="68a97-189">**Ian Cooper**, Coding Architect at Brighter</span></span>
>
> <span data-ttu-id="68a97-190">**Unai Zorrilla**, Architect and Dev Lead di Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="68a97-190">**Unai Zorrilla**, Architect and Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="68a97-191">**Eduard Tomas**, Dev Lead di Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="68a97-191">**Eduard Tomas**, Dev Lead at Plain Concepts</span></span>
>
> <span data-ttu-id="68a97-192">**Ramon Tomas**, sviluppatore di Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="68a97-192">**Ramon Tomas**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="68a97-193">**David Sanz**, sviluppatore di Plain Concepts</span><span class="sxs-lookup"><span data-stu-id="68a97-193">**David Sanz**, Developer at Plain Concepts</span></span>
>
> <span data-ttu-id="68a97-194">**Javier Valero**, Chief Operating Officer di Grupo Solutio</span><span class="sxs-lookup"><span data-stu-id="68a97-194">**Javier Valero**, Chief Operating Officer at Grupo Solutio</span></span>
>
> <span data-ttu-id="68a97-195">**Pierre Millet**, Senior Consultant, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-195">**Pierre Millet**, Sr. Consultant, Microsoft</span></span>
>
> <span data-ttu-id="68a97-196">**Michael Friis**, Product Manager, Docker Inc</span><span class="sxs-lookup"><span data-stu-id="68a97-196">**Michael Friis**, Product Manager, Docker Inc</span></span>
>
> <span data-ttu-id="68a97-197">**Charles Lowell**, Software Engineer, team VS CAT, Microsoft</span><span class="sxs-lookup"><span data-stu-id="68a97-197">**Charles Lowell**, Software Engineer, VS CAT team, Microsoft</span></span>
>
> <span data-ttu-id="68a97-198">**Miguel Veloso**, Senior Consultant, Turing Challenge</span><span class="sxs-lookup"><span data-stu-id="68a97-198">**Miguel Veloso**, Sr. Consultant at Turing Challenge</span></span>

## <a name="copyright"></a><span data-ttu-id="68a97-199">Copyright</span><span class="sxs-lookup"><span data-stu-id="68a97-199">Copyright</span></span>

<span data-ttu-id="68a97-200">Download disponibile all'indirizzo: <https://aka.ms/microservicesebook></span><span class="sxs-lookup"><span data-stu-id="68a97-200">DOWNLOAD available at: <https://aka.ms/microservicesebook></span></span>

<span data-ttu-id="68a97-201">PUBBLICATO DA</span><span class="sxs-lookup"><span data-stu-id="68a97-201">PUBLISHED BY</span></span>

<span data-ttu-id="68a97-202">Microsoft Developer Division, team dei prodotti .NET e Visual Studio</span><span class="sxs-lookup"><span data-stu-id="68a97-202">Microsoft Developer Division, .NET and Visual Studio product teams</span></span>

<span data-ttu-id="68a97-203">Una divisione di Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="68a97-203">A division of Microsoft Corporation</span></span>

<span data-ttu-id="68a97-204">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="68a97-204">One Microsoft Way</span></span>

<span data-ttu-id="68a97-205">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="68a97-205">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="68a97-206">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="68a97-206">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="68a97-207">Tutti i diritti sono riservati.</span><span class="sxs-lookup"><span data-stu-id="68a97-207">All rights reserved.</span></span> <span data-ttu-id="68a97-208">Nessuna parte del contenuto di questo libro può essere riprodotta o trasmessa in qualsiasi forma o con qualsiasi mezzo, senza il permesso scritto dell'editore.</span><span class="sxs-lookup"><span data-stu-id="68a97-208">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="68a97-209">Questo libro viene fornito "così com'è" ed esprime i punti di vista e le opinioni dell'autore.</span><span class="sxs-lookup"><span data-stu-id="68a97-209">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="68a97-210">I punti di vista, le opinioni e le informazioni contenute nel presente libro, inclusi gli URL e altri riferimenti a siti Web, possono essere soggetti a modifiche senza preavviso.</span><span class="sxs-lookup"><span data-stu-id="68a97-210">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="68a97-211">Alcuni esempi contenuti nella presente guida vengono forniti solo a fini illustrativi e sono fittizi.</span><span class="sxs-lookup"><span data-stu-id="68a97-211">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="68a97-212">Nessuna associazione o connessione reale è intenzionale o può essere presupposta.</span><span class="sxs-lookup"><span data-stu-id="68a97-212">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="68a97-213">Microsoft e i marchi elencati nella pagina Web relativa ai marchi all'indirizzo <https://www.microsoft.com> sono marchi delle società del gruppo Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68a97-213">Microsoft and the trademarks listed at <https://www.microsoft.com> on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="68a97-214">Mac e macOS sono marchi registrati di Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="68a97-214">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="68a97-215">Il logo Docker con la balena è un marchio registrato di Docker, Inc. Usato su autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="68a97-215">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="68a97-216">Tutti gli altri marchi e logo appartengono ai rispettivi proprietari.</span><span class="sxs-lookup"><span data-stu-id="68a97-216">All other marks and logos are property of their respective owners.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="68a97-217">avanti</span><span class="sxs-lookup"><span data-stu-id="68a97-217">Next</span></span>](container-docker-introduction/index.md)
