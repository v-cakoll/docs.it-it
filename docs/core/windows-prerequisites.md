---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
author: JRAlexander
ms.author: johalex
ms.date: 04/24/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 6f2ba8540a38f8e30d3d968f5e2c891c850053aa
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="61f33-103">Prerequisiti per .NET Core in Windows</span><span class="sxs-lookup"><span data-stu-id="61f33-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="61f33-104">Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="61f33-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="61f33-105">Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:</span><span class="sxs-lookup"><span data-stu-id="61f33-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="61f33-106">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="61f33-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="61f33-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="61f33-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="61f33-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="61f33-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="61f33-109">Versioni di Windows supportate da .NET Core</span><span class="sxs-lookup"><span data-stu-id="61f33-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="61f33-110">.NET Core è supportato nelle versioni seguenti di:</span><span class="sxs-lookup"><span data-stu-id="61f33-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="61f33-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="61f33-111">Windows 7 SP1</span></span>
* <span data-ttu-id="61f33-112">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="61f33-112">Windows 8.1</span></span>
* <span data-ttu-id="61f33-113">Aggiornamento dell'anniversario di Windows 10 (versione 1607) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="61f33-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="61f33-114">Windows Server 2008 R2 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="61f33-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="61f33-115">Windows Server 2012 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="61f33-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="61f33-116">Windows Server 2012 R2 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="61f33-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="61f33-117">Windows Server 2016 (Full Server, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="61f33-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="61f33-118">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, vedere [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="61f33-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="61f33-119">Per l'elenco completo dei sistemi operativi supportati .NET Core 1.x, vedere [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="61f33-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="61f33-120">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="61f33-120">.NET Core dependencies</span></span>

<span data-ttu-id="61f33-121">.NET Core 1.1 e versioni precedenti richiedono Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="61f33-121">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="61f33-122">Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="61f33-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="61f33-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="61f33-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="61f33-124">Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="61f33-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="61f33-125">Distribuzione di un'applicazione .NET Core indipendente.</span><span class="sxs-lookup"><span data-stu-id="61f33-125">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="61f33-126">Compilazione del prodotto dall'origine.</span><span class="sxs-lookup"><span data-stu-id="61f33-126">Building the product from source.</span></span>
* <span data-ttu-id="61f33-127">Installazione di .NET Core tramite un file *ZIP*.</span><span class="sxs-lookup"><span data-stu-id="61f33-127">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="61f33-128">Sono inclusi i server di compilazione/di integrazione continua/di distribuzione continua.</span><span class="sxs-lookup"><span data-stu-id="61f33-128">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="61f33-129">*Per Windows 8.1 e versioni precedenti o Windows Server 2012 R2 e versioni precedenti:* assicurarsi che l'installazione di Windows sia aggiornata e includa [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), che può essere installato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="61f33-129">*For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:* Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows) which can be installed through Windows Update.</span></span> <span data-ttu-id="61f33-130">Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core viene visualizzato un errore simile al seguente: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span><span class="sxs-lookup"><span data-stu-id="61f33-130">If you don't have this update installed, you'll see an error when you launch a .NET Core application like the following: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="61f33-131">Prerequisiti con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="61f33-131">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="61f33-132">È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="61f33-132">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="61f33-133">[Visual Studio 2017](#visual-studio-2017) fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="61f33-133">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="61f33-134">Nelle [note sulla versione ](/visualstudio/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="61f33-134">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="61f33-135">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="61f33-135">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="61f33-136">Per sviluppare app .NET Core 2.x in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="61f33-136">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="61f33-137">[Scaricare e installare Visual Studio 2017 versione 15.3.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="61f33-137">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="61f33-139">Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio 2017 usa .NET Core 1.x per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="61f33-139">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="61f33-140">Installare .NET Core 2.x SDK per ottenere il supporto di .NET Core 2.x in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="61f33-140">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="61f33-141">Installare [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="61f33-141">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="61f33-142">Ridestinare i progetti .NET Core 1.x esistenti o nuovi a .NET Core 2.x usando le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="61f33-142">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="61f33-143">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="61f33-143">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="61f33-144">Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="61f33-144">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="61f33-146">Dopo l'installazione di .NET Core 2.x SDK, Visual Studio 2017 usa .NET Core SDK 2.x per impostazione predefinita e supporta le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="61f33-146">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

* <span data-ttu-id="61f33-147">Aprire, compilare ed eseguire progetti .NET Core 1.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="61f33-147">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="61f33-148">Ridestinare i progetti .NET Core 1.x a .NET Core 2.x, compilare ed eseguire i progetti.</span><span class="sxs-lookup"><span data-stu-id="61f33-148">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
* <span data-ttu-id="61f33-149">Creare nuovi progetti .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="61f33-149">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="61f33-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="61f33-150">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="61f33-151">Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017 RTM (versione 15.0.26228.4) o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="61f33-151">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="61f33-153">È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="61f33-153">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="61f33-154">Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.</span><span class="sxs-lookup"><span data-stu-id="61f33-154">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="61f33-155">I progetti sono basati sul file project.json che è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="61f33-155">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="61f33-156">Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).</span><span class="sxs-lookup"><span data-stu-id="61f33-156">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

> [!TIP]
> <span data-ttu-id="61f33-157">Per verificare la versione di Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="61f33-157">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="61f33-158">Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="61f33-158">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="61f33-159">Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="61f33-159">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="61f33-160">Per le app .NET Core 2.1 anteprima 1, Visual Studio 2017 versione 15.6 anteprima 6 o successiva.</span><span class="sxs-lookup"><span data-stu-id="61f33-160">For .NET Core 2.1 Preview 1 apps, Visual Studio 2017 version 15.6 Preview 6 or higher.</span></span>
>   * <span data-ttu-id="61f33-161">Per le app .NET Core 2.0, Visual Studio 2017 versione 15.3 o successiva.</span><span class="sxs-lookup"><span data-stu-id="61f33-161">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="61f33-162">Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="61f33-162">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
