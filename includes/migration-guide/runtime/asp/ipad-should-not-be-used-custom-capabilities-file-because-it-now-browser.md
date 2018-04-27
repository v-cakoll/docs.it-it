### <a name="ipad-should-not-be-used-in-custom-capabilities-file-because-it-is-now-a-browser-capability"></a>IPad non deve essere usato nel file di funzionalità personalizzato perché ora è una funzionalità del browser

|   |   |
|---|---|
|Dettagli|A partire da .NET 4.5, iPad è un identificatore nel file di funzionalità del browser predefinito di ASP.NET, quindi non deve essere usato in un file di funzionalità personalizzato|
|Suggerimento|Se sono richieste funzionalità specifiche per iPad, è necessario modificare il comportamento di iPad impostando le funzionalità sul refID &quot;IPad&quot; predefinito del gateway anziché generando un nuovo ID &quot;IPad&quot; in base alla corrispondenza dell'agente utente.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|

