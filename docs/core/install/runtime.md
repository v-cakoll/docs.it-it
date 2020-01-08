---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a45cb570ccf572a699359598319fd3867fb5e5dd
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75340965"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="409a7-104">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="409a7-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="409a7-105">In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="409a7-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="409a7-106">Il runtime di .NET Core viene usato per eseguire app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="409a7-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="409a7-107">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="409a7-107">Install with an installer</span></span>

<span data-ttu-id="409a7-108">Windows dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="409a7-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="409a7-109">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="409a7-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="409a7-110">CPU x86 (32 bit)</span><span class="sxs-lookup"><span data-stu-id="409a7-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="409a7-111">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="409a7-111">Install with an installer</span></span>

<span data-ttu-id="409a7-112">macOS dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="409a7-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="409a7-113">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="409a7-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="409a7-114">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="409a7-114">Install with a package manager</span></span>

<span data-ttu-id="409a7-115">È possibile installare il runtime di .NET Core con molti dei comuni gestori di pacchetti Linux.</span><span class="sxs-lookup"><span data-stu-id="409a7-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="409a7-116">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-managers.md)).</span><span class="sxs-lookup"><span data-stu-id="409a7-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="409a7-117">L'installazione con gestione pacchetti è supportata solo nell'architettura x64.</span><span class="sxs-lookup"><span data-stu-id="409a7-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="409a7-118">Se si sta installando il runtime di .NET Core con un'architettura diversa, ad esempio ARM, seguire le istruzioni nella sezione [download e installazione manuale](#download-and-manually-install) .</span><span class="sxs-lookup"><span data-stu-id="409a7-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="409a7-119">Per altre informazioni sulle architetture supportate, vedere [dipendenze e requisiti di .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="409a7-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="409a7-120">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="409a7-120">Download and manually install</span></span>

<span data-ttu-id="409a7-121">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="409a7-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="409a7-122">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="409a7-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="409a7-123">I comandi di `export` precedenti rendono disponibili solo i comandi interfaccia della riga di comando di .NET Core per la sessione terminal in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="409a7-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="409a7-124">È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="409a7-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="409a7-125">Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso.</span><span class="sxs-lookup"><span data-stu-id="409a7-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="409a7-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="409a7-126">For example:</span></span>
>
> - <span data-ttu-id="409a7-127">**Shell bash**: *~/. bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="409a7-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="409a7-128">**Korn Shell**: *~/.KSHRC* o *. profile*</span><span class="sxs-lookup"><span data-stu-id="409a7-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="409a7-129">**Shell Z**: *~/.zshrc* o *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="409a7-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="409a7-130">Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione `PATH` esistente.</span><span class="sxs-lookup"><span data-stu-id="409a7-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="409a7-131">Se non è inclusa alcuna istruzione `PATH`, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="409a7-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="409a7-132">Inoltre, aggiungere `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="409a7-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="409a7-133">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="409a7-133">Install with PowerShell automation</span></span>

<span data-ttu-id="409a7-134">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="409a7-134">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="409a7-135">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="409a7-135">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="409a7-136">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="409a7-136">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="409a7-137">È possibile scegliere una versione specifica specificando l'opzione `Channel`.</span><span class="sxs-lookup"><span data-stu-id="409a7-137">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="409a7-138">Includere l'opzione `Runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="409a7-138">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="409a7-139">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="409a7-139">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="409a7-140">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="409a7-140">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="409a7-141">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="409a7-141">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="409a7-142">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="409a7-142">Install with bash automation</span></span>

<span data-ttu-id="409a7-143">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="409a7-143">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="409a7-144">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="409a7-144">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="409a7-145">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="409a7-145">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="409a7-146">È possibile scegliere una versione specifica specificando l'opzione `current`.</span><span class="sxs-lookup"><span data-stu-id="409a7-146">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="409a7-147">Includere l'opzione `runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="409a7-147">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="409a7-148">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="409a7-148">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="409a7-149">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="409a7-149">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="409a7-150">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="409a7-150">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="409a7-151">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="409a7-151">All .NET Core downloads</span></span>

<span data-ttu-id="409a7-152">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="409a7-152">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="409a7-153">Download di .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="409a7-153">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="409a7-154">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="409a7-154">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="409a7-155">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="409a7-155">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="409a7-156">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="409a7-156">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="409a7-157">Docker</span><span class="sxs-lookup"><span data-stu-id="409a7-157">Docker</span></span>

<span data-ttu-id="409a7-158">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="409a7-158">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="409a7-159">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="409a7-159">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="409a7-160">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="409a7-160">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="409a7-161">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="409a7-161">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="409a7-162">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="409a7-162">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="409a7-163">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="409a7-163">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="409a7-164">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="409a7-164">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="409a7-165">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="409a7-165">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="409a7-166">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="409a7-166">Next steps</span></span>

- <span data-ttu-id="409a7-167">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="409a7-167">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
