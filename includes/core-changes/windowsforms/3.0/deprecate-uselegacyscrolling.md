---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937012"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Opzione di compatibilità DomainUpDown.UseLegacyScrolling non supportata

L'opzione `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` di compatibilità, introdotta in .NET Framework 4.7.1, non è supportata in Windows Form in .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.7.1, l'opzione `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` di <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> compatibilità ha consentito agli sviluppatori di rifiutare esplicitamente l'indipendenza e le azioni. L'opzione ha ripristinato il <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> comportamento legacy, in cui viene ignorato <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> se è presente <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> il testo del contesto e lo sviluppatore deve usare l'azione sul controllo prima dell'azione. Per ulteriori informazioni, vedere [ \<Elemento> AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` l'opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'interruttore. L'opzione non è supportata e non sono disponibili funzionalità alternative.

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
