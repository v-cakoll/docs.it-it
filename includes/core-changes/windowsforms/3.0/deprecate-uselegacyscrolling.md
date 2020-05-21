---
ms.openlocfilehash: dd850e83540ffed4dc95b00f807f49b0dd3725e9
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83720998"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Opzione di compatibilità DomainUpDown. UseLegacyScrolling non supportata

L' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.7.1, l' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione di compatibilità consente agli sviluppatori di rifiutare esplicitamente <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> le <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> azioni e indipendenti. Il Commuter ha ripristinato il comportamento legacy, in cui <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> viene ignorato se il testo del contesto è presente e lo sviluppatore deve usare <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> Action sul controllo prima dell' <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> azione. Per ulteriori informazioni, vedere [ \< AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core l' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
