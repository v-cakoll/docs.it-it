---
ms.openlocfilehash: e6c93a1bc31c041f36fca3704bca32012a2b42ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858970"
---
### <a name="selector-selectionchanged-event-and-selectedvalue-property"></a>Evento SelectionChanged e proprietà SelectedValue di Selector

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1, un <xref:System.Windows.Controls.Primitives.Selector> aggiorna sempre il valore della relativa proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> prima di generare l'evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> quando la selezione cambia. In questo modo la proprietà SelectedValue è coerente con le altre proprietà di selezione (<xref:System.Windows.Controls.Primitives.Selector.SelectedItem%2A> e <xref:System.Windows.Controls.Primitives.Selector.SelectedIndex%2A>), che vengono aggiornate prima della generazione dell'evento.<p/>In .NET Framework 4.7 e versioni precedenti, l'aggiornamento di SelectedValue avveniva prima dell'evento nella maggior parte dei casi, ma si verificava dopo l'evento se la modifica della selezione era causata dalla modifica della proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>.|
|Suggerimento|Le app destinate a .NET Framework 4.7.1 o versioni successive possono rifiutare esplicitamente questa modifica e usare il comportamento legacy aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Le app destinate a .NET Framework 4.7 o versioni precedenti ma in esecuzione su .NET Framework 4.7.1 o versioni successive possono abilitare il nuovo comportamento aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7.1|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
