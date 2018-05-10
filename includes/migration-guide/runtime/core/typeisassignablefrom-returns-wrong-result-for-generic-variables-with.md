### <a name="typeisassignablefrom-returns-wrong-result-for-generic-variables-with-constraints"></a>Type.IsAssignableFrom restituisce un risultato errato per le variabili generiche con vincoli

|   |   |
|---|---|
|Dettagli|In .NET Framework 4.5 <xref:System.Type.IsAssignableFrom(System.Type)> restituisce erroneamente <code>false</code> in tutti i casi per alcuni tipi generici con vincoli.|
|Suggerimento|Questo problema è stato risolto in un aggiornamento di manutenzione. Per risolvere questo problema, aggiornare .NET Framework 4.5 o eseguire l'aggiornamento a .NET Framework 4.5.1 o versioni successive. In alternativa, evitare di usare IsAssignableFrom con tipi generici che hanno vincoli su parametri generici. Le API reflection possono essere usate come alternativa.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Type.IsAssignableFrom(System.Type)?displayProperty=nameWithType></li></ul>|
|Analizzatori|<ul><li>CD0089</li></ul>|

