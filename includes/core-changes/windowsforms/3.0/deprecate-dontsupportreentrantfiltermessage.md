---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644005"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. DontSupportReentrantFilterMessage non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.6.1, l'opzione di compatibilità `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` risolve possibili <xref:System.IndexOutOfRangeException> eccezioni quando viene chiamato il messaggio <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> con un'implementazione di <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> personalizzata. Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

In .NET Core, l'opzione `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
