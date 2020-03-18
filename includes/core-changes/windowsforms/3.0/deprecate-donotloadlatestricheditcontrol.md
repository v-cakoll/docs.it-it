---
ms.openlocfilehash: 3f0e8fb4d0d727b40cff5de7cfdc7529bf32dac4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937002"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Opzione di compatibilità DoNotLoadLatestRichEditControl non supportata

L'opzione `Switch.System.Windows.Forms.UseLegacyImages` di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Form in .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

In .NET Framework 4.6.2 e <xref:System.Windows.Forms.RichTextBox> versioni precedenti, il controllo crea un'istanza del controllo Win32 RichEdit v3.0 <xref:System.Windows.Forms.RichTextBox> e per le applicazioni destinate a .NET Framework 4.7.1, il controllo crea un'istanza di RichEdit v4.1 (in *msftedit.dll*). L'opzione `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` di compatibilità è stata introdotta per consentire alle applicazioni destinate a .NET Framework 4.7.1 e versioni successive di rifiutare esplicitamente il nuovo controllo RichEdit v4.1 e di utilizzare invece il controllo RichEdit v3 precedente.

In .NET Core `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` l'opzione non è supportata. Sono supportate <xref:System.Windows.Forms.RichTextBox> solo le nuove versioni del controllo.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'interruttore. L'opzione non è supportata e non sono disponibili funzionalità alternative.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
