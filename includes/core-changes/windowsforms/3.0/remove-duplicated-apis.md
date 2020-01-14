---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937091"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>API duplicate rimosse da Windows Forms

Una serie di API duplicate accidentalmente nello spazio dei nomi <xref:System.Windows.Forms?displayProperty=fullName> a partire da .NET Core 3,0 Preview 4 sono state rimosse in .NET Core 3,0 RC1.

#### <a name="change-description"></a>Descrizione delle modifiche

.NET Core 3,0 Preview 4 ha inavvertitamente duplicato un numero di tipi nello spazio dei nomi <xref:System.Windows.Forms?displayProperty=fullName> già esistente nello spazio dei nomi <xref:System.ComponentModel.Design?displayProperty=fullName>. A partire da .NET Core 3,0 RC1, questi tipi duplicati non sono più disponibili. Nella tabella seguente vengono elencati il tipo originale e il tipo duplicato:

> [!div class="mx-tdCol2BreakAll"]
> |Tipo originale|Tipo duplicato|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a>Versione introdotta

3,0 RC1

#### <a name="recommended-action"></a>Azione consigliata

Aggiornare il codice in modo che faccia riferimento al tipo originale, come illustrato nella colonna di **tipo originale** della tabella.

#### <a name="category"></a>Categoria

Windows Form

#### <a name="affected-apis"></a>API interessate

- Non rilevabile tramite l'analisi dell'API.

<!--

### Affected APIs

- Not detectable via API analysis.

-->
