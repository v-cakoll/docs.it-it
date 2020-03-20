---
ms.openlocfilehash: 923105114c9e8da02c61c842cc02bed1ead3eddc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859061"
---
### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a>Evento TabControl SelectionChanged e proprietà SelectedContent

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1, un elemento <xref:System.Windows.Controls.TabControl> aggiorna il valore della proprietà <xref:System.Windows.Controls.TabControl.SelectedContent> prima di generare l'evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> quando la selezione viene modificata. In .NET Framework 4.7 e versioni precedenti l'aggiornamento a SelectedContent avviene dopo l'evento.|
|Suggerimento|Le app destinate a .NET Framework 4.7.1 o versioni successive possono rifiutare esplicitamente questa modifica e usare il comportamento legacy aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Le app destinate a .NET Framework 4.7 o versioni precedenti ma in esecuzione su .NET Framework 4.7.1 o versioni successive possono abilitare il nuovo comportamento aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file di configurazione dell'applicazione:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Scope|Minorenne|
|Versione|4.7.1|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
