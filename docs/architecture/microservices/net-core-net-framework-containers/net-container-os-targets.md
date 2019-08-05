---
title: Come scegliere il sistema operativo per i contenitori .NET
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Come scegliere il sistema operativo per i contenitori .NET
ms.date: 01/07/2019
ms.openlocfilehash: 6f160aeba5257722490788271e6f89359342cc0d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675758"
---
# <a name="what-os-to-target-with-net-containers"></a><span data-ttu-id="bb4cf-103">Come scegliere il sistema operativo per i contenitori .NET</span><span class="sxs-lookup"><span data-stu-id="bb4cf-103">What OS to target with .NET containers</span></span>

<span data-ttu-id="bb4cf-104">Considerata la varietà di sistemi operativi supportati da Docker e le differenze tra .NET Framework e .NET Core, è necessario scegliere un sistema operativo e le versioni specifiche a seconda del framework in uso.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-104">Given the diversity of operating systems supported by Docker and the differences between .NET Framework and .NET Core, you should target a specific OS and specific versions depending on the framework you are using.</span></span>

<span data-ttu-id="bb4cf-105">Per Windows, è possibile usare Windows Server Core o Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-105">For Windows, you can use Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="bb4cf-106">Queste versioni di Windows offrono caratteristiche diverse (IIS in Windows Server Core rispetto a un server Web self-hosted come Kestrel in Windows Nano Server) che potrebbero essere richieste rispettivamente da .NET Framework o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-106">These Windows versions provide different characteristics (IIS in Windows Server Core versus a self-hosted web server like Kestrel in Nano Server) that might be needed by .NET Framework or .NET Core, respectively.</span></span>

<span data-ttu-id="bb4cf-107">Per Linux, sono disponibili più distribuzioni supportate in immagini Docker. NET ufficiali, ad esempio Debian.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-107">For Linux, multiple distros are available and supported in official .NET Docker images (like Debian).</span></span>

<span data-ttu-id="bb4cf-108">Nella figura 3-1 sono mostrate le versioni possibili del sistema operativo a seconda del framework .NET usato.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-108">In Figure 3-1 you can see the possible OS version depending on the .NET framework used.</span></span>

![Quando si distribuiscono applicazioni .NET Framework legacy, è necessario usare come destinazione Windows Server Core, che è compatibile con le app legacy e IIS e ha un'immagine di dimensioni maggiori.](./media/image1.png)

<span data-ttu-id="bb4cf-113">**Figura 3-1.**</span><span class="sxs-lookup"><span data-stu-id="bb4cf-113">**Figure 3-1.**</span></span> <span data-ttu-id="bb4cf-114">Sistemi operativi possibili a seconda delle versioni del framework .NET</span><span class="sxs-lookup"><span data-stu-id="bb4cf-114">Operating systems to target depending on versions of the .NET framework</span></span>

<span data-ttu-id="bb4cf-115">È anche possibile creare un'immagine Docker personalizzata, se si vuole usare una distribuzione Linux diversa o un'immagine con versioni non fornite da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-115">You can also create your own Docker image in cases where you want to use a different Linux distro or where you want an image with versions not provided by Microsoft.</span></span> <span data-ttu-id="bb4cf-116">Si può ad esempio creare un'immagine con ASP.NET Core in esecuzione in .NET Framework tradizionale e in Windows Server Core, che non rappresenta uno scenario così comune per Docker.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-116">For example, you might create an image with ASP.NET Core running on the traditional .NET Framework and Windows Server Core, which is a not-so-common scenario for Docker.</span></span>

<span data-ttu-id="bb4cf-117">Quando si aggiunge il nome dell'immagine al file Dockerfile, è possibile selezionare il sistema operativo e la versione a seconda del tag usato, come negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb4cf-117">When you add the image name to your Dockerfile file, you can select the operating system and version depending on the tag you use, as in the following examples:</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="bb4cf-118">Image</span><span class="sxs-lookup"><span data-stu-id="bb4cf-118">Image</span></span></th>
<th><span data-ttu-id="bb4cf-119">Commenti</span><span class="sxs-lookup"><span data-stu-id="bb4cf-119">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="bb4cf-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span><span class="sxs-lookup"><span data-stu-id="bb4cf-120">mcr.microsoft.com/dotnet/core/runtime:2.2</span></span></td>
<td><span data-ttu-id="bb4cf-121">Multiarchitettura .NET Core 2.2: supporta Linux e Windows Nano Server a seconda dell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-121">.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4cf-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span><span class="sxs-lookup"><span data-stu-id="bb4cf-122">mcr.microsoft.com/dotnet/core/aspnet:2.2</span></span></td>
<td><p><span data-ttu-id="bb4cf-123">Multiarchitettura ASP .NET Core 2.2: supporta Linux e Windows Nano Server a seconda dell'host Docker.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-123">ASP.NET Core 2.2 multi-architecture: Supports Linux and Windows Nano Server depending on the Docker host.</span></span></p>
<p><span data-ttu-id="bb4cf-124">L'immagine aspnetcore ha poche ottimizzazioni per ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="bb4cf-124">The aspnetcore image has a few optimizations for ASP.NET Core.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bb4cf-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span><span class="sxs-lookup"><span data-stu-id="bb4cf-125">mcr.microsoft.com/dotnet/core/aspnet:2.2-alpine</span></span></td>
<td><span data-ttu-id="bb4cf-126">Solo runtime .NET Core 2.2 in distribuzioni Linux Alpine</span><span class="sxs-lookup"><span data-stu-id="bb4cf-126">.NET Core 2.2 runtime-only on Linux Alpine distro</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bb4cf-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span><span class="sxs-lookup"><span data-stu-id="bb4cf-127">mcr.microsoft.com/dotnet/core/aspnet:2.2-nanoserver-1803</span></span></td>
<td><span data-ttu-id="bb4cf-128">Solo runtime .NET Core 2.2 in Windows Nano Server (Windows Server versione 1803)</span><span class="sxs-lookup"><span data-stu-id="bb4cf-128">.NET Core 2.2 runtime-only on Windows Nano Server (Windows Server version 1803)</span></span></td>
</tr>
</tbody>
</table>

> [!div class="step-by-step"]
> <span data-ttu-id="bb4cf-129">[Precedente](container-framework-choice-factors.md)
> [Successivo](official-net-docker-images.md)</span><span class="sxs-lookup"><span data-stu-id="bb4cf-129">[Previous](container-framework-choice-factors.md)
[Next](official-net-docker-images.md)</span></span>
