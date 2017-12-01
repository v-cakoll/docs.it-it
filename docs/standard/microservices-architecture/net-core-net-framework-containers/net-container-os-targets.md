---
title: Il sistema operativo di destinazione con i contenitori di .NET
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Il sistema operativo di destinazione con i contenitori di .NET
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 828ccb5e7a76f9419e80793b6cb3a6ba24f358cf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="what-os-to-target-with-net-containers"></a>Il sistema operativo di destinazione con i contenitori di .NET

Considerata la diversità di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, si deve essere indirizzata a uno specifico sistema operativo e le versioni specifiche a seconda del framework in uso. 

Per Windows, è possibile utilizzare Windows Server Core o Nano Server di Windows. Queste versioni di Windows forniscono caratteristiche diverse (da IIS in Windows Server Core rispetto a un server web self-hosted come Kestrel in Nano Server) che potrebbero essere necessari per .NET Framework o .NET Core, rispettivamente. 

Per Linux e le distribuzioni più sono disponibile e supportata nelle immagini Docker .NET ufficiale (ad esempio, Debian).

Nella figura 3-1. è possibile visualizzare la versione del sistema operativo possibili a seconda di .NET framework utilizzata.

![](./media/image1.png)

**Figura 3-1.** Sistemi operativi di destinazione, a seconda delle versioni di .NET framework

È anche possibile creare la propria immagine di Docker in casi in cui si desidera utilizzare una distribuzione Linux diversa o in cui si desidera un'immagine con le versioni non fornite da Microsoft. Ad esempio, è possibile creare un'immagine con ASP.NET Core in esecuzione in .NET Framework e Windows Server Core, è uno scenario non comune per Docker tradizionale.

Quando si aggiunge il nome dell'immagine nel file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag che si usa, come negli esempi seguenti:

-   Microsoft /**dotnet:2.0.0-runtime-jessie**

        .NET Core 2.0 runtime-only on Linux

-   Microsoft /**dotnet:2.0.0-runtime-nanoserver-1709** 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   Microsoft /**aspnetcore:2.0**
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
[Precedente] (contenitore-framework-scelta-factors.md) [Avanti] (ufficiale-net-docker-images.md)
