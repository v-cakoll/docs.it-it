---
title: Tabella decisioni. Framework .NET da usare per Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Tabella decisioni, framework .NET da usare per Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 0e384fabca88d8ad6f93ae626140fb3d5dcaf971
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabella decisioni: framework .NET da usare per Docker

La tabella seguente indica se usare .NET Framework o .NET Core con contenitori Windows o Linux. Tenere presente che per i contenitori Linux sono necessari host Docker (macchine virtuali o server) basati su Linux e che per i contenitori Windows sono necessari host Docker (macchine virtuali o server) basati su Windows Server.

Sono molte le funzionalità dell'applicazione che influiscono sulla scelta. Ponderare l'importanza di tali funzionalità per prendere una decisione.

> [!IMPORTANT]
> I computer di sviluppo eseguiranno un host Docker, Linux o Windows. I servizi correlati da eseguire e testare insieme in un'unica soluzione dovranno essere eseguiti sulla stessa piattaforma di contenitori.

* L'architettura dell'applicazione è **microservizi in contenitori**.
    - L'implementazione .NET dovrà essere *.NET Core*.
    - La piattaforma di contenitori può essere *contenitori Linux* o *contenitori Windows*.
* L'architettura dell'applicazione è un'**applicazione monolitica**.
    - L'implementazione .NET può essere *.NET Core* o *.NET Framework*.
    - Se si è scelto di usare *.NET Core*, la piattaforma di contenitori può essere *contenitori Linux* o *contenitori Windows*.
    - Se si è scelto di usare *.NET Framework*, la piattaforma di contenitori deve essere *contenitori Windows*.
* L'applicazione è un **nuovo sviluppo basato su contenitori (green field)**.
    - L'implementazione .NET dovrà essere *.NET Core*.
    - La piattaforma di contenitori può essere *contenitori Linux* o *contenitori Windows*.
* L'applicazione è una **migrazione di un'app legacy (brown field) Windows Server ai contenitori**
    - L'implementazione .NET è *.NET Framework* in base alla dipendenza dal framework.
    - La piattaforma di contenitori deve essere *contenitori Windows* a causa della dipendenza da .NET Framework.
* L'obiettivo di progettazione dell'applicazione è **migliori prestazioni e scalabilità**.
    - L'implementazione .NET dovrà essere *.NET Core*.
    - La piattaforma di contenitori può essere *contenitori Linux* o *contenitori Windows*.
* L'applicazione è stata creata con **ASP.NET Core**.
    - L'implementazione .NET dovrà essere *.NET Core*.
    - È possibile usare l'implementazione *.NET Framework* se sono presenti altre dipendenze da framework.
    - Se si è scelto di usare *.NET Core*, la piattaforma di contenitori può essere *contenitori Linux* o *contenitori Windows*.
    - Se si è scelto di usare *.NET Framework*, la piattaforma di contenitori deve essere *contenitori Windows*.
* L'applicazione è stata creata con **ASP.NET 4 (MVC 5, Web API 2 e Web Form)**.
    - L'implementazione .NET è *.NET Framework* in base alla dipendenza dal framework.
    - La piattaforma di contenitori deve essere *contenitori Windows* a causa della dipendenza da .NET Framework.
* L'applicazione usa **servizi SignalR**.
    - L'implementazione .NET può essere *.NET Framework* o *.NET Core 2.1 o versioni successive (quando saranno rilasciate)*.
    - La piattaforma di contenitori deve essere *contenitori Windows* se è stata scelta l'implementazione SignalR in .NET Framework.
    - La piattaforma di contenitori può essere contenitori Linux o Windows se è stata scelta l'implementazione SignalR in .NET Core 2.1 o versioni successive (quando saranno rilasciate).  
    - Quando i **servizi SignalR** vengono eseguiti in *.NET Core*, è possibile usare *contenitori Linux o contenitori Windows*.
* L'applicazione usa **WCF, WF e altri framework legacy**.
    - L'implementazione .NET può essere *.NET Framework* o *.NET Core (nella roadmap per una versione futura)*.
    - La piattaforma di contenitori deve essere *contenitori Windows* a causa della dipendenza da .NET Framework.
* L'applicazione prevede l'**utilizzo di servizi di Azure**.
    - L'implementazione .NET può essere *.NET Framework* o *.NET Core (prossimamente tutti i servizi di Azure forniranno SDK client per .NET Core)*.
    - Se si usano le API client di .NET Framework, la piattaforma di contenitori deve essere *contenitori Windows*.
    - Se si usano le API client disponibili per *.NET Core* è anche possibile scegliere tra *contenitori Linux e contenitori Windows*.

>[!div class="step-by-step"]
[Indietro] (net-framework-container-scenarios.md) [Avanti] (net-container-os-targets.md)
