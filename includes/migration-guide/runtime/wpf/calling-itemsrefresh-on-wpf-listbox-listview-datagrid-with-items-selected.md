### <a name="calling-itemsrefresh-on-a-wpf-listbox-listview-or-datagrid-with-items-selected-can-cause-duplicate-items-to-appear-in-the-element"></a>La chiamata di Items.Refresh su un controllo WPF ListBox, ListView o DataGrid con elementi selezionati può determinare la visualizzazione di elementi duplicati nell'elemento

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5, la chiamata di ListBox.Items.Refresh dal codice mentre sono presenti elementi selezionati in un controllo <xref:System.Windows.Controls.ListBox?displayProperty=name> può causare la duplicazione degli elementi selezionati nell'elenco. Si verifica un problema analogo con <xref:System.Windows.Controls.ListView?displayProperty=name> e <xref:System.Windows.Controls.DataGrid?displayProperty=name>. Questo problema è risolto in .NET Framework 4.6.|
|Suggerimento|Questo problema può essere evitato deselezionando gli elementi a livello di codice prima della chiamata di <xref:System.Windows.Data.CollectionView.Refresh?displayProperty=name>, per poi selezionarli di nuovo dopo il completamento della chiamata. In alternativa, questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Data.CollectionView.Refresh?displayProperty=nameWithType></li></ul>|

