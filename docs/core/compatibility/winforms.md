---
title: Modifiche di rilievo di Windows Form
description: Vengono elencate le modifiche di rilievo in Windows Form per .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 25c568a8a0092a9c4874419c64c7dcebea4dce9e
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888126"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="7c3d6-103">Modifiche di rilievo in Windows FormBreaking changes in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7c3d6-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="7c3d6-104">Il supporto di Windows Form è stato aggiunto a .NET Core nella versione 3.0.Windows Forms support was added to .NET Core in version 3.0.</span><span class="sxs-lookup"><span data-stu-id="7c3d6-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="7c3d6-105">In questo articolo vengono elencate le modifiche di rilievo per Windows Form dalla versione di .NET Core in cui sono state introdotte.</span><span class="sxs-lookup"><span data-stu-id="7c3d6-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="7c3d6-106">Se si sta aggiornando un'app Windows Form da .NET Framework o da una versione precedente di .NET Core (3.0 o versione successiva), questo articolo è applicabile all'utente.</span><span class="sxs-lookup"><span data-stu-id="7c3d6-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="7c3d6-107">In questa pagina sono documentate le seguenti modifiche di rilievo:</span><span class="sxs-lookup"><span data-stu-id="7c3d6-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="7c3d6-108">Modifica</span><span class="sxs-lookup"><span data-stu-id="7c3d6-108">Breaking change</span></span> | <span data-ttu-id="7c3d6-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="7c3d6-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="7c3d6-110">API WinForms ora generano ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="7c3d6-110">WinForms APIs now throw ArgumentNullException</span></span>](#winforms-apis-now-throw-argumentnullexception) | <span data-ttu-id="7c3d6-111">5.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-111">5.0</span></span> |
| [<span data-ttu-id="7c3d6-112">Controlli rimossi</span><span class="sxs-lookup"><span data-stu-id="7c3d6-112">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="7c3d6-113">3.1</span><span class="sxs-lookup"><span data-stu-id="7c3d6-113">3.1</span></span> |
| [<span data-ttu-id="7c3d6-114">Evento CellFormatting non generato se è visualizzata la descrizione comando</span><span class="sxs-lookup"><span data-stu-id="7c3d6-114">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="7c3d6-115">3.1</span><span class="sxs-lookup"><span data-stu-id="7c3d6-115">3.1</span></span> |
| [<span data-ttu-id="7c3d6-116">Control.DefaultFont modificato in Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="7c3d6-116">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="7c3d6-117">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-117">3.0</span></span> |
| [<span data-ttu-id="7c3d6-118">Modernizzazione di FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="7c3d6-118">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="7c3d6-119">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-119">3.0</span></span> |
| [<span data-ttu-id="7c3d6-120">SerializableAttribute rimosso da alcuni tipi di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7c3d6-120">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="7c3d6-121">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-121">3.0</span></span> |
| [<span data-ttu-id="7c3d6-122">Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata</span><span class="sxs-lookup"><span data-stu-id="7c3d6-122">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-123">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-123">3.0</span></span> |
| [<span data-ttu-id="7c3d6-124">Opzione di compatibilità DomainUpDown.UseLegacyScrolling non supportata</span><span class="sxs-lookup"><span data-stu-id="7c3d6-124">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-125">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-125">3.0</span></span> |
| [<span data-ttu-id="7c3d6-126">Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata</span><span class="sxs-lookup"><span data-stu-id="7c3d6-126">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-127">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-127">3.0</span></span> |
| [<span data-ttu-id="7c3d6-128">L'opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non è supportata</span><span class="sxs-lookup"><span data-stu-id="7c3d6-128">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-129">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-129">3.0</span></span> |
| [<span data-ttu-id="7c3d6-130">Non è supportata l'opzione di compatibilità DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="7c3d6-130">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-131">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-131">3.0</span></span> |
| [<span data-ttu-id="7c3d6-132">EnableVisualStyleValidation opzione di compatibilità non supportata</span><span class="sxs-lookup"><span data-stu-id="7c3d6-132">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-133">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-133">3.0</span></span> |
| [<span data-ttu-id="7c3d6-134">Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata</span><span class="sxs-lookup"><span data-stu-id="7c3d6-134">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-135">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-135">3.0</span></span> |
| [<span data-ttu-id="7c3d6-136">Opzione di compatibilità UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="7c3d6-136">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="7c3d6-137">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-137">3.0</span></span> |
| [<span data-ttu-id="7c3d6-138">Modifica dell'accesso per AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="7c3d6-138">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="7c3d6-139">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-139">3.0</span></span> |
| [<span data-ttu-id="7c3d6-140">API duplicate rimosse da Windows Form</span><span class="sxs-lookup"><span data-stu-id="7c3d6-140">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="7c3d6-141">3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-141">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="7c3d6-142">.NET 5.0 (informazioni in base alle persone)</span><span class="sxs-lookup"><span data-stu-id="7c3d6-142">.NET 5.0</span></span>

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="7c3d6-143">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7c3d6-143">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="7c3d6-144">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7c3d6-144">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7c3d6-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c3d6-145">See also</span></span>

- [<span data-ttu-id="7c3d6-146">Convertire un'app Windows Form in .NET Core</span><span class="sxs-lookup"><span data-stu-id="7c3d6-146">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
