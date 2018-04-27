### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET non supporta più la qualificazione parziale dello spazio dei nomi per le API System.Windows

|   |   |
|---|---|
|Dettagli|A partire da .NET 4.5.2, i progetti VB.NET non possono specificare API System.Windows con spazi dei nomi parzialmente qualificati. Ad esempio, un riferimento a <code>Windows.Forms.DialogResult</code> avrà esito negativo. Il codice deve invece fare riferimento al nome completo (<xref:System.Windows.Forms.DialogResult>) o importare lo spazio dei nomi specifico e fare semplicemente riferimento a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.|
|Suggerimento|È consigliabile aggiornare il codice in modo che faccia riferimento alle API <code>System.Windows</code> tramite nomi semplici (e importare lo spazio dei nomi rilevante) o con nomi completi.|
|Ambito|Secondario|
|Versione|4.5.2|
|Tipo|Ridestinazione|

