---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 6a0390ff1db900815628e4c7eb69e7a6c5f148a8
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324600"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="a2d0e-104">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a2d0e-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="a2d0e-105">In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="a2d0e-106">Il runtime di .NET Core viene usato per eseguire app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="a2d0e-107">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="a2d0e-107">Install with an installer</span></span>

<span data-ttu-id="a2d0e-108">Windows dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="a2d0e-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="a2d0e-109">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="a2d0e-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="a2d0e-110">CPU x86 (32 bit)</span><span class="sxs-lookup"><span data-stu-id="a2d0e-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="a2d0e-111">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="a2d0e-111">Install with an installer</span></span>

<span data-ttu-id="a2d0e-112">macOS dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="a2d0e-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="a2d0e-113">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="a2d0e-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="a2d0e-114">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="a2d0e-114">Download and manually install</span></span>

<span data-ttu-id="a2d0e-115">In alternativa ai programmi di installazione di macOS per .NET Core, è possibile scaricare e installare manualmente il Runtime.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="a2d0e-116">Per installare il runtime e abilitare i comandi interfaccia della riga di comando di .NET Core disponibili nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="a2d0e-117">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="a2d0e-118">Si presuppone che il runtime venga scaricato nel `~/Downloads/dotnet-runtime.pkg` file.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="a2d0e-119">Installare in Linux</span><span class="sxs-lookup"><span data-stu-id="a2d0e-119">Install on Linux</span></span>

<span data-ttu-id="a2d0e-120">Questo articolo verrà rimosso a breve.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-120">This article will be removed soon.</span></span> <span data-ttu-id="a2d0e-121">Attualmente viene sostituito da [installare .NET Core in Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-121">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="a2d0e-122">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2d0e-122">Install with PowerShell automation</span></span>

<span data-ttu-id="a2d0e-123">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-123">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="a2d0e-124">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-124">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="a2d0e-125">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-125">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="a2d0e-126">È possibile scegliere una versione specifica specificando l' `Channel` opzione.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-126">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="a2d0e-127">Includere l' `Runtime` opzione per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-127">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="a2d0e-128">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-128">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="a2d0e-129">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-129">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="a2d0e-130">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-130">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="a2d0e-131">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="a2d0e-131">Download and manually install</span></span>

<span data-ttu-id="a2d0e-132">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-132">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="a2d0e-133">Quindi, creare una directory in cui eseguire l'installazione, ad esempio `%USERPROFILE%\dotnet` .</span><span class="sxs-lookup"><span data-stu-id="a2d0e-133">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="a2d0e-134">Estrarre infine il file zip scaricato in tale directory.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-134">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="a2d0e-135">Per impostazione predefinita, i comandi e le app di interfaccia della riga di comando di .NET Core non usano .NET Core installato in questo modo ed è necessario scegliere esplicitamente di usarlo.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-135">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="a2d0e-136">A tale scopo, modificare le variabili di ambiente con cui viene avviata un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="a2d0e-136">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="a2d0e-137">Questo approccio consente di installare più versioni in posizioni separate, quindi scegliere in modo esplicito il percorso di installazione che un'applicazione deve usare eseguendo l'applicazione con le variabili di ambiente che puntano a tale posizione.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-137">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="a2d0e-138">Anche quando queste variabili di ambiente sono impostate, .NET Core considera ancora il percorso di installazione globale predefinito quando si seleziona il Framework migliore per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-138">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="a2d0e-139">Il valore predefinito è in genere `C:\Program Files\dotnet` usato dai programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-139">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="a2d0e-140">È possibile indicare al runtime di usare solo il percorso di installazione personalizzato impostando anche questa variabile di ambiente:</span><span class="sxs-lookup"><span data-stu-id="a2d0e-140">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="a2d0e-141">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="a2d0e-141">Install with bash automation</span></span>

<span data-ttu-id="a2d0e-142">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-142">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="a2d0e-143">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-143">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="a2d0e-144">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-144">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="a2d0e-145">È possibile scegliere una versione specifica specificando l' `current` opzione.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-145">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="a2d0e-146">Includere l' `runtime` opzione per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-146">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="a2d0e-147">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-147">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="a2d0e-148">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-148">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="a2d0e-149">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-149">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="a2d0e-150">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="a2d0e-150">All .NET Core downloads</span></span>

<span data-ttu-id="a2d0e-151">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2d0e-151">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="a2d0e-152">Download di .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="a2d0e-152">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="a2d0e-153">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="a2d0e-153">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="a2d0e-154">Docker</span><span class="sxs-lookup"><span data-stu-id="a2d0e-154">Docker</span></span>

<span data-ttu-id="a2d0e-155">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-155">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="a2d0e-156">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-156">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="a2d0e-157">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-157">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="a2d0e-158">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-158">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="a2d0e-159">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-159">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="a2d0e-160">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-160">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="a2d0e-161">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="a2d0e-161">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="a2d0e-162">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-162">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2d0e-163">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a2d0e-163">Next steps</span></span>

- <span data-ttu-id="a2d0e-164">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="a2d0e-164">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
