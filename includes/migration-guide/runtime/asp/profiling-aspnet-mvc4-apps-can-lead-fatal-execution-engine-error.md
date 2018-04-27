### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>La profilatura delle app ASP.Net MVC4 può causare un errore irreversibile del motore di esecuzione

|   |   |
|---|---|
|Dettagli|I profiler che usano gli assembly NGEN /Profile potrebbero causare arresti anomali delle applicazioni ASP.NET MVC4 profilate all'avvio con una 'eccezione irreversibile del motore di esecuzione'|
|Suggerimento|Questo problema è risolto in .NET Framework 4.5.2. In alternativa, il profiler può evitare questo problema specificando <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> nella maschera dell'evento.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|

