---
ms.openlocfilehash: 5aca2b8b3ca6572194692888eae3c5614245b481
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936985"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, introdotta in .NET Framework 4.7.2, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione delle modifiche

A partire da .NET Framework 4.7.2, l'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento della proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, che ora restituisce un riferimento al controllo del codice sorgente. Il comportamento precedente della proprietà consisteva nel restituire `null`. Per ulteriori informazioni, vedere [\<elemento > AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core, l'opzione `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Categoria

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
