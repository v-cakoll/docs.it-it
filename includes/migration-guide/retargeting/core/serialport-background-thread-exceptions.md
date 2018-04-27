### <a name="serialport-background-thread-exceptions"></a>Eccezioni di thread in background SerialPort

|   |   |
|---|---|
|Dettagli|I thread in background creati con flussi <xref:System.IO.Ports.SerialPort> non terminano più il processo quando vengono generate eccezioni del sistema operativo. Nelle applicazioni destinate a .NET Framework 4.7 e versioni precedenti, un processo viene terminato quando viene generata un'eccezione del sistema operativo per un thread in background creato con un flusso <xref:System.IO.Ports.SerialPort>. Nelle applicazioni destinate a .NET Framework 4.7.1 o versioni successive, i thread in background rimangono in attesa di eventi del sistema operativo correlati alla porta seriale attiva e potrebbe verificarsi un arresto anomalo in alcuni casi, ad esempio in seguito alla rimozione improvvisa della porta seriale.|
|Suggerimento|Per le app destinate a .NET Framework 4.7.1, è possibile rifiutare esplicitamente la gestione delle eccezioni, nel caso non sia opportuna, aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Per le app destinate alle versioni precedenti di .NET Framework, ma eseguite in .NET Framework 4.7.1 o versioni successive è possibile acconsentire esplicitamente alla gestione delle eccezioni aggiungendo il codice seguente alla sezione <code>&lt;runtime&gt;</code> del file <code>app.config</code>:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|

