---
title: Applicazioni SOA
description: Tenere presente che i contenitori possono essere anche un'opzione di distribuzione utile per le applicazioni SOA.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: ee71873ac15246f979fd2b08d92280ba797ff6ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795402"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="096c7-103">Applicazioni orientate ai servizi</span><span class="sxs-lookup"><span data-stu-id="096c7-103">Service-oriented applications</span></span>

<span data-ttu-id="096c7-104">Service-Oriented Architecture (SOA) è un termine sovrautilizzato che significava molti aspetti diversi a persone diverse.</span><span class="sxs-lookup"><span data-stu-id="096c7-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="096c7-105">Ma come un denominatore comune, SOA significa strutturare l'architettura dell'applicazione scomponendola in diversi servizi (più di frequente come servizi HTTP) che possono essere classificati in diversi tipi, come sottosistemi o, in altri casi, come i livelli.</span><span class="sxs-lookup"><span data-stu-id="096c7-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="096c7-106">Attualmente, è possibile distribuire questi servizi come i contenitori Docker, risolvere i problemi di distribuzione perché tutte le dipendenze sono inclusi nell'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="096c7-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="096c7-107">Tuttavia, quando è necessario scalare orizzontalmente SOA, potrebbero verificarsi problemi se si esegue la distribuzione in base alle singole istanze.</span><span class="sxs-lookup"><span data-stu-id="096c7-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="096c7-108">Questo problema può essere gestito tramite software di clustering o un agente di orchestrazione Docker.</span><span class="sxs-lookup"><span data-stu-id="096c7-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="096c7-109">Esamineremo gli agenti di orchestrazione più dettagliatamente nella sezione successiva, quando si esplorano gli approcci di microservizi.</span><span class="sxs-lookup"><span data-stu-id="096c7-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="096c7-110">I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.</span><span class="sxs-lookup"><span data-stu-id="096c7-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="096c7-111">Alla fine della giornata, le soluzioni di clustering contenitori sono utili per un'architettura SOA tradizionale e per un'architettura di microservizi più avanzata in cui ogni microservizio è proprietario al modello di dati.</span><span class="sxs-lookup"><span data-stu-id="096c7-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="096c7-112">E grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitico condivisi dai servizi SOA.</span><span class="sxs-lookup"><span data-stu-id="096c7-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="096c7-113">Tuttavia, la discussione sulla suddivisione dei dati è esclusivamente sull'architettura e progettazione.</span><span class="sxs-lookup"><span data-stu-id="096c7-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="096c7-114">[Precedente](state-and-data-in-docker-applications.md)
>[Successivo](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="096c7-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
