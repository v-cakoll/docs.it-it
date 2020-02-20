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
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>Modifiche di rilievo per la migrazione da .NET Framework a .NET Core

Se si esegue la migrazione di un'app da .NET Framework a .NET Core, le modifiche di rilievo elencate in questo articolo potrebbero interessare l'utente. Le modifiche di rilievo sono raggruppate per categoria e all'interno di tali categorie dalla versione di .NET Core in cui sono state introdotte.

> [!NOTE]
> Questo articolo non è un elenco completo delle modifiche di rilievo tra .NET Framework e .NET Core. Di seguito sono riportate le modifiche di rilievo più importanti che verranno acquisite.

## <a name="corefx"></a>CoreFx

- [Modificare il valore predefinito di UseShellExecute](#change-in-default-value-of-useshellexecute)
- [UnauthorizedAccessException generata da FileSystemInfo. Attributes](#unauthorizedaccessexception-thrown-by-filesysteminfoattributes)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

### <a name="net-core-10"></a>.NET Core 1.0

[!INCLUDE [UnauthorizedAccessException thrown by FileSystemInfo.Attributes](~/includes/core-changes/corefx/1.0/filesysteminfo-attributes-exceptions.md)]

***

## <a name="cryptography"></a>Crittografia

- [Il parametro booleano di SignedCms. ComputeSignature è rispettato](#boolean-parameter-of-signedcmscomputesignature-is-respected)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

## <a name="windows-forms"></a>Windows Form

È stato aggiunto il supporto Windows Forms a .NET Core nella versione 3,0. Se si esegue la migrazione di un'app Windows Forms da .NET Framework a .NET Core, le modifiche di rilievo elencate qui potrebbero influire sull'app.

- [Controlli rimossi](#removed-controls)
- [Evento CellFormatting non generato se viene visualizzata la descrizione comando](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [Control. DefaultFont modificato in Segoe UI 9 PT](#default-control-font-changed-to-segoe-ui-9-pt)
- [Modernizzazione di FolderBrowserDialog](#modernization-of-the-folderbrowserdialog)
- [SerializableAttribute rimosso da alcuni tipi di Windows Forms](#serializableattribute-removed-from-some-windows-forms-types)
- [Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [Opzione di compatibilità DomainUpDown. UseLegacyScrolling non supportata](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [Opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non supportata](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [Opzione di compatibilità DontSupportReentrantFilterMessage non supportata](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [Opzione di compatibilità EnableVisualStyleValidation non supportata](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [Opzione di compatibilità UseLegacyImages non supportata](#uselegacyimages-compatibility-switch-not-supported)
- [Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [API duplicate rimosse da Windows Forms](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a>.NET Core 3,1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="see-also"></a>Vedere anche

- [API che generano sempre eccezioni in .NET Core](unsupported-apis.md)
- [.NET Framework tecnologie non disponibili in .NET Core](../porting/net-framework-tech-unavailable.md)
