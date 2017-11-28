---
title: Scelta di NET Core o NET Framework per i contenitori di Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Scelta tra .NET Core e .NET Framework per contenitori di Docker
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f7a5fee26f4d138ae22f3551a25a674b22a2f6d1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a>Scelta di NET Core o NET Framework per i contenitori di Docker

Per la creazione di applicazioni lato server in contenitori di Docker con .NET sono supportate due implementazioni: [.NET Framework](https://www.microsoft.com/net/download/framework) e [.NET Core](https://www.microsoft.com/net/download/core). Queste implementazioni condividono molti componenti .NET standard e possono condividere codice. Tuttavia, esistono differenze fondamentali tra le due opzioni e la scelta dell’implementazione da usare dipende dall'obiettivo che si vuole conseguire. In questa sezione vengono fornite istruzioni su come scegliere l’implementazione.


>[!div class="step-by-step"]
[Precedente] (../container-docker-introduction/docker-containers-images-registries.md) [Successivo] (guidance.md generale)
