---
title: Installare .NET Core SDK in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per lo sviluppo di app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 54819b409422e8bda9efe25478aa3424683a380b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567473"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="92251-104">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="92251-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="92251-105">In questo articolo si apprenderà come installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="92251-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="92251-106">Il .NET Core SDK viene usato per creare le app e le librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="92251-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="92251-107">Il runtime di .NET Core viene sempre installato con l'SDK.</span><span class="sxs-lookup"><span data-stu-id="92251-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows,os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="92251-108">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="92251-108">Install with an installer</span></span>

<span data-ttu-id="92251-109">Sia Windows che macOS hanno programmi di installazione autonomi che possono essere usati per installare .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="92251-109">Both Windows and macOS have standalone installers that can be used to install the .NET Core 3.0 SDK.</span></span>

- <span data-ttu-id="92251-110">[CPU Windows x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.0) | [cpu x86 (32-bit)](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span><span class="sxs-lookup"><span data-stu-id="92251-110">Windows [x64 (64-bit) CPUs](https://dotnet.microsoft.com/download/dotnet-core/3.0) | [x86 (32-bit) CPUs](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span></span>
- <span data-ttu-id="92251-111">[CPU MacOS x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span><span class="sxs-lookup"><span data-stu-id="92251-111">macOS [x64 (64-bit) CPUs](https://dotnet.microsoft.com/download/dotnet-core/3.0)</span></span>

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="92251-112">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="92251-112">Install with a package manager</span></span>

<span data-ttu-id="92251-113">È possibile installare il .NET Core SDK con molti dei gestori di pacchetti Linux comuni.</span><span class="sxs-lookup"><span data-stu-id="92251-113">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="92251-114">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-managers.md)).</span><span class="sxs-lookup"><span data-stu-id="92251-114">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="92251-115">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="92251-115">Download and manually install</span></span>

<span data-ttu-id="92251-116">Per estrarre l'SDK e rendere disponibili i comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="92251-116">To extract the SDK and make the commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="92251-117">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="92251-117">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.0.101-linux-musl-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="92251-118">I comandi precedenti comunicheranno solo i comandi .NET SDK disponibili per la sessione terminal in cui è stata eseguita.</span><span class="sxs-lookup"><span data-stu-id="92251-118">The above commands will only make the .NET SDK commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="92251-119">È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente.</span><span class="sxs-lookup"><span data-stu-id="92251-119">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="92251-120">Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso.</span><span class="sxs-lookup"><span data-stu-id="92251-120">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="92251-121">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="92251-121">For example:</span></span>
>
> - <span data-ttu-id="92251-122">**Shell bash**: *~/. bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="92251-122">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="92251-123">**Korn Shell**: *~/.KSHRC* o *. profile*</span><span class="sxs-lookup"><span data-stu-id="92251-123">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="92251-124">**Shell Z**: *~/.zshrc* o *. zprofile*</span><span class="sxs-lookup"><span data-stu-id="92251-124">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="92251-125">Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione `PATH` esistente.</span><span class="sxs-lookup"><span data-stu-id="92251-125">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="92251-126">Se non è inclusa alcuna istruzione `PATH`, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="92251-126">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="92251-127">Inoltre, aggiungere `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.</span><span class="sxs-lookup"><span data-stu-id="92251-127">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="92251-128">Eseguire l'installazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92251-128">Install with Visual Studio</span></span>

<span data-ttu-id="92251-129">Se si usa Visual Studio per sviluppare app .NET Core, nella tabella seguente viene descritta la versione minima richiesta di Visual Studio in base alla versione .NET Core SDK di destinazione.</span><span class="sxs-lookup"><span data-stu-id="92251-129">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="92251-130">Versione .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="92251-130">.NET Core SDK version</span></span> | <span data-ttu-id="92251-131">Versione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="92251-131">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="92251-132">Anteprima 3,1</span><span class="sxs-lookup"><span data-stu-id="92251-132">3.1 Preview</span></span>           | <span data-ttu-id="92251-133">Visual Studio 2019 versione 16,4 Preview o successiva.</span><span class="sxs-lookup"><span data-stu-id="92251-133">Visual Studio 2019 version 16.4 preview or higher.</span></span> |
| <span data-ttu-id="92251-134">3.0</span><span class="sxs-lookup"><span data-stu-id="92251-134">3.0</span></span>                   | <span data-ttu-id="92251-135">Visual Studio 2019 versione 16,3 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92251-135">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="92251-136">2.2</span><span class="sxs-lookup"><span data-stu-id="92251-136">2.2</span></span>                   | <span data-ttu-id="92251-137">Visual Studio 2017 versione 15,9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92251-137">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="92251-138">2.1</span><span class="sxs-lookup"><span data-stu-id="92251-138">2.1</span></span>                   | <span data-ttu-id="92251-139">Visual Studio 2017 versione 15,7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="92251-139">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="92251-140">Se Visual Studio è già installato, è possibile controllare la versione con i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="92251-140">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="92251-141">Apri Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="92251-141">Open Visual Studio.</span></span>
01. <span data-ttu-id="92251-142">Selezionare la **guida** > **informazioni su Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="92251-142">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="92251-143">Leggere il numero di versione dalla finestra **di dialogo informazioni su** .</span><span class="sxs-lookup"><span data-stu-id="92251-143">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="92251-144">Visual Studio è in grado di installare il .NET Core SDK e il runtime più recenti.</span><span class="sxs-lookup"><span data-stu-id="92251-144">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="92251-145">[Scaricare Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="92251-145">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="92251-146">Selezionare un carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="92251-146">Select a workload</span></span>

<span data-ttu-id="92251-147">Quando si installa o si modifica Visual Studio, selezionare uno dei carichi di lavoro seguenti, a seconda del tipo di applicazione che si sta compilando:</span><span class="sxs-lookup"><span data-stu-id="92251-147">When installing or modifying Visual Studio, select one of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="92251-148">Il carico di lavoro **sviluppo multipiattaforma .NET Core** nella sezione **altri set di strumenti** .</span><span class="sxs-lookup"><span data-stu-id="92251-148">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="92251-149">Il carico di lavoro di **sviluppo ASP.NET e Web** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="92251-149">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="92251-150">Il carico di lavoro **sviluppo di Azure** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="92251-150">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="92251-151">Il carico di lavoro **sviluppo per desktop .NET** nella sezione **Desktop & per dispositivi mobili** .</span><span class="sxs-lookup"><span data-stu-id="92251-151">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="92251-152">[![Windows Visual Studio 2019 con carico di lavoro .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="92251-152">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="92251-153">Installare con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="92251-153">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="92251-154">Visual Studio per Mac installa l'.NET Core SDK quando si seleziona il carico di lavoro di **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="92251-154">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="92251-155">Per iniziare a usare lo sviluppo di .NET Core in macOS, vedere [installare Visual Studio 2019 per Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="92251-155">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

<span data-ttu-id="92251-156">[![macOS Visual Studio 2019 per Mac con funzionalità di carico di lavoro .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="92251-156">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="92251-157">Installare insieme a Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="92251-157">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="92251-158">Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop.</span><span class="sxs-lookup"><span data-stu-id="92251-158">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="92251-159">Visual Studio Code è disponibile per Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="92251-159">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="92251-160">Anche se Visual Studio Code non dispone di un programma di installazione di .NET Core automatizzato come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.</span><span class="sxs-lookup"><span data-stu-id="92251-160">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="92251-161">[Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="92251-161">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="92251-162">[Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="92251-162">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="92251-163">[Installare l' C# estensione dal Marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="92251-163">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="92251-164">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="92251-164">Install with PowerShell automation</span></span>

<span data-ttu-id="92251-165">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="92251-165">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="92251-166">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="92251-166">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="92251-167">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="92251-167">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="92251-168">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="92251-168">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="92251-169">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="92251-169">Install with bash automation</span></span>

<span data-ttu-id="92251-170">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="92251-170">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="92251-171">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="92251-171">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="92251-172">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="92251-172">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="92251-173">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="92251-173">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="92251-174">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="92251-174">All .NET Core downloads</span></span>

<span data-ttu-id="92251-175">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="92251-175">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="92251-176">Download di .NET Core 3,1 Preview</span><span class="sxs-lookup"><span data-stu-id="92251-176">.NET Core 3.1 Preview downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="92251-177">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="92251-177">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="92251-178">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="92251-178">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="92251-179">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="92251-179">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="92251-180">Docker</span><span class="sxs-lookup"><span data-stu-id="92251-180">Docker</span></span>

<span data-ttu-id="92251-181">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="92251-181">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="92251-182">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92251-182">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="92251-183">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="92251-183">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="92251-184">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="92251-184">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="92251-185">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="92251-185">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="92251-186">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="92251-186">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="92251-187">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="92251-187">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="92251-188">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="92251-188">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="92251-189">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="92251-189">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="92251-190">[Esercitazione: C# Hello World esercitazione](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="92251-190">[Tutorial: C# Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="92251-191">[Esercitazione: Visual Basic Hello World esercitazione](../tutorials/vb-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="92251-191">[Tutorial: Visual Basic Hello World tutorial](../tutorials/vb-with-visual-studio.md).</span></span>
- <span data-ttu-id="92251-192">[Esercitazione: creare una nuova app con Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span><span class="sxs-lookup"><span data-stu-id="92251-192">[Tutorial: Create a new app with Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span></span>
- <span data-ttu-id="92251-193">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="92251-193">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="92251-194">[Esercitazione: Introduzione a MacOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="92251-194">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="92251-195">[Esercitazione: creare una nuova app con Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span><span class="sxs-lookup"><span data-stu-id="92251-195">[Tutorial: Create a new app with Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span></span>
- <span data-ttu-id="92251-196">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="92251-196">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
