---
title: Installare .NET Core SDK in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per lo sviluppo di app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 290bdfb05b328bb311e6ff5ef493048b05985899
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801944"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="94e94-104">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="94e94-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="94e94-105">In questo articolo si apprenderà come installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="94e94-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="94e94-106">Il .NET Core SDK viene usato per creare le app e le librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="94e94-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="94e94-107">Il runtime di .NET Core viene sempre installato con l'SDK.</span><span class="sxs-lookup"><span data-stu-id="94e94-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="94e94-108">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="94e94-108">Install with an installer</span></span>

<span data-ttu-id="94e94-109">Windows dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,0 SDK:</span><span class="sxs-lookup"><span data-stu-id="94e94-109">Windows has standalone installers that can be used to install the .NET Core 3.0 SDK:</span></span>

- [<span data-ttu-id="94e94-110">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="94e94-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0) 
- [<span data-ttu-id="94e94-111">CPU x86 (32 bit)</span><span class="sxs-lookup"><span data-stu-id="94e94-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="94e94-112">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="94e94-112">Install with an installer</span></span>

<span data-ttu-id="94e94-113">macOS dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,0 SDK:</span><span class="sxs-lookup"><span data-stu-id="94e94-113">macOS has standalone installers that can be used to install the .NET Core 3.0 SDK:</span></span>

- [<span data-ttu-id="94e94-114">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="94e94-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="94e94-115">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="94e94-115">Install with a package manager</span></span>

<span data-ttu-id="94e94-116">È possibile installare il .NET Core SDK con molti dei gestori di pacchetti Linux comuni.</span><span class="sxs-lookup"><span data-stu-id="94e94-116">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="94e94-117">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-managers.md)).</span><span class="sxs-lookup"><span data-stu-id="94e94-117">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="94e94-118">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="94e94-118">Download and manually install</span></span>

<span data-ttu-id="94e94-119">Per estrarre l'SDK e rendere disponibili i comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="94e94-119">To extract the SDK and make the commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="94e94-120">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="94e94-120">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.0.101-linux-musl-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="94e94-121">I comandi precedenti comunicheranno solo i comandi .NET SDK disponibili per la sessione terminal in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="94e94-121">The above commands will only make the .NET SDK commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="94e94-122">È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="94e94-122">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="94e94-123">Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso.</span><span class="sxs-lookup"><span data-stu-id="94e94-123">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="94e94-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="94e94-124">For example:</span></span>
>
> - <span data-ttu-id="94e94-125">**Shell bash**: *~/. bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="94e94-125">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="94e94-126">**Korn Shell**: *~/.KSHRC* o *. profile*</span><span class="sxs-lookup"><span data-stu-id="94e94-126">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="94e94-127">**Shell Z**: *~/.zshrc* o *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="94e94-127">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="94e94-128">Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione `PATH` esistente.</span><span class="sxs-lookup"><span data-stu-id="94e94-128">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="94e94-129">Se non è inclusa alcuna istruzione `PATH`, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="94e94-129">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="94e94-130">Inoltre, aggiungere `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="94e94-130">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="94e94-131">Eseguire l'installazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94e94-131">Install with Visual Studio</span></span>

<span data-ttu-id="94e94-132">Se si usa Visual Studio per sviluppare app .NET Core, nella tabella seguente viene descritta la versione minima richiesta di Visual Studio in base alla versione .NET Core SDK di destinazione.</span><span class="sxs-lookup"><span data-stu-id="94e94-132">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="94e94-133">Versione .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="94e94-133">.NET Core SDK version</span></span> | <span data-ttu-id="94e94-134">Versione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="94e94-134">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="94e94-135">Anteprima 3,1</span><span class="sxs-lookup"><span data-stu-id="94e94-135">3.1 Preview</span></span>           | <span data-ttu-id="94e94-136">Visual Studio 2019 versione 16,4 Preview o successiva.</span><span class="sxs-lookup"><span data-stu-id="94e94-136">Visual Studio 2019 version 16.4 preview or higher.</span></span> |
| <span data-ttu-id="94e94-137">3.0</span><span class="sxs-lookup"><span data-stu-id="94e94-137">3.0</span></span>                   | <span data-ttu-id="94e94-138">Visual Studio 2019 versione 16,3 o successiva.</span><span class="sxs-lookup"><span data-stu-id="94e94-138">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="94e94-139">2.2</span><span class="sxs-lookup"><span data-stu-id="94e94-139">2.2</span></span>                   | <span data-ttu-id="94e94-140">Visual Studio 2017 versione 15,9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="94e94-140">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="94e94-141">2.1</span><span class="sxs-lookup"><span data-stu-id="94e94-141">2.1</span></span>                   | <span data-ttu-id="94e94-142">Visual Studio 2017 versione 15,7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="94e94-142">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="94e94-143">Se Visual Studio è già installato, è possibile controllare la versione con i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="94e94-143">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="94e94-144">Apri Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94e94-144">Open Visual Studio.</span></span>
01. <span data-ttu-id="94e94-145">Selezionare la **guida** > **informazioni su Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="94e94-145">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="94e94-146">Leggere il numero di versione dalla finestra **di dialogo informazioni su** .</span><span class="sxs-lookup"><span data-stu-id="94e94-146">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="94e94-147">Visual Studio è in grado di installare il .NET Core SDK e il runtime più recenti.</span><span class="sxs-lookup"><span data-stu-id="94e94-147">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="94e94-148">[Scaricare Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="94e94-148">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="94e94-149">Selezionare un carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="94e94-149">Select a workload</span></span>

<span data-ttu-id="94e94-150">Quando si installa o si modifica Visual Studio, selezionare uno dei carichi di lavoro seguenti, a seconda del tipo di applicazione che si sta compilando:</span><span class="sxs-lookup"><span data-stu-id="94e94-150">When installing or modifying Visual Studio, select one of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="94e94-151">Il carico di lavoro **sviluppo multipiattaforma .NET Core** nella sezione **altri set di strumenti** .</span><span class="sxs-lookup"><span data-stu-id="94e94-151">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="94e94-152">Il carico di lavoro di **sviluppo ASP.NET e Web** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="94e94-152">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="94e94-153">Il carico di lavoro **sviluppo di Azure** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="94e94-153">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="94e94-154">Il carico di lavoro **sviluppo per desktop .NET** nella sezione **Desktop & per dispositivi mobili** .</span><span class="sxs-lookup"><span data-stu-id="94e94-154">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="94e94-155">[![Windows Visual Studio 2019 con carico di lavoro .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="94e94-155">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="94e94-156">Installare con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="94e94-156">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="94e94-157">Visual Studio per Mac installa l'.NET Core SDK quando si seleziona il carico di lavoro di **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="94e94-157">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="94e94-158">Per iniziare a usare lo sviluppo di .NET Core in macOS, vedere [installare Visual Studio 2019 per Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="94e94-158">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

<span data-ttu-id="94e94-159">[![macOS Visual Studio 2019 per Mac con funzionalità di carico di lavoro .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="94e94-159">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="94e94-160">Installare insieme a Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="94e94-160">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="94e94-161">Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop.</span><span class="sxs-lookup"><span data-stu-id="94e94-161">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="94e94-162">Visual Studio Code è disponibile per Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="94e94-162">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="94e94-163">Anche se Visual Studio Code non dispone di un programma di installazione di .NET Core automatizzato come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.</span><span class="sxs-lookup"><span data-stu-id="94e94-163">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="94e94-164">[Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="94e94-164">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="94e94-165">[Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="94e94-165">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="94e94-166">[Installare l' C# estensione dal Marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="94e94-166">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="94e94-167">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="94e94-167">Install with PowerShell automation</span></span>

<span data-ttu-id="94e94-168">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="94e94-168">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="94e94-169">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-169">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="94e94-170">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="94e94-170">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="94e94-171">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="94e94-171">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="94e94-172">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="94e94-172">Install with bash automation</span></span>

<span data-ttu-id="94e94-173">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="94e94-173">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="94e94-174">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-174">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="94e94-175">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="94e94-175">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="94e94-176">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="94e94-176">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="94e94-177">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="94e94-177">All .NET Core downloads</span></span>

<span data-ttu-id="94e94-178">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="94e94-178">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="94e94-179">Download di .NET Core 3,1 Preview</span><span class="sxs-lookup"><span data-stu-id="94e94-179">.NET Core 3.1 Preview downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="94e94-180">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="94e94-180">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="94e94-181">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="94e94-181">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="94e94-182">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="94e94-182">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="94e94-183">Docker</span><span class="sxs-lookup"><span data-stu-id="94e94-183">Docker</span></span>

<span data-ttu-id="94e94-184">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="94e94-184">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="94e94-185">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="94e94-185">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="94e94-186">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="94e94-186">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="94e94-187">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="94e94-187">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="94e94-188">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="94e94-188">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="94e94-189">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="94e94-189">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="94e94-190">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="94e94-190">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="94e94-191">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-191">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="94e94-192">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="94e94-192">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="94e94-193">[Esercitazione: C# Hello World esercitazione](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-193">[Tutorial: C# Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="94e94-194">[Esercitazione: Visual Basic Hello World esercitazione](../tutorials/vb-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-194">[Tutorial: Visual Basic Hello World tutorial](../tutorials/vb-with-visual-studio.md).</span></span>
- <span data-ttu-id="94e94-195">[Esercitazione: creare una nuova app con Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span><span class="sxs-lookup"><span data-stu-id="94e94-195">[Tutorial: Create a new app with Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span></span>
- <span data-ttu-id="94e94-196">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-196">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="94e94-197">[Esercitazione: Introduzione a MacOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-197">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="94e94-198">[Esercitazione: creare una nuova app con Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span><span class="sxs-lookup"><span data-stu-id="94e94-198">[Tutorial: Create a new app with Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span></span>
- <span data-ttu-id="94e94-199">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="94e94-199">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
