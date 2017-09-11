---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
keywords: .NET Core, Windows, prerequisiti, dipendenze, Visual Studio
author: mairaw
ms.author: mairaw
ms.date: 06/26/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0e414af0edbafed5b7f540eda6de2e5078eac789
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="beca0-104">Prerequisiti per .NET Core in Windows</span><span class="sxs-lookup"><span data-stu-id="beca0-104">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="beca0-105">Questo articolo descrive le dipendenze e i prerequisiti per distribuire ed eseguire applicazioni .NET Core in computer Windows e svilupparle con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="beca0-105">This article shows you what dependencies you need to deploy and run .NET Core applications on Windows machines and develop using Visual Studio.</span></span>

## <a name="supported-windows-versions"></a><span data-ttu-id="beca0-106">Versioni di Windows supportate</span><span class="sxs-lookup"><span data-stu-id="beca0-106">Supported Windows versions</span></span>

<span data-ttu-id="beca0-107">.NET Core è supportato nelle versioni di Windows seguenti:</span><span class="sxs-lookup"><span data-stu-id="beca0-107">.NET Core is supported on the following versions of Windows:</span></span>

* <span data-ttu-id="beca0-108">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="beca0-108">Windows 7 SP1</span></span>
* <span data-ttu-id="beca0-109">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="beca0-109">Windows 8.1</span></span>
* <span data-ttu-id="beca0-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="beca0-110">Windows 10</span></span>
* <span data-ttu-id="beca0-111">Windows Server 2008 R2 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="beca0-111">Windows Server 2008 R2 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="beca0-112">Windows Server 2012 SP1 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="beca0-112">Windows Server 2012 SP1 (Full Server or Server Core)</span></span>
* <span data-ttu-id="beca0-113">Windows Server 2012 R2 (Full Server o Server Core)</span><span class="sxs-lookup"><span data-stu-id="beca0-113">Windows Server 2012 R2 (Full Server or Server Core)</span></span>
* <span data-ttu-id="beca0-114">Windows Server 2016 (Full Server, Server Core o Nano Server)</span><span class="sxs-lookup"><span data-stu-id="beca0-114">Windows Server 2016 (Full Server, Server Core or Nano Server)</span></span>

<span data-ttu-id="beca0-115">Per l'elenco completo dei sistemi operativi supportati, vedere le [note sulla versione di .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).</span><span class="sxs-lookup"><span data-stu-id="beca0-115">See the [.NET Core Release Notes](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) for the full set of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="beca0-116">Dipendenze .NET Core</span><span class="sxs-lookup"><span data-stu-id="beca0-116">.NET Core dependencies</span></span>

<span data-ttu-id="beca0-117">.NET Core richiede Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="beca0-117">.NET Core requires the Visual C++ Redistributable when running on Windows versions earlier than Windows 10 and Windows Server 2016.</span></span> <span data-ttu-id="beca0-118">Questa dipendenza viene installata automaticamente se si usa il programma di installazione di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="beca0-118">This dependency is automatically installed for you if you use the .NET Core installer.</span></span> <span data-ttu-id="beca0-119">È invece necessario installare manualmente [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) se si esegue l'installazione di .NET Core tramite lo [script del programma di installazione ](./tools/dotnet-install-script.md) o si distribuisce un'applicazione .NET Core completa.</span><span class="sxs-lookup"><span data-stu-id="beca0-119">However, you need to manually install the [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) if you are installing .NET Core via the [installer script](./tools/dotnet-install-script.md) or deploying a self-contained .NET Core application.</span></span>

> [!NOTE]
> <span data-ttu-id="beca0-120"><em>Solo per i computer Windows 7 e Windows Server 2008:</em></span><span class="sxs-lookup"><span data-stu-id="beca0-120"><em>For Windows 7 and Windows Server 2008 machines only:</em></span></span><br>
> <span data-ttu-id="beca0-121">Verificare che l'installazione di Windows sia aggiornata e includa l'hotfix [KB2533623](https://support.microsoft.com/help/2533623) installato tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="beca0-121">Make sure that your Windows installation is up-to-date and includes hotfix [KB2533623](https://support.microsoft.com/help/2533623) installed through Windows Update.</span></span>

## <a name="prerequisites-with-visual-studio-2017"></a><span data-ttu-id="beca0-122">Prerequisiti con Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="beca0-122">Prerequisites with Visual Studio 2017</span></span>

<span data-ttu-id="beca0-123">È possibile usare l'editor preferito per sviluppare applicazioni .NET Core con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="beca0-123">You can use any editor of your choice to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="beca0-124">Se si vuole tuttavia sviluppare applicazioni .NET Core in Windows in un ambiente di sviluppo integrato, è possibile usare [Visual Studio 2017](#visual-studio-2017).</span><span class="sxs-lookup"><span data-stu-id="beca0-124">However, if you want to develop .NET Core applications on Windows in an integrated development environment, you can use [Visual Studio 2017](#visual-studio-2017).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="beca0-125">Anche se è possibile usare Visual Studio 2015 con una versione di anteprima degli strumenti di .NET Core, questi progetti saranno basati su *project.json*, che ora è deprecato.</span><span class="sxs-lookup"><span data-stu-id="beca0-125">Even though, it's possible to use Visual Studio 2015 with a preview version of the .NET Core tooling, these projects will be *project.json*-based, which is now deprecated.</span></span> <span data-ttu-id="beca0-126">Visual Studio 2017 usa file di progetto basati su MSBuild.</span><span class="sxs-lookup"><span data-stu-id="beca0-126">Visual Studio 2017 uses project files based on MSBuild.</span></span> <span data-ttu-id="beca0-127">Per altre informazioni sulle modifiche del formato, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).</span><span class="sxs-lookup"><span data-stu-id="beca0-127">For more information about the format changes, see [High-level overview of changes](./tools/cli-msbuild-architecture.md).</span></span>

<span data-ttu-id="beca0-128">Per usare Visual Studio 2017 per lo sviluppo di app .NET Core, è necessario avere l'ultima versione di Visual Studio installata con il set di strumenti di **sviluppo multipiattaforma di .NET Core** selezionato (nella sezione **Altri set di strumenti**).</span><span class="sxs-lookup"><span data-stu-id="beca0-128">To use Visual Studio 2017 to develop .NET Core apps, you'll need to have the latest version of Visual Studio installed with the **.NET Core cross-platform development** toolset (in the **Other Toolsets** section) selected.</span></span>
<span data-ttu-id="beca0-129">![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)</span><span class="sxs-lookup"><span data-stu-id="beca0-129">![Screenshot of Visual Studio 2017 installation with the ".NET Core cross-platform development" workload selected](./media/windows-prerequisites/vs_workloads.jpg)</span></span>

<span data-ttu-id="beca0-130">Ci sono edizioni diverse di Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="beca0-130">There are different editions of Visual Studio 2017.</span></span> <span data-ttu-id="beca0-131">Per iniziare, è possibile scaricare [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="beca0-131">You can download [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) for free to get started.</span></span>  <span data-ttu-id="beca0-132">Per altre informazioni sul processo di installazione di Visual Studio, vedere [Install Visual Studio 2017](/visualstudio/install/install-visual-studio) (Installare Visual Studio 2017).</span><span class="sxs-lookup"><span data-stu-id="beca0-132">To learn more about the Visual Studio installation process, see [Install Visual Studio 2017](/visualstudio/install/install-visual-studio).</span></span>

<span data-ttu-id="beca0-133">Per verificare che la versione a disposizione sia la più recente di Visual Studio 2017, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="beca0-133">To verify that you're running the latest version of Visual Studio 2017, do the following:</span></span>

 * <span data-ttu-id="beca0-134">Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).</span><span class="sxs-lookup"><span data-stu-id="beca0-134">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
 * <span data-ttu-id="beca0-135">Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** il numero di versione deve essere 15.0.26228.4 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="beca0-135">In the **About Microsoft Visual Studio** dialog, the version number should be 15.0.26228.4 or higher.</span></span>

<span data-ttu-id="beca0-136">Nelle [note sulla versione ](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="beca0-136">You can read more about the changes in Visual Studio 2017 in the [release notes](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes).</span></span>

