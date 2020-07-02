---
ms.openlocfilehash: c3c3ed44cf53625c246dfe0408bb861750ecf336
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622025"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>La chiamata di DataGrid.CommitEdit da un gestore CellEditEnding fa perdere lo stato attivo

#### <a name="details"></a>Dettagli

La chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit> da uno dei gestori eventi <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> di <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> causa la perdita dello stato attivo per <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

Questo bug è stato risolto in .NET Framework 4.5.2, pertanto può essere evitato eseguendo l'aggiornamento di .NET Framework. In alternativa, è possibile evitarlo selezionando di nuovo in modo esplicito <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> dopo la chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
