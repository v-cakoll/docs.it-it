---
ms.openlocfilehash: add3ff8faed2e7fab245e5b6f1b9158b7bdd06f5
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567358"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a>Evento CellFormatting non generato se viene visualizzata la descrizione comando

Un <xref:System.Windows.Forms.DataGridView> Mostra ora le descrizioni comandi di testo e di errore di una cella quando il mouse viene spostato e quando viene selezionato tramite la tastiera. Se viene visualizzata una descrizione comando, l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> non viene generato.

#### <a name="change-description"></a>Descrizione della modifica

Prima di .NET Core 3,1, un <xref:System.Windows.Forms.DataGridView> la cui proprietà <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> era impostata su `true` mostrava una descrizione comando per il testo di una cella ed errori quando la cella veniva spostata da un mouse. Le descrizioni comandi non sono state visualizzate quando è stata selezionata una cella tramite la tastiera, ad esempio usando il tasto TAB, i tasti di scelta rapida o la navigazione con la freccia. Se l'utente ha modificato una cella e, mentre il <xref:System.Windows.Forms.DataGridView> era ancora in modalità di modifica, il puntatore del mouse su una cella che non disponeva della <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> proprietà è stato impostato, è stato generato un evento <xref:System.Windows.Forms.DataGridView.CellFormatting> per formattare il testo della cella per la visualizzazione nella cella.

Per soddisfare gli standard di accessibilità, a partire da .NET Core 3,1, un <xref:System.Windows.Forms.DataGridView> la cui proprietà <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> è impostata su `true` Visualizza descrizioni comandi per il testo di una cella ed errori non solo quando la cella viene posizionata al passaggio del mouse, ma anche quando viene selezionata tramite la tastiera. In seguito a questa modifica, l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting> *non* viene generato quando si passa il mouse sulle celle che non dispongono del set di proprietà <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> mentre il <xref:System.Windows.Forms.DataGridView> è in modalità di modifica. L'evento non viene generato perché il contenuto della cella al passaggio del mouse viene visualizzato come descrizione comando anziché essere visualizzato nella cella.

#### <a name="version-introduced"></a>Versione introdotta

3,1

#### <a name="recommended-action"></a>Azione consigliata

Effettuare il refactoring di qualsiasi codice che dipende dall'evento <xref:System.Windows.Forms.DataGridView.CellFormatting> mentre il <xref:System.Windows.Forms.DataGridView> è in modalità di modifica.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

Non rilevabile tramite l'analisi dell'API.

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
