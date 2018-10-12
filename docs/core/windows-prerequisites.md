---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: 63c0de2b413f38458dba89506f4070760b3f53f8
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45747468"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="823c4-103">Prerequisiti per .NET Core in Windows</span><span class="sxs-lookup"><span data-stu-id="823c4-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="823c4-104">Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="823c4-104">This article shows the dependencies needed to develop .NET Core applications on Windows.</span></span> <span data-ttu-id="823c4-105">Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:</span><span class="sxs-lookup"><span data-stu-id="823c4-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="823c4-106">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="823c4-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="823c4-107">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="823c4-107">Visual Studio 2017</span></span>](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [<span data-ttu-id="823c4-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="823c4-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a><span data-ttu-id="823c4-109">Versioni di Windows supportate da .NET Core</span><span class="sxs-lookup"><span data-stu-id="823c4-109">.NET Core supported Windows versions</span></span>

<span data-ttu-id="823c4-110">.NET Core è supportato nelle versioni seguenti di:</span><span class="sxs-lookup"><span data-stu-id="823c4-110">.NET Core is supported on the following versions of:</span></span>

* <span data-ttu-id="823c4-111">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="823c4-111">Windows 7 SP1</span></span>
* <span data-ttu-id="823c4-112">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="823c4-112">Windows 8.1</span></span>
* <span data-ttu-id="823c4-113">Aggiornamento dell'anniversario di Windows 10 (versione 1607) o versioni successive</span><span class="sxs-lookup"><span data-stu-id="823c4-113">Windows 10 Anniversary Update (version 1607) or later versions</span></span>
* <span data-ttu-id="823c4-114">Windows Server 2008 R2 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="823c4-114">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="823c4-115">Windows Server 2012 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="823c4-115">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="823c4-116">Windows Server 2012 R2 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="823c4-116">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="823c4-117">Windows Server 2016 o versioni successive (Full Server, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="823c4-117">Windows Server 2016 or later versions (Full Server, Server Core, or Nano Server)</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="823c4-118">Sistemi operativi supportati da .NET Core</span><span class="sxs-lookup"><span data-stu-id="823c4-118">.NET Core supported operating systems</span></span>

<span data-ttu-id="823c4-119">Gli articoli seguenti contengono un elenco completo dei sistemi operativi supportati da .NET Core per ogni versione:</span><span class="sxs-lookup"><span data-stu-id="823c4-119">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="823c4-120">.NET Core 2.1: versioni dei sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="823c4-120">.NET Core 2.1 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="823c4-121">.NET Core 2.0: versioni dei sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="823c4-121">.NET Core 2.0 - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [<span data-ttu-id="823c4-122">.NET Core 1.x: versioni dei sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="823c4-122">.NET Core 1.x - Supported OS Versions</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a><span data-ttu-id="823c4-123">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="823c4-123">.NET Core dependencies</span></span>

<span data-ttu-id="823c4-124">.NET Core 1.1 e versioni precedenti richiedono Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="823c4-124">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="823c4-125">Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="823c4-125">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="823c4-126">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="823c4-126">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="823c4-127">Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="823c4-127">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="823c4-128">Distribuzione di un'applicazione .NET Core indipendente.</span><span class="sxs-lookup"><span data-stu-id="823c4-128">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="823c4-129">Compilazione del prodotto dall'origine.</span><span class="sxs-lookup"><span data-stu-id="823c4-129">Building the product from source.</span></span>
* <span data-ttu-id="823c4-130">Installazione di .NET Core tramite un file *ZIP*.</span><span class="sxs-lookup"><span data-stu-id="823c4-130">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="823c4-131">Sono inclusi i server di compilazione/di integrazione continua/di distribuzione continua.</span><span class="sxs-lookup"><span data-stu-id="823c4-131">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="823c4-132">**Per Windows 8.1 e versioni precedenti, o Windows Server 2012 R2 e versioni precedenti:**</span><span class="sxs-lookup"><span data-stu-id="823c4-132">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="823c4-133">Verificare che l'installazione di Windows sia aggiornata e includa l'aggiornamento [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), che può essere installato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="823c4-133">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="823c4-134">Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="823c4-134">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="823c4-135">**Per Windows 7 o Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="823c4-135">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="823c4-136">Oltre all'aggiornamento KB2999226, verificare che sia installato anche l'aggiornamento [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="823c4-136">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="823c4-137">Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="823c4-137">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="823c4-138">Prerequisiti con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="823c4-138">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="823c4-139">È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="823c4-139">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="823c4-140">Visual Studio 2017 fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="823c4-140">Visual Studio 2017 provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="823c4-141">Nelle [note sulla versione ](/visualstudio/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="823c4-141">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="823c4-142">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="823c4-142">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="823c4-143">Per sviluppare app .NET Core 2.1 in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="823c4-143">To develop .NET Core 2.1 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="823c4-144">[Scaricare e installare Visual Studio 2017 versione 15.7.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="823c4-144">[Download and install Visual Studio 2017 version 15.7.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-8-workloads.jpg)

<span data-ttu-id="823c4-146">Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, per impostazione predefinita Visual Studio 2017 15.7 usa .NET Core 2.0 SDK e Visual Studio 2017 15.8 usa 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="823c4-146">After the **.NET Core cross-platform development** toolset is installed, by default, Visual Studio 2017 15.7 uses .NET Core 2.0 SDK and Visual Studio 2017 15.8 uses 2.1 SDK.</span></span>

 2. <span data-ttu-id="823c4-147">Se si usa Visual Studio 2017 15.7, installare [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) o eseguire l'aggiornamento a Visual Studio 2017 15.8.</span><span class="sxs-lookup"><span data-stu-id="823c4-147">If you're using Visual Studio 2017 15.7, install the [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) or upgrade to Visual Studio 2017 15.8.</span></span>

 3. <span data-ttu-id="823c4-148">Ridestinare i progetti .NET Core esistenti o nuovi a .NET Core 2.1 usando le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="823c4-148">Retarget existing or new .NET Core projects to .NET Core 2.1 using the following instructions:</span></span>
    * <span data-ttu-id="823c4-149">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="823c4-149">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="823c4-150">Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.1**.</span><span class="sxs-lookup"><span data-stu-id="823c4-150">In the **Target framework** selection menu, set the value to **.NET Core 2.1**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="823c4-152">Dopo aver configurato Visual Studio con .NET Core 2.1 SDK, è possibile eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="823c4-152">Once you have Visual Studio configured with .NET Core 2.1 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="823c4-153">Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="823c4-153">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="823c4-154">Ridestinare i progetti .NET Core 1.x e 2.0 a .NET Core 2.1, compilare ed eseguire i progetti.</span><span class="sxs-lookup"><span data-stu-id="823c4-154">Retarget .NET Core 1.x and 2.0 projects to .NET Core 2.1, build, and run.</span></span>
* <span data-ttu-id="823c4-155">Creare nuovi progetti .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="823c4-155">Create new .NET Core 2.1 projects.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="823c4-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="823c4-156">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="823c4-157">Per sviluppare app .NET Core 2.0 in Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="823c4-157">To develop .NET Core 2.0 apps in Visual Studio 2017:</span></span>

 1. <span data-ttu-id="823c4-158">[Scaricare e installare Visual Studio 2017 versione 15.3.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="823c4-158">[Download and install Visual Studio 2017 version 15.3.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-3-workloads.jpg)

<span data-ttu-id="823c4-160">Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio 2017 usa .NET Core 1.x per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="823c4-160">After the **.NET Core cross-platform development** toolset is installed, Visual Studio 2017 uses .NET Core 1.x by default.</span></span> <span data-ttu-id="823c4-161">Installare .NET Core 2.0 SDK per ottenere il supporto di .NET Core 2.0 in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="823c4-161">Install the .NET Core 2.0 SDK to get .NET Core 2.0 support in Visual Studio 2017.</span></span>

 2. <span data-ttu-id="823c4-162">Installare [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).</span><span class="sxs-lookup"><span data-stu-id="823c4-162">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).</span></span>
 3. <span data-ttu-id="823c4-163">Ridestinare i progetti .NET Core 1.x esistenti o nuovi a .NET Core 2.0 usando le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="823c4-163">Retarget existing or new .NET Core 1.x projects to .NET Core 2.0 using the following instructions:</span></span>
    * <span data-ttu-id="823c4-164">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="823c4-164">On the **Project** menu, Choose **Properties**.</span></span>
    * <span data-ttu-id="823c4-165">Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.0**.</span><span class="sxs-lookup"><span data-stu-id="823c4-165">In the **Target framework** selection menu, set the value to **.NET Core 2.0**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

<span data-ttu-id="823c4-167">Dopo l'installazione di .NET Core 2.0 SDK, Visual Studio 2017 usa .NET Core SDK 2.0 per impostazione predefinita e supporta le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="823c4-167">Once the .NET Core 2.0 SDK is installed, Visual Studio 2017 uses the .NET Core SDK 2.0 by default, and supports the following actions:</span></span>

* <span data-ttu-id="823c4-168">Aprire, compilare ed eseguire progetti .NET Core 1.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="823c4-168">Open, build, and run existing .NET Core 1.x projects.</span></span>
* <span data-ttu-id="823c4-169">Ridestinare i progetti .NET Core 1.x a .NET Core 2.0, compilare ed eseguire i progetti.</span><span class="sxs-lookup"><span data-stu-id="823c4-169">Retarget .NET Core 1.x projects to .NET Core 2.0, build, and run.</span></span>
* <span data-ttu-id="823c4-170">Creare nuovi progetti .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="823c4-170">Create new .NET Core 2.0 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="823c4-171">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="823c4-171">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="823c4-172">Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="823c4-172">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="823c4-174">È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="823c4-174">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="823c4-175">Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.</span><span class="sxs-lookup"><span data-stu-id="823c4-175">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="823c4-176">I progetti sono basati sul file project.json che è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="823c4-176">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="823c4-177">Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).</span><span class="sxs-lookup"><span data-stu-id="823c4-177">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>
---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="823c4-178">Per verificare la versione di Visual Studio 2017:</span><span class="sxs-lookup"><span data-stu-id="823c4-178">To verify your Visual Studio 2017 version:</span></span>
>
> * <span data-ttu-id="823c4-179">Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="823c4-179">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="823c4-180">Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="823c4-180">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="823c4-181">Per le app .NET Core 2.2 anteprima 1, Visual Studio 2017 versione 15.9 (attualmente in anteprima) o successiva.</span><span class="sxs-lookup"><span data-stu-id="823c4-181">For .NET Core 2.2 Preview 1 apps, Visual Studio 2017 version 15.9 (currently in Preview) or higher.</span></span>
>   * <span data-ttu-id="823c4-182">Per le app .NET Core 2.1, Visual Studio 2017 versione 15.7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="823c4-182">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="823c4-183">Per le app .NET Core 2.0, Visual Studio 2017 versione 15.3 o successiva.</span><span class="sxs-lookup"><span data-stu-id="823c4-183">For .NET Core 2.0 apps, Visual Studio 2017 version 15.3 or higher.</span></span>
>   * <span data-ttu-id="823c4-184">Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="823c4-184">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
