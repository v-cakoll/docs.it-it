### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>Il rendering delle finestre WPF viene eseguito senza ritaglio quando le finestre si estendono oltre un singolo monitor

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6 in esecuzione su Windows 8 e versioni successive viene eseguito il rendering dell'intera finestra senza ritaglio quando la finestra si estende al di fuori di un singolo schermo in uno scenario d'uso di più monitor. Questo comportamento è diverso rispetto a quello delle versioni precedenti di .NET Framework in cui le finestre WPF che si estendevano oltre un singolo schermo venivano ritagliate.|
|Suggerimento|Questo funzionamento (applicazione o non applicazione del ritaglio) può essere impostato esplicitamente tramite l'elemento <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> in <code>&lt;appSettings&gt;</code> nel file di configurazione di un'applicazione oppure impostando la proprietà <code>EnableMultiMonitorDisplayClipping</code> all'avvio dell'app.|
|Ambito|Secondario|
|Versione|4.6|
|Tipo|Runtime|

