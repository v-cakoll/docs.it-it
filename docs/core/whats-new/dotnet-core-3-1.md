---
title: Novità di .NET Core 3.1
description: Informazioni sulle nuove funzionalità disponibili in .NET Core 3,1.
dev_langs:
- csharp
author: adegeo
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 2373b21e92c6ca68aac33684a9bd0912a2e642b3
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324268"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="4dc57-103">Novità di .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="4dc57-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="4dc57-104">Questo articolo descrive le novità di .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="4dc57-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="4dc57-105">Questa versione contiene miglioramenti secondari a .NET Core 3,0, con particolare attenzione alle piccole, ma importanti correzioni.</span><span class="sxs-lookup"><span data-stu-id="4dc57-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="4dc57-106">La funzionalità più importante di .NET Core 3,1 è che si tratta di una versione di [supporto a lungo termine (LTS)](#long-term-support) .</span><span class="sxs-lookup"><span data-stu-id="4dc57-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="4dc57-107">Se si usa Visual Studio 2019, è necessario eseguire l'aggiornamento a [Visual studio 2019 versione 16,4 o successiva](https://visualstudio.microsoft.com/downloads/) per lavorare con i progetti .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="4dc57-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4 or later](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="4dc57-108">Per informazioni sulle novità di Visual Studio versione 16,4, vedere Novità di [Visual studio 2019 versione 16,4](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span><span class="sxs-lookup"><span data-stu-id="4dc57-108">For information on what's new in Visual Studio version 16.4, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes-v16.4#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="4dc57-109">Visual Studio per Mac supporta inoltre e include .NET Core 3,1 in Visual Studio per Mac 8,4.</span><span class="sxs-lookup"><span data-stu-id="4dc57-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="4dc57-110">Per ulteriori informazioni sulla versione, vedere l' [annuncio di .NET Core 3,1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="4dc57-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="4dc57-111">[Scaricare e iniziare a usare .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1) in Windows, MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="4dc57-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="4dc57-112">Supporto a lungo termine</span><span class="sxs-lookup"><span data-stu-id="4dc57-112">Long-term support</span></span>

<span data-ttu-id="4dc57-113">.NET Core 3,1 è una versione LTS con supporto Microsoft per i prossimi tre anni.</span><span class="sxs-lookup"><span data-stu-id="4dc57-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="4dc57-114">Si consiglia vivamente di spostare le app in .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="4dc57-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="4dc57-115">Il ciclo di vita corrente di altre versioni principali è il seguente:</span><span class="sxs-lookup"><span data-stu-id="4dc57-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="4dc57-116">Versione</span><span class="sxs-lookup"><span data-stu-id="4dc57-116">Release</span></span> | <span data-ttu-id="4dc57-117">Nota</span><span class="sxs-lookup"><span data-stu-id="4dc57-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="4dc57-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4dc57-118">.NET Core 3.0</span></span> | <span data-ttu-id="4dc57-119">Fine vita il 3 marzo 2020.</span><span class="sxs-lookup"><span data-stu-id="4dc57-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="4dc57-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="4dc57-120">.NET Core 2.2</span></span> | <span data-ttu-id="4dc57-121">Fine vita il 23 dicembre 2019.</span><span class="sxs-lookup"><span data-stu-id="4dc57-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="4dc57-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4dc57-122">.NET Core 2.1</span></span> | <span data-ttu-id="4dc57-123">Fine del ciclo di vita del 21 agosto 2021.</span><span class="sxs-lookup"><span data-stu-id="4dc57-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="4dc57-124">Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="4dc57-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="macos-apphost-and-notarization"></a><span data-ttu-id="4dc57-125">appHost e autenticazione macOS</span><span class="sxs-lookup"><span data-stu-id="4dc57-125">macOS appHost and notarization</span></span>

<span data-ttu-id="4dc57-126">*solo macOS*</span><span class="sxs-lookup"><span data-stu-id="4dc57-126">*macOS only*</span></span>

<span data-ttu-id="4dc57-127">A partire dalla .NET Core SDK autenticata 3,1 per macOS, l'impostazione appHost è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4dc57-127">Starting with the notarized .NET Core SDK 3.1 for macOS, the appHost setting is disabled by default.</span></span> <span data-ttu-id="4dc57-128">Per altre informazioni, vedere [la pagina relativa all'autenticazione di MacOS Catalina e l'effetto sui download e sui progetti di .NET Core](../install/macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4dc57-128">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="4dc57-129">Quando è abilitata l'impostazione appHost, .NET Core genera un eseguibile nativo di Mach-O durante la compilazione o la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="4dc57-129">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="4dc57-130">L'app viene eseguita nel contesto di appHost quando viene eseguita dal codice sorgente con il `dotnet run` comando oppure avviando direttamente il file eseguibile di Mach-O.</span><span class="sxs-lookup"><span data-stu-id="4dc57-130">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="4dc57-131">Senza appHost, l'unico modo in cui un utente può avviare un'app [dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) è con il `dotnet <filename.dll>` comando.</span><span class="sxs-lookup"><span data-stu-id="4dc57-131">Without the appHost, the only way a user can start a [runtime-dependent](../deploying/index.md#publish-runtime-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="4dc57-132">Quando si pubblica l'app [autonoma](../deploying/index.md#publish-self-contained), viene sempre creato un APPHOST.</span><span class="sxs-lookup"><span data-stu-id="4dc57-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="4dc57-133">È possibile configurare appHost a livello di progetto o impostare il appHost per un `dotnet` comando specifico con il `-p:UseAppHost` parametro:</span><span class="sxs-lookup"><span data-stu-id="4dc57-133">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="4dc57-134">File di progetto</span><span class="sxs-lookup"><span data-stu-id="4dc57-134">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="4dc57-135">Parametro della riga di comando</span><span class="sxs-lookup"><span data-stu-id="4dc57-135">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="4dc57-136">Per ulteriori informazioni sull' `UseAppHost` impostazione, vedere [Proprietà MSBuild per Microsoft. NET. SDK](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="4dc57-136">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="4dc57-137">Windows Form</span><span class="sxs-lookup"><span data-stu-id="4dc57-137">Windows Forms</span></span>

<span data-ttu-id="4dc57-138">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="4dc57-138">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="4dc57-139">Sono state apportate modifiche di rilievo in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4dc57-139">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="4dc57-140">I controlli legacy erano inclusi in Windows Forms che non erano disponibili nella casella degli strumenti di progettazione di Visual Studio per un certo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="4dc57-140">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="4dc57-141">Questi sono stati sostituiti con nuovi controlli nella .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="4dc57-141">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="4dc57-142">Questi elementi sono stati rimossi da desktop SDK per .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="4dc57-142">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="4dc57-143">Rimozione del controllo</span><span class="sxs-lookup"><span data-stu-id="4dc57-143">Removed control</span></span> | <span data-ttu-id="4dc57-144">Sostituzione consigliata</span><span class="sxs-lookup"><span data-stu-id="4dc57-144">Recommended replacement</span></span> | <span data-ttu-id="4dc57-145">API associate rimosse</span><span class="sxs-lookup"><span data-stu-id="4dc57-145">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="4dc57-146">DataGrid</span><span class="sxs-lookup"><span data-stu-id="4dc57-146">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="4dc57-147">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="4dc57-147">DataGridCell</span></span><br/><span data-ttu-id="4dc57-148">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="4dc57-148">DataGridRow</span></span><br/><span data-ttu-id="4dc57-149">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="4dc57-149">DataGridTableCollection</span></span><br/><span data-ttu-id="4dc57-150">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="4dc57-150">DataGridColumnCollection</span></span><br/><span data-ttu-id="4dc57-151">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="4dc57-151">DataGridTableStyle</span></span><br/><span data-ttu-id="4dc57-152">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="4dc57-152">DataGridColumnStyle</span></span><br/><span data-ttu-id="4dc57-153">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="4dc57-153">DataGridLineStyle</span></span><br/><span data-ttu-id="4dc57-154">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="4dc57-154">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="4dc57-155">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="4dc57-155">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="4dc57-156">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="4dc57-156">DataGridBoolColumn</span></span><br/><span data-ttu-id="4dc57-157">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="4dc57-157">DataGridTextBox</span></span><br/><span data-ttu-id="4dc57-158">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="4dc57-158">GridColumnStylesCollection</span></span><br/><span data-ttu-id="4dc57-159">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="4dc57-159">GridTableStylesCollection</span></span><br/><span data-ttu-id="4dc57-160">HitTestType</span><span class="sxs-lookup"><span data-stu-id="4dc57-160">HitTestType</span></span> |
| <span data-ttu-id="4dc57-161">ToolBar</span><span class="sxs-lookup"><span data-stu-id="4dc57-161">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="4dc57-162">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="4dc57-162">ToolBarAppearance</span></span> |
| <span data-ttu-id="4dc57-163">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="4dc57-163">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="4dc57-164">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="4dc57-164">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="4dc57-165">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="4dc57-165">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="4dc57-166">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="4dc57-166">ToolBarButtonStyle</span></span><br/><span data-ttu-id="4dc57-167">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="4dc57-167">ToolBarTextAlign</span></span> |
| <span data-ttu-id="4dc57-168">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="4dc57-168">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="4dc57-169">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="4dc57-169">MenuItemCollection</span></span> |
| <span data-ttu-id="4dc57-170">MainMenu</span><span class="sxs-lookup"><span data-stu-id="4dc57-170">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="4dc57-171">MenuItem</span><span class="sxs-lookup"><span data-stu-id="4dc57-171">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="4dc57-172">Si consiglia di aggiornare le applicazioni a .NET Core 3,1 e di passare ai controlli sostitutivi.</span><span class="sxs-lookup"><span data-stu-id="4dc57-172">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="4dc57-173">La sostituzione dei controlli è un processo semplice, sostanzialmente "trova e Sostituisci" sul tipo.</span><span class="sxs-lookup"><span data-stu-id="4dc57-173">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="4dc57-174">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="4dc57-174">C++/CLI</span></span>

<span data-ttu-id="4dc57-175">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="4dc57-175">*Windows only*</span></span>

<span data-ttu-id="4dc57-176">È stato aggiunto il supporto per la creazione di progetti C++/CLI (noti anche come "C++ gestiti").</span><span class="sxs-lookup"><span data-stu-id="4dc57-176">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="4dc57-177">I file binari prodotti da questi progetti sono compatibili con .NET Core 3,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="4dc57-177">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="4dc57-178">Per aggiungere il supporto per C++/CLI in Visual Studio 2019 versione 16,4, installare il [carico di lavoro sviluppo di applicazioni desktop con c++](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span><span class="sxs-lookup"><span data-stu-id="4dc57-178">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="4dc57-179">Questo carico di lavoro aggiunge due modelli a Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="4dc57-179">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="4dc57-180">Libreria di classi CLR (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="4dc57-180">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="4dc57-181">Progetto CLR vuoto (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="4dc57-181">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="4dc57-182">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4dc57-182">Next steps</span></span>

- [<span data-ttu-id="4dc57-183">Esaminare le modifiche di rilievo tra .NET Core 3,0 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="4dc57-183">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="4dc57-184">Esaminare le modifiche di rilievo apportate in .NET Core 3,1 per le app Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4dc57-184">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
