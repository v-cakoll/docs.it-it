---
title: Scelta di NET Core o NET Framework per i contenitori di Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Scelta tra .NET Core e .NET Framework per contenitori di Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: 9abff2614e4022408a069be25440196111db19ab
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46562109"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="42b50-103">Scelta di NET Core o NET Framework per i contenitori di Docker</span><span class="sxs-lookup"><span data-stu-id="42b50-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="42b50-104">Per la creazione di applicazioni lato server in contenitori di Docker con .NET sono supportati due framework: [.NET Framework e .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="42b50-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="42b50-105">Queste implementazioni condividono molti componenti della piattaforma .NET e possono condividere codice.</span><span class="sxs-lookup"><span data-stu-id="42b50-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="42b50-106">Tuttavia, esistono differenze fondamentali tra le due opzioni e la scelta del framework da usare dipende dall'obiettivo che si vuole conseguire.</span><span class="sxs-lookup"><span data-stu-id="42b50-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="42b50-107">In questa sezione vengono fornite istruzioni su come scegliere il framework.</span><span class="sxs-lookup"><span data-stu-id="42b50-107">This section provides guidance on when to choose each framework.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="42b50-108">[Precedente](../container-docker-introduction/docker-containers-images-registries.md)
[Successivo](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="42b50-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
