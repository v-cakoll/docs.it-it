---
title: Progettare applicazioni Docker
description: Riferimento a una guida dettagliata all'architettura dei microservizi, argomento non trattato nel dettaglio nella presente guida.
ms.date: 02/15/2019
ms.openlocfilehash: 535b6cefb7371014527032972ec27ebfe4b67ebc
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/13/2019
ms.locfileid: "65644643"
---
# <a name="design-docker-applications"></a>Progettare applicazioni Docker

Il capitolo 1 ha presentato i concetti fondamentali relativi ai contenitori e a Docker. Le informazioni fornite rappresentano il livello di conoscenza di base necessario per iniziare. Le applicazioni aziendali tuttavia possono essere complesse e composte da più servizi anziché da un singolo servizio o contenitore. Per questi casi d'uso facoltativi, è necessario conoscere ulteriori approcci di programmazione, ad esempio SOA (Service-Oriented Architecture), e concetti più avanzati relativi ai microservizi e all'orchestrazione dei contenitori. Poiché in questo documento non sono descritti solamente i microservizi ma il ciclo di vita di qualsiasi applicazione Docker, l'architettura dei microservizi non è descritta nel dettaglio poiché è anche possibile usare i contenitori e Docker con una normale architettura SOA, attività o processi in background o persino con approcci di sviluppo di applicazioni monolitiche.

**Altre informazioni** Per altre informazioni sulle applicazioni aziendali e una descrizione dettagliata dell'architettura dei microservizi, leggere la guida [NET Microservices: Architecture for Containerized .NET Applications](../../microservices-architecture/index.md) (Microservizi NET: Architettura per le applicazioni .NET aggiunte a contenitori) che è possibile scaricare da <https://aka.ms/MicroservicesEbook>.

Tuttavia, prima di addentrarsi nel ciclo di vita delle applicazioni e in DevOps, è importante conoscere il modo in cui l'applicazione verrà progettata e costruita e le scelte di progettazione.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[Successivo](common-container-design-principles.md)
