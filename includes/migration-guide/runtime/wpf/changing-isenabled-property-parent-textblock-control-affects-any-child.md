### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>La modifica della proprietà IsEnabled dell'elemento padre di un controllo TextBlock influisce sui controlli figlio

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6.2, la modifica della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> dell'elemento padre di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=name> influisce sui controlli figlio, ad esempio collegamenti ipertestuali e pulsanti, del controllo <xref:System.Windows.Controls.TextBlock?displayProperty=name>. In .NET Framework 4.6.1 e versioni precedenti i controlli all'interno di <xref:System.Windows.Controls.TextBlock?displayProperty=name> non sempre riflettono lo stato della proprietà <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> dell'elemento padre <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Suggerimento|Nessuno. Questa modifica è conforme al comportamento previsto per i controlli all'interno di un controllo <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Ambito|Secondario|
|Versione|4.6.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|

