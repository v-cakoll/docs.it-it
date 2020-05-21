---
ms.openlocfilehash: 3dfacadb5127319d4ce27f367803637cfb1ed00f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721027"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>API duplicate rimosse da Windows Forms

Una serie di API duplicate accidentalmente nello <xref:System.Windows.Forms?displayProperty=fullName> spazio dei nomi a partire da .net core 3,0 Preview 4 sono state rimosse in .net core 3,0 RC1.

#### <a name="change-description"></a>Descrizione modifica:

.NET Core 3,0 Preview 4 ha inavvertitamente duplicato un numero di tipi nello <xref:System.Windows.Forms?displayProperty=fullName> spazio dei nomi già esistente nello <xref:System.ComponentModel.Design?displayProperty=fullName> spazio dei nomi. A partire da .NET Core 3,0 RC1, questi tipi duplicati non sono più disponibili. Nella tabella seguente vengono elencati il tipo originale e il tipo duplicato:

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

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

- Nessuno.

<!--

#### Affected APIs

- Not detectable via API analysis.

-->
