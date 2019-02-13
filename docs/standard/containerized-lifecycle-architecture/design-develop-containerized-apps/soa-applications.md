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
# <a name="soa-applications"></a>Applicazioni SOA

SOA è un termine sovrautilizzato e genere così tante cose diversi a persone diverse. Ma come minimo e un denominatore comune, SOA, o l'orientamento ai servizi, Media è struttura l'architettura dell'applicazione scomponendola in più servizi (più di frequente come servizi HTTP) che possono essere classificati in diversi tipi, ad esempio sottosistemi In alternativa, in altri casi, come livelli.

Oggi, è possibile distribuire questi servizi come contenitori Docker, che consente di risolvere i problemi di distribuzione perché tutte le dipendenze sono incluse nell'immagine del contenitore. Tuttavia, quando è necessario eseguire la scalabilità orizzontale SOA, potrebbero verificarsi problemi se si esegue la distribuzione in base alle singole istanze. Si tratta in cui un software di clustering o dell'agente di orchestrazione di Docker consente di. Esamineremo questo più dettagliatamente nella sezione successiva quando si esaminano gli approcci di microservizi.

Alla fine della giornata, le soluzioni di clustering contenitori sono utili per un'architettura SOA tradizionale o per un'architettura di microservizi più avanzata in cui ogni microservizio è proprietario al modello di dati. E, grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitico condivisi dai servizi SOA. Tuttavia, la discussione sulla suddivisione dei dati è esclusivamente sull'architettura e progettazione.

>[!div class="step-by-step"]
>[Precedente](state-and-data-in-docker-applications.md)
>[Successivo](orchestrate-high-scalability-availability.md)