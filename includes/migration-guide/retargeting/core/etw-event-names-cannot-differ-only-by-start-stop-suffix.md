### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>I nomi di eventi ETW non possono essere diversi solo per il suffisso "Start" o "Stop"

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6 e 4.6.1 il runtime genera una <xref:System.ArgumentException> quando due nomi di eventi ETW (Event Tracing for Windows) sono diversi solo per il suffisso &quot;Start&quot; o &quot;Stop&quot;, ad esempio quando un evento è denominato <code>LogUser</code> e un altro <code>LogUserStart</code>. In questo caso, il runtime non può creare l'origine dell'evento, quindi non viene generata alcuna registrazione.|
|Suggerimento|Per evitare l'eccezione, assicurarsi che non siano presenti nomi di evento che differiscono solo per il suffisso &quot;Start&quot; oppure &quot;Stop&quot;. Questo requisito è stato rimosso a rimosso a partire da .NET Framework 4.6.2 e il runtime può risolvere l'ambiguità di nomi di evento che differiscono solo per il suffisso &quot;Start&quot; e &quot;Stop&quot;.|
|Ambito|Microsoft Edge|
|Versione|4.6|
|Tipo|Ridestinazione|

