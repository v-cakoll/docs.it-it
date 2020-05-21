---
ms.openlocfilehash: bba74f26eafd52b966928835d5003d03af1eabdc
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721062"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a>Opzione di compatibilità DoNotSupportSelectAllShortcutInMultilineTextBox non supportata

L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.6.1, selezionando il tasto <kbd>CTRL</kbd>  +  <kbd>un</kbd> tasto di scelta rapida in un controllo è stato <xref:System.Windows.Forms.TextBox> selezionato tutto il testo. In .NET Framework 4,6 e versioni precedenti, selezionando il tasto <kbd>CTRL</kbd>  +  <kbd>un</kbd> tasto di scelta rapida non è stato possibile selezionare tutto il testo se [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e le <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> proprietà sono entrambe impostate su `true` . L' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione di compatibilità è stata introdotta in .NET Framework 4.6.1 per mantenere il comportamento originale. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.

In .NET Core l' `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- Nessuno

<!-- 

#### Affected APIs

- Not detectable via API analysis

-->
