---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643984"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. DoNotLoadLatestRichEditControl non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyImages`, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

Nel .NET Framework 4.6.2 e nelle versioni precedenti, il controllo <xref:System.Windows.Forms.RichTextBox> crea un'istanza del controllo di RichEdit Win32 v 3.0 e per le applicazioni destinate .NET Framework 4.7.1, il controllo di <xref:System.Windows.Forms.RichTextBox> crea un'istanza di RichEdit v 4.1 (in *Msftedit. dll*). Il `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione di compatibilità è stata introdotta per consentire alle applicazioni destinate .NET Framework 4.7.1 e versioni successive di rifiutare esplicitamente il nuovo controllo RichEdit v 4.1 e usare invece il vecchio controllo RichEdit V3.

In .NET Core, l'opzione `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` non è supportata. Sono supportate solo le nuove versioni del controllo <xref:System.Windows.Forms.RichTextBox>.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
