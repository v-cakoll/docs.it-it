### <a name="unexpected-invalidcastexception-from-invokemethod-activity-in-wf4"></a>InvalidCastException imprevista dall'attività InvokeMethod in WF4

|   |   |
|---|---|
|Dettagli|L'uso di un oggetto <xref:System.Activities.Statements.InvokeMethod> che ha come destinazione un metodo con un parametro nullable può generare un'eccezione <xref:System.InvalidCastException?displayProperty=name>.|
|Suggerimento|Questo comportamento è stato ripristinato in una versione di manutenzione di .NET Framework 4.5. Per risolvere questo problema, aggiornare .NET Framework 4.5 o eseguire l'aggiornamento a .NET Framework 4.5.1 o versioni successive.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Activities.Statements.InvokeMethod.Parameters?displayProperty=nameWithType></li></ul>|
|Analizzatori|<ul><li>CD0088</li></ul>|

