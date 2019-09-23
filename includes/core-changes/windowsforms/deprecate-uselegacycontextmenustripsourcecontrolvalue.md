---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181827"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Opzione di compatibilità switch. System. Windows. Forms. UseLegacyContextMenuStripSourceControlValue non supportata

L' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità, introdotta in .NET Framework 4.7.2, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione della modifica

A partire da .NET Framework 4.7.2, l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> della proprietà, che ora restituisce un riferimento al controllo del codice sorgente. Il comportamento precedente della proprietà era restituire `null`. Per ulteriori informazioni, vedere [ \<AppContextSwitchOverrides > Element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione non è supportata.

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
