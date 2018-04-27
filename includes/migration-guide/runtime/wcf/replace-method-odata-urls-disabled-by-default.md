### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a>Il metodo Replace negli URL OData è disabilitato per impostazione predefinita

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, il metodo Replace negli URL OData è disabilitato per impostazione predefinita. Quando il metodo Replace è disabilitato per OData, ora per impostazione predefinita, le eventuali richieste utente che includono funzioni di sostituzione (non comuni) avranno esito negativo.|
|Suggerimento|Se il metodo Replace è necessario (situazione non comune) è possibile riabilitarlo tramite le impostazioni di configurazione (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>). L'abilitazione di un metodo Replace, tuttavia, può introdurre vulnerabilità per la sicurezza ed è consigliabile usarlo solo dopo attente valutazioni.|
|Ambito|Microsoft Edge|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|

