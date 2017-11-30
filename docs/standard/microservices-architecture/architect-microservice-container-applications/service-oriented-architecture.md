---
title: Architettura orientata ai servizi
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Architettura orientata ai servizi
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 970ff86c77100077d4c7710c0a697d1745d35819
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="5491c-104">Architettura orientata ai servizi</span><span class="sxs-lookup"><span data-stu-id="5491c-104">Service-oriented architecture</span></span> 

<span data-ttu-id="5491c-105">Architettura orientata ai servizi (SOA) è un termine eccessivo e mira diversi significati a seconda degli utenti.</span><span class="sxs-lookup"><span data-stu-id="5491c-105">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="5491c-106">Ma come denominatore comune, significa che è strutturare l'applicazione scomponendo in più servizi (più di frequente, come i servizi HTTP) che possono essere classificati come tipi diversi, ad esempio i sottosistemi o livelli di SOA.</span><span class="sxs-lookup"><span data-stu-id="5491c-106">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="5491c-107">Tali servizi possono ora essere distribuiti come contenitori di Docker, che risolve i problemi di distribuzione, poiché tutte le dipendenze sono inclusi nell'immagine contenitore.</span><span class="sxs-lookup"><span data-stu-id="5491c-107">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="5491c-108">Tuttavia, quando è necessario applicare la scalabilità verticale applicazioni SOA, potrebbe essere la scalabilità e problemi di disponibilità, se si distribuisce in base a singolo host Docker.</span><span class="sxs-lookup"><span data-stu-id="5491c-108">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="5491c-109">Si tratta in Docker software di clustering o agente di orchestrazione consentirà out, come illustrato nelle sezioni successive in cui vengono descritti gli approcci di distribuzione per microservizi.</span><span class="sxs-lookup"><span data-stu-id="5491c-109">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="5491c-110">I contenitori di docker sono utili, ma non obbligatorio, per le architetture orientate ai servizi tradizionali e le architetture di microservizi più avanzate.</span><span class="sxs-lookup"><span data-stu-id="5491c-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="5491c-111">Microservizi derivano da SOA, ma è diversa dall'architettura di microservizi SOA.</span><span class="sxs-lookup"><span data-stu-id="5491c-111">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="5491c-112">Funzionalità quali grande Broker centrale, orchestrators centrale a livello di organizzazione e [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) sono tipici di SOA.</span><span class="sxs-lookup"><span data-stu-id="5491c-112">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="5491c-113">Ma nella maggior parte dei casi, si tratta di anti-pattern della community di microservizio.</span><span class="sxs-lookup"><span data-stu-id="5491c-113">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="5491c-114">Infatti, alcuni utenti sostengono che "l'architettura del microservizio è SOA eseguita right".</span><span class="sxs-lookup"><span data-stu-id="5491c-114">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="5491c-115">Questa guida è incentrata su microservizi, poiché un approccio SOA è meno rigorosa rispetto i requisiti e le tecniche utilizzate in un'architettura microservizio.</span><span class="sxs-lookup"><span data-stu-id="5491c-115">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="5491c-116">Se si conosce come compilare un'applicazione basata su microservizio, è inoltre necessario conoscere come compilare un'applicazione orientata ai servizi più semplice.</span><span class="sxs-lookup"><span data-stu-id="5491c-116">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="5491c-117">[Precedente] (docker-applicazione-stato-data.md) [Avanti] (microservizi architecture.md)</span><span class="sxs-lookup"><span data-stu-id="5491c-117">[Previous] (docker-application-state-data.md) [Next] (microservices-architecture.md)</span></span>
