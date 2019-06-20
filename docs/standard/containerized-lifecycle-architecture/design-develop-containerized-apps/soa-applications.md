---
title: Applicazioni SOA
description: Tenere presente che anche i contenitori possono essere un'opzione di distribuzione utile per le applicazioni SOA.
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644755"
---
# <a name="service-oriented-applications"></a>Applicazioni orientate ai servizi

Architettura orientata ai servizi (SOA) è un termine molto usato che può avere significati diversi a seconda delle persone. In generale, architettura orientata ai servizi significa strutturare l'architettura dell'applicazione scomponendola in più servizi (comunemente servizi HTTP) che possono essere classificati in diversi tipi, come ad esempio sottosistemi o livelli.

Oggi tali servizi possono essere distribuiti come contenitori Docker, che risolvono i problemi di distribuzione poiché tutte le dipendenze sono incluse nell'immagine del contenitore. Tuttavia, quando è necessario scalare orizzontalmente le applicazioni SOA, potrebbero verificarsi problemi se si esegue la distribuzione in base alle singole istanze. Questo problema può essere gestito usando software di clustering Docker o un agente di orchestrazione. Gli agenti di orchestrazione verranno illustrati più dettagliatamente nella sezione successiva, quando si esamineranno gli approcci relativi ai microservizi.

I contenitori Docker sono utili (ma non necessari) sia per le architetture orientate ai servizi tradizionali sia per le architetture di microservizi più avanzate.

Alla fine, le soluzioni di clustering dei contenitori sono utili sia per un'architettura SOA tradizionale che per un'architettura di microservizi più avanzata in cui ogni microservizio è proprietario del modello di dati. E grazie alla presenza di più database, è anche possibile scalare orizzontalmente il livello dei dati invece di lavorare con database monolitici condivisi dai servizi SOA. Tuttavia, la discussione sulla suddivisione dei dati riguarda esclusivamente l'architettura e la progettazione.

>[!div class="step-by-step"]
>[Precedente](state-and-data-in-docker-applications.md)
>[Successivo](orchestrate-high-scalability-availability.md)
