---
title: Tabella decisioni. Framework .NET da usare per Docker
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Tabella decisioni, framework .NET da usare per Docker
ms.date: 09/11/2018
ms.openlocfilehash: 8ffe2b7bc0bee976d3a63b274994dbcc8aef0c61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628319"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabella decisioni: framework .NET da usare per Docker

La tabella decisioni seguente indica se usare .NET Framework o .NET Core. Tenere presente che per i contenitori Linux sono necessari host Docker (macchine virtuali o server) basati su Linux e che per i contenitori Windows sono necessari host Docker (macchine virtuali o server) basati su Windows Server.

> [!IMPORTANT]
> I computer di sviluppo eseguiranno un host Docker, Linux o Windows. I servizi correlati da eseguire e testare insieme in un'unica soluzione dovranno essere eseguiti sulla stessa piattaforma di contenitori.

| Architettura/Tipo di app | Contenitori Linux | Contenitori Windows |
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
| Utilizzo di servizi di Azure | .NET Core <br/> (eventualmente la maggior parte dei servizi di Azure fornirà SDK client per .NET Core) | .NET Framework <br/> .NET Core <br/> (eventualmente la maggior parte dei servizi di Azure fornirà SDK client per .NET Core) |

>[!div class="step-by-step"]
>[Successivo](net-framework-container-scenarios.md)
>[precedente](net-container-os-targets.md)
