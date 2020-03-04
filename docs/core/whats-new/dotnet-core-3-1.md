---
title: Novità di .NET Core 3.1
description: Informazioni sulle nuove funzionalità disponibili in .NET Core 3,1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 323a2390f079c17b81db01e4e3787916251943bf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156556"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="26d73-103">Novità di .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="26d73-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="26d73-104">Questo articolo descrive le novità di .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="26d73-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="26d73-105">Questa versione contiene miglioramenti secondari a .NET Core 3,0, con particolare attenzione alle piccole, ma importanti correzioni.</span><span class="sxs-lookup"><span data-stu-id="26d73-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="26d73-106">La funzionalità più importante di .NET Core 3,1 è che si tratta di una versione di [supporto a lungo termine (LTS)](#long-term-support) .</span><span class="sxs-lookup"><span data-stu-id="26d73-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="26d73-107">Se si usa Visual Studio 2019, è necessario eseguire l'aggiornamento a [Visual studio 2019 versione 16,4](https://visualstudio.microsoft.com/downloads/) per lavorare con i progetti .net core 3,1.</span><span class="sxs-lookup"><span data-stu-id="26d73-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="26d73-108">Per ulteriori informazioni sulle novità di Visual Studio, vedere Novità di [Visual studio 2019 versione 16,4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).</span><span class="sxs-lookup"><span data-stu-id="26d73-108">For more information on what's new in Visual Studio, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="26d73-109">Visual Studio per Mac supporta inoltre e include .NET Core 3,1 in Visual Studio per Mac 8,4.</span><span class="sxs-lookup"><span data-stu-id="26d73-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="26d73-110">Per ulteriori informazioni sulla versione, vedere l' [annuncio di .NET Core 3,1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="26d73-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="26d73-111">[Scaricare e iniziare a usare .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1) in Windows, MacOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="26d73-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="26d73-112">Supporto a lungo termine</span><span class="sxs-lookup"><span data-stu-id="26d73-112">Long-term support</span></span>

<span data-ttu-id="26d73-113">.NET Core 3,1 è una versione LTS con supporto Microsoft per i prossimi tre anni.</span><span class="sxs-lookup"><span data-stu-id="26d73-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="26d73-114">Si consiglia vivamente di spostare le app in .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="26d73-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="26d73-115">Il ciclo di vita corrente di altre versioni principali è il seguente:</span><span class="sxs-lookup"><span data-stu-id="26d73-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="26d73-116">Versione</span><span class="sxs-lookup"><span data-stu-id="26d73-116">Release</span></span> | <span data-ttu-id="26d73-117">Note</span><span class="sxs-lookup"><span data-stu-id="26d73-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="26d73-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="26d73-118">.NET Core 3.0</span></span> | <span data-ttu-id="26d73-119">Fine vita il 3 marzo 2020.</span><span class="sxs-lookup"><span data-stu-id="26d73-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="26d73-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="26d73-120">.NET Core 2.2</span></span> | <span data-ttu-id="26d73-121">Fine vita il 23 dicembre 2019.</span><span class="sxs-lookup"><span data-stu-id="26d73-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="26d73-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="26d73-122">.NET Core 2.1</span></span> | <span data-ttu-id="26d73-123">Fine del ciclo di vita del 21 agosto 2021.</span><span class="sxs-lookup"><span data-stu-id="26d73-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="26d73-124">Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="26d73-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="macos-apphost-and-notarization"></a><span data-ttu-id="26d73-125">appHost e autenticazione macOS</span><span class="sxs-lookup"><span data-stu-id="26d73-125">macOS appHost and notarization</span></span>

<span data-ttu-id="26d73-126">*solo macOS*</span><span class="sxs-lookup"><span data-stu-id="26d73-126">*macOS only*</span></span>

<span data-ttu-id="26d73-127">A partire dalla .NET Core SDK autenticata 3,1 per macOS, l'impostazione appHost è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="26d73-127">Starting with the notarized .NET Core SDK 3.1 for macOS, the appHost setting is disabled by default.</span></span> <span data-ttu-id="26d73-128">Per altre informazioni, vedere [la pagina relativa all'autenticazione di MacOS Catalina e l'effetto sui download e sui progetti di .NET Core](../install/macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="26d73-128">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="26d73-129">Quando è abilitata l'impostazione appHost, .NET Core genera un eseguibile nativo di Mach-O durante la compilazione o la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="26d73-129">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="26d73-130">L'app viene eseguita nel contesto di appHost quando viene eseguita dal codice sorgente con il comando `dotnet run` o avviando direttamente il file eseguibile di Mach-O.</span><span class="sxs-lookup"><span data-stu-id="26d73-130">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="26d73-131">Senza appHost, l'unico modo in cui un utente può avviare un'app [dipendente dal runtime](../deploying/index.md#publish-runtime-dependent) è con il comando `dotnet <filename.dll>`.</span><span class="sxs-lookup"><span data-stu-id="26d73-131">Without the appHost, the only way a user can start a [runtime-dependent](../deploying/index.md#publish-runtime-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="26d73-132">Quando si pubblica l'app [autonoma](../deploying/index.md#publish-self-contained), viene sempre creato un APPHOST.</span><span class="sxs-lookup"><span data-stu-id="26d73-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="26d73-133">È possibile configurare appHost a livello di progetto o impostare il appHost per un comando `dotnet` specifico con il parametro `-p:UseAppHost`:</span><span class="sxs-lookup"><span data-stu-id="26d73-133">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="26d73-134">File di progetto</span><span class="sxs-lookup"><span data-stu-id="26d73-134">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="26d73-135">Parametro della riga di comando</span><span class="sxs-lookup"><span data-stu-id="26d73-135">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="26d73-136">Per ulteriori informazioni sull'impostazione di `UseAppHost`, vedere [Proprietà MSBuild per Microsoft. NET. SDK](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="26d73-136">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="26d73-137">Windows Form</span><span class="sxs-lookup"><span data-stu-id="26d73-137">Windows Forms</span></span>

<span data-ttu-id="26d73-138">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="26d73-138">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="26d73-139">Sono state apportate modifiche di rilievo in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="26d73-139">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="26d73-140">I controlli legacy erano inclusi in Windows Forms che non erano disponibili nella casella degli strumenti di progettazione di Visual Studio per un certo periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="26d73-140">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="26d73-141">Questi sono stati sostituiti con nuovi controlli nella .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="26d73-141">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="26d73-142">Questi elementi sono stati rimossi da desktop SDK per .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="26d73-142">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="26d73-143">Rimozione del controllo</span><span class="sxs-lookup"><span data-stu-id="26d73-143">Removed control</span></span> | <span data-ttu-id="26d73-144">Sostituzione consigliata</span><span class="sxs-lookup"><span data-stu-id="26d73-144">Recommended replacement</span></span> | <span data-ttu-id="26d73-145">API associate rimosse</span><span class="sxs-lookup"><span data-stu-id="26d73-145">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="26d73-146">DataGrid</span><span class="sxs-lookup"><span data-stu-id="26d73-146">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="26d73-147">DataGridCell</span><span class="sxs-lookup"><span data-stu-id="26d73-147">DataGridCell</span></span><br/><span data-ttu-id="26d73-148">DataGridRow</span><span class="sxs-lookup"><span data-stu-id="26d73-148">DataGridRow</span></span><br/><span data-ttu-id="26d73-149">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="26d73-149">DataGridTableCollection</span></span><br/><span data-ttu-id="26d73-150">DataGridColumnCollection</span><span class="sxs-lookup"><span data-stu-id="26d73-150">DataGridColumnCollection</span></span><br/><span data-ttu-id="26d73-151">DataGridTableStyle</span><span class="sxs-lookup"><span data-stu-id="26d73-151">DataGridTableStyle</span></span><br/><span data-ttu-id="26d73-152">DataGridColumnStyle</span><span class="sxs-lookup"><span data-stu-id="26d73-152">DataGridColumnStyle</span></span><br/><span data-ttu-id="26d73-153">DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="26d73-153">DataGridLineStyle</span></span><br/><span data-ttu-id="26d73-154">DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="26d73-154">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="26d73-155">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="26d73-155">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="26d73-156">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="26d73-156">DataGridBoolColumn</span></span><br/><span data-ttu-id="26d73-157">DataGridTextBox</span><span class="sxs-lookup"><span data-stu-id="26d73-157">DataGridTextBox</span></span><br/><span data-ttu-id="26d73-158">GridColumnStylesCollection</span><span class="sxs-lookup"><span data-stu-id="26d73-158">GridColumnStylesCollection</span></span><br/><span data-ttu-id="26d73-159">GridTableStylesCollection</span><span class="sxs-lookup"><span data-stu-id="26d73-159">GridTableStylesCollection</span></span><br/><span data-ttu-id="26d73-160">HitTestType</span><span class="sxs-lookup"><span data-stu-id="26d73-160">HitTestType</span></span> |
| <span data-ttu-id="26d73-161">ToolBar</span><span class="sxs-lookup"><span data-stu-id="26d73-161">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="26d73-162">ToolBarAppearance</span><span class="sxs-lookup"><span data-stu-id="26d73-162">ToolBarAppearance</span></span> |
| <span data-ttu-id="26d73-163">ToolBarButton</span><span class="sxs-lookup"><span data-stu-id="26d73-163">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="26d73-164">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="26d73-164">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="26d73-165">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="26d73-165">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="26d73-166">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="26d73-166">ToolBarButtonStyle</span></span><br/><span data-ttu-id="26d73-167">ToolBarTextAlign</span><span class="sxs-lookup"><span data-stu-id="26d73-167">ToolBarTextAlign</span></span> |
| <span data-ttu-id="26d73-168">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="26d73-168">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="26d73-169">MenuItemCollection</span><span class="sxs-lookup"><span data-stu-id="26d73-169">MenuItemCollection</span></span> |
| <span data-ttu-id="26d73-170">MainMenu</span><span class="sxs-lookup"><span data-stu-id="26d73-170">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="26d73-171">MenuItem</span><span class="sxs-lookup"><span data-stu-id="26d73-171">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="26d73-172">Si consiglia di aggiornare le applicazioni a .NET Core 3,1 e di passare ai controlli sostitutivi.</span><span class="sxs-lookup"><span data-stu-id="26d73-172">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="26d73-173">La sostituzione dei controlli è un processo semplice, sostanzialmente "trova e Sostituisci" sul tipo.</span><span class="sxs-lookup"><span data-stu-id="26d73-173">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="26d73-174">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="26d73-174">C++/CLI</span></span>

<span data-ttu-id="26d73-175">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="26d73-175">*Windows only*</span></span>

<span data-ttu-id="26d73-176">È stato aggiunto il supporto per C++la creazione di progetti/CLI (noti C++anche come "gestiti").</span><span class="sxs-lookup"><span data-stu-id="26d73-176">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="26d73-177">I file binari prodotti da questi progetti sono compatibili con .NET Core 3,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="26d73-177">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="26d73-178">Per aggiungere il supporto C++per/CLI in Visual Studio 2019 versione 16,4, installare lo [sviluppo di C++ applicazioni desktop con il carico di lavoro](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span><span class="sxs-lookup"><span data-stu-id="26d73-178">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="26d73-179">Questo carico di lavoro aggiunge due modelli a Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="26d73-179">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="26d73-180">Libreria di classi CLR (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="26d73-180">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="26d73-181">Progetto CLR vuoto (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="26d73-181">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="26d73-182">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="26d73-182">Next steps</span></span>

- [<span data-ttu-id="26d73-183">Esaminare le modifiche di rilievo tra .NET Core 3,0 e 3,1.</span><span class="sxs-lookup"><span data-stu-id="26d73-183">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="26d73-184">Esaminare le modifiche di rilievo apportate in .NET Core 3,1 per le app Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="26d73-184">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
