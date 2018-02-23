---
title: Architettura orientata ai servizi
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Architettura orientata ai servizi
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
ms.openlocfilehash: 6a5f0f53f4208c9944adea33fe1aa3f35fed81ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="08c0e-104">Architettura orientata ai servizi</span><span class="sxs-lookup"><span data-stu-id="08c0e-104">Service-oriented architecture</span></span> 

<span data-ttu-id="08c0e-105">Architettura orientata ai servizi è un termine molto usato che può avere significati diversi a seconda delle persone.</span><span class="sxs-lookup"><span data-stu-id="08c0e-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="08c0e-106">In generale, architettura orientata ai servizi significa strutturare l'applicazione scomponendola in più servizio (comunemente servizi HTTP) che possono essere classificati in diversi tipi, come sottosistemi o livelli.</span><span class="sxs-lookup"><span data-stu-id="08c0e-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="08c0e-107">Tali servizi possono ora essere distribuiti come contenitori Docker per risolvere alcuni problemi di distribuzione, poiché tutte le dipendenze sono incluse nell'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="08c0e-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="08c0e-108">Tuttavia, se è necessario ridimensionare le applicazioni con architettura orientata ai servizi per aumentarne le prestazioni, è possibile riscontrare problematiche di scalabilità e disponibilità se la distribuzione è basata su host Docker singoli.</span><span class="sxs-lookup"><span data-stu-id="08c0e-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="08c0e-109">In questo caso, è opportuno usare il software di clustering Docker o un agente di orchestrazione, come illustrato nelle sezioni successive dove vengono descritti gli approcci di distribuzione per i microservizi.</span><span class="sxs-lookup"><span data-stu-id="08c0e-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="08c0e-110">I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.</span><span class="sxs-lookup"><span data-stu-id="08c0e-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="08c0e-111">I microservizi derivano dall'architettura orientata ai servizi, ma quest'ultima è diversa dall'architettura di microservizi.</span><span class="sxs-lookup"><span data-stu-id="08c0e-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="08c0e-112">I broker centralizzati di grandi dimensioni, gli agenti di orchestrazione centralizzati a livello dell'organizzazione e il [bus di servizio aziendale](https://en.wikipedia.org/wiki/Enterprise_service_bus) (ESB, Enterprise Service Bus) sono funzionalità tipiche dell'architettura orientata ai servizi.</span><span class="sxs-lookup"><span data-stu-id="08c0e-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="08c0e-113">Ma nella maggior parte dei casi, sono considerate come antipattern nella community dei microservizi.</span><span class="sxs-lookup"><span data-stu-id="08c0e-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="08c0e-114">Infatti, alcuni sostengono che l'"architettura di microservizi non è altro che un'architettura orientata ai servizi".</span><span class="sxs-lookup"><span data-stu-id="08c0e-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="08c0e-115">Questa guida fa riferimento ai microservizi, in quanto l'approccio dell'architettura orientato ai servizi è meno rigoroso rispetto ai requisiti e alle tecniche usati in un'architettura di microservizi.</span><span class="sxs-lookup"><span data-stu-id="08c0e-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="08c0e-116">Se si è in grado di creare un'applicazione basata su microservizi, si riuscirà anche a creare una più semplice applicazione orientata ai servizi.</span><span class="sxs-lookup"><span data-stu-id="08c0e-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="08c0e-117">[Indietro] (docker-application-state-data.md) [Avanti] (microservices-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="08c0e-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
