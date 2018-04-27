### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>Il valore predefinito MsmqSecureHashAlgorithm di WCF è ora SHA256

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.7.1 l'algoritmo di firma del messaggio predefinito in WCF per i messaggi Msmq è SHA256. In .NET Framework 4.7 e versioni precedenti l'algoritmo di firma del messaggio predefinito è SHA1.|
|Suggerimento|Se si riscontrano problemi di compatibilità con questa modifica in .NET Framework 4.7.1 o versione successiva, è possibile rifiutarla esplicitamente aggiungendo la riga seguente alla sezione <code>&lt;runtime&gt;</code> del file app.config:<pre><code class="language-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Ambito|Secondario|
|Versione|4.7.1|
|Tipo|Runtime|

