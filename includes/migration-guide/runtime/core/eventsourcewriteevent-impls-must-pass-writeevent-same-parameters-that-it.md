### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>EventSource.WriteEvent impls deve passare a WriteEvent gli stessi parametri che ha ricevuto (oltre all'ID)

|   |   |
|---|---|
|Dettagli|Il runtime applica ora il contratto che specifica quanto segue: Una classe derivata da <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> che definisce un metodo di eventi ETW deve chiamare il metodo <code>EventSource.WriteEvent</code> della classe di base con l'ID evento seguito dagli stessi argomenti passati al metodo eventi ETW.|
|Suggerimento|Viene generata un'eccezione <xref:System.IndexOutOfRangeException?displayProperty=name> se un <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> legge i dati <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> in-process per un'origine evento che viola questo contratto.|
|Ambito|Secondario|
|Versione|4.5.1|
|Tipo|Runtime|

