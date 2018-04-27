### <a name="unicode-standard-version-80-categories-now-supported"></a>Le categorie dello standard Unicode versione 8.0 sono ora supportate

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.6.2 i dati Unicode nel framework sono stati aggiornati dallo standard Unicode versione 6.3 alla versione 8.0.  Quando si richiede la categoria di caratteri Unicode in .NET Framework 4.6.2, alcuni risultati potrebbero non corrispondere ai risultati ottenuti nelle versioni precedenti di .NET Framework.  Questa modifica interessa principalmente le sillabe Cherokee e i simboli delle vocali e dei toni di Tai Lue semplificato.|
|Suggerimento|Esaminare il codice e rimuovere o modificare la logica che dipende dalle categorie di caratteri Unicode hardcoded.|
|Ambito|Secondario|
|Versione|4.6.2|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

