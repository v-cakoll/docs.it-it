---
ms.openlocfilehash: 459e7e1f0b5543f069682dadf60668e94b472377
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643970"
---
### <a name="switchsystemwindowsformsdomainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Switch. System. Windows. Forms. DomainUpDown. UseLegacyScrolling opzione di compatibilità non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling`, introdotta in .NET Framework 4.7.1, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.7.1, l'opzione di compatibilità `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` consente agli sviluppatori di rifiutare esplicitamente le azioni di <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> e <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> indipendenti. Il cambio ha ripristinato il comportamento legacy, in cui il <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> viene ignorato se è presente il testo del contesto e lo sviluppatore deve usare <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> azione sul controllo prima dell'azione di <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. Per ulteriori informazioni, vedere [\<elemento > AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core, l'opzione `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` non è supportata.

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
