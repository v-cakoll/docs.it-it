---
title: Modifiche di rilievo, .NET Framework a .NET Core 3,0-.NET Core
description: Elenca le modifiche di rilievo da .NET Framework a .NET Core 3,0 per Windows Forms e Windows Presentation Foundation.
ms.date: 09/10/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28da6a99e86d6c6f5cfc3b05c0a3a6419c310127
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182106"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a>Modifiche di rilievo per la migrazione da .NET Framework a .NET Core 3,0

> [!IMPORTANT]
> Questo articolo è in costruzione. Questo non è un elenco completo delle modifiche di rilievo di .NET Core. Per altre informazioni sulle modifiche di rilievo di .NET Core, è possibile esaminare i singoli [problemi di modifiche di rilievo](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) nel repository DotNet/docs su GitHub. 

Se si esegue la migrazione di un'applicazione Windows Forms o Windows Presentation Foundation da .NET Framework a .NET Core 3,0, consultare gli argomenti seguenti per le modifiche di rilievo che potrebbero incidere sull'app:

## <a name="windows-forms"></a>Windows Form

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
