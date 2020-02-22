---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ba50eb222d9eab6bffbb8ebfdf0ecf47951ce719
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543521"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="45d83-104">Installare il runtime di .NET Core</span><span class="sxs-lookup"><span data-stu-id="45d83-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="45d83-105">In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="45d83-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="45d83-106">Il runtime di .NET Core viene usato per eseguire app create con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="45d83-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="45d83-107">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="45d83-107">Install with an installer</span></span>

<span data-ttu-id="45d83-108">Windows dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="45d83-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="45d83-109">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="45d83-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="45d83-110">CPU x86 (32 bit)</span><span class="sxs-lookup"><span data-stu-id="45d83-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="45d83-111">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="45d83-111">Install with an installer</span></span>

<span data-ttu-id="45d83-112">macOS dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:</span><span class="sxs-lookup"><span data-stu-id="45d83-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="45d83-113">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="45d83-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="45d83-114">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="45d83-114">Install with a package manager</span></span>

<span data-ttu-id="45d83-115">È possibile installare il runtime di .NET Core con molti dei comuni gestori di pacchetti Linux.</span><span class="sxs-lookup"><span data-stu-id="45d83-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="45d83-116">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-managers.md)).</span><span class="sxs-lookup"><span data-stu-id="45d83-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="45d83-117">L'installazione con gestione pacchetti è supportata solo nell'architettura x64.</span><span class="sxs-lookup"><span data-stu-id="45d83-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="45d83-118">Se si sta installando il runtime di .NET Core con un'architettura diversa, ad esempio ARM, seguire le istruzioni nella sezione [download e installazione manuale](#download-and-manually-install) .</span><span class="sxs-lookup"><span data-stu-id="45d83-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="45d83-119">Per altre informazioni sulle architetture supportate, vedere [dipendenze e requisiti di .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="45d83-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="45d83-120">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="45d83-120">Download and manually install</span></span>

<span data-ttu-id="45d83-121">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="45d83-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="45d83-122">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="45d83-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="45d83-123">I comandi di `export` precedenti rendono disponibili solo i comandi interfaccia della riga di comando di .NET Core per la sessione terminal in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="45d83-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="45d83-124">È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="45d83-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="45d83-125">Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso.</span><span class="sxs-lookup"><span data-stu-id="45d83-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="45d83-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="45d83-126">For example:</span></span>
>
> - <span data-ttu-id="45d83-127">**Shell bash**: *~/. bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="45d83-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="45d83-128">**Korn Shell**: *~/.KSHRC* o *. profile*</span><span class="sxs-lookup"><span data-stu-id="45d83-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="45d83-129">**Shell Z**: *~/.zshrc* o *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="45d83-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="45d83-130">Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione `PATH` esistente.</span><span class="sxs-lookup"><span data-stu-id="45d83-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="45d83-131">Se non è inclusa alcuna istruzione `PATH`, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="45d83-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="45d83-132">Inoltre, aggiungere `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="45d83-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="45d83-133">Questo approccio consente di installare diverse versioni in posizioni separate e scegliere in modo esplicito quello da usare per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45d83-133">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="45d83-134">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="45d83-134">Install with PowerShell automation</span></span>

<span data-ttu-id="45d83-135">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="45d83-135">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="45d83-136">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="45d83-136">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="45d83-137">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="45d83-137">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="45d83-138">È possibile scegliere una versione specifica specificando l'opzione `Channel`.</span><span class="sxs-lookup"><span data-stu-id="45d83-138">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="45d83-139">Includere l'opzione `Runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="45d83-139">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="45d83-140">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="45d83-140">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="45d83-141">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="45d83-141">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="45d83-142">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="45d83-142">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="45d83-143">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="45d83-143">Download and manually install</span></span>

<span data-ttu-id="45d83-144">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="45d83-144">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="45d83-145">Quindi, creare una directory in cui eseguire l'installazione, ad esempio `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="45d83-145">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="45d83-146">Estrarre infine il file zip scaricato in tale directory.</span><span class="sxs-lookup"><span data-stu-id="45d83-146">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="45d83-147">Per impostazione predefinita, i comandi e le app di interfaccia della riga di comando di .NET Core non useranno .NET Core installato in questo modo.</span><span class="sxs-lookup"><span data-stu-id="45d83-147">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="45d83-148">È necessario scegliere esplicitamente di usarlo.</span><span class="sxs-lookup"><span data-stu-id="45d83-148">You have to explicitly choose to use it.</span></span> <span data-ttu-id="45d83-149">A tale scopo, modificare le variabili di ambiente con cui viene avviata un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="45d83-149">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="45d83-150">Questo approccio consente di installare più versioni in posizioni separate, quindi scegliere in modo esplicito il percorso di installazione che un'applicazione deve usare eseguendo l'applicazione con le variabili di ambiente che puntano a tale posizione.</span><span class="sxs-lookup"><span data-stu-id="45d83-150">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="45d83-151">Anche quando queste variabili di ambiente sono impostate, .NET Core considera ancora il percorso di installazione globale predefinito quando si seleziona il Framework migliore per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45d83-151">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="45d83-152">Il valore predefinito è in genere `C:\Program Files\dotnet`, che vengono utilizzati dai programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="45d83-152">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="45d83-153">È possibile indicare al runtime di usare solo il percorso di installazione personalizzato impostando anche questa variabile di ambiente:</span><span class="sxs-lookup"><span data-stu-id="45d83-153">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="45d83-154">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="45d83-154">Install with bash automation</span></span>

<span data-ttu-id="45d83-155">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime.</span><span class="sxs-lookup"><span data-stu-id="45d83-155">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="45d83-156">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="45d83-156">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="45d83-157">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="45d83-157">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="45d83-158">È possibile scegliere una versione specifica specificando l'opzione `current`.</span><span class="sxs-lookup"><span data-stu-id="45d83-158">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="45d83-159">Includere l'opzione `runtime` per installare un Runtime.</span><span class="sxs-lookup"><span data-stu-id="45d83-159">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="45d83-160">In caso contrario, lo script installa l' [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="45d83-160">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="45d83-161">Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità.</span><span class="sxs-lookup"><span data-stu-id="45d83-161">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="45d83-162">Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.</span><span class="sxs-lookup"><span data-stu-id="45d83-162">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="45d83-163">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="45d83-163">All .NET Core downloads</span></span>

<span data-ttu-id="45d83-164">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="45d83-164">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="45d83-165">Download di .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="45d83-165">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="45d83-166">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="45d83-166">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="45d83-167">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="45d83-167">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="45d83-168">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="45d83-168">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="45d83-169">Docker</span><span class="sxs-lookup"><span data-stu-id="45d83-169">Docker</span></span>

<span data-ttu-id="45d83-170">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="45d83-170">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="45d83-171">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="45d83-171">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="45d83-172">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="45d83-172">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="45d83-173">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="45d83-173">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="45d83-174">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="45d83-174">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="45d83-175">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="45d83-175">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="45d83-176">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="45d83-176">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="45d83-177">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="45d83-177">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="45d83-178">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="45d83-178">Next steps</span></span>

- <span data-ttu-id="45d83-179">[Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="45d83-179">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
