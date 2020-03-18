---
title: Modifiche di rilievo di Windows Form
description: Vengono elencate le modifiche di rilievo in Windows Form per .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 7fba78382d011bc9d489924fa185a44e598c5a76
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399098"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="f53d6-103">Modifiche di rilievo in Windows FormBreaking changes in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f53d6-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="f53d6-104">Il supporto di Windows Form è stato aggiunto a .NET Core nella versione 3.0.Windows Forms support was added to .NET Core in version 3.0.</span><span class="sxs-lookup"><span data-stu-id="f53d6-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="f53d6-105">In questo articolo vengono elencate le modifiche di rilievo per Windows Form dalla versione di .NET Core in cui sono state introdotte.</span><span class="sxs-lookup"><span data-stu-id="f53d6-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="f53d6-106">Se si sta aggiornando un'app Windows Form da .NET Framework o da una versione precedente di .NET Core (3.0 o versione successiva), questo articolo è applicabile all'utente.</span><span class="sxs-lookup"><span data-stu-id="f53d6-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="f53d6-107">In questa pagina sono documentate le seguenti modifiche di rilievo:</span><span class="sxs-lookup"><span data-stu-id="f53d6-107">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="f53d6-108">Controlli rimossi</span><span class="sxs-lookup"><span data-stu-id="f53d6-108">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="f53d6-109">Evento CellFormatting non generato se è visualizzata la descrizione comando</span><span class="sxs-lookup"><span data-stu-id="f53d6-109">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="f53d6-110">Control.DefaultFont modificato in Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="f53d6-110">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="f53d6-111">Modernizzazione di FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="f53d6-111">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="f53d6-112">SerializableAttribute rimosso da alcuni tipi di Windows Form</span><span class="sxs-lookup"><span data-stu-id="f53d6-112">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="f53d6-113">Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata</span><span class="sxs-lookup"><span data-stu-id="f53d6-113">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-114">Opzione di compatibilità DomainUpDown.UseLegacyScrolling non supportata</span><span class="sxs-lookup"><span data-stu-id="f53d6-114">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-115">Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata</span><span class="sxs-lookup"><span data-stu-id="f53d6-115">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-116">L'opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non è supportata</span><span class="sxs-lookup"><span data-stu-id="f53d6-116">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-117">Non è supportata l'opzione di compatibilità DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="f53d6-117">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-118">EnableVisualStyleValidation opzione di compatibilità non supportata</span><span class="sxs-lookup"><span data-stu-id="f53d6-118">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-119">Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata</span><span class="sxs-lookup"><span data-stu-id="f53d6-119">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-120">Opzione di compatibilità UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="f53d6-120">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="f53d6-121">Modifica dell'accesso per AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="f53d6-121">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="f53d6-122">API duplicate rimosse da Windows Form</span><span class="sxs-lookup"><span data-stu-id="f53d6-122">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

## <a name="net-core-31"></a><span data-ttu-id="f53d6-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="f53d6-123">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="f53d6-124">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f53d6-124">.NET Core 3.0</span></span>

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

***

## <a name="see-also"></a><span data-ttu-id="f53d6-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f53d6-125">See also</span></span>

- [<span data-ttu-id="f53d6-126">Convertire un'app Windows Form in .NET Core</span><span class="sxs-lookup"><span data-stu-id="f53d6-126">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
