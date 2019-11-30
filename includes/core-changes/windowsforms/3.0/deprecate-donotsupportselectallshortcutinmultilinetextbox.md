---
ms.openlocfilehash: a9d0fe3516ade04bc38b804268a9d989f6891d80
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643991"
---
### <a name="switchsystemwindowsformsdonotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. DoNotSupportSelectAllShortcutInMultilineTextBox non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.6.1, selezionando <kbd>Ctrl</kbd> + <kbd>un</kbd> tasto di scelta rapida in un controllo <xref:System.Windows.Forms.TextBox> selezionato tutto il testo. In .NET Framework 4,6 e versioni precedenti, la selezione di <kbd>Ctrl</kbd> + <kbd>un</kbd> tasto di scelta rapida non è riuscita a selezionare tutto il testo se le proprietà [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> sono entrambe impostate su `true`. L'opzione di compatibilità `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

In .NET Core, l'opzione `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuna

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
