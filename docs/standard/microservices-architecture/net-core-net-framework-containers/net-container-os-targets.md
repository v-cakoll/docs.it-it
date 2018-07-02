---
title: Come scegliere il sistema operativo per i contenitori .NET
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Come scegliere il sistema operativo per i contenitori .NET
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: fca5cf280d5abb85da78413a6eed463a2ffe6a88
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104879"
---
# <a name="what-os-to-target-with-net-containers"></a>Come scegliere il sistema operativo per i contenitori .NET

Considerata la varietà di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, è necessario scegliere un sistema operativo e le versioni specifiche a seconda del framework in uso. 

Per Windows, è possibile usare Windows Server Core o Windows Nano Server. Queste versioni di Windows offrono caratteristiche diverse (IIS in Windows Server Core rispetto a un server Web self-hosted come Kestrel in Windows Nano Server) che potrebbero essere richieste rispettivamente da .NET Framework o .NET Core. 

Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.

Nella figura 3-1 sono mostrate le versioni possibili del sistema operativo a seconda del framework .NET usato.

![](./media/image1.png)

**Figura 3-1.** Sistemi operativi possibili a seconda delle versioni del framework .NET

È anche possibile creare un'immagine Docker personalizzata, se si vuole usare una distribuzione Linux diversa o un'immagine con versioni non fornite da Microsoft. Si può ad esempio creare un'immagine con ASP.NET Core in esecuzione in .NET Framework tradizionale e in Windows Server Core, che non rappresenta uno scenario così comune per Docker.

Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag usato, come negli esempi seguenti:

-   microsoft/**dotnet:2.1-runtime**

        .NET Core 2.1 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.

-   microsoft/**dotnet:2.1-aspnetcore-runtime**
    
        ASP.NET Core 2.1 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 

-   microsoft/**dotnet:2.1-aspnetcore-runtime-alpine** 

        .NET Core 2.1 runtime-only on Linux Alpine distro

-   microsoft/**dotnet:2.1-aspnetcore-runtime-nanoserver-1803** 

        .NET Core 2.1 runtime-only on Windows Nano Server (Windows Server version 1803)




>[!div class="step-by-step"]
[Precedente](container-framework-choice-factors.md)
[Successivo](official-net-docker-images.md)
