---
ms.openlocfilehash: 9631e64bb403a3fe7b1b91e8ac592b57ce8068d9
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937101"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione delle modifiche

A partire da .NET Framework 4.6.1, selezionando <kbd>Ctrl</kbd> + <kbd>un</kbd> tasto di scelta rapida in un controllo <xref:System.Windows.Forms.TextBox> selezionato tutto il testo. In .NET Framework 4,6 e versioni precedenti, la selezione di <kbd>Ctrl</kbd> + <kbd>un</kbd> tasto di scelta rapida non è riuscita a selezionare tutto il testo se le proprietà [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> sono entrambe impostate su `true`. L'opzione di compatibilità `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale. Per altre informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

In .NET Core, l'opzione `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Categoria

Windows Form

#### <a name="affected-apis"></a>API interessate

- nessuna

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
