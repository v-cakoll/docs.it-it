### <a name="xml-schema-validation-is-stricter"></a>La convalida di XML Schema è più rigida

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 la convalida XML Schema è più rigida. Se si usa xsd:anyURI per convalidare un URI, come un protocollo mailto, la convalida ha esito negativo se sono presenti spazi nell'URI. Nelle versioni precedenti di .NET Framework la convalida aveva esito positivo. La modifica influisce solo sulle applicazioni destinate a .NET Framework 4.5.|
|Suggerimento|Se è necessario usare la convalida .NET Framework 4.0 meno restrittiva, l'applicazione da convalidare può essere destinata alla versione 4.0 di .NET Framework. Tuttavia, con il reindirizzamento a .NET 4.5 è necessario effettuare una revisione del codice per assicurarsi che gli URI non validi (con spazi) non siano previsti come valori di attributo con il tipo di dati anyURI.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Ridestinazione|

