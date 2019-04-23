---
title: Scelta di NET Core o NET Framework per i contenitori di Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Scelta tra .NET Core e .NET Framework per contenitori di Docker
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/11/2018
ms.openlocfilehash: e71739b06275d4ee786d246004930d7b66fbc72b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62019607"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="582af-103">Scelta di NET Core o NET Framework per i contenitori di Docker</span><span class="sxs-lookup"><span data-stu-id="582af-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="582af-104">Per la creazione di applicazioni lato server in contenitori di Docker con .NET sono supportati due framework: [.NET Framework e .NET Core](https://www.microsoft.com/net/download).</span><span class="sxs-lookup"><span data-stu-id="582af-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://www.microsoft.com/net/download).</span></span> <span data-ttu-id="582af-105">Queste implementazioni condividono molti componenti della piattaforma .NET e possono condividere codice.</span><span class="sxs-lookup"><span data-stu-id="582af-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="582af-106">Tuttavia, esistono differenze fondamentali tra le due opzioni e la scelta del framework da usare dipende dall'obiettivo che si vuole conseguire.</span><span class="sxs-lookup"><span data-stu-id="582af-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="582af-107">In questa sezione vengono fornite istruzioni su come scegliere il framework.</span><span class="sxs-lookup"><span data-stu-id="582af-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="582af-108">[Precedente](../container-docker-introduction/docker-containers-images-registries.md)
>[Successivo](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="582af-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>