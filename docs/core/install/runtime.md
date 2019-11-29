---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d39e5912cf2ae73631c2f1192adb516e84dfed32
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552193"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="f0a4e-104">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0a4e-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="f0a4e-105">In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="f0a4e-106">Il runtime di .NET Core viene usato per eseguire app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

<span data-ttu-id="f0a4e-107">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f0a4e-107">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="f0a4e-108">Download di .NET Core 3,1 Preview 3</span><span class="sxs-lookup"><span data-stu-id="f0a4e-108">.NET Core 3.1 Preview 3 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="f0a4e-109">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="f0a4e-109">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="f0a4e-110">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="f0a4e-110">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="f0a4e-111">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="f0a4e-111">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

::: zone pivot="os-windows,os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="f0a4e-112">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="f0a4e-112">Install with an installer</span></span>

<span data-ttu-id="f0a4e-113">Sia Windows che macOS hanno programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-113">Both Windows and macOS have standalone installers that can be used to install the .NET Core 3.0 runtime.</span></span>

- <span data-ttu-id="f0a4e-114">CPU di Windows [x64](https://dotnet.microsoft.com/download/thank-you/dotnet-runtime-3.0.0-windows-x64-installer) | [x32 CPU](https://dotnet.microsoft.com/download/thank-you/dotnet-runtime-3.0.0-windows-x86-installer)</span><span class="sxs-lookup"><span data-stu-id="f0a4e-114">Windows [x64 CPUs](https://dotnet.microsoft.com/download/thank-you/dotnet-runtime-3.0.0-windows-x64-installer) | [x32 CPUs](https://dotnet.microsoft.com/download/thank-you/dotnet-runtime-3.0.0-windows-x86-installer)</span></span>
- <span data-ttu-id="f0a4e-115">[CPU MacOS x64](https://dotnet.microsoft.com/download/thank-you/dotnet-runtime-3.0.0-macos-x64-installer)</span><span class="sxs-lookup"><span data-stu-id="f0a4e-115">macOS [x64 CPUs](https://dotnet.microsoft.com/download/thank-you/dotnet-runtime-3.0.0-macos-x64-installer)</span></span>

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="f0a4e-116">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="f0a4e-116">Install with a package manager</span></span>

<span data-ttu-id="f0a4e-117">È possibile installare il runtime di .NET Core con molti dei comuni gestori di pacchetti Linux.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-117">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="f0a4e-118">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-manager-rhel7.md)).</span><span class="sxs-lookup"><span data-stu-id="f0a4e-118">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="f0a4e-119">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0a4e-119">Install with PowerShell automation</span></span>

<span data-ttu-id="f0a4e-120">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-120">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="f0a4e-121">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f0a4e-121">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="f0a4e-122">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-122">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="f0a4e-123">Per installare la versione corrente di .NET Core (3,0), eseguire lo script con l'opzione seguente:</span><span class="sxs-lookup"><span data-stu-id="f0a4e-123">To install the current release of .NET Core (3.0), run the script with the following switch:</span></span>

```powershell
dotnet-install.ps1 -Channel 3.0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="f0a4e-124">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="f0a4e-124">Install with bash automation</span></span>

<span data-ttu-id="f0a4e-125">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-125">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="f0a4e-126">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f0a4e-126">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="f0a4e-127">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-127">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="f0a4e-128">Per installare la versione corrente di .NET Core (3,0), eseguire lo script con l'opzione seguente:</span><span class="sxs-lookup"><span data-stu-id="f0a4e-128">To install the current release of .NET Core (3.0), run the script with the following switch:</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="docker"></a><span data-ttu-id="f0a4e-129">Docker</span><span class="sxs-lookup"><span data-stu-id="f0a4e-129">Docker</span></span>

<span data-ttu-id="f0a4e-130">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-130">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="f0a4e-131">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-131">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="f0a4e-132">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-132">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="f0a4e-133">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="f0a4e-133">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="f0a4e-134">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-134">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="f0a4e-135">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-135">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="f0a4e-136">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f0a4e-136">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="f0a4e-137">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="f0a4e-137">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f0a4e-138">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f0a4e-138">Next steps</span></span>

- <span data-ttu-id="f0a4e-139">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="f0a4e-139">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
