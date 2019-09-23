---
ms.openlocfilehash: 459e7e1f0b5543f069682dadf60668e94b472377
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181788"
---
### <a name="switchsystemwindowsformsdomainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Switch. System. Windows. Forms. DomainUpDown. UseLegacyScrolling opzione di compatibilità non supportata

L' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.7.1, l' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione di compatibilità consente agli sviluppatori di rifiutare esplicitamente <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> le <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> azioni e indipendenti. Il Commuter ha ripristinato il comportamento legacy <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> , in cui viene ignorato se il testo del contesto è presente e lo sviluppatore <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> deve usare Action sul controllo prima <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> dell'azione. Per ulteriori informazioni, vedere [ \<AppContextSwitchOverrides > Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core l' `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
