### <a name="glyphruncomputeinkboundingbox-and-formattedtextextent-return-different-values-beginning-in-net-45"></a>GlyphRun.ComputeInkBoundingBox() e FormattedText.Extent restituiscono valori diversi a partire da .NET 4.5

|   |   |
|---|---|
|Dettagli|Sono stati apportati miglioramenti a <xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox> e <xref:System.Windows.Media.FormattedText.Extent> in .NET Framework 4.5 per risolvere i problemi a causa dei quali i rettangoli di selezione sono troppo piccoli per i glifi contenuti in alcuni casi in .NET Framework 4.0. Ne consegue che alcuni rettangoli di selezione sono più grandi a partire da .NET Framework 4.5 e quindi si noteranno alcune piccole differenze nel layout dell'interfaccia utente.|
|Suggerimento|Tenere presente che le dimensioni di alcuni rettangoli di selezione con glifi sono aumentate. Queste modifiche consentiranno in genere di migliorare la presentazione e l'hit testing per i rettangoli, ma se si preferisce il comportamento precedente alla versione .NET 4.5, è possibile sceglierlo in modo esplicito aggiungendo la voce seguente al file app.config:<pre><code class="language-xml">&lt;appsettings&gt;&#13;&#10;&lt;add key=&quot;IncludeAllInkInBoundingBox&quot; value=&quot;false&quot;&gt;&#13;&#10;&lt;/appsettings&gt;&#13;&#10;</code></pre>|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Media.GlyphRun.ComputeInkBoundingBox?displayProperty=nameWithType></li><li><xref:System.Windows.Media.FormattedText.Extent?displayProperty=nameWithType></li></ul>|

