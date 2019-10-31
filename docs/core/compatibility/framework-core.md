---
title: Modifiche di rilievo, .NET Framework a .NET Core 3,0-.NET Core
description: Elenca le modifiche di rilievo da .NET Framework a .NET Core 3,0 per Windows Forms e Windows Presentation Foundation.
ms.date: 09/10/2019
ms.openlocfilehash: a374e35192c7aad07e986e0e0b75039642744edc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089566"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="d12f6-103">Modifiche di rilievo per la migrazione da .NET Framework a .NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="d12f6-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d12f6-104">Questo articolo è in costruzione.</span><span class="sxs-lookup"><span data-stu-id="d12f6-104">This article is under construction.</span></span> <span data-ttu-id="d12f6-105">Questo non è un elenco completo delle modifiche di rilievo di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d12f6-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="d12f6-106">Per altre informazioni sulle modifiche di rilievo di .NET Core, è possibile esaminare i singoli [problemi di modifiche di rilievo](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) nel repository DotNet/docs su GitHub.</span><span class="sxs-lookup"><span data-stu-id="d12f6-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="d12f6-107">Se si esegue la migrazione di un'applicazione Windows Forms o Windows Presentation Foundation da .NET Framework a .NET Core 3,0, consultare gli argomenti seguenti per le modifiche di rilievo che potrebbero incidere sull'app:</span><span class="sxs-lookup"><span data-stu-id="d12f6-107">If you are migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="d12f6-108">Windows Form</span><span class="sxs-lookup"><span data-stu-id="d12f6-108">Windows Forms</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
