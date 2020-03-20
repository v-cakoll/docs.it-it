---
ms.openlocfilehash: 1a1fc91ea2bb81e0f94b64323085ccf99072a1f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802547"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView genera ArgumentOutOfRangeException

|   |   |
|---|---|
|Dettagli|<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funziona in modo asincrono quando è abilitata la virtualizzazione delle colonne la cui larghezza tuttavia non è stata ancora determinata.  Se le colonne vengono rimosse prima dell'operazione asincrona, può verificarsi un evento <xref:System.ArgumentOutOfRangeException?displayProperty=name>.|
|Suggerimento|Una delle operazioni seguenti:<ol><li>Effettuare l'aggiornamento a .NET Framework 4.7.</li><li>Installare la patch più recente per la manutenzione di .NET Framework 4.6.2.</li><li>Evitare di rimuovere colonne fino al completamento della risposta asincrona a <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>|
|Scope|Microsoft Edge|
|Versione|4.6.2|
|Type|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
