---
ms.openlocfilehash: 923105114c9e8da02c61c842cc02bed1ead3eddc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236466"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a>Evento TabControl SelectionChanged e proprietà SelectedContent

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1, un elemento <xref:System.Windows.Controls.TabControl> aggiorna il valore della proprietà <xref:System.Windows.Controls.TabControl.SelectedContent> prima di generare l'evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> quando la selezione viene modificata. In .NET Framework 4.7 e versioni precedenti l'aggiornamento a SelectedContent avviene dopo l'evento.|
|Suggerimento|Le app destinate a .NET Framework 4.7.1 o versioni successive possono rifiutare esplicitamente questa modifica e usare il comportamento legacy aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Le app destinate a .NET Framework 4.7 o versioni precedenti ma in esecuzione su .NET Framework 4.7.1 o versioni successive possono abilitare il nuovo comportamento aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
