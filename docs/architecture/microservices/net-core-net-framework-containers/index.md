---
title: Scelta di NET Core o NET Framework per i contenitori di Docker
description: Architettura di microservizi .NET per le applicazioni .NET incluse in contenitori | Scelta tra .NET Core e .NET Framework per contenitori di Docker
ms.date: 09/11/2018
ms.openlocfilehash: b01aaf25f4071e8e4a07905a12ec9dd0d89a738d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849269"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="eaa5c-103">Scelta di NET Core o NET Framework per i contenitori di Docker</span><span class="sxs-lookup"><span data-stu-id="eaa5c-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="eaa5c-104">Per la creazione di applicazioni lato server in contenitori di Docker con .NET sono supportati due framework: [.NET Framework e .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="eaa5c-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="eaa5c-105">Queste implementazioni condividono molti componenti della piattaforma .NET e possono condividere codice.</span><span class="sxs-lookup"><span data-stu-id="eaa5c-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="eaa5c-106">Tuttavia, esistono differenze fondamentali tra le due opzioni e la scelta del framework da usare dipende dall'obiettivo che si vuole conseguire.</span><span class="sxs-lookup"><span data-stu-id="eaa5c-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="eaa5c-107">In questa sezione vengono fornite istruzioni su come scegliere il framework.</span><span class="sxs-lookup"><span data-stu-id="eaa5c-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="eaa5c-108">[Precedente](../container-docker-introduction/docker-containers-images-registries.md)
>[Successivo](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="eaa5c-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
