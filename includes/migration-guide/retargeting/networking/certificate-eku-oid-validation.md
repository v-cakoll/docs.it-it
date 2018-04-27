### <a name="certificate-eku-oid-validation"></a>Convalida dell'OID EKU del certificato

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.6, le classi <xref:System.Net.Security.SslStream> o <xref:System.Net.ServicePointManager> eseguono la convalida dell'oggetto identificatore (OID) dell'utilizzo chiavi avanzato (EKU). Un'estensione di utilizzo chiavi avanzato (EKU) è una raccolta di identificatori di oggetto (OID) che indica le applicazioni che usano la chiave. La convalida dell'OID EKU usa callback del certificato remoto per assicurarsi che il certificato remoto abbia gli OID corretti per lo scopo previsto.|
|Suggerimento|Se questa modifica non è opportuna, è possibile disabilitare la convalida dell'OID EKU del certificato aggiungendo l'opzione seguente a [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) nella sezione [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) del file di configurazione dell'app:<pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontCheckCertificateEKUs=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Questa impostazione è disponibile solo per la compatibilità con le versioni precedenti. Il suo uso non è altrimenti consigliato.</blockquote> |
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Ridestinazione|
|API interessate|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|

