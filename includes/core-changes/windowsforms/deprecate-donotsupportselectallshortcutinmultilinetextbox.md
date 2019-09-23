---
ms.openlocfilehash: a9d0fe3516ade04bc38b804268a9d989f6891d80
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181837"
---
### <a name="switchsystemwindowsformsdonotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. DoNotSupportSelectAllShortcutInMultilineTextBox non supportata

L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.6.1, selezionando il tasto <kbd>CTRL</kbd> + <kbd>un</kbd> tasto <xref:System.Windows.Forms.TextBox> di scelta rapida in un controllo è stato selezionato tutto il testo. In .NET Framework 4,6 e versioni precedenti, selezionando il tasto <kbd>CTRL</kbd> + <kbd>un</kbd> tasto di scelta rapida non è stato possibile selezionare tutto il <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> testo se [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e le proprietà sono entrambe impostate su. `true` L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale. Per altre informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

In .NET Core l' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuno

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
