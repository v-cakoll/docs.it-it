---
title: Architettura orientata ai servizi
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Architettura orientata ai servizi
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 67560cc93b3d147be36a691af440bb78f2315557
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105005"
---
# <a name="service-oriented-architecture"></a><span data-ttu-id="89715-103">Architettura orientata ai servizi</span><span class="sxs-lookup"><span data-stu-id="89715-103">Service-oriented architecture</span></span> 

<span data-ttu-id="89715-104">Architettura orientata ai servizi è un termine molto usato che può avere significati diversi a seconda delle persone.</span><span class="sxs-lookup"><span data-stu-id="89715-104">Service-oriented architecture (SOA) was an overused term and has meant different things to different people.</span></span> <span data-ttu-id="89715-105">In generale, architettura orientata ai servizi significa strutturare l'applicazione scomponendola in più servizio (comunemente servizi HTTP) che possono essere classificati in diversi tipi, come sottosistemi o livelli.</span><span class="sxs-lookup"><span data-stu-id="89715-105">But as a common denominator, SOA means that you structure your application by decomposing it into multiple services (most commonly as HTTP services) that can be classified as different types like subsystems or tiers.</span></span>

<span data-ttu-id="89715-106">Tali servizi possono ora essere distribuiti come contenitori Docker per risolvere alcuni problemi di distribuzione, poiché tutte le dipendenze sono incluse nell'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="89715-106">Those services can now be deployed as Docker containers, which solves deployment issues, because all the dependencies are included in the container image.</span></span> <span data-ttu-id="89715-107">Tuttavia, se è necessario ridimensionare le applicazioni con architettura orientata ai servizi per aumentarne le prestazioni, è possibile riscontrare problematiche di scalabilità e disponibilità se la distribuzione è basata su host Docker singoli.</span><span class="sxs-lookup"><span data-stu-id="89715-107">However, when you need to scale up SOA applications, you might have scalability and availability challenges if you are deploying based on single Docker hosts.</span></span> <span data-ttu-id="89715-108">In questo caso, è opportuno usare il software di clustering Docker o un agente di orchestrazione, come illustrato nelle sezioni successive dove vengono descritti gli approcci di distribuzione per i microservizi.</span><span class="sxs-lookup"><span data-stu-id="89715-108">This is where Docker clustering software or an orchestrator will help you out, as explained in later sections where we describe deployment approaches for microservices.</span></span>

<span data-ttu-id="89715-109">I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.</span><span class="sxs-lookup"><span data-stu-id="89715-109">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="89715-110">I microservizi derivano dall'architettura orientata ai servizi, ma quest'ultima è diversa dall'architettura di microservizi.</span><span class="sxs-lookup"><span data-stu-id="89715-110">Microservices derive from SOA, but SOA is different from microservices architecture.</span></span> <span data-ttu-id="89715-111">I broker centralizzati di grandi dimensioni, gli agenti di orchestrazione centralizzati a livello dell'organizzazione e il [bus di servizio aziendale](https://en.wikipedia.org/wiki/Enterprise_service_bus) (ESB, Enterprise Service Bus) sono funzionalità tipiche dell'architettura orientata ai servizi.</span><span class="sxs-lookup"><span data-stu-id="89715-111">Features like big central brokers, central orchestrators at the organization level, and the [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) are typical in SOA.</span></span> <span data-ttu-id="89715-112">Ma nella maggior parte dei casi, sono considerate come antipattern nella community dei microservizi.</span><span class="sxs-lookup"><span data-stu-id="89715-112">But in most cases, these are anti-patterns in the microservice community.</span></span> <span data-ttu-id="89715-113">Infatti, alcuni sostengono che l'"architettura di microservizi non è altro che un'architettura orientata ai servizi".</span><span class="sxs-lookup"><span data-stu-id="89715-113">In fact, some people argue that “The microservice architecture is SOA done right.”</span></span>

<span data-ttu-id="89715-114">Questa guida fa riferimento ai microservizi, in quanto l'approccio dell'architettura orientato ai servizi è meno rigoroso rispetto ai requisiti e alle tecniche usati in un'architettura di microservizi.</span><span class="sxs-lookup"><span data-stu-id="89715-114">This guide focuses on microservices, because a SOA approach is less prescriptive than the requirements and techniques used in a microservice architecture.</span></span> <span data-ttu-id="89715-115">Se si è in grado di creare un'applicazione basata su microservizi, si riuscirà anche a creare una più semplice applicazione orientata ai servizi.</span><span class="sxs-lookup"><span data-stu-id="89715-115">If you know how to build a microservice-based application, you also know how to build a simpler service-oriented application.</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="89715-116">[Precedente](docker-application-state-data.md)
[Successivo](microservices-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="89715-116">[Previous](docker-application-state-data.md)
[Next](microservices-architecture.md)</span></span>
