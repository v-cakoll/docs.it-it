### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a>La chiamata di DataGrid.CommitEdit da un gestore CellEditEnding fa perdere lo stato attivo

|   |   |
|---|---|
|Dettagli|La chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit> da uno dei gestori eventi <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> di <xref:System.Windows.Controls.DataGrid?displayProperty=name> causa la perdita dello stato attivo per <xref:System.Windows.Controls.DataGrid?displayProperty=name>.|
|Suggerimento|Questo bug è stato risolto in .NET Framework 4.5.2, pertanto può essere evitato eseguendo l'aggiornamento di .NET Framework. In alternativa, è possibile evitarlo selezionando di nuovo in modo esplicito <xref:System.Windows.Controls.DataGrid?displayProperty=name> dopo la chiamata di <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|

