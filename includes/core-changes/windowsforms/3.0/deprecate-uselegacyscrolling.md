---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937012"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Opzione di compatibilità DomainUpDown. UseLegacyScrolling non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling`, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione delle modifiche

A partire da .NET Framework 4.7.1, l'opzione di compatibilità `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` consente agli sviluppatori di rifiutare esplicitamente le azioni di <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> indipendenti. Il cambio ha ripristinato il comportamento legacy, in cui il <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> viene ignorato se è presente il testo del contesto e lo sviluppatore deve usare <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> azione sul controllo prima dell'azione di <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. Per ulteriori informazioni, vedere [\<elemento > AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core, l'opzione `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Categoria

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
