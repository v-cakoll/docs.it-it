---
title: Tabella decisioni. Framework .NET da usare per Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Tabella decisioni, framework .NET da usare per Docker
ms.date: 09/11/2018
ms.openlocfilehash: 0087d80c2d949daf14e1edd773dd310f47c508a9
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71039670"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabella decisioni: framework .NET da usare per Docker

La tabella decisioni seguente indica se usare .NET Framework o .NET Core. Tenere presente che per i contenitori Linux sono necessari host Docker (macchine virtuali o server) basati su Linux e che per i contenitori Windows sono necessari host Docker (macchine virtuali o server) basati su Windows Server.

> [!IMPORTANT]
> I computer di sviluppo eseguiranno un host Docker, Linux o Windows. I servizi correlati da eseguire e testare insieme in un'unica soluzione dovranno essere eseguiti sulla stessa piattaforma di contenitori.

| Architettura/tipo di app | Contenitori Linux | Contenitori di Windows |
|-------------------------|------------------|--------------------|
| Microservizi in contenitori | .NET Core | .NET Core |
| App monolitica | .NET Core | .NET Framework <br/> .NET Core |
| Prestazioni e scalabilità migliori del settore | .NET Core | .NET Core |
| Migrazione di un'app legacy (brown field) Windows Server ai contenitori | -- | .NET Framework |
| Nuovo sviluppo basato su contenitori (green field) | .NET Core | .NET Core |
| ASP.NET Core | .NET Core | .NET Core (consigliato) <br/> .NET Framework |
| ASP.NET 4 (MVC 5, Web API 2 e Web Form) | -- | .NET Framework |
| Servizi SignalR | .NET Core 2.1 o versioni successive | .NET Framework <br/> .NET Core 2.1 o versioni successive |
| WCF, WF e altri framework legacy | WCF in .NET Core (solo libreria client) | .NET Framework <br/> WCF in .NET Core (solo libreria client) |
| Utilizzo di servizi di Azure | .NET Core <br/> (prossimamente tutti i servizi di Azure forniranno SDK client per .NET Core) | .NET Framework <br/> .NET Core <br/> (prossimamente tutti i servizi di Azure forniranno SDK client per .NET Core) |

>[!div class="step-by-step"]
>[Precedente](net-framework-container-scenarios.md)
>[Successivo](net-container-os-targets.md)
