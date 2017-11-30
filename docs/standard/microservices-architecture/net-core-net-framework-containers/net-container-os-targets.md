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
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="5a2a3-104">Il sistema operativo di destinazione con i contenitori di .NET</span><span class="sxs-lookup"><span data-stu-id="5a2a3-104">What OS to target with .NET containers</span></span>

<span data-ttu-id="5a2a3-105">Considerata la diversità di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, si deve essere indirizzata a uno specifico sistema operativo e le versioni specifiche a seconda del framework in uso.</span><span class="sxs-lookup"><span data-stu-id="5a2a3-105">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="5a2a3-106">Per Windows, è possibile utilizzare Windows Server Core o Nano Server di Windows.</span><span class="sxs-lookup"><span data-stu-id="5a2a3-106">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="5a2a3-107">Queste versioni di Windows forniscono caratteristiche diverse (da IIS in Windows Server Core rispetto a un server web self-hosted come Kestrel in Nano Server) che potrebbero essere necessari per .NET Framework o .NET Core, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="5a2a3-107">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="5a2a3-108">Per Linux e le distribuzioni più sono disponibile e supportata nelle immagini Docker .NET ufficiale (ad esempio, Debian).</span><span class="sxs-lookup"><span data-stu-id="5a2a3-108">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="5a2a3-109">Nella figura 3-1. è possibile visualizzare la versione del sistema operativo possibili a seconda di .NET framework utilizzata.</span><span class="sxs-lookup"><span data-stu-id="5a2a3-109">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="5a2a3-110">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="5a2a3-110">**Figure 3-1.**</span></span> <span data-ttu-id="5a2a3-111">Sistemi operativi di destinazione, a seconda delle versioni di .NET framework</span><span class="sxs-lookup"><span data-stu-id="5a2a3-111">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="5a2a3-112">È anche possibile creare la propria immagine di Docker in casi in cui si desidera utilizzare una distribuzione Linux diversa o in cui si desidera un'immagine con le versioni non fornite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5a2a3-112">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="5a2a3-113">Ad esempio, è possibile creare un'immagine con ASP.NET Core in esecuzione in .NET Framework e Windows Server Core, è uno scenario non comune per Docker tradizionale.</span><span class="sxs-lookup"><span data-stu-id="5a2a3-113">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="5a2a3-114">Quando si aggiunge il nome dell'immagine nel file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag che si usa, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5a2a3-114">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="5a2a3-115">Microsoft /**dotnet:2.0.0-runtime-jessie**</span><span class="sxs-lookup"><span data-stu-id="5a2a3-115">microsoft/**dotnet:2.0.0-runtime-jessie**</span></span>

        .NET Core 2.0 runtime-only on Linux

-   <span data-ttu-id="5a2a3-116">Microsoft /**dotnet:2.0.0-runtime-nanoserver-1709**</span><span class="sxs-lookup"><span data-stu-id="5a2a3-116">microsoft/**dotnet:2.0.0-runtime-nanoserver-1709**</span></span> 

        .NET Core 2.0 runtime-only on Windows Nano Server (Windows Server 2016 Fall Creators Update version 1709)

-   <span data-ttu-id="5a2a3-117">Microsoft /**aspnetcore:2.0**</span><span class="sxs-lookup"><span data-stu-id="5a2a3-117">microsoft/**aspnetcore:2.0**</span></span>
    
        .NET Core 2.0 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 





>[!div class="step-by-step"]
<span data-ttu-id="5a2a3-118">[Precedente] (contenitore-framework-scelta-factors.md) [Avanti] (ufficiale-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="5a2a3-118">[Previous] (container-framework-choice-factors.md) [Next] (official-net-docker-images.md)</span></span>
