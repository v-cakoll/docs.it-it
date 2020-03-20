---
ms.openlocfilehash: e2d63d85adce64db6e00b62ec17f55ae71ce3052
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803277"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>La chiamata di DataGrid.CommitEdit da un gestore CellEditEnding fa perdere lo stato attivo

|   |   |
|---|---|
|Dettagli|La chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit> da uno dei gestori eventi <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> di <xref:System.Windows.Controls.DataGrid?displayProperty=name> causa la perdita dello stato attivo per <xref:System.Windows.Controls.DataGrid?displayProperty=name>.|
|Suggerimento|Questo bug è stato risolto in .NET Framework 4.5.2, pertanto può essere evitato eseguendo l'aggiornamento di .NET Framework. In alternativa, è possibile evitarlo selezionando di nuovo in modo esplicito <xref:System.Windows.Controls.DataGrid?displayProperty=name> dopo la chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.|
|Scope|Microsoft Edge|
|Versione|4.5|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
