---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937091"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>API duplicate rimosse da Windows Form

Un numero di API accidentalmente duplicate <xref:System.Windows.Forms?displayProperty=fullName> nello spazio dei nomi a partire da .NET Core 3.0 Preview 4 sono state rimosse in .NET Core 3.0 RC1.

#### <a name="change-description"></a>Descrizione modifica:

.NET Core 3.0 Preview 4 ha inavvertitamente <xref:System.Windows.Forms?displayProperty=fullName> duplicato un numero <xref:System.ComponentModel.Design?displayProperty=fullName> di tipi nello spazio dei nomi già esistenti nello spazio dei nomi. A partire da .NET Core 3.0 RC1, questi tipi duplicati non sono più disponibili. Nella tabella seguente sono elencati il tipo originale e il tipo duplicato:

> [!div class="mx-tdCol2BreakAll"]
> |Tipo originale|Tipo duplicato|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a>Versione introdotta

3.0 RC1

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice in modo che faccia riferimento al tipo originale, come illustrato nella colonna **Tipo originale** della tabella.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

- Non rilevabile tramite l'analisi API.

<!--

### Affected APIs

- Not detectable via API analysis.

-->
