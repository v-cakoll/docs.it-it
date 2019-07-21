---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 1921ef565c2d04624009f7684e439ddba1cdf57e
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331069"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="07073-103">Prerequisiti per .NET Core in Windows</span><span class="sxs-lookup"><span data-stu-id="07073-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="07073-104">Questo articolo illustra le versioni supportate del sistema operativo per eseguire le applicazioni .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="07073-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="07073-105">Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:</span><span class="sxs-lookup"><span data-stu-id="07073-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="07073-106">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="07073-106">Command line</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="07073-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="07073-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [<span data-ttu-id="07073-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="07073-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="07073-109">Se si sviluppa in Windows con Visual Studio 2017, la sezione [Prerequisiti con Visual Studio 2017](#prerequisites-with-visual-studio-2017) illustra in modo più dettagliato le versioni minime supportate per lo sviluppo .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07073-109">Also, if you're developing on Windows using Visual Studio 2017, the [Prerequisites with Visual Studio 2017](#prerequisites-with-visual-studio-2017) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="07073-110">Sistemi operativi supportati da .NET Core</span><span class="sxs-lookup"><span data-stu-id="07073-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="07073-111">Gli articoli seguenti contengono un elenco completo dei sistemi operativi supportati da .NET Core per ogni versione:</span><span class="sxs-lookup"><span data-stu-id="07073-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="07073-112">.NET Core 3.0 (Preview)</span><span class="sxs-lookup"><span data-stu-id="07073-112">.NET Core 3.0 (Preview)</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="07073-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="07073-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="07073-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="07073-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="07073-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="07073-115">.NET Core 1.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

<span data-ttu-id="07073-116">Per i collegamenti per il download e altre informazioni, vedere [.NET downloads](https://dotnet.microsoft.com/download) (Download .NET) per scaricare la versione più recente o [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) (Archivio di download .NET) per le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="07073-116">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="07073-117">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="07073-117">.NET Core dependencies</span></span>

<span data-ttu-id="07073-118">.NET Core 1.1 e versioni precedenti richiedono Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="07073-118">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="07073-119">Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07073-119">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="07073-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="07073-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="07073-121">Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="07073-121">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="07073-122">Distribuzione di un'applicazione .NET Core indipendente.</span><span class="sxs-lookup"><span data-stu-id="07073-122">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="07073-123">Compilazione del prodotto dall'origine.</span><span class="sxs-lookup"><span data-stu-id="07073-123">Building the product from source.</span></span>
* <span data-ttu-id="07073-124">Installazione di .NET Core tramite un file *ZIP*.</span><span class="sxs-lookup"><span data-stu-id="07073-124">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="07073-125">Sono inclusi i server di compilazione/di integrazione continua/di distribuzione continua.</span><span class="sxs-lookup"><span data-stu-id="07073-125">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="07073-126">**Per Windows 8.1 e versioni precedenti, o Windows Server 2012 R2 e versioni precedenti:**</span><span class="sxs-lookup"><span data-stu-id="07073-126">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="07073-127">Verificare che l'installazione di Windows sia aggiornata e includa l'aggiornamento [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), che può essere installato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="07073-127">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="07073-128">Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="07073-128">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="07073-129">**Per Windows 7 o Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="07073-129">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="07073-130">Oltre all'aggiornamento KB2999226, verificare che sia installato anche l'aggiornamento [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="07073-130">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="07073-131">Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="07073-131">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-for-net-core-30-preview-3"></a><span data-ttu-id="07073-132">Prerequisiti per .NET Core 3.0 Preview 3</span><span class="sxs-lookup"><span data-stu-id="07073-132">Prerequisites for .NET Core 3.0 Preview 3</span></span>

<span data-ttu-id="07073-133">.NET core 3.0 Preview 3 ha gli stessi prerequisiti delle altre versioni di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="07073-133">.NET Core 3.0 Preview 3 has the same prerequisites as other versions of .NET Core.</span></span> <span data-ttu-id="07073-134">Se tuttavia si vuole usare Visual Studio per creare progetti .NET Core 3.0, è necessario usare [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="07073-134">However, if you want to use Visual Studio to create .NET Core 3.0 projects, you must use the [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="07073-135">È possibile installare Visual Studio 2019 side-by-side con altre versioni di Visual Studio, senza alcun conflitto.</span><span class="sxs-lookup"><span data-stu-id="07073-135">Visual Studio 2019 can be installed side-by-side with other versions of Visual Studio without conflict.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="07073-136">Prerequisiti con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="07073-136">Prerequisites with Visual Studio 2017</span></span>
    
<span data-ttu-id="07073-137">È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="07073-137">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="07073-138">Visual Studio 2017 fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="07073-138">Visual Studio 2017 provides an integrated development environment for .NET Core apps on Windows.</span></span>

<span data-ttu-id="07073-139">Nelle [note sulla versione ](/visualstudio/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="07073-139">You can read more about the changes in Visual Studio 2017 in the [release notes](/visualstudio/releasenotes/vs2017-relnotes).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="07073-140">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="07073-140">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="07073-141">Per sviluppare app .NET Core in Visual Studio 2017 con .NET Core 2.2 SDK:</span><span class="sxs-lookup"><span data-stu-id="07073-141">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="07073-142">[Scaricare e installare Visual Studio 2017 versione 15.9.0 o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="07073-142">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="07073-144">Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio installa in genere una versione precedente di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="07073-144">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="07073-145">Visual Studio 2017 15.9, ad esempio, usa .NET Core 2.1 SDK per impostazione predefinita dopo l'installazione del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="07073-145">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="07073-146">Per aggiornare Visual Studio per usare .NET Core 2.2 SDK:</span><span class="sxs-lookup"><span data-stu-id="07073-146">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="07073-147">Installare [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="07073-147">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="07073-148">Se si vuole che il progetto usi il runtime di .NET Core più recente, ridestinare i progetti .NET Core nuovi o esistenti a .NET Core 2.2 seguendo queste istruzioni:</span><span class="sxs-lookup"><span data-stu-id="07073-148">If you want your project to use the latest .NET Core runtime, retarget existing or new .NET Core projects to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="07073-149">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="07073-149">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="07073-150">Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.2**.</span><span class="sxs-lookup"><span data-stu-id="07073-150">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione ".NET Core 2.2" selezionata](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="07073-152">Dopo aver configurato Visual Studio con .NET Core 2.2 SDK, è possibile eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="07073-152">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="07073-153">Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="07073-153">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="07073-154">Ridestinare i progetti .NET Core 1.x e 2.x a .NET Core 2.2, compilarli ed eseguirli.</span><span class="sxs-lookup"><span data-stu-id="07073-154">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="07073-155">Creare nuovi progetti .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="07073-155">Create new .NET Core 2.2 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07073-156">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07073-156">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="07073-157">Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="07073-157">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="07073-159">È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="07073-159">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
  > * <span data-ttu-id="07073-160">Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.</span><span class="sxs-lookup"><span data-stu-id="07073-160">The .NET Core tooling is a preview version, which is not supported.</span></span>
  > * <span data-ttu-id="07073-161">I progetti sono basati sul file project.json che è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="07073-161">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="07073-162">Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).</span><span class="sxs-lookup"><span data-stu-id="07073-162">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

---

<a name="vs-mapping"></a>

> [!TIP]
> <span data-ttu-id="07073-163">Per verificare la versione di Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="07073-163">To verify your Visual Studio version:</span></span>
>
> * <span data-ttu-id="07073-164">Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="07073-164">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
> * <span data-ttu-id="07073-165">Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="07073-165">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>
>   * <span data-ttu-id="07073-166">Per le app .NET Core 3.0 Preview 3, Visual Studio 2019 versione 16.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="07073-166">For .NET Core 3.0 Preview 3 apps, Visual Studio 2019 version 16.0 or higher.</span></span>
>   * <span data-ttu-id="07073-167">Per le app .NET Core 2.2, Visual Studio 2017 versione 15.9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="07073-167">For .NET Core 2.2 apps, Visual Studio 2017 version 15.9 or higher.</span></span>
>   * <span data-ttu-id="07073-168">Per le app .NET Core 2.1, Visual Studio 2017 versione 15.7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="07073-168">For .NET Core 2.1 apps, Visual Studio 2017 version 15.7 or higher.</span></span>
>   * <span data-ttu-id="07073-169">Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="07073-169">For .NET Core 1.x apps, Visual Studio 2017 version 15.0 or higher.</span></span>
