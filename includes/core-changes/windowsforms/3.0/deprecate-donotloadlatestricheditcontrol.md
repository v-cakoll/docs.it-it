---
ms.openlocfilehash: cb8c0532bb2bcfbcd619cd382f3d236b431c3480
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721040"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata

L' `Switch.System.Windows.Forms.UseLegacyImages` opzione di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

Nel .NET Framework 4.6.2 e nelle versioni precedenti, il <xref:System.Windows.Forms.RichTextBox> controllo creerà un'istanza del controllo RichEdit Win32 v 3.0 e per le applicazioni destinate .NET Framework 4.7.1, il <xref:System.Windows.Forms.RichTextBox> controllo creerà un'istanza di RichEdit v 4.1 (in *Msftedit. dll*). L' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione di compatibilità è stata introdotta per consentire alle applicazioni destinate .NET Framework 4.7.1 e versioni successive di rifiutare esplicitamente il nuovo controllo RichEdit v 4.1 e usare invece il vecchio controllo RichEdit V3.

In .NET Core l' `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` opzione non è supportata. Sono supportate solo le nuove versioni del <xref:System.Windows.Forms.RichTextBox> controllo.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

#### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
