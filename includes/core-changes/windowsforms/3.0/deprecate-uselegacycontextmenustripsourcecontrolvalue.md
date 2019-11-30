---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644019"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. UseLegacyContextMenuStripSourceControlValue non supportata

L'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, introdotta in .NET Framework 4.7.2, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.7.2, l'opzione di compatibilità `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento della proprietà <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, che ora restituisce un riferimento al controllo del codice sorgente. Il comportamento precedente della proprietà consisteva nel restituire `null`. Per ulteriori informazioni, vedere [\<elemento > AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core, l'opzione `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
