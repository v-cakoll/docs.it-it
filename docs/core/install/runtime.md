---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: fbe9b9e12dc53d9ab6570299e03f2b0a8868fb53
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567265"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="566d0-104">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="566d0-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="566d0-105">In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="566d0-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="566d0-106">Il runtime di .NET Core viene usato per eseguire app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="566d0-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows,os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="566d0-107">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="566d0-107">Install with an installer</span></span>

<span data-ttu-id="566d0-108">Sia Windows che macOS hanno programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="566d0-108">Both Windows and macOS have standalone installers that can be used to install the .NET Core 3.0 runtime.</span></span>

- <span data-ttu-id="566d0-109">[CPU Windows x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.0) | [cpu x86 (32-bit)](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span><span class="sxs-lookup"><span data-stu-id="566d0-109">Windows [x64 (64-bit) CPUs](https://dotnet.microsoft.com/download/dotnet-core/3.0) | [x86 (32-bit) CPUs](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span></span>
- <span data-ttu-id="566d0-110">[CPU MacOS x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span><span class="sxs-lookup"><span data-stu-id="566d0-110">macOS [x64 (64-bit) CPUs](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span></span>

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="566d0-111">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="566d0-111">Install with a package manager</span></span>

<span data-ttu-id="566d0-112">È possibile installare il runtime di .NET Core con molti dei comuni gestori di pacchetti Linux.</span><span class="sxs-lookup"><span data-stu-id="566d0-112">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="566d0-113">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-manager-rhel7.md)).</span><span class="sxs-lookup"><span data-stu-id="566d0-113">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="566d0-114">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="566d0-114">Install with PowerShell automation</span></span>

<span data-ttu-id="566d0-115">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="566d0-115">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="566d0-116">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="566d0-116">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="566d0-117">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="566d0-117">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="566d0-118">Per installare la versione corrente di .NET Core (3,0), eseguire lo script con l'opzione seguente:</span><span class="sxs-lookup"><span data-stu-id="566d0-118">To install the current release of .NET Core (3.0), run the script with the following switch:</span></span>

```powershell
dotnet-install.ps1 -Channel 3.0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="566d0-119">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="566d0-119">Install with bash automation</span></span>

<span data-ttu-id="566d0-120">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="566d0-120">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="566d0-121">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="566d0-121">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="566d0-122">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="566d0-122">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="566d0-123">Per installare la versione corrente di .NET Core (3,0), eseguire lo script con l'opzione seguente:</span><span class="sxs-lookup"><span data-stu-id="566d0-123">To install the current release of .NET Core (3.0), run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="566d0-124">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="566d0-124">All .NET Core downloads</span></span>

<span data-ttu-id="566d0-125">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="566d0-125">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="566d0-126">Download di .NET Core 3,1 Preview</span><span class="sxs-lookup"><span data-stu-id="566d0-126">.NET Core 3.1 Preview downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="566d0-127">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="566d0-127">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="566d0-128">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="566d0-128">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="566d0-129">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="566d0-129">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="566d0-130">Docker</span><span class="sxs-lookup"><span data-stu-id="566d0-130">Docker</span></span>

<span data-ttu-id="566d0-131">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="566d0-131">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="566d0-132">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="566d0-132">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="566d0-133">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="566d0-133">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="566d0-134">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="566d0-134">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="566d0-135">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="566d0-135">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="566d0-136">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="566d0-136">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="566d0-137">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="566d0-137">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="566d0-138">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="566d0-138">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="566d0-139">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="566d0-139">Next steps</span></span>

- <span data-ttu-id="566d0-140">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="566d0-140">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
