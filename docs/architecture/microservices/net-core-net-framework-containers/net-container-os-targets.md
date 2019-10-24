---
title: Come scegliere il sistema operativo per i contenitori .NET
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Come scegliere il sistema operativo per i contenitori .NET
ms.date: 01/07/2019
ms.openlocfilehash: 8bcfa0212f84c575a63f76e05edec1e511cadc36
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72772010"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="21bab-103">Come scegliere il sistema operativo per i contenitori .NET</span><span class="sxs-lookup"><span data-stu-id="21bab-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="21bab-104">Considerata la varietà di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, è necessario scegliere un sistema operativo e le versioni specifiche a seconda del framework in uso.</span><span class="sxs-lookup"><span data-stu-id="21bab-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="21bab-105">Per Windows, è possibile usare Windows Server Core o Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="21bab-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="21bab-106">Queste versioni di Windows offrono caratteristiche diverse (IIS in Windows Server Core rispetto a un server Web self-hosted come Kestrel in Windows Nano Server) che potrebbero essere richieste rispettivamente da .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="21bab-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="21bab-107">Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.</span><span class="sxs-lookup"><span data-stu-id="21bab-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="21bab-108">Nella figura 3-1 sono mostrate le versioni possibili del sistema operativo a seconda del framework .NET usato.</span><span class="sxs-lookup"><span data-stu-id="21bab-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![Quando si distribuiscono applicazioni .NET Framework legacy, è necessario usare come destinazione Windows Server Core, che è compatibile con le app legacy e IIS e ha un'immagine di dimensioni maggiori.](./media/image1.png)

<span data-ttu-id="21bab-113">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="21bab-113">**Figure 3-1.**</span></span> <span data-ttu-id="21bab-114">Sistemi operativi possibili a seconda delle versioni del framework .NET</span><span class="sxs-lookup"><span data-stu-id="21bab-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="21bab-115">È anche possibile creare un'immagine Docker personalizzata, se si vuole usare una distribuzione Linux diversa o un'immagine con versioni non fornite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21bab-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="21bab-116">Si può ad esempio creare un'immagine con ASP.NET Core in esecuzione in .NET Framework tradizionale e in Windows Server Core, che non rappresenta uno scenario così comune per Docker.</span><span class="sxs-lookup"><span data-stu-id="21bab-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21bab-117">Quando si usano le immagini di Windows Server Core, si potrebbe notare che alcune dll risultano mancanti, rispetto alle immagini Windows complete.</span><span class="sxs-lookup"><span data-stu-id="21bab-117">When using Windows Server Core images, you might find that some DLLs are missing, when compared to full Windows images.</span></span> <span data-ttu-id="21bab-118">Per risolvere questo problema, è possibile creare un'immagine server core personalizzata, aggiungendo i file mancanti al momento della compilazione dell'immagine, come indicato in questo [Commento di GitHub](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span><span class="sxs-lookup"><span data-stu-id="21bab-118">You might be able to solve this problem by creating a custom Server Core image, adding the missing files at image build time, as mentioned in this [GitHub comment](https://github.com/microsoft/dotnet-framework-docker/issues/299#issuecomment-511537448).</span></span>

<span data-ttu-id="21bab-119">Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag usato, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="21bab-119">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

| <span data-ttu-id="21bab-120">Immagine</span><span class="sxs-lookup"><span data-stu-id="21bab-120">Image</span></span> | <span data-ttu-id="21bab-121">Comments</span><span class="sxs-lookup"><span data-stu-id="21bab-121">Comments</span></span> |
|-------|----------|
| <span data-ttu-id="21bab-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="21bab-122">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span> | <span data-ttu-id="21bab-123">.NET Core 2,2 multiarchitettura: supporta Linux e Windows nano server a seconda dell'host docker.</span><span class="sxs-lookup"><span data-stu-id="21bab-123">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> |
| <span data-ttu-id="21bab-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="21bab-124">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span> | <span data-ttu-id="21bab-125">ASP.NET Core 2,2 multiarchitettura: supporta Linux e Windows nano server a seconda dell'host docker.</span><span class="sxs-lookup"><span data-stu-id="21bab-125">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span> <br/> <span data-ttu-id="21bab-126">L'immagine aspnetcore ha poche ottimizzazioni per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="21bab-126">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span> |
| <span data-ttu-id="21bab-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="21bab-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span> | <span data-ttu-id="21bab-128">Solo runtime .NET Core 2.2 in distribuzioni Linux Alpine</span><span class="sxs-lookup"><span data-stu-id="21bab-128">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span> |
| <span data-ttu-id="21bab-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="21bab-129">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span> | <span data-ttu-id="21bab-130">Solo runtime .NET Core 2.2 in Windows Nano Server (Windows Server versione 1803)</span><span class="sxs-lookup"><span data-stu-id="21bab-130">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="21bab-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="21bab-131">Additional resources</span></span>

- <span data-ttu-id="21bab-132">**BitmapDecoder non riesce a causa di WindowsCodecsExt. dll mancante (problema di GitHub)**</span><span class="sxs-lookup"><span data-stu-id="21bab-132">**BitmapDecoder fails due to missing WindowsCodecsExt.dll (GitHub issue)**</span></span>  
  <https://github.com/microsoft/dotnet-framework-docker/issues/299>

> [!div class="step-by-step"]
> <span data-ttu-id="21bab-133">[Precedente](container-framework-choice-factors.md)
> [Successivo](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="21bab-133">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
