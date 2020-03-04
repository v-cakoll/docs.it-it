---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a41bbdf5419585f06773583dbe82ab0d84ebaa4c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157636"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="f6139-104">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f6139-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="f6139-105">In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6139-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="f6139-106">Il runtime di .NET Core viene usato per eseguire app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6139-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="f6139-107">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="f6139-107">Install with an installer</span></span>

<span data-ttu-id="f6139-108">Windows dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="f6139-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="f6139-109">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="f6139-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="f6139-110">CPU x86 (32 bit)</span><span class="sxs-lookup"><span data-stu-id="f6139-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="f6139-111">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="f6139-111">Install with an installer</span></span>

<span data-ttu-id="f6139-112">macOS dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="f6139-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="f6139-113">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="f6139-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="f6139-114">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="f6139-114">Download and manually install</span></span>

<span data-ttu-id="f6139-115">In alternativa ai programmi di installazione di macOS per .NET Core, è possibile scaricare e installare manualmente il Runtime.</span><span class="sxs-lookup"><span data-stu-id="f6139-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="f6139-116">Per installare il runtime e abilitare i comandi interfaccia della riga di comando di .NET Core disponibili nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6139-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="f6139-117">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="f6139-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="f6139-118">Si presuppone che il runtime venga scaricato nel file di `~/Downloads/dotnet-runtime.pkg`.</span><span class="sxs-lookup"><span data-stu-id="f6139-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="f6139-119">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="f6139-119">Install with a package manager</span></span>

<span data-ttu-id="f6139-120">È possibile installare il runtime di .NET Core con molti dei comuni gestori di pacchetti Linux.</span><span class="sxs-lookup"><span data-stu-id="f6139-120">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="f6139-121">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-managers.md)).</span><span class="sxs-lookup"><span data-stu-id="f6139-121">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="f6139-122">L'installazione con gestione pacchetti è supportata solo nell'architettura x64.</span><span class="sxs-lookup"><span data-stu-id="f6139-122">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="f6139-123">Se si sta installando il runtime di .NET Core con un'architettura diversa, ad esempio ARM, seguire le istruzioni nella sezione [download e installazione manuale](#download-and-manually-install) .</span><span class="sxs-lookup"><span data-stu-id="f6139-123">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="f6139-124">Per altre informazioni sulle architetture supportate, vedere [dipendenze e requisiti di .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="f6139-124">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="f6139-125">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="f6139-125">Download and manually install</span></span>

<span data-ttu-id="f6139-126">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6139-126">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="f6139-127">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="f6139-127">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="f6139-128">I comandi di `export` precedenti rendono disponibili solo i comandi interfaccia della riga di comando di .NET Core per la sessione terminal in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="f6139-128">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="f6139-129">È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="f6139-129">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="f6139-130">Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso.</span><span class="sxs-lookup"><span data-stu-id="f6139-130">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="f6139-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f6139-131">For example:</span></span>
>
> - <span data-ttu-id="f6139-132">**Shell bash**: *~/. bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="f6139-132">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="f6139-133">**Korn Shell**: *~/.KSHRC* o *. profile*</span><span class="sxs-lookup"><span data-stu-id="f6139-133">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="f6139-134">**Shell Z**: *~/.zshrc* o *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="f6139-134">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="f6139-135">Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione `PATH` esistente.</span><span class="sxs-lookup"><span data-stu-id="f6139-135">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="f6139-136">Se non è inclusa alcuna istruzione `PATH`, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="f6139-136">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="f6139-137">Inoltre, aggiungere `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="f6139-137">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="f6139-138">Questo approccio consente di installare diverse versioni in posizioni separate e scegliere in modo esplicito quello da usare per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6139-138">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="f6139-139">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6139-139">Install with PowerShell automation</span></span>

<span data-ttu-id="f6139-140">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="f6139-140">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="f6139-141">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f6139-141">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="f6139-142">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="f6139-142">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="f6139-143">È possibile scegliere una versione specifica specificando l'opzione `Channel`.</span><span class="sxs-lookup"><span data-stu-id="f6139-143">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="f6139-144">Includere l'opzione `Runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="f6139-144">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="f6139-145">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="f6139-145">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="f6139-146">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="f6139-146">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="f6139-147">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="f6139-147">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="f6139-148">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="f6139-148">Download and manually install</span></span>

<span data-ttu-id="f6139-149">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6139-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="f6139-150">Quindi, creare una directory in cui eseguire l'installazione, ad esempio `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="f6139-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="f6139-151">Estrarre infine il file zip scaricato in tale directory.</span><span class="sxs-lookup"><span data-stu-id="f6139-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="f6139-152">Per impostazione predefinita, i comandi e le app di interfaccia della riga di comando di .NET Core non useranno .NET Core installato in questo modo.</span><span class="sxs-lookup"><span data-stu-id="f6139-152">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="f6139-153">È necessario scegliere esplicitamente di usarlo.</span><span class="sxs-lookup"><span data-stu-id="f6139-153">You have to explicitly choose to use it.</span></span> <span data-ttu-id="f6139-154">A tale scopo, modificare le variabili di ambiente con cui viene avviata un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="f6139-154">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="f6139-155">Questo approccio consente di installare più versioni in posizioni separate, quindi scegliere in modo esplicito il percorso di installazione che un'applicazione deve usare eseguendo l'applicazione con le variabili di ambiente che puntano a tale posizione.</span><span class="sxs-lookup"><span data-stu-id="f6139-155">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="f6139-156">Anche quando queste variabili di ambiente sono impostate, .NET Core considera ancora il percorso di installazione globale predefinito quando si seleziona il Framework migliore per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6139-156">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="f6139-157">Il valore predefinito è in genere `C:\Program Files\dotnet`, che vengono utilizzati dai programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="f6139-157">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="f6139-158">È possibile indicare al runtime di usare solo il percorso di installazione personalizzato impostando anche questa variabile di ambiente:</span><span class="sxs-lookup"><span data-stu-id="f6139-158">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="f6139-159">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="f6139-159">Install with bash automation</span></span>

<span data-ttu-id="f6139-160">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="f6139-160">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="f6139-161">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="f6139-161">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="f6139-162">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="f6139-162">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="f6139-163">È possibile scegliere una versione specifica specificando l'opzione `current`.</span><span class="sxs-lookup"><span data-stu-id="f6139-163">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="f6139-164">Includere l'opzione `runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="f6139-164">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="f6139-165">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="f6139-165">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="f6139-166">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="f6139-166">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="f6139-167">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="f6139-167">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="f6139-168">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="f6139-168">All .NET Core downloads</span></span>

<span data-ttu-id="f6139-169">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6139-169">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="f6139-170">Download di .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="f6139-170">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="f6139-171">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="f6139-171">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="f6139-172">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="f6139-172">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="f6139-173">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="f6139-173">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="f6139-174">Docker</span><span class="sxs-lookup"><span data-stu-id="f6139-174">Docker</span></span>

<span data-ttu-id="f6139-175">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="f6139-175">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="f6139-176">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f6139-176">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="f6139-177">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="f6139-177">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="f6139-178">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="f6139-178">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="f6139-179">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="f6139-179">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="f6139-180">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="f6139-180">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="f6139-181">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f6139-181">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="f6139-182">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="f6139-182">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6139-183">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f6139-183">Next steps</span></span>

- <span data-ttu-id="f6139-184">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="f6139-184">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
