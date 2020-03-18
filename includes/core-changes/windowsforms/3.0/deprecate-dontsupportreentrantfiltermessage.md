---
ms.openlocfilehash: 3272dc562981269b868df4ca9d3a5806918aba5f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937099"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Non è supportata l'opzione di compatibilità DontSupportReentrantFilterMessage

L'opzione `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Form in .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.6.1, l'opzione `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` di compatibilità risolve le possibili <xref:System.IndexOutOfRangeException> eccezioni quando il <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> messaggio viene chiamato con un'implementazione personalizzata. <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

In .NET Core `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` l'opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'interruttore. L'opzione non è supportata e non sono disponibili funzionalità alternative.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
