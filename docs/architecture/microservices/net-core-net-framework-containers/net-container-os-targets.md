---
title: Come scegliere il sistema operativo per i contenitori .NET
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Come scegliere il sistema operativo per i contenitori .NET
ms.date: 01/30/2020
ms.openlocfilehash: a09e3981ece478a9795c0f27acc98d604864cdd5
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501854"
---
# <a name="what-os-to-target-with-net-containers"></a>Come scegliere il sistema operativo per i contenitori .NET

Considerata la varietà di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, è necessario scegliere un sistema operativo e le versioni specifiche a seconda del framework in uso.

Per Windows, è possibile usare Windows Server Core o Windows Nano Server. Queste versioni di Windows offrono caratteristiche diverse (IIS in Windows Server Core rispetto a un server Web self-hosted come Kestrel in Windows Nano Server) che potrebbero essere richieste rispettivamente da .NET Framework o .NET Core.

Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.

Nella figura 3-1 sono mostrate le versioni possibili del sistema operativo a seconda del framework .NET usato.

![Diagramma che illustra il sistema operativo da usare con i contenitori .NET.](./media/net-container-os-targets/targeting-operating-systems.png)

**Figura 3-1.** Sistemi operativi possibili a seconda delle versioni del framework .NET

Quando si distribuiscono applicazioni legacy .NET Framework è necessario usare Windows Server Core, compatibile con le app legacy e IIS, ma con un'immagine più grande. Quando si distribuiscono applicazioni .NET Core, è possibile usare come destinazione Windows Nano Server, che è ottimizzato per il cloud, usa Kestrel, è di dimensioni inferiori e viene avviato più rapidamente. È anche possibile usare come destinazione Linux, che supporta Debian, Alpine e altri sistemi. USA anche gheppio, è più piccolo e inizia più velocemente.

È anche possibile creare un'immagine Docker personalizzata, se si vuole usare una distribuzione Linux diversa o un'immagine con versioni non fornite da Microsoft. Si può ad esempio creare un'immagine con ASP.NET Core in esecuzione in .NET Framework tradizionale e in Windows Server Core, che non rappresenta uno scenario così comune per Docker.

> [!IMPORTANT]
> Quando si usano le immagini di Windows Server Core, si potrebbe notare che alcune dll risultano mancanti, rispetto alle immagini Windows complete. Per risolvere questo problema, è possibile creare un'immagine server core personalizzata, aggiungendo i file mancanti al momento della compilazione dell'immagine, come indicato in questo [Commento di GitHub](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).

Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag usato, come negli esempi seguenti:

| Immagine | Comments |
|-------|----------|
| mcr.microsoft.com/dotnet/core/runtime:3.1 | .NET Core 3,1 multiarchitettura: supporta Linux e Windows nano server a seconda dell'host docker. |
| mcr.microsoft.com/dotnet/core/aspnet:3.1 | ASP.NET Core 3,1 multiarchitettura: supporta Linux e Windows nano server a seconda dell'host docker. <br/> L'immagine aspnetcore ha poche ottimizzazioni per ASP.NET Core. |
| mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim | Runtime di .NET Core 3,1-solo per la distribuzione Debian Linux |
| mcr.microsoft.com/dotnet/core/aspnet:3.1-nanoserver-1809 | Runtime di .NET Core 3,1-solo in Windows nano Server (Windows Server versione 1809) |

## <a name="additional-resources"></a>Risorse aggiuntive

- **BitmapDecoder non riesce a causa di WindowsCodecsExt. dll mancante (problema di GitHub)**  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> [Precedente](container-framework-choice-factors.md)
> [Successivo](official-net-docker-images.md)
