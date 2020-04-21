---
title: Applicazioni SOA
description: Tenere presente che anche i contenitori possono essere un'opzione di distribuzione utile per le applicazioni SOA.
ms.date: 02/15/2019
ms.openlocfilehash: f8619cb50a7d90b911db9ff2c8ef37c3c5fde210
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738379"
---
# <a name="service-oriented-applications"></a>Applicazioni orientate ai servizi

Architettura orientata ai servizi (SOA) è un termine molto usato che può avere significati diversi a seconda delle persone. In generale, architettura orientata ai servizi significa strutturare l'architettura dell'applicazione scomponendola in più servizi (comunemente servizi HTTP) che possono essere classificati in diversi tipi, come ad esempio sottosistemi o livelli.

Oggi tali servizi possono essere distribuiti come contenitori Docker, che risolvono i problemi di distribuzione poiché tutte le dipendenze sono incluse nell'immagine del contenitore. Tuttavia, quando è necessario scalare orizzontalmente le applicazioni SOA, potrebbero verificarsi problemi se si esegue la distribuzione in base alle singole istanze. Questo problema può essere gestito usando software di clustering Docker o un agente di orchestrazione. Gli agenti di orchestrazione verranno illustrati più dettagliatamente nella sezione successiva, quando si esamineranno gli approcci relativi ai microservizi.

I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.

Alla fine, le soluzioni di clustering dei contenitori sono utili sia per un'architettura SOA tradizionale che per un'architettura di microservizi più avanzata in cui ogni microservizio è proprietario del modello di dati. E grazie a più database, è anche possibile scalare orizzontalmente il livello dati invece di lavorare con database monolitici condivisi dai servizi SOA. Tuttavia, la discussione sulla suddivisione dei dati riguarda esclusivamente l'architettura e la progettazione.

>[!div class="step-by-step"]
>[Successivo](state-and-data-in-docker-applications.md)
>[precedente](orchestrate-high-scalability-availability.md)
