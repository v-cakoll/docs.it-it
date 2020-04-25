---
title: Windows Forms modifiche di rilievo
description: Elenca le modifiche di rilievo apportate Windows Forms per .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 75d369c7fb999da81a50fe46716e125c3840eb7a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158437"
---
# <a name="breaking-changes-in-windows-forms"></a><span data-ttu-id="1481e-103">Modifiche di rilievo in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1481e-103">Breaking changes in Windows Forms</span></span>

<span data-ttu-id="1481e-104">È stato aggiunto il supporto Windows Forms a .NET Core nella versione 3,0.</span><span class="sxs-lookup"><span data-stu-id="1481e-104">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="1481e-105">Questo articolo elenca le modifiche di rilievo per Windows Forms dalla versione di .NET Core in cui sono state introdotte.</span><span class="sxs-lookup"><span data-stu-id="1481e-105">This article lists breaking changes for Windows Forms by the .NET Core version in which they were introduced.</span></span> <span data-ttu-id="1481e-106">Se si sta aggiornando un'app Windows Forms da .NET Framework o da una versione precedente di .NET Core (3,0 o versione successiva), questo articolo è applicabile all'utente.</span><span class="sxs-lookup"><span data-stu-id="1481e-106">If you're upgrading a Windows Forms app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article is applicable to you.</span></span>

<span data-ttu-id="1481e-107">In questa pagina sono documentate le modifiche di rilievo seguenti:</span><span class="sxs-lookup"><span data-stu-id="1481e-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="1481e-108">Modifica</span><span class="sxs-lookup"><span data-stu-id="1481e-108">Breaking change</span></span> | <span data-ttu-id="1481e-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="1481e-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="1481e-110">Rimossi controlli barra di stato</span><span class="sxs-lookup"><span data-stu-id="1481e-110">Removed status bar controls</span></span>](#removed-status-bar-controls) | <span data-ttu-id="1481e-111">5.0</span><span class="sxs-lookup"><span data-stu-id="1481e-111">5.0</span></span> |
| [<span data-ttu-id="1481e-112">I metodi WinForms ora generano ArgumentException</span><span class="sxs-lookup"><span data-stu-id="1481e-112">WinForms methods now throw ArgumentException</span></span>](#winforms-methods-now-throw-argumentexception) | <span data-ttu-id="1481e-113">5.0</span><span class="sxs-lookup"><span data-stu-id="1481e-113">5.0</span></span> |
| [<span data-ttu-id="1481e-114">I metodi WinForms ora generano ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="1481e-114">WinForms methods now throw ArgumentNullException</span></span>](#winforms-methods-now-throw-argumentnullexception) | <span data-ttu-id="1481e-115">5.0</span><span class="sxs-lookup"><span data-stu-id="1481e-115">5.0</span></span> |
| [<span data-ttu-id="1481e-116">Controlli rimossi</span><span class="sxs-lookup"><span data-stu-id="1481e-116">Removed controls</span></span>](#removed-controls) | <span data-ttu-id="1481e-117">3.1</span><span class="sxs-lookup"><span data-stu-id="1481e-117">3.1</span></span> |
| [<span data-ttu-id="1481e-118">Evento CellFormatting non generato se viene visualizzata la descrizione comando</span><span class="sxs-lookup"><span data-stu-id="1481e-118">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown) | <span data-ttu-id="1481e-119">3.1</span><span class="sxs-lookup"><span data-stu-id="1481e-119">3.1</span></span> |
| [<span data-ttu-id="1481e-120">Control. DefaultFont modificato in Segoe UI 9 PT</span><span class="sxs-lookup"><span data-stu-id="1481e-120">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt) | <span data-ttu-id="1481e-121">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-121">3.0</span></span> |
| [<span data-ttu-id="1481e-122">Modernizzazione di FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="1481e-122">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog) | <span data-ttu-id="1481e-123">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-123">3.0</span></span> |
| [<span data-ttu-id="1481e-124">SerializableAttribute rimosso da alcuni tipi di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1481e-124">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types) | <span data-ttu-id="1481e-125">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-125">3.0</span></span> |
| [<span data-ttu-id="1481e-126">Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-126">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | <span data-ttu-id="1481e-127">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-127">3.0</span></span> |
| [<span data-ttu-id="1481e-128">Opzione di compatibilità DomainUpDown. UseLegacyScrolling non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-128">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | <span data-ttu-id="1481e-129">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-129">3.0</span></span> |
| [<span data-ttu-id="1481e-130">Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-130">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | <span data-ttu-id="1481e-131">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-131">3.0</span></span> |
| [<span data-ttu-id="1481e-132">Opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-132">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | <span data-ttu-id="1481e-133">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-133">3.0</span></span> |
| [<span data-ttu-id="1481e-134">Opzione di compatibilità DontSupportReentrantFilterMessage non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-134">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | <span data-ttu-id="1481e-135">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-135">3.0</span></span> |
| [<span data-ttu-id="1481e-136">Opzione di compatibilità EnableVisualStyleValidation non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-136">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported) | <span data-ttu-id="1481e-137">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-137">3.0</span></span> |
| [<span data-ttu-id="1481e-138">Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-138">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | <span data-ttu-id="1481e-139">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-139">3.0</span></span> |
| [<span data-ttu-id="1481e-140">Opzione di compatibilità UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="1481e-140">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported) | <span data-ttu-id="1481e-141">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-141">3.0</span></span> |
| [<span data-ttu-id="1481e-142">Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="1481e-142">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem) | <span data-ttu-id="1481e-143">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-143">3.0</span></span> |
| [<span data-ttu-id="1481e-144">API duplicate rimosse da Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1481e-144">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms) | <span data-ttu-id="1481e-145">3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-145">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="1481e-146">.NET 5,0</span><span class="sxs-lookup"><span data-stu-id="1481e-146">.NET 5.0</span></span>

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

## <a name="net-core-31"></a><span data-ttu-id="1481e-147">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="1481e-147">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="1481e-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1481e-148">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1481e-149">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="1481e-149">See also</span></span>

- [<span data-ttu-id="1481e-150">Trasferire un'app Windows Forms a .NET Core</span><span class="sxs-lookup"><span data-stu-id="1481e-150">Port a Windows Forms app to .NET Core</span></span>](../porting/winforms.md)
