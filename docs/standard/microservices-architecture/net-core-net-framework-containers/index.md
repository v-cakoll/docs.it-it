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
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 60d21de06262a14f9be6a1a5ce80edf15ddf1b59
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="8488b-104">Scelta di NET Core o NET Framework per i contenitori di Docker</span><span class="sxs-lookup"><span data-stu-id="8488b-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="8488b-105">Per la creazione di applicazioni lato server in contenitori di Docker con .NET sono supportate due implementazioni: [.NET Framework](https://www.microsoft.com/net/download/framework) e [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="8488b-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="8488b-106">Queste implementazioni condividono molti componenti .NET standard e possono condividere codice.</span><span class="sxs-lookup"><span data-stu-id="8488b-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="8488b-107">Tuttavia, esistono differenze fondamentali tra le due opzioni e la scelta dell’implementazione da usare dipende dall'obiettivo che si vuole conseguire.</span><span class="sxs-lookup"><span data-stu-id="8488b-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="8488b-108">In questa sezione vengono fornite istruzioni su come scegliere l’implementazione.</span><span class="sxs-lookup"><span data-stu-id="8488b-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="8488b-109">[Precedente] (../container-docker-introduction/docker-containers-images-registries.md) [Successivo] (guidance.md generale)</span><span class="sxs-lookup"><span data-stu-id="8488b-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
