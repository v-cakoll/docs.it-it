---
title: Applicazioni SOA
description: Tenere presente che i contenitori possono essere anche un'opzione di distribuzione utile per le applicazioni SOA.
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644755"
---
# <a name="service-oriented-applications"></a>Applicazioni orientate ai servizi

Service-Oriented Architecture (SOA) è un termine sovrautilizzato che significava molti aspetti diversi a persone diverse. Ma come un denominatore comune, SOA significa strutturare l'architettura dell'applicazione scomponendola in diversi servizi (più di frequente come servizi HTTP) che possono essere classificati in diversi tipi, come sottosistemi o, in altri casi, come i livelli.

Attualmente, è possibile distribuire questi servizi come i contenitori Docker, risolvere i problemi di distribuzione perché tutte le dipendenze sono inclusi nell'immagine del contenitore. Tuttavia, quando è necessario scalare orizzontalmente SOA, potrebbero verificarsi problemi se si esegue la distribuzione in base alle singole istanze. Questo problema può essere gestito tramite software di clustering o un agente di orchestrazione Docker. Esamineremo gli agenti di orchestrazione più dettagliatamente nella sezione successiva, quando si esplorano gli approcci di microservizi.

I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.

Alla fine della giornata, le soluzioni di clustering contenitori sono utili per un'architettura SOA tradizionale e per un'architettura di microservizi più avanzata in cui ogni microservizio è proprietario al modello di dati. E grazie a più database, è anche possibile scalare orizzontalmente il livello di dati invece di lavorare con i database monolitico condivisi dai servizi SOA. Tuttavia, la discussione sulla suddivisione dei dati è esclusivamente sull'architettura e progettazione.

>[!div class="step-by-step"]
>[Precedente](state-and-data-in-docker-applications.md)
>[Successivo](orchestrate-high-scalability-availability.md)
