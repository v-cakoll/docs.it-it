### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a>DataGridCellsPanel.BringIndexIntoView genera ArgumentOutOfRangeException

|   |   |
|---|---|
|Dettagli|<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funziona in modo asincrono quando è abilitata la virtualizzazione delle colonne la cui larghezza tuttavia non è stata ancora determinata.  Se le colonne vengono rimosse prima dell'operazione asincrona, può verificarsi un evento <xref:System.ArgumentOutOfRangeException?displayProperty=name>.|
|Suggerimento|Una delle operazioni seguenti:<ol><li>Eseguire l'aggiornamento a .NET 4.7.</li><li>Installare la patch più recente per la manutenzione di .NET 4.6.2.</li><li>Evitare di rimuovere colonne fino al completamento della risposta asincrona a <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</li></ol>|
|Ambito|Microsoft Edge|
|Versione|4.6.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|

