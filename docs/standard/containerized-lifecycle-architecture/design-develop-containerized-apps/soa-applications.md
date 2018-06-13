---
title: Applicazioni SOA
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 37313c4eb437b6b7a362456a7d1ee3b3aecb6020
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569425"
---
# <a name="soa-applications"></a><span data-ttu-id="6362f-103">Applicazioni SOA</span><span class="sxs-lookup"><span data-stu-id="6362f-103">SOA applications</span></span>

<span data-ttu-id="6362f-104">SOA è un termine eccessivo e deve moltissime operazioni diverse a seconda degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6362f-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="6362f-105">Ma minimo e un denominatore comune, SOA, o orientamento ai servizi, Media, si struttura l'architettura dell'applicazione scomponendo in più servizi (più di frequente, come i servizi HTTP) che possono essere classificati in diversi tipi come sottosistemi In alternativa, in altri casi, come livelli.</span><span class="sxs-lookup"><span data-stu-id="6362f-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="6362f-106">Oggi, è possibile distribuire i servizi come contenitori di Docker, che risolve i problemi di distribuzione in quanto tutte le dipendenze sono incluse nell'immagine contenitore.</span><span class="sxs-lookup"><span data-stu-id="6362f-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="6362f-107">Tuttavia, quando è necessario eseguire la scalabilità SOA, potrebbero verificarsi problemi se si distribuisce in base alle singole istanze.</span><span class="sxs-lookup"><span data-stu-id="6362f-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="6362f-108">Si tratta in cui una Docker software di clustering o orchestrator consentono.</span><span class="sxs-lookup"><span data-stu-id="6362f-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="6362f-109">Verrà esaminato questo più dettagliatamente nella sezione successiva quando si esaminano gli approcci di microservizi.</span><span class="sxs-lookup"><span data-stu-id="6362f-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="6362f-110">Alla fine del giorno, le soluzioni di clustering contenitore sono utili per un'architettura SOA tradizionale o per un'architettura di microservizi più avanzata in cui ogni microservizio appartiene il modello di dati.</span><span class="sxs-lookup"><span data-stu-id="6362f-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="6362f-111">E, grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitici condivisi dai servizi SOA.</span><span class="sxs-lookup"><span data-stu-id="6362f-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="6362f-112">Tuttavia, la discussione sulla divisione dei dati è esclusivamente sull'architettura e progettazione.</span><span class="sxs-lookup"><span data-stu-id="6362f-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="6362f-113">[Precedente] [Avanti] (orchestrare-elevata-scalabilità-availability.md) (state-and-data-in-docker-applications.md)</span><span class="sxs-lookup"><span data-stu-id="6362f-113">[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)</span></span>
