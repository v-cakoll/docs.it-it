---
ms.openlocfilehash: 55c13aa70a03bcc548ce1d096cca8f40de6cda84
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720892"
---
### <a name="dontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a>Opzione di compatibilità DontSupportReentrantFilterMessage non supportata

L' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione di compatibilità, introdotta in .NET Framework 4.6.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.6.1, l' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione di compatibilità risolve le possibili <xref:System.IndexOutOfRangeException> eccezioni quando il <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> messaggio viene chiamato con un' <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementazione personalizzata. Per altre informazioni, vedere [Mitigazione: Implementazioni IMessageFilter.PreFilterMessage personalizzate](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).

In .NET Core l' `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
