---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
author: JRAlexander
ms.author: johalex
ms.date: 02/28/2018
ms.topic: article
ms.prod: .net-core
ms.workload:
- dotnetcore
ms.openlocfilehash: e64ecb807fd377458a9998ebbdfe2f6f15b115bb
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="0e9a8-103">Prerequisiti per .NET Core in Windows</span><span class="sxs-lookup"><span data-stu-id="0e9a8-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="0e9a8-104">Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="0e9a8-105">Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="0e9a8-106">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="0e9a8-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="0e9a8-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0e9a8-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="0e9a8-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="0e9a8-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="0e9a8-109">Versioni di Windows supportate da .NET Core</span><span class="sxs-lookup"><span data-stu-id="0e9a8-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="0e9a8-110">.NET Core è supportato nelle versioni seguenti di:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="0e9a8-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="0e9a8-111">Windows 7 SP1</span></span>
* <span data-ttu-id="0e9a8-112">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="0e9a8-112">Windows 8.1</span></span>
* <span data-ttu-id="0e9a8-113">Aggiornamento dell'anniversario di Windows 10 (versione 1607) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="0e9a8-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="0e9a8-114">Windows Server 2008 R2 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="0e9a8-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="0e9a8-115">Windows Server 2012 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="0e9a8-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="0e9a8-116">Windows Server 2012 R2 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="0e9a8-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="0e9a8-117">Windows Server 2016 (Full Server, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="0e9a8-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="0e9a8-118">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, vedere [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="0e9a8-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="0e9a8-119">Per l'elenco completo dei sistemi operativi supportati .NET Core 1.x, vedere [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="0e9a8-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="0e9a8-120">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="0e9a8-120">.NET Core dependencies</span></span>

<span data-ttu-id="0e9a8-121">.NET Core 1.1 e versioni precedenti richiedono Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-121">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="0e9a8-122">Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="0e9a8-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="0e9a8-124">Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="0e9a8-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="0e9a8-125">Distribuzione di un'applicazione .NET Core indipendente.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-125">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="0e9a8-126">Compilazione del prodotto dall'origine.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-126">Building the product from source.</span></span>
* <span data-ttu-id="0e9a8-127">Installazione di .NET Core tramite un file *ZIP*.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-127">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="0e9a8-128">Sono inclusi i server di compilazione/di integrazione continua/di distribuzione continua.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-128">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="0e9a8-129">*Solo per computer Windows 7 e Windows Server 2008:* verificare che l'installazione di Windows sia aggiornata e includa l'hotfix [KB2533623](https://support.microsoft.com/help/2533623) installato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-129">*For Windows 7 and Windows Server 2008 machines only:* Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="0e9a8-130">Prerequisiti con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0e9a8-130">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="0e9a8-131">È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-131">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="0e9a8-132">[Visual Studio 2017](#visual-studio-2017) fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-132">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="0e9a8-133">Nelle [note sulla versione ](/visualstudio/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-133">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="0e9a8-134">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="0e9a8-134">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="0e9a8-135">Per sviluppare app .NET Core 2.x in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-135">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="0e9a8-136">[Scaricare e installare Visual Studio 2017 versione 15.3.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-136">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="0e9a8-138">Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio 2017 usa .NET Core 1.x per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-138">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="0e9a8-139">Installare .NET Core 2.x SDK per ottenere il supporto di .NET Core 2.x in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-139">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="0e9a8-140">Installare [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="0e9a8-140">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="0e9a8-141">Ridestinare i progetti .NET Core 1.x esistenti o nuovi a .NET Core 2.x usando le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-141">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="0e9a8-142">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-142">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="0e9a8-143">Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-143">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="0e9a8-145">Dopo l'installazione di .NET Core 2.x SDK, Visual Studio 2017 usa .NET Core SDK 2.x per impostazione predefinita e supporta le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-145">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

* <span data-ttu-id="0e9a8-146">Aprire, compilare ed eseguire progetti .NET Core 1.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-146">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="0e9a8-147">Ridestinare i progetti .NET Core 1.x a .NET Core 2.x, compilare ed eseguire i progetti.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-147">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
* <span data-ttu-id="0e9a8-148">Creare nuovi progetti .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-148">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0e9a8-149">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0e9a8-149">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0e9a8-150">Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017 RTM (versione 15.0.26228.4) o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-150">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="0e9a8-152">È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-152">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="0e9a8-153">Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-153">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="0e9a8-154">I progetti sono basati sul file project.json che è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-154">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="0e9a8-155">Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).</span><span class="sxs-lookup"><span data-stu-id="0e9a8-155">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

> [!TIP]
> <span data-ttu-id="0e9a8-156">Per verificare la versione di Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="0e9a8-156">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="0e9a8-157">Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="0e9a8-157">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="0e9a8-158">Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-158">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="0e9a8-159">Per le app .NET Core 2.x, Visual Studio 2017 versione 15.3 (26730.01) o successiva.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-159">For .NET Core 2.x apps, Visual Studio 2017 version 15.3 (26730.01) or higher.</span></span>
>   * <span data-ttu-id="0e9a8-160">Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 (26228.04) o successiva.</span><span class="sxs-lookup"><span data-stu-id="0e9a8-160">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 (26228.04) or higher.</span></span>
