---
title: Installare .NET Core SDK in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per lo sviluppo di app .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a11d1eb3bae6affaa548407cbd68c166a30e99da
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324661"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="2e0ec-104">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="2e0ec-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="2e0ec-105">In questo articolo si apprenderà come installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="2e0ec-106">Il .NET Core SDK viene usato per creare le app e le librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="2e0ec-107">Il runtime di .NET Core viene sempre installato con l'SDK.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="2e0ec-108">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="2e0ec-108">Install with an installer</span></span>

<span data-ttu-id="2e0ec-109">Windows dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,1 SDK:</span><span class="sxs-lookup"><span data-stu-id="2e0ec-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="2e0ec-110">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="2e0ec-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="2e0ec-111">CPU x86 (32 bit)</span><span class="sxs-lookup"><span data-stu-id="2e0ec-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="2e0ec-112">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="2e0ec-112">Install with an installer</span></span>

<span data-ttu-id="2e0ec-113">macOS dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,1 SDK:</span><span class="sxs-lookup"><span data-stu-id="2e0ec-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="2e0ec-114">CPU x64 (64 bit)</span><span class="sxs-lookup"><span data-stu-id="2e0ec-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="2e0ec-115">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="2e0ec-115">Download and manually install</span></span>

<span data-ttu-id="2e0ec-116">In alternativa ai programmi di installazione di macOS per .NET Core, è possibile scaricare e installare manualmente l'SDK.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="2e0ec-117">Per estrarre l'SDK e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="2e0ec-118">Quindi, aprire un terminale ed eseguire i comandi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="2e0ec-119">Si presuppone che il runtime venga scaricato nel `~/Downloads/dotnet-sdk.pkg` file.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="2e0ec-120">Installare in Linux</span><span class="sxs-lookup"><span data-stu-id="2e0ec-120">Install on Linux</span></span>

<span data-ttu-id="2e0ec-121">Questo articolo verrà rimosso a breve.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-121">This article will be removed soon.</span></span> <span data-ttu-id="2e0ec-122">Attualmente viene sostituito da [installare .NET Core in Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-122">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="2e0ec-123">Eseguire l'installazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e0ec-123">Install with Visual Studio</span></span>

<span data-ttu-id="2e0ec-124">Se si usa Visual Studio per sviluppare app .NET Core, nella tabella seguente viene descritta la versione minima richiesta di Visual Studio in base alla versione .NET Core SDK di destinazione.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-124">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="2e0ec-125">Versione .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="2e0ec-125">.NET Core SDK version</span></span> | <span data-ttu-id="2e0ec-126">Versione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2e0ec-126">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="2e0ec-127">3.1</span><span class="sxs-lookup"><span data-stu-id="2e0ec-127">3.1</span></span>                   | <span data-ttu-id="2e0ec-128">Visual Studio 2019 versione 16,4 o successiva.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-128">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="2e0ec-129">3.0</span><span class="sxs-lookup"><span data-stu-id="2e0ec-129">3.0</span></span>                   | <span data-ttu-id="2e0ec-130">Visual Studio 2019 versione 16,3 o successiva.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-130">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="2e0ec-131">2.2</span><span class="sxs-lookup"><span data-stu-id="2e0ec-131">2.2</span></span>                   | <span data-ttu-id="2e0ec-132">Visual Studio 2017 versione 15,9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-132">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="2e0ec-133">2.1</span><span class="sxs-lookup"><span data-stu-id="2e0ec-133">2.1</span></span>                   | <span data-ttu-id="2e0ec-134">Visual Studio 2017 versione 15,7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-134">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="2e0ec-135">Se Visual Studio è già installato, è possibile controllare la versione con i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-135">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="2e0ec-136">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-136">Open Visual Studio.</span></span>
01. <span data-ttu-id="2e0ec-137">Selezionare la **Guida**  >  **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-137">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="2e0ec-138">Leggere il numero di versione dalla finestra **di dialogo informazioni su** .</span><span class="sxs-lookup"><span data-stu-id="2e0ec-138">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="2e0ec-139">Visual Studio è in grado di installare il .NET Core SDK e il runtime più recenti.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-139">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="2e0ec-140">[Scaricare Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-140">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="2e0ec-141">Selezionare un carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="2e0ec-141">Select a workload</span></span>

<span data-ttu-id="2e0ec-142">Quando si installa o si modifica Visual Studio, selezionare uno o più dei carichi di lavoro seguenti, a seconda del tipo di applicazione che si sta compilando:</span><span class="sxs-lookup"><span data-stu-id="2e0ec-142">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="2e0ec-143">Il carico di lavoro **sviluppo multipiattaforma .NET Core** nella sezione **altri set di strumenti** .</span><span class="sxs-lookup"><span data-stu-id="2e0ec-143">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="2e0ec-144">Il carico di lavoro di **sviluppo ASP.NET e Web** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="2e0ec-144">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="2e0ec-145">Il carico di lavoro **sviluppo di Azure** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="2e0ec-145">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="2e0ec-146">Il carico di lavoro **sviluppo per desktop .NET** nella sezione **Desktop & per dispositivi mobili** .</span><span class="sxs-lookup"><span data-stu-id="2e0ec-146">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="2e0ec-147">[![Windows Visual Studio 2019 con carico di lavoro .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2e0ec-147">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="2e0ec-148">Scaricare e installare manualmente</span><span class="sxs-lookup"><span data-stu-id="2e0ec-148">Download and manually install</span></span>

<span data-ttu-id="2e0ec-149">Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="2e0ec-150">Quindi, creare una directory in cui eseguire l'installazione, ad esempio `%USERPROFILE%\dotnet` .</span><span class="sxs-lookup"><span data-stu-id="2e0ec-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="2e0ec-151">Estrarre infine il file zip scaricato in tale directory.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="2e0ec-152">Per impostazione predefinita, i comandi e le app di interfaccia della riga di comando di .NET Core non usano .NET Core installato in questo modo ed è necessario scegliere esplicitamente di usarlo.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-152">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="2e0ec-153">A tale scopo, modificare le variabili di ambiente con cui viene avviata un'applicazione:</span><span class="sxs-lookup"><span data-stu-id="2e0ec-153">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="2e0ec-154">Questo approccio consente di installare più versioni in posizioni separate, quindi scegliere in modo esplicito il percorso di installazione che un'applicazione deve usare eseguendo l'applicazione con le variabili di ambiente che puntano a tale posizione.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-154">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="2e0ec-155">Anche quando queste variabili di ambiente sono impostate, .NET Core considera ancora il percorso di installazione globale predefinito quando si seleziona il Framework migliore per l'esecuzione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-155">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="2e0ec-156">Il valore predefinito è in genere `C:\Program Files\dotnet` usato dai programmi di installazione.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-156">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="2e0ec-157">È possibile indicare al runtime di usare solo il percorso di installazione personalizzato impostando anche questa variabile di ambiente:</span><span class="sxs-lookup"><span data-stu-id="2e0ec-157">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="2e0ec-158">Installare con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="2e0ec-158">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="2e0ec-159">Visual Studio per Mac installa l'.NET Core SDK quando si seleziona il carico di lavoro di **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="2e0ec-159">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="2e0ec-160">Per iniziare a usare lo sviluppo di .NET Core in macOS, vedere [installare Visual Studio 2019 per Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-160">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="2e0ec-161">Per la versione più recente, .NET Core 3,1, è necessario usare l'anteprima Visual Studio per Mac 8,4.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-161">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="2e0ec-162">[![macOS Visual Studio 2019 per Mac con funzionalità di carico di lavoro .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="2e0ec-162">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-windows,os-macos"

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="2e0ec-163">Installare insieme a Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2e0ec-163">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="2e0ec-164">Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-164">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="2e0ec-165">Visual Studio Code è disponibile per Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-165">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="2e0ec-166">Anche se Visual Studio Code non dispone di un programma di installazione di .NET Core automatizzato come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-166">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="2e0ec-167">[Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-167">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="2e0ec-168">[Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-168">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="2e0ec-169">[Installare l'estensione C# dal marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-169">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="2e0ec-170">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e0ec-170">Install with PowerShell automation</span></span>

<span data-ttu-id="2e0ec-171">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-171">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="2e0ec-172">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-172">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="2e0ec-173">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-173">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="2e0ec-174">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-174">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="2e0ec-175">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="2e0ec-175">Install with bash automation</span></span>

<span data-ttu-id="2e0ec-176">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-176">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="2e0ec-177">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-177">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="2e0ec-178">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-178">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="2e0ec-179">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-179">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="2e0ec-180">Tutti i download di .NET Core</span><span class="sxs-lookup"><span data-stu-id="2e0ec-180">All .NET Core downloads</span></span>

<span data-ttu-id="2e0ec-181">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e0ec-181">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="2e0ec-182">Download di .NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="2e0ec-182">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="2e0ec-183">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="2e0ec-183">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="2e0ec-184">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="2e0ec-184">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="2e0ec-185">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="2e0ec-185">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="2e0ec-186">Docker</span><span class="sxs-lookup"><span data-stu-id="2e0ec-186">Docker</span></span>

<span data-ttu-id="2e0ec-187">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-187">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="2e0ec-188">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-188">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="2e0ec-189">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-189">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="2e0ec-190">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-190">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="2e0ec-191">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-191">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="2e0ec-192">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-192">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="2e0ec-193">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="2e0ec-193">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="2e0ec-194">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-194">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2e0ec-195">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2e0ec-195">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="2e0ec-196">[Esercitazione: Hello World esercitazione](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-196">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="2e0ec-197">[Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-197">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="2e0ec-198">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-198">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="2e0ec-199">[Uso dell'autenticazione di MacOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-199">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="2e0ec-200">[Esercitazione: Introduzione a MacOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-200">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="2e0ec-201">[Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="2e0ec-202">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="2e0ec-203">[Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-203">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="2e0ec-204">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="2e0ec-204">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
