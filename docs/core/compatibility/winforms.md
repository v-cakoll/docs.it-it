---
title: Windows Forms modifiche di rilievo
description: Elenca le modifiche di rilievo apportate Windows Forms per .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: bd87e438ecf9930bfcd5377f9a3799d5f3693f49
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702468"
---
# <a name="breaking-changes-in-windows-forms"></a>Modifiche di rilievo in Windows Forms

È stato aggiunto il supporto Windows Forms a .NET Core nella versione 3,0. Questo articolo elenca le modifiche di rilievo per Windows Forms dalla versione di .NET Core in cui sono state introdotte. Se si sta aggiornando un'app Windows Forms da .NET Framework o da una versione precedente di .NET Core (3,0 o versione successiva), questo articolo è applicabile all'utente.

In questa pagina sono documentate le modifiche di rilievo seguenti:

| Modifica | Versione introdotta |
| - | :-: |
| [Rimossi controlli barra di stato](#removed-status-bar-controls) | 5.0 |
| [I metodi WinForms ora generano ArgumentException](#winforms-methods-now-throw-argumentexception) | 5.0 |
| [I metodi WinForms ora generano ArgumentNullException](#winforms-methods-now-throw-argumentnullexception) | 5.0 |
| [Le proprietà di WinForms ora generano ArgumentOutOfRangeException](#winforms-properties-now-throw-argumentoutofrangeexception) | 5.0 |
| [Controlli rimossi](#removed-controls) | 3.1 |
| [Evento CellFormatting non generato se viene visualizzata la descrizione comando](#cellformatting-event-not-raised-if-tooltip-is-shown) | 3.1 |
| [Control. DefaultFont modificato in Segoe UI 9 PT](#default-control-font-changed-to-segoe-ui-9-pt) | 3.0 |
| [Modernizzazione di FolderBrowserDialog](#modernization-of-the-folderbrowserdialog) | 3.0 |
| [SerializableAttribute rimosso da alcuni tipi di Windows Forms](#serializableattribute-removed-from-some-windows-forms-types) | 3.0 |
| [Opzione di compatibilità AllowUpdateChildControlIndexForTabControls non supportata](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported) | 3.0 |
| [Opzione di compatibilità DomainUpDown. UseLegacyScrolling non supportata](#domainupdownuselegacyscrolling-compatibility-switch-not-supported) | 3.0 |
| [Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata](#donotloadlatestricheditcontrol-compatibility-switch-not-supported) | 3.0 |
| [Opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non supportata](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported) | 3.0 |
| [Opzione di compatibilità DontSupportReentrantFilterMessage non supportata](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported) | 3.0 |
| [Opzione di compatibilità EnableVisualStyleValidation non supportata](#enablevisualstylevalidation-compatibility-switch-not-supported) | 3.0 |
| [Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported) | 3.0 |
| [Opzione di compatibilità UseLegacyImages non supportata](#uselegacyimages-compatibility-switch-not-supported) | 3.0 |
| [Modifica dell'accesso per AccessibleObject. RuntimeIDFirstItem](#change-of-access-for-accessibleobjectruntimeidfirstitem) | 3.0 |
| [API duplicate rimosse da Windows Forms](#duplicated-apis-removed-from-windows-forms) | 3.0 |

## <a name="net-50"></a>.NET 5,0

[!INCLUDE [winforms-deprecated-controls](../../../includes/core-changes/windowsforms/5.0/winforms-deprecated-controls.md)]

***

[!INCLUDE [invalid-args-cause-argumentexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentexception.md)]

***

[!INCLUDE [null-args-cause-argumentnullexception](../../../includes/core-changes/windowsforms/5.0/null-args-cause-argumentnullexception.md)]

***

[!INCLUDE [invalid-args-cause-argumentoutofrangeexception](../../../includes/core-changes/windowsforms/5.0/invalid-args-cause-argumentoutofrangeexception.md)]

***

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

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

## <a name="see-also"></a>Vedere anche

- [Trasferire un'app Windows Forms a .NET Core](../porting/winforms.md)
