---
ms.openlocfilehash: add3ff8faed2e7fab245e5b6f1b9158b7bdd06f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567358"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a>Evento CellFormatting non generato se è visualizzata la descrizione comando

Ora <xref:System.Windows.Forms.DataGridView> mostra il testo di una cella e le descrizioni comandi di errore quando si passa con il mouse e quando viene selezionato tramite la tastiera. Se viene visualizzata <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> una descrizione comando, l'evento non viene generato.

#### <a name="change-description"></a>Descrizione modifica:

Prima di .NET Core 3.1, un <xref:System.Windows.Forms.DataGridView> oggetto che aveva la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> proprietà impostata su `true` mostrava una descrizione comando per il testo di una cella e gli errori quando la cella veniva posizionata da un mouse. Le descrizioni comandi non venivano visualizzate quando una cella è stata selezionata tramite la tastiera (ad esempio, utilizzando il tasto TAB, i tasti di scelta rapida o la navigazione con le frecce). Se l'utente ha modificato una <xref:System.Windows.Forms.DataGridView> cella e quindi, mentre era ancora in modalità di modifica, si è posizionato su una cella per la cui <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> proprietà non era impostata, è stato generato un <xref:System.Windows.Forms.DataGridView.CellFormatting> evento per formattare il testo della cella da visualizzare nella cella.

Per soddisfare gli standard di accessibilità, a <xref:System.Windows.Forms.DataGridView> partire da <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> .NET `true` Core 3.1, un oggetto che ha la proprietà impostata su Mostra le descrizioni comandi per il testo e gli errori di una cella non solo quando la cella è al passaggio del mouse, ma anche quando viene selezionata tramite la tastiera. Come conseguenza di questa <xref:System.Windows.Forms.DataGridView.CellFormatting> modifica, l'evento *non* viene <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> generato quando le celle <xref:System.Windows.Forms.DataGridView> per i quali non è impostata la proprietà vengono visualizzate al passaggio del mouse mentre l'oggetto è in modalità di modifica. L'evento non viene generato perché il contenuto della cella al passaggio del mouse viene visualizzato come descrizione comando anziché essere visualizzato nella cella.

#### <a name="version-introduced"></a>Versione introdotta

3.1

#### <a name="recommended-action"></a>Azione consigliata

Eseguire il refactoring <xref:System.Windows.Forms.DataGridView.CellFormatting> di qualsiasi <xref:System.Windows.Forms.DataGridView> codice che dipende dall'evento mentre l'oggetto è in modalità di modifica.

#### <a name="category"></a>Category

Windows Form

#### <a name="affected-apis"></a>API interessate

Non rilevabile tramite l'analisi API.

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
