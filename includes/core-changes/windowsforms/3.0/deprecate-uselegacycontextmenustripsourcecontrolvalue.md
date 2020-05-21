---
ms.openlocfilehash: 3ada05a13ec7acde1d8374ed733d0d51cdfb408c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721653"
---
### <a name="uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Opzione di compatibilità UseLegacyContextMenuStripSourceControlValue non supportata

L' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità, introdotta in .NET Framework 4.7.2, non è supportata in Windows Forms in .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

A partire da .NET Framework 4.7.2, l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione di compatibilità consente allo sviluppatore di rifiutare esplicitamente il nuovo comportamento della <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType> proprietà, che ora restituisce un riferimento al controllo del codice sorgente. Il comportamento precedente della proprietà era restituire `null` . Per ulteriori informazioni, vedere [ \< AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

In .NET Core l' `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` opzione non è supportata.

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Rimuovere l'opzione. L'opzione non è supportata e non è disponibile alcuna funzionalità alternativa.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
