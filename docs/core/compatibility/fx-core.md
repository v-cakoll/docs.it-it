---
title: Modifiche di rilievo-.NET Framework a .NET Core
titleSuffix: ''
description: Elenca le modifiche di rilievo da .NET Framework a .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: f712be14d7debc4b3008f8459e6ee925754b25f0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449400"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="c10f1-103">Modifiche di rilievo per la migrazione da .NET Framework a .NET Core</span><span class="sxs-lookup"><span data-stu-id="c10f1-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="c10f1-104">Se si esegue la migrazione di un'app da .NET Framework a .NET Core, le modifiche di rilievo elencate in questo articolo potrebbero interessare l'utente.</span><span class="sxs-lookup"><span data-stu-id="c10f1-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="c10f1-105">Le modifiche di rilievo sono raggruppate per categoria e all'interno di tali categorie dalla versione di .NET Core in cui sono state introdotte.</span><span class="sxs-lookup"><span data-stu-id="c10f1-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core in which they were introduced.</span></span>

> [!NOTE]
> <span data-ttu-id="c10f1-106">Questo articolo non è un elenco completo delle modifiche di rilievo tra .NET Framework e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c10f1-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="c10f1-107">Di seguito sono riportate le modifiche di rilievo più importanti che verranno acquisite.</span><span class="sxs-lookup"><span data-stu-id="c10f1-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="c10f1-108">CoreFx</span><span class="sxs-lookup"><span data-stu-id="c10f1-108">CoreFx</span></span>

- [<span data-ttu-id="c10f1-109">Modificare il valore predefinito di UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="c10f1-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)
- [<span data-ttu-id="c10f1-110">UnauthorizedAccessException generata da FileSystemInfo. Attributes</span><span class="sxs-lookup"><span data-stu-id="c10f1-110">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)

### <a name="net-core-21"></a><span data-ttu-id="c10f1-111">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c10f1-111">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a><span data-ttu-id="c10f1-112">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c10f1-112">.NET Core 1.0</span></span>

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

## <a name="cryptography"></a><span data-ttu-id="c10f1-113">Crittografia</span><span class="sxs-lookup"><span data-stu-id="c10f1-113">Cryptography</span></span>

- [<span data-ttu-id="c10f1-114">Il parametro booleano di SignedCms. ComputeSignature è rispettato</span><span class="sxs-lookup"><span data-stu-id="c10f1-114">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a><span data-ttu-id="c10f1-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c10f1-115">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="c10f1-116">Windows Form</span><span class="sxs-lookup"><span data-stu-id="c10f1-116">Windows Forms</span></span>

<span data-ttu-id="c10f1-117">È stato aggiunto il supporto Windows Forms a .NET Core nella versione 3,0.</span><span class="sxs-lookup"><span data-stu-id="c10f1-117">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="c10f1-118">Se si esegue la migrazione di un'app Windows Forms da .NET Framework a .NET Core, le modifiche di rilievo elencate qui potrebbero influire sull'app.</span><span class="sxs-lookup"><span data-stu-id="c10f1-118">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="c10f1-119">Controlli rimossi</span><span class="sxs-lookup"><span data-stu-id="c10f1-119">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="c10f1-120">Evento CellFormatting non generato se viene visualizzata la descrizione comando</span><span class="sxs-lookup"><span data-stu-id="c10f1-120">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="c10f1-121">Control. DefaultFont modificato in Segoe UI 9 PT</span><span class="sxs-lookup"><span data-stu-id="c10f1-121">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="c10f1-122">Modernizzazione di FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="c10f1-122">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="c10f1-123">SerializableAttribute rimosso da alcuni tipi di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c10f1-123">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="c10f1-124">Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-124">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-125">Opzione di compatibilità DomainUpDown. UseLegacyScrolling non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-125">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-126">Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-126">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-127">Opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-127">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-128">Opzione di compatibilità DontSupportReentrantFilterMessage non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-128">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-129">Opzione di compatibilità EnableVisualStyleValidation non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-129">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-130">Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-130">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-131">Opzione di compatibilità UseLegacyImages non supportata</span><span class="sxs-lookup"><span data-stu-id="c10f1-131">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="c10f1-132">Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="c10f1-132">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="c10f1-133">API duplicate rimosse da Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c10f1-133">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a><span data-ttu-id="c10f1-134">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="c10f1-134">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="c10f1-135">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c10f1-135">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="c10f1-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c10f1-136">See also</span></span>

- [<span data-ttu-id="c10f1-137">API che generano sempre eccezioni in .NET Core</span><span class="sxs-lookup"><span data-stu-id="c10f1-137">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="c10f1-138">.NET Framework tecnologie non disponibili in .NET Core</span><span class="sxs-lookup"><span data-stu-id="c10f1-138">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
