### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a>ServiceBase non propaga le eccezioni OnStart

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.7 e versioni precedenti, le eccezioni generate all'avvio del servizio non vengono propagate al chiamante di <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>. A partire dalle applicazioni destinate a .NET Framework 4.7.1, il runtime propaga le eccezioni a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> per i servizi che non vengono avviati.|
|Suggerimento|All'avvio del servizio, se si verifica un'eccezione, tale eccezione verrà propagata. Questo dovrebbe aiutare a diagnosticare i casi di errore di avvio dei servizi. Se questo comportamento è indesiderato, è possibile rifiutarlo esplicitamente aggiungendo l'elemento <AppContextSwitchOverrides> seguente alla sezione <runtime> del file di configurazione dell'applicazione:<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true&quot; /&gt;&#13;&#10;</code></pre>Se l'applicazione è destinata a una versione precedente alla 4.7.1 ma si vuole avere a disposizione questo comportamento, aggiungere l'elemento <AppContextSwitchOverrides> seguente alla sezione <runtime> del file di configurazione dell'applicazione:<pre><code class="language-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false&quot; /&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.1|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType></li><li><xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType></li></ul>|

