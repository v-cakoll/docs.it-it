---
ms.openlocfilehash: 4a34a64eba72ea24c1d830566565ce4fbee8e5b7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721212"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a>Evento CellFormatting non generato se viene visualizzata la descrizione comando

Un oggetto <xref:System.Windows.Forms.DataGridView> Mostra ora le descrizioni comandi di testo e di errore di una cella quando il mouse viene spostato e quando viene selezionato tramite la tastiera. Se viene visualizzata una descrizione comando, l' <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> evento non viene generato.

#### <a name="change-description"></a>Descrizione modifica:

Prima di .NET Core 3,1, un oggetto <xref:System.Windows.Forms.DataGridView> con la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> proprietà impostata su `true` mostrava una descrizione comando per il testo di una cella ed errori quando la cella veniva posizionata con il mouse. Le descrizioni comandi non sono state visualizzate quando è stata selezionata una cella tramite la tastiera, ad esempio usando il tasto TAB, i tasti di scelta rapida o la navigazione con la freccia. Se l'utente ha modificato una cella e quindi, mentre <xref:System.Windows.Forms.DataGridView> era ancora in modalità di modifica, il puntatore del mouse su una cella che non disponeva della <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> proprietà è <xref:System.Windows.Forms.DataGridView.CellFormatting> stata impostata, è stato generato un evento per formattare il testo della cella per la visualizzazione nella cella.

Per soddisfare gli standard di accessibilità, a partire da .NET Core 3,1, un oggetto <xref:System.Windows.Forms.DataGridView> la cui <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> proprietà è impostata su `true` Mostra descrizioni comandi per il testo di una cella ed errori non solo quando la cella viene posizionata, ma anche quando viene selezionata tramite la tastiera. In seguito a questa modifica, l' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento *non* viene generato quando le celle per le quali non è impostato il <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> set di proprietà vengono posizionate mentre <xref:System.Windows.Forms.DataGridView> è in modalità di modifica. L'evento non viene generato perché il contenuto della cella al passaggio del mouse viene visualizzato come descrizione comando anziché essere visualizzato nella cella.

#### <a name="version-introduced"></a>Versione introdotta

3.1

#### <a name="recommended-action"></a>Azione consigliata

Effettuare il refactoring di qualsiasi codice che dipende dall' <xref:System.Windows.Forms.DataGridView.CellFormatting> evento mentre <xref:System.Windows.Forms.DataGridView> è in modalità di modifica.

#### <a name="category"></a>Category

Windows Forms

#### <a name="affected-apis"></a>API interessate

Nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
