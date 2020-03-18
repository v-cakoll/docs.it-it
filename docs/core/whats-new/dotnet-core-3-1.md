---
title: Novità di .NET Core 3.1
description: Informazioni sulle nuove funzionalità disponibili in .NET Core 3.1.Learn about the new features found in .NET Core 3.1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 323a2390f079c17b81db01e4e3787916251943bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156556"
---
# <a name="whats-new-in-net-core-31"></a><span data-ttu-id="f837f-103">Novità di .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f837f-103">What's new in .NET Core 3.1</span></span>

<span data-ttu-id="f837f-104">In questo articolo vengono descritte le novità di .NET Core 3.1.This article describes what is new in .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f837f-104">This article describes what is new in .NET Core 3.1.</span></span> <span data-ttu-id="f837f-105">Questa versione contiene piccoli miglioramenti a .NET Core 3.0, concentrandosi su correzioni piccole ma importanti.</span><span class="sxs-lookup"><span data-stu-id="f837f-105">This release contains minor improvements to .NET Core 3.0, focusing on small, but important, fixes.</span></span> <span data-ttu-id="f837f-106">La funzionalità più importante di .NET Core 3.1 è che si tratta di una versione [di supporto a lungo termine (LTS).](#long-term-support)</span><span class="sxs-lookup"><span data-stu-id="f837f-106">The most important feature about .NET Core 3.1 is that it's a [long-term support (LTS)](#long-term-support) release.</span></span>

<span data-ttu-id="f837f-107">Se si usa Visual Studio 2019, è necessario eseguire l'aggiornamento a [Visual Studio 2019 versione 16.4](https://visualstudio.microsoft.com/downloads/) per usare i progetti .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f837f-107">If you're using Visual Studio 2019, you must update to [Visual Studio 2019 version 16.4](https://visualstudio.microsoft.com/downloads/) to work with .NET Core 3.1 projects.</span></span> <span data-ttu-id="f837f-108">Per altre informazioni sulle novità di Visual Studio, vedere Novità di Visual Studio 2019 versione 16.4.For more information on what's new in Visual Studio, see [What's New in Visual Studio 2019 version 16.4.](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164)</span><span class="sxs-lookup"><span data-stu-id="f837f-108">For more information on what's new in Visual Studio, see [What's New in Visual Studio 2019 version 16.4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).</span></span>

<span data-ttu-id="f837f-109">Visual Studio per Mac supporta e include .NET Core 3.1 in Visual Studio per Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="f837f-109">Visual Studio for Mac also supports and includes .NET Core 3.1 in Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="f837f-110">Per ulteriori informazioni sulla versione, vedere l'annuncio di [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span><span class="sxs-lookup"><span data-stu-id="f837f-110">For more information about the release, see the [.NET Core 3.1 announcement](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

- <span data-ttu-id="f837f-111">[Scarica e inizia a usare .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) su Windows, macOS o Linux.</span><span class="sxs-lookup"><span data-stu-id="f837f-111">[Download and get started with .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) on Windows, macOS, or Linux.</span></span>

## <a name="long-term-support"></a><span data-ttu-id="f837f-112">Supporto a lungo termine</span><span class="sxs-lookup"><span data-stu-id="f837f-112">Long-term support</span></span>

<span data-ttu-id="f837f-113">.NET Core 3.1 è una versione LTS con il supporto di Microsoft per i prossimi tre anni.</span><span class="sxs-lookup"><span data-stu-id="f837f-113">.NET Core 3.1 is an LTS release with support from Microsoft for the next three years.</span></span> <span data-ttu-id="f837f-114">È consigliabile spostare le app in .NET Core 3.1.It's highly recommended that you move your apps to .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f837f-114">It's highly recommended that you move your apps to .NET Core 3.1.</span></span> <span data-ttu-id="f837f-115">Il ciclo di vita corrente di altre versioni principali è il seguente:</span><span class="sxs-lookup"><span data-stu-id="f837f-115">The current lifecycle of other major releases is as follows:</span></span>

| <span data-ttu-id="f837f-116">Versione</span><span class="sxs-lookup"><span data-stu-id="f837f-116">Release</span></span> | <span data-ttu-id="f837f-117">Note</span><span class="sxs-lookup"><span data-stu-id="f837f-117">Note</span></span> |
| ------- | ---- |
| <span data-ttu-id="f837f-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f837f-118">.NET Core 3.0</span></span> | <span data-ttu-id="f837f-119">Fine del ciclo di vita il 3 marzo 2020.</span><span class="sxs-lookup"><span data-stu-id="f837f-119">End of life on March 3, 2020.</span></span>     |
| <span data-ttu-id="f837f-120">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="f837f-120">.NET Core 2.2</span></span> | <span data-ttu-id="f837f-121">Fine del ciclo di vita il 23 dicembre 2019.</span><span class="sxs-lookup"><span data-stu-id="f837f-121">End of life on December 23, 2019.</span></span> |
| <span data-ttu-id="f837f-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f837f-122">.NET Core 2.1</span></span> | <span data-ttu-id="f837f-123">Fine del ciclo di vita il 21 agosto 2021.</span><span class="sxs-lookup"><span data-stu-id="f837f-123">End of life on August 21, 2021.</span></span>    |

<span data-ttu-id="f837f-124">Per ulteriori informazioni, vedere i criteri di supporto di [.NET Core.](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)</span><span class="sxs-lookup"><span data-stu-id="f837f-124">For more information, see the [.NET Core support policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="macos-apphost-and-notarization"></a><span data-ttu-id="f837f-125">macOS appHost e notarizzazione</span><span class="sxs-lookup"><span data-stu-id="f837f-125">macOS appHost and notarization</span></span>

<span data-ttu-id="f837f-126">*Solo macOS*</span><span class="sxs-lookup"><span data-stu-id="f837f-126">*macOS only*</span></span>

<span data-ttu-id="f837f-127">A partire dal .NET Core SDK 3.1 non arizzato per macOS, l'impostazione appHost è disabilitata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f837f-127">Starting with the notarized .NET Core SDK 3.1 for macOS, the appHost setting is disabled by default.</span></span> <span data-ttu-id="f837f-128">Per ulteriori informazioni, consultate la notificazione di [macOS Catalina e l'impatto sui download e sui progetti di .NET Core.](../install/macos-notarization-issues.md)</span><span class="sxs-lookup"><span data-stu-id="f837f-128">For more information, see [macOS Catalina Notarization and the impact on .NET Core downloads and projects](../install/macos-notarization-issues.md).</span></span>

<span data-ttu-id="f837f-129">Quando l'impostazione appHost è abilitata, .NET Core genera un eseguibile Mach-O nativo durante la compilazione o la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="f837f-129">When the appHost setting is enabled, .NET Core generates a native Mach-O executable when you build or publish.</span></span> <span data-ttu-id="f837f-130">L'app viene eseguita nel contesto di appHost `dotnet run` quando viene eseguita dal codice sorgente con il comando o avviando direttamente l'eseguibile Mach-O.</span><span class="sxs-lookup"><span data-stu-id="f837f-130">Your app runs in the context of the appHost when it is run from source code with the `dotnet run` command, or by starting the Mach-O executable directly.</span></span>

<span data-ttu-id="f837f-131">Senza appHost, l'unico modo in cui un utente `dotnet <filename.dll>` può [avviare](../deploying/index.md#publish-runtime-dependent) un'app dipendente dal runtime è con il comando.</span><span class="sxs-lookup"><span data-stu-id="f837f-131">Without the appHost, the only way a user can start a [runtime-dependent](../deploying/index.md#publish-runtime-dependent) app is with the `dotnet <filename.dll>` command.</span></span> <span data-ttu-id="f837f-132">Un appHost viene sempre creato quando si pubblica l'app [indipendente.](../deploying/index.md#publish-self-contained)</span><span class="sxs-lookup"><span data-stu-id="f837f-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="f837f-133">Puoi configurare appHost a livello di progetto o attivare `dotnet` o `-p:UseAppHost` disattivare l'appHost per un comando specifico con il parametro:</span><span class="sxs-lookup"><span data-stu-id="f837f-133">You can either configure the appHost at the project level, or toggle the appHost for a specific `dotnet` command with the `-p:UseAppHost` parameter:</span></span>

- <span data-ttu-id="f837f-134">File di progetto</span><span class="sxs-lookup"><span data-stu-id="f837f-134">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="f837f-135">Parametro della riga di comando</span><span class="sxs-lookup"><span data-stu-id="f837f-135">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="f837f-136">Per ulteriori informazioni `UseAppHost` sull'impostazione, vedere [Proprietà MSBuild per Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span><span class="sxs-lookup"><span data-stu-id="f837f-136">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

## <a name="windows-forms"></a><span data-ttu-id="f837f-137">Windows Form</span><span class="sxs-lookup"><span data-stu-id="f837f-137">Windows Forms</span></span>

<span data-ttu-id="f837f-138">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="f837f-138">*Windows only*</span></span>

> [!WARNING]
> <span data-ttu-id="f837f-139">Sono state apportate modifiche di rilievo in Windows Form.There are breaking changes in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f837f-139">There are breaking changes in Windows Forms.</span></span>

<span data-ttu-id="f837f-140">Controlli legacy sono stati inclusi in Windows Form che sono stati non disponibili nella casella degli strumenti di progettazione di Visual Studio per qualche tempo.</span><span class="sxs-lookup"><span data-stu-id="f837f-140">Legacy controls were included in Windows Forms that have been unavailable in the Visual Studio Designer Toolbox for some time.</span></span> <span data-ttu-id="f837f-141">Questi sono stati sostituiti con nuovi controlli in .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="f837f-141">These were replaced with new controls back in .NET Framework 2.0.</span></span> <span data-ttu-id="f837f-142">Questi sono stati rimossi da Desktop SDK per .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="f837f-142">These have been removed from the Desktop SDK for .NET Core 3.1.</span></span>

| <span data-ttu-id="f837f-143">Controllo rimosso</span><span class="sxs-lookup"><span data-stu-id="f837f-143">Removed control</span></span> | <span data-ttu-id="f837f-144">Sostituzione consigliata</span><span class="sxs-lookup"><span data-stu-id="f837f-144">Recommended replacement</span></span> | <span data-ttu-id="f837f-145">API associate rimosse</span><span class="sxs-lookup"><span data-stu-id="f837f-145">Associated APIs removed</span></span> |
| --------------- | ----------------------- | ----------------------- |
| <span data-ttu-id="f837f-146">DataGrid</span><span class="sxs-lookup"><span data-stu-id="f837f-146">DataGrid</span></span>        | <xref:System.Windows.Forms.DataGridView>      | <span data-ttu-id="f837f-147">Datagridcell</span><span class="sxs-lookup"><span data-stu-id="f837f-147">DataGridCell</span></span><br/><span data-ttu-id="f837f-148">Datagridrow</span><span class="sxs-lookup"><span data-stu-id="f837f-148">DataGridRow</span></span><br/><span data-ttu-id="f837f-149">DataGridTableCollection</span><span class="sxs-lookup"><span data-stu-id="f837f-149">DataGridTableCollection</span></span><br/><span data-ttu-id="f837f-150">Datagridcolumncollection</span><span class="sxs-lookup"><span data-stu-id="f837f-150">DataGridColumnCollection</span></span><br/><span data-ttu-id="f837f-151">Datagridtablestyle</span><span class="sxs-lookup"><span data-stu-id="f837f-151">DataGridTableStyle</span></span><br/><span data-ttu-id="f837f-152">Datagridcolumnstyle</span><span class="sxs-lookup"><span data-stu-id="f837f-152">DataGridColumnStyle</span></span><br/><span data-ttu-id="f837f-153">Oggetto DataGridLineStyle</span><span class="sxs-lookup"><span data-stu-id="f837f-153">DataGridLineStyle</span></span><br/><span data-ttu-id="f837f-154">DataGridParentRowsLabel (Etichetta)DataGridParentRowsLabel</span><span class="sxs-lookup"><span data-stu-id="f837f-154">DataGridParentRowsLabel</span></span><br/><span data-ttu-id="f837f-155">DataGridParentRowsLabelStyle</span><span class="sxs-lookup"><span data-stu-id="f837f-155">DataGridParentRowsLabelStyle</span></span><br/><span data-ttu-id="f837f-156">DataGridBoolColumn</span><span class="sxs-lookup"><span data-stu-id="f837f-156">DataGridBoolColumn</span></span><br/><span data-ttu-id="f837f-157">Datagridtextbox</span><span class="sxs-lookup"><span data-stu-id="f837f-157">DataGridTextBox</span></span><br/><span data-ttu-id="f837f-158">Gridcolumnstylescollection</span><span class="sxs-lookup"><span data-stu-id="f837f-158">GridColumnStylesCollection</span></span><br/><span data-ttu-id="f837f-159">Gridtablestylescollection</span><span class="sxs-lookup"><span data-stu-id="f837f-159">GridTableStylesCollection</span></span><br/><span data-ttu-id="f837f-160">HitTestType (Tipo di HitTest)</span><span class="sxs-lookup"><span data-stu-id="f837f-160">HitTestType</span></span> |
| <span data-ttu-id="f837f-161">ToolBar</span><span class="sxs-lookup"><span data-stu-id="f837f-161">ToolBar</span></span>         | <xref:System.Windows.Forms.ToolStrip>         | <span data-ttu-id="f837f-162">ToolBarAspetto</span><span class="sxs-lookup"><span data-stu-id="f837f-162">ToolBarAppearance</span></span> |
| <span data-ttu-id="f837f-163">Toolbarbutton</span><span class="sxs-lookup"><span data-stu-id="f837f-163">ToolBarButton</span></span>   | <xref:System.Windows.Forms.ToolStripButton>   | <span data-ttu-id="f837f-164">ToolBarButtonClickEventArgs</span><span class="sxs-lookup"><span data-stu-id="f837f-164">ToolBarButtonClickEventArgs</span></span><br/><span data-ttu-id="f837f-165">ToolBarButtonClickEventHandler</span><span class="sxs-lookup"><span data-stu-id="f837f-165">ToolBarButtonClickEventHandler</span></span><br/><span data-ttu-id="f837f-166">ToolBarButtonStyle</span><span class="sxs-lookup"><span data-stu-id="f837f-166">ToolBarButtonStyle</span></span><br/><span data-ttu-id="f837f-167">ToolBarTextAlign (Riga di dialogo)</span><span class="sxs-lookup"><span data-stu-id="f837f-167">ToolBarTextAlign</span></span> |
| <span data-ttu-id="f837f-168">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="f837f-168">ContextMenu</span></span>     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | <span data-ttu-id="f837f-169">Menuitemcollection</span><span class="sxs-lookup"><span data-stu-id="f837f-169">MenuItemCollection</span></span> |
| <span data-ttu-id="f837f-170">MainMenu</span><span class="sxs-lookup"><span data-stu-id="f837f-170">MainMenu</span></span>        | <xref:System.Windows.Forms.MenuStrip>         |  |
| <span data-ttu-id="f837f-171">MenuItem</span><span class="sxs-lookup"><span data-stu-id="f837f-171">MenuItem</span></span>        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

<span data-ttu-id="f837f-172">È consigliabile aggiornare le applicazioni a .NET Core 3.1 e passare ai controlli di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="f837f-172">We recommend you update your applications to .NET Core 3.1 and move to the replacement controls.</span></span> <span data-ttu-id="f837f-173">La sostituzione dei controlli è un processo semplice, essenzialmente "trova e sostituisci" sul tipo.</span><span class="sxs-lookup"><span data-stu-id="f837f-173">Replacing the controls is a straightforward process, essentially "find and replace" on the type.</span></span>

## <a name="ccli"></a><span data-ttu-id="f837f-174">C++/CLI</span><span class="sxs-lookup"><span data-stu-id="f837f-174">C++/CLI</span></span>

<span data-ttu-id="f837f-175">*Solo Windows*</span><span class="sxs-lookup"><span data-stu-id="f837f-175">*Windows only*</span></span>

<span data-ttu-id="f837f-176">È stato aggiunto il supporto per la creazione di progetti in C, c/CLI, noti anche come progetti "gestiti in C).</span><span class="sxs-lookup"><span data-stu-id="f837f-176">Support has been added for creating C++/CLI (also known as "managed C++") projects.</span></span> <span data-ttu-id="f837f-177">I file binari prodotti da questi progetti sono compatibili con .NET Core 3.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="f837f-177">Binaries produced from these projects are compatible with .NET Core 3.0 and later versions.</span></span>

<span data-ttu-id="f837f-178">Per aggiungere il supporto per il linguaggio C.NET/CLI in Visual Studio 2019 versione 16.4, installare lo sviluppo desktop con il carico di lavoro di [C.](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads)</span><span class="sxs-lookup"><span data-stu-id="f837f-178">To add support for C++/CLI in Visual Studio 2019 version 16.4, install the [Desktop development with C++ workload](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads).</span></span> <span data-ttu-id="f837f-179">Questo carico di lavoro aggiunge due modelli a Visual Studio:This workload adds two templates to Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="f837f-179">This workload adds two templates to Visual Studio:</span></span>

- <span data-ttu-id="f837f-180">CLR Class Library (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="f837f-180">CLR Class Library (.NET Core)</span></span>
- <span data-ttu-id="f837f-181">CLR Empty Project (.NET Core)</span><span class="sxs-lookup"><span data-stu-id="f837f-181">CLR Empty Project (.NET Core)</span></span>

## <a name="next-steps"></a><span data-ttu-id="f837f-182">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f837f-182">Next steps</span></span>

- [<span data-ttu-id="f837f-183">Esaminare le modifiche di rilievo tra .NET Core 3.0 e 3.1.Review the breaking changes between .NET Core 3.0 and 3.1.</span><span class="sxs-lookup"><span data-stu-id="f837f-183">Review the breaking changes between .NET Core 3.0 and 3.1.</span></span>](../compatibility/3.0-3.1.md)
- [<span data-ttu-id="f837f-184">Esaminare le modifiche di rilievo in .NET Core 3.1 per le applicazioni Windows Form.Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span><span class="sxs-lookup"><span data-stu-id="f837f-184">Review the breaking changes in .NET Core 3.1 for Windows Forms apps.</span></span>](../compatibility/winforms.md#net-core-31)
