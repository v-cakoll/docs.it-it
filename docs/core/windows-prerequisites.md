---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
author: JRAlexander
ms.author: johalex
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: fdbba188cf939ce3eb969a1f780e086fcf17da13
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="82ed9-103">Prerequisiti per .NET Core in Windows</span><span class="sxs-lookup"><span data-stu-id="82ed9-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="82ed9-104">Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="82ed9-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="82ed9-105">Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:</span><span class="sxs-lookup"><span data-stu-id="82ed9-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="82ed9-106">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="82ed9-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="82ed9-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="82ed9-107">Visual Studio 2017</span></span>](https://www.visualstudio.com/downloads/)
* [<span data-ttu-id="82ed9-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="82ed9-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="82ed9-109">Versioni di Windows supportate da .NET Core</span><span class="sxs-lookup"><span data-stu-id="82ed9-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="82ed9-110">.NET Core è supportato nelle versioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82ed9-110">.NET Core is supported on the following versions of :</span></span>

* <span data-ttu-id="82ed9-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="82ed9-111">Windows 7 SP1</span></span>
* <span data-ttu-id="82ed9-112">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="82ed9-112">Windows 8.1</span></span>
* <span data-ttu-id="82ed9-113">Windows 10, Aggiornamento dell'anniversario di Windows 10 (versione 1607) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="82ed9-113">Windows 10, Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="82ed9-114">Windows Server 2008 R2 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="82ed9-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="82ed9-115">Windows Server 2012 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="82ed9-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="82ed9-116">Windows Server 2012 R2 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="82ed9-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="82ed9-117">Windows Server 2016 (Full Server, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="82ed9-117">Windows Server 2016 (Full Server, Server Core, or Nano Server)</span></span>

<span data-ttu-id="82ed9-118">Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, vedere [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="82ed9-118">See [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems.</span></span>

<span data-ttu-id="82ed9-119">Per l'elenco completo dei sistemi operativi supportati .NET Core 1.x, vedere [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x - Versioni di sistemi operativi supportate).</span><span class="sxs-lookup"><span data-stu-id="82ed9-119">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="82ed9-120">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="82ed9-120">.NET Core dependencies</span></span>

<span data-ttu-id="82ed9-121">.NET Core 1.1 e versioni precedenti richiedono Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="82ed9-121">.NET Core 1.1 and earlier requires the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="82ed9-122">Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="82ed9-122">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="82ed9-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="82ed9-123">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

   * <span data-ttu-id="82ed9-124">Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="82ed9-124">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
   * <span data-ttu-id="82ed9-125">Distribuzione di un'applicazione .NET Core indipendente.</span><span class="sxs-lookup"><span data-stu-id="82ed9-125">Deploying a self-contained .NET Core application.</span></span>

> [!NOTE]
> <span data-ttu-id="82ed9-126"><em>Solo per i computer Windows 7 e Windows Server 2008:</em></span><span class="sxs-lookup"><span data-stu-id="82ed9-126"><em>For Windows 7 and Windows Server 2008 machines only:</em></span></span><br>
> <span data-ttu-id="82ed9-127">Verificare che l'installazione di Windows sia aggiornata e includa l'hotfix [KB2533623](https://support.microsoft.com/help/2533623) installato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="82ed9-127">Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="82ed9-128">Prerequisiti con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="82ed9-128">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="82ed9-129">È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="82ed9-129">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span>  <span data-ttu-id="82ed9-130">[Visual Studio 2017](#visual-studio-2017) fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="82ed9-130">[Visual Studio 2017](#visual-studio-2017) provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="82ed9-131">Nelle [note sulla versione ](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="82ed9-131">You can read more about the changes in Visual Studio 2017 in the [release notes](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span></span>
# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="82ed9-132">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="82ed9-132">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="82ed9-133">Per sviluppare app .NET Core 2.x in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="82ed9-133">To develop .NET Core 2.x apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="82ed9-134">[Scaricare e installare Visual Studio 2017 versione 15.3.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="82ed9-134">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="82ed9-135">![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-3-workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="82ed9-135">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs-15-3-workloads.jpg)</span></span>

<span data-ttu-id="82ed9-136">Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio 2017 usa .NET Core 1.x per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="82ed9-136">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="82ed9-137">Installare .NET Core 2.x SDK per ottenere il supporto di .NET Core 2.x in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="82ed9-137">Install the .NET Core 2.x SDK to get .NET Core 2.x support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="82ed9-138">Installare [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="82ed9-138">Install the [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).</span></span>
 3. <span data-ttu-id="82ed9-139">Ridestinare i progetti .NET Core 1.x esistenti o nuovi a .NET Core 2.x usando le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82ed9-139">Retarget existing or new .NET Core 1.x projects to .NET Core 2.x using the following instructions:</span></span>
    * <span data-ttu-id="82ed9-140">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="82ed9-140">On the **Project** menu, Choose **Properties**.</span></span> 
    * <span data-ttu-id="82ed9-141">Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="82ed9-141">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="82ed9-143">Dopo l'installazione di .NET Core 2.x SDK, Visual Studio 2017 usa .NET Core SDK 2.x per impostazione predefinita e supporta le seguenti azioni:</span><span class="sxs-lookup"><span data-stu-id="82ed9-143">Once the .NET Core 2.x SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.x by default, and supports the following actions:</span></span>

  * <span data-ttu-id="82ed9-144">Aprire, compilare ed eseguire progetti .NET Core 1.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="82ed9-144">Open, build, and run existing .NET Core 1.x projects.</span></span>
  * <span data-ttu-id="82ed9-145">Ridestinare i progetti .NET Core 1.x a .NET Core 2.x, compilare ed eseguire i progetti.</span><span class="sxs-lookup"><span data-stu-id="82ed9-145">Retarget .NET Core 1.x projects to .NET Core 2.x, build, and run.</span></span>
  * <span data-ttu-id="82ed9-146">Creare nuovi progetti .NET Core 2.x.</span><span class="sxs-lookup"><span data-stu-id="82ed9-146">Create new .NET Core 2.x projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="82ed9-147">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="82ed9-147">.NET Core 1.x</span></span>](#tab/netcore1x)
<span data-ttu-id="82ed9-148">Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017 RTM (versione 15.0.26228.4) o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="82ed9-148">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017 RTM (version 15.0.26228.4) or higher](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="82ed9-149">![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="82ed9-149">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs_workloads.jpg)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="82ed9-150">È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="82ed9-150">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="82ed9-151">Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.</span><span class="sxs-lookup"><span data-stu-id="82ed9-151">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="82ed9-152">I progetti sono basati sul file project.json che è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="82ed9-152">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="82ed9-153">Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).</span><span class="sxs-lookup"><span data-stu-id="82ed9-153">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

>[!TIP]
  > <span data-ttu-id="82ed9-154">Per verificare la versione di Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="82ed9-154">To verify your Visual Studio 2017 version:</span></span>
>
     > * <span data-ttu-id="82ed9-155">Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="82ed9-155">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
     > * <span data-ttu-id="82ed9-156">Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="82ed9-156">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>     * <span data-ttu-id="82ed9-157">Per le app .NET Core 2.x, Visual Studio 2017 versione 15.3 (26730.01) o successiva.</span><span class="sxs-lookup"><span data-stu-id="82ed9-157">For .NET Core 2.x apps, Visual Studio 2017 version 15.3 (26730.01) or higher.</span></span>
>     * <span data-ttu-id="82ed9-158">Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 (26228.04) o successiva.</span><span class="sxs-lookup"><span data-stu-id="82ed9-158">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 (26228.04) or higher.</span></span>
