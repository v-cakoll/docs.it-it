---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: c46a1f12ca20c0e21ee205e409a2a5a89e3389b3
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214559"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="a636f-103">Prerequisiti per .NET Core in Windows</span><span class="sxs-lookup"><span data-stu-id="a636f-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="a636f-104">Questo articolo illustra le versioni supportate del sistema operativo per eseguire le applicazioni .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="a636f-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="a636f-105">Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:</span><span class="sxs-lookup"><span data-stu-id="a636f-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="a636f-106">Riga di comando</span><span class="sxs-lookup"><span data-stu-id="a636f-106">Command line</span></span>](./tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="a636f-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a636f-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [<span data-ttu-id="a636f-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a636f-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="a636f-109">Inoltre, se si sta sviluppando in Windows con Visual Studio, i [prerequisiti per lo sviluppo di app .NET Core con Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) illustrano in modo più dettagliato le versioni minime supportate per lo sviluppo di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a636f-109">Also, if you're developing on Windows using Visual Studio, the [Prerequisites to develop .NET Core apps with Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="a636f-110">Sistemi operativi supportati da .NET Core</span><span class="sxs-lookup"><span data-stu-id="a636f-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="a636f-111">Gli articoli seguenti contengono un elenco completo dei sistemi operativi supportati da .NET Core per ogni versione:</span><span class="sxs-lookup"><span data-stu-id="a636f-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="a636f-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a636f-112">.NET Core 3.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="a636f-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a636f-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="a636f-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a636f-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [<span data-ttu-id="a636f-115">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="a636f-115">.NET Core 1.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

<span data-ttu-id="a636f-116">Per i collegamenti per il download e altre informazioni, vedere [.NET downloads](https://dotnet.microsoft.com/download) (Download .NET) per scaricare la versione più recente o [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) (Archivio di download .NET) per le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="a636f-116">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="a636f-117">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="a636f-117">.NET Core dependencies</span></span>

<span data-ttu-id="a636f-118">.NET Core 1.1 e versioni precedenti richiedono Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="a636f-118">.NET Core 1.1 and earlier versions require the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="a636f-119">Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a636f-119">This dependency is automatically installed by the .NET Core installer.</span></span>

<span data-ttu-id="a636f-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:</span><span class="sxs-lookup"><span data-stu-id="a636f-120">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="a636f-121">Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="a636f-121">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="a636f-122">Distribuzione di un'applicazione .NET Core indipendente.</span><span class="sxs-lookup"><span data-stu-id="a636f-122">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="a636f-123">Compilazione del prodotto dall'origine.</span><span class="sxs-lookup"><span data-stu-id="a636f-123">Building the product from source.</span></span>
* <span data-ttu-id="a636f-124">Installazione di .NET Core tramite un file *ZIP*.</span><span class="sxs-lookup"><span data-stu-id="a636f-124">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="a636f-125">Sono inclusi i server di compilazione/di integrazione continua/di distribuzione continua.</span><span class="sxs-lookup"><span data-stu-id="a636f-125">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="a636f-126">**Per Windows 8.1 e versioni precedenti, o Windows Server 2012 R2 e versioni precedenti:**</span><span class="sxs-lookup"><span data-stu-id="a636f-126">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="a636f-127">Verificare che l'installazione di Windows sia aggiornata e includa l'aggiornamento [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), che può essere installato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="a636f-127">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="a636f-128">Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span><span class="sxs-lookup"><span data-stu-id="a636f-128">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="a636f-129">**Per Windows 7 o Windows Server 2008 R2:**</span><span class="sxs-lookup"><span data-stu-id="a636f-129">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="a636f-130">Oltre all'aggiornamento KB2999226, verificare che sia installato anche l'aggiornamento [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot).</span><span class="sxs-lookup"><span data-stu-id="a636f-130">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="a636f-131">Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span><span class="sxs-lookup"><span data-stu-id="a636f-131">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a><span data-ttu-id="a636f-132">Prerequisiti per lo sviluppo di app .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a636f-132">Prerequisites to develop .NET Core apps with Visual Studio</span></span>
    
<span data-ttu-id="a636f-133">Anche se è possibile usare qualsiasi editor per sviluppare applicazioni .NET Core usando il .NET Core SDK, Visual Studio 2017 e versioni successive forniscono una Integrated Development Environment per le app .NET Core in Windows.</span><span class="sxs-lookup"><span data-stu-id="a636f-133">Even though you can use any editor to develop .NET Core applications using the .NET Core SDK, Visual Studio 2017 and later versions provide an integrated development environment for .NET Core apps on Windows.</span></span>

<a name="vs-mapping"></a>

<span data-ttu-id="a636f-134">Per ogni versione di .NET Core è necessaria una versione minima di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a636f-134">Each .NET Core version has a minimum version of Visual Studio required.</span></span> <span data-ttu-id="a636f-135">Per verificare la versione di Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="a636f-135">To verify your Visual Studio version:</span></span>

* <span data-ttu-id="a636f-136">Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="a636f-136">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
* <span data-ttu-id="a636f-137">Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.</span><span class="sxs-lookup"><span data-stu-id="a636f-137">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>

<span data-ttu-id="a636f-138">La tabella seguente elenca la versione minima per ogni SDK:</span><span class="sxs-lookup"><span data-stu-id="a636f-138">The following table lists the minimum version for each SDK:</span></span>

| <span data-ttu-id="a636f-139">Versione .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="a636f-139">.NET Core SDK version</span></span> | <span data-ttu-id="a636f-140">Versione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a636f-140">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="a636f-141">3.0</span><span class="sxs-lookup"><span data-stu-id="a636f-141">3.0</span></span>                   | <span data-ttu-id="a636f-142">Visual Studio 2019 versione 16,3 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a636f-142">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="a636f-143">2.2</span><span class="sxs-lookup"><span data-stu-id="a636f-143">2.2</span></span>                   | <span data-ttu-id="a636f-144">Visual Studio 2017 versione 15,9 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a636f-144">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="a636f-145">2.1</span><span class="sxs-lookup"><span data-stu-id="a636f-145">2.1</span></span>                   | <span data-ttu-id="a636f-146">Visual Studio 2017 versione 15,7 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a636f-146">Visual Studio 2017 version 15.7 or higher.</span></span> |
| <span data-ttu-id="a636f-147">1. x</span><span class="sxs-lookup"><span data-stu-id="a636f-147">1.x</span></span>                   | <span data-ttu-id="a636f-148">Visual Studio 2017 versione 15,0 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a636f-148">Visual Studio 2017 version 15.0 or higher.</span></span> |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="a636f-149">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a636f-149">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="a636f-150">Per sviluppare app .NET Core in Visual Studio 2019 usando .NET Core 3,0 SDK:</span><span class="sxs-lookup"><span data-stu-id="a636f-150">To develop .NET Core apps in Visual Studio 2019 using the .NET Core 3.0 SDK:</span></span>

* <span data-ttu-id="a636f-151">[Scaricare e installare Visual Studio 2019 versione 16,3 o successiva](/visualstudio/install/install-visual-studio) e selezionare uno dei carichi di lavoro seguenti che include la .NET Core SDK, a seconda del tipo di applicazione che si sta compilando:</span><span class="sxs-lookup"><span data-stu-id="a636f-151">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) and select one of the following workloads that includes the .NET Core SDK, depending on the kind of application you're building:</span></span>

  * <span data-ttu-id="a636f-152">Il carico di lavoro **sviluppo multipiattaforma .NET Core** nella sezione **altri set di strumenti** .</span><span class="sxs-lookup"><span data-stu-id="a636f-152">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
  * <span data-ttu-id="a636f-153">Il carico di lavoro di **sviluppo ASP.NET e Web** nella sezione **Web & cloud** .</span><span class="sxs-lookup"><span data-stu-id="a636f-153">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
  * <span data-ttu-id="a636f-154">Carico di lavoro **sviluppo di NET desktop** nella sezione **Windows** .</span><span class="sxs-lookup"><span data-stu-id="a636f-154">The **NET desktop development** workload in the **Windows** section.</span></span>

<span data-ttu-id="a636f-155">La figura seguente mostra il carico di lavoro **sviluppo multipiattaforma .NET Core** selezionato nell'interfaccia utente di Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="a636f-155">The following image shows the **.NET Core cross-platform development** workload selected in the Visual Studio UI:</span></span>

![Screenshot dell'installazione di Visual Studio 2019 con il carico di lavoro "sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-2019-workloads.jpg)

<span data-ttu-id="a636f-157">Visual Studio 2019 16,3 USA .NET Core 3,0 SDK per impostazione predefinita dopo l'installazione di uno di questi carichi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a636f-157">Visual Studio 2019 16.3 uses .NET Core 3.0 SDK by default after any of these workloads are installed.</span></span>

<span data-ttu-id="a636f-158">Se si vuole che i progetti esistenti usino il runtime di .NET Core più recente, ridestinare ogni progetto .NET Core esistente a .NET Core 3,0 usando le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a636f-158">If you want your existing projects to use the latest .NET Core runtime, retarget each existing .NET Core project to .NET Core 3.0 using the following instructions:</span></span>

* <span data-ttu-id="a636f-159">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a636f-159">On the **Project** menu, choose **Properties**.</span></span>
* <span data-ttu-id="a636f-160">Nel menu di selezione del **Framework di destinazione** impostare il valore su **.NET Core 3,0**.</span><span class="sxs-lookup"><span data-stu-id="a636f-160">In the **Target framework** selection menu, set the value to **.NET Core 3.0**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2019 con la voce di menu Framework di destinazione ".NET Core 3,0" selezionata](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

<span data-ttu-id="a636f-162">Dopo aver configurato Visual Studio con .NET Core 3,0 SDK, è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a636f-162">Once you have Visual Studio configured with .NET Core 3.0 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="a636f-163">Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="a636f-163">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="a636f-164">Ridestinare i progetti .NET Core 1. x e 2. x a .NET Core 3,0, compilare ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="a636f-164">Retarget .NET Core 1.x and 2.x projects to .NET Core 3.0, build, and run.</span></span>
* <span data-ttu-id="a636f-165">Creare nuovi progetti .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="a636f-165">Create new .NET Core 3.0 projects.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="a636f-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="a636f-166">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="a636f-167">Per sviluppare app .NET Core in Visual Studio 2017 con .NET Core 2.2 SDK:</span><span class="sxs-lookup"><span data-stu-id="a636f-167">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

* <span data-ttu-id="a636f-168">[Scaricare e installare Visual Studio 2017 versione 15.9.0 o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="a636f-168">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="a636f-170">Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio installa in genere una versione precedente di .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="a636f-170">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="a636f-171">Visual Studio 2017 15.9, ad esempio, usa .NET Core 2.1 SDK per impostazione predefinita dopo l'installazione del carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="a636f-171">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="a636f-172">Per aggiornare Visual Studio per usare .NET Core 2.2 SDK:</span><span class="sxs-lookup"><span data-stu-id="a636f-172">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="a636f-173">Installare [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="a636f-173">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="a636f-174">Se si vuole che il progetto usi la versione più recente di .NET Core Runtime, ridestinare ogni progetto .NET Core esistente o nuovo a .NET Core 2,2 usando le istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a636f-174">If you want your project to use the latest .NET Core runtime, retarget each existing or new .NET Core project to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="a636f-175">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a636f-175">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="a636f-176">Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.2**.</span><span class="sxs-lookup"><span data-stu-id="a636f-176">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione ".NET Core 2.2" selezionata](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="a636f-178">Dopo aver configurato Visual Studio con .NET Core 2.2 SDK, è possibile eseguire le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a636f-178">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="a636f-179">Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.</span><span class="sxs-lookup"><span data-stu-id="a636f-179">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="a636f-180">Ridestinare i progetti .NET Core 1.x e 2.x a .NET Core 2.2, compilarli ed eseguirli.</span><span class="sxs-lookup"><span data-stu-id="a636f-180">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="a636f-181">Creare nuovi progetti .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="a636f-181">Create new .NET Core 2.2 projects.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a636f-182">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a636f-182">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="a636f-183">Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.</span><span class="sxs-lookup"><span data-stu-id="a636f-183">To develop .NET Core 1.x apps in Visual Studio, [download and install Visual Studio 2017](/visualstudio/install/install-visual-studio) with the **".NET Core cross-platform development"** workload (in the **Other Toolsets** section) selected.</span></span>

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> <span data-ttu-id="a636f-185">È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="a636f-185">It's possible to use Visual Studio 2015 for .NET Core 1.x development, but it's not recommended for the following reasons:</span></span>
>
> * <span data-ttu-id="a636f-186">Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.</span><span class="sxs-lookup"><span data-stu-id="a636f-186">The .NET Core tooling is a preview version, which is not supported.</span></span>
> * <span data-ttu-id="a636f-187">I progetti sono basati sul file project.json che è stato deprecato.</span><span class="sxs-lookup"><span data-stu-id="a636f-187">The projects are project.json-based, which is deprecated.</span></span>
>
> <span data-ttu-id="a636f-188">Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).</span><span class="sxs-lookup"><span data-stu-id="a636f-188">For more information about the project format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

---
