### <a name="icommandcanexecutechanged-event-behaviour-changed-in-net-45"></a>Comportamento dell'evento ICommand.CanExecuteChanged modificato in .NET 4.5

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 un oggetto <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name> viene ignorato a meno che il mittente dell'evento non sia lo stesso oggetto che ha generato l'evento. Questo bug è stato risolto con gli aggiornamenti di manutenzione di .NET Framework 4.5.|
|Suggerimento|Questo bug è stato risolto nelle service release di .NET Framework 4.5, quindi può essere evitato assicurandosi che .NET Framework sia aggiornato oppure eseguendo l'aggiornamento a .NET Framework 4.5.1. In alternativa, è possibile modificare il codice dell'applicazione che usa <xref:System.Windows.Input.ICommand?displayProperty=name> per garantire che quando viene generato un comando <xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=name> il mittente corrisponda all'oggetto che genera l'evento.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Windows.Input.ICommand.CanExecuteChanged?displayProperty=nameWithType></li></ul>|
|Analizzatori|<ul><li>CD0084</li></ul>|

