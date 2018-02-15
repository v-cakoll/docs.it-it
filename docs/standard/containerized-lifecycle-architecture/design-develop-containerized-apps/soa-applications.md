---
title: Applicazioni SOA
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 81d2b60303e051568b664ec20225d835a09187c0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="soa-applications"></a>Applicazioni SOA

SOA è un termine eccessivo e deve moltissime operazioni diverse a seconda degli utenti. Ma minimo e un denominatore comune, SOA, o orientamento ai servizi, Media, si struttura l'architettura dell'applicazione scomponendo in più servizi (più di frequente, come i servizi HTTP) che possono essere classificati in diversi tipi come sottosistemi In alternativa, in altri casi, come livelli.

Oggi, è possibile distribuire i servizi come contenitori di Docker, che risolve i problemi di distribuzione in quanto tutte le dipendenze sono incluse nell'immagine contenitore. Tuttavia, quando è necessario eseguire la scalabilità SOA, potrebbero verificarsi problemi se si distribuisce in base alle singole istanze. Si tratta in cui una Docker software di clustering o orchestrator consentono. Verrà esaminato questo più dettagliatamente nella sezione successiva quando si esaminano gli approcci di microservizi.

Alla fine del giorno, le soluzioni di clustering contenitore sono utili per un'architettura SOA tradizionale o per un'architettura di microservizi più avanzata in cui ogni microservizio appartiene il modello di dati. E, grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitici condivisi dai servizi SOA. Tuttavia, la discussione sulla divisione dei dati è esclusivamente sull'architettura e progettazione.


>[!div class="step-by-step"]
[Previous] (state-and-data-in-docker-applications.md) [Next] (orchestrate-high-scalability-availability.md)
