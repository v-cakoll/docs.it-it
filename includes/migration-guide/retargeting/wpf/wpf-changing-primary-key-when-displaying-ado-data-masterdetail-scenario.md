---
ms.openlocfilehash: 2cd107dc92fd0fae89717c38840ce7ea44f3ac9a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774085"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a>WPF modifica una chiave primaria quando si visualizzano dati ADO in uno scenario master/dettagli

|   |   |
|---|---|
|Dettagli|Si supponga di avere una raccolta ADO di elementi di tipo <code>Order</code>, con una relazione denominata &quot;OrderDetails&quot; che la mette in relazione con una raccolta di elementi di tipo <code>Detail</code> tramite la chiave primaria &quot;OrderID&quot;. Nell'app WPF, è possibile associare un elenco ai dettagli per un ordine specifico:<pre><code class="lang-xml">&lt;ListBox ItemsSource=&quot;{Binding Path=OrderDetails}&quot; &gt;&#13;&#10;</code></pre>dove DataContext è un <code>Order</code>. WPF ottiene il valore della proprietà <code>OrderDetails</code>, una raccolta D di tutti gli elementi <code>Detail</code> il cui <code>OrderID</code> corrisponde a <code>OrderID</code> dell'elemento master. La modifica funzionale si verifica quando si modifica la chiave primaria <code>OrderID</code> dell'elemento master. ADO modifica automaticamente l'<code>OrderID</code> di ognuno dei record interessati nella raccolta dei dettagli, vale a dire quelli copiati nella raccolta D.  Cosa accade a D?<ul><li>Comportamento precedente:   la raccolta D viene cancellata.   L'elemento master <em>non</em> genera una notifica della modifica per la proprietà <code>OrderDetails</code>.  L'oggetto ListBox continua a usare la raccolta D, che ora è vuota.</li><li>Nuovo comportamento:  la raccolta D rimane invariata.   Ognuno dei relativi elementi genera una notifica della modifica della proprietà <code>OrderID</code>.  L'oggetto ListBox continua a usare la raccolta D e visualizza i dettagli con il nuovo <code>OrderID</code>.</li></ul>WPF implementa il nuovo comportamento creando la raccolta D in un modo diverso: chiamando il metodo ADO <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> con l'argomento <code>followParent</code> impostato su <code>true</code>.|
|Suggerimento|Per ottenere il nuovo comportamento, le app usano l'opzione AppContext.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;&#13;&#10;</code></pre>Per impostazione predefinita, l'opzione è impostata su <code>true</code> (comportamento precedente) per le app destinate a .NET 4.7.1 o versione precedente, e su <code>false</code> (nuovo comportamento) per le app destinate a .NET 4.7.2 o versione successiva.|
|Ambito|Secondario|
|Versione|4.7.2|
|Tipo|Ridestinazione|
