### <a name="change-in-behavior-for-taskwaitall-methods-with-time-out-arguments"></a>Modifica del comportamento per i metodi Task.WaitAll con argomenti di timeout

|   |   |
|---|---|
|Dettagli|In .NET 4.5 il comportamento di Task.WaitAll è stato reso più coerente. In .NET Framework 4 questi metodi hanno un comportamento non coerente. Alla scadenza del timeout, se una o più attività sono state completate o annullate prima della chiamata al metodo, il metodo genera un'eccezione <xref:System.AggregateException?displayProperty=name>. Alla scadenza del timeout, se nessuna attività è stata completata o annullata prima della chiamata al metodo, ma una o più attività sono entrate in questi stati dopo la chiamata al metodo, il metodo restituisce false.<br/><br/>In .NET Framework 4.5 questi overload del metodo ora restituiscono false in presenza di attività ancora in esecuzione allo scadere dell'intervallo di timeout e generano un'eccezione <xref:System.AggregateException?displayProperty=name> solo se un'attività di input è stata annullata, indipendentemente dal fatto che sia stata annullata prima o dopo la chiamata del metodo, e non ci sono altre attività ancora in esecuzione.|
|Suggerimento|Se veniva rilevata un'eccezione <xref:System.AggregateException?displayProperty=name> come mezzo per rilevare un'attività annullata prima della chiamata al metodo WaitAll, il codice deve invece eseguire lo stesso rilevamento tramite la proprietà IsCanceled (ad esempio: .Any(t =&gt; t.IsCanceled)) in quanto .NET 4.6 genererà un'eccezione in questo caso solo se tutte le attività attese vengono completate prima del timeout.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.Int32,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Threading.Tasks.Task.WaitAll(System.Threading.Tasks.Task[],System.TimeSpan)?displayProperty=nameWithType></li></ul>|

