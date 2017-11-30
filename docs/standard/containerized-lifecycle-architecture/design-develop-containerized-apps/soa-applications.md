---
title: Applicazioni SOA
description: Ciclo di vita dell'applicazione nei contenitori Docker con strumenti e piattaforma Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 92a69ccd18759be3b319395d8609d65bb6d3e1b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="soa-applications"></a><span data-ttu-id="81c34-104">Applicazioni SOA</span><span class="sxs-lookup"><span data-stu-id="81c34-104">SOA applications</span></span>

<span data-ttu-id="81c34-105">SOA è un termine eccessivo e deve moltissime operazioni diverse a seconda degli utenti.</span><span class="sxs-lookup"><span data-stu-id="81c34-105">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="81c34-106">Ma minimo e un denominatore comune, SOA, o orientamento ai servizi, Media, si struttura l'architettura dell'applicazione scomponendo in più servizi (più di frequente, come i servizi HTTP) che possono essere classificati in diversi tipi come sottosistemi In alternativa, in altri casi, come livelli.</span><span class="sxs-lookup"><span data-stu-id="81c34-106">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="81c34-107">Oggi, è possibile distribuire i servizi come contenitori di Docker, che risolve i problemi di distribuzione in quanto tutte le dipendenze sono incluse nell'immagine contenitore.</span><span class="sxs-lookup"><span data-stu-id="81c34-107">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="81c34-108">Tuttavia, quando è necessario eseguire la scalabilità SOA, potrebbero verificarsi problemi se si distribuisce in base alle singole istanze.</span><span class="sxs-lookup"><span data-stu-id="81c34-108">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="81c34-109">Si tratta in cui una Docker software di clustering o orchestrator consentono.</span><span class="sxs-lookup"><span data-stu-id="81c34-109">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="81c34-110">Verrà esaminato questo più dettagliatamente nella sezione successiva quando si esaminano gli approcci di microservizi.</span><span class="sxs-lookup"><span data-stu-id="81c34-110">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="81c34-111">Alla fine del giorno, le soluzioni di clustering contenitore sono utili per un'architettura SOA tradizionale o per un'architettura di microservizi più avanzata in cui ogni microservizio appartiene il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="81c34-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="81c34-112">E, grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitici condivisi dai servizi SOA.</span><span class="sxs-lookup"><span data-stu-id="81c34-112">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="81c34-113">Tuttavia, la discussione sulla divisione dei dati è esclusivamente sull'architettura e progettazione.</span><span class="sxs-lookup"><span data-stu-id="81c34-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="81c34-114">[Precedente] [Avanti] (orchestrare-elevata-scalabilità-availability.md) (state-and-data-in-docker-applications.md)</span><span class="sxs-lookup"><span data-stu-id="81c34-114">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>
