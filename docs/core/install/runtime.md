---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74835728"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="44464-104">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="44464-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="44464-105">In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="44464-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="44464-106">Il runtime di .NET Core viene usato per eseguire app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="44464-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="44464-107">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="44464-107">Install with an installer</span></span>

<span data-ttu-id="44464-108">Windows dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="44464-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="44464-109">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="44464-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="44464-110">CPU x86 (32 bit)</span><span class="sxs-lookup"><span data-stu-id="44464-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="44464-111">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="44464-111">Install with an installer</span></span>

<span data-ttu-id="44464-112">macOS dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="44464-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="44464-113">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="44464-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="44464-114">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="44464-114">Install with a package manager</span></span>

<span data-ttu-id="44464-115">È possibile installare il runtime di .NET Core con molti dei comuni gestori di pacchetti Linux.</span><span class="sxs-lookup"><span data-stu-id="44464-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="44464-116">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-manager-rhel7.md)).</span><span class="sxs-lookup"><span data-stu-id="44464-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="44464-117">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="44464-117">Install with PowerShell automation</span></span>

<span data-ttu-id="44464-118">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="44464-118">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="44464-119">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="44464-119">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="44464-120">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="44464-120">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="44464-121">È possibile scegliere una versione specifica specificando l'opzione `Channel`.</span><span class="sxs-lookup"><span data-stu-id="44464-121">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="44464-122">Includere l'opzione `Runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="44464-122">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="44464-123">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="44464-123">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="44464-124">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="44464-124">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="44464-125">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="44464-125">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="44464-126">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="44464-126">Install with bash automation</span></span>

<span data-ttu-id="44464-127">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="44464-127">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="44464-128">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="44464-128">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="44464-129">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="44464-129">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="44464-130">È possibile scegliere una versione specifica specificando l'opzione `current`.</span><span class="sxs-lookup"><span data-stu-id="44464-130">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="44464-131">Includere l'opzione `runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="44464-131">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="44464-132">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="44464-132">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="44464-133">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="44464-133">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="44464-134">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="44464-134">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="44464-135">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="44464-135">All .NET Core downloads</span></span>

<span data-ttu-id="44464-136">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="44464-136">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="44464-137">Download di .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="44464-137">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="44464-138">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="44464-138">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="44464-139">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="44464-139">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="44464-140">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="44464-140">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="44464-141">Docker</span><span class="sxs-lookup"><span data-stu-id="44464-141">Docker</span></span>

<span data-ttu-id="44464-142">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="44464-142">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="44464-143">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="44464-143">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="44464-144">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="44464-144">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="44464-145">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="44464-145">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="44464-146">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="44464-146">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="44464-147">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="44464-147">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="44464-148">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="44464-148">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="44464-149">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="44464-149">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="44464-150">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="44464-150">Next steps</span></span>

- <span data-ttu-id="44464-151">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="44464-151">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
