---
title: Applicazioni SOA
description: Tenere presente che i contenitori possono essere anche un'opzione di distribuzione utile per le applicazioni SOA.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: 4fd39e075c5730cf7fddb0138cdb5267a914c91f
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221264"
---
# <a name="soa-applications"></a><span data-ttu-id="51028-103">Applicazioni SOA</span><span class="sxs-lookup"><span data-stu-id="51028-103">SOA applications</span></span>

<span data-ttu-id="51028-104">SOA è un termine sovrautilizzato e genere così tante cose diversi a persone diverse.</span><span class="sxs-lookup"><span data-stu-id="51028-104">SOA was an overused term and meant so many different things to different people.</span></span> <span data-ttu-id="51028-105">Ma come minimo e un denominatore comune, SOA, o l'orientamento ai servizi, Media è struttura l'architettura dell'applicazione scomponendola in più servizi (più di frequente come servizi HTTP) che possono essere classificati in diversi tipi, ad esempio sottosistemi In alternativa, in altri casi, come livelli.</span><span class="sxs-lookup"><span data-stu-id="51028-105">But at a minimum and as a common denominator, SOA, or service orientation, mean that you structure the architecture of your application by decomposing it in multiple services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="51028-106">Oggi, è possibile distribuire questi servizi come contenitori Docker, che consente di risolvere i problemi di distribuzione perché tutte le dipendenze sono incluse nell'immagine del contenitore.</span><span class="sxs-lookup"><span data-stu-id="51028-106">Today, you can deploy those services as Docker containers, which solves deployment-related issues because all of the dependencies are included within the container image.</span></span> <span data-ttu-id="51028-107">Tuttavia, quando è necessario eseguire la scalabilità orizzontale SOA, potrebbero verificarsi problemi se si esegue la distribuzione in base alle singole istanze.</span><span class="sxs-lookup"><span data-stu-id="51028-107">However, when you need to scale-out SOAs, you might encounter challenges if you are deploying based on single instances.</span></span> <span data-ttu-id="51028-108">Si tratta in cui un software di clustering o dell'agente di orchestrazione di Docker consente di.</span><span class="sxs-lookup"><span data-stu-id="51028-108">This is where a Docker clustering software or orchestrator will help you.</span></span> <span data-ttu-id="51028-109">Esamineremo questo più dettagliatamente nella sezione successiva quando si esaminano gli approcci di microservizi.</span><span class="sxs-lookup"><span data-stu-id="51028-109">We'll look at this in greater detail in the next section when we examine microservices approaches.</span></span>

<span data-ttu-id="51028-110">Alla fine della giornata, le soluzioni di clustering contenitori sono utili per un'architettura SOA tradizionale o per un'architettura di microservizi più avanzata in cui ogni microservizio è proprietario al modello di dati.</span><span class="sxs-lookup"><span data-stu-id="51028-110">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture or for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="51028-111">E, grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitico condivisi dai servizi SOA.</span><span class="sxs-lookup"><span data-stu-id="51028-111">And, thanks to multiple databases, you also can scale-out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="51028-112">Tuttavia, la discussione sulla suddivisione dei dati è esclusivamente sull'architettura e progettazione.</span><span class="sxs-lookup"><span data-stu-id="51028-112">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="51028-113">[Precedente](state-and-data-in-docker-applications.md)
>[Successivo](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="51028-113">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>