### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>Solo i protocolli Tls 1.0, 1.1 e 1.2 sono supportati in System.Net.ServicePointManager e System.Net.Security.SslStream

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6, le classi <xref:System.Net.ServicePointManager> e <xref:System.Net.Security.SslStream> possono usare solo uno dei tre protocolli seguenti: Tls1.0, Tls1.1 o Tls1.2. Il protocollo SSL 3.0 e la crittografia RC4 non sono supportati.|
|Suggerimento|La mitigazione consigliata consiste nell'aggiornare l'app sul lato server a Tls1.0, Tls1.1 o Tls1.2. Se ciò non è fattibile o se le app client non funzionano, è possibile usare la classe <xref:System.AppContext?displayProperty=name> per rifiutare esplicitamente questa funzionalità in uno dei due modi seguenti:<ol><li>Impostando a livello di codice le opzioni di compatibilità su <xref:System.AppContext?displayProperty=name>, come spiegato [qui](http://blogs.msdn.com/b/dotnet/archive/2015/04/29/net-announcements-at-build-2015.aspx#dotnet46).</li><li>Aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config: <code>&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSchUseStrongCrypto=true&quot;/&gt;</code>;</li></ol>|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType></li></ul>|

