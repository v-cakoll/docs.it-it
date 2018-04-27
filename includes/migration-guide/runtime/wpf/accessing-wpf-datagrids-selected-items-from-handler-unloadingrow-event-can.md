### <a name="accessing-a-wpf-datagrids-selected-items-from-a-handler-of-the-datagrids-unloadingrow-event-can-cause-a-nullreferenceexception"></a>L'accesso agli elementi selezionati di un elemento DataGrid WPF da parte di un gestore dell'evento UnloadingRow di DataGrid può determinare un'eccezione NullReferenceException

|   |   |
|---|---|
|Dettagli|A causa di un bug in .NET Framework 4.5, i gestori eventi per gli eventi <xref:System.Windows.Controls.DataGrid> che includono la rimozione di una riga possono originare un'eccezione <xref:System.NullReferenceException?displayProperty=name> se accedono alle proprietà <xref:System.Windows.Controls.Primitives.Selector.SelectedItem?displayProperty=name> o <xref:System.Windows.Controls.Primitives.MultiSelector.SelectedItems?displayProperty=name> di <xref:System.Windows.Controls.DataGrid>.|
|Suggerimento|Questo problema è stato corretto in .NET Framework 4.6 e può essere risolto eseguendo l'aggiornamento a tale versione di .NET Framework.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.DataGrid.UnloadingRow?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.UnloadingRowDetails?displayProperty=nameWithType></li></ul>|

