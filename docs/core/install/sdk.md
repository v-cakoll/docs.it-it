---
title: Installare .NET Core SDK in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per lo sviluppo di app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 11/06/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 2f65e9dc39a4cd1076af1a70dfedfa671f20b42d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450877"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="3b26f-104">Installare il .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="3b26f-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="3b26f-105">In questo articolo si apprenderà come installare il .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3b26f-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="3b26f-106">Il .NET Core SDK viene usato per creare le app e le librerie .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b26f-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="3b26f-107">Il runtime di .NET Core viene sempre installato con l'SDK.</span><span class="sxs-lookup"><span data-stu-id="3b26f-107">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="3b26f-108">È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3b26f-108">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="3b26f-109">Download di .NET Core 3,1 Preview 3</span><span class="sxs-lookup"><span data-stu-id="3b26f-109">.NET Core 3.1 Preview 3 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="3b26f-110">Download di .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="3b26f-110">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="3b26f-111">Download di .NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="3b26f-111">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="3b26f-112">Download di .NET Core 2,1</span><span class="sxs-lookup"><span data-stu-id="3b26f-112">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

<span data-ttu-id="3b26f-113">È anche possibile installare .NET Core come parte di un Integrated Development Environment (IDE), descritto dettagliatamente nelle sezioni riportate di seguito.</span><span class="sxs-lookup"><span data-stu-id="3b26f-113">You can also install .NET Core as part of an integrated development environment (IDE), detailed in the sections below.</span></span>

## <a name="install-with-an-installer"></a><span data-ttu-id="3b26f-114">Eseguire l'installazione con un programma di installazione</span><span class="sxs-lookup"><span data-stu-id="3b26f-114">Install with an installer</span></span>

<span data-ttu-id="3b26f-115">Sia Windows che macOS hanno programmi di installazione autonomi che possono essere usati per installare .NET Core 3,0 SDK.</span><span class="sxs-lookup"><span data-stu-id="3b26f-115">Both Windows and macOS have standalone installers that can be used to install the .NET Core 3.0 SDK.</span></span>

- <span data-ttu-id="3b26f-116">CPU di Windows [x64](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-3.0.100-windows-x64-installer) | [x32 CPU](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-3.0.100-windows-x86-installer)</span><span class="sxs-lookup"><span data-stu-id="3b26f-116">Windows [x64 CPUs](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-3.0.100-windows-x64-installer) | [x32 CPUs](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-3.0.100-windows-x86-installer)</span></span>
- <span data-ttu-id="3b26f-117">[CPU MacOS x64](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-3.0.100-macos-x64-installer)</span><span class="sxs-lookup"><span data-stu-id="3b26f-117">macOS [x64 CPUs](https://dotnet.microsoft.com/download/thank-you/dotnet-sdk-3.0.100-macos-x64-installer)</span></span>

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="3b26f-118">Installare con gestione pacchetti</span><span class="sxs-lookup"><span data-stu-id="3b26f-118">Install with a package manager</span></span>

<span data-ttu-id="3b26f-119">È possibile installare il .NET Core SDK con molti dei gestori di pacchetti Linux comuni.</span><span class="sxs-lookup"><span data-stu-id="3b26f-119">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="3b26f-120">Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-manager-rhel7.md)).</span><span class="sxs-lookup"><span data-stu-id="3b26f-120">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="3b26f-121">Eseguire l'installazione con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b26f-121">Install with Visual Studio</span></span>

<span data-ttu-id="3b26f-122">Se si usa Visual Studio per sviluppare app .NET Core, nella tabella seguente viene descritta la versione minima richiesta di Visual Studio in base alla versione .NET Core SDK di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3b26f-122">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="3b26f-123">Versione .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="3b26f-123">.NET Core SDK version</span></span> | <span data-ttu-id="3b26f-124">Versione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b26f-124">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="3b26f-125">3.0</span><span class="sxs-lookup"><span data-stu-id="3b26f-125">3.0</span></span>                   | <span data-ttu-id="3b26f-126">Visual Studio 2019 versione 16,3 o successiva.</span><span class="sxs-lookup"><span data-stu-id="3b26f-126">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="3b26f-127">2.2</span><span class="sxs-lookup"><span data-stu-id="3b26f-127">2.2</span></span>                   | <span data-ttu-id="3b26f-128">Visual Studio 2017 versione 15,9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="3b26f-128">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="3b26f-129">2.1</span><span class="sxs-lookup"><span data-stu-id="3b26f-129">2.1</span></span>                   | <span data-ttu-id="3b26f-130">Visual Studio 2017 versione 15,7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="3b26f-130">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="3b26f-131">Se Visual Studio è già installato, è possibile controllare la versione con i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="3b26f-131">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="3b26f-132">Apri Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3b26f-132">Open Visual Studio.</span></span>
01. <span data-ttu-id="3b26f-133">Selezionare la **guida** > **informazioni su Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="3b26f-133">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="3b26f-134">Leggere il numero di versione dalla finestra **di dialogo informazioni su** .</span><span class="sxs-lookup"><span data-stu-id="3b26f-134">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="3b26f-135">Visual Studio è in grado di installare il .NET Core SDK e il runtime più recenti.</span><span class="sxs-lookup"><span data-stu-id="3b26f-135">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="3b26f-136">[Scaricare Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="3b26f-136">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="3b26f-137">Selezionare un carico di lavoro</span><span class="sxs-lookup"><span data-stu-id="3b26f-137">Select a workload</span></span>

<span data-ttu-id="3b26f-138">Quando si installa o si modifica Visual Studio, selezionare uno dei carichi di lavoro seguenti, a seconda del tipo di applicazione che si sta compilando:</span><span class="sxs-lookup"><span data-stu-id="3b26f-138">When installing or modifying Visual Studio, select one of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="3b26f-139">Il carico di lavoro **sviluppo multipiattaforma .NET Core** nella sezione **altri set di strumenti** .</span><span class="sxs-lookup"><span data-stu-id="3b26f-139">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="3b26f-140">Il carico di lavoro di **sviluppo ASP.NET e Web** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="3b26f-140">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="3b26f-141">Il carico di lavoro **sviluppo di Azure** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="3b26f-141">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="3b26f-142">Il carico di lavoro **sviluppo per desktop .NET** nella sezione **Desktop & per dispositivi mobili** .</span><span class="sxs-lookup"><span data-stu-id="3b26f-142">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="3b26f-143">[![Windows Visual Studio 2019 con carico di lavoro .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3b26f-143">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="3b26f-144">Installare con Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="3b26f-144">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="3b26f-145">Visual Studio per Mac installa l'.NET Core SDK quando si seleziona il carico di lavoro di **.NET Core** .</span><span class="sxs-lookup"><span data-stu-id="3b26f-145">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="3b26f-146">Per iniziare a usare lo sviluppo di .NET Core in macOS, vedere [installare Visual Studio 2019 per Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="3b26f-146">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

<span data-ttu-id="3b26f-147">[![macOS Visual Studio 2019 per Mac con funzionalità di carico di lavoro .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3b26f-147">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-from-visual-studio-code"></a><span data-ttu-id="3b26f-148">Installare da Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3b26f-148">Install from Visual Studio Code</span></span>

<span data-ttu-id="3b26f-149">Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop.</span><span class="sxs-lookup"><span data-stu-id="3b26f-149">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="3b26f-150">Visual Studio Code è disponibile per Windows, macOS e Linux.</span><span class="sxs-lookup"><span data-stu-id="3b26f-150">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="3b26f-151">Sebbene Visual Studio Code non sia dotato del supporto per .NET Core, l'aggiunta del supporto di .NET Core è semplice.</span><span class="sxs-lookup"><span data-stu-id="3b26f-151">While Visual Studio Code doesn't come with .NET Core support, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="3b26f-152">[Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="3b26f-152">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="3b26f-153">[Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span><span class="sxs-lookup"><span data-stu-id="3b26f-153">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>
01. <span data-ttu-id="3b26f-154">[Installare l' C# estensione dal Marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="3b26f-154">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="3b26f-155">Eseguire l'installazione con l'automazione di PowerShell</span><span class="sxs-lookup"><span data-stu-id="3b26f-155">Install with PowerShell automation</span></span>

<span data-ttu-id="3b26f-156">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="3b26f-156">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="3b26f-157">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-157">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="3b26f-158">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="3b26f-158">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="3b26f-159">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="3b26f-159">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="3b26f-160">Installare con l'automazione bash</span><span class="sxs-lookup"><span data-stu-id="3b26f-160">Install with bash automation</span></span>

<span data-ttu-id="3b26f-161">Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK.</span><span class="sxs-lookup"><span data-stu-id="3b26f-161">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="3b26f-162">È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-162">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="3b26f-163">Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 2,1.</span><span class="sxs-lookup"><span data-stu-id="3b26f-163">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="3b26f-164">Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.</span><span class="sxs-lookup"><span data-stu-id="3b26f-164">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="docker"></a><span data-ttu-id="3b26f-165">Docker</span><span class="sxs-lookup"><span data-stu-id="3b26f-165">Docker</span></span>

<span data-ttu-id="3b26f-166">I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="3b26f-166">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="3b26f-167">I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3b26f-167">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="3b26f-168">.NET Core può essere eseguito in un contenitore docker.</span><span class="sxs-lookup"><span data-stu-id="3b26f-168">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="3b26f-169">Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="3b26f-169">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="3b26f-170">Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="3b26f-170">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="3b26f-171">Microsoft fornisce immagini progettate per scenari specifici.</span><span class="sxs-lookup"><span data-stu-id="3b26f-171">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="3b26f-172">Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b26f-172">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="3b26f-173">Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-173">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b26f-174">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3b26f-174">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="3b26f-175">[Esercitazione: C# Hello World esercitazione](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-175">[Tutorial: C# Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="3b26f-176">[Esercitazione: Visual Basic Hello World esercitazione](../tutorials/vb-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-176">[Tutorial: Visual Basic Hello World tutorial](../tutorials/vb-with-visual-studio.md).</span></span>
- <span data-ttu-id="3b26f-177">[Esercitazione: creare una nuova app con Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span><span class="sxs-lookup"><span data-stu-id="3b26f-177">[Tutorial: Create a new app with Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span></span>
- <span data-ttu-id="3b26f-178">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-178">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="3b26f-179">[Esercitazione: Introduzione a MacOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-179">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="3b26f-180">[Esercitazione: creare una nuova app con Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span><span class="sxs-lookup"><span data-stu-id="3b26f-180">[Tutorial: Create a new app with Visual Studio Code](https://code.visualstudio.com/docs/languages/dotnet).</span></span>
- <span data-ttu-id="3b26f-181">[Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="3b26f-181">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
