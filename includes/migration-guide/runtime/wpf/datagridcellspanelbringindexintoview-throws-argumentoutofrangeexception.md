---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622363"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView genera ArgumentOutOfRangeException

#### <a name="details"></a>Dettagli

<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funziona in modo asincrono quando è abilitata la virtualizzazione delle colonne la cui larghezza tuttavia non è stata ancora determinata.  Se le colonne vengono rimosse prima dell'operazione asincrona, può verificarsi un evento <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.

#### <a name="suggestion"></a>Suggerimento

Una delle operazioni seguenti:<ol><li>Effettuare l'aggiornamento a .NET Framework 4.7.</li><li>Installare la patch più recente per la manutenzione di .NET Framework 4.6.2.</li><li>Evitare di rimuovere colonne fino al completamento della risposta asincrona a <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Microsoft Edge|
|Version|4.6.2|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
