---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181729"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. DoNotLoadLatestRichEditControl non supportata

L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

Nel .NET Framework 4.6.2 e nelle versioni precedenti, il <xref:System.Windows.Forms.RichTextBox> controllo creerà un'istanza del controllo RichEdit Win32 v 3.0 e per le applicazioni destinate .NET Framework 4.7.1 <xref:System.Windows.Forms.RichTextBox> , il controllo creerà un'istanza di RichEdit v 4.1 (in  *Msftedit. dll*). L' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione di compatibilità è stata introdotta per consentire alle applicazioni destinate .NET Framework 4.7.1 e versioni successive di rifiutare esplicitamente il nuovo controllo RichEdit v 4.1 e usare invece il vecchio controllo RichEdit V3.

In .NET Core l' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione non è supportata. Sono supportate solo le <xref:System.Windows.Forms.RichTextBox> nuove versioni del controllo.

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
