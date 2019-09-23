---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181797"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. DontSupportReentrantFilterMessage non supportata

L' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.6.1, l' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione di compatibilità risolve <xref:System.IndexOutOfRangeException> le possibili eccezioni <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> quando il messaggio viene chiamato con <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> un'implementazione personalizzata. Per altre informazioni, vedere [Mitigazione: Implementazioni personalizzate di IMessageFilter.](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md)PreFilterMessage.

In .NET Core l' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione non è supportata.

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
