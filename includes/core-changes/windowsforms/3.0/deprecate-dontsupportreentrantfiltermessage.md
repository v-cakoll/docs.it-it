---
ms.openlocfilehash: 3272dc562981269b868df4ca9d3a5806918aba5f
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937099"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Opzione di compatibilità DontSupportReentrantFilterMessage non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione delle modifiche

A partire da .NET Framework 4.6.1, l'opzione di compatibilità `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` risolve possibili <xref:System.IndexOutOfRangeException> eccezioni quando viene chiamato il messaggio <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> con un'implementazione di <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizzata. Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

In .NET Core, l'opzione `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Categoria

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
