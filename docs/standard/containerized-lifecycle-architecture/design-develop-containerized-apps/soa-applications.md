---
title: Applicazioni SOA
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 276071a5d55015f2feecc27020ad614684907b4c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105211"
---
# <a name="soa-applications"></a>Applicazioni SOA

SOA è un termine sovrautilizzato e disponibili moltissimi diversi significati a seconda degli utenti. Ma come minimo e un denominatore comune, SOA, o orientamento ai servizi, Media è struttura l'architettura dell'applicazione dalla scomposizione in più servizi (più di frequente come servizi HTTP) che possono essere classificati in diversi tipi sottosistemi In alternativa, in altri casi, come livelli.

Oggi, è possibile distribuire i servizi come contenitori di Docker, che risolve i problemi di distribuzione in quanto tutte le dipendenze sono incluse nell'immagine contenitore. Tuttavia, quando è necessario eseguire la scalabilità orizzontale SOA, potrebbero verificarsi problemi se si distribuisce in base alle singole istanze. Si tratta in cui una Docker software di clustering o orchestrator consentono. Verranno ora esaminate ciò più dettagliatamente nella sezione successiva quando si esaminano microservizi approcci.

Alla fine del giorno, le soluzioni contenitore clustering sono utili per un'architettura SOA tradizionale o per un'architettura di microservizi più avanzata in cui ogni microservizio appartiene il modello di dati. E, grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitici condivisi dai servizi SOA. Tuttavia, la discussione sulla divisione dei dati è esclusivamente sull'architettura e progettazione.


>[!div class="step-by-step"]
[Precedente](state-and-data-in-docker-applications.md)
[Successivo](orchestrate-high-scalability-availability.md)
