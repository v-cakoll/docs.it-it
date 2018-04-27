### <a name="flowdocument-may-show-an-extra-line-of-text"></a>FlowDocument può visualizzare una riga di testo aggiuntiva

|   |   |
|---|---|
|Dettagli|In alcuni casi, un elemento <xref:System.Windows.Documents.FlowDocument> visualizzerà una riga di testo aggiuntiva quando è in esecuzione in .NET Framework 4.5 rispetto a quanto viene visualizzato quando è in esecuzione in .NET Framework 4.0. Non esistono casi noti del fatto che la modifica causi la visualizzazione non chiara o non leggibile del testo, ma potrebbe determinare la visualizzazione di testo in precedenza omesso dalla visualizzazione di <xref:System.Windows.Documents.FlowDocument>.|
|Suggerimento|In alcuni casi, la riduzione della proprietà PageHeight dell'elemento visualizzato di una unità può ripristinare il numero di righe visualizzate in precedenza.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Documents.FlowDocument.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Documents.FlowDocument.%23ctor(System.Windows.Documents.Block)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentReader.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.FlowDocumentPageViewer.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.DocumentPageView.%23ctor?displayProperty=nameWithType></li></ul>|

