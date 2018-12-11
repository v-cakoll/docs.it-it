---
title: Applicazioni SOA
description: Ciclo di vita delle applicazioni Docker in contenitori con piattaforma e strumenti Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 7f88daaf0787cf780e7ab9602f35ae4e6ab8308c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155314"
---
# <a name="soa-applications"></a>Applicazioni SOA

SOA è un termine sovrautilizzato e genere così tante cose diversi a persone diverse. Ma come minimo e un denominatore comune, SOA, o l'orientamento ai servizi, Media è struttura l'architettura dell'applicazione scomponendola in più servizi (più di frequente come servizi HTTP) che possono essere classificati in diversi tipi, ad esempio sottosistemi In alternativa, in altri casi, come livelli.

Oggi, è possibile distribuire questi servizi come contenitori Docker, che consente di risolvere i problemi di distribuzione perché tutte le dipendenze sono incluse nell'immagine del contenitore. Tuttavia, quando è necessario eseguire la scalabilità orizzontale SOA, potrebbero verificarsi problemi se si esegue la distribuzione in base alle singole istanze. Si tratta in cui un software di clustering o dell'agente di orchestrazione di Docker consente di. Esamineremo questo più dettagliatamente nella sezione successiva quando si esaminano gli approcci di microservizi.

Alla fine della giornata, le soluzioni di clustering contenitori sono utili per un'architettura SOA tradizionale o per un'architettura di microservizi più avanzata in cui ogni microservizio è proprietario al modello di dati. E, grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitico condivisi dai servizi SOA. Tuttavia, la discussione sulla suddivisione dei dati è esclusivamente sull'architettura e progettazione.

>[!div class="step-by-step"]
>[Precedente](state-and-data-in-docker-applications.md)
>[Successivo](orchestrate-high-scalability-availability.md)