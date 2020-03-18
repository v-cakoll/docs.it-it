---
ms.openlocfilehash: 9631e64bb403a3fe7b1b91e8ac592b57ce8068d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937101"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>L'opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non è supportata

L'opzione `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Form in .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.6.1, selezionando <xref:System.Windows.Forms.TextBox> il tasto di scelta rapida <kbd>Ctrl</kbd> + <kbd>A</kbd> in un controllo selezionato tutto il testo. In .NET Framework 4.6 e versioni precedenti, la selezione del tasto di scelta rapida <kbd>Ctrl</kbd> + <kbd>A</kbd> non è riuscita a selezionare tutto il testo se la casella [di testo.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> le proprietà sono state entrambe impostate `true`su . L'opzione `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` di compatibilità è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

In .NET Core `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` l'opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'interruttore. L'opzione non è supportata e non sono disponibili funzionalità alternative.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuno

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
