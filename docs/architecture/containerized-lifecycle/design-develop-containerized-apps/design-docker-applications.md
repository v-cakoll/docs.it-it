---
title: Progettare applicazioni Docker
description: Riferimento a una guida dettagliata all'architettura dei microservizi, argomento non trattato nel dettaglio nella presente guida.
ms.date: 02/15/2019
ms.openlocfilehash: b8a08658ec6c3df3e1aed596a0240223768dd647
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738469"
---
# <a name="design-docker-applications"></a>Progettare applicazioni Docker

Il capitolo 1 ha presentato i concetti fondamentali relativi ai contenitori e a Docker. Le informazioni fornite rappresentano il livello di conoscenza di base necessario per iniziare. Le applicazioni aziendali tuttavia possono essere complesse e composte da più servizi anziché da un singolo servizio o contenitore. Per questi casi d'uso facoltativi, è necessario conoscere ulteriori approcci di programmazione, ad esempio SOA (Service-Oriented Architecture), e concetti più avanzati relativi ai microservizi e all'orchestrazione dei contenitori. L'ambito di questo documento non è limitato ai microservizi, ma a qualsiasi ciclo di vita dell'applicazione Docker, pertanto non esplora l'architettura dei microservizi in modo approfondito perché è anche possibile utilizzare contenitori e Docker con SOA regolari, attività o processi in background o anche con approcci di distribuzione monolitici dell'applicazione.

**Maggiori informazioni** Per altre informazioni sulle applicazioni aziendali e sull'architettura dei microservizi approfondita, leggere la guida <https://aka.ms/MicroservicesEbook> [Net Microservices: Architecture for Containerized Applications](../../microservices/index.md) che è anche possibile scaricare da .

Tuttavia, prima di addentrarsi nel ciclo di vita delle applicazioni e in DevOps, è importante conoscere il modo in cui l'applicazione verrà progettata e costruita e le scelte di progettazione.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](common-container-design-principles.md)
