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
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="e4718-103">Come scegliere il sistema operativo per i contenitori .NET</span><span class="sxs-lookup"><span data-stu-id="e4718-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="e4718-104">Considerata la varietà di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, è necessario scegliere un sistema operativo e le versioni specifiche a seconda del framework in uso.</span><span class="sxs-lookup"><span data-stu-id="e4718-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span> 

<span data-ttu-id="e4718-105">Per Windows, è possibile usare Windows Server Core o Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="e4718-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="e4718-106">Queste versioni di Windows offrono caratteristiche diverse (IIS in Windows Server Core rispetto a un server Web self-hosted come Kestrel in Windows Nano Server) che potrebbero essere richieste rispettivamente da .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e4718-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span> 

<span data-ttu-id="e4718-107">Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.</span><span class="sxs-lookup"><span data-stu-id="e4718-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="e4718-108">Nella figura 3-1 sono mostrate le versioni possibili del sistema operativo a seconda del framework .NET usato.</span><span class="sxs-lookup"><span data-stu-id="e4718-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![](./media/image1.png)

<span data-ttu-id="e4718-109">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="e4718-109">**Figure 3-1.**</span></span> <span data-ttu-id="e4718-110">Sistemi operativi possibili a seconda delle versioni del framework .NET</span><span class="sxs-lookup"><span data-stu-id="e4718-110">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="e4718-111">È anche possibile creare un'immagine Docker personalizzata, se si vuole usare una distribuzione Linux diversa o un'immagine con versioni non fornite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e4718-111">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="e4718-112">Si può ad esempio creare un'immagine con ASP.NET Core in esecuzione in .NET Framework tradizionale e in Windows Server Core, che non rappresenta uno scenario così comune per Docker.</span><span class="sxs-lookup"><span data-stu-id="e4718-112">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="e4718-113">Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag usato, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4718-113">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

-   <span data-ttu-id="e4718-114">microsoft/**dotnet:2.1-runtime**</span><span class="sxs-lookup"><span data-stu-id="e4718-114">microsoft/**dotnet:2.1-runtime**</span></span>

        .NET Core 2.1 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.

-   <span data-ttu-id="e4718-115">microsoft/**dotnet:2.1-aspnetcore-runtime**</span><span class="sxs-lookup"><span data-stu-id="e4718-115">microsoft/**dotnet:2.1-aspnetcore-runtime**</span></span>
    
        ASP.NET Core 2.1 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.
        The aspnetcore image has a few optimizations for ASP.NET Core. 

-   <span data-ttu-id="e4718-116">microsoft/**dotnet:2.1-aspnetcore-runtime-alpine**</span><span class="sxs-lookup"><span data-stu-id="e4718-116">microsoft/**dotnet:2.1-aspnetcore-runtime-alpine**</span></span> 

        .NET Core 2.1 runtime-only on Linux Alpine distro

-   <span data-ttu-id="e4718-117">microsoft/**dotnet:2.1-aspnetcore-runtime-nanoserver-1803**</span><span class="sxs-lookup"><span data-stu-id="e4718-117">microsoft/**dotnet:2.1-aspnetcore-runtime-nanoserver-1803**</span></span> 

        .NET Core 2.1 runtime-only on Windows Nano Server (Windows Server version 1803)




>[!div class="step-by-step"]
<span data-ttu-id="e4718-118">[Precedente](container-framework-choice-factors.md)
[Successivo](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="e4718-118">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
