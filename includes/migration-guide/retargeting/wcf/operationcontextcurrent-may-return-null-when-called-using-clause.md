---
ms.openlocfilehash: e08b78b49cab88d4435d75b04bd446b413a61340
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859321"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a>OperationContext.Current può restituire Null in caso di chiamata in una clausola using

|   |   |
|---|---|
|Dettagli|<xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> può restituire <code>null</code> e può essere generata un'eccezione <xref:System.NullReferenceException> se vengono soddisfatte tutte le condizioni seguenti:<ul><li>Si recupera il valore della proprietà <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> in un metodo che restituisce <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</li><li>Si crea un'istanza dell'oggetto <xref:System.ServiceModel.OperationContextScope> in una clausola <code>using</code>.</li><li>Si recupera il valore della proprietà <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> all'interno di <code>using statement</code>. Ad esempio:</li></ul><pre><code class="lang-csharp">using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext context = OperationContext.Current;      // OperationContext.Current is null.&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre>|
|Suggerimento|Per risolvere questo problema, è possibile eseguire le operazioni seguenti:<ul><li>Modificare il codice come segue per<code>null</code> <xref:System.ServiceModel.OperationContext.Current%2A> creare un'istanza di un nuovo oggetto non:Modify your code as follows to instantiate a new non- object:</li></ul><pre><code class="lang-csharp">OperationContext ocx = OperationContext.Current;&#13;&#10;using (new OperationContextScope(OperationContext.Current))&#13;&#10;{&#13;&#10;OperationContext.Current = new OperationContext(ocx.Channel);&#13;&#10;// ...&#13;&#10;}&#13;&#10;</code></pre><ul><li>Installare l'aggiornamento più recente di .NET Framework 4.6.2 oppure eseguire l'aggiornamento a una versione successiva di .NET Framework. Viene così disabilitato il flusso di <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> e ripristinato il comportamento delle applicazioni WCF in .NET Framework 4.6.1 e versioni precedenti. Questo comportamento è configurabile ed è equivalente all'aggiunta dell'impostazione dell'app seguente nel file di configurazione:</li></ul><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>Se questa modifica non è opportuna e l'applicazione dipende dal flusso del contesto di esecuzione tra i contesti operativi, è possibile abilitare il flusso come indicato di seguito:<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.ServiceModel.DisableOperationContextAsyncFlow&quot; value=&quot;false&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Scope|Microsoft Edge|
|Versione|4.6.2|
|Type|Ridestinazione|
|API interessate|<ul><li><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType></li></ul>|
