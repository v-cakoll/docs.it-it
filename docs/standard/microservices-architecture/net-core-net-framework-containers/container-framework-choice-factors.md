---
title: Tabella decisioni. Versioni di .NET Framework da utilizzare per Docker
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Tabella decisioni, le versioni di .NET Framework da utilizzare per Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4889662c4d887bebd320389e3ced6aae1c93133b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabella decisioni: le versioni di .NET Framework da utilizzare per Docker

Di seguito vengono riepilogati se si desidera utilizzare i contenitori di .NET Framework o .NET Core e Windows o Linux. Tenere presente che per i contenitori di Linux, è necessario host Docker basati su Linux (macchine virtuali o server) e per i contenitori di Windows è necessario Windows Server basato su host Docker (macchine virtuali o server).

Sono disponibili diverse funzionalità dell'applicazione che interessano la decisione. Valutare l'importanza di queste funzionalità, è necessario prendere la decisione.

> [!IMPORTANT]
> Il computer di sviluppo verrà eseguito un host Docker, Linux o Windows. Microservizi correlati che si desidera eseguire e testare insieme in un'unica soluzione saranno necessario eseguire la stessa piattaforma di contenitore.

* La scelta di architettura dell'applicazione è **Microservizi sui contenitori**.
    - Deve essere la scelta di implementazione di .NET *.NET Core*.
    - Può essere la scelta della piattaforma contenitore *contenitori di Linux* o *contenitori di Windows*.
* La scelta di architettura dell'applicazione è un **applicazione monolitico**.
    - Può essere la scelta di implementazione di .NET *.NET Core* o *.NET Framework*.
    - Se si è scelto *.NET Core*, può essere la scelta della piattaforma contenitore *contenitori di Linux* o *contenitori di Windows*.
    - Se si è scelto *.NET Framework*, deve essere la scelta della piattaforma contenitore *contenitori di Windows*.
* L'applicazione è un **nuovo sviluppo basato su contenitore ("verde-field")**.
    - Deve essere la scelta di implementazione di .NET *.NET Core*.
    - Può essere la scelta della piattaforma contenitore *contenitori di Linux* o *contenitori di Windows*.
* L'applicazione è un **migrazione app legacy ("brown-field") di Windows Server per i contenitori**
    - La scelta di implementazione di .NET è *.NET Framework* in base alle dipendenze di framework.
    - Deve essere la scelta della piattaforma contenitore *contenitori di Windows* a causa di dipendenze di .NET Framework.
* Obiettivo di progettazione dell'applicazione **scalabilità e prestazioni migliori in class**.
    - Deve essere la scelta di implementazione di .NET *.NET Core*.
    - Può essere la scelta della piattaforma contenitore *contenitori di Linux* o *contenitori di Windows*.
* È stato compilato l'applicazione utilizzando **ASP.NET Core**.
    - Deve essere la scelta di implementazione di .NET *.NET Core*.
    - È possibile utilizzare il *.NET Framework* implementazione, se si dispone di altre dipendenze di framework.
    - Se si è scelto *.NET Core*, può essere la scelta della piattaforma contenitore *contenitori di Linux* o *contenitori di Windows*.
    - Se si è scelto *.NET Framework*, deve essere la scelta della piattaforma contenitore *contenitori di Windows*.
* È stato compilato l'applicazione utilizzando **ASP.NET 4 (5 MVC, API Web 2 e Web Form)**.
    - La scelta di implementazione di .NET è *.NET Framework* in base alle dipendenze di framework.
    - Deve essere la scelta della piattaforma contenitore *contenitori di Windows* a causa di dipendenze di .NET Framework.
* L'applicazione usa **i servizi SignalR**.
    - Può essere la scelta di implementazione di .NET *.NET Framework*, o *.NET Core 2.1 (quando rilasciato) o versione successiva*.
    - Deve essere la scelta della piattaforma contenitore *contenitori di Windows* se si sceglie l'implementazione di SignalR in .NET Framework.
    - La scelta della piattaforma contenitore può essere contenitori di Linux o i contenitori di Windows se si sceglie l'implementazione di SignalR in .NET Core 2.1 o versioni successive (quando rilasciato).  
    - Quando **i servizi SignalR** eseguiti *.NET Core*, è possibile utilizzare *Linux contenitori o i contenitori di Windows*.
* L'applicazione usa **WCF, WF e altri framework legacy**.
    - La scelta di implementazione di .NET è *.NET Framework*, o *.NET Core (in Guida di orientamento per una versione successiva)*.
    - Deve essere la scelta della piattaforma contenitore *contenitori di Windows* a causa di dipendenze di .NET Framework.
* L'applicazione prevede **servizi al consumo di Azure**.
    - La scelta di implementazione di .NET è *.NET Framework*, o *(servizi di Azure alla fine di tutti i fornirà client SDK per .NET Core) di .NET Core*.
    - Deve essere la scelta della piattaforma contenitore *contenitori di Windows* se si utilizza l'API client di .NET Framework.
    - Se si utilizzano le API disponibili per client *.NET Core*, è anche possibile scegliere tra *Linux contenitori e i contenitori di Windows*.

>[!div class="step-by-step"]
[Precedente] (net-framework-contenitore-scenarios.md) [Avanti] (net-contenitore-os-targets.md)
