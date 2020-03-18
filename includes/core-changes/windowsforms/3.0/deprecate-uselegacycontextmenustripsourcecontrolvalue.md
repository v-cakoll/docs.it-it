---
ms.openlocfilehash: 5aca2b8b3ca6572194692888eae3c5614245b481
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75936985"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata

L'opzione `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` di compatibilità, introdotta in .NET Framework 4.7.2, non è supportata in Windows Form in .NET Core 3.0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.7.2, l'opzione `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` di compatibilità <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento della proprietà, che ora restituisce un riferimento al controllo del codice sorgente. Il comportamento precedente della proprietà `null`consisteva nel restituire . Per ulteriori informazioni, vedere [ \<Elemento> AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` l'opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'interruttore. L'opzione non è supportata e non sono disponibili funzionalità alternative.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
