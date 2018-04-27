### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>I codici di errore per maxRequestLength o maxReceivedMessageSize sono diversi

|   |   |
|---|---|
|Dettagli|I messaggi nei servizi Web WCF ospitati in Internet Information Services (IIS) o ASP.NET Development Server che superano maxRequestLength (in ASP.NET) o maxReceivedMessageSize (in WCF) hanno un codice di errore diverso. Il codice di stato HTTP è cambiato da 400 (Richiesta non valida) a 413 (Entità troppo grande) e i messaggi che superano la soglia impostata da maxRequestLength o da maxReceivedMessageSize generano un'eccezione <xref:System.ServiceModel.ProtocolException?displayProperty=name>. Sono inclusi i casi in cui la modalità di trasferimento è Streamed.|
|Suggerimento|Questa modifica semplifica il debug nei casi in cui la lunghezza del messaggio supera i limiti consentiti da ASP.NET o WCF. È necessario modificare qualsiasi codice che esegue l'elaborazione in base a un codice di stato HTTP 400.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|

