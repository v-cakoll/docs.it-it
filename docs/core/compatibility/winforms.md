---
title: Modifiche di rilievo Windows Forms-.NET Core
description: Elenca le modifiche di rilievo apportate Windows Forms per .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: cde76369bcb65a87fde1437c8bf8fd3b3c19a0c7
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937019"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="d541c-103">Modifiche di rilievo in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d541c-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="d541c-104">È stato aggiunto il supporto Windows Forms a .NET Core nella versione 3,0.</span><span class="sxs-lookup"><span data-stu-id="d541c-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="d541c-105">Questo articolo elenca le modifiche di rilievo per Windows Forms dalla versione di .NET Core in cui sono state introdotte.</span><span class="sxs-lookup"><span data-stu-id="d541c-105">This articles lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="d541c-106">Se si sta aggiornando un'app Windows Forms da .NET Framework o da una versione precedente di .NET Core (3,0 o versione successiva), questo articolo è applicabile all'utente.</span><span class="sxs-lookup"><span data-stu-id="d541c-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="d541c-107">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="d541c-107">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

## <a name="net-core-30"></a><span data-ttu-id="d541c-108">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d541c-108">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

## <a name="see-also"></a><span data-ttu-id="d541c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d541c-109">See also</span></span>

- [<span data-ttu-id="d541c-110">Trasferire un'app Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="d541c-110">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
