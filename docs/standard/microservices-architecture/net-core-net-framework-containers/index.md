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
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="9ae6f-104">Scelta di NET Core o NET Framework per i contenitori di Docker</span><span class="sxs-lookup"><span data-stu-id="9ae6f-104">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="9ae6f-105">Per la creazione di applicazioni lato server in contenitori di Docker con .NET sono supportate due implementazioni: [.NET Framework](https://www.microsoft.com/net/download/framework) e [.NET Core](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="9ae6f-105">There are two supported implementations for building server-side containerized Docker applications with .NET: [.NET Framework](https://www.microsoft.com/net/download/framework) and [.NET Core](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="9ae6f-106">Queste implementazioni condividono molti componenti .NET standard e possono condividere codice.</span><span class="sxs-lookup"><span data-stu-id="9ae6f-106">They share many .NET Standard components, and you can share code across the two.</span></span> <span data-ttu-id="9ae6f-107">Tuttavia, esistono differenze fondamentali tra le due opzioni e la scelta dell’implementazione da usare dipende dall'obiettivo che si vuole conseguire.</span><span class="sxs-lookup"><span data-stu-id="9ae6f-107">However, there are fundamental differences between them, and which implementation you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="9ae6f-108">In questa sezione vengono fornite istruzioni su come scegliere l’implementazione.</span><span class="sxs-lookup"><span data-stu-id="9ae6f-108">This section provides guidance on when to choose each implementation.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="9ae6f-109">[Precedente] (../container-docker-introduction/docker-containers-images-registries.md) [Successivo] (guidance.md generale)</span><span class="sxs-lookup"><span data-stu-id="9ae6f-109">[Previous] (../container-docker-introduction/docker-containers-images-registries.md) [Next] (general-guidance.md)</span></span>
